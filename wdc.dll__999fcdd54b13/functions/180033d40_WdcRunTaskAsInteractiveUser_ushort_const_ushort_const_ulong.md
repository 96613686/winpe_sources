# WdcRunTaskAsInteractiveUser(ushort const *,ushort const *,ulong)

- ea: `0x180033d40`
- end: `0x18003420f`
- name: `?WdcRunTaskAsInteractiveUser@@YAJPEBG0K@Z`
- size: `1231`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000b7d0`
- `0x18000b854`
- `0x180019990`
- `0x180033d40`
- `0x180086010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180033e43`
- `KERNEL32!GetCurrentProcessId` at `0x180033e43`
- `KERNEL32!GetLastError` at `0x180033e5f`
- `KERNEL32!GetLastError` at `0x180033ea5`
- `KERNEL32!GetLastError` at `0x180033ee3`
- `KERNEL32!GetLastError` at `0x180033e5f`
- `KERNEL32!GetLastError` at `0x180033ea5`
- `KERNEL32!GetLastError` at `0x180033ee3`
- `KERNEL32!ProcessIdToSessionId` at `0x180033e50`
- `KERNEL32!ProcessIdToSessionId` at `0x180033e50`
- `OLEAUT32!__imp_SysAllocString` at `0x180034018`
- `OLEAUT32!__imp_SysAllocString` at `0x18003408d`
- `OLEAUT32!__imp_SysAllocString` at `0x180034018`
- `OLEAUT32!__imp_SysAllocString` at `0x18003408d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180033fa8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180033fa8`
- `OLEAUT32!__imp_SysFreeString` at `0x180033f9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180034080`
- `OLEAUT32!__imp_SysFreeString` at `0x180034187`
- `OLEAUT32!__imp_SysFreeString` at `0x180033f9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180034080`
- `OLEAUT32!__imp_SysFreeString` at `0x180034187`
- `OLEAUT32!__imp_VariantInit` at `0x180033da7`
- `OLEAUT32!__imp_VariantInit` at `0x180033db2`
- `OLEAUT32!__imp_VariantInit` at `0x180033da7`
- `OLEAUT32!__imp_VariantInit` at `0x180033db2`
- `OLEAUT32!__imp_VariantClear` at `0x180034173`
- `OLEAUT32!__imp_VariantClear` at `0x18003417e`
- `OLEAUT32!__imp_VariantClear` at `0x180034173`
- `OLEAUT32!__imp_VariantClear` at `0x18003417e`
- `ole32!CoCreateInstance` at `0x180033dd6`
- `ole32!CoCreateInstance` at `0x180033dd6`
- `WTSAPI32!WTSFreeMemory` at `0x180034197`
- `WTSAPI32!WTSFreeMemory` at `0x1800341a7`
- `WTSAPI32!WTSFreeMemory` at `0x180034197`
- `WTSAPI32!WTSFreeMemory` at `0x1800341a7`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180033e9b`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180033ed9`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180033e9b`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180033ed9`

## string_xrefs

- `0x180033f7d`: `WdcRunTaskAsInteractiveUser`
- `0x1800340cf`: `WdcRunTaskAsInteractiveUser`
- `0x18003415c`: `WdcRunTaskAsInteractiveUser`
- `0x18003400c`: `\Microsoft\Windows\Task Manager`

## pseudocode

```c
__int64 __fastcall WdcRunTaskAsInteractiveUser(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int a3)
{
  OLECHAR *v4; // rdi
  HRESULT v7; // eax
  signed int v8; // ebx
  __int64 v9; // rax
  __int64 (__fastcall *v10)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  signed int v13; // eax
  signed int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r15
  int v20; // eax
  unsigned __int16 *v21; // rax
  BSTR v22; // rax
  BSTR v23; // rax
  __int64 v24; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  LPVOID *ppva; // [rsp+20h] [rbp-E0h]
  DWORD pSessionId; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR ppBuffer; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v33; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG v34; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v36; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v37; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *pRecInfo; // [rsp+D0h] [rbp-30h]
  VARIANTARG v39; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG v40; // [rsp+100h] [rbp+0h] BYREF
  DWORD pBytesReturned; // [rsp+188h] [rbp+88h] BYREF

  ppBuffer = 0;
  memset(&v34, 0, sizeof(v34));
  v32 = 0;
  v4 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  pBytesReturned = 0;
  pSessionId = 0;
  v33 = 0;
  v31 = 0;
  v30 = 0;
  VariantInit(&pvarg);
  VariantInit(&v34);
  v7 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v33);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_42;
  v37 = *(_OWORD *)&pvarg.vt;
  v9 = *(_QWORD *)v33;
  pRecInfo = pvarg.pRecInfo;
  v39 = pvarg;
  v10 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v9 + 80);
  v40 = pvarg;
  v36 = pvarg;
  v7 = v10(v33, &v36, &v40, &v39, &v37);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_42;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( !LastError )
      goto LABEL_22;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_23;
  }
  if ( !WTSQuerySessionInformationW(0, pSessionId, WTSDomainName, &ppBuffer, &pBytesReturned) )
  {
    v13 = GetLastError();
    v8 = v13;
    if ( !v13 )
      goto LABEL_22;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_23;
  }
  if ( !WTSQuerySessionInformationW(0, pSessionId, WTSUserName, &v30, &pBytesReturned) )
  {
    v14 = GetLastError();
    v8 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v8 = (unsigned __int16)v14 | 0x80070000;
      if ( v8 >= 0 )
        goto LABEL_18;
LABEL_23:
      v7 = v8;
      goto LABEL_42;
    }
