/**
 * Simple code to add GET parameters to url.
 *
 * Tags:
 * Manipulate a url string by adding GET parameters
 * PHP: Adding parameters to a url?
 * How can I add GET variables to end of the current url in php
 * How to add url parameter to the current url?
 * php - add/update a parameter in a url
 *
 */

function addQueryArgs(array $args, string $url)
{
    if (filter_var($url, FILTER_VALIDATE_URL)) {
        $urlParts = parse_url($url);
        if (isset($urlParts['query'])) {
            parse_str($urlParts['query'], $urlQueryArgs);
            $urlParts['query'] = http_build_query(array_merge($urlQueryArgs, $args));
            $newUrl = $urlParts['scheme'] . '://' . $urlParts['host'] . $urlParts['path'] . '?' . $urlParts['query'];
        } else {
            $newUrl = $url . '?' . http_build_query($args);
        }
        return $newUrl;

    } else {
        return $url;
    }
}

$newUrl = addQueryArgs(array('add' => 'this', 'and' => 'this'), 'http://example.com/?have=others');
