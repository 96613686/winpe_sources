# WEBHOST_PROTOCOL_MANAGER::RunCustomAction(ushort const *,ushort const *,ICustomActionResultCallback *)

- ea: `0x180002670`
- end: `0x180002eb9`
- name: `?RunCustomAction@WEBHOST_PROTOCOL_MANAGER@@UEAAJPEBG0PEAVICustomActionResultCallback@@@Z`
- size: `2121`
- prototype: `__int64 __fastcall(WEBHOST_PROTOCOL_MANAGER *this, const unsigned __int16 *, const unsigned __int16 *, struct ICustomActionResultCallback *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002670`
- `0x180004836`
- `0x180004842`
- `0x18000484e`
- `0x180004880`
- `0x180005010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800028d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800028e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800028f1`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c90`
- `OLEAUT32!__imp_SysFreeString` at `0x180002ca3`
- `OLEAUT32!__imp_SysFreeString` at `0x180002cb3`
- `OLEAUT32!__imp_SysFreeString` at `0x180002e63`
- `OLEAUT32!__imp_SysFreeString` at `0x180002e73`
- `OLEAUT32!__imp_SysFreeString` at `0x180002e83`
- `OLEAUT32!__imp_SysFreeString` at `0x1800028d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800028e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800028f1`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c90`
- `OLEAUT32!__imp_SysFreeString` at `0x180002ca3`
- `OLEAUT32!__imp_SysFreeString` at `0x180002cb3`
- `OLEAUT32!__imp_SysFreeString` at `0x180002e63`
- `OLEAUT32!__imp_SysFreeString` at `0x180002e73`
- `OLEAUT32!__imp_SysFreeString` at `0x180002e83`
- `OLEAUT32!__imp_SysStringLen` at `0x180002bb8`
- `OLEAUT32!__imp_SysStringLen` at `0x180002c03`
- `OLEAUT32!__imp_SysStringLen` at `0x180002c4e`
- `OLEAUT32!__imp_SysStringLen` at `0x180002bb8`
- `OLEAUT32!__imp_SysStringLen` at `0x180002c03`
- `OLEAUT32!__imp_SysStringLen` at `0x180002c4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029a6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002e8e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002e8e`
- `iisutil!PuDbgPrint` at `0x180002743`
- `iisutil!PuDbgPrint` at `0x180002743`
- `iisutil!PuDbgPrintError` at `0x1800027ab`
- `iisutil!PuDbgPrintError` at `0x1800027ab`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002998`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002998`

## string_xrefs

