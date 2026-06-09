# DhcpInform

- ea: `0x18006e720`
- end: `0x18006f244`
- name: `DhcpInform`
- size: `2852`
- prototype: `void __stdcall(PVOID)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18006e720`
- `0x18006f864`
- `0x180076ccc`
- `0x180077552`
- `0x18007755e`
- `0x180077590`
- `0x180077620`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e8b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e92b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ea71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006efc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e8b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e92b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ea71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006efc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f047`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e881`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ea5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ebeb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ed3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ee14`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e881`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ea5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ebeb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ed3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ee14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ea50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ed31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006edf7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f1e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f1ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f1f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f201`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f210`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f219`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ea50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ed31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006edf7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f1e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f1ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f1f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f201`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f210`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f219`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006eae9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006eae9`
- `dhcpcsvc!DhcpRequestParams` at `0x18006ea3a`
- `dhcpcsvc!DhcpRequestParams` at `0x18006ea3a`

## string_xrefs

- `0x18006f136`: `DhcpInform: Send reponse to Protocol engine`
- `0x18006f14b`: `DhcpInform: Send reponse to Protocol engine`
- `0x18006f187`: `DhcpInform: SendMessageToProtocolEngine=%d`
- `0x18006f1bf`: `DhcpInform: SendMessageToProtocolEngine=%d`
- `0x18006e913`: `DhcpInform: No need to send response to Protocol engine`
- `0x18006f1cd`: `DhcpInform: No need to send response to Protocol engine`

## pseudocode

```c
void __fastcall DhcpInform(_DWORD *a1)
{
  unsigned int *v2; // r14
  void *v3; // r12
  unsigned int v4; // esi
  ULONG v5; // ebx
  BYTE *Buffer; // r13
  DWORD LastError; // eax
  const CHAR *v8; // rcx
  __int64 v9; // r8
  int v10; // edi
  WCHAR *v11; // r8
  DWORD v12; // eax
  DWORD v13; // ebx
  unsigned int v14; // edx
  int v15; // r13d
  int v16; // edi
  ULONG v17; // eax
  __int64 v18; // rbx
  unsigned int v19; // edx
  char *v20; // rax
  _DWORD *v21; // rdi
  unsigned int v22; // edx
  int i; // r14d
  __int64 v24; // r8
  unsigned int *v25; // rax
  unsigned int v26; // edx
  bool v27; // zf
  int v28; // esi
  HLOCAL v29; // rax
  unsigned int v30; // edx
  __int64 v31; // r8
  unsigned int v32; // edx
  unsigned __int8 *v33; // rcx
  DWORD v34; // eax
  HLOCAL v35; // rbx
  unsigned int v36; // eax
  unsigned int v37; // [rsp+50h] [rbp-B0h]
  ULONG v38; // [rsp+58h] [rbp-A8h]
  DWORD pSize; // [rsp+5Ch] [rbp-A4h] BYREF
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h]
  __int64 v43; // [rsp+70h] [rbp-90h]
  unsigned int *v44; // [rsp+78h] [rbp-88h]
  HLOCAL v45; // [rsp+80h] [rbp-80h]
  DHCPCAPI_PARAMS_ARRAY RecdParams; // [rsp+90h] [rbp-70h] BYREF
  DHCPCAPI_PARAMS_ARRAY SendParams; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v48[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-48h]
  __int64 v50; // [rsp+C0h] [rbp-40h]
  __int64 v51; // [rsp+C8h] [rbp-38h]
  int v52; // [rsp+D0h] [rbp-30h]
  unsigned int *v53; // [rsp+D8h] [rbp-28h]
  int v54; // [rsp+E0h] [rbp-20h]
  int v55; // [rsp+E4h] [rbp-1Ch]
  unsigned int v56; // [rsp+E8h] [rbp-18h]
  void *v57; // [rsp+F0h] [rbp-10h]
  HLOCAL v58; // [rsp+F8h] [rbp-8h]
  int v59; // [rsp+1C90h] [rbp+1B90h] BYREF
  __int64 v60; // [rsp+1C94h] [rbp+1B94h]
  void *Src; // [rsp+1CA0h] [rbp+1BA0h]
  size_t Size; // [rsp+1CA8h] [rbp+1BA8h]
  int v63; // [rsp+1CB0h] [rbp+1BB0h]
  __int64 v64; // [rsp+1CB4h] [rbp+1BB4h]
  __int64 v65; // [rsp+1CC0h] [rbp+1BC0h]
  int v66; // [rsp+1CC8h] [rbp+1BC8h]
  int v67; // [rsp+1CD0h] [rbp+1BD0h]
  __int64 v68; // [rsp+1CD4h] [rbp+1BD4h]
  __int64 v69; // [rsp+1CE0h] [rbp+1BE0h]
  int v70; // [rsp+1CE8h] [rbp+1BE8h]
  int v71; // [rsp+1CF0h] [rbp+1BF0h]
  __int64 v72; // [rsp+1CF4h] [rbp+1BF4h]
  __int64 v73; // [rsp+1D00h] [rbp+1C00h]
  int v74; // [rsp+1D08h] [rbp+1C08h]
  int v75; // [rsp+1D10h] [rbp+1C10h]
  __int64 v76; // [rsp+1D14h] [rbp+1C14h]
  __int64 v77; // [rsp+1D20h] [rbp+1C20h]
  int v78; // [rsp+1D28h] [rbp+1C28h]
  int v79; // [rsp+1D30h] [rbp+1C30h]
  __int64 v80; // [rsp+1D34h] [rbp+1C34h]
  __int64 v81; // [rsp+1D40h] [rbp+1C40h]
  int v82; // [rsp+1D48h] [rbp+1C48h]
  int v83; // [rsp+1D50h] [rbp+1C50h] BYREF
  char v84[2044]; // [rsp+1D54h] [rbp+1C54h] BYREF

  v48[1] = 0;
  memset_0(v48, 0, 0x1BDCu);
  v64 = 44;
  v44 = 0;
  v40 = 0;
  v2 = 0;
  v41 = 0;
  hMem = 0;
  v3 = 0;
  v59 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  v4 = 0;
  v63 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v60 = 6;
  v68 = 43;
  v72 = 1;
  v76 = 249;
  v80 = 15;
  v43 = 0;
  pSize = 2048;
  memset_0(v84, 0, sizeof(v84));
  v5 = 5;
  if ( a1[6] )
    v5 = 6;
  v38 = v5;
  v45 = LocalAlloc(0x40u, 0x800u);
  Buffer = (BYTE *)v45;
  if ( !v45 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( unk_1800AB320 )
      {
        LOWORD(v83) = 0;
        LastError = GetLastError();
        FormatRRASErrorString(&v83, L"DhcpInform:LocalAlloc=%d", LastError);
LABEL_8:
        ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, unk_1800AB320, &v83);
      }
    }
    else
    {
      GetLastError();
      v8 = "DhcpInform:LocalAlloc=%d";
LABEL_13:
      TraceHlp(v8);
    }
    goto LABEL_9;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800AB328 )
    {
      v9 = *(_QWORD *)a1;
      LOWORD(v83) = 0;
      FormatRRASErrorString(&v83, L"DhcpRequestParams(%ws)...", v9);
      ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800AB328, &v83);
    }
  }
  else
  {
    TraceHlp("DhcpRequestParams(%ws)...");
  }
  v10 = 4;
  while ( 1 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800AB328 )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
          gIphlpEtwContext,
          xmmword_1800AB328,
          L"DhcpRequestParams Start");
    }
    else
    {
      TraceHlp("DhcpRequestParams Start");
    }
    v11 = *(WCHAR **)a1;
    *(&RecdParams.nParams + 1) = v43;
    RecdParams.Params = (LPDHCPCAPI_PARAMS)&v59;
    *(&SendParams.nParams + 1) = 0;
    RecdParams.nParams = v5;
    SendParams.nParams = 0;
    SendParams.Params = 0;
    v12 = DhcpRequestParams(2u, 0, v11, 0, &SendParams, &RecdParams, Buffer, &pSize, 0);
    v13 = v12;
    if ( v12 == 234 )
    {
      LocalFree(Buffer);
      v45 = LocalAlloc(0x40u, pSize);
      Buffer = (BYTE *)v45;
      if ( v45 )
        goto LABEL_33;
      v13 = GetLastError();
      if ( v13 == 234 )
        goto LABEL_33;
      goto LABEL_26;
    }
    if ( v12 == 2 )
      break;
