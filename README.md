# technotrack-NN2021S-HW
Here I posted the homework that I did on the course [technotrack](https://github.com/mailcourses/technotrack-NN2021S-lectures)
function Div(el)
    if not el.attr or not contains('spoiler', el.attr.classes) then
        return el
    end

    local title = el.attr.attributes['title'] or 'Спойлер'
    table.insert(el.content, 1,
        pandoc.RawBlock('html', '<' .. 'spoiler title="' .. title .. '">', 'RawBlock'))
    table.insert(el.content,
        pandoc.RawBlock('html', '<' .. '/spoiler>', 'RawBlock'))
    return el.content
end