LABEL_22:
    v8 = -2147467259;
    goto LABEL_23;
  }
LABEL_18:
  v15 = -1;
  if ( a2 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a2[v16] );
  }
  else
  {
    v16 = 0;
  }
  v17 = -1;
  do
    ++v17;
  while ( a1[v17] );
  v18 = -1;
  do
    ++v18;
  while ( ppBuffer[v18] );
  do
    ++v15;
  while ( v30[v15] );
  v19 = v15 + v18 + v17;
  v20 = ULongLongToULong(v16 + v19 + 13, &pBytesReturned);
  v8 = v20;
  if ( v20 < 0 )
  {
    LODWORD(ppv) = v20;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\run.cpp",
      "WdcRunTaskAsInteractiveUser",
      0,
      L"FAILURE: 0x%08x",
      ppv);
    goto LABEL_44;
  }
  SysFreeString(0);
  v21 = SysAllocStringLen(0, pBytesReturned);
  v4 = v21;
  if ( !v16 )
    a2 = &pszTargetName;
  v7 = StringCchPrintfW(v21, v16 + v19 + 13, L"%08x|%s\\%s|%s|%s", a3, ppBuffer, v30, a2, a1);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_42;
  v34.llVal = (LONGLONG)v4;
  v34.vt = 8;
  v22 = SysAllocString(L"\\Microsoft\\Windows\\Task Manager");
  v4 = v22;
  if ( !v22 )
  {
    LODWORD(ppv) = -2147024882;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", ppv);
    v4 = 0;
    LODWORD(ppv) = -2147024882;
    v8 = -2147024882;
LABEL_43:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\run.cpp",
      "WdcRunTaskAsInteractiveUser",
      0,
      L"FAILURE: 0x%08x",
      ppv);
    goto LABEL_44;
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v33 + 56LL))(v33, v22, &v32);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_42;
  SysFreeString(v4);
  v23 = SysAllocString(L"Interactive");
  v4 = v23;
  if ( !v23 )
  {
    LODWORD(ppv) = -2147024882;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", ppv);
    LODWORD(ppva) = -2147024882;
    v8 = -2147024882;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\run.cpp",
      "WdcRunTaskAsInteractiveUser",
      0,
      L"FAILURE: 0x%08x",
      ppva);
    v4 = 0;
    goto LABEL_44;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 **))(*(_QWORD *)v32 + 104LL))(v32, v23, &v31);
  v8 = v7;
  if ( v7 < 0
    || (v24 = *v31,
        v36 = v34,
        v7 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int64, _QWORD, _QWORD, _QWORD))(v24 + 104))(
               v31,
               &v36,
               4,
               pSessionId,
               0,
               0),
        v8 = v7,
        v7 < 0) )
  {
LABEL_42:
    LODWORD(ppv) = v7;
    goto LABEL_43;
  }