LABEL_26:
    if ( v13 != 2 )
      goto LABEL_27;
LABEL_33:
    v5 = v38;
  }
  if ( --v10 )
  {
    Sleep(0x3E8u);
    goto LABEL_33;
  }
LABEL_27:
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800AB328 )
    {
      LOWORD(v83) = 0;
      FormatRRASErrorString(&v83, L"DhcpRequestParams done(%d)", v13);
      ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800AB328, &v83);
    }
  }
  else
  {
    TraceHlp("DhcpRequestParams done(%d)");
  }
  if ( v13 )
  {
LABEL_9:
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800AB328 )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
          gIphlpEtwContext,
          xmmword_1800AB328,
          L"DhcpInform: No need to send response to Protocol engine");
    }
    else
    {
      TraceHlp("DhcpInform: No need to send response to Protocol engine");
    }
    v35 = hMem;
LABEL_128:
    LocalFree(*(HLOCAL *)a1);
    LocalFree(v35);
    LocalFree(v2);
    if ( v3 )
      LocalFree(v3);
    goto LABEL_130;
  }
  v14 = 0;
  v15 = 0;
  v37 = 0;
  v16 = 0;
  v17 = 0;
  while ( 2 )
  {
    LODWORD(v43) = v17;
    if ( v17 < v38 )
    {
      v18 = 32LL * v17;
      if ( *(_DWORD *)((char *)&v60 + v18) != 1 )
      {
        if ( *((_DWORD *)&v60 + 8 * v17) != 6 )
        {
          switch ( *((_DWORD *)&v60 + 8 * v17) )
          {
            case 0xF:
              v28 = *((_DWORD *)&Size + 8 * v17);
              if ( !v28 )
                goto LABEL_116;
              if ( v3 )
                LocalFree(v3);
              v29 = LocalAlloc(0x40u, (unsigned int)(v28 + 1));
              v4 = 0;
              v3 = v29;
              if ( !v29 )
              {
LABEL_95:
                if ( !gIsIphlpEtwTracingAvailable )
                {
                  GetLastError();
                  v8 = "DhcpInform: LocalAlloc=%d";
                  goto LABEL_13;
                }
                if ( !unk_1800AB320 )
                  goto LABEL_9;
                LOWORD(v83) = 0;
                v34 = GetLastError();
                FormatRRASErrorString(&v83, L"DhcpInform: LocalAlloc=%d", v34);
                goto LABEL_8;
              }
              memcpy_0(v29, *(void **)((char *)&Src + v18), *(unsigned int *)((char *)&Size + v18));
              if ( gIsIphlpEtwTracingAvailable )
              {
                if ( (_QWORD)xmmword_1800AB328 )
                {
                  LOWORD(v83) = 0;
                  FormatRRASErrorString(&v83, L"DhcpInform: DOMAIN_NAME %hs", v3);
                  ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(
                    gIphlpEtwContext,
                    xmmword_1800AB328,
                    &v83);
                }
              }
              else
              {
                TraceHlp("DhcpInform: DOMAIN_NAME %hs");
              }
LABEL_51:
              v16 = 1;
              break;
            case 0x2C:
              v22 = *((_DWORD *)&Size + 8 * v17);
              if ( !v22 )
                goto LABEL_115;
              if ( (v22 & 3) != 0 )
              {
                if ( !gIsIphlpEtwTracingAvailable )
                {
                  v8 = "Invalid NETBIOS_NAME_SERVER size %d";
                  goto LABEL_13;
                }
                if ( !unk_1800AB320 )
                  goto LABEL_9;
                LOWORD(v83) = 0;
                FormatRRASErrorString(&v83, L"Invalid NETBIOS_NAME_SERVER size %d", v22);
                goto LABEL_8;
              }
              for ( i = 0; i < 2; ++i )
              {
                v24 = *(__int64 *)((char *)&Src + v18);
                v25 = (unsigned int *)&v41;
                v26 = *(unsigned __int8 *)(v4 + v24)
                    + (*(unsigned __int8 *)(v4 + 1 + v24) << 8)
                    + (*(unsigned __int8 *)(v4 + 2 + v24) << 16)
                    + (*(unsigned __int8 *)(v4 + 3 + v24) << 24);
                if ( !i )
                  v25 = (unsigned int *)&v40;
                v27 = gIsIphlpEtwTracingAvailable == 0;
                *v25 = v26;
                if ( v27 )
                {
                  TraceHlp("DhcpInform: NETBIOS_NAME_SERVER 0x%x");
                }
                else if ( (_QWORD)xmmword_1800AB328 )
                {
                  LOWORD(v83) = 0;
                  FormatRRASErrorString(&v83, L"DhcpInform: NETBIOS_NAME_SERVER 0x%x", v26);
                  ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(
                    gIphlpEtwContext,
                    xmmword_1800AB328,
                    &v83);
                }
                v4 += 4;
                v16 = 1;
                if ( v4 == *(_DWORD *)((char *)&Size + v18) )
                  break;
              }
              v2 = v44;
LABEL_92:
              v4 = 0;
              break;
            case 0xF9:
              v19 = *((_DWORD *)&Size + 8 * v17);
              if ( !v19 )
                goto LABEL_115;
              if ( v19 < 5 )
              {
                if ( !gIsIphlpEtwTracingAvailable )
                {
                  v8 = "Invalid OPTION_VENDOR_ROUTE_PLUMB size %d";
                  goto LABEL_13;
                }
                if ( !unk_1800AB320 )
                  goto LABEL_9;
                LOWORD(v83) = 0;
                FormatRRASErrorString(&v83, L"Invalid OPTION_VENDOR_ROUTE_PLUMB size %d", v19);
                goto LABEL_8;
              }
              if ( gIsIphlpEtwTracingAvailable )
              {
                if ( (_QWORD)xmmword_1800AB328 )
                {
                  LOWORD(v83) = 0;
                  FormatRRASErrorString(&v83, L"DhcpInform: OPTION_VENDOR_ROUTE_PLUMB Code Len 0x%x", v19);
                  ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(
                    gIphlpEtwContext,
                    xmmword_1800AB328,
                    &v83);
                }
              }
              else
              {
                TraceHlp("DhcpInform: OPTION_VENDOR_ROUTE_PLUMB Code Len 0x%x");
              }
              v20 = (char *)LocalAlloc(0x40u, *(unsigned int *)((char *)&Size + v18) + 4LL);
              hMem = v20;
              v21 = v20;
              if ( !v20 )
                goto LABEL_95;
              memcpy_0(v20 + 4, *(void **)((char *)&Src + v18), *(unsigned int *)((char *)&Size + v18));
              *v21 = *(_DWORD *)((char *)&Size + v18);
              goto LABEL_51;
            default:
LABEL_94:
              v17 = v43 + 1;
              continue;
          }
          v14 = v37;
          goto LABEL_94;
        }
        v30 = *((_DWORD *)&Size + 8 * v17);
        if ( !v30 )
          goto LABEL_115;
        if ( (v30 & 3) != 0 )
        {
          if ( !gIsIphlpEtwTracingAvailable )
          {
            v8 = "Invalid DOMAIN_NAME_SERVERS size %d";
            goto LABEL_13;
          }
          if ( !unk_1800AB320 )
            goto LABEL_9;
          LOWORD(v83) = 0;
          FormatRRASErrorString(&v83, L"Invalid DOMAIN_NAME_SERVERS size %d", v30);
          goto LABEL_8;
        }
        if ( v2 )
        {
          LocalFree(v2);
          v15 = 0;
        }
        v44 = (unsigned int *)LocalAlloc(0x40u, *(_DWORD *)((_BYTE *)&Size + v18) & 0xFFFFFFFC);
        v2 = v44;
        if ( !v44 )
          goto LABEL_95;
        while ( v4 < *(_DWORD *)((char *)&Size + v18) )
        {
          v31 = *(__int64 *)((char *)&Src + v18);
          v27 = gIsIphlpEtwTracingAvailable == 0;
          v2[v15] = *(unsigned __int8 *)(v4 + v31)
                  + (*(unsigned __int8 *)(v4 + 1 + v31) << 8)
                  + (*(unsigned __int8 *)(v4 + 2 + v31) << 16)
                  + (*(unsigned __int8 *)(v4 + 3 + v31) << 24);
          if ( v27 )
          {
            TraceHlp("DhcpInform: DOMAIN_NAME_SERVER 0x%x");
          }
          else if ( (_QWORD)xmmword_1800AB328 )
          {
            LOWORD(v83) = 0;
            FormatRRASErrorString(&v83, L"DhcpInform: DOMAIN_NAME_SERVER 0x%x", v2[v15]);
            ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800AB328, &v83);
          }
          v4 += 4;
          v16 = 1;
          ++v15;
        }
        goto LABEL_92;
      }
      v32 = *((_DWORD *)&Size + 8 * v17);
      if ( !v32 )
      {
LABEL_115:
        v14 = v37;
        break;
      }
      if ( (v32 & 3) != 0 )
      {
        if ( !gIsIphlpEtwTracingAvailable )
        {
          v8 = "Invalid OPTION_SUBNET_MASK size %d";
          goto LABEL_13;
        }
        if ( !unk_1800AB320 )
          goto LABEL_9;
        LOWORD(v83) = 0;
        FormatRRASErrorString(&v83, L"Invalid OPTION_SUBNET_MASK size %d", v32);
        goto LABEL_8;
      }
      v33 = (unsigned __int8 *)*(&Src + 4 * v17);
      v14 = *v33 + (v33[1] << 8) + (v33[2] << 16) + (v33[3] << 24);
      v37 = v14;
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800AB328 )
        {
          LOWORD(v83) = 0;
          FormatRRASErrorString(&v83, L"DhcpInform: OPTION_SUBNET_MASK 0x%x", v14);
          ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800AB328, &v83);
          goto LABEL_89;
        }
      }
      else
      {
        TraceHlp("DhcpInform: OPTION_SUBNET_MASK 0x%x");
LABEL_89:
        v14 = v37;
      }
      v16 = 1;
      goto LABEL_94;
    }
    break;
  }
