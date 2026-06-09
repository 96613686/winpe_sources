# ClientEAPAuthHandler::GetIDFromCert(_CERT_CONTEXT const *,_IKE_ID_PAYLOAD * *)

- ea: `0x180042ad8`
- end: `0x1800435ca`
- name: `?GetIDFromCert@ClientEAPAuthHandler@@IEAAKPEBU_CERT_CONTEXT@@PEAPEAU_IKE_ID_PAYLOAD@@@Z`
- size: `2802`
- prototype: `__int64 __fastcall(void **this, const struct _CERT_CONTEXT *, struct _IKE_ID_PAYLOAD **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800435d0`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180008a7c`
- `0x18000a0d0`
- `0x180042ad8`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `msvcrt!wcschr` at `0x1800430b8`
- `msvcrt!wcschr` at `0x1800430b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043427`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043444`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043427`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043444`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042e70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042e70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042e5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043419`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043436`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042e5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043419`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800434d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800434d6`
- `CRYPT32!CryptDecodeObject` at `0x180042e41`
- `CRYPT32!CryptDecodeObject` at `0x180042fa8`
- `CRYPT32!CryptDecodeObject` at `0x180042e41`
- `CRYPT32!CryptDecodeObject` at `0x180042fa8`
- `CRYPT32!CertFindExtension` at `0x180042d0d`
- `CRYPT32!CertFindExtension` at `0x180042d0d`

## string_xrefs

- `0x18004335b`: `StringCopyWtoAAlloc failed: %d`

## pseudocode