LABEL_44:
  VariantClear(&pvarg);
  VariantClear(&v34);
  SysFreeString(v4);
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  if ( v30 )
    WTSFreeMemory(v30);
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
    v31 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v33 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180033d40  push    rbp
0x180033d42  push    rbx
0x180033d43  push    rsi
0x180033d44  push    rdi
0x180033d45  push    r12
0x180033d47  push    r13
0x180033d49  push    r14
0x180033d4b  push    r15
0x180033d4d  lea     rbp, [rsp-28h]
0x180033d52  sub     rsp, 128h
0x180033d59  xor     r15d, r15d
0x180033d5c  xorps   xmm0, xmm0
0x180033d5f  xor     eax, eax
0x180033d61  mov     [rsp+160h+ppBuffer], r15
0x180033d66  mov     r12, rcx
0x180033d69  mov     qword ptr [rbp+60h+var_F0+10h], rax
0x180033d6d  lea     rcx, [rbp+60h+pvarg]; pvarg
0x180033d71  mov     qword ptr [rbp+60h+pvarg+10h], rax
0x180033d75  movups  xmmword ptr [rsp+160h+var_F0], xmm0
0x180033d7a  mov     [rsp+160h+var_100], r15
0x180033d7f  mov     edi, r15d
0x180033d82  movups  xmmword ptr [rbp+60h+pvarg], xmm0
0x180033d86  mov     [rbp+60h+pBytesReturned], r15d
0x180033d8d  mov     r13d, r8d
0x180033d90  mov     [rsp+160h+pSessionId], r15d
0x180033d95  mov     r14, rdx
0x180033d98  mov     [rsp+160h+var_F8], r15
0x180033d9d  mov     [rsp+160h+var_108], r15
0x180033da2  mov     [rsp+160h+var_110], r15
0x180033da7  call    cs:__imp_VariantInit
0x180033dad  lea     rcx, [rsp+160h+var_F0]; pvarg
0x180033db2  call    cs:__imp_VariantInit
0x180033db8  lea     rax, [rsp+160h+var_F8]
0x180033dbd  xor     edx, edx; pUnkOuter
0x180033dbf  lea     r9, IID_ITaskService; riid
0x180033dc6  mov     [rsp+160h+ppv], rax; ppv
0x180033dcb  lea     r8d, [r15+1]; dwClsContext
0x180033dcf  lea     rcx, CLSID_TaskScheduler; rclsid
0x180033dd6  call    cs:__imp_CoCreateInstance
0x180033ddc  mov     ebx, eax
0x180033dde  test    eax, eax
0x180033de0  js      loc_18003414E
0x180033de6  movups  xmm1, xmmword ptr [rbp+60h+pvarg]
0x180033dea  lea     rdx, [rbp+60h+var_A0]
0x180033dee  mov     rcx, [rsp+160h+var_F8]
0x180033df3  movsd   xmm0, qword ptr [rbp+60h+pvarg+10h]
0x180033df8  lea     r9, [rbp+60h+var_80]
0x180033dfc  mov     [rsp+160h+ppv], rdx
0x180033e01  lea     r8, [rbp+60h+var_60]
0x180033e05  lea     rdx, [rbp+60h+var_C0]
0x180033e09  movaps  [rbp+60h+var_A0], xmm1
0x180033e0d  mov     rax, [rcx]
0x180033e10  movsd   [rbp+60h+var_90], xmm0
0x180033e15  movaps  [rbp+60h+var_80], xmm1
0x180033e19  movsd   [rbp+60h+var_70], xmm0
0x180033e1e  mov     rax, [rax+50h]
0x180033e22  movaps  [rbp+60h+var_60], xmm1
0x180033e26  movsd   [rbp+60h+var_50], xmm0
0x180033e2b  movaps  [rbp+60h+var_C0], xmm1
0x180033e2f  movsd   [rbp+60h+var_B0], xmm0
0x180033e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e39  mov     ebx, eax
0x180033e3b  test    eax, eax
0x180033e3d  js      loc_18003414E
0x180033e43  call    cs:__imp_GetCurrentProcessId
0x180033e49  mov     ecx, eax; dwProcessId
0x180033e4b  lea     rdx, [rsp+160h+pSessionId]; pSessionId
0x180033e50  call    cs:__imp_ProcessIdToSessionId
0x180033e56  mov     esi, 80070000h
0x180033e5b  test    eax, eax
0x180033e5d  jnz     short loc_180033E7E
0x180033e5f  call    cs:__imp_GetLastError
0x180033e65  mov     ebx, eax
0x180033e67  test    eax, eax
0x180033e69  jz      loc_180033F12
0x180033e6f  jle     short loc_180033E76
0x180033e71  movzx   ebx, ax
0x180033e74  or      ebx, esi
0x180033e76  test    ebx, ebx
0x180033e78  js      loc_180033F17
0x180033e7e  mov     edx, [rsp+160h+pSessionId]; SessionId
0x180033e82  lea     rax, [rbp+60h+pBytesReturned]
0x180033e89  lea     r9, [rsp+160h+ppBuffer]; ppBuffer
0x180033e8e  mov     [rsp+160h+ppv], rax; pBytesReturned
0x180033e93  mov     r8d, 7; WTSInfoClass
0x180033e99  xor     ecx, ecx; hServer
0x180033e9b  call    cs:__imp_WTSQuerySessionInformationW
0x180033ea1  test    eax, eax
0x180033ea3  jnz     short loc_180033EBC
0x180033ea5  call    cs:__imp_GetLastError
0x180033eab  mov     ebx, eax
0x180033ead  test    eax, eax
0x180033eaf  jz      short loc_180033F12
0x180033eb1  jle     short loc_180033EB8
0x180033eb3  movzx   ebx, ax
0x180033eb6  or      ebx, esi
0x180033eb8  test    ebx, ebx
0x180033eba  js      short loc_180033F17
0x180033ebc  mov     edx, [rsp+160h+pSessionId]; SessionId
0x180033ec0  lea     rax, [rbp+60h+pBytesReturned]
0x180033ec7  lea     r9, [rsp+160h+var_110]; ppBuffer
0x180033ecc  mov     [rsp+160h+ppv], rax; pBytesReturned
0x180033ed1  mov     r8d, 5; WTSInfoClass
0x180033ed7  xor     ecx, ecx; hServer
0x180033ed9  call    cs:__imp_WTSQuerySessionInformationW
0x180033edf  test    eax, eax
0x180033ee1  jnz     short loc_180033EFA
0x180033ee3  call    cs:__imp_GetLastError
0x180033ee9  mov     ebx, eax
0x180033eeb  test    eax, eax
0x180033eed  jz      short loc_180033F12
0x180033eef  jle     short loc_180033EF6
0x180033ef1  movzx   ebx, ax
0x180033ef4  or      ebx, esi
0x180033ef6  test    ebx, ebx
0x180033ef8  js      short loc_180033F17
0x180033efa  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180033efe  test    r14, r14
0x180033f01  jz      short loc_180033F1E
0x180033f03  mov     rsi, rcx
0x180033f06  inc     rsi
0x180033f09  cmp     [r14+rsi*2], r15w
0x180033f0e  jnz     short loc_180033F06
0x180033f10  jmp     short loc_180033F21
0x180033f12  mov     ebx, 80004005h
0x180033f17  mov     eax, ebx
0x180033f19  jmp     loc_18003414E
0x180033f1e  mov     rsi, r15
0x180033f21  mov     rax, rcx
0x180033f24  inc     rax
0x180033f27  cmp     [r12+rax*2], r15w
0x180033f2c  jnz     short loc_180033F24
0x180033f2e  mov     r8, [rsp+160h+ppBuffer]
0x180033f33  mov     rdx, rcx
0x180033f36  inc     rdx
0x180033f39  cmp     [r8+rdx*2], r15w
0x180033f3e  jnz     short loc_180033F36
0x180033f40  mov     r8, [rsp+160h+var_110]
0x180033f45  inc     rcx
0x180033f48  cmp     [r8+rcx*2], r15w
0x180033f4d  jnz     short loc_180033F45
0x180033f4f  lea     r15, [rdx+rax]
0x180033f53  add     r15, rcx
0x180033f56  lea     rdx, [rbp+60h+pBytesReturned]; unsigned int *
0x180033f5d  lea     rcx, [r15+0Dh]
0x180033f61  add     rcx, rsi; unsigned __int64
0x180033f64  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180033f69  mov     ebx, eax
0x180033f6b  test    eax, eax
0x180033f6d  jns     short loc_180033F98
0x180033f6f  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180033f76  mov     dword ptr [rsp+160h+ppv], eax
0x180033f7a  xor     r8d, r8d; int
0x180033f7d  lea     rdx, aWdcruntaskasin_0; "WdcRunTaskAsInteractiveUser"
0x180033f84  lea     rcx, aBaseDiagnosisP_19; "base\\diagnosis\\pdui\\perfmon\\mon\\ru"...
0x180033f8b  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180033f90  xor     r15d, r15d
0x180033f93  jmp     loc_18003416F
0x180033f98  xor     ecx, ecx; bstrString
0x180033f9a  call    cs:__imp_SysFreeString
0x180033fa0  mov     edx, [rbp+60h+pBytesReturned]; ui
0x180033fa6  xor     ecx, ecx; strIn
0x180033fa8  call    cs:__imp_SysAllocStringLen
0x180033fae  mov     rcx, [rsp+160h+var_110]
0x180033fb3  lea     rdx, [r15+0Dh]
0x180033fb7  mov     rdi, rax
0x180033fba  mov     [rsp+160h+var_128], r12
0x180033fbf  lea     rax, pszTargetName
0x180033fc6  test    rsi, rsi
0x180033fc9  mov     r9d, r13d
0x180033fcc  lea     r8, a08xSSSS; "%08x|%s\\%s|%s|%s"
0x180033fd3  cmovz   r14, rax
0x180033fd7  add     rdx, rsi; unsigned __int64
0x180033fda  mov     [rsp+160h+var_130], r14
0x180033fdf  mov     [rsp+160h+var_138], rcx
0x180033fe4  mov     rcx, [rsp+160h+ppBuffer]
0x180033fe9  mov     [rsp+160h+ppv], rcx
0x180033fee  mov     rcx, rdi; unsigned __int16 *
0x180033ff1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033ff6  xor     r15d, r15d
0x180033ff9  mov     ebx, eax
0x180033ffb  test    eax, eax
0x180033ffd  js      loc_18003414E
0x180034003  lea     eax, [r15+8]
0x180034007  mov     qword ptr [rsp+160h+var_F0+8], rdi
0x18003400c  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\Task Manager"
0x180034013  mov     word ptr [rsp+160h+var_F0], ax
0x180034018  call    cs:__imp_SysAllocString
0x18003401e  mov     rdi, rax
0x180034021  test    rax, rax
0x180034024  jnz     short loc_18003405A
0x180034026  mov     esi, 8007000Eh
0x18003402b  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180034032  xor     r8d, r8d; int
0x180034035  mov     dword ptr [rsp+160h+ppv], esi
0x180034039  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180034040  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180034047  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003404c  mov     edi, r15d
0x18003404f  mov     dword ptr [rsp+160h+ppv], esi
0x180034053  mov     ebx, esi
0x180034055  jmp     loc_180034152
0x18003405a  mov     rcx, [rsp+160h+var_F8]
0x18003405f  lea     r8, [rsp+160h+var_100]
0x180034064  mov     rdx, rdi
0x180034067  mov     rax, [rcx]
0x18003406a  mov     rax, [rax+38h]
0x18003406e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034073  mov     ebx, eax
0x180034075  test    eax, eax
0x180034077  js      loc_18003414E
0x18003407d  mov     rcx, rdi; bstrString
0x180034080  call    cs:__imp_SysFreeString
0x180034086  lea     rcx, aInteractive; "Interactive"
0x18003408d  call    cs:__imp_SysAllocString
0x180034093  mov     rdi, rax
0x180034096  test    rax, rax
0x180034099  jnz     short loc_1800340EC
0x18003409b  mov     esi, 8007000Eh
0x1800340a0  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800340a7  xor     r8d, r8d; int
0x1800340aa  mov     dword ptr [rsp+160h+ppv], esi
0x1800340ae  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x1800340b5  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x1800340bc  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800340c1  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800340c8  mov     dword ptr [rsp+160h+ppv], esi
0x1800340cc  xor     r8d, r8d; int
0x1800340cf  lea     rdx, aWdcruntaskasin_0; "WdcRunTaskAsInteractiveUser"
0x1800340d6  lea     rcx, aBaseDiagnosisP_19; "base\\diagnosis\\pdui\\perfmon\\mon\\ru"...
0x1800340dd  mov     ebx, esi
0x1800340df  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800340e4  mov     rdi, r15
0x1800340e7  jmp     loc_18003416F
0x1800340ec  mov     rcx, [rsp+160h+var_100]
0x1800340f1  lea     r8, [rsp+160h+var_108]
0x1800340f6  mov     rdx, rdi
0x1800340f9  mov     rax, [rcx]
0x1800340fc  mov     rax, [rax+68h]
0x180034100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034105  mov     ebx, eax
0x180034107  test    eax, eax
0x180034109  js      short loc_18003414E
0x18003410b  mov     rcx, [rsp+160h+var_108]
0x180034110  lea     rdx, [rbp+60h+var_C0]
0x180034114  movups  xmm0, xmmword ptr [rsp+160h+var_F0]
0x180034119  mov     r8d, 4
0x18003411f  mov     r9d, [rsp+160h+pSessionId]
0x180034124  movsd   xmm1, qword ptr [rbp+60h+var_F0+10h]
0x180034129  mov     rax, [rcx]
0x18003412c  mov     [rsp+160h+var_138], r15
0x180034131  movaps  [rbp+60h+var_C0], xmm0
0x180034135  movsd   [rbp+60h+var_B0], xmm1
0x18003413a  mov     rax, [rax+68h]
0x18003413e  mov     [rsp+160h+ppv], r15
0x180034143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034148  mov     ebx, eax
0x18003414a  test    eax, eax
0x18003414c  jns     short loc_18003416F
0x18003414e  mov     dword ptr [rsp+160h+ppv], eax
0x180034152  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180034159  xor     r8d, r8d; int
0x18003415c  lea     rdx, aWdcruntaskasin_0; "WdcRunTaskAsInteractiveUser"
0x180034163  lea     rcx, aBaseDiagnosisP_19; "base\\diagnosis\\pdui\\perfmon\\mon\\ru"...
0x18003416a  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003416f  lea     rcx, [rbp+60h+pvarg]; pvarg
0x180034173  call    cs:__imp_VariantClear
0x180034179  lea     rcx, [rsp+160h+var_F0]; pvarg
0x18003417e  call    cs:__imp_VariantClear
0x180034184  mov     rcx, rdi; bstrString
0x180034187  call    cs:__imp_SysFreeString
0x18003418d  mov     rcx, [rsp+160h+ppBuffer]; pMemory
0x180034192  test    rcx, rcx
0x180034195  jz      short loc_18003419D
0x180034197  call    cs:__imp_WTSFreeMemory
0x18003419d  mov     rcx, [rsp+160h+var_110]; pMemory
0x1800341a2  test    rcx, rcx
0x1800341a5  jz      short loc_1800341AD
0x1800341a7  call    cs:__imp_WTSFreeMemory
0x1800341ad  mov     rcx, [rsp+160h+var_108]
0x1800341b2  test    rcx, rcx
0x1800341b5  jz      short loc_1800341C8
0x1800341b7  mov     rax, [rcx]
0x1800341ba  mov     rax, [rax+10h]
0x1800341be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341c3  mov     [rsp+160h+var_108], r15
0x1800341c8  mov     rcx, [rsp+160h+var_100]
0x1800341cd  test    rcx, rcx
0x1800341d0  jz      short loc_1800341E3
0x1800341d2  mov     rax, [rcx]
0x1800341d5  mov     rax, [rax+10h]
0x1800341d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341de  mov     [rsp+160h+var_100], r15
0x1800341e3  mov     rcx, [rsp+160h+var_F8]
0x1800341e8  test    rcx, rcx
0x1800341eb  jz      short loc_1800341F9
0x1800341ed  mov     rax, [rcx]
0x1800341f0  mov     rax, [rax+10h]
0x1800341f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341f9  mov     eax, ebx
  ... truncated ...
```