- `0x180002709`: `servercommon\inetsrv\iis\iisrearc\core\webhost_pm\webhost_protocol_manager.cxx`
- `0x180002a6e`: `servercommon\inetsrv\iis\iisrearc\core\webhost_pm\webhost_protocol_manager.cxx`
- `0x1800026fe`: `WEBHOST_PROTOCOL_MANAGER::RunCustomAction`
- `0x180002989`: `WEBHOST_PROTOCOL_MANAGER::RunCustomAction`
- `0x180002a67`: `WEBHOST_PROTOCOL_MANAGER::RunCustomAction`
- `0x180002a22`: `Error retrieving the virtual path\n`
- `0x180002da5`: `Error retrieving the virtual path\n`
- `0x180002a06`: `Error retrieving the physical path\n`
- `0x180002d86`: `Error retrieving the physical path\n`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::RunCustomAction(
        WEBHOST_PROTOCOL_MANAGER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct ICustomActionResultCallback *a4)
{
  struct ICustomActionResultCallback *v7; // r12
  signed int v8; // ebx
  const char *v9; // rax
  __int64 v10; // r8
  unsigned int v11; // r15d
  __int64 v12; // rdi
  __int64 v13; // r14
  __int64 v14; // rsi
  int v15; // eax
  int v16; // ecx
  signed int LastError; // eax
  char *v18; // r15
  char *v19; // r15
  size_t v20; // rdi
  char *v21; // r12
  size_t v22; // r14
  size_t v23; // rdi
  char *v24; // r13
  size_t v25; // r15
  size_t v26; // rdi
  char *v27; // r14
  size_t v28; // rsi
  __int64 v29; // r9
  __int64 v30; // rdx
  char *v31; // r8
  unsigned int v32; // eax
  int v34; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+40h] [rbp-C0h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v38; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch] BYREF
  int v42; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v43; // [rsp+6Ch] [rbp-94h]
  struct ICustomActionResultCallback *v44; // [rsp+70h] [rbp-90h]
  _BYTE v45[32]; // [rsp+78h] [rbp-88h] BYREF
  char *v46; // [rsp+98h] [rbp-68h]
  int v47; // [rsp+A0h] [rbp-60h]
  __int16 v48; // [rsp+A4h] [rbp-5Ch]
  char v49; // [rsp+B0h] [rbp-50h] BYREF
  char v50[255]; // [rsp+B1h] [rbp-4Fh] BYREF

  v44 = a4;
  v36 = 0;
  v35 = 0;
  v40 = 0;
  bstrString = 0;
  pbstr = 0;
  v38 = 0;
  v41 = 0;
  v7 = a4;
  v42 = 0;
  v34 = 0;
  memset_0(v50, 0, sizeof(v50));
  v46 = &v49;
  v49 = 0;
  v47 = 256;
  v48 = 256;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\webhost_pm\\webhost_protocol_manager.cxx",
      961,
      "WEBHOST_PROTOCOL_MANAGER::RunCustomAction",
      "Calling PMH method %S \n");
  if ( wcscmp_0(a2, L"PMH_App_Domain_Enum_V1") )
  {
    if ( wcscmp_0(a2, L"PMH_App_Domain_Unload_V1") )
    {
      v8 = -2147467263;
      goto LABEL_72;
    }
    v32 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**((_QWORD **)this + 8) + 32LL))(
            *((_QWORD *)this + 8),
            a3);
    v29 = 0;
    v8 = v32;
    v31 = 0;
    v30 = v32;
    goto LABEL_70;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 8) + 48LL))(*((_QWORD *)this + 8), &v36);
  if ( v8 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_72;
    v9 = "Failed to get app domain info enum\n";
    v10 = 974;
    goto LABEL_7;
  }
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 32LL))(v36, &v40);
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 40LL))(v36, &v34);
  if ( v8 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v9 = "Error moving the enum forward.\n";
      v10 = 1009;
LABEL_7:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\webhost_pm\\webhost_protocol_manager.cxx",
        v10,
        "WEBHOST_PROTOCOL_MANAGER::RunCustomAction",
        v8,
        v9);
      goto LABEL_72;
    }
    goto LABEL_72;
  }
  v11 = 4;
  v43 = 4;
  if ( v34 )
  {
    v12 = -1;
    while ( 1 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 24LL))(v36, &v35);
      if ( v8 < 0 )
        break;
      v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 24LL))(v35, &bstrString);
      if ( v8 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_72;
        v9 = "Error retrieving the app domain id!\n";
        v10 = 1039;
        goto LABEL_7;
      }
      v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 32LL))(v35, &pbstr);
      if ( v8 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_72;
        v9 = "Error retrieving the virtual path\n";
        v10 = 1050;
        goto LABEL_7;
      }
      v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 40LL))(v35, &v38);
      if ( v8 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_72;
        v9 = "Error retrieving the physical path\n";
        v10 = 1061;
        goto LABEL_7;
      }
      v13 = -1;
      do
        ++v13;
      while ( bstrString[v13] );
      v14 = -1;
      do
        ++v14;
      while ( pbstr[v14] );
      do
        ++v12;
      while ( v38[v12] );
      SysFreeString(bstrString);
      bstrString = 0;
      SysFreeString(pbstr);
      pbstr = 0;
      SysFreeString(v38);
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v35 = 0;
      v34 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 40LL))(v36, &v34);
      if ( v8 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_72;
        v9 = "Error moving the enum forward.\n";
        v10 = 1087;
        goto LABEL_7;
      }
      v15 = 2 * v12 + 6;
      v16 = (2 * (_BYTE)v12 + 6) & 3;
      v12 = -1;
      v11 += 2 * v13 + 6 + 2 * v14 + 6 + v16 + v15 + ((2 * (_BYTE)v14 + 6) & 3) + ((2 * (_BYTE)v13 + 6) & 3) + 8;
      v43 = v11;
      if ( !v34 )
        goto LABEL_24;
    }
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_72;
    v10 = 1023;
    goto LABEL_39;
  }
