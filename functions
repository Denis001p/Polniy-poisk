import math


def degree(obj):
    corners = obj['boundedBy']['Envelope']
    left_bottom, right_upper = corners['lowerCorner'].split(), corners['upperCorner'].split()
    return str(abs((float(left_bottom[0]) - float(right_upper[0])) / 2)), \
           str(abs((float(left_bottom[1]) - float(right_upper[1])) / 2))


def lonlat_distance(a, b):
    degree_to_meters_factor = 111 * 1000
    a_lon, a_lat = a
    b_lon, b_lat = b
    
    radians_lattitude = math.radians((a_lat + b_lat) / 2.)
    lat_lon_factor = math.cos(radians_lattitude)

    dx = abs(a_lon - b_lon) * degree_to_meters_factor * lat_lon_factor
    dy = abs(a_lat - b_lat) * degree_to_meters_factor

    distance = math.sqrt(dx * dx + dy * dy)

    return distance
