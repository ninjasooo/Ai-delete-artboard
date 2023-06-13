# Ai-delete-artboard
delete a specific artboard on adobe illustrator

#target illustrator

function test() {
    var doc = app.activeDocument, thisBoard, selectedObjects;
    doc.selection = null;
    for (var i = doc.artboards.length - 1; i >= 0; i--) {
        thisBoard = doc.artboards[i];
        if (doc.artboards.length > 1) {
            doc.artboards.setActiveArtboardIndex(i);
            selectedObjects = doc.selectObjectsOnActiveArtboard();
            if (doc.selection.length < 1 || doc.selection == null) {
                thisBoard.remove();
            }
        }
    }
};

test();
