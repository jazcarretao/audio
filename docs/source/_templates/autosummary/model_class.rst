..
  autogenerated from source/_templates/autosummary/model_class.rst

.. currentmodule:: torchaudio.models

..

{%- set methods=["forward"] %}
{%- set helpers={
        "torchaudio.models.RNNTBeamSearch": [
            "Hypothesis",
        ],
    }
-%}
{%- set factory={
        "torchaudio.models.ConvTasNet": [
            "conv_tasnet_base",
        ],
        "torchaudio.models.Wav2Vec2Model": [
            "wav2vec2_model",
            "wav2vec2_base",
            "wav2vec2_large",
            "wav2vec2_large_lv60k",
            "wav2vec2_xlsr_300m",
            "wav2vec2_xlsr_1b",
            "wav2vec2_xlsr_2b",
            "hubert_base",
            "hubert_large",
            "hubert_xlarge",
            "wavlm_model",
            "wavlm_base",
            "wavlm_large",
        ],
        "torchaudio.models.HuBERTPretrainModel": [
            "hubert_pretrain_model",
            "hubert_pretrain_base",
            "hubert_pretrain_large",
            "hubert_pretrain_xlarge",
        ],
        "torchaudio.models.RNNT": [
            "emformer_rnnt_model",
            "emformer_rnnt_base",
        ],
        "torchaudio.models.HDemucs": [
            "hdemucs_low",
            "hdemucs_medium",
            "hdemucs_high",
        ],
    }
-%}
{%- set utils={
        "torchaudio.models.Wav2Vec2Model": [
            "~torchaudio.models.wav2vec2.utils.import_fairseq_model",
            "~torchaudio.models.wav2vec2.utils.import_huggingface_model",
        ]
    }
-%}

{%- if name in ["Wav2Vec2Model"] %}
  {{ methods.extend(["extract_features"]) }}
{%- elif name in ["Emformer", "RNNTBeamSearch", "WaveRNN", "Tacotron2", ] %}
  {{ methods.extend(["infer"]) }}
{%- elif name == "RNNT" %}
  {{ methods.extend(["transcribe_streaming", "transcribe", "predict", "join"]) }}
{%- endif %}

.. TITLE

{{ name | underline }}

.. CLASS DEFINITIONS

.. autoclass:: {{ fullname }}

Methods
=======

{% for item in methods %}

{{item | underline("-") }}

.. container:: py attribute

   .. automethod:: {{[fullname, item] | join('.')}}

{%- endfor %}

.. HELPER STRUCTURES

{%- if helpers[fullname] %}

Support Structures
==================

{%- for item in helpers[fullname] %}

{{item | underline("-") }}

.. container:: py attribute

   .. autodata:: {{["torchaudio.models", item] | join('.')}}
      :no-value:

{%- endfor %}

{%- endif %}

.. FACTORY FUNCTIONS

{%- if factory[fullname] %}

Factory Functions
=================

.. autosummary::
   :toctree: ../generated
   :nosignatures:

{% for item in factory[fullname] %}
   {{["~torchaudio.models", item] | join('.')}}
{%- endfor %}

{%- endif %}

.. UTILITY FUNCTIONS

{%- if utils[fullname] %}

Utility Functions
=================

.. autosummary::
   :toctree: ../generated
   :nosignatures:

{% for item in utils[fullname] %}
   {{ item }}
{%- endfor %}

{%- endif %}
