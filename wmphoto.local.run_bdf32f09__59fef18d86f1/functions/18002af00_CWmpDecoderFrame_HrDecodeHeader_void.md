# CWmpDecoderFrame::HrDecodeHeader(void)

- ea: `0x18002af00`
- end: `0x18002bd5f`
- name: `?HrDecodeHeader@CWmpDecoderFrame@@MEAAJXZ`
- size: `3679`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ac90`

## callees

- `0x180010094`
- `0x180028870`
- `0x18002af00`
- `0x18002dbd0`
- `0x1800303a4`
- `0x1800363b0`
- `0x180036418`
- `0x18003ca60`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b63e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b63e`

## pseudocode

```c
__int64 __fastcall CWmpDecoderFrame::HrDecodeHeader(CWmpDecoderFrame *this)
{
  __int128 *v2; // r13
  HRESULT v3; // ebx
  int v4; // r12d
  int v5; // r15d
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int128 v23; // xmm0
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  int v27; // eax
  int v28; // edx
  const unsigned __int8 *v29; // rdx
  int v30; // eax
  char v31; // cl
  GUID v32; // xmm0
  unsigned int v33; // r8d
  __int64 v34; // rdx
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  int v38; // eax
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // rdx
  ULONGLONG v43; // rcx
  __int64 v44; // rdx
  int v45; // ecx
  int v46; // ecx
  GUID v47; // xmm0
  int v48; // eax
  int v49; // ebx
  __int64 v50; // rsi
  __int64 v51; // rcx
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  GUID v55; // xmm0
  char v56; // dl
  unsigned int v57; // ecx
  int v58; // eax
  __int128 v59; // [rsp+30h] [rbp-30h] BYREF
  __int128 *v60; // [rsp+40h] [rbp-20h]
  __int128 v61; // [rsp+48h] [rbp-18h] BYREF
  __int64 v62; // [rsp+58h] [rbp-8h]
  __int16 v63; // [rsp+A0h] [rbp+40h] BYREF
  ULONGLONG pullResult; // [rsp+A8h] [rbp+48h] BYREF

  v2 = 0;
  pullResult = 0;
  v3 = CWmpCodecBase::HrTestStateMinimum(this, 2);
  if ( v3 < 0 )
    goto LABEL_74;
  v4 = 0;
  v5 = 0;
  if ( !*((_DWORD *)this + 16689) )
  {
    v6 = *((_QWORD *)this + 8305);
    v62 = 0;
    v60 = 0;
    v61 = 0;
    LOWORD(v61) = 18;
    WORD4(v61) = -17278;
    v59 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v6 + 56LL))(v6, 0, &v61, &v59);
    v3 = v7;
    if ( v7 < 0 )
    {
      if ( v7 != -2003292352 )
        goto LABEL_74;
    }
    else
    {
      if ( (_WORD)v59 != 4 )
      {
LABEL_5:
        v3 = -2003292350;
        goto LABEL_74;
      }
      *((double *)this + 14) = *((float *)&v59 + 2);
    }
    v8 = *((_QWORD *)this + 8305);
    v62 = 0;
    v60 = 0;
    v61 = 0;
    LOWORD(v61) = 18;
    WORD4(v61) = -17277;
    v59 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v8 + 56LL))(v8, 0, &v61, &v59);
    v3 = v9;
    if ( v9 < 0 )
    {
      if ( v9 != -2003292352 )
        goto LABEL_74;
    }
    else
    {
      if ( (_WORD)v59 != 4 )
        goto LABEL_5;
      *((double *)this + 15) = *((float *)&v59 + 2);
    }
    v10 = *((_QWORD *)this + 8305);
    v62 = 0;
    v60 = 0;
    v61 = 0;
    LOWORD(v61) = 18;
    WORD4(v61) = -17280;
    v59 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v10 + 56LL))(
           v10,
           0,
           &v61,
           &v59);
    if ( v3 < 0 )
      goto LABEL_74;
    if ( (_WORD)v59 != 19 )
      goto LABEL_5;
    v11 = *((_QWORD *)this + 8305);
    v4 = DWORD2(v59);
    v62 = 0;
    v60 = 0;
    v61 = 0;
    LOWORD(v61) = 18;
    WORD4(v61) = -17279;
    v59 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v11 + 56LL))(
           v11,
           0,
           &v61,
           &v59);
    if ( v3 < 0 )
      goto LABEL_74;
    if ( (_WORD)v59 != 19 )
      goto LABEL_5;
    v12 = *((_QWORD *)this + 8305);
    v5 = DWORD2(v59);
    v62 = 0;
    v60 = 0;
    v61 = 0;
    LOWORD(v61) = 18;
    WORD4(v61) = -17216;
    v59 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v12 + 56LL))(
           v12,
           0,
           &v61,
           &v59);
    if ( v3 < 0 )
      goto LABEL_74;
    if ( (_WORD)v59 != 19 )
      goto LABEL_5;
    v13 = *((_QWORD *)this + 8305);
    *((_DWORD *)this + 32) = DWORD2(v59);
    v62 = 0;
    v60 = 0;
    v61 = 0;
    LOWORD(v61) = 18;
    WORD4(v61) = -17215;
    v59 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v13 + 56LL))(
           v13,
           0,
           &v61,
           &v59);
    if ( v3 < 0 )
      goto LABEL_74;
    if ( (_WORD)v59 != 19 )
      goto LABEL_5;
    v14 = *((_QWORD *)this + 8305);
    *((_DWORD *)this + 33) = DWORD2(v59);
    v62 = 0;
    v60 = 0;
    v61 = 0;
    WORD4(v61) = -17404;
    v59 = 0;
    LOWORD(v61) = 18;
    if ( (*(int (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v14 + 56LL))(v14, 0, &v61, &v59) < 0 )
    {
      v15 = 0;
    }
    else
    {
      if ( (_WORD)v59 != 19 )
        goto LABEL_5;
      v15 = BYTE8(v59) & 1;
    }
    *((_DWORD *)this + 16690) = v15;
    v16 = *((_QWORD *)this + 8305);
    v62 = 0;
    v60 = 0;
    v61 = 0;
    LOWORD(v61) = 18;
    WORD4(v61) = -17214;
    v59 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v16 + 56LL))(
            v16,
            0,
            &v61,
            &v59);
    v3 = v17;
    if ( v17 < 0 )
    {
      if ( v17 != -2003292352 )
        goto LABEL_74;
    }
    else
    {
      if ( (_WORD)v59 != 19 )
        goto LABEL_5;
      *((_DWORD *)this + 34) = DWORD2(v59);
    }
    v18 = *((_QWORD *)this + 8305);
    v62 = 0;
    v60 = 0;
    v61 = 0;
    LOWORD(v61) = 18;
    WORD4(v61) = -17213;
    v59 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v18 + 56LL))(
            v18,
            0,
            &v61,
            &v59);
    v3 = v19;
    if ( v19 < 0 )
    {
      if ( v19 != -2003292352 )
        goto LABEL_74;
    }
    else
    {
      if ( (_WORD)v59 != 19 )
        goto LABEL_5;
      *((_DWORD *)this + 35) = DWORD2(v59);
    }
    v20 = *((_QWORD *)this + 8305);
    v62 = 0;
    v60 = 0;
    v61 = 0;
    LOWORD(v61) = 18;
    WORD4(v61) = -30861;
    v59 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v20 + 56LL))(
            v20,
            0,
            &v61,
            &v59);
    v3 = v21;
    if ( v21 < 0 )
    {
      if ( v21 != -2003292352 )
        goto LABEL_74;
    }
    else
    {
      if ( (_WORD)v59 != 65 )
        goto LABEL_5;
      *((_QWORD *)this + 8306) = v60;
      *((_DWORD *)this + 16614) = DWORD2(v59);
    }
    v22 = *((_QWORD *)this + 8305);
    v62 = 0;
    v60 = 0;
    v61 = 0;
    LOWORD(v61) = 18;
    WORD4(v61) = -17407;
    v59 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v22 + 56LL))(
           v22,
           0,
           &v61,
           &v59);
    if ( v3 < 0 )
      goto LABEL_74;
    if ( (v59 & 0x1000) == 0 )
      goto LABEL_5;
    v2 = v60;
    if ( (_WORD)v59 != 4113 || DWORD2(v59) != 16 )
      goto LABEL_5;
    v23 = *v60;
    v62 = 0;
    v60 = 0;
    *(_OWORD *)((char *)this + 66476) = v23;
    v24 = *((_QWORD *)this + 8305);
    v61 = 0;
    LOWORD(v61) = 18;
    WORD4(v61) = -17406;
    v59 = 0;
    v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v24 + 56LL))(
            v24,
            0,
            &v61,
            &v59);
    v3 = v25;
    if ( v25 < 0 )
    {
      if ( v25 != -2003292352 )
        goto LABEL_74;
    }
    else
    {
      if ( (_WORD)v59 != 19 )
        goto LABEL_5;
      if ( DWORD2(v59) >= 8 )
      {
        v3 = -2003292317;
        goto LABEL_74;
      }
      *((_DWORD *)this + 16608) = DWORD2(v59);
    }
    v26 = *((_QWORD *)this + 8305);
    v62 = 0;
    v60 = 0;
    v61 = 0;
    LOWORD(v61) = 18;
    WORD4(v61) = -17405;
    v59 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v26 + 56LL))(
            v26,
            0,
            &v61,
            &v59);
    v3 = v27;
    if ( v27 < 0 )
    {
      if ( v27 != -2003292352 )
        goto LABEL_74;
    }
    else
    {
      if ( (_WORD)v59 != 19 )
        goto LABEL_5;
      if ( DWORD2(v59) )
      {
        v3 = -2147467263;
        goto LABEL_74;
      }
    }
    *((_OWORD *)this + 4156) = *(_OWORD *)((char *)this + 66476);
    v3 = WmpPixelLookupEx((CWmpDecoderFrame *)((char *)this + 66496), v28);
    if ( v3 < 0 )
      goto LABEL_74;
    v30 = *((_DWORD *)this + 16636) & 0x10;
    if ( !v30 || !*((_DWORD *)this + 34) || (v31 = 1, !*((_DWORD *)this + 35)) )
      v31 = 0;
    *((_BYTE *)this + 96) = v31;
    if ( v30 )
      v32 = GUID_WICPixelFormat32bppPBGRA;
    else
      v32 = GUID_WICPixelFormat32bppBGR;
    *(GUID *)((char *)this + 66460) = v32;
    *(_OWORD *)((char *)this + 24) = *(_OWORD *)((char *)this + 66476);
    if ( *(_QWORD *)((char *)this + 66476) == *(_QWORD *)&GUID_WICPixelFormat32bppBGR101010.Data1
      && *(_QWORD *)((char *)this + 66484) == *(_QWORD *)GUID_WICPixelFormat32bppBGR101010.Data4 )
    {
      v29 = (const unsigned __int8 *)*((_QWORD *)this + 8306);
      if ( v29 )
      {
        v33 = *((_DWORD *)this + 16614);
        if ( v33 )
        {
          v63 = 0;
          if ( (int)ICCInspector::Initialize((ICCInspector *)&v63, v29, v33) >= 0 )
          {
            if ( HIBYTE(v63) )
              *(GUID *)((char *)this + 24) = GUID_WICPixelFormat64bppRGBHalf;
          }
        }
      }
    }
    *(_OWORD *)((char *)this + 40) = *(_OWORD *)((char *)this + 24);
    v3 = WmpPixelLookupEx((CWmpDecoderFrame *)((char *)this + 40), (int)v29);
    if ( v3 < 0 )
      goto LABEL_74;
  }
  v34 = *((unsigned int *)this + 32);
  *((_QWORD *)this + 56) = (char *)this + 152;
  if ( (*((unsigned int (__fastcall **)(char *, __int64))this + 30))((char *)this + 152, v34)
    || (unsigned int)ImageStrDecGetInfo((char *)this + 256, (char *)this + 384) )
  {
    goto LABEL_68;
  }
  v35 = *((unsigned int *)this + 64);
  *((_DWORD *)this + 25) = v35;
  v36 = *((unsigned int *)this + 66);
  *((_DWORD *)this + 26) = v36;
  if ( *((_DWORD *)this + 16689) )
  {
    v46 = *((_DWORD *)this + 69);
    switch ( v46 )
    {
      case 0:
      case 15:
        v47 = GUID_WICPixelFormatBlackWhite;
        break;
      case 8:
        v47 = GUID_WICPixelFormat16bppBGR555;
        break;
      case 10:
        v47 = GUID_WICPixelFormat16bppBGR565;
        break;
      case 9:
        v47 = GUID_WICPixelFormat32bppBGR101010;
        break;
      default:
        v48 = *((_DWORD *)this + 68);
        v49 = *((_DWORD *)this + 8314);
        LODWORD(v36) = *((_DWORD *)this + 76);
        switch ( v46 )
        {
          case 7:
            if ( !v48 )
            {
              v47 = GUID_WICPixelFormat32bppGrayFloat;
              goto LABEL_173;
            }
            if ( v48 == 7 )
            {
              if ( v49 )
              {
                if ( (_DWORD)v36 )
                  v47 = GUID_WICPixelFormat128bppPRGBAFloat;
                else
                  v47 = GUID_WICPixelFormat128bppRGBAFloat;
              }
              else
              {
                v47 = GUID_WICPixelFormat128bppRGBFloat;
              }
              goto LABEL_173;
            }
            break;
          case 6:
            if ( !v48 )
            {
              v47 = GUID_WICPixelFormat32bppGrayFixedPoint;
              goto LABEL_173;
            }
            if ( v48 == 7 )
            {
              if ( v49 )
                v47 = GUID_WICPixelFormat128bppRGBAFixedPoint;
              else
                v47 = GUID_WICPixelFormat96bppRGBFixedPoint;
              goto LABEL_173;
            }
            break;
          case 4:
            if ( !v48 )
            {
              v47 = GUID_WICPixelFormat16bppGrayHalf;
              goto LABEL_173;
            }
            if ( v48 == 7 )
            {
              if ( v49 )
                v47 = GUID_WICPixelFormat64bppRGBAHalf;
              else
                v47 = GUID_WICPixelFormat48bppRGBHalf;
              goto LABEL_173;
            }
            break;
          case 3:
            if ( !v48 )
            {
              v47 = GUID_WICPixelFormat16bppGrayFixedPoint;
              goto LABEL_173;
            }
            if ( v48 == 7 )
            {
              if ( v49 )
                v47 = GUID_WICPixelFormat64bppRGBAFixedPoint;
              else
                v47 = GUID_WICPixelFormat48bppRGBFixedPoint;
              goto LABEL_173;
            }
            break;
          default:
            v50 = *((_QWORD *)this + 53);
            if ( v46 == 2 )
            {
              if ( v48 )
              {
                switch ( v48 )
                {
                  case 7:
                    if ( v49 )
                    {
                      if ( (_DWORD)v36 )
                        v47 = GUID_WICPixelFormat64bppPRGBA;
                      else
                        v47 = GUID_WICPixelFormat64bppRGBA;
                    }
                    else
                    {
                      v47 = GUID_WICPixelFormat48bppRGB;
                    }
                    break;
                  case 4:
                    if ( v49 )
                      v47 = GUID_WICPixelFormat80bppCMYKAlpha;
                    else
                      v47 = GUID_WICPixelFormat64bppCMYK;
                    break;
                  case 6:
                    LODWORD(v36) = tls_index;
                    if ( dword_18005060C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                       + (unsigned int)tls_index)
                                                     + 4LL) )
                    {
                      Init_thread_header(&dword_18005060C);
                      if ( dword_18005060C == -1 )
                      {
                        xmmword_1800503C0[0] = (__int128)GUID_WICPixelFormat48bpp3Channels;
                        xmmword_1800503D0 = (__int128)GUID_WICPixelFormat64bpp4Channels;
                        xmmword_1800503E0 = (__int128)GUID_WICPixelFormat80bpp5Channels;
                        xmmword_1800503F0 = (__int128)GUID_WICPixelFormat96bpp6Channels;
                        xmmword_180050400 = (__int128)GUID_WICPixelFormat112bpp7Channels;
                        xmmword_180050410 = (__int128)GUID_WICPixelFormat128bpp8Channels;
                        xmmword_180050420 = (__int128)GUID_WICPixelFormat64bpp3ChannelsAlpha;
                        xmmword_180050430 = (__int128)GUID_WICPixelFormat80bpp4ChannelsAlpha;
                        xmmword_180050440 = (__int128)GUID_WICPixelFormat96bpp5ChannelsAlpha;
                        xmmword_180050450 = (__int128)GUID_WICPixelFormat112bpp6ChannelsAlpha;
                        xmmword_180050460 = (__int128)GUID_WICPixelFormat128bpp7ChannelsAlpha;
                        xmmword_180050470 = (__int128)GUID_WICPixelFormat144bpp8ChannelsAlpha;
                        Init_thread_footer(&dword_18005060C);
                      }
                    }
                    if ( (unsigned __int64)(v50 - 3) > 5 )
                      goto LABEL_174;
                    v47 = (GUID)xmmword_1800503C0[(v49 != 0 ? 6 : 0) - 3 + v50];
                    break;
                  default:
                    goto LABEL_174;
                }
              }
              else
              {
                v47 = GUID_WICPixelFormat16bppGray;
              }
              goto LABEL_173;
            }
            if ( v46 == 1 )
            {
              if ( v48 )
              {
                switch ( v48 )
                {
                  case 8:
                    v47 = GUID_WICPixelFormat32bppRGBE;
                    break;
                  case 7:
                    if ( v49 )
                    {
                      if ( (_DWORD)v36 )
                        v47 = GUID_WICPixelFormat32bppPRGBA;
                      else
                        v47 = GUID_WICPixelFormat32bppRGBA;
                    }
                    else
                    {
                      v47 = GUID_WICPixelFormat24bppRGB;
                    }
                    break;
                  case 4:
                    if ( v49 )
                      v47 = GUID_WICPixelFormat40bppCMYKAlpha;
                    else
                      v47 = GUID_WICPixelFormat32bppCMYK;
                    break;
                  case 6:
                    LODWORD(v36) = tls_index;
                    if ( dword_180050608 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                       + (unsigned int)tls_index)
                                                     + 4LL) )
                    {
                      Init_thread_header(&dword_180050608);
                      if ( dword_180050608 == -1 )
                      {
                        xmmword_180050480[0] = (__int128)GUID_WICPixelFormat24bpp3Channels;
                        xmmword_180050490 = (__int128)GUID_WICPixelFormat32bpp4Channels;
                        xmmword_1800504A0 = (__int128)GUID_WICPixelFormat40bpp5Channels;
                        xmmword_1800504B0 = (__int128)GUID_WICPixelFormat48bpp6Channels;
                        xmmword_1800504C0 = (__int128)GUID_WICPixelFormat56bpp7Channels;
                        xmmword_1800504D0 = (__int128)GUID_WICPixelFormat64bpp8Channels;
                        xmmword_1800504E0 = (__int128)GUID_WICPixelFormat32bpp3ChannelsAlpha;
                        xmmword_1800504F0 = (__int128)GUID_WICPixelFormat40bpp4ChannelsAlpha;
                        xmmword_180050500 = (__int128)GUID_WICPixelFormat48bpp5ChannelsAlpha;
                        xmmword_180050510 = (__int128)GUID_WICPixelFormat56bpp6ChannelsAlpha;
                        xmmword_180050520 = (__int128)GUID_WICPixelFormat64bpp7ChannelsAlpha;
                        xmmword_180050530 = (__int128)GUID_WICPixelFormat72bpp8ChannelsAlpha;
                        Init_thread_footer(&dword_180050608);
                      }
                    }
                    if ( (unsigned __int64)(v50 - 3) > 5 )
                      goto LABEL_174;
                    v47 = (GUID)xmmword_180050480[(v49 != 0 ? 6 : 0) - 3 + v50];
                    break;
                  default:
                    goto LABEL_174;
                }
              }
              else
              {
                v47 = GUID_WICPixelFormat8bppGray;
              }
              goto LABEL_173;
            }
            break;
        }
LABEL_174:
        *(_OWORD *)((char *)this + 40) = *(_OWORD *)((char *)this + 24);
        v3 = WmpPixelLookupEx((CWmpDecoderFrame *)((char *)this + 40), v36);
        if ( v3 < 0 )
          goto LABEL_74;
        v52 = *(_OWORD *)((char *)this + 24);
        *((_BYTE *)this + 96) = 0;
        v53 = *(_OWORD *)(v51 + 16);
        *(_OWORD *)((char *)this + 66476) = v52;
        *((_OWORD *)this + 4156) = *(_OWORD *)v51;
        v54 = *(_OWORD *)(v51 + 32);
        *((_OWORD *)this + 4157) = v53;
        *(_QWORD *)&v53 = *(_QWORD *)(v51 + 48);
        *((_OWORD *)this + 4158) = v54;
        *((_QWORD *)this + 8318) = v53;
        if ( (*((_BYTE *)this + 66544) & 0x10) != 0 )
          v55 = GUID_WICPixelFormat32bppPBGRA;
        else
          v55 = GUID_WICPixelFormat32bppBGR;
        *(GUID *)((char *)this + 66460) = v55;
        goto LABEL_179;
    }
LABEL_173:
    *(GUID *)((char *)this + 24) = v47;
    goto LABEL_174;
  }
  if ( (_DWORD)v35 == v4 )
  {
    if ( (_DWORD)v36 != v5 )
    {
LABEL_73:
      v3 = -2003292319;
      goto LABEL_74;
    }
  }
  else if ( (_DWORD)v35 != v5 || (_DWORD)v36 != v4 )
  {
    goto LABEL_73;
  }
  v38 = *((_DWORD *)this + 68);
  if ( v38 != *((_DWORD *)this + 16630) && v38 != *((_DWORD *)this + 16631)
    || *((_DWORD *)this + 69) != *((_DWORD *)this + 16632) )
  {
    goto LABEL_73;
  }
  v39 = v35;
  v40 = v35 + 15;
  if ( v40 < v39 || (v41 = v36, v42 = v36 + 15, v42 < v41) )
  {
    v3 = -2147024362;
    goto LABEL_74;
  }
  v3 = ULongLongMult(v40 & 0xFFFFFFFFFFFFFFF0uLL, v42 & 0xFFFFFFFFFFFFFFF0uLL, &pullResult);
  if ( v3 >= 0 )
  {
    v43 = *((unsigned int *)this + 33);
    if ( (_DWORD)v43 && v43 <= pullResult >> 12 || v43 >> 7 >= pullResult )
    {
      v3 = -2003292320;
      goto LABEL_74;
    }
    if ( !*((_BYTE *)this + 96) )
    {
LABEL_95:
      if ( (*((_BYTE *)this + 66432) & 4) != 0 )
      {
        v45 = *((_DWORD *)this + 25);
        *((_DWORD *)this + 25) = *((_DWORD *)this + 26);
        *((_QWORD *)this + 15) = *((_QWORD *)this + 14);
        *((_DWORD *)this + 26) = v45;
      }
LABEL_179:
      v56 = *((_BYTE *)this + 96);
      v57 = *((_DWORD *)this + 109);
      if ( v56 && *((_DWORD *)this + 8365) < (signed int)v57 )
        v57 = *((_DWORD *)this + 8365);
      if ( v57 > 3 )
        goto LABEL_73;
      v3 = 0;
      v58 = 4 - v57;
      *((_DWORD *)this + 16692) = 4 - v57;
      if ( v57 == 0 )
      {
        *((_DWORD *)this + 16692) = 3;
        v58 = 3;
      }
      if ( !*((_DWORD *)this + 104) || v56 && !*((_DWORD *)this + 8360) )
      {
        *((_DWORD *)this + 16692) = 1;
        v58 = 1;
      }
      *((_DWORD *)this + 16693) = v58 - 1;
      goto LABEL_74;
    }
    v44 = *((unsigned int *)this + 34);
    *((_QWORD *)this + 4184) = (char *)this + 152;
    if ( !(*((unsigned int (__fastcall **)(char *, __int64))this + 30))((char *)this + 152, v44)
      && !(unsigned int)ImageStrDecGetInfo((char *)this + 33280, (char *)this + 33408) )
    {
      if ( *((_QWORD *)this + 4160) != *((_DWORD *)this + 25)
        || *((_QWORD *)this + 4161) != *((_DWORD *)this + 26)
        || *((_DWORD *)this + 8324)
        || *((_DWORD *)this + 8325) != *((_DWORD *)this + 16632)
        || *((_QWORD *)this + 4181) != 1 )
      {
        goto LABEL_73;
      }
      goto LABEL_95;
    }
LABEL_68:
    v3 = -2147467259;
  }
LABEL_74:
  CoTaskMemFree(v2);
  *((_DWORD *)this + 4) = ((v3 >> 31) & 0xFFFFFFFD) + 3;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002af00  mov     [rsp-38h+arg_10], rbx
0x18002af05  push    rbp
0x18002af06  push    rsi
0x18002af07  push    rdi
0x18002af08  push    r12
0x18002af0a  push    r13
0x18002af0c  push    r14
0x18002af0e  push    r15
0x18002af10  mov     rbp, rsp
0x18002af13  sub     rsp, 60h
0x18002af17  xor     esi, esi
0x18002af19  mov     rdi, rcx
0x18002af1c  mov     r13d, esi
0x18002af1f  mov     [rbp+pullResult], rsi
0x18002af23  lea     edx, [rsi+2]; int
0x18002af26  call    ?HrTestStateMinimum@CWmpCodecBase@@UEAAJH@Z; CWmpCodecBase::HrTestStateMinimum(int)
0x18002af2b  mov     ebx, eax
0x18002af2d  test    eax, eax
0x18002af2f  js      loc_18002B63B
0x18002af35  mov     r12d, esi
0x18002af38  mov     r15d, esi
0x18002af3b  cmp     [rdi+104C4h], esi
0x18002af41  jnz     loc_18002B5D0
0x18002af47  mov     rcx, [rdi+10388h]
0x18002af4e  lea     r15d, [rsi+12h]
0x18002af52  xor     eax, eax
0x18002af54  lea     r9, [rbp+var_30]
0x18002af58  mov     [rbp+var_8], rax
0x18002af5c  lea     r8, [rbp+var_18]
0x18002af60  mov     [rbp+var_20], rax
0x18002af64  xorps   xmm0, xmm0
0x18002af67  movups  [rbp+var_18], xmm0
0x18002af6b  mov     eax, 0BC82h
0x18002af70  mov     word ptr [rbp+var_18], r15w
0x18002af75  mov     word ptr [rbp+var_18+8], ax
0x18002af79  xorps   xmm1, xmm1
0x18002af7c  movups  [rbp+var_30], xmm1
0x18002af80  mov     rax, [rcx]
0x18002af83  xor     edx, edx
0x18002af85  mov     rax, [rax+38h]
0x18002af89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af8e  mov     ebx, eax
0x18002af90  mov     r14d, 88982F40h
0x18002af96  test    eax, eax
0x18002af98  js      short loc_18002AFBE
0x18002af9a  lea     r12d, [rsi+4]
0x18002af9e  cmp     r12w, word ptr [rbp+var_30]
0x18002afa3  jz      short loc_18002AFAF
0x18002afa5  mov     ebx, 88982F42h
0x18002afaa  jmp     loc_18002B63B
0x18002afaf  movss   xmm0, dword ptr [rbp+var_30+8]
0x18002afb4  cvtps2pd xmm0, xmm0
0x18002afb7  movsd   qword ptr [rdi+70h], xmm0
0x18002afbc  jmp     short loc_18002AFCD
0x18002afbe  cmp     eax, r14d
0x18002afc1  jnz     loc_18002B63B
0x18002afc7  mov     r12d, 4
0x18002afcd  mov     rcx, [rdi+10388h]
0x18002afd4  lea     r9, [rbp+var_30]
0x18002afd8  xor     eax, eax
0x18002afda  lea     r8, [rbp+var_18]
0x18002afde  mov     [rbp+var_8], rax
0x18002afe2  xorps   xmm0, xmm0
0x18002afe5  mov     [rbp+var_20], rax
0x18002afe9  xorps   xmm1, xmm1
0x18002afec  movups  [rbp+var_18], xmm0
0x18002aff0  mov     eax, 0BC83h
0x18002aff5  mov     word ptr [rbp+var_18], r15w
0x18002affa  mov     word ptr [rbp+var_18+8], ax
0x18002affe  xor     edx, edx
0x18002b000  movups  [rbp+var_30], xmm1
0x18002b004  mov     rax, [rcx]
0x18002b007  mov     rax, [rax+38h]
0x18002b00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b010  mov     ebx, eax
0x18002b012  test    eax, eax
0x18002b014  js      short loc_18002B02C
0x18002b016  cmp     r12w, word ptr [rbp+var_30]
0x18002b01b  jnz     short loc_18002AFA5
0x18002b01d  movss   xmm0, dword ptr [rbp+var_30+8]
0x18002b022  cvtps2pd xmm0, xmm0
0x18002b025  movsd   qword ptr [rdi+78h], xmm0
0x18002b02a  jmp     short loc_18002B035
0x18002b02c  cmp     eax, r14d
0x18002b02f  jnz     loc_18002B63B
0x18002b035  mov     rcx, [rdi+10388h]
0x18002b03c  lea     r9, [rbp+var_30]
0x18002b040  xor     eax, eax
0x18002b042  lea     r8, [rbp+var_18]
0x18002b046  mov     [rbp+var_8], rax
0x18002b04a  xorps   xmm0, xmm0
0x18002b04d  mov     [rbp+var_20], rax
0x18002b051  xorps   xmm1, xmm1
0x18002b054  movups  [rbp+var_18], xmm0
0x18002b058  mov     eax, 0BC80h
0x18002b05d  mov     word ptr [rbp+var_18], r15w
0x18002b062  mov     word ptr [rbp+var_18+8], ax
0x18002b066  xor     edx, edx
0x18002b068  movups  [rbp+var_30], xmm1
0x18002b06c  mov     rax, [rcx]
0x18002b06f  mov     rax, [rax+38h]
0x18002b073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b078  mov     ebx, eax
0x18002b07a  test    eax, eax
0x18002b07c  js      loc_18002B63B
0x18002b082  mov     r14d, 13h
0x18002b088  cmp     r14w, word ptr [rbp+var_30]
0x18002b08d  jnz     loc_18002AFA5
0x18002b093  mov     rcx, [rdi+10388h]
0x18002b09a  lea     r9, [rbp+var_30]
0x18002b09e  mov     r12d, dword ptr [rbp+var_30+8]
0x18002b0a2  lea     r8, [rbp+var_18]
0x18002b0a6  xor     eax, eax
0x18002b0a8  xorps   xmm0, xmm0
0x18002b0ab  mov     [rbp+var_8], rax
0x18002b0af  xorps   xmm1, xmm1
0x18002b0b2  mov     [rbp+var_20], rax
0x18002b0b6  xor     edx, edx
0x18002b0b8  movups  [rbp+var_18], xmm0
0x18002b0bc  mov     eax, 0BC81h
0x18002b0c1  mov     word ptr [rbp+var_18], r15w
0x18002b0c6  mov     word ptr [rbp+var_18+8], ax
0x18002b0ca  movups  [rbp+var_30], xmm1
0x18002b0ce  mov     rax, [rcx]
0x18002b0d1  mov     rax, [rax+38h]
0x18002b0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0da  mov     ebx, eax
0x18002b0dc  test    eax, eax
0x18002b0de  js      loc_18002B63B
0x18002b0e4  cmp     r14w, word ptr [rbp+var_30]
0x18002b0e9  jnz     loc_18002AFA5
0x18002b0ef  mov     rcx, [rdi+10388h]
0x18002b0f6  lea     r9, [rbp+var_30]
0x18002b0fa  mov     r15d, dword ptr [rbp+var_30+8]
0x18002b0fe  lea     r8, [rbp+var_18]
0x18002b102  xor     eax, eax
0x18002b104  xorps   xmm0, xmm0
0x18002b107  mov     [rbp+var_8], rax
0x18002b10b  xorps   xmm1, xmm1
0x18002b10e  mov     [rbp+var_20], rax
0x18002b112  xor     edx, edx
0x18002b114  movups  [rbp+var_18], xmm0
0x18002b118  lea     eax, [r14-1]
0x18002b11c  mov     word ptr [rbp+var_18], ax
0x18002b120  mov     eax, 0BCC0h
0x18002b125  mov     word ptr [rbp+var_18+8], ax
0x18002b129  movups  [rbp+var_30], xmm1
0x18002b12d  mov     rax, [rcx]
0x18002b130  mov     rax, [rax+38h]
0x18002b134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b139  mov     ebx, eax
0x18002b13b  test    eax, eax
0x18002b13d  js      loc_18002B63B
0x18002b143  cmp     r14w, word ptr [rbp+var_30]
0x18002b148  jnz     loc_18002AFA5
0x18002b14e  mov     eax, dword ptr [rbp+var_30+8]
0x18002b151  lea     r9, [rbp+var_30]
0x18002b155  mov     rcx, [rdi+10388h]
0x18002b15c  lea     r8, [rbp+var_18]
0x18002b160  mov     [rdi+80h], eax
0x18002b166  xorps   xmm0, xmm0
0x18002b169  xor     eax, eax
0x18002b16b  xorps   xmm1, xmm1
0x18002b16e  mov     [rbp+var_8], rax
0x18002b172  xor     edx, edx
0x18002b174  mov     [rbp+var_20], rax
0x18002b178  lea     eax, [r14-1]
0x18002b17c  movups  [rbp+var_18], xmm0
0x18002b180  mov     word ptr [rbp+var_18], ax
0x18002b184  mov     eax, 0BCC1h
0x18002b189  mov     word ptr [rbp+var_18+8], ax
0x18002b18d  movups  [rbp+var_30], xmm1
0x18002b191  mov     rax, [rcx]
0x18002b194  mov     rax, [rax+38h]
0x18002b198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b19d  mov     ebx, eax
0x18002b19f  test    eax, eax
0x18002b1a1  js      loc_18002B63B
0x18002b1a7  cmp     r14w, word ptr [rbp+var_30]
0x18002b1ac  jnz     loc_18002AFA5
0x18002b1b2  mov     eax, dword ptr [rbp+var_30+8]
0x18002b1b5  lea     r9, [rbp+var_30]
0x18002b1b9  mov     rcx, [rdi+10388h]
0x18002b1c0  lea     r8, [rbp+var_18]
0x18002b1c4  mov     [rdi+84h], eax
0x18002b1ca  xorps   xmm0, xmm0
0x18002b1cd  xor     eax, eax
0x18002b1cf  xorps   xmm1, xmm1
0x18002b1d2  mov     [rbp+var_8], rax
0x18002b1d6  xor     edx, edx
0x18002b1d8  mov     [rbp+var_20], rax
0x18002b1dc  movups  [rbp+var_18], xmm0
0x18002b1e0  lea     ebx, [rax+12h]
0x18002b1e3  mov     eax, 0BC04h
0x18002b1e8  mov     word ptr [rbp+var_18+8], ax
0x18002b1ec  movups  [rbp+var_30], xmm1
0x18002b1f0  mov     word ptr [rbp+var_18], bx
0x18002b1f4  mov     rax, [rcx]
0x18002b1f7  mov     rax, [rax+38h]
0x18002b1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b200  test    eax, eax
0x18002b202  js      short loc_18002B217
0x18002b204  cmp     r14w, word ptr [rbp+var_30]
0x18002b209  jnz     loc_18002AFA5
0x18002b20f  mov     eax, dword ptr [rbp+var_30+8]
0x18002b212  and     eax, 1
0x18002b215  jmp     short loc_18002B219
0x18002b217  mov     eax, esi
0x18002b219  mov     [rdi+104C8h], eax
0x18002b21f  lea     r9, [rbp+var_30]
0x18002b223  mov     rcx, [rdi+10388h]
0x18002b22a  lea     r8, [rbp+var_18]
0x18002b22e  xor     eax, eax
0x18002b230  xorps   xmm0, xmm0
0x18002b233  mov     [rbp+var_8], rax
0x18002b237  xorps   xmm1, xmm1
0x18002b23a  mov     [rbp+var_20], rax
0x18002b23e  xor     edx, edx
0x18002b240  movups  [rbp+var_18], xmm0
0x18002b244  mov     eax, 0BCC2h
0x18002b249  mov     word ptr [rbp+var_18], bx
0x18002b24d  mov     word ptr [rbp+var_18+8], ax
0x18002b251  movups  [rbp+var_30], xmm1
0x18002b255  mov     rax, [rcx]
0x18002b258  mov     rax, [rax+38h]
0x18002b25c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b261  mov     ebx, eax
0x18002b263  test    eax, eax
0x18002b265  js      short loc_18002B27D
0x18002b267  cmp     r14w, word ptr [rbp+var_30]
0x18002b26c  jnz     loc_18002AFA5
0x18002b272  mov     eax, dword ptr [rbp+var_30+8]
0x18002b275  mov     [rdi+88h], eax
0x18002b27b  jmp     short loc_18002B288
0x18002b27d  cmp     eax, 88982F40h
0x18002b282  jnz     loc_18002B63B
0x18002b288  mov     rcx, [rdi+10388h]
0x18002b28f  lea     r9, [rbp+var_30]
0x18002b293  xor     eax, eax
0x18002b295  lea     r8, [rbp+var_18]
0x18002b299  mov     [rbp+var_8], rax
0x18002b29d  xorps   xmm0, xmm0
0x18002b2a0  mov     [rbp+var_20], rax
0x18002b2a4  xorps   xmm1, xmm1
0x18002b2a7  movups  [rbp+var_18], xmm0
0x18002b2ab  mov     eax, 12h
0x18002b2b0  xor     edx, edx
0x18002b2b2  mov     word ptr [rbp+var_18], ax
0x18002b2b6  mov     eax, 0BCC3h
0x18002b2bb  mov     word ptr [rbp+var_18+8], ax
0x18002b2bf  movups  [rbp+var_30], xmm1
0x18002b2c3  mov     rax, [rcx]
0x18002b2c6  mov     rax, [rax+38h]
0x18002b2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2cf  mov     ebx, eax
0x18002b2d1  test    eax, eax
0x18002b2d3  js      short loc_18002B2EB
0x18002b2d5  cmp     r14w, word ptr [rbp+var_30]
0x18002b2da  jnz     loc_18002AFA5
0x18002b2e0  mov     eax, dword ptr [rbp+var_30+8]
0x18002b2e3  mov     [rdi+8Ch], eax
0x18002b2e9  jmp     short loc_18002B2F6
0x18002b2eb  cmp     eax, 88982F40h
0x18002b2f0  jnz     loc_18002B63B
0x18002b2f6  mov     rcx, [rdi+10388h]
0x18002b2fd  lea     r9, [rbp+var_30]
0x18002b301  xor     eax, eax
0x18002b303  lea     r8, [rbp+var_18]
0x18002b307  mov     [rbp+var_8], rax
0x18002b30b  xorps   xmm0, xmm0
0x18002b30e  mov     [rbp+var_20], rax
0x18002b312  xorps   xmm1, xmm1
0x18002b315  movups  [rbp+var_18], xmm0
0x18002b319  mov     eax, 12h
0x18002b31e  xor     edx, edx
0x18002b320  mov     word ptr [rbp+var_18], ax
0x18002b324  mov     eax, 8773h
0x18002b329  mov     word ptr [rbp+var_18+8], ax
0x18002b32d  movups  [rbp+var_30], xmm1
0x18002b331  mov     rax, [rcx]
0x18002b334  mov     rax, [rax+38h]
0x18002b338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b33d  mov     ebx, eax
0x18002b33f  test    eax, eax
0x18002b341  js      short loc_18002B368
0x18002b343  mov     eax, 41h ; 'A'
0x18002b348  cmp     ax, word ptr [rbp+var_30]
0x18002b34c  jnz     loc_18002AFA5
0x18002b352  mov     rax, [rbp+var_20]
0x18002b356  mov     [rdi+10390h], rax
0x18002b35d  mov     eax, dword ptr [rbp+var_30+8]
0x18002b360  mov     [rdi+10398h], eax
0x18002b366  jmp     short loc_18002B373
0x18002b368  cmp     eax, 88982F40h
0x18002b36d  jnz     loc_18002B63B
0x18002b373  mov     rcx, [rdi+10388h]
0x18002b37a  lea     r9, [rbp+var_30]
0x18002b37e  xor     eax, eax
0x18002b380  lea     r8, [rbp+var_18]
0x18002b384  mov     [rbp+var_8], rax
  ... truncated ...
```
