mport streamlit as st
import pandas as pd
from openbb_terminal.sdk import openbb
from openbb_terminal.config_terminal import theme  # noqa: F401
from openbb_terminal.helper_classes import TerminalStyle
from openbb_terminal import helper_funcs as helper  # noqa: F401
from openbb_terminal.reports import widget_helpers as widgets  # noqa: F401
from openbb_terminal.cryptocurrency.due_diligence.pycoingecko_model import (  # noqa: F401
    Coin,
)
from openbb_terminal.core.library.breadcrumb import Breadcrumb
from openbb_terminal.core.library.trail_map import TrailMap
from openbb_terminal.core.library.breadcrumb import MetadataBuilder

TerminalStyle().applyMPLstyle()
trail = ""
trail_map = TrailMap()
metadata = MetadataBuilder.build(trail=trail, trail_map=trail_map)
backgroundColor='#FFFFFF'


openbb = Breadcrumb(
    metadata=metadata,
    trail=trail,
    trail_map=trail_map,
)

#st.markdown('<style>body{background-color: Black;}</style>', unsafe_allow_html=True)
st.set_page_config(layout="wide")
st.set_option('deprecation.showPyplotGlobalUse', False)


def color_negative_red(val):
    if type(val) != 'str':
        color = 'green' if val > 0 else 'red'
        return f'color: {color}'

def color_positive_red(val):
    if type(val) != 'str':
        color = 'red' if val > 0 else 'green'
        return f'color: {color}'

col1, col2, col3 = st.columns([30, 30, 30])
with col1:
    st.subheader('Global Bonds')
    st.dataframe(openbb.economy.glbonds())
