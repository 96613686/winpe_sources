# XMLParser::Run(long)

- ea: `0x18003b420`
- end: `0x18003c5df`
- name: `?Run@XMLParser@@UEAAJJ@Z`
- size: `4543`
- prototype: `__int64 __fastcall(XMLParser *__hidden this, int)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c000`
- `0x18000df40`
- `0x180013150`
- `0x180022f60`
- `0x18002e98c`
- `0x18003b420`
- `0x18003c5f0`
- `0x18003c6f8`
- `0x18003da18`
- `0x18003dd00`
- `0x18003df40`
- `0x18003e164`
- `0x180052848`
- `0x18005c484`
- `0x180067170`
- `0x18006a0d1`
- `0x18006a0dd`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18003b738`
- `ntdll!RtlPopFrame` at `0x18003b738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c527`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c54f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c54f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003bfc0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003bfc0`

## string_xrefs

- `0x18003bd5b`: `SXS.DLL: XML Parser has found multiple roots in the document which is an error.\n`
- `0x18003bff5`: `SXS.DLL: XML Parser has found an initial element which is not valid at the root level.\n`
- `0x18003c0e8`: `SXS.DLL: XML Parser found unclosed tags at the end of the input stream.\n`
- `0x18003c11a`: `SXS.DLL: XML Parser has found PCDATA at the root level which is not valid XML.\n`
- `0x18003b75e`: `SXS.DLL: XMLParser::Run() failing because _fInsideRun is set or lChars == 0\n`
- `0x18003c17c`: `SXS.DLL: XMLParser::Run() failing because _pFactory is NULL\n`
- `0x18003c197`: `SXS.DLL: XMLParser::Run() failing because _fStopped is set\n`
- `0x18003c1c0`: `SXS.DLL: XMLParser::Run() failing because _pTokenizer == NULL and _fLastError != S_OK (== 0x%08lx)\n`
- `0x18003c1d4`: `SXS.DLL: XMLParser::Run() failing because _pTokenizer == NULL and _fLastError == S_OK\n`
- `0x18003c315`: `SXS.DLL: XML Parser has found an unexpected end tag.\n`
- `0x18003c2ec`: `SXS.DLL: Unknown XML Parser node type %d.\n`
- `0x18003c46b`: `SXS.DLL: XML Parser has found no root in the document.\n`
- `0x18003c3b6`: `SXS.DLL: XML Parser found a duplicate attribute\n`
- `0x18003bb10`: `SXS.DLL: XML Parser found a duplicate attribute (#2)\n`
- `0x18003c38e`: `SXS.DLL: XML Parser found an unexpected end tag.\n`
- `0x18003c330`: `SXS.DLL: XML Parser found an end tag mismatch\n`
- `0x18003c351`: `SXS.DLL: XML Parser found an end tag mismatch.\n`

## pseudocode