```c
__int64 __fastcall ClientEAPAuthHandler::GetIDFromCert(
        void **this,
        const struct _CERT_CONTEXT *a2,
        struct _IKE_ID_PAYLOAD **a3)
{
  PVOID *v6; // rbx
  void *v7; // r15
  unsigned int v8; // esi
  char v9; // al
  _QWORD *v10; // rax
  __int64 v11; // rax
  char *v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  __int128 *v15; // r9
  __int64 v16; // r9
  __int64 v17; // rdx
  PCERT_EXTENSION Extension; // r14
  _QWORD *v19; // rax
  __int64 v20; // rax
  char *v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // rcx
  __int128 *v24; // r9
  unsigned int v25; // eax
  DWORD v26; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *pvStructInfo; // rax
  _QWORD *v29; // r13
  _QWORD *v30; // rax
  __int64 v31; // rax
  char *v32; // rcx
  _QWORD *v33; // rax
  __int64 v34; // rcx
  __int128 *v35; // r9
  _QWORD *v36; // rax
  __int64 v37; // rax
  DWORD LastError; // eax
  char *v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rcx
  __int128 *v42; // r9
  __int64 i; // rbx
  __int64 v44; // r14
  __int64 v45; // rax
  wchar_t *v46; // r14
  _QWORD *v47; // rax
  __int64 v48; // rax
  __int64 v49; // rdx
  char *v50; // rcx
  _QWORD *v51; // rax
  __int64 v52; // rcx
  __int128 *v53; // r9
  const WCHAR *v54; // rbx
  _QWORD *v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdx
  _QWORD *v58; // rax
  __int64 v59; // rax
  __int64 v60; // rdx
  char *v61; // rcx
  _QWORD *v62; // rax
  __int64 v63; // rcx
  __int128 *v64; // r9
  unsigned int v65; // eax
  __int64 v66; // rcx
  _QWORD *v67; // rax
  __int64 v68; // rax
  char *v69; // rcx
  _QWORD *v70; // rax
  __int64 v71; // rcx
  __int128 *v72; // r9
  __int64 v73; // rdx
  HANDLE v74; // rax
  HANDLE v75; // rax
  _QWORD *v76; // rax
  __int64 v77; // rax
  DWORD v78; // eax
  char *v79; // rcx
  _QWORD *v80; // rax
  __int64 v81; // rcx
  __int128 *v82; // r9
  unsigned int v83; // ebx
  unsigned int IDObject; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbStructInfo; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h]
  int v88; // [rsp+50h] [rbp-B0h]
  __int64 v89; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v90; // [rsp+60h] [rbp-A0h]
  __int128 v91; // [rsp+70h] [rbp-90h]
  __int64 v92; // [rsp+80h] [rbp-80h]
  int v93; // [rsp+88h] [rbp-78h]
  int v94; // [rsp+8Ch] [rbp-74h]
  __int128 v95; // [rsp+90h] [rbp-70h] BYREF
  int v96; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v97; // [rsp+A4h] [rbp-5Ch]
  __int128 v98; // [rsp+B4h] [rbp-4Ch]
  int v99; // [rsp+C4h] [rbp-3Ch]
  int v100; // [rsp+D0h] [rbp-30h] BYREF
  char v101[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  IDObject = 0;
  pcbStructInfo = 0;
  v88 = 0;
  v7 = 0;
  lpMem = 0;
  v100 = 0;
  memset_0(v101, 0, sizeof(v101));
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  v95 = 0;
  v90 = 0;
  v89 = 0;
  v91 = 0;
  v92 = 0;
  v8 = -1;
  v93 = -1;
  v94 = 0;
  v9 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v89,
      L"ClientEAPAuthHandler::GetIDFromCert",
      &IDObject,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      this[70]);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v9 = byte_1800AA941;
  }
  if ( a3 )
  {
    Extension = CertFindExtension("2.5.29.17", a2->pCertInfo->cExtension, a2->pCertInfo->rgExtension);
    if ( !Extension )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_45;
      LOWORD(v96) = 0;
      v19 = this[70];
      if ( v19 )
      {
        v20 = v19[14];
        if ( v20 )
        {
          if ( *(_QWORD *)(v20 + 16) )
            v8 = *(_DWORD *)(v20 + 16);
        }
      }
      ConvertPortNoToString(&v96, v8);
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_45;
      v21 = (char *)this[70];
      v22 = v21 + 112;
      if ( v21 )
      {
        if ( *v22 )
          v23 = *v22 + 2686LL;
        else
          v23 = 0;
        if ( *v22 )
        {
          v24 = (__int128 *)(*v22 + 2120LL);
LABEL_44:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)L"No subject-alt-name extention found in the certificate.",
            (_DWORD)v24,
            v23,
            (__int64)&v96);
LABEL_45:
          v6 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_187;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_183;
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids);
          goto LABEL_182;
        }
      }
      else
      {
        v23 = 0;
      }
      v24 = &v95;
      goto LABEL_44;
    }
    pcbStructInfo = 0;
    v25 = CryptDecodeObject(
            0x10001u,
            "2.5.29.17",
            Extension->Value.pbData,
            Extension->Value.cbData,
            1u,
            0,
            &pcbStructInfo);
    if ( v25 )
    {
      if ( pcbStructInfo )
      {
        v26 = pcbStructInfo;
        ProcessHeap = GetProcessHeap();
        pvStructInfo = HeapAlloc(ProcessHeap, 8u, v26);
        v29 = pvStructInfo;
        if ( !pvStructInfo )
        {
          IDObject = 8;
          if ( (byte_1800AA941 & 4) == 0 )
          {
LABEL_68:
            v6 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              goto LABEL_187;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_183;
            v17 = 71;
            v16 = IDObject;
            goto LABEL_28;
          }
          LOWORD(v96) = 0;
          v30 = this[70];
          if ( v30 )
          {
            v31 = v30[14];
            if ( v31 )
            {
              if ( *(_QWORD *)(v31 + 16) )
                v8 = *(_DWORD *)(v31 + 16);
            }
          }
          ConvertPortNoToString(&v96, v8);
          if ( (byte_1800AA941 & 4) == 0 )
          {
LABEL_67:
            if ( !IDObject )
              goto LABEL_182;
            goto LABEL_68;
          }
          v32 = (char *)this[70];
          v33 = v32 + 112;
          if ( v32 )
          {
            if ( *v33 )
              v34 = *v33 + 2686LL;
            else
              v34 = 0;
            if ( *v33 )
            {
              v35 = (__int128 *)(*v33 + 2120LL);
LABEL_66:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)L"Memory allocation failed",
                (_DWORD)v35,
                v34,
                (__int64)&v96);
              goto LABEL_67;
            }
          }
          else
          {
            v34 = 0;
          }
          v35 = &v95;
          goto LABEL_66;
        }
        if ( !CryptDecodeObject(
                0x10001u,
                "2.5.29.17",
                Extension->Value.pbData,
                Extension->Value.cbData,
                1u,
                pvStructInfo,
                &pcbStructInfo) )
        {
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_160;
          LOWORD(v100) = 0;
          LOWORD(v96) = 0;
          v36 = this[70];
          if ( v36 )
          {
            v37 = v36[14];
            if ( v37 )
            {
              if ( *(_QWORD *)(v37 + 16) )
                v8 = *(_DWORD *)(v37 + 16);
            }
          }
          ConvertPortNoToString(&v96, v8);
          LastError = GetLastError();
          FormatRRASErrorString(&v100, L"CryptDecodeObject Failed: 0x%x.", LastError);
          if ( (byte_1800AA941 & 4) == 0 )
            goto LABEL_160;
          v39 = (char *)this[70];
          v40 = v39 + 112;
          if ( v39 )
          {
            if ( *v40 )
              v41 = *v40 + 2686LL;
            else
              v41 = 0;
            if ( *v40 )
            {
              v42 = (__int128 *)(*v40 + 2120LL);
LABEL_87:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceError,
                (unsigned int)&v100,
                (_DWORD)v42,
                v41,
                (__int64)&v96);
LABEL_160:
              v74 = GetProcessHeap();
              HeapFree(v74, 0, v29);
              if ( v7 )
              {
                v75 = GetProcessHeap();
                HeapFree(v75, 0, v7);
              }
              goto LABEL_182;
            }
          }
          else
          {
            v41 = 0;
          }
          v42 = &v95;
          goto LABEL_87;
        }
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= *(_DWORD *)v29 )
            goto LABEL_160;
          v44 = 3 * i;
          v45 = v29[1];
          if ( *(_DWORD *)(v45 + 24 * i) == 3 )
            break;
          if ( *(_DWORD *)(v45 + 24 * i) == 2 )
          {
            v46 = wcschr(*(const wchar_t **)(v45 + 24 * i + 8), 0x40u);
            if ( !v46 && (byte_1800AA941 & 8) != 0 )
            {
              LOWORD(v100) = 0;
              LOWORD(v96) = 0;
              v47 = this[70];
              if ( v47 && (v48 = v47[14]) != 0 && *(_QWORD *)(v48 + 16) )
                v49 = *(unsigned int *)(v48 + 16);
              else
                v49 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v96, v49);
              FormatRRASErrorString(
                &v100,
                L"The rfc822 name '%s' in the cert subject-alt-name is not valid.",
                *(_QWORD *)(v29[1] + 24 * i + 8));
              if ( (byte_1800AA941 & 8) != 0 )
              {
                v50 = (char *)this[70];
                v51 = v50 + 112;
                if ( v50 )
                {
                  if ( *v51 )
                    v52 = *v51 + 2686LL;
                  else
                    v52 = 0;
                  if ( *v51 )
                  {
                    v53 = (__int128 *)(*v51 + 2120LL);
                    goto LABEL_109;
                  }
                }
                else
                {
                  v52 = 0;
                }
                v53 = &v95;
LABEL_109:
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasVpnIkeParamTraceInfo,
                  (unsigned int)&v100,
                  (_DWORD)v53,
                  v52,
                  (__int64)&v96);
              }
            }
            v54 = v46 + 1;
            if ( (byte_1800AA941 & 8) != 0 )
            {
              LOWORD(v100) = 0;
              LOWORD(v96) = 0;
              v55 = this[70];
              if ( v55 && (v56 = v55[14]) != 0 && *(_QWORD *)(v56 + 16) )
                v57 = *(unsigned int *)(v56 + 16);
              else
                v57 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v96, v57);
              FormatRRASErrorString(
                &v100,
                L"Sending the FQDN from rfc822 name of the cert subject-alt-name as IDi: %s.",
                v46 + 1);
              goto LABEL_124;
            }
            goto LABEL_134;
          }
        }
        v54 = *(const WCHAR **)(v45 + 24 * i + 8);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v100) = 0;
          LOWORD(v96) = 0;
          v58 = this[70];
          if ( v58 && (v59 = v58[14]) != 0 && *(_QWORD *)(v59 + 16) )
            v60 = *(unsigned int *)(v59 + 16);
          else
            v60 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v96, v60);
          FormatRRASErrorString(
            &v100,
            L"Sending the DNS from cert subject-alt-name as IDi: %s.",
            *(_QWORD *)(v29[1] + 8 * v44 + 8));
LABEL_124:
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v61 = (char *)this[70];
            v62 = v61 + 112;
            if ( v61 )
            {
              if ( *v62 )
                v63 = *v62 + 2686LL;
              else
                v63 = 0;
              if ( *v62 )
              {
                v64 = (__int128 *)(*v62 + 2120LL);
LABEL_133:
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasVpnIkeParamTraceInfo,
                  (unsigned int)&v100,
                  (_DWORD)v64,
                  v63,
                  (__int64)&v96);
                goto LABEL_134;
              }
            }
            else
            {
              v63 = 0;
            }
            v64 = &v95;
            goto LABEL_133;
          }
        }
LABEL_134:
        if ( !v54 )
          goto LABEL_160;
        v65 = StringCopyWtoAAlloc(v54);
        IDObject = v65;
        if ( !v65 )
        {
          v7 = lpMem;
          v73 = -1;
          do
            ++v73;
          while ( *((_BYTE *)lpMem + v73) );
          LOBYTE(v66) = 2;
          IDObject = CreateIDObject(v66, v73, lpMem, a3);
          goto LABEL_160;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v65);
        }
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_155;
        LOWORD(v100) = 0;
        LOWORD(v96) = 0;
        v67 = this[70];
        if ( v67 )
        {
          v68 = v67[14];
          if ( v68 )
          {
            if ( *(_QWORD *)(v68 + 16) )
              v8 = *(_DWORD *)(v68 + 16);
          }
        }
        ConvertPortNoToString(&v96, v8);
        FormatRRASErrorString(&v100, L"StringCopyWtoAAlloc failed: %d", IDObject);
        if ( (byte_1800AA941 & 4) == 0 )
        {
LABEL_155:
          v7 = lpMem;
          if ( IDObject != 8 )
            IDObject = 0;
          goto LABEL_160;
        }
        v69 = (char *)this[70];
        v70 = v69 + 112;
        if ( v69 )
        {
          if ( *v70 )
            v71 = *v70 + 2686LL;
          else
            v71 = 0;
          if ( *v70 )
          {
            v72 = (__int128 *)(*v70 + 2120LL);
LABEL_154:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v100,
              (_DWORD)v72,
              v71,
              (__int64)&v96);
            goto LABEL_155;
          }
        }
        else
        {
          v71 = 0;
        }
        v72 = &v95;
        goto LABEL_154;
      }
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_167:
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_183;
        LOWORD(v100) = 0;
        LOWORD(v96) = 0;
        v76 = this[70];
        if ( v76 )
        {
          v77 = v76[14];
          if ( v77 )
          {
            if ( *(_QWORD *)(v77 + 16) )
              v8 = *(_DWORD *)(v77 + 16);
          }
        }
        ConvertPortNoToString(&v96, v8);
        v78 = GetLastError();
        FormatRRASErrorString(&v100, L"CryptDecodeObject Failed: 0x%x.", v78);
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_182;
        v79 = (char *)this[70];
        v80 = v79 + 112;
        if ( v79 )
        {
          if ( *v80 )
            v81 = *v80 + 2686LL;
          else
            v81 = 0;
          if ( *v80 )
          {
            v82 = (__int128 *)(*v80 + 2120LL);
LABEL_181:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v100,
              (_DWORD)v82,
              v81,
              (__int64)&v96);
            goto LABEL_182;
          }
        }
        else
        {
          v81 = 0;
        }
        v82 = &v95;
        goto LABEL_181;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v25);
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_167;
  }
  if ( (v9 & 4) == 0 )
    goto LABEL_24;
  LOWORD(v96) = 0;
  v10 = this[70];
  if ( v10 )
  {
    v11 = v10[14];
    if ( v11 )
    {
      if ( *(_QWORD *)(v11 + 16) )
        v8 = *(_DWORD *)(v11 + 16);
    }
  }
  ConvertPortNoToString(&v96, v8);
  if ( (byte_1800AA941 & 4) != 0 )
  {
    v12 = (char *)this[70];
    v13 = v12 + 112;
    if ( v12 )
    {
      if ( *v13 )
        v14 = *v13 + 2686LL;
      else
        v14 = 0;
      if ( *v13 )
      {
        v15 = (__int128 *)(*v13 + 2120LL);
LABEL_22:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Invalid Parameter",
          (_DWORD)v15,
          v14,
          (__int64)&v96);
        goto LABEL_23;
      }
    }
    else
    {
      v14 = 0;
    }
    v15 = &v95;
    goto LABEL_22;
  }
LABEL_23:
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
  v16 = 87;
  IDObject = 87;
  if ( v6 == &WPP_GLOBAL_Control )
    goto LABEL_187;
  if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
  {
    v17 = 68;
LABEL_28:
    WPP_SF_d(v6[2], v17, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, v16);
LABEL_182:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_183:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 74, &WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids, IDObject);
LABEL_187:
  v83 = IDObject;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v89);
  return v83;
}

```