LABEL_24:
  if ( BUFFER::Resize((BUFFER *)v45, v11) )
  {
    v18 = v46;
    *(_DWORD *)v46 = v40;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 48LL))(v36);
    v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 40LL))(v36, &v34);
    if ( v8 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v9 = "Error moving the enum forward.\n";
        v10 = 1117;
        goto LABEL_7;
      }
      goto LABEL_72;
    }
    v19 = v18 + 4;
    if ( v34 )
    {
      while ( 1 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 24LL))(v36, &v35);
        if ( v8 < 0 )
          break;
        v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 24LL))(v35, &bstrString);
        if ( v8 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_72;
          v9 = "Error retrieving the app domain id!\n";
          v10 = 1141;
          goto LABEL_7;
        }
        v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 32LL))(v35, &pbstr);
        if ( v8 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_72;
          v9 = "Error retrieving the virtual path\n";
          v10 = 1152;
          goto LABEL_7;
        }
        v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 40LL))(v35, &v38);
        if ( v8 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_72;
          v9 = "Error retrieving the physical path\n";
          v10 = 1163;
          goto LABEL_7;
        }
        v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 48LL))(v35, &v41);
        if ( v8 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_72;
          v9 = "Error retrieving the site id!\n";
          v10 = 1174;
          goto LABEL_7;
        }
        v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 56LL))(v35, &v42);
        if ( v8 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_72;
          v9 = "Error retrieving the idle flag\n";
          v10 = 1185;
          goto LABEL_7;
        }
        *(_DWORD *)v19 = v41;
        *((_DWORD *)v19 + 1) = v42;
        v20 = 2 * SysStringLen(bstrString);
        memcpy_0(v19 + 12, bstrString, v20);
        v21 = &v19[v20 + 12];
        LODWORD(v20) = v20 + 2;
        v22 = v20 & 3;
        memset_0(v21, 0, v22 + 2);
        *((_DWORD *)v19 + 2) = v22 + v20;
        v23 = 2 * SysStringLen(pbstr);
        memcpy_0(&v21[v22 + 6], pbstr, v23);
        v24 = &v21[v22 + 6 + v23];
        LODWORD(v23) = v23 + 2;
        v25 = v23 & 3;
        memset_0(v24, 0, v25 + 2);
        *(_DWORD *)&v21[v22 + 2] = v25 + v23;
        v26 = 2 * SysStringLen(v38);
        memcpy_0(&v24[v25 + 6], v38, v26);
        v27 = &v24[v25 + 6 + v26];
        LODWORD(v26) = v26 + 2;
        v28 = v26 & 3;
        memset_0(v27, 0, v28 + 2);
        *(_DWORD *)&v24[v25 + 2] = v28 + v26;
        SysFreeString(bstrString);
        bstrString = 0;
        SysFreeString(pbstr);
        pbstr = 0;
        SysFreeString(v38);
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        v35 = 0;
        v34 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 40LL))(v36, &v34);
        if ( v8 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_72;
          v9 = "Error moving the enum forward.\n";
          v10 = 1213;
          goto LABEL_7;
        }
        v19 = &v27[v28 + 2];
        if ( !v34 )
        {
          v7 = v44;
          goto LABEL_53;
        }
      }
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_72;
      v10 = 1130;
LABEL_39:
      v9 = "Error retrieving the app domain info object.\n";
      goto LABEL_7;
    }
LABEL_53:
    v29 = v43;
    v30 = 0;
    v31 = v46;
LABEL_70:
    (*(void (__fastcall **)(struct ICustomActionResultCallback *, __int64, char *, __int64))(*(_QWORD *)v7 + 16LL))(
      v7,
      v30,
      v31,
      v29);
    goto LABEL_72;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v9 = "Failed resizing the buffer to send data\n";
    v10 = 1100;
    goto LABEL_7;
  }
