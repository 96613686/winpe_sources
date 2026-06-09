# CWmpDecoderFrame::HrDecodeHeader(void)

- ea: `0x18002b180`
- end: `0x18002bfe6`
- name: `?HrDecodeHeader@CWmpDecoderFrame@@MEAAJXZ`
- size: `3686`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ae40`

## callees

- `0x18001022c`
- `0x18002b160`
- `0x18002b180`
- `0x18002ded0`
- `0x180030800`
- `0x180036980`
- `0x1800369e8`
- `0x18003d270`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b8be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b8be`

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
                    if ( dword_18005160C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                       + (unsigned int)tls_index)
                                                     + 4LL) )
                    {
                      Init_thread_header(&dword_18005160C);
                      if ( dword_18005160C == -1 )
                      {
                        xmmword_1800513C0[0] = (__int128)GUID_WICPixelFormat48bpp3Channels;
                        xmmword_1800513D0 = (__int128)GUID_WICPixelFormat64bpp4Channels;
                        xmmword_1800513E0 = (__int128)GUID_WICPixelFormat80bpp5Channels;
                        xmmword_1800513F0 = (__int128)GUID_WICPixelFormat96bpp6Channels;
                        xmmword_180051400 = (__int128)GUID_WICPixelFormat112bpp7Channels;
                        xmmword_180051410 = (__int128)GUID_WICPixelFormat128bpp8Channels;
                        xmmword_180051420 = (__int128)GUID_WICPixelFormat64bpp3ChannelsAlpha;
                        xmmword_180051430 = (__int128)GUID_WICPixelFormat80bpp4ChannelsAlpha;
                        xmmword_180051440 = (__int128)GUID_WICPixelFormat96bpp5ChannelsAlpha;
                        xmmword_180051450 = (__int128)GUID_WICPixelFormat112bpp6ChannelsAlpha;
                        xmmword_180051460 = (__int128)GUID_WICPixelFormat128bpp7ChannelsAlpha;
                        xmmword_180051470 = (__int128)GUID_WICPixelFormat144bpp8ChannelsAlpha;
                        Init_thread_footer(&dword_18005160C);
                      }
                    }
                    if ( (unsigned __int64)(v50 - 3) > 5 )
                      goto LABEL_174;
                    v47 = (GUID)xmmword_1800513C0[(v49 != 0 ? 6 : 0) - 3 + v50];
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
                    if ( dword_180051608 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                       + (unsigned int)tls_index)
                                                     + 4LL) )
                    {
                      Init_thread_header(&dword_180051608);
                      if ( dword_180051608 == -1 )
                      {
                        xmmword_180051480[0] = (__int128)GUID_WICPixelFormat24bpp3Channels;
                        xmmword_180051490 = (__int128)GUID_WICPixelFormat32bpp4Channels;
                        xmmword_1800514A0 = (__int128)GUID_WICPixelFormat40bpp5Channels;
                        xmmword_1800514B0 = (__int128)GUID_WICPixelFormat48bpp6Channels;
                        xmmword_1800514C0 = (__int128)GUID_WICPixelFormat56bpp7Channels;
                        xmmword_1800514D0 = (__int128)GUID_WICPixelFormat64bpp8Channels;
                        xmmword_1800514E0 = (__int128)GUID_WICPixelFormat32bpp3ChannelsAlpha;
                        xmmword_1800514F0 = (__int128)GUID_WICPixelFormat40bpp4ChannelsAlpha;
                        xmmword_180051500 = (__int128)GUID_WICPixelFormat48bpp5ChannelsAlpha;
                        xmmword_180051510 = (__int128)GUID_WICPixelFormat56bpp6ChannelsAlpha;
                        xmmword_180051520 = (__int128)GUID_WICPixelFormat64bpp7ChannelsAlpha;
                        xmmword_180051530 = (__int128)GUID_WICPixelFormat72bpp8ChannelsAlpha;
                        Init_thread_footer(&dword_180051608);
                      }
                    }
                    if ( (unsigned __int64)(v50 - 3) > 5 )
                      goto LABEL_174;
                    v47 = (GUID)xmmword_180051480[(v49 != 0 ? 6 : 0) - 3 + v50];
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
0x18002b180  mov     [rsp-38h+arg_10], rbx
0x18002b185  push    rbp
0x18002b186  push    rsi
0x18002b187  push    rdi
0x18002b188  push    r12
0x18002b18a  push    r13
0x18002b18c  push    r14
0x18002b18e  push    r15
0x18002b190  mov     rbp, rsp
0x18002b193  sub     rsp, 60h
0x18002b197  xor     esi, esi
0x18002b199  mov     rdi, rcx
0x18002b19c  mov     r13d, esi
0x18002b19f  mov     [rbp+pullResult], rsi
0x18002b1a3  lea     edx, [rsi+2]; int
0x18002b1a6  call    ?HrTestStateMinimum@CWmpCodecBase@@UEAAJH@Z; CWmpCodecBase::HrTestStateMinimum(int)
0x18002b1ab  mov     ebx, eax
0x18002b1ad  test    eax, eax
0x18002b1af  js      loc_18002B8BB
0x18002b1b5  mov     r12d, esi
0x18002b1b8  mov     r15d, esi
0x18002b1bb  cmp     [rdi+104C4h], esi
0x18002b1c1  jnz     loc_18002B850
0x18002b1c7  mov     rcx, [rdi+10388h]
0x18002b1ce  lea     r15d, [rsi+12h]
0x18002b1d2  xor     eax, eax
0x18002b1d4  lea     r9, [rbp+var_30]
0x18002b1d8  mov     [rbp+var_8], rax
0x18002b1dc  lea     r8, [rbp+var_18]
0x18002b1e0  mov     [rbp+var_20], rax
0x18002b1e4  xorps   xmm0, xmm0
0x18002b1e7  movups  [rbp+var_18], xmm0
0x18002b1eb  mov     eax, 0BC82h
0x18002b1f0  mov     word ptr [rbp+var_18], r15w
0x18002b1f5  mov     word ptr [rbp+var_18+8], ax
0x18002b1f9  xorps   xmm1, xmm1
0x18002b1fc  movups  [rbp+var_30], xmm1
0x18002b200  mov     rax, [rcx]
0x18002b203  xor     edx, edx
0x18002b205  mov     rax, [rax+38h]
0x18002b209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b20e  mov     ebx, eax
0x18002b210  mov     r14d, 88982F40h
0x18002b216  test    eax, eax
0x18002b218  js      short loc_18002B23E
0x18002b21a  lea     r12d, [rsi+4]
0x18002b21e  cmp     r12w, word ptr [rbp+var_30]
0x18002b223  jz      short loc_18002B22F
0x18002b225  mov     ebx, 88982F42h
0x18002b22a  jmp     loc_18002B8BB
0x18002b22f  movss   xmm0, dword ptr [rbp+var_30+8]
0x18002b234  cvtps2pd xmm0, xmm0
0x18002b237  movsd   qword ptr [rdi+70h], xmm0
0x18002b23c  jmp     short loc_18002B24D
0x18002b23e  cmp     eax, r14d
0x18002b241  jnz     loc_18002B8BB
0x18002b247  mov     r12d, 4
0x18002b24d  mov     rcx, [rdi+10388h]
0x18002b254  lea     r9, [rbp+var_30]
0x18002b258  xor     eax, eax
0x18002b25a  lea     r8, [rbp+var_18]
0x18002b25e  mov     [rbp+var_8], rax
0x18002b262  xorps   xmm0, xmm0
0x18002b265  mov     [rbp+var_20], rax
0x18002b269  xorps   xmm1, xmm1
0x18002b26c  movups  [rbp+var_18], xmm0
0x18002b270  mov     eax, 0BC83h
0x18002b275  mov     word ptr [rbp+var_18], r15w
0x18002b27a  mov     word ptr [rbp+var_18+8], ax
0x18002b27e  xor     edx, edx
0x18002b280  movups  [rbp+var_30], xmm1
0x18002b284  mov     rax, [rcx]
0x18002b287  mov     rax, [rax+38h]
0x18002b28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b290  mov     ebx, eax
0x18002b292  test    eax, eax
0x18002b294  js      short loc_18002B2AC
0x18002b296  cmp     r12w, word ptr [rbp+var_30]
0x18002b29b  jnz     short loc_18002B225
0x18002b29d  movss   xmm0, dword ptr [rbp+var_30+8]
0x18002b2a2  cvtps2pd xmm0, xmm0
0x18002b2a5  movsd   qword ptr [rdi+78h], xmm0
0x18002b2aa  jmp     short loc_18002B2B5
0x18002b2ac  cmp     eax, r14d
0x18002b2af  jnz     loc_18002B8BB
0x18002b2b5  mov     rcx, [rdi+10388h]
0x18002b2bc  lea     r9, [rbp+var_30]
0x18002b2c0  xor     eax, eax
0x18002b2c2  lea     r8, [rbp+var_18]
0x18002b2c6  mov     [rbp+var_8], rax
0x18002b2ca  xorps   xmm0, xmm0
0x18002b2cd  mov     [rbp+var_20], rax
0x18002b2d1  xorps   xmm1, xmm1
0x18002b2d4  movups  [rbp+var_18], xmm0
0x18002b2d8  mov     eax, 0BC80h
0x18002b2dd  mov     word ptr [rbp+var_18], r15w
0x18002b2e2  mov     word ptr [rbp+var_18+8], ax
0x18002b2e6  xor     edx, edx
0x18002b2e8  movups  [rbp+var_30], xmm1
0x18002b2ec  mov     rax, [rcx]
0x18002b2ef  mov     rax, [rax+38h]
0x18002b2f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2f8  mov     ebx, eax
0x18002b2fa  test    eax, eax
0x18002b2fc  js      loc_18002B8BB
0x18002b302  mov     r14d, 13h
0x18002b308  cmp     r14w, word ptr [rbp+var_30]
0x18002b30d  jnz     loc_18002B225
0x18002b313  mov     rcx, [rdi+10388h]
0x18002b31a  lea     r9, [rbp+var_30]
0x18002b31e  mov     r12d, dword ptr [rbp+var_30+8]
0x18002b322  lea     r8, [rbp+var_18]
0x18002b326  xor     eax, eax
0x18002b328  xorps   xmm0, xmm0
0x18002b32b  mov     [rbp+var_8], rax
0x18002b32f  xorps   xmm1, xmm1
0x18002b332  mov     [rbp+var_20], rax
0x18002b336  xor     edx, edx
0x18002b338  movups  [rbp+var_18], xmm0
0x18002b33c  mov     eax, 0BC81h
0x18002b341  mov     word ptr [rbp+var_18], r15w
0x18002b346  mov     word ptr [rbp+var_18+8], ax
0x18002b34a  movups  [rbp+var_30], xmm1
0x18002b34e  mov     rax, [rcx]
0x18002b351  mov     rax, [rax+38h]
0x18002b355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b35a  mov     ebx, eax
0x18002b35c  test    eax, eax
0x18002b35e  js      loc_18002B8BB
0x18002b364  cmp     r14w, word ptr [rbp+var_30]
0x18002b369  jnz     loc_18002B225
0x18002b36f  mov     rcx, [rdi+10388h]
0x18002b376  lea     r9, [rbp+var_30]
0x18002b37a  mov     r15d, dword ptr [rbp+var_30+8]
0x18002b37e  lea     r8, [rbp+var_18]
0x18002b382  xor     eax, eax
0x18002b384  xorps   xmm0, xmm0
0x18002b387  mov     [rbp+var_8], rax
0x18002b38b  xorps   xmm1, xmm1
0x18002b38e  mov     [rbp+var_20], rax
0x18002b392  xor     edx, edx
0x18002b394  movups  [rbp+var_18], xmm0
0x18002b398  lea     eax, [r14-1]
0x18002b39c  mov     word ptr [rbp+var_18], ax
0x18002b3a0  mov     eax, 0BCC0h
0x18002b3a5  mov     word ptr [rbp+var_18+8], ax
0x18002b3a9  movups  [rbp+var_30], xmm1
0x18002b3ad  mov     rax, [rcx]
0x18002b3b0  mov     rax, [rax+38h]
0x18002b3b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3b9  mov     ebx, eax
0x18002b3bb  test    eax, eax
0x18002b3bd  js      loc_18002B8BB
0x18002b3c3  cmp     r14w, word ptr [rbp+var_30]
0x18002b3c8  jnz     loc_18002B225
0x18002b3ce  mov     eax, dword ptr [rbp+var_30+8]
0x18002b3d1  lea     r9, [rbp+var_30]
0x18002b3d5  mov     rcx, [rdi+10388h]
0x18002b3dc  lea     r8, [rbp+var_18]
0x18002b3e0  mov     [rdi+80h], eax
0x18002b3e6  xorps   xmm0, xmm0
0x18002b3e9  xor     eax, eax
0x18002b3eb  xorps   xmm1, xmm1
0x18002b3ee  mov     [rbp+var_8], rax
0x18002b3f2  xor     edx, edx
0x18002b3f4  mov     [rbp+var_20], rax
0x18002b3f8  lea     eax, [r14-1]
0x18002b3fc  movups  [rbp+var_18], xmm0
0x18002b400  mov     word ptr [rbp+var_18], ax
0x18002b404  mov     eax, 0BCC1h
0x18002b409  mov     word ptr [rbp+var_18+8], ax
0x18002b40d  movups  [rbp+var_30], xmm1
0x18002b411  mov     rax, [rcx]
0x18002b414  mov     rax, [rax+38h]
0x18002b418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b41d  mov     ebx, eax
0x18002b41f  test    eax, eax
0x18002b421  js      loc_18002B8BB
0x18002b427  cmp     r14w, word ptr [rbp+var_30]
0x18002b42c  jnz     loc_18002B225
0x18002b432  mov     eax, dword ptr [rbp+var_30+8]
0x18002b435  lea     r9, [rbp+var_30]
0x18002b439  mov     rcx, [rdi+10388h]
0x18002b440  lea     r8, [rbp+var_18]
0x18002b444  mov     [rdi+84h], eax
0x18002b44a  xorps   xmm0, xmm0
0x18002b44d  xor     eax, eax
0x18002b44f  xorps   xmm1, xmm1
0x18002b452  mov     [rbp+var_8], rax
0x18002b456  xor     edx, edx
0x18002b458  mov     [rbp+var_20], rax
0x18002b45c  movups  [rbp+var_18], xmm0
0x18002b460  lea     ebx, [rax+12h]
0x18002b463  mov     eax, 0BC04h
0x18002b468  mov     word ptr [rbp+var_18+8], ax
0x18002b46c  movups  [rbp+var_30], xmm1
0x18002b470  mov     word ptr [rbp+var_18], bx
0x18002b474  mov     rax, [rcx]
0x18002b477  mov     rax, [rax+38h]
0x18002b47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b480  test    eax, eax
0x18002b482  js      short loc_18002B497
0x18002b484  cmp     r14w, word ptr [rbp+var_30]
0x18002b489  jnz     loc_18002B225
0x18002b48f  mov     eax, dword ptr [rbp+var_30+8]
0x18002b492  and     eax, 1
0x18002b495  jmp     short loc_18002B499
0x18002b497  mov     eax, esi
0x18002b499  mov     [rdi+104C8h], eax
0x18002b49f  lea     r9, [rbp+var_30]
0x18002b4a3  mov     rcx, [rdi+10388h]
0x18002b4aa  lea     r8, [rbp+var_18]
0x18002b4ae  xor     eax, eax
0x18002b4b0  xorps   xmm0, xmm0
0x18002b4b3  mov     [rbp+var_8], rax
0x18002b4b7  xorps   xmm1, xmm1
0x18002b4ba  mov     [rbp+var_20], rax
0x18002b4be  xor     edx, edx
0x18002b4c0  movups  [rbp+var_18], xmm0
0x18002b4c4  mov     eax, 0BCC2h
0x18002b4c9  mov     word ptr [rbp+var_18], bx
0x18002b4cd  mov     word ptr [rbp+var_18+8], ax
0x18002b4d1  movups  [rbp+var_30], xmm1
0x18002b4d5  mov     rax, [rcx]
0x18002b4d8  mov     rax, [rax+38h]
0x18002b4dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4e1  mov     ebx, eax
0x18002b4e3  test    eax, eax
0x18002b4e5  js      short loc_18002B4FD
0x18002b4e7  cmp     r14w, word ptr [rbp+var_30]
0x18002b4ec  jnz     loc_18002B225
0x18002b4f2  mov     eax, dword ptr [rbp+var_30+8]
0x18002b4f5  mov     [rdi+88h], eax
0x18002b4fb  jmp     short loc_18002B508
0x18002b4fd  cmp     eax, 88982F40h
0x18002b502  jnz     loc_18002B8BB
0x18002b508  mov     rcx, [rdi+10388h]
0x18002b50f  lea     r9, [rbp+var_30]
0x18002b513  xor     eax, eax
0x18002b515  lea     r8, [rbp+var_18]
0x18002b519  mov     [rbp+var_8], rax
0x18002b51d  xorps   xmm0, xmm0
0x18002b520  mov     [rbp+var_20], rax
0x18002b524  xorps   xmm1, xmm1
0x18002b527  movups  [rbp+var_18], xmm0
0x18002b52b  mov     eax, 12h
0x18002b530  xor     edx, edx
0x18002b532  mov     word ptr [rbp+var_18], ax
0x18002b536  mov     eax, 0BCC3h
0x18002b53b  mov     word ptr [rbp+var_18+8], ax
0x18002b53f  movups  [rbp+var_30], xmm1
0x18002b543  mov     rax, [rcx]
0x18002b546  mov     rax, [rax+38h]
0x18002b54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b54f  mov     ebx, eax
0x18002b551  test    eax, eax
0x18002b553  js      short loc_18002B56B
0x18002b555  cmp     r14w, word ptr [rbp+var_30]
0x18002b55a  jnz     loc_18002B225
0x18002b560  mov     eax, dword ptr [rbp+var_30+8]
0x18002b563  mov     [rdi+8Ch], eax
0x18002b569  jmp     short loc_18002B576
0x18002b56b  cmp     eax, 88982F40h
0x18002b570  jnz     loc_18002B8BB
0x18002b576  mov     rcx, [rdi+10388h]
0x18002b57d  lea     r9, [rbp+var_30]
0x18002b581  xor     eax, eax
0x18002b583  lea     r8, [rbp+var_18]
0x18002b587  mov     [rbp+var_8], rax
0x18002b58b  xorps   xmm0, xmm0
0x18002b58e  mov     [rbp+var_20], rax
0x18002b592  xorps   xmm1, xmm1
0x18002b595  movups  [rbp+var_18], xmm0
0x18002b599  mov     eax, 12h
0x18002b59e  xor     edx, edx
0x18002b5a0  mov     word ptr [rbp+var_18], ax
0x18002b5a4  mov     eax, 8773h
0x18002b5a9  mov     word ptr [rbp+var_18+8], ax
0x18002b5ad  movups  [rbp+var_30], xmm1
0x18002b5b1  mov     rax, [rcx]
0x18002b5b4  mov     rax, [rax+38h]
0x18002b5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5bd  mov     ebx, eax
0x18002b5bf  test    eax, eax
0x18002b5c1  js      short loc_18002B5E8
0x18002b5c3  mov     eax, 41h ; 'A'
0x18002b5c8  cmp     ax, word ptr [rbp+var_30]
0x18002b5cc  jnz     loc_18002B225
0x18002b5d2  mov     rax, [rbp+var_20]
0x18002b5d6  mov     [rdi+10390h], rax
0x18002b5dd  mov     eax, dword ptr [rbp+var_30+8]
0x18002b5e0  mov     [rdi+10398h], eax
0x18002b5e6  jmp     short loc_18002B5F3
0x18002b5e8  cmp     eax, 88982F40h
0x18002b5ed  jnz     loc_18002B8BB
0x18002b5f3  mov     rcx, [rdi+10388h]
0x18002b5fa  lea     r9, [rbp+var_30]
0x18002b5fe  xor     eax, eax
0x18002b600  lea     r8, [rbp+var_18]
0x18002b604  mov     [rbp+var_8], rax
  ... truncated ...
```