```c
__int64 __fastcall XMLParser::Run(XMLParser *this, int a2)
{
  __int64 v4; // rcx
  int v5; // edi
  char v6; // r12
  __int16 *v7; // rdx
  __int64 v8; // rbx
  unsigned int *v9; // rcx
  int v10; // eax
  int v11; // eax
  unsigned int v12; // r8d
  char v13; // bl
  __int64 v14; // rcx
  char v15; // di
  char v16; // r15
  char v17; // r14
  bool v18; // zf
  __int64 v19; // rcx
  unsigned int v20; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  char v27; // cl
  __int16 v28; // r8
  unsigned __int16 v29; // r11
  __int16 v30; // r9
  __int16 v31; // dx
  __int16 v32; // cx
  int v33; // eax
  int v34; // eax
  __int64 v35; // rax
  int v36; // r8d
  RawStack *v37; // rcx
  char *v38; // rdx
  unsigned int v39; // ebx
  __int64 v40; // rax
  const void *v41; // rdi
  unsigned __int64 v42; // r14
  unsigned __int64 v43; // rdx
  char *v44; // rax
  __int64 v45; // rbx
  int v46; // eax
  int v47; // eax
  int v48; // ecx
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rcx
  __int16 v53; // cx
  unsigned __int16 v54; // r11
  __int16 v55; // r9
  __int16 v56; // r8
  __int16 v57; // dx
  int v58; // eax
  int v59; // eax
  __int64 v60; // rax
  int v61; // eax
  __int64 v62; // r8
  __int64 v63; // rdx
  const unsigned __int16 *v64; // r14
  const unsigned __int16 *v65; // r15
  unsigned __int64 v66; // rdi
  char *v67; // rax
  unsigned int v68; // eax
  __int64 v69; // rbx
  signed int v70; // edi
  __int64 v71; // rax
  SIZE_T v72; // rax
  HANDLE v73; // rcx
  LPVOID v74; // rax
  _DWORD *v75; // rcx
  int v76; // eax
  int v77; // edx
  int v78; // eax
  int v79; // r8d
  int v80; // eax
  int v81; // r8d
  __int64 v82; // rcx
  __int64 v83; // r8
  __int64 v84; // rcx
  __int64 v85; // r9
  XMLParser *v86; // rcx
  int v87; // eax
  __int64 v88; // r8
  __int64 v89; // rcx
  __int64 v90; // r9
  int v91; // eax
  int v92; // eax
  DWORD LastError; // ebx
  int v94; // ecx
  __int128 v95; // [rsp+38h] [rbp-49h] BYREF
  void *Buf2[2]; // [rsp+48h] [rbp-39h]
  __int128 v97; // [rsp+58h] [rbp-29h]
  int v98; // [rsp+68h] [rbp-19h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+70h] [rbp-11h] BYREF
  __int64 v100; // [rsp+88h] [rbp+7h]
  int v101; // [rsp+90h] [rbp+Fh]
  int *v102; // [rsp+98h] [rbp+17h]
  __int128 *v103; // [rsp+A0h] [rbp+1Fh] BYREF

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_1800707D0;
  v102 = &v98;
  v98 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v100 = 544438355;
  v101 = 189;
  CFrame::BaseEnter((CFrame *)&Frame);
  v103 = 0;
  v95 = 0;
  *(_OWORD *)Buf2 = 0;
  v97 = 0;
  if ( *((_BYTE *)this + 49) )
    *((_BYTE *)this + 49) = 0;
  v4 = *((_QWORD *)this + 24);
  if ( !v4 )
  {
    FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XMLParser::Run() failing because _pFactory is NULL\n");
    v5 = -2147467259;
    goto LABEL_53;
  }
  if ( *((_BYTE *)this + 50) )
  {
    FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XMLParser::Run() failing because _fStopped is set\n");
    v5 = -1072896687;
    goto LABEL_53;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    v81 = *((_DWORD *)this + 8);
    if ( !v81 )
    {
      FusionpDbgPrintEx(
        0xC0000000,
        "SXS.DLL: XMLParser::Run() failing because _pTokenizer == NULL and _fLastError == S_OK\n");
      v5 = 0;
      v98 = 0;
      goto LABEL_50;
    }
    FusionpDbgPrintEx(
      0xC0000000,
      "SXS.DLL: XMLParser::Run() failing because _pTokenizer == NULL and _fLastError != S_OK (== 0x%08lx)\n",
      v81);
    v5 = *((_DWORD *)this + 8);
LABEL_53:
    v98 = v5;
    goto LABEL_50;
  }
  if ( *((_BYTE *)this + 60) || !a2 )
  {
    FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XMLParser::Run() failing because _fInsideRun is set or lChars == 0\n");
    v5 = -2147483638;
    goto LABEL_53;
  }
  *((_BYTE *)this + 60) = 1;
  v5 = *((_DWORD *)this + 8);
  if ( v5 )
  {
    v13 = 0;
    v98 = *((_DWORD *)this + 8);
LABEL_43:
    v18 = v5 == 0;
LABEL_44:
    if ( v18 || v5 == -2147483638 )
    {
      if ( !v13 )
      {
LABEL_49:
        *((_BYTE *)this + 60) = 0;
        goto LABEL_50;
      }
    }
    else
    {
      v89 = *((_QWORD *)this + 24);
      *((_DWORD *)this + 8) = v5;
      if ( *((_QWORD *)this + 21) )
        v90 = (unsigned int)(*((_DWORD *)this + 36) + 1);
      else
        v90 = 0;
      v91 = (*(__int64 (__fastcall **)(__int64, XMLParser *, _QWORD, __int64, _QWORD))(*(_QWORD *)v89 + 48LL))(
              v89,
              this,
              (unsigned int)v5,
              v90,
              *((_QWORD *)this + 21));
      v5 = v98;
      if ( v91 )
        *((_DWORD *)this + 8) = v98;
    }
    if ( !*((_BYTE *)this + 50) )
    {
      v19 = *((_QWORD *)this + 24);
      *((_DWORD *)this + 8) = v5;
      *((_WORD *)this + 25) = 1;
      v20 = (*(__int64 (__fastcall **)(__int64, XMLParser *, __int64))(*(_QWORD *)v19 + 24LL))(v19, this, 8);
      v5 = v20;
      if ( v20 )
      {
        v98 = v20;
        if ( !*((_DWORD *)this + 8) )
        {
          v92 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 24) + 48LL))(
                  *((_QWORD *)this + 24),
                  this,
                  v20,
                  0,
                  0);
          v5 = v92;
          if ( v92 )
            v98 = v92;
          else
            v5 = v98;
        }
        *((_DWORD *)this + 8) = v5;
      }
      else
      {
        v5 = v98;
      }
    }
    goto LABEL_49;
  }
  if ( *((_BYTE *)this + 51) )
  {
    v5 = v98;
    goto LABEL_11;
  }
  *((_BYTE *)this + 51) = 1;
  v5 = (*(__int64 (__fastcall **)(__int64, XMLParser *, _QWORD))(*(_QWORD *)v4 + 24LL))(v4, this, 0);
  v98 = v5;
  if ( !*((_BYTE *)this + 50) )
  {
LABEL_11:
    v6 = 0;
    *((_BYTE *)this + 48) = 0;
    if ( *((_BYTE *)this + 64) )
    {
      v82 = *((_QWORD *)this + 24);
      v83 = *((_QWORD *)this + 19);
      *((_BYTE *)this + 64) = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, XMLParser *, __int64))(*(_QWORD *)v82 + 32LL))(v82, this, v83);
      v98 = v5;
    }
    if ( *((_BYTE *)this + 65) )
    {
      v84 = *((_QWORD *)this + 24);
      v85 = *((_QWORD *)this + 19);
      *((_BYTE *)this + 65) = 0;
      v98 = (*(__int64 (__fastcall **)(__int64, XMLParser *, __int64, __int64))(*(_QWORD *)v84 + 40LL))(
              v84,
              this,
              1,
              v85);
      v5 = v98;
      if ( v98 < 0 )
      {
        v5 = XMLParser::pop(this);
        v98 = v5;
      }
    }
    *(_QWORD *)&v95 = 48;
    DWORD2(v95) = 0;
    v97 = 0;
    v103 = &v95;
    Buf2[0] = 0;
    Buf2[1] = 0;
    while ( 1 )
    {
      ++*((_DWORD *)this + 14);
LABEL_16:
      while ( 1 )
      {
        v7 = &_ImageBase;
LABEL_17:
        if ( v5 || *((_BYTE *)this + 49) )
          break;
        v8 = *((_QWORD *)this + 2);
        DWORD2(v95) = 0;
        if ( *(_BYTE *)(v8 + 196) )
        {
          v5 = -2147418113;
          v98 = -2147418113;
          goto LABEL_68;
        }
        if ( *(_BYTE *)(v8 + 116) )
        {
          v9 = *(unsigned int **)(v8 + 88);
          v10 = *(_DWORD *)(v8 + 112);
          v7 = (__int16 *)v9[4];
          if ( (int)v7 <= v10 )
            v11 = 0;
          else
            v11 = (_DWORD)v7 + ~v10;
          v12 = v9[11];
          v9[7] = v11;
          if ( v12 != (_DWORD)v7 )
          {
            v9[12] = v9[10];
            v9[13] = v12;
          }
          *(_DWORD *)(v8 + 112) = 0;
          *(_BYTE *)(v8 + 116) = 0;
        }
        v5 = (*(__int64 (__fastcall **)(__int64, __int16 *))v8)(v8, v7);
        if ( v5 )
        {
LABEL_27:
          DWORD1(v95) = 0;
          if ( v5 == -2147483638 )
          {
            Buf2[1] = 0;
            Buf2[0] = 0;
            v98 = -2147483638;
            *((_BYTE *)this + 48) = 1;
            break;
          }
        }
        else
        {
          while ( !*(_DWORD *)(v8 + 104) )
          {
            v5 = (*(__int64 (__fastcall **)(__int64))v8)(v8);
            if ( v5 )
              goto LABEL_27;
          }
          DWORD1(v95) = *(_DWORD *)(v8 + 104);
        }
        if ( *(_BYTE *)(v8 + 193) )
        {
          Buf2[0] = *(void **)(v8 + 176);
          LODWORD(Buf2[1]) = *(_DWORD *)(v8 + 184);
          *(_WORD *)(v8 + 192) = 0;
          *(_DWORD *)(v8 + 184) = 0;
        }
        else
        {
          v22 = *(_QWORD *)(v8 + 88);
          v23 = *(_QWORD *)(v22 + 8);
          if ( v23 )
          {
            Buf2[0] = (void *)(v23 + 2LL * *(int *)(v22 + 28));
            v24 = *(_DWORD *)(v22 + 16) + ~*(_DWORD *)(v22 + 28);
            LODWORD(Buf2[1]) = v24;
          }
          else
          {
            v24 = (int)Buf2[1];
          }
          v25 = *(_DWORD *)(v8 + 108);
          if ( !v25 )
            goto LABEL_65;
          LODWORD(Buf2[1]) = v25 + v24;
        }
        *(_DWORD *)(v8 + 108) = 0;
LABEL_65:
        if ( v5 && (unsigned int)(v5 + 1072896688) > 0x36 )
        {
          v75 = *(_DWORD **)(v8 + 88);
          v76 = *(_DWORD *)(v8 + 112);
          v77 = v75[4];
          if ( v77 <= v76 )
            v78 = 0;
          else
            v78 = v77 + ~v76;
          v79 = v75[11];
          v75[7] = v78;
          if ( v79 != v77 )
          {
            v75[12] = v75[10];
            v75[13] = v79;
          }
          *(_DWORD *)(v8 + 112) = 0;
        }
        else
        {
          *(_BYTE *)(v8 + 116) = 1;
        }
        v26 = *(_DWORD *)(v8 + 128);
        *(_DWORD *)(v8 + 104) = 0;
        HIDWORD(Buf2[1]) = v26;
        *(_QWORD *)(v8 + 128) = 0;
        v98 = v5;
        v7 = &_ImageBase;
LABEL_68:
        v27 = *((_BYTE *)this + 63);
        if ( !v27 )
        {
          if ( !DWORD1(v95) || DWORD1(v95) == 18 || DWORD1(v95) == 4 )
          {
            v27 = 0;
          }
          else
          {
            *((_BYTE *)this + 63) = 1;
            v27 = 1;
          }
        }
        switch ( DWORD1(v95) )
        {
          case 0xE:
LABEL_84:
            if ( *((_BYTE *)this + 62) )
            {
              FusionpDbgPrintEx(
                0xC0000000,
                "SXS.DLL: XML Parser has found PCDATA at the root level which is not valid XML.\n");
              v5 = -1072896682;
              goto LABEL_91;
            }
LABEL_85:
            HIDWORD(v95) = 1;
            if ( *((_WORD *)this + 80) )
            {
              v36 = *((_DWORD *)this + 32);
              v37 = (XMLParser *)((char *)this + 112);
              if ( *((_DWORD *)this + 33) == v36 )
              {
                v38 = RawStack::__push(v37);
              }
              else
              {
                v63 = (unsigned int)(*(_DWORD *)v37 * v36);
                *((_DWORD *)this + 32) = v36 + 1;
                v38 = (char *)(*((_QWORD *)this + 15) + v63);
              }
              *((_QWORD *)this + 19) = v38;
              if ( v38 )
              {
                *((_QWORD *)&v97 + 1) = *(unsigned __int16 *)(*((_QWORD *)this + 2) + 122LL);
                *(_OWORD *)v38 = v95;
                *((_OWORD *)v38 + 1) = *(_OWORD *)Buf2;
                *((_OWORD *)v38 + 2) = v97;
                if ( *((_WORD *)this + 88) != *((_WORD *)this + 89) || (v5 = XMLParser::GrowNodeInfo(this), v5 >= 0) )
                {
                  v5 = 0;
                  *(_QWORD *)(*((_QWORD *)this + 21) + 8LL * (unsigned __int16)(*((_WORD *)this + 89))++) = *((_QWORD *)this + 19);
                  ++*((_WORD *)this + 80);
                }
              }
              else
              {
                v5 = -2147024882;
              }
              goto LABEL_91;
            }
            v5 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, __int64, __int128 **))(**((_QWORD **)this + 24)
                                                                                              + 56LL))(
                   *((_QWORD *)this + 24),
                   this,
                   *((_QWORD *)this + 23),
                   1,
                   &v103);
            v98 = v5;
            *(_QWORD *)&v97 = 0;
            break;
          case 4:
            if ( !v27 )
              goto LABEL_94;
            v5 = -1072896681;
            v98 = -1072896681;
            goto LABEL_17;
          case 0x3F:
            if ( !*((_DWORD *)this + 32) )
            {
              FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XML Parser has found an unexpected end tag.\n");
              v5 = -1072896686;
              goto LABEL_91;
            }
            v45 = *((_QWORD *)this + 19);
            if ( !v45 )
            {
              FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XML Parser found an unexpected end tag.\n");
              v5 = -1072896686;
              goto LABEL_91;
            }
            if ( !LODWORD(Buf2[1]) )
              goto LABEL_117;
            if ( *(_DWORD *)(v45 + 24) != LODWORD(Buf2[1]) )
            {
              FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XML Parser found an end tag mismatch\n");
              v5 = -1072896659;
              goto LABEL_91;
            }
            v64 = (const unsigned __int16 *)Buf2[0];
            v65 = *(const unsigned __int16 **)(v45 + 16);
            v66 = LODWORD(Buf2[1]);
            if ( memcmp_0(v65, Buf2[0], 2LL * LODWORD(Buf2[1])) )
            {
              if ( *((_BYTE *)this + 54) )
              {
                if ( !(unsigned int)FusionpCompareStrings(v65, v66, v64, v66, 1) )
                  goto LABEL_117;
              }
              else
              {
                FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XML Parser found an end tag mismatch.\n");
              }
              v5 = -1072896659;
              v98 = -1072896659;
            }
            else
            {
LABEL_117:
              v46 = *((_DWORD *)this + 32);
              if ( v46 && (v47 = v46 - 1, (*((_DWORD *)this + 32) = v47) != 0) )
              {
                v48 = v47 - 1;
                v49 = *((_QWORD *)this + 15);
                v50 = (unsigned int)(*((_DWORD *)this + 28) * v48);
                --*((_WORD *)this + 89);
                v51 = v50 + v49;
                *((_QWORD *)this + 19) = v51;
                if ( v51 )
                {
                  *((_QWORD *)this + 23) = *(_QWORD *)(v51 + 32);
                  goto LABEL_121;
                }
              }
              else
              {
                --*((_WORD *)this + 89);
                *((_QWORD *)this + 19) = 0;
              }
              v18 = *((_DWORD *)this + 22) == 1;
              *((_QWORD *)this + 23) = *((_QWORD *)this + 3);
              if ( v18 )
                *((_BYTE *)this + 62) = 1;
LABEL_121:
              v52 = *((_QWORD *)this + 24);
              v98 = 0;
              v5 = (*(__int64 (__fastcall **)(__int64, XMLParser *, _QWORD, __int64))(*(_QWORD *)v52 + 40LL))(
                     v52,
                     this,
                     0,
                     v45);
              v98 = v5;
            }
            break;
          case 0x3D:
            v53 = *((_WORD *)this + 80);
            v54 = v53 + 1;
            if ( v53 )
            {
              v55 = *((_WORD *)this + 89);
              v56 = *((_WORD *)this + 80);
              v57 = v55;
              do
              {
                v58 = *((_DWORD *)this + 32);
                if ( v58 && (v59 = v58 - 1, v55 = v57, *((_DWORD *)this + 32) = v59, v53 = v56, v59) )
                  v60 = *((_QWORD *)this + 15) + (unsigned int)(*((_DWORD *)this + 28) * (v59 - 1));
                else
                  v60 = 0;
                --v55;
                *((_QWORD *)this + 19) = v60;
                --v53;
                *((_WORD *)this + 89) = v55;
                *((_WORD *)this + 80) = v53;
                v56 = v53;
                v57 = v55;
              }
              while ( v53 );
            }
            v61 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 24)
                                                                                          + 56LL))(
                    *((_QWORD *)this + 24),
                    this,
                    *((_QWORD *)this + 23),
                    v54,
                    *((_QWORD *)this + 21) + 8LL * *((int *)this + 36));
            v62 = *((_QWORD *)this + 19);
            v5 = v61;
            v98 = v61;
            *((_QWORD *)this + 23) = *(_QWORD *)(v62 + 32);
            if ( v61 < 0 )
            {
              *((_BYTE *)this + 64) = 1;
            }
            else
            {
              v5 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *))(**((_QWORD **)this + 24) + 32LL))(
                     *((_QWORD *)this + 24),
                     this);
              v98 = v5;
            }
            break;
          default:
            if ( DWORD1(v95) != 3 )
            {
              switch ( DWORD1(v95) )
              {
                case 0:
                  goto LABEL_17;
                case 1:
                  break;
                case 2:
                  goto LABEL_157;
                case 0xD:
                  goto LABEL_84;
                case 0x10:
                case 0x12:
                  goto LABEL_85;
                case 0x11:
                  if ( !*((_BYTE *)this + 62) )
                    goto LABEL_85;
                  v5 = -1072896682;
                  v98 = -1072896682;
                  goto LABEL_17;
                case 0x1C:
                  v6 = 1;
                  DWORD2(v95) = DWORD1(v95);
                  DWORD1(v95) = 2;
                  *((_BYTE *)this + 55) = 1;
                  break;
                case 0x1D:
                case 0x1E:
                  if ( !*((_BYTE *)this + 55) && *((_DWORD *)this + 22) == 1 )
                  {
                    v5 = -1072896663;
                    v98 = -1072896663;
                    goto LABEL_17;
                  }
                  if ( DWORD1(v95) == 30 && *((int *)this + 22) > 1 )
                  {
                    v5 = -1072896646;
                    v98 = -1072896646;
                    goto LABEL_17;
                  }
                  DWORD2(v95) = DWORD1(v95);
                  DWORD1(v95) = 2;
LABEL_157:
                  v6 = 1;
                  break;
                case 0x3A:
                case 0x3B:
                case 0x3C:
                  DWORD2(v95) = DWORD1(v95);
                  DWORD1(v95) = 13;
                  if ( !*((_WORD *)this + 80) )
                    goto LABEL_85;
                  HIDWORD(v95) = 1;
                  v98 = XMLParser::pushAttributeValue(this, (struct _XML_NODE_INFO *)&v95);
                  v5 = v98;
                  if ( v98 >= 0 )
                  {
                    v5 = XMLParser::CopyText(v86, *((struct XMLParser::_MY_XML_NODE_INFO **)this + 19));
                    v98 = v5;
                  }
                  continue;
                case 0x3E:
                  goto LABEL_75;
                case 0x40:
                  goto LABEL_83;
                case 0x41:
                  *((_BYTE *)this + 55) = 0;
LABEL_75:
                  v28 = *((_WORD *)this + 80);
                  v29 = v28 + 1;
                  if ( v28 )
                  {
                    v30 = *((_WORD *)this + 89);
                    v31 = *((_WORD *)this + 80);
                    v32 = v30;
                    do
                    {
                      v33 = *((_DWORD *)this + 32);
                      if ( v33 && (v34 = v33 - 1, v30 = v32, *((_DWORD *)this + 32) = v34, v28 = v31, v34) )
                        v35 = *((_QWORD *)this + 15) + (unsigned int)(*((_DWORD *)this + 28) * (v34 - 1));
                      else
                        v35 = 0;
                      --v30;
                      *((_QWORD *)this + 19) = v35;
                      --v28;
                      *((_WORD *)this + 89) = v30;
                      *((_WORD *)this + 80) = v28;
                      v31 = v28;
                      v32 = v30;
                    }
                    while ( v28 );
                  }
                  v98 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 24)
                                                                                                + 56LL))(
                          *((_QWORD *)this + 24),
                          this,
                          *((_QWORD *)this + 23),
                          v29,
                          *((_QWORD *)this + 21) + 8LL * *((int *)this + 36));
                  v5 = v98;
                  if ( v98 < 0 )
                  {
                    *((_BYTE *)this + 65) = 1;
                  }
                  else
                  {
                    v98 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64, _QWORD))(**((_QWORD **)this + 24)
                                                                                          + 40LL))(
                            *((_QWORD *)this + 24),
                            this,
                            1,
                            *((_QWORD *)this + 19));
                    v5 = v98;
                    if ( v98 >= 0 )
                    {
LABEL_83:
                      v5 = XMLParser::pop(this);
                      v98 = v5;
                    }
                  }
                  continue;
                case 0x46:
                  if ( !*((_BYTE *)this + 62) )
                    goto LABEL_17;
                  v71 = *((_QWORD *)this + 13);
                  if ( *(_BYTE *)(v71 + 18) || *(_BYTE *)(v71 + 17) )
                    goto LABEL_17;
                  v5 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64))(**((_QWORD **)this + 24) + 24LL))(
                         *((_QWORD *)this + 24),
                         this,
                         5);
                  v98 = v5;
                  continue;
                default:
                  v98 = -2147467259;
                  FusionpDbgPrintEx(0xC0000000, "SXS.DLL: Unknown XML Parser node type %d.\n", DWORD1(v95));
                  v5 = v98;
                  continue;
              }
            }
LABEL_94:
            if ( !*((_BYTE *)this + 62) )
              goto LABEL_95;
            if ( DWORD1(v95) != 1 )
            {
              if ( (unsigned int)(DWORD1(v95) - 3) > 2 )
              {
                FusionpDbgPrintEx(
                  0xC0000000,
                  "SXS.DLL: XML Parser has found an initial element which is not valid at the root level.\n");
                v5 = -1072896682;
LABEL_91:
                v98 = v5;
                continue;
              }
              goto LABEL_95;
            }
            if ( *((_BYTE *)this + 61) )
            {
              FusionpDbgPrintEx(
                0xC0000000,
                "SXS.DLL: XML Parser has found multiple roots in the document which is an error.\n");
              v5 = -1072896683;
              v98 = -1072896683;
            }
            else
            {
              *((_BYTE *)this + 61) = 1;
LABEL_95:
              HIDWORD(v95) = 0;
              if ( v6 )
              {
                if ( *((_WORD *)this + 80) )
                {
                  v39 = *((_DWORD *)this + 32);
                  while ( 1 )
                  {
                    while ( 1 )
                    {
                      if ( (signed int)--v39 <= *((_DWORD *)this + 36) )
                        goto LABEL_112;
                      if ( v39 >= *((_DWORD *)this + 33) )
                        v40 = 0;
                      else
                        v40 = *((_QWORD *)this + 15) + *((_DWORD *)this + 28) * v39;
                      if ( *(_DWORD *)(v40 + 4) == 2 && *(_DWORD *)(v40 + 24) == LODWORD(Buf2[1]) )
                      {
                        v41 = *(const void **)(v40 + 16);
                        v42 = LODWORD(Buf2[1]);
                        if ( !memcmp_0(v41, Buf2[0], 2LL * LODWORD(Buf2[1])) )
                          break;
                      }
                    }
                    if ( !*((_BYTE *)this + 54) )
                      break;
                    v43 = -1;
                    do
                      ++v43;
                    while ( *((_WORD *)v41 + v43) );
                    if ( !(unsigned int)FusionpCompareStrings(
                                          (const unsigned __int16 *)v41,
                                          v43,
                                          (const unsigned __int16 *)Buf2[0],
                                          v42,
                                          1) )
                    {
                      FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XML Parser found a duplicate attribute (#2)\n");
LABEL_218:
                      v5 = -1072896684;
                      v98 = -1072896684;
                      goto LABEL_16;
                    }
                  }
                  FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XML Parser found a duplicate attribute\n");
                  goto LABEL_218;
                }
LABEL_112:
                ++*((_WORD *)this + 80);
                v44 = RawStack::_push((XMLParser *)((char *)this + 112));
                *((_QWORD *)this + 19) = v44;
                if ( v44 )
                {
                  *(_OWORD *)v44 = v95;
                  *((_OWORD *)v44 + 1) = *(_OWORD *)Buf2;
                  *((_OWORD *)v44 + 2) = v97;
                  if ( *((_WORD *)this + 88) == *((_WORD *)this + 89)
                    && (v87 = XMLParser::GrowNodeInfo(this), v5 = v87, v87 < 0) )
                  {
                    v98 = v87;
                  }
                  else
                  {
                    v5 = 0;
                    *(_QWORD *)(*((_QWORD *)this + 21) + 8LL * (unsigned __int16)(*((_WORD *)this + 89))++) = *((_QWORD *)this + 19);
                    v6 = 0;
                    v98 = 0;
                  }
                }
                else
                {
                  v5 = -2147024882;
                  v98 = -2147024882;
                }
              }
              else
              {
                *((_DWORD *)this + 36) = *((_DWORD *)this + 32);
                v67 = RawStack::_push((XMLParser *)((char *)this + 112));
                *((_QWORD *)this + 19) = v67;
                if ( !v67 )
                {
                  v5 = -2147024882;
                  goto LABEL_91;
                }
                *(_OWORD *)v67 = v95;
                *((_OWORD *)v67 + 1) = *(_OWORD *)Buf2;
                *((_OWORD *)v67 + 2) = v97;
                if ( *((_WORD *)this + 88) == *((_WORD *)this + 89)
                  && (v80 = XMLParser::GrowNodeInfo(this), v5 = v80, v80 < 0) )
                {
                  v98 = v80;
                }
                else
                {
                  *(_QWORD *)(*((_QWORD *)this + 21) + 8LL * *((unsigned __int16 *)this + 89)) = *((_QWORD *)this + 19);
                  v68 = (unsigned int)Buf2[1];
                  ++*((_WORD *)this + 89);
                  *((_BYTE *)this + 62) = 0;
                  if ( v68 + 1 < v68 )
                    goto LABEL_149;
                  v69 = *((_QWORD *)this + 19);
                  if ( *(_DWORD *)(v69 + 56) >= v68 + 1 )
                  {
LABEL_178:
                    memcpy_0(*(void **)(*((_QWORD *)this + 19) + 48LL), Buf2[0], 2LL * LODWORD(Buf2[1]));
                    v5 = 0;
                    *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 19) + 48LL) + 2LL * LODWORD(Buf2[1])) = 0;
                    *(_QWORD *)(*((_QWORD *)this + 19) + 16LL) = *(_QWORD *)(*((_QWORD *)this + 19) + 48LL);
                    v98 = 0;
                  }
                  else
                  {
                    v70 = v68 + 50;
                    if ( v68 + 50 >= v68 )
                    {
                      operator delete(*(void **)(v69 + 48));
                      v72 = 2LL * v70;
                      v73 = g_hHeap;
                      *(_QWORD *)(v69 + 48) = 0;
                      if ( !is_mul_ok(v70, 2u) )
                        v72 = -1;
                      v74 = HeapAlloc(v73, 0, v72);
                      *(_QWORD *)(v69 + 48) = v74;
                      if ( v74 )
                      {
                        *(_DWORD *)(v69 + 56) = v70;
                        goto LABEL_178;
                      }
                      v5 = -2147024882;
                      v98 = -2147024882;
                    }
                    else
                    {
LABEL_149:
                      v5 = -2147024362;
                      v98 = -2147024362;
                    }
                  }
                }
              }
            }
            break;
        }
      }
      --*((_DWORD *)this + 14);
      v13 = 0;
      if ( v5 != -1072896768 )
        goto LABEL_43;
      v14 = *((_QWORD *)this + 13);
      v98 = 0;
      v15 = *(_BYTE *)(v14 + 18);
      if ( v15 && *(_DWORD *)(v14 + 24) != *((_DWORD *)this + 32) )
      {
        FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XML Parser found unclosed tags at the end of the input stream.\n");
        v5 = XMLParser::ReportUnclosedTags(this, *(_DWORD *)(*((_QWORD *)this + 13) + 24LL));
        v98 = v5;
        goto LABEL_43;
      }
      v16 = *(_BYTE *)(v14 + 17);
      v17 = *(_BYTE *)(v14 + 19);
      if ( (unsigned int)XMLParser::PopDownload(this) )
      {
        if ( *((int *)this + 32) > 0 )
        {
          v5 = XMLParser::ReportUnclosedTags(this, 0);
          v98 = v5;
        }
        else if ( *((_BYTE *)this + 61) )
        {
          v5 = v98;
        }
        else
        {
          FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XML Parser has found no root in the document.\n");
          v5 = -1072896680;
          v98 = -1072896680;
        }
        v13 = 1;
        goto LABEL_43;
      }
      if ( v17 )
        goto LABEL_33;
      if ( v15 )
      {
        v88 = 7;
        goto LABEL_227;
      }
      if ( v16 )
      {
        v88 = 2;
LABEL_227:
        v5 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64))(**((_QWORD **)this + 24) + 24LL))(
               *((_QWORD *)this + 24),
               this,
               v88);
        v98 = v5;
      }
      else
      {
LABEL_33:
        v5 = v98;
      }
      v18 = v5 == 0;
      if ( v5 < 0 )
        goto LABEL_44;
      if ( *((int *)this + 14) > 0 || *((_BYTE *)this + 50) )
      {
        v5 = 0;
        v98 = 0;
        *((_BYTE *)this + 60) = 0;
        goto LABEL_50;
      }
    }
  }
  v5 = 0;
  v98 = 0;
  *((_BYTE *)this + 60) = 0;
LABEL_50:
  if ( g_FusionEnterExitTracingEnabled )
  {
    LastError = GetLastError();
    v94 = *v102;
    if ( *v102 < 0 )
      FusionpTraceCOMFailure(v94, 0);
    else
      FusionpTraceCallCOMSuccessfulExit(v94, 0);
    SetLastError(LastError);
  }
  RtlPopFrame(&Frame);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003b420  mov     r11, rsp
0x18003b423  push    rbp
0x18003b424  push    rbx
0x18003b425  push    rdi
0x18003b426  lea     rbp, [r11-5Fh]
0x18003b42a  sub     rsp, 0C0h
0x18003b431  mov     rax, cs:__security_cookie
0x18003b438  xor     rax, rsp
0x18003b43b  mov     [rbp+57h+var_30], rax
0x18003b43f  mov     [r11+10h], rsi
0x18003b443  lea     rax, qword_1800707D0
0x18003b44a  mov     [rbp+57h+Frame.Context], rax
0x18003b44e  mov     rsi, rcx
0x18003b451  mov     [r11+20h], r13
0x18003b455  lea     rax, [rbp+57h+var_70]
0x18003b459  xor     r13d, r13d
0x18003b45c  mov     [rbp+57h+var_40], rax
0x18003b460  lea     rcx, [rbp+57h+Frame]; this
0x18003b464  mov     [rbp+57h+var_70], r13d
0x18003b468  mov     ebx, edx
0x18003b46a  mov     [rbp+57h+Frame.Flags], 1
0x18003b471  mov     [rbp+57h+Frame.Previous], r13
0x18003b475  mov     [rbp+57h+var_50], 20737853h
0x18003b47d  mov     [rbp+57h+var_48], 0BDh
0x18003b484  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18003b489  xorps   xmm0, xmm0
0x18003b48c  mov     [rbp+57h+var_38], r13
0x18003b490  movups  [rbp+57h+var_A0], xmm0
0x18003b494  movups  xmmword ptr [rbp+57h+Buf2], xmm0
0x18003b498  movups  [rbp+57h+var_80], xmm0
0x18003b49c  cmp     [rsi+31h], r13b
0x18003b4a0  jnz     loc_18003C173
0x18003b4a6  mov     rcx, [rsi+0C0h]
0x18003b4ad  mov     [rsp+0D0h+arg_10], r12
0x18003b4b5  mov     [rsp+0B8h], r14
0x18003b4bd  mov     [rsp+0D0h+var_20], r15
0x18003b4c5  test    rcx, rcx
0x18003b4c8  jz      loc_18003C17C
0x18003b4ce  cmp     [rsi+32h], r13b
0x18003b4d2  jnz     loc_18003C197
0x18003b4d8  cmp     [rsi+10h], r13
0x18003b4dc  jz      loc_18003C1B2
0x18003b4e2  cmp     [rsi+3Ch], r13b
0x18003b4e6  jnz     loc_18003B75E
0x18003b4ec  test    ebx, ebx
0x18003b4ee  jz      loc_18003B75E
0x18003b4f4  mov     byte ptr [rsi+3Ch], 1
0x18003b4f8  mov     edi, [rsi+20h]
0x18003b4fb  test    edi, edi
0x18003b4fd  jnz     loc_18003C1EC
0x18003b503  cmp     [rsi+33h], r13b
0x18003b507  jnz     loc_18003C1F6
0x18003b50d  mov     byte ptr [rsi+33h], 1
0x18003b511  xor     r8d, r8d
0x18003b514  mov     rax, [rcx]
0x18003b517  mov     rdx, rsi
0x18003b51a  mov     rax, [rax+18h]
0x18003b51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b523  mov     edi, eax
0x18003b525  mov     [rbp+57h+var_70], eax
0x18003b528  cmp     [rsi+32h], r13b
0x18003b52c  jnz     loc_18003B68F
0x18003b532  xor     r12b, r12b
0x18003b535  mov     [rsi+30h], r12b
0x18003b539  cmp     [rsi+40h], r12b
0x18003b53d  jnz     loc_18003C1FE
0x18003b543  cmp     [rsi+41h], r12b
0x18003b547  jnz     loc_18003C229
0x18003b54d  xorps   xmm0, xmm0
0x18003b550  mov     qword ptr [rbp+57h+var_A0], 30h ; '0'
0x18003b558  lea     rax, [rbp+57h+var_A0]
0x18003b55c  mov     dword ptr [rbp+57h+var_A0+8], r13d
0x18003b560  movdqu  [rbp+57h+var_80], xmm0
0x18003b565  mov     [rbp+57h+var_38], rax
0x18003b569  mov     [rbp+57h+Buf2], r13
0x18003b56d  mov     [rbp+57h+Buf2+8], r13
0x18003b571  nop     dword ptr [rax+00h]
0x18003b575  nop     word ptr [rax+rax+00000000h]
0x18003b580  inc     dword ptr [rsi+38h]
0x18003b583  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18003b58a  mov     r14d, 0FFFFh
0x18003b590  lea     rdx, __ImageBase
0x18003b597  test    edi, edi; jumptable 000000018003B894 case 0
0x18003b599  jnz     loc_18003B62C
0x18003b59f  cmp     [rsi+31h], r13b
0x18003b5a3  jnz     loc_18003B62C
0x18003b5a9  mov     rbx, [rsi+10h]
0x18003b5ad  mov     dword ptr [rbp+57h+var_A0+8], r13d
0x18003b5b1  cmp     [rbx+0C4h], r13b
0x18003b5b8  jnz     loc_18003C166
0x18003b5be  cmp     [rbx+74h], r13b
0x18003b5c2  jz      short loc_18003B5F8
0x18003b5c4  mov     rcx, [rbx+58h]
0x18003b5c8  mov     eax, [rbx+70h]
0x18003b5cb  mov     edx, [rcx+10h]
0x18003b5ce  cmp     edx, eax
0x18003b5d0  jle     loc_18003BB1C
0x18003b5d6  not     eax
0x18003b5d8  add     eax, edx
0x18003b5da  mov     r8d, [rcx+2Ch]
0x18003b5de  mov     [rcx+1Ch], eax
0x18003b5e1  cmp     r8d, edx
0x18003b5e4  jz      short loc_18003B5F0
0x18003b5e6  mov     eax, [rcx+28h]
0x18003b5e9  mov     [rcx+30h], eax
0x18003b5ec  mov     [rcx+34h], r8d
0x18003b5f0  mov     [rbx+70h], r13d
0x18003b5f4  mov     [rbx+74h], r13b
0x18003b5f8  mov     rax, [rbx]
0x18003b5fb  mov     rcx, rbx
0x18003b5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b603  mov     edi, eax
0x18003b605  test    eax, eax
0x18003b607  jz      loc_18003B780
0x18003b60d  mov     dword ptr [rbp+57h+var_A0+4], r13d
0x18003b611  cmp     edi, 8000000Ah
0x18003b617  jnz     loc_18003B7A1
0x18003b61d  mov     [rbp+57h+Buf2+8], r13
0x18003b621  mov     [rbp+57h+Buf2], r13
0x18003b625  mov     [rbp+57h+var_70], edi
0x18003b628  mov     byte ptr [rsi+30h], 1
0x18003b62c  dec     dword ptr [rsi+38h]
0x18003b62f  xor     bl, bl
0x18003b631  cmp     edi, 0C00CE500h
0x18003b637  jnz     short loc_18003B6B7
0x18003b639  mov     rcx, [rsi+68h]
0x18003b63d  mov     [rbp+57h+var_70], r13d
0x18003b641  movzx   edi, byte ptr [rcx+12h]
0x18003b645  test    dil, dil
0x18003b648  jnz     loc_18003C0D9
0x18003b64e  movzx   r15d, byte ptr [rcx+11h]
0x18003b653  movzx   r14d, byte ptr [rcx+13h]
0x18003b658  mov     rcx, rsi; this
0x18003b65b  call    ?PopDownload@XMLParser@@AEAAJXZ; XMLParser::PopDownload(void)
0x18003b660  test    eax, eax
0x18003b662  jnz     short loc_18003B69C
0x18003b664  test    r14b, r14b
0x18003b667  jz      loc_18003C419
0x18003b66d  mov     edi, [rbp+57h+var_70]
0x18003b670  test    edi, edi
0x18003b672  js      short loc_18003B6B9
0x18003b674  cmp     [rsi+38h], r13d
0x18003b678  jg      short loc_18003B683
0x18003b67a  cmp     [rsi+32h], bl
0x18003b67d  jz      loc_18003B571
0x18003b683  mov     edi, r13d
0x18003b686  mov     [rbp+57h+var_70], r13d
0x18003b68a  mov     [rsi+3Ch], bl
0x18003b68d  jmp     short loc_18003B6FF
0x18003b68f  mov     edi, r13d
0x18003b692  mov     [rbp+57h+var_70], r13d
0x18003b696  mov     [rsi+3Ch], dil
0x18003b69a  jmp     short loc_18003B6FF
0x18003b69c  cmp     [rsi+80h], r13d
0x18003b6a3  jg      loc_18003C457
0x18003b6a9  cmp     [rsi+3Dh], bl
0x18003b6ac  jz      loc_18003C46B
0x18003b6b2  mov     edi, [rbp+57h+var_70]
0x18003b6b5  mov     bl, 1
0x18003b6b7  test    edi, edi
0x18003b6b9  jnz     loc_18003C489
0x18003b6bf  test    bl, bl
0x18003b6c1  jz      short loc_18003B6FB
0x18003b6c3  cmp     [rsi+32h], r13b
0x18003b6c7  jnz     short loc_18003B6FB
0x18003b6c9  mov     rcx, [rsi+0C0h]
0x18003b6d0  mov     r8d, 8
0x18003b6d6  mov     [rsi+20h], edi
0x18003b6d9  mov     rdx, rsi
0x18003b6dc  mov     word ptr [rsi+32h], 1
0x18003b6e2  mov     rax, [rcx]
0x18003b6e5  mov     rax, [rax+18h]
0x18003b6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6ee  mov     edi, eax
0x18003b6f0  test    eax, eax
0x18003b6f2  jnz     loc_18003C4E7
0x18003b6f8  mov     edi, [rbp+57h+var_70]
0x18003b6fb  mov     [rsi+3Ch], r13b
0x18003b6ff  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18003b706  mov     r15, [rsp+0D0h+var_20]
0x18003b70e  mov     r14, [rsp+0B8h]
0x18003b716  mov     r13, [rsp+0D0h+arg_18]
0x18003b71e  mov     r12, [rsp+0D0h+arg_10]
0x18003b726  mov     rsi, [rsp+0D0h+arg_8]
0x18003b72e  jnz     loc_18003C527
0x18003b734  lea     rcx, [rbp+57h+Frame]; Frame
0x18003b738  call    cs:__imp_RtlPopFrame
0x18003b73f  nop     dword ptr [rax+rax+00h]
0x18003b744  mov     eax, edi
0x18003b746  mov     rcx, [rbp+57h+var_30]
0x18003b74a  xor     rcx, rsp; StackCookie
0x18003b74d  call    __security_check_cookie
0x18003b752  add     rsp, 0C0h
0x18003b759  pop     rdi
0x18003b75a  pop     rbx
0x18003b75b  pop     rbp
0x18003b75c  retn
0x18003b75e  lea     rdx, aSxsDllXmlparse_3; "SXS.DLL: XMLParser::Run() failing becau"...
0x18003b765  mov     ecx, 0C0000000h; unsigned int
0x18003b76a  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18003b76f  mov     edi, 8000000Ah
0x18003b774  mov     [rbp+57h+var_70], edi
0x18003b777  jmp     short loc_18003B6FF
0x18003b780  mov     eax, [rbx+68h]
0x18003b783  test    eax, eax
0x18003b785  jnz     short loc_18003B79E
0x18003b787  mov     rax, [rbx]
0x18003b78a  mov     rcx, rbx
0x18003b78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b792  mov     edi, eax
0x18003b794  test    eax, eax
0x18003b796  jnz     loc_18003B60D
0x18003b79c  jmp     short loc_18003B780
0x18003b79e  mov     dword ptr [rbp+57h+var_A0+4], eax
0x18003b7a1  cmp     [rbx+0C1h], r13b
0x18003b7a8  jnz     short loc_18003B7E0
0x18003b7aa  mov     rdx, [rbx+58h]
0x18003b7ae  mov     rcx, [rdx+8]
0x18003b7b2  test    rcx, rcx
0x18003b7b5  jz      loc_18003C26F
0x18003b7bb  movsxd  rax, dword ptr [rdx+1Ch]
0x18003b7bf  lea     rcx, [rcx+rax*2]
0x18003b7c3  mov     [rbp+57h+Buf2], rcx
0x18003b7c7  mov     eax, [rdx+1Ch]
0x18003b7ca  not     eax
0x18003b7cc  add     eax, [rdx+10h]
0x18003b7cf  mov     dword ptr [rbp+57h+Buf2+8], eax
0x18003b7d2  mov     ecx, [rbx+6Ch]
0x18003b7d5  test    ecx, ecx
0x18003b7d7  jz      short loc_18003B807
0x18003b7d9  add     eax, ecx
0x18003b7db  mov     dword ptr [rbp+57h+Buf2+8], eax
0x18003b7de  jmp     short loc_18003B803
0x18003b7e0  mov     rax, [rbx+0B0h]
0x18003b7e7  mov     [rbp+57h+Buf2], rax
0x18003b7eb  mov     eax, [rbx+0B8h]
0x18003b7f1  mov     dword ptr [rbp+57h+Buf2+8], eax
0x18003b7f4  mov     [rbx+0C0h], r13w
0x18003b7fc  mov     [rbx+0B8h], r13d
0x18003b803  mov     [rbx+6Ch], r13d
0x18003b807  test    edi, edi
0x18003b809  jnz     loc_18003C027
0x18003b80f  mov     byte ptr [rbx+74h], 1
0x18003b813  mov     eax, [rbx+80h]
0x18003b819  mov     [rbx+68h], r13d
0x18003b81d  mov     dword ptr [rbp+57h+Buf2+0Ch], eax
0x18003b820  mov     [rbx+80h], r13
0x18003b827  mov     [rbp+57h+var_70], edi
0x18003b82a  cmp     edi, 8000000Ah
0x18003b830  jz      loc_18003B628
0x18003b836  lea     rdx, __ImageBase
0x18003b83d  movzx   ecx, byte ptr [rsi+3Fh]
0x18003b841  test    cl, cl
0x18003b843  jz      loc_18003BB24
0x18003b849  mov     eax, dword ptr [rbp+57h+var_A0+4]
0x18003b84c  cmp     eax, 0Eh
0x18003b84f  jz      loc_18003B9A1; jumptable 000000018003B894 case 13
0x18003b855  cmp     eax, 4
0x18003b858  jz      loc_18003BA61
0x18003b85e  cmp     eax, 3Fh ; '?'
0x18003b861  jz      loc_18003BB69
0x18003b867  cmp     eax, 3Dh ; '='
0x18003b86a  jz      loc_18003BC46
0x18003b870  cmp     eax, 3
0x18003b873  jz      loc_18003BA69; jumptable 000000018003B894 case 1
0x18003b879  cmp     eax, 46h; switch 71 cases
0x18003b87c  ja      def_18003B894; jumptable 000000018003B894 default case, cases 3-12,14,15,19-27,31-57,61,63,66-69
0x18003b882  movzx   eax, ds:(byte_18003C598 - 180000000h)[rdx+rax]
0x18003b88a  mov     ecx, ds:(jpt_18003B894 - 180000000h)[rdx+rax*4]
0x18003b891  add     rcx, rdx
0x18003b894  jmp     rcx; switch jump
0x18003b89a  movzx   r8d, word ptr [rsi+0A0h]; jumptable 000000018003B894 case 62
0x18003b8a2  lea     r11d, [r8+1]
0x18003b8a6  test    r8w, r8w
0x18003b8aa  jz      short loc_18003B91A
0x18003b8ac  movzx   r9d, word ptr [rsi+0B2h]
0x18003b8b4  movzx   edx, r8w
0x18003b8b8  movzx   ecx, r9w
0x18003b8bc  nop     dword ptr [rax+00h]
0x18003b8c0  mov     eax, [rsi+80h]
0x18003b8c6  test    eax, eax
0x18003b8c8  jz      loc_18003BA59
0x18003b8ce  dec     eax
0x18003b8d0  movzx   r9d, cx
0x18003b8d4  mov     [rsi+80h], eax
0x18003b8da  movzx   r8d, dx
0x18003b8de  test    eax, eax
0x18003b8e0  jz      loc_18003BA59
0x18003b8e6  dec     eax
0x18003b8e8  imul    eax, [rsi+70h]
0x18003b8ec  add     rax, [rsi+78h]
0x18003b8f0  dec     r9w
0x18003b8f4  mov     [rsi+98h], rax
0x18003b8fb  sub     r8w, 1
0x18003b900  mov     [rsi+0B2h], r9w
0x18003b908  mov     [rsi+0A0h], r8w
0x18003b910  movzx   edx, r8w
0x18003b914  movzx   ecx, r9w
0x18003b918  jnz     short loc_18003B8C0
0x18003b91a  movsxd  rdx, dword ptr [rsi+90h]
  ... truncated ...
```