LABEL_72:
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( pbstr )
    SysFreeString(pbstr);
  if ( v38 )
    SysFreeString(v38);
  BUFFER::~BUFFER((BUFFER *)v45);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002670  push    rbp
0x180002672  push    rbx
0x180002673  push    rsi
0x180002674  push    rdi
0x180002675  push    r12
0x180002677  push    r13
0x180002679  push    r14
0x18000267b  push    r15
0x18000267d  lea     rbp, [rsp-0C8h]
0x180002685  sub     rsp, 1C8h
0x18000268c  mov     rax, cs:__security_cookie
0x180002693  xor     rax, rsp
0x180002696  mov     [rbp+100h+var_50], rax
0x18000269d  xor     r13d, r13d
0x1800026a0  mov     [rsp+200h+var_190], r9
0x1800026a5  mov     rsi, r8
0x1800026a8  mov     [rsp+200h+var_1C0], r13
0x1800026ad  mov     rbx, rdx
0x1800026b0  mov     [rsp+200h+var_1C8], r13
0x1800026b5  mov     rdi, rcx
0x1800026b8  mov     [rsp+200h+var_1A0], r13d
0x1800026bd  xor     edx, edx; Val
0x1800026bf  mov     [rsp+200h+bstrString], r13
0x1800026c4  mov     r8d, 0FFh; Size
0x1800026ca  mov     [rsp+200h+pbstr], r13
0x1800026cf  lea     rcx, [rbp+100h+var_14F]; void *
0x1800026d3  mov     [rsp+200h+var_1B0], r13
0x1800026d8  mov     [rsp+200h+var_19C], r13d
0x1800026dd  mov     r12, r9
0x1800026e0  mov     [rsp+200h+var_198], r13d
0x1800026e5  mov     [rsp+200h+var_1D0], r13d
0x1800026ea  call    memset_0
0x1800026ef  test    cs:g_dwDebugFlags, 3
0x1800026f6  lea     rax, [rbp+100h+var_150]
0x1800026fa  mov     [rbp+100h+var_168], rax
0x1800026fe  lea     r14, aWebhostProtoco_2; "WEBHOST_PROTOCOL_MANAGER::RunCustomActi"...
0x180002705  mov     [rbp+100h+var_150], r13b
0x180002709  lea     r15, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180002710  mov     [rbp+100h+var_160], 100h
0x180002717  mov     [rbp+100h+var_15C], 100h
0x18000271d  jz      short loc_180002749
0x18000271f  mov     rcx, cs:g_pDebug
0x180002726  lea     rax, aCallingPmhMeth; "Calling PMH method %S \n"
0x18000272d  mov     [rsp+200h+var_1D8], rbx
0x180002732  mov     r9, r14
0x180002735  mov     r8d, 3C1h
0x18000273b  mov     [rsp+200h+var_1E0], rax
0x180002740  mov     rdx, r15
0x180002743  call    cs:__imp_PuDbgPrint
0x180002749  lea     rdx, aPmhAppDomainEn; "PMH_App_Domain_Enum_V1"
0x180002750  mov     rcx, rbx; String1
0x180002753  call    wcscmp_0
0x180002758  test    eax, eax
0x18000275a  jnz     loc_180002DE6
0x180002760  mov     rcx, [rdi+40h]
0x180002764  lea     rdx, [rsp+200h+var_1C0]
0x180002769  mov     rax, [rcx]
0x18000276c  mov     rax, [rax+30h]
0x180002770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002775  mov     ebx, eax
0x180002777  test    eax, eax
0x180002779  jns     short loc_1800027B6
0x18000277b  test    cs:g_dwDebugFlags, 0Fh
0x180002782  jz      loc_180002E2D
0x180002788  lea     rax, aFailedToGetApp; "Failed to get app domain info enum\n"
0x18000278f  mov     r8d, 3CEh
0x180002795  mov     r9, r14
0x180002798  mov     rdx, r15
0x18000279b  mov     rcx, cs:g_pDebug
0x1800027a2  mov     [rsp+200h+var_1D8], rax
0x1800027a7  mov     dword ptr [rsp+200h+var_1E0], ebx
0x1800027ab  call    cs:__imp_PuDbgPrintError
0x1800027b1  jmp     loc_180002E2D
0x1800027b6  mov     rcx, [rsp+200h+var_1C0]
0x1800027bb  lea     rdx, [rsp+200h+var_1A0]
0x1800027c0  mov     rax, [rcx]
0x1800027c3  mov     rax, [rax+20h]
0x1800027c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027cc  mov     rcx, [rsp+200h+var_1C0]
0x1800027d1  lea     rdx, [rsp+200h+var_1D0]
0x1800027d6  mov     rax, [rcx]
0x1800027d9  mov     rax, [rax+28h]
0x1800027dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027e2  mov     ebx, eax
0x1800027e4  test    eax, eax
0x1800027e6  jns     short loc_180002804
0x1800027e8  test    cs:g_dwDebugFlags, 0Fh
0x1800027ef  jz      loc_180002E2D
0x1800027f5  lea     rax, aErrorMovingThe; "Error moving the enum forward.\n"
0x1800027fc  mov     r8d, 3F1h
0x180002802  jmp     short loc_180002795
0x180002804  mov     r15d, 4
0x18000280a  mov     [rsp+200h+var_194], r15d
0x18000280f  cmp     [rsp+200h+var_1D0], r13d
0x180002814  jz      loc_180002990
0x18000281a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000281e  mov     rcx, [rsp+200h+var_1C0]
0x180002823  lea     rdx, [rsp+200h+var_1C8]
0x180002828  mov     rax, [rcx]
0x18000282b  mov     rax, [rax+18h]
0x18000282f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002834  mov     ebx, eax
0x180002836  test    eax, eax
0x180002838  js      loc_180002A4D
0x18000283e  mov     rcx, [rsp+200h+var_1C8]
0x180002843  lea     rdx, [rsp+200h+bstrString]
0x180002848  mov     rax, [rcx]
0x18000284b  mov     rax, [rax+18h]
0x18000284f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002854  mov     ebx, eax
0x180002856  test    eax, eax
0x180002858  js      loc_180002A31
0x18000285e  mov     rcx, [rsp+200h+var_1C8]
0x180002863  lea     rdx, [rsp+200h+pbstr]
0x180002868  mov     rax, [rcx]
0x18000286b  mov     rax, [rax+20h]
0x18000286f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002874  mov     ebx, eax
0x180002876  test    eax, eax
0x180002878  js      loc_180002A15
0x18000287e  mov     rcx, [rsp+200h+var_1C8]
0x180002883  lea     rdx, [rsp+200h+var_1B0]
0x180002888  mov     rax, [rcx]
0x18000288b  mov     rax, [rax+28h]
0x18000288f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002894  mov     ebx, eax
0x180002896  test    eax, eax
0x180002898  js      loc_1800029F9
0x18000289e  mov     rcx, [rsp+200h+bstrString]; bstrString
0x1800028a3  mov     r14, rdi
0x1800028a6  inc     r14
0x1800028a9  cmp     [rcx+r14*2], r13w
0x1800028ae  jnz     short loc_1800028A6
0x1800028b0  mov     rax, [rsp+200h+pbstr]
0x1800028b5  mov     rsi, rdi
0x1800028b8  inc     rsi
0x1800028bb  cmp     [rax+rsi*2], r13w
0x1800028c0  jnz     short loc_1800028B8
0x1800028c2  mov     rax, [rsp+200h+var_1B0]
0x1800028c7  inc     rdi
0x1800028ca  cmp     [rax+rdi*2], r13w
0x1800028cf  jnz     short loc_1800028C7
0x1800028d1  call    cs:__imp_SysFreeString
0x1800028d7  mov     rcx, [rsp+200h+pbstr]; bstrString
0x1800028dc  mov     [rsp+200h+bstrString], r13
0x1800028e1  call    cs:__imp_SysFreeString
0x1800028e7  mov     rcx, [rsp+200h+var_1B0]; bstrString
0x1800028ec  mov     [rsp+200h+pbstr], r13
0x1800028f1  call    cs:__imp_SysFreeString
0x1800028f7  mov     rcx, [rsp+200h+var_1C8]
0x1800028fc  mov     [rsp+200h+var_1B0], r13
0x180002901  mov     rax, [rcx]
0x180002904  mov     rax, [rax+10h]
0x180002908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000290d  mov     rcx, [rsp+200h+var_1C0]
0x180002912  lea     rdx, [rsp+200h+var_1D0]
0x180002917  mov     [rsp+200h+var_1C8], r13
0x18000291c  mov     [rsp+200h+var_1D0], r13d
0x180002921  mov     rax, [rcx]
0x180002924  mov     rax, [rax+28h]
0x180002928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000292d  mov     ebx, eax
0x18000292f  test    eax, eax
0x180002931  js      loc_1800029DD
0x180002937  lea     eax, ds:6[rdi*2]
0x18000293e  add     r15d, 8
0x180002942  mov     ecx, eax
0x180002944  lea     r8d, ds:6[rsi*2]
0x18000294c  lea     r9d, ds:6[r14*2]
0x180002954  and     ecx, 3
0x180002957  mov     edx, r8d
0x18000295a  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180002961  and     edx, 3
0x180002964  add     edx, eax
0x180002966  mov     eax, r9d
0x180002969  and     eax, 3
0x18000296c  add     edx, ecx
0x18000296e  add     eax, edx
0x180002970  add     eax, r8d
0x180002973  add     eax, r9d
0x180002976  add     r15d, eax
0x180002979  mov     [rsp+200h+var_194], r15d
0x18000297e  cmp     [rsp+200h+var_1D0], r13d
0x180002983  jnz     loc_18000281E
0x180002989  lea     r14, aWebhostProtoco_2; "WEBHOST_PROTOCOL_MANAGER::RunCustomActi"...
0x180002990  mov     edx, r15d
0x180002993  lea     rcx, [rsp+200h+var_188]
0x180002998  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000299e  test    al, al
0x1800029a0  jnz     loc_180002A7A
0x1800029a6  call    cs:__imp_GetLastError
0x1800029ac  mov     ebx, eax
0x1800029ae  test    eax, eax
0x1800029b0  jle     short loc_1800029BB
0x1800029b2  movzx   ebx, ax
0x1800029b5  or      ebx, 80070000h
0x1800029bb  test    cs:g_dwDebugFlags, 0Fh
0x1800029c2  jz      loc_180002E2D
0x1800029c8  lea     rax, aFailedResizing; "Failed resizing the buffer to send data"...
0x1800029cf  mov     r9, r14
0x1800029d2  mov     r8d, 44Ch
0x1800029d8  jmp     loc_180002A6E
0x1800029dd  test    cs:g_dwDebugFlags, 0Fh
0x1800029e4  jz      loc_180002E2D
0x1800029ea  lea     rax, aErrorMovingThe; "Error moving the enum forward.\n"
0x1800029f1  mov     r8d, 43Fh
0x1800029f7  jmp     short loc_180002A67
0x1800029f9  test    cs:g_dwDebugFlags, 0Fh
0x180002a00  jz      loc_180002E2D
0x180002a06  lea     rax, aErrorRetrievin_1; "Error retrieving the physical path\n"
0x180002a0d  mov     r8d, 425h
0x180002a13  jmp     short loc_180002A67
0x180002a15  test    cs:g_dwDebugFlags, 0Fh
0x180002a1c  jz      loc_180002E2D
0x180002a22  lea     rax, aErrorRetrievin_4; "Error retrieving the virtual path\n"
0x180002a29  mov     r8d, 41Ah
0x180002a2f  jmp     short loc_180002A67
0x180002a31  test    cs:g_dwDebugFlags, 0Fh
0x180002a38  jz      loc_180002E2D
0x180002a3e  lea     rax, aErrorRetrievin_0; "Error retrieving the app domain id!\n"
0x180002a45  mov     r8d, 40Fh
0x180002a4b  jmp     short loc_180002A67
0x180002a4d  test    cs:g_dwDebugFlags, 0Fh
0x180002a54  jz      loc_180002E2D
0x180002a5a  mov     r8d, 3FFh
0x180002a60  lea     rax, aErrorRetrievin; "Error retrieving the app domain info ob"...
0x180002a67  lea     r9, aWebhostProtoco_2; "WEBHOST_PROTOCOL_MANAGER::RunCustomActi"...
0x180002a6e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180002a75  jmp     loc_18000279B
0x180002a7a  mov     eax, [rsp+200h+var_1A0]
0x180002a7e  mov     r15, [rbp+100h+var_168]
0x180002a82  mov     [r15], eax
0x180002a85  mov     rcx, [rsp+200h+var_1C0]
0x180002a8a  mov     rax, [rcx]
0x180002a8d  mov     rax, [rax+30h]
0x180002a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a96  mov     rcx, [rsp+200h+var_1C0]
0x180002a9b  lea     rdx, [rsp+200h+var_1D0]
0x180002aa0  mov     rax, [rcx]
0x180002aa3  mov     rax, [rax+28h]
0x180002aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aac  mov     ebx, eax
0x180002aae  test    eax, eax
0x180002ab0  jns     short loc_180002AD1
0x180002ab2  test    cs:g_dwDebugFlags, 0Fh
0x180002ab9  jz      loc_180002E2D
0x180002abf  lea     rax, aErrorMovingThe; "Error moving the enum forward.\n"
0x180002ac6  mov     r9, r14
0x180002ac9  mov     r8d, 45Dh
0x180002acf  jmp     short loc_180002A6E
0x180002ad1  add     r15, 4
0x180002ad5  cmp     [rsp+200h+var_1D0], r13d
0x180002ada  jz      loc_180002D0C
0x180002ae0  mov     rcx, [rsp+200h+var_1C0]
0x180002ae5  lea     rdx, [rsp+200h+var_1C8]
0x180002aea  mov     rax, [rcx]
0x180002aed  mov     rax, [rax+18h]
0x180002af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002af6  mov     ebx, eax
0x180002af8  test    eax, eax
0x180002afa  js      loc_180002DD2
0x180002b00  mov     rcx, [rsp+200h+var_1C8]
0x180002b05  lea     rdx, [rsp+200h+bstrString]
0x180002b0a  mov     rax, [rcx]
0x180002b0d  mov     rax, [rax+18h]
0x180002b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b16  mov     ebx, eax
0x180002b18  test    eax, eax
0x180002b1a  js      loc_180002DB7
0x180002b20  mov     rcx, [rsp+200h+var_1C8]
0x180002b25  lea     rdx, [rsp+200h+pbstr]
0x180002b2a  mov     rax, [rcx]
0x180002b2d  mov     rax, [rax+20h]
0x180002b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b36  mov     ebx, eax
0x180002b38  test    eax, eax
0x180002b3a  js      loc_180002D98
0x180002b40  mov     rcx, [rsp+200h+var_1C8]
0x180002b45  lea     rdx, [rsp+200h+var_1B0]
0x180002b4a  mov     rax, [rcx]
0x180002b4d  mov     rax, [rax+28h]
0x180002b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b56  mov     ebx, eax
0x180002b58  test    eax, eax
0x180002b5a  js      loc_180002D79
0x180002b60  mov     rcx, [rsp+200h+var_1C8]
0x180002b65  lea     rdx, [rsp+200h+var_19C]
0x180002b6a  mov     rax, [rcx]
0x180002b6d  mov     rax, [rax+30h]
0x180002b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b76  mov     ebx, eax
0x180002b78  test    eax, eax
0x180002b7a  js      loc_180002D5A
0x180002b80  mov     rcx, [rsp+200h+var_1C8]
0x180002b85  lea     rdx, [rsp+200h+var_198]
0x180002b8a  mov     rax, [rcx]
0x180002b8d  mov     rax, [rax+38h]
0x180002b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b96  mov     ebx, eax
0x180002b98  test    eax, eax
  ... truncated ...
```