## disassembly

```asm
0x180042ad8  mov     [rsp-8+arg_18], rbx
0x180042add  push    rbp
0x180042ade  push    rsi
0x180042adf  push    rdi
0x180042ae0  push    r12
0x180042ae2  push    r13
0x180042ae4  push    r14
0x180042ae6  push    r15
0x180042ae8  lea     rbp, [rsp-7E0h]
0x180042af0  sub     rsp, 8E0h
0x180042af7  mov     rax, cs:__security_cookie
0x180042afe  xor     rax, rsp
0x180042b01  mov     [rbp+810h+var_40], rax
0x180042b08  mov     r12, r8
0x180042b0b  mov     r14, rdx
0x180042b0e  mov     rdi, rcx
0x180042b11  lea     rax, WPP_GLOBAL_Control
0x180042b18  mov     rbx, cs:WPP_GLOBAL_Control
0x180042b1f  cmp     rbx, rax
0x180042b22  jz      short loc_180042B4C
0x180042b24  test    byte ptr [rbx+1Ch], 1
0x180042b28  jz      short loc_180042B4C
0x180042b2a  cmp     byte ptr [rbx+19h], 6
0x180042b2e  jb      short loc_180042B4C
0x180042b30  mov     edx, 43h ; 'C'
0x180042b35  lea     r8, WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids
0x180042b3c  mov     rcx, [rbx+10h]
0x180042b40  call    WPP_SF_
0x180042b45  mov     rbx, cs:WPP_GLOBAL_Control
0x180042b4c  xor     r13d, r13d
0x180042b4f  mov     [rsp+910h+var_8D0], r13d
0x180042b54  mov     [rsp+910h+var_8CC], r13d
0x180042b59  mov     [rsp+910h+var_8C0], r13d
0x180042b5e  mov     r15d, r13d
0x180042b61  mov     [rsp+910h+lpMem], r13
0x180042b66  mov     [rbp+810h+var_840], r13d
0x180042b6a  xor     edx, edx; Val
0x180042b6c  mov     r8d, 7FCh; Size
0x180042b72  lea     rcx, [rbp+810h+var_83C]; void *
0x180042b76  call    memset_0
0x180042b7b  mov     [rbp+810h+var_870], r13d
0x180042b7f  xorps   xmm0, xmm0
0x180042b82  xor     eax, eax
0x180042b84  movups  [rbp+810h+var_86C], xmm0
0x180042b88  movups  [rbp+810h+var_85C], xmm0
0x180042b8c  mov     [rbp+810h+var_84C], eax
0x180042b8f  movups  [rbp+810h+var_880], xmm0
0x180042b93  xorps   xmm1, xmm1
0x180042b96  movdqu  [rsp+910h+var_8B0], xmm1
0x180042b9c  mov     [rsp+910h+var_8B8], r13
0x180042ba1  movdqu  [rsp+910h+var_8A0], xmm0
0x180042ba7  mov     [rbp+810h+var_890], r13
0x180042bab  or      esi, 0FFFFFFFFh
0x180042bae  mov     [rbp+810h+var_888], esi
0x180042bb1  mov     [rbp+810h+var_884], r13d
0x180042bb5  mov     al, cs:byte_1800AA941
0x180042bbb  test    al, 8
0x180042bbd  jz      short loc_180042BF5
0x180042bbf  mov     rax, [rdi+230h]
0x180042bc6  mov     qword ptr [rsp+910h+dwFlags], rax; void *
0x180042bcb  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180042bd2  lea     r8, [rsp+910h+var_8D0]; unsigned int *
0x180042bd7  lea     rdx, aClienteapauthh_12; "ClientEAPAuthHandler::GetIDFromCert"
0x180042bde  lea     rcx, [rsp+910h+var_8B8]; this
0x180042be3  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180042be8  mov     rbx, cs:WPP_GLOBAL_Control
0x180042bef  mov     al, cs:byte_1800AA941
0x180042bf5  test    r12, r12
0x180042bf8  jnz     loc_180042CF5
0x180042bfe  test    al, 4
0x180042c00  jz      loc_180042CAD
0x180042c06  mov     word ptr [rbp+810h+var_870], r13w
0x180042c0b  mov     rax, [rdi+230h]
0x180042c12  test    rax, rax
0x180042c15  jz      short loc_180042C29
0x180042c17  mov     rax, [rax+70h]
0x180042c1b  test    rax, rax
0x180042c1e  jz      short loc_180042C29
0x180042c20  cmp     [rax+10h], r13
0x180042c24  jz      short loc_180042C29
0x180042c26  mov     esi, [rax+10h]
0x180042c29  mov     edx, esi
0x180042c2b  lea     rcx, [rbp+810h+var_870]
0x180042c2f  call    ConvertPortNoToString
0x180042c34  test    cs:byte_1800AA941, 4
0x180042c3b  jz      short loc_180042CA6
0x180042c3d  mov     rcx, [rdi+230h]
0x180042c44  lea     rax, [rcx+70h]
0x180042c48  test    rcx, rcx
0x180042c4b  jz      short loc_180042C77
0x180042c4d  mov     rdx, [rax]
0x180042c50  test    rdx, rdx
0x180042c53  jz      short loc_180042C5E
0x180042c55  lea     rcx, [rdx+0A7Eh]
0x180042c5c  jmp     short loc_180042C66
0x180042c5e  test    rcx, rcx
0x180042c61  jz      short loc_180042C77
0x180042c63  mov     rcx, r13
0x180042c66  mov     rdx, [rax]
0x180042c69  test    rdx, rdx
0x180042c6c  jz      short loc_180042C7A
0x180042c6e  lea     r9, [rdx+848h]
0x180042c75  jmp     short loc_180042C7E
0x180042c77  mov     rcx, r13
0x180042c7a  lea     r9, [rbp+810h+var_880]
0x180042c7e  lea     rax, [rbp+810h+var_870]
0x180042c82  mov     [rsp+910h+pvStructInfo], rax
0x180042c87  mov     qword ptr [rsp+910h+dwFlags], rcx
0x180042c8c  lea     r8, aInvalidParamet_0; "Invalid Parameter"
0x180042c93  lea     rdx, RasVpnIkeParamTraceError
0x180042c9a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180042ca1  call    McTemplateU0zjzz_EventWriteTransfer
0x180042ca6  mov     rbx, cs:WPP_GLOBAL_Control
0x180042cad  mov     r9d, 57h ; 'W'
0x180042cb3  mov     [rsp+910h+var_8D0], r9d
0x180042cb8  lea     r14, WPP_GLOBAL_Control
0x180042cbf  cmp     rbx, r14
0x180042cc2  jz      loc_180043590
0x180042cc8  test    byte ptr [rbx+1Ch], 1
0x180042ccc  jz      loc_180043565
0x180042cd2  cmp     byte ptr [rbx+19h], 2
0x180042cd6  jb      loc_180043565
0x180042cdc  lea     edx, [r9-13h]
0x180042ce0  lea     r8, WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids
0x180042ce7  mov     rcx, [rbx+10h]
0x180042ceb  call    WPP_SF_d
0x180042cf0  jmp     loc_18004355E
0x180042cf5  mov     rdx, [r14+18h]
0x180042cf9  mov     r8, [rdx+0C8h]; rgExtensions
0x180042d00  mov     edx, [rdx+0C0h]; cExtensions
0x180042d06  lea     rcx, szStructType; "2.5.29.17"
0x180042d0d  call    cs:__imp_CertFindExtension
0x180042d13  mov     r14, rax
0x180042d16  test    rax, rax
0x180042d19  jnz     loc_180042E11
0x180042d1f  test    cs:byte_1800AA941, 4
0x180042d26  jz      loc_180042DCC
0x180042d2c  mov     word ptr [rbp+810h+var_870], r13w
0x180042d31  mov     rax, [rdi+230h]
0x180042d38  test    rax, rax
0x180042d3b  jz      short loc_180042D4F
0x180042d3d  mov     rax, [rax+70h]
0x180042d41  test    rax, rax
0x180042d44  jz      short loc_180042D4F
0x180042d46  cmp     [rax+10h], r13
0x180042d4a  jz      short loc_180042D4F
0x180042d4c  mov     esi, [rax+10h]
0x180042d4f  mov     edx, esi
0x180042d51  lea     rcx, [rbp+810h+var_870]
0x180042d55  call    ConvertPortNoToString
0x180042d5a  test    cs:byte_1800AA941, 4
0x180042d61  jz      short loc_180042DCC
0x180042d63  mov     rcx, [rdi+230h]
0x180042d6a  lea     rax, [rcx+70h]
0x180042d6e  test    rcx, rcx
0x180042d71  jz      short loc_180042D9D
0x180042d73  mov     rdx, [rax]
0x180042d76  test    rdx, rdx
0x180042d79  jz      short loc_180042D84
0x180042d7b  lea     rcx, [rdx+0A7Eh]
0x180042d82  jmp     short loc_180042D8C
0x180042d84  test    rcx, rcx
0x180042d87  jz      short loc_180042D9D
0x180042d89  mov     rcx, r13
0x180042d8c  mov     rdx, [rax]
0x180042d8f  test    rdx, rdx
0x180042d92  jz      short loc_180042DA0
0x180042d94  lea     r9, [rdx+848h]
0x180042d9b  jmp     short loc_180042DA4
0x180042d9d  mov     rcx, r13
0x180042da0  lea     r9, [rbp+810h+var_880]
0x180042da4  lea     rax, [rbp+810h+var_870]
0x180042da8  mov     [rsp+910h+pvStructInfo], rax
0x180042dad  mov     qword ptr [rsp+910h+dwFlags], rcx
0x180042db2  lea     r8, aNoSubjectAltNa; "No subject-alt-name extention found in "...
0x180042db9  lea     rdx, RasVpnIkeParamTraceError
0x180042dc0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180042dc7  call    McTemplateU0zjzz_EventWriteTransfer
0x180042dcc  mov     rbx, cs:WPP_GLOBAL_Control
0x180042dd3  lea     r14, WPP_GLOBAL_Control
0x180042dda  cmp     rbx, r14
0x180042ddd  jz      loc_180043590
0x180042de3  test    byte ptr [rbx+1Ch], 1
0x180042de7  jz      loc_180043565
0x180042ded  cmp     byte ptr [rbx+19h], 2
0x180042df1  jb      loc_180043565
0x180042df7  mov     edx, 45h ; 'E'
0x180042dfc  lea     r8, WPP_9b1d92632a283ee141f1a9f16fafbea4_Traceguids
0x180042e03  mov     rcx, [rbx+10h]
0x180042e07  call    WPP_SF_
0x180042e0c  jmp     loc_18004355E
0x180042e11  mov     [rsp+910h+var_8CC], r13d
0x180042e16  lea     rax, [rsp+910h+var_8CC]
0x180042e1b  mov     [rsp+910h+pcbStructInfo], rax; pcbStructInfo
0x180042e20  mov     [rsp+910h+pvStructInfo], r13; pvStructInfo
0x180042e25  mov     [rsp+910h+dwFlags], 1; dwFlags
0x180042e2d  mov     r9d, [r14+10h]; cbEncoded
0x180042e31  mov     r8, [r14+18h]; pbEncoded
0x180042e35  lea     rdx, szStructType; "2.5.29.17"
0x180042e3c  mov     ecx, 10001h; dwCertEncodingType
0x180042e41  call    cs:__imp_CryptDecodeObject
0x180042e47  test    eax, eax
0x180042e49  jz      loc_180043488
0x180042e4f  mov     ecx, [rsp+910h+var_8CC]
0x180042e53  test    ecx, ecx
0x180042e55  jz      loc_18004344F
0x180042e5b  mov     ebx, ecx
0x180042e5d  call    cs:__imp_GetProcessHeap
0x180042e63  mov     r8d, ebx; dwBytes
0x180042e66  mov     ebx, 8
0x180042e6b  mov     edx, ebx; dwFlags
0x180042e6d  mov     rcx, rax; hHeap
0x180042e70  call    cs:__imp_HeapAlloc
0x180042e76  mov     r13, rax
0x180042e79  test    rax, rax
0x180042e7c  jnz     loc_180042F7D
0x180042e82  mov     [rsp+910h+var_8D0], ebx
0x180042e86  test    cs:byte_1800AA941, 4
0x180042e8d  jz      loc_180042F43
0x180042e93  mov     word ptr [rbp+810h+var_870], ax
0x180042e97  mov     rax, [rdi+230h]
0x180042e9e  test    rax, rax
0x180042ea1  jz      short loc_180042EB5
0x180042ea3  mov     rax, [rax+70h]
0x180042ea7  test    rax, rax
0x180042eaa  jz      short loc_180042EB5
0x180042eac  cmp     [rax+10h], r13
0x180042eb0  jz      short loc_180042EB5
0x180042eb2  mov     esi, [rax+10h]
0x180042eb5  mov     edx, esi
0x180042eb7  lea     rcx, [rbp+810h+var_870]
0x180042ebb  call    ConvertPortNoToString
0x180042ec0  test    cs:byte_1800AA941, 4
0x180042ec7  jz      short loc_180042F30
0x180042ec9  mov     rcx, [rdi+230h]
0x180042ed0  lea     rax, [rcx+70h]
0x180042ed4  test    rcx, rcx
0x180042ed7  jz      short loc_180042F02
0x180042ed9  mov     rdx, [rax]
0x180042edc  test    rdx, rdx
0x180042edf  jz      short loc_180042EEA
0x180042ee1  lea     rcx, [rdx+0A7Eh]
0x180042ee8  jmp     short loc_180042EF1
0x180042eea  test    rcx, rcx
0x180042eed  jz      short loc_180042F02
0x180042eef  xor     ecx, ecx
0x180042ef1  mov     rdx, [rax]
0x180042ef4  test    rdx, rdx
0x180042ef7  jz      short loc_180042F04
0x180042ef9  lea     r9, [rdx+848h]
0x180042f00  jmp     short loc_180042F08
0x180042f02  xor     ecx, ecx
0x180042f04  lea     r9, [rbp+810h+var_880]
0x180042f08  lea     rax, [rbp+810h+var_870]
0x180042f0c  mov     [rsp+910h+pvStructInfo], rax
0x180042f11  mov     qword ptr [rsp+910h+dwFlags], rcx
0x180042f16  lea     r8, aMemoryAllocati_0; "Memory allocation failed"
0x180042f1d  lea     rdx, RasVpnIkeParamTraceError
0x180042f24  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180042f2b  call    McTemplateU0zjzz_EventWriteTransfer
0x180042f30  cmp     [rsp+910h+var_8D0], 0
0x180042f35  jnz     short loc_180042F43
0x180042f37  lea     r14, WPP_GLOBAL_Control
0x180042f3e  jmp     loc_18004355E
0x180042f43  mov     rbx, cs:WPP_GLOBAL_Control
0x180042f4a  lea     r14, WPP_GLOBAL_Control
0x180042f51  cmp     rbx, r14
0x180042f54  jz      loc_180043590
0x180042f5a  test    byte ptr [rbx+1Ch], 1
0x180042f5e  jz      loc_180043565
0x180042f64  cmp     byte ptr [rbx+19h], 2
0x180042f68  jb      loc_180043565
0x180042f6e  mov     edx, 47h ; 'G'
0x180042f73  mov     r9d, [rsp+910h+var_8D0]
0x180042f78  jmp     loc_180042CE0
0x180042f7d  lea     rax, [rsp+910h+var_8CC]
0x180042f82  mov     [rsp+910h+pcbStructInfo], rax; pcbStructInfo
0x180042f87  mov     [rsp+910h+pvStructInfo], r13; pvStructInfo
0x180042f8c  mov     [rsp+910h+dwFlags], 1; dwFlags
0x180042f94  mov     r9d, [r14+10h]; cbEncoded
0x180042f98  mov     r8, [r14+18h]; pbEncoded
0x180042f9c  lea     rdx, szStructType; "2.5.29.17"
0x180042fa3  mov     ecx, 10001h; dwCertEncodingType
0x180042fa8  call    cs:__imp_CryptDecodeObject
0x180042fae  test    eax, eax
0x180042fb0  jnz     loc_180043084
0x180042fb6  test    cs:byte_1800AA941, 4
0x180042fbd  jz      loc_180043412
0x180042fc3  mov     word ptr [rbp+810h+var_840], ax
0x180042fc7  mov     word ptr [rbp+810h+var_870], ax
0x180042fcb  mov     rax, [rdi+230h]
0x180042fd2  test    rax, rax
0x180042fd5  jz      short loc_180042FEA
0x180042fd7  mov     rax, [rax+70h]
0x180042fdb  test    rax, rax
0x180042fde  jz      short loc_180042FEA
0x180042fe0  cmp     qword ptr [rax+10h], 0
0x180042fe5  jz      short loc_180042FEA
0x180042fe7  mov     esi, [rax+10h]
0x180042fea  mov     edx, esi
  ... truncated ...
```