LABEL_116:
  if ( !v16 )
    goto LABEL_9;
  v35 = hMem;
  v50 = *((_QWORD *)a1 + 1);
  v49 = *((_QWORD *)a1 + 2);
  v51 = *(_QWORD *)a1;
  v54 = v40;
  v55 = v41;
  v48[0] = 11;
  v52 = v15;
  v53 = v2;
  v56 = v14;
  v57 = v3;
  v58 = hMem;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800AB328 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        xmmword_1800AB328,
        L"DhcpInform: Send reponse to Protocol engine");
  }
  else
  {
    TraceHlp("DhcpInform: Send reponse to Protocol engine");
  }
  v36 = (*((__int64 (__fastcall **)(_DWORD *))a1 + 4))(v48);
  if ( v36 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( unk_1800AB320 )
      {
        LOWORD(v83) = 0;
        FormatRRASErrorString(&v83, L"DhcpInform: SendMessageToProtocolEngine=%d", v36);
        ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, unk_1800AB320, &v83);
      }
    }
    else
    {
      TraceHlp("DhcpInform: SendMessageToProtocolEngine=%d");
    }
    goto LABEL_128;
  }
LABEL_130:
  if ( v45 )
    LocalFree(v45);
  LocalFree(a1);
}

```

## disassembly

```asm
0x18006e720  push    rbp
0x18006e722  push    rbx
0x18006e723  push    rsi
0x18006e724  push    rdi
0x18006e725  push    r12
0x18006e727  push    r13
0x18006e729  push    r14
0x18006e72b  push    r15
0x18006e72d  lea     rbp, [rsp-2468h]
0x18006e735  mov     eax, 2568h
0x18006e73a  call    _alloca_probe
0x18006e73f  sub     rsp, rax
0x18006e742  mov     rax, cs:__security_cookie
0x18006e749  xor     rax, rsp
0x18006e74c  mov     [rbp+24A0h+var_50], rax
0x18006e753  mov     r15, rcx
0x18006e756  xor     eax, eax
0x18006e758  lea     rcx, [rbp+24A0h+var_24F0]; void *
0x18006e75c  mov     [rbp+24A0h+var_24EC], eax
0x18006e75f  xor     edx, edx; Val
0x18006e761  mov     r8d, 1BDCh; Size
0x18006e767  call    memset_0
0x18006e76c  xor     ecx, ecx
0x18006e76e  mov     [rbp+24A0h+var_8EC], 2Ch ; ','
0x18006e779  xor     eax, eax
0x18006e77b  mov     [rsp+25A0h+var_2528], rcx
0x18006e780  mov     edi, 800h
0x18006e785  mov     [rsp+25A0h+var_2540], ecx
0x18006e789  mov     r14d, ecx
0x18006e78c  mov     [rsp+25A0h+var_253C], ecx
0x18006e790  lea     r13d, [rcx+6]
0x18006e794  mov     [rsp+25A0h+hMem], rcx
0x18006e799  mov     r12d, ecx
0x18006e79c  mov     [rbp+24A0h+var_910], ecx
0x18006e7a2  mov     [rbp+24A0h+Src], rcx
0x18006e7a9  lea     r8d, [rdi-4]; Size
0x18006e7ad  mov     dword ptr [rbp+24A0h+Size], ecx
0x18006e7b3  mov     esi, ecx
0x18006e7b5  mov     [rbp+24A0h+var_8F0], ecx
0x18006e7bb  xor     edx, edx; Val
0x18006e7bd  mov     [rbp+24A0h+var_8E0], rcx
0x18006e7c4  mov     [rbp+24A0h+var_8D8], ecx
0x18006e7ca  mov     [rbp+24A0h+var_8D0], ecx
0x18006e7d0  mov     [rbp+24A0h+var_8C0], rcx
0x18006e7d7  mov     [rbp+24A0h+var_8B8], ecx
0x18006e7dd  mov     [rbp+24A0h+var_8B0], ecx
0x18006e7e3  mov     [rbp+24A0h+var_8A0], rcx
0x18006e7ea  mov     [rbp+24A0h+var_898], ecx
0x18006e7f0  mov     [rbp+24A0h+var_890], ecx
0x18006e7f6  mov     [rbp+24A0h+var_880], rcx
0x18006e7fd  mov     [rbp+24A0h+var_878], ecx
0x18006e803  mov     [rbp+24A0h+var_870], ecx
0x18006e809  mov     [rbp+24A0h+var_860], rcx
0x18006e810  mov     [rbp+24A0h+var_858], ecx
0x18006e816  mov     [rbp+24A0h+var_850], ecx
0x18006e81c  lea     rcx, [rbp+24A0h+var_84C]; void *
0x18006e823  mov     [rbp+24A0h+var_90C], r13
0x18006e82a  mov     [rbp+24A0h+var_8CC], 2Bh ; '+'
0x18006e835  mov     [rbp+24A0h+var_8AC], 1
0x18006e840  mov     [rbp+24A0h+var_88C], 0F9h
0x18006e84b  mov     [rbp+24A0h+var_86C], 0Fh
0x18006e856  mov     [rsp+25A0h+var_2530], rax
0x18006e85b  mov     [rsp+25A0h+var_2550], rax
0x18006e860  mov     [rsp+25A0h+var_2544], edi
0x18006e864  call    memset_0
0x18006e869  cmp     [r15+18h], esi
0x18006e86d  lea     ebx, [r12+5]
0x18006e872  mov     edx, edi; uBytes
0x18006e874  lea     ecx, [r12+40h]; uFlags
0x18006e879  cmovnz  ebx, r13d
0x18006e87d  mov     [rsp+25A0h+var_2548], ebx
0x18006e881  call    cs:__imp_LocalAlloc
0x18006e887  mov     [rbp+24A0h+var_2520], rax
0x18006e88b  mov     r13, rax
0x18006e88e  test    rax, rax
0x18006e891  jnz     loc_18006E941
0x18006e897  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x18006e89d  jz      loc_18006E92B
0x18006e8a3  cmp     qword ptr cs:unk_1800AB320, rsi
0x18006e8aa  jz      short loc_18006E8F0
0x18006e8ac  mov     word ptr [rbp+24A0h+var_850], si
0x18006e8b3  call    cs:__imp_GetLastError
0x18006e8b9  lea     rdx, aDhcpinformLoca; "DhcpInform:LocalAlloc=%d"
0x18006e8c0  mov     r8d, eax
0x18006e8c3  lea     rcx, [rbp+24A0h+var_850]
0x18006e8ca  call    FormatRRASErrorString
0x18006e8cf  mov     rdx, qword ptr cs:unk_1800AB320
0x18006e8d6  lea     r8, [rbp+24A0h+var_850]
0x18006e8dd  mov     rcx, cs:gIphlpEtwContext
0x18006e8e4  mov     rax, cs:gIphlpTemplateFunc
0x18006e8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e8f0  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x18006e8f6  jz      loc_18006F1CD
0x18006e8fc  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006e903  test    rdx, rdx
0x18006e906  jz      loc_18006F1D9
0x18006e90c  mov     rcx, cs:gIphlpEtwContext
0x18006e913  lea     r8, aDhcpinformNoNe; "DhcpInform: No need to send response to"...
0x18006e91a  mov     rax, cs:gIphlpTemplateFunc
0x18006e921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e926  jmp     loc_18006F1D9
0x18006e92b  call    cs:__imp_GetLastError
0x18006e931  lea     rcx, aDhcpinformLoca_0; "DhcpInform:LocalAlloc=%d"
0x18006e938  mov     edx, eax
0x18006e93a  call    TraceHlp
0x18006e93f  jmp     short loc_18006E8F0
0x18006e941  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x18006e947  jz      short loc_18006E994
0x18006e949  cmp     qword ptr cs:xmmword_1800AB328, rsi
0x18006e950  jz      short loc_18006E9A3
0x18006e952  mov     r8, [r15]
0x18006e955  lea     rdx, aDhcprequestpar_0; "DhcpRequestParams(%ws)..."
0x18006e95c  xor     eax, eax
0x18006e95e  lea     rcx, [rbp+24A0h+var_850]
0x18006e965  mov     word ptr [rbp+24A0h+var_850], ax
0x18006e96c  call    FormatRRASErrorString
0x18006e971  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006e978  lea     r8, [rbp+24A0h+var_850]
0x18006e97f  mov     rcx, cs:gIphlpEtwContext
0x18006e986  mov     rax, cs:gIphlpTemplateFunc
0x18006e98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e992  jmp     short loc_18006E9A3
0x18006e994  mov     rdx, [r15]
0x18006e997  lea     rcx, aDhcprequestpar_1; "DhcpRequestParams(%ws)..."
0x18006e99e  call    TraceHlp
0x18006e9a3  mov     edi, 4
0x18006e9a8  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x18006e9ae  jz      short loc_18006E9D8
0x18006e9b0  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006e9b7  test    rdx, rdx
0x18006e9ba  jz      short loc_18006E9E4
0x18006e9bc  mov     rcx, cs:gIphlpEtwContext
0x18006e9c3  lea     r8, aDhcprequestpar_4; "DhcpRequestParams Start"
0x18006e9ca  mov     rax, cs:gIphlpTemplateFunc
0x18006e9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e9d6  jmp     short loc_18006E9E4
0x18006e9d8  lea     rcx, aDhcprequestpar_3; "DhcpRequestParams Start"
0x18006e9df  call    TraceHlp
0x18006e9e4  mov     rax, [rsp+25A0h+var_2530]
0x18006e9e9  xor     edx, edx; Reserved
0x18006e9eb  mov     r8, [r15]; AdapterName
0x18006e9ee  xor     r9d, r9d; ClassId
0x18006e9f1  mov     dword ptr [rbp+24A0h+var_2510+4], eax
0x18006e9f4  lea     rax, [rbp+24A0h+var_910]
0x18006e9fb  mov     [rbp+24A0h+var_2510.Params], rax
0x18006e9ff  mov     rax, [rsp+25A0h+var_2550]
0x18006ea04  lea     ecx, [rdx+2]; Flags
0x18006ea07  mov     dword ptr [rbp+24A0h+var_2500+4], eax
0x18006ea0a  lea     rax, [rsp+25A0h+var_2544]
0x18006ea0f  mov     [rsp+25A0h+RequestIdStr], rsi; RequestIdStr
0x18006ea14  mov     [rsp+25A0h+pSize], rax; pSize
0x18006ea19  lea     rax, [rbp+24A0h+var_2510]
0x18006ea1d  mov     [rsp+25A0h+Buffer], r13; Buffer
0x18006ea22  mov     [rsp+25A0h+RecdParams], rax; RecdParams
0x18006ea27  lea     rax, [rbp+24A0h+var_2500]
0x18006ea2b  mov     [rsp+25A0h+SendParams], rax; SendParams
0x18006ea30  mov     [rbp+24A0h+var_2510.nParams], ebx
0x18006ea33  mov     [rbp+24A0h+var_2500.nParams], esi
0x18006ea36  mov     [rbp+24A0h+var_2500.Params], rsi
0x18006ea3a  call    cs:__imp_DhcpRequestParams
0x18006ea40  mov     ebx, eax
0x18006ea42  cmp     eax, 0EAh
0x18006ea47  jnz     loc_18006EADA
0x18006ea4d  mov     rcx, r13; hMem
0x18006ea50  call    cs:__imp_LocalFree
0x18006ea56  mov     edx, [rsp+25A0h+var_2544]; uBytes
0x18006ea5a  mov     ecx, 40h ; '@'; uFlags
0x18006ea5f  call    cs:__imp_LocalAlloc
0x18006ea65  mov     [rbp+24A0h+var_2520], rax
0x18006ea69  mov     r13, rax
0x18006ea6c  test    rax, rax
0x18006ea6f  jnz     short loc_18006EAEF
0x18006ea71  call    cs:__imp_GetLastError
0x18006ea77  mov     ebx, eax
0x18006ea79  cmp     eax, 0EAh
0x18006ea7e  jz      short loc_18006EAEF
0x18006ea80  cmp     ebx, 2
0x18006ea83  jnz     short loc_18006EA89
0x18006ea85  test    edi, edi
0x18006ea87  jnz     short loc_18006EAEF
0x18006ea89  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x18006ea8f  jz      short loc_18006EAF8
0x18006ea91  cmp     qword ptr cs:xmmword_1800AB328, rsi
0x18006ea98  jz      short loc_18006EB06
0x18006ea9a  mov     r8d, ebx
0x18006ea9d  mov     word ptr [rbp+24A0h+var_850], si
0x18006eaa4  lea     rdx, aDhcprequestpar_2; "DhcpRequestParams done(%d)"
0x18006eaab  lea     rcx, [rbp+24A0h+var_850]
0x18006eab2  call    FormatRRASErrorString
0x18006eab7  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006eabe  lea     r8, [rbp+24A0h+var_850]
0x18006eac5  mov     rcx, cs:gIphlpEtwContext
0x18006eacc  mov     rax, cs:gIphlpTemplateFunc
0x18006ead3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ead8  jmp     short loc_18006EB06
0x18006eada  cmp     eax, 2
0x18006eadd  jnz     short loc_18006EA80
0x18006eadf  sub     edi, 1
0x18006eae2  jz      short loc_18006EA89
0x18006eae4  mov     ecx, 3E8h; dwMilliseconds
0x18006eae9  call    cs:__imp_Sleep
0x18006eaef  mov     ebx, [rsp+25A0h+var_2548]
0x18006eaf3  jmp     loc_18006E9A8
0x18006eaf8  mov     edx, ebx
0x18006eafa  lea     rcx, aDhcprequestpar_5; "DhcpRequestParams done(%d)"
0x18006eb01  call    TraceHlp
0x18006eb06  test    ebx, ebx
0x18006eb08  jnz     loc_18006E8F0
0x18006eb0e  mov     edx, esi
0x18006eb10  mov     r13d, esi
0x18006eb13  mov     dword ptr [rsp+25A0h+var_2550], edx
0x18006eb17  mov     edi, esi
0x18006eb19  mov     eax, esi
0x18006eb1b  mov     dword ptr [rsp+25A0h+var_2530], eax
0x18006eb1f  cmp     eax, [rsp+25A0h+var_2548]
0x18006eb23  jnb     loc_18006F0CF
0x18006eb29  mov     ebx, eax
0x18006eb2b  shl     rbx, 5
0x18006eb2f  mov     ecx, dword ptr [rbp+rbx+24A0h+var_90C]
0x18006eb36  sub     ecx, 1
0x18006eb39  jz      loc_18006EEE7
0x18006eb3f  sub     ecx, 5
0x18006eb42  jz      loc_18006EDD7
0x18006eb48  sub     ecx, 9
0x18006eb4b  jz      loc_18006ED1A
0x18006eb51  sub     ecx, 1Dh
0x18006eb54  jz      loc_18006EC2E
0x18006eb5a  cmp     ecx, 0CDh
0x18006eb60  jnz     loc_18006EF9C
0x18006eb66  mov     edx, dword ptr [rbp+rbx+24A0h+Size]
0x18006eb6d  test    edx, edx
0x18006eb6f  jz      loc_18006F0C7
0x18006eb75  cmp     edx, 5
0x18006eb78  jb      loc_18006EFD9
0x18006eb7e  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x18006eb84  jz      short loc_18006EBCF
0x18006eb86  cmp     qword ptr cs:xmmword_1800AB328, rsi
0x18006eb8d  jz      short loc_18006EBDB
0x18006eb8f  mov     r8d, edx
0x18006eb92  mov     word ptr [rbp+24A0h+var_850], si
0x18006eb99  lea     rdx, aDhcpinformOpti_0; "DhcpInform: OPTION_VENDOR_ROUTE_PLUMB C"...
0x18006eba0  lea     rcx, [rbp+24A0h+var_850]
0x18006eba7  call    FormatRRASErrorString
0x18006ebac  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006ebb3  lea     r8, [rbp+24A0h+var_850]
0x18006ebba  mov     rcx, cs:gIphlpEtwContext
0x18006ebc1  mov     rax, cs:gIphlpTemplateFunc
0x18006ebc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ebcd  jmp     short loc_18006EBDB
0x18006ebcf  lea     rcx, aDhcpinformOpti_2; "DhcpInform: OPTION_VENDOR_ROUTE_PLUMB C"...
0x18006ebd6  call    TraceHlp
0x18006ebdb  mov     edx, dword ptr [rbp+rbx+24A0h+Size]
0x18006ebe2  mov     ecx, 40h ; '@'; uFlags
0x18006ebe7  add     rdx, 4; uBytes
0x18006ebeb  call    cs:__imp_LocalAlloc
0x18006ebf1  mov     [rsp+25A0h+hMem], rax
0x18006ebf6  mov     rdi, rax
0x18006ebf9  test    rax, rax
0x18006ebfc  jz      loc_18006EFA7
0x18006ec02  mov     r8d, dword ptr [rbp+rbx+24A0h+Size]; Size
0x18006ec0a  lea     rcx, [rax+4]; void *
0x18006ec0e  mov     rdx, [rbp+rbx+24A0h+Src]; Src
0x18006ec16  call    memcpy_0
0x18006ec1b  mov     ecx, dword ptr [rbp+rbx+24A0h+Size]
0x18006ec22  mov     [rdi], ecx
0x18006ec24  mov     edi, 1
0x18006ec29  jmp     loc_18006EF98
0x18006ec2e  mov     edx, dword ptr [rbp+rbx+24A0h+Size]
0x18006ec35  test    edx, edx
0x18006ec37  jz      loc_18006F0C7
0x18006ec3d  test    dl, 3
0x18006ec40  jnz     loc_18006F010
0x18006ec46  xor     r14d, r14d
0x18006ec49  cmp     r14d, 2
0x18006ec4d  jge     loc_18006EF91
0x18006ec53  mov     r8, [rbp+rbx+24A0h+Src]
0x18006ec5b  lea     eax, [rsi+3]
0x18006ec5e  movzx   edx, byte ptr [rax+r8]
0x18006ec63  lea     eax, [rsi+2]
0x18006ec66  movzx   eax, byte ptr [rax+r8]
0x18006ec6b  shl     eax, 10h
0x18006ec6e  shl     edx, 18h
0x18006ec71  add     edx, eax
0x18006ec73  lea     eax, [rsi+1]
0x18006ec76  movzx   eax, byte ptr [rax+r8]
0x18006ec7b  shl     eax, 8
0x18006ec7e  add     edx, eax
0x18006ec80  mov     eax, esi
0x18006ec82  movzx   ecx, byte ptr [rax+r8]
0x18006ec87  lea     rax, [rsp+25A0h+var_253C]
0x18006ec8c  add     edx, ecx
0x18006ec8e  lea     rcx, [rsp+25A0h+var_2540]
0x18006ec93  test    r14d, r14d
0x18006ec96  cmovz   rax, rcx
0x18006ec9a  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006eca1  mov     [rax], edx
0x18006eca3  jz      short loc_18006ECF1
0x18006eca5  cmp     qword ptr cs:xmmword_1800AB328, 0
0x18006ecad  jz      short loc_18006ECFD
0x18006ecaf  xor     eax, eax
  ... truncated ...
```
