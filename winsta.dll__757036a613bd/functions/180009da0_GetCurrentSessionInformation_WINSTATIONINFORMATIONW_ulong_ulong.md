# GetCurrentSessionInformation(_WINSTATIONINFORMATIONW *,ulong,ulong *)

- ea: `0x180009da0`
- end: `0x18000a780`
- name: `?GetCurrentSessionInformation@@YAJPEAU_WINSTATIONINFORMATIONW@@KPEAK@Z`
- size: `2528`
- prototype: `__int64 __fastcall(struct _WINSTATIONINFORMATIONW *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b2b0`
- `0x18000c820`

## callees

- `0x180005374`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008340`
- `0x180008e30`
- `0x180009da0`
- `0x18000baac`
- `0x1800230b8`
- `0x1800230ec`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18000a08d`
- `msvcrt!_resetstkoflw` at `0x18000a3d8`
- `msvcrt!_resetstkoflw` at `0x18000a08d`
- `msvcrt!_resetstkoflw` at `0x18000a3d8`
- `ntdll!NtQuerySystemTime` at `0x18000a327`
- `ntdll!NtQuerySystemTime` at `0x18000a327`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a0c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a40b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a0c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a40b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a628`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a45d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a48f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a45d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a48f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a577`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a775`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a577`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a775`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a46e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a46e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a346`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a346`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a481`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a481`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a32d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a32d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a271`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a271`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030462`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800304a2`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030462`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800304a2`
- `RPCRT4!NdrClientCall3` at `0x18000a069`
- `RPCRT4!NdrClientCall3` at `0x18000a3c3`
- `RPCRT4!NdrClientCall3` at `0x18000a069`
- `RPCRT4!NdrClientCall3` at `0x18000a3c3`

## string_xrefs

- `0x18000a501`: `StringCchCopy failed: %x`
- `0x18000a521`: `StringCchCopy failed: %x`
- `0x18000a230`: `StringCchCopy failed: 0x%x in %s`
- `0x18000a4a6`: `OpenProcessToken failed: 0x%x`
- `0x18000a43b`: `RpcGetSessionProtocolLastInputTime failed: 0x%x`
- `0x18000a5b7`: `OpenThreadToken failed: 0x%x`
- `0x18000a3ee`: `Stack Overflow occured at RpcGetCurrentSessionProtocolLastInputTime(): 0x%x`
- `0x18000a4eb`: `RpcGetCurrentSessionProtocolLastInputTime failed: 0x%x in %s`
- `0x18000a680`: `RpcGetCurrentSessionProtocolLastInputTime returned NULL pBuffStatus`
- `0x18000a6af`: `RpcGetCurrentSessionProtocolLastInputTime returned %d bytes, expected %d`

## pseudocode

```c
__int64 __fastcall GetCurrentSessionInformation(struct _WINSTATIONINFORMATIONW *a1, unsigned int a2, unsigned int *a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  _WORD *v7; // r9
  __int64 v8; // r14
  int *v9; // r15
  __int64 v10; // rcx
  int *v11; // rdx
  __int64 v12; // r10
  __int16 v13; // ax
  int v14; // esi
  _WORD *v15; // rax
  int v16; // esi
  _QWORD *v17; // rax
  _QWORD *v18; // rbx
  _WORD *v19; // r9
  __int64 v20; // rcx
  __int64 v21; // r10
  __int16 v22; // ax
  _WORD *v23; // rax
  __int64 v24; // rax
  CLIENT_CALL_RETURN v25; // rbx
  unsigned int v26; // r11d
  struct _WINSTATIONINFORMATIONW *v27; // r15
  __int64 v28; // rcx
  __int16 *v29; // rdx
  __int64 v30; // r9
  BYTE *v31; // r10
  __int16 v32; // ax
  __int64 v33; // r8
  BYTE *v34; // rax
  __int64 v35; // rcx
  __int16 *v36; // rdx
  __int64 v37; // r9
  BYTE *v38; // r10
  __int16 v39; // ax
  BYTE *v40; // rax
  __int16 *v41; // rcx
  __int64 v42; // rdx
  BYTE *v43; // r9
  __int16 v44; // ax
  BYTE *v45; // rax
  HANDLE CurrentThread; // rax
  int UserSessionId; // eax
  __int64 v49; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v52; // eax
  signed int v53; // eax
  _OWORD *v54; // rax
  BYTE *v55; // rcx
  __int64 v56; // rdx
  CLIENT_CALL_RETURN v57; // [rsp+20h] [rbp-198h]
  __int64 v58; // [rsp+40h] [rbp-178h] BYREF
  struct _WINSTATIONINFORMATIONW *v59; // [rsp+48h] [rbp-170h]
  struct _WINSTATIONINFORMATIONW *v60; // [rsp+50h] [rbp-168h]
  HANDLE hObject[2]; // [rsp+58h] [rbp-160h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-150h] BYREF
  struct _WINSTATIONINFORMATIONW *Pointer; // [rsp+70h] [rbp-148h]
  unsigned __int16 v64[4]; // [rsp+78h] [rbp-140h] BYREF
  _QWORD *v65; // [rsp+80h] [rbp-138h]
  unsigned __int16 v66[4]; // [rsp+88h] [rbp-130h] BYREF
  _QWORD *v67; // [rsp+90h] [rbp-128h]
  unsigned int *v68; // [rsp+98h] [rbp-120h]
  CLIENT_CALL_RETURN v69; // [rsp+A0h] [rbp-118h]
  char v70[8]; // [rsp+B0h] [rbp-108h] BYREF
  int v71; // [rsp+B8h] [rbp-100h]
  char v72; // [rsp+C0h] [rbp-F8h] BYREF
  char v73; // [rsp+102h] [rbp-B6h] BYREF
  char v74; // [rsp+126h] [rbp-92h] BYREF
  __int64 v75; // [rsp+150h] [rbp-68h]
  __int64 v76; // [rsp+158h] [rbp-60h]
  __int64 v77; // [rsp+160h] [rbp-58h]
  HLOCAL v78; // [rsp+178h] [rbp-40h]

  Pointer = a1;
  v59 = a1;
  v60 = a1;
  v68 = a3;
  *(_QWORD *)v66 = 0;
  v5 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    *v5 = 0;
    v5[1] = 0;
    v5[2] = 0;
    v5[3] = 0;
    v5[4] = 0;
    v5[5] = 0;
    v5[6] = 1;
    v5[7] = 0;
    v7 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
    v6[5] = v7;
    v8 = 2147483646;
    v9 = &dword_18003D0CC;
    if ( v7 )
    {
      v10 = 2147483646;
      v11 = &dword_18003D0CC;
      v12 = 1;
      do
      {
        if ( !v10 )
          break;
        v13 = *(_WORD *)v11;
        if ( !*(_WORD *)v11 )
          break;
        v11 = (int *)((char *)v11 + 2);
        *v7++ = v13;
        --v10;
        --v12;
      }
      while ( v12 );
      v14 = -2147024774;
      if ( v12 )
        v14 = 0;
      v15 = v7 - 1;
      if ( v12 )
        v15 = v7;
      *v15 = 0;
      if ( v12 )
      {
        if ( !v6[3] && !*((_DWORD *)v6 + 12) )
        {
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v6) == -2147023174 )
            *((_DWORD *)v6 + 13) = 1;
          CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v6);
        }
      }
      else
      {
        ConvertHRESULT2WIN32(v14);
        _DbgPrintMessage(8, "StringCchCopy failed: %x", v14);
      }
    }
  }
  else
  {
    v6 = 0;
    v8 = 2147483646;
    v9 = &dword_18003D0CC;
  }
  v16 = -2147024774;
  v67 = v6;
  if ( v6 )
  {
    *(_DWORD *)&v66[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  *(_QWORD *)v64 = 1;
  v17 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v17;
  if ( v17 )
  {
    *v17 = 0;
    v17[1] = 0;
    v17[2] = 0;
    v17[3] = 0;
    v17[4] = 0;
    v17[5] = 0;
    v17[6] = 1;
    v17[7] = 0;
    v19 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
    v18[5] = v19;
    if ( v19 )
    {
      v20 = 2147483646;
      v21 = 1;
      do
      {
        if ( !v20 )
          break;
        v22 = *(_WORD *)v9;
        if ( !*(_WORD *)v9 )
          break;
        v9 = (int *)((char *)v9 + 2);
        *v19++ = v22;
        --v20;
        --v21;
      }
      while ( v21 );
      if ( v21 )
        v16 = 0;
      v23 = v19 - 1;
      if ( v21 )
        v23 = v19;
      *v23 = 0;
      if ( v21 )
      {
        if ( !v18[3] && !*((_DWORD *)v18 + 12) )
        {
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v18) == -2147023174 )
            *((_DWORD *)v18 + 13) = 1;
          CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v18);
        }
      }
      else
      {
        ConvertHRESULT2WIN32(v16);
        _DbgPrintMessage(8, "StringCchCopy failed: %x", v16);
      }
    }
  }
  else
  {
    v18 = 0;
  }
  v65 = v18;
  if ( v18 )
  {
    *(_DWORD *)&v64[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  memset_0(v70, 0, 0xD0u);
  hMem = 0;
  HIDWORD(v58) = 0;
  hObject[0] = 0;
  *v68 = 0;
  if ( a2 < 0x4C0 )
  {
    LODWORD(v25.Pointer) = -2147024809;
    goto LABEL_64;
  }
  memset_0(a1, 0, sizeof(struct _WINSTATIONINFORMATIONW));
  if ( CSmartPublicBinding::operator void *(v66) && CSmartPublicBinding::operator void *(v64) )
  {
    v24 = CSmartPublicBinding::operator void *(v66);
    v69.Simple = 0;
    v25.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032230, 2u, 0, v24, 1, v70).Pointer;
    v69.Pointer = v25.Pointer;
    v26 = -2147024774;
    v27 = Pointer;
    if ( SLODWORD(v25.Simple) < 0 )
    {
      _DbgPrintMessage(
        8,
        "RpcGetCurrentSessionInformation failed: 0x%x in %s",
        LODWORD(v25.Pointer),
        "GetCurrentSessionInformation");
      goto LABEL_64;
    }
    v28 = 2147483646;
    v29 = (__int16 *)&v74;
    v30 = 21;
    v31 = &a1->Reserved3[1084];
    do
    {
      if ( !v28 )
        break;
      v32 = *v29;
      if ( !*v29 )
        break;
      ++v29;
      *(_WORD *)v31 = v32;
      v31 += 2;
      --v28;
      --v30;
    }
    while ( v30 );
    v33 = 2147942522LL;
    if ( v30 )
      v33 = 0;
    v34 = v31 - 2;
    if ( v30 )
      v34 = v31;
    *(_WORD *)v34 = 0;
    if ( !v30 )
      goto LABEL_107;
    v35 = 2147483646;
    v36 = (__int16 *)&v73;
    v37 = 18;
    v38 = &a1->Reserved3[1048];
    do
    {
      if ( !v35 )
        break;
      v39 = *v36;
      if ( !*v36 )
        break;
      ++v36;
      *(_WORD *)v38 = v39;
      v38 += 2;
      --v35;
      --v37;
    }
    while ( v37 );
    v33 = 2147942522LL;
    if ( v37 )
      v33 = 0;
    v40 = v38 - 2;
    if ( v37 )
      v40 = v38;
    *(_WORD *)v40 = 0;
    if ( !v37 )
    {
LABEL_107:
      LODWORD(v25.Pointer) = v33;
      goto LABEL_63;
    }
    *(_DWORD *)v27->Reserved2 = v71;
    v41 = (__int16 *)&v72;
    v42 = 33;
    v43 = &a1->Reserved2[4];
    do
    {
      if ( !v8 )
        break;
      v44 = *v41;
      if ( !*v41 )
        break;
      ++v41;
      *(_WORD *)v43 = v44;
      v43 += 2;
      --v8;
      --v42;
    }
    while ( v42 );
    if ( v42 )
      v26 = 0;
    v45 = v43 - 2;
    if ( v42 )
      v45 = v43;
    *(_WORD *)v45 = 0;
    if ( !v42 )
    {
      LODWORD(v25.Pointer) = v26;
      v33 = v26;
LABEL_63:
      _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", v33, "GetCurrentSessionInformation");
      goto LABEL_64;
    }
    *(_QWORD *)&a1->Reserved3[4] = v75;
    v59 = (struct _WINSTATIONINFORMATIONW *)&a1->Reserved3[12];
    *(_QWORD *)&a1->Reserved3[12] = v76;
    *(_QWORD *)&a1->Reserved3[28] = v77;
    LODWORD(v25.Pointer) = -2147022646;
    LODWORD(v58) = -2147022646;
    if ( *(_DWORD *)v27->Reserved2 != 4 )
    {
      v49 = CSmartPublicBinding::operator void *(v64);
      Pointer = 0;
      LODWORD(v57.Pointer) = 0;
      Pointer = (struct _WINSTATIONINFORMATIONW *)NdrClientCall3(
                                                    (MIDL_STUBLESS_PROXY_INFO *)&stru_180032080,
                                                    3u,
                                                    0,
                                                    v49,
                                                    v57.Simple,
                                                    &hMem,
                                                    (char *)&v58 + 4,
                                                    &a1->Reserved3[20],
                                                    v58).Pointer;
      LODWORD(v25.Pointer) = (_DWORD)Pointer;
    }
    if ( LODWORD(v25.Pointer) == -2147022646
      || LODWORD(v25.Pointer) == -2147023174
      || LODWORD(v25.Pointer) == -2147467262
      || LODWORD(v25.Pointer) == -2147023179 )
    {
      memset_0(&a1->Reserved3[36], 0, 0x3F4u);
      *(_QWORD *)&a1->Reserved3[20] = *(_QWORD *)&a1->Reserved3[12];
    }
    else
    {
      if ( SLODWORD(v25.Simple) < 0 )
      {
        _DbgPrintMessage(
          8,
          "RpcGetCurrentSessionProtocolLastInputTime failed: 0x%x in %s",
          LODWORD(v25.Pointer),
          "GetCurrentSessionInformation");
        goto LABEL_64;
      }
      v54 = hMem;
      if ( !hMem )
      {
        _DbgPrintMessage(8, "RpcGetCurrentSessionProtocolLastInputTime returned NULL pBuffStatus", v33);
        LODWORD(v25.Pointer) = -2147467261;
        goto LABEL_64;
      }
      if ( HIDWORD(v58) < 0x3F4 )
      {
        _DbgPrintMessage(
          8,
          "RpcGetCurrentSessionProtocolLastInputTime returned %d bytes, expected %d",
          HIDWORD(v58),
          1012);
        LODWORD(v25.Pointer) = -2147024809;
        goto LABEL_64;
      }
      v55 = &a1->Reserved3[36];
      v56 = 7;
      do
      {
        *(_OWORD *)v55 = *v54;
        *((_OWORD *)v55 + 1) = v54[1];
        *((_OWORD *)v55 + 2) = v54[2];
        *((_OWORD *)v55 + 3) = v54[3];
        *((_OWORD *)v55 + 4) = v54[4];
        *((_OWORD *)v55 + 5) = v54[5];
        *((_OWORD *)v55 + 6) = v54[6];
        *((_OWORD *)v55 + 7) = v54[7];
        v55 += 128;
        v54 += 8;
        --v56;
      }
      while ( v56 );
      *(_OWORD *)v55 = *v54;
      *((_OWORD *)v55 + 1) = v54[1];
      *((_OWORD *)v55 + 2) = v54[2];
      *((_OWORD *)v55 + 3) = v54[3];
      *((_OWORD *)v55 + 4) = v54[4];
      *((_OWORD *)v55 + 5) = v54[5];
      *((_OWORD *)v55 + 6) = v54[6];
      *((_DWORD *)v55 + 28) = *((_DWORD *)v54 + 28);
    }
    NtQuerySystemTime((PLARGE_INTEGER)&a1->Reserved3[1132]);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, hObject) )
      goto LABEL_76;
    if ( GetLastError() == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, hObject) )
      {
LABEL_76:
        UserSessionId = CUtils::GetUserSessionId(hObject[0], (int *)&a1->LogonId);
        LODWORD(v25.Pointer) = UserSessionId;
        if ( UserSessionId < 0 )
        {
          _DbgPrintMessage(
            8,
            "CUtils::GetUserSessionId() failed: 0x%x in %s",
            (unsigned int)UserSessionId,
            "GetCurrentSessionInformation");
        }
        else
        {
          *v68 = 1216;
          LODWORD(v25.Pointer) = 0;
        }
        goto LABEL_64;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v25.Pointer) = LastError;
      _DbgPrintMessage(8, "OpenProcessToken failed: 0x%x", LastError);
    }
    else
    {
      v53 = GetLastError();
      if ( v53 > 0 )
        v53 = (unsigned __int16)v53 | 0x80070000;
      LODWORD(v25.Pointer) = v53;
      _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x", v53);
    }
  }
  else
  {
    v52 = GetLastError();
    LODWORD(v25.Pointer) = v52;
    if ( v52 > 0 )
      LODWORD(v25.Pointer) = (unsigned __int16)v52 | 0x80070000;
  }
LABEL_64:
  if ( hMem )
    LocalFree(hMem);
  if ( v78 )
    LocalFree(v78);
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v64);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v66);
  return LODWORD(v25.Pointer);
}

```

## disassembly

```asm
0x180009da0  mov     [rsp+arg_8], rbx
0x180009da5  mov     [rsp+arg_18], rsi
0x180009daa  push    rdi
0x180009dab  push    r12
0x180009dad  push    r13
0x180009daf  push    r14
0x180009db1  push    r15
0x180009db3  sub     rsp, 190h
0x180009dba  mov     rax, cs:__security_cookie
0x180009dc1  xor     rax, rsp
0x180009dc4  mov     [rsp+1B8h+var_38], rax
0x180009dcc  mov     r12d, edx
0x180009dcf  mov     [rsp+1B8h+var_148], rcx
0x180009dd4  mov     [rsp+1B8h+var_170], rcx
0x180009dd9  mov     r13, rcx
0x180009ddc  mov     [rsp+1B8h+var_168], rcx
0x180009de1  mov     [rsp+1B8h+var_120], r8
0x180009de9  xor     edi, edi
0x180009deb  mov     qword ptr [rsp+1B8h+var_130], rdi
0x180009df3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009dfa  mov     ecx, 40h ; '@'; unsigned __int64
0x180009dff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009e04  mov     rbx, rax
0x180009e07  test    rax, rax
0x180009e0a  jz      loc_18000A5D9
0x180009e10  mov     [rax], rdi
0x180009e13  mov     [rax+8], rdi
0x180009e17  mov     [rax+10h], rdi
0x180009e1b  mov     [rax+18h], rdi
0x180009e1f  mov     [rax+20h], rdi
0x180009e23  mov     [rax+28h], rdi
0x180009e27  mov     qword ptr [rax+30h], 1
0x180009e2f  mov     [rax+38h], rdi
0x180009e33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009e3a  mov     ecx, 2; unsigned __int64
0x180009e3f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009e44  mov     r9, rax
0x180009e47  mov     [rbx+28h], rax
0x180009e4b  mov     r14d, 7FFFFFFEh
0x180009e51  lea     r15, dword_18003D0CC
0x180009e58  test    rax, rax
0x180009e5b  jz      short loc_180009EBD
0x180009e5d  mov     ecx, r14d
0x180009e60  mov     rdx, r15
0x180009e63  mov     r10d, 1
0x180009e69  nop     dword ptr [rax+00000000h]
0x180009e70  test    rcx, rcx
0x180009e73  jz      short loc_180009E92
0x180009e75  movzx   eax, word ptr [rdx]
0x180009e78  test    ax, ax
0x180009e7b  jz      short loc_180009E92
0x180009e7d  add     rdx, 2
0x180009e81  mov     [r9], ax
0x180009e85  add     r9, 2
0x180009e89  dec     rcx
0x180009e8c  sub     r10, 1
0x180009e90  jnz     short loc_180009E70
0x180009e92  mov     esi, 8007007Ah
0x180009e97  test    r10, r10
0x180009e9a  cmovnz  esi, edi
0x180009e9d  lea     rax, [r9-2]
0x180009ea1  cmovnz  rax, r9
0x180009ea5  mov     [rax], di
0x180009ea8  jz      loc_18000A4F7
0x180009eae  cmp     [rbx+18h], rdi
0x180009eb2  jnz     short loc_180009EBD
0x180009eb4  cmp     [rbx+30h], edi
0x180009eb7  jz      loc_18000A537
0x180009ebd  mov     esi, 8007007Ah
0x180009ec2  mov     [rsp+1B8h+var_128], rbx
0x180009eca  test    rbx, rbx
0x180009ecd  jz      loc_18000A5EE
0x180009ed3  mov     dword ptr [rsp+1B8h+var_130+4], 1
0x180009ede  mov     qword ptr [rsp+1B8h+var_140], 1
0x180009ee7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009eee  mov     ecx, 40h ; '@'; unsigned __int64
0x180009ef3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009ef8  mov     rbx, rax
0x180009efb  test    rax, rax
0x180009efe  jz      loc_18000A61B
0x180009f04  mov     [rax], rdi
0x180009f07  mov     [rax+8], rdi
0x180009f0b  mov     [rax+10h], rdi
0x180009f0f  mov     [rax+18h], rdi
0x180009f13  mov     [rax+20h], rdi
0x180009f17  mov     [rax+28h], rdi
0x180009f1b  mov     qword ptr [rax+30h], 1
0x180009f23  mov     [rax+38h], rdi
0x180009f27  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009f2e  mov     ecx, 2; unsigned __int64
0x180009f33  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009f38  mov     r9, rax
0x180009f3b  mov     [rbx+28h], rax
0x180009f3f  test    rax, rax
0x180009f42  jz      short loc_180009F99
0x180009f44  mov     rcx, r14
0x180009f47  mov     r10d, 1
0x180009f4d  nop     dword ptr [rax]
0x180009f50  test    rcx, rcx
0x180009f53  jz      short loc_180009F73
0x180009f55  movzx   eax, word ptr [r15]
0x180009f59  test    ax, ax
0x180009f5c  jz      short loc_180009F73
0x180009f5e  add     r15, 2
0x180009f62  mov     [r9], ax
0x180009f66  add     r9, 2
0x180009f6a  dec     rcx
0x180009f6d  sub     r10, 1
0x180009f71  jnz     short loc_180009F50
0x180009f73  test    r10, r10
0x180009f76  cmovnz  esi, edi
0x180009f79  lea     rax, [r9-2]
0x180009f7d  cmovnz  rax, r9
0x180009f81  mov     [rax], di
0x180009f84  jz      loc_18000A517
0x180009f8a  cmp     [rbx+18h], rdi
0x180009f8e  jnz     short loc_180009F99
0x180009f90  cmp     [rbx+30h], edi
0x180009f93  jz      loc_18000A557
0x180009f99  mov     [rsp+1B8h+var_138], rbx
0x180009fa1  test    rbx, rbx
0x180009fa4  jz      loc_18000A623
0x180009faa  mov     dword ptr [rsp+1B8h+var_140+4], 1
0x180009fb2  xor     edx, edx; Val
0x180009fb4  mov     r8d, 0D0h; Size
0x180009fba  lea     rcx, [rsp+1B8h+var_108]; void *
0x180009fc2  call    memset_0
0x180009fc7  mov     [rsp+1B8h+hMem], rdi
0x180009fcc  mov     [rsp+1B8h+var_174], edi
0x180009fd0  mov     [rsp+1B8h+hObject], rdi
0x180009fd5  mov     rax, [rsp+1B8h+var_120]
0x180009fdd  mov     [rax], edi
0x180009fdf  cmp     r12d, 4C0h
0x180009fe6  jb      loc_18000A644
0x180009fec  xor     edx, edx; Val
0x180009fee  mov     r8d, 4C0h; Size
0x180009ff4  mov     rcx, r13; void *
0x180009ff7  call    memset_0
0x180009ffc  lea     rcx, [rsp+1B8h+var_130]; unsigned __int16 *
0x18000a004  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000a009  test    rax, rax
0x18000a00c  jz      loc_18000A582
0x18000a012  mov     [rsp+1B8h+var_178], 80004001h
0x18000a01a  lea     rcx, [rsp+1B8h+var_140]; unsigned __int16 *
0x18000a01f  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000a024  test    rax, rax
0x18000a027  jz      loc_18000A582
0x18000a02d  lea     rcx, [rsp+1B8h+var_130]; unsigned __int16 *
0x18000a035  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000a03a  mov     [rsp+1B8h+var_118], rdi
0x18000a042  lea     rcx, [rsp+1B8h+var_108]
0x18000a04a  mov     [rsp+1B8h+var_190], rcx
0x18000a04f  mov     dword ptr [rsp+1B8h+var_198], 1
0x18000a057  mov     r9, rax
0x18000a05a  xor     r8d, r8d; pReturnValue
0x18000a05d  mov     edx, 2; nProcNum
0x18000a062  lea     rcx, stru_180032230; pProxyInfo
0x18000a069  call    cs:__imp_NdrClientCall3
0x18000a06f  mov     rbx, rax
0x18000a072  mov     [rsp+1B8h+var_118], rax
0x18000a07a  mov     [rsp+1B8h+var_178], eax
0x18000a07e  mov     r11d, 8007007Ah
0x18000a084  mov     r15, [rsp+1B8h+var_148]
0x18000a089  jmp     short loc_18000A0E0
0x18000a08b  mov     ebx, eax
0x18000a08d  call    cs:__imp__resetstkoflw
0x18000a093  test    eax, eax
0x18000a095  jz      short loc_18000A0B6
0x18000a097  mov     ebx, 800703E9h
0x18000a09c  mov     [rsp+1B8h+var_178], ebx
0x18000a0a0  mov     r8d, ebx
0x18000a0a3  lea     rdx, aStackOverflowO; "Stack Overflow occured at RpcGetCurrent"...
0x18000a0aa  mov     ecx, 8; int
0x18000a0af  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a0b4  jmp     short loc_18000A0CA
0x18000a0b6  mov     ecx, ebx; dwExceptionCode
0x18000a0b8  xor     r9d, r9d; lpArguments
0x18000a0bb  xor     r8d, r8d; nNumberOfArguments
0x18000a0be  xor     edx, edx; dwExceptionFlags
0x18000a0c0  call    cs:__imp_RaiseException
0x18000a0c6  mov     ebx, [rsp+1B8h+var_178]
0x18000a0ca  xor     edi, edi
0x18000a0cc  mov     r14d, 7FFFFFFEh
0x18000a0d2  mov     r11d, 8007007Ah
0x18000a0d8  mov     r15, [rsp+1B8h+var_170]
0x18000a0dd  mov     r13, r15
0x18000a0e0  jmp     short loc_18000A11E
0x18000a0e2  test    eax, eax
0x18000a0e4  jle     short loc_18000A0EE
0x18000a0e6  movzx   eax, ax
0x18000a0e9  or      eax, 80070000h
0x18000a0ee  mov     ebx, eax
0x18000a0f0  mov     [rsp+1B8h+var_178], eax
0x18000a0f4  mov     r8d, eax
0x18000a0f7  lea     rdx, aRpcgetcurrents_10; "RpcGetCurrentSessionInformation threw a"...
0x18000a0fe  mov     ecx, 8; int
0x18000a103  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a108  xor     edi, edi
0x18000a10a  mov     r14d, 7FFFFFFEh
0x18000a110  mov     r11d, 8007007Ah
0x18000a116  mov     r15, [rsp+1B8h+var_170]
0x18000a11b  mov     r13, r15
0x18000a11e  test    ebx, ebx
0x18000a120  js      loc_18000A64E
0x18000a126  mov     rcx, r14
0x18000a129  lea     rdx, [rsp+1B8h+var_92]
0x18000a131  mov     r9d, 15h
0x18000a137  lea     r10, [r13+488h]
0x18000a13e  xchg    ax, ax
0x18000a140  test    rcx, rcx
0x18000a143  jz      short loc_18000A162
0x18000a145  movzx   eax, word ptr [rdx]
0x18000a148  test    ax, ax
0x18000a14b  jz      short loc_18000A162
0x18000a14d  add     rdx, 2
0x18000a151  mov     [r10], ax
0x18000a155  add     r10, 2
0x18000a159  dec     rcx
0x18000a15c  sub     r9, 1
0x18000a160  jnz     short loc_18000A140
0x18000a162  mov     r8d, r11d
0x18000a165  test    r9, r9
0x18000a168  cmovnz  r8d, edi
0x18000a16c  lea     rax, [r10-2]
0x18000a170  cmovnz  rax, r10
0x18000a174  mov     [rax], di
0x18000a177  jz      loc_18000A66E
0x18000a17d  mov     rcx, r14
0x18000a180  lea     rdx, [rsp+1B8h+var_B6]
0x18000a188  mov     r9d, 12h
0x18000a18e  lea     r10, [r13+464h]
0x18000a195  test    rcx, rcx
0x18000a198  jz      short loc_18000A1B7
0x18000a19a  movzx   eax, word ptr [rdx]
0x18000a19d  test    ax, ax
0x18000a1a0  jz      short loc_18000A1B7
0x18000a1a2  add     rdx, 2
0x18000a1a6  mov     [r10], ax
0x18000a1aa  add     r10, 2
0x18000a1ae  dec     rcx
0x18000a1b1  sub     r9, 1
0x18000a1b5  jnz     short loc_18000A195
0x18000a1b7  mov     r8d, r11d
0x18000a1ba  test    r9, r9
0x18000a1bd  cmovnz  r8d, edi
0x18000a1c1  lea     rax, [r10-2]
0x18000a1c5  cmovnz  rax, r10
0x18000a1c9  mov     [rax], di
0x18000a1cc  jz      loc_18000A66E
0x18000a1d2  mov     eax, [rsp+1B8h+var_100]
0x18000a1d9  mov     [r15], eax
0x18000a1dc  lea     rcx, [rsp+1B8h+var_F8]
0x18000a1e4  mov     edx, 21h ; '!'
0x18000a1e9  lea     r9, [r13+4]
0x18000a1ed  nop     dword ptr [rax]
0x18000a1f0  test    r14, r14
0x18000a1f3  jz      short loc_18000A212
0x18000a1f5  movzx   eax, word ptr [rcx]
0x18000a1f8  test    ax, ax
0x18000a1fb  jz      short loc_18000A212
0x18000a1fd  add     rcx, 2
0x18000a201  mov     [r9], ax
0x18000a205  add     r9, 2
0x18000a209  dec     r14
0x18000a20c  sub     rdx, 1
0x18000a210  jnz     short loc_18000A1F0
0x18000a212  test    rdx, rdx
0x18000a215  cmovnz  r11d, edi
0x18000a219  lea     rax, [r9-2]
0x18000a21d  cmovnz  rax, r9
0x18000a221  mov     [rax], di
0x18000a224  jnz     loc_18000A2BD
0x18000a22a  mov     ebx, r11d
0x18000a22d  mov     r8d, r11d
0x18000a230  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x18000a237  lea     r9, aGetcurrentsess_2; "GetCurrentSessionInformation"
0x18000a23e  mov     ecx, 8; int
0x18000a243  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a248  mov     rcx, [rsp+1B8h+hMem]; hMem
0x18000a24d  test    rcx, rcx
0x18000a250  jnz     loc_18000A577
0x18000a256  mov     rcx, [rsp+1B8h+var_40]; hMem
0x18000a25e  test    rcx, rcx
0x18000a261  jnz     loc_18000A775
0x18000a267  mov     rcx, [rsp+1B8h+hObject]; hObject
0x18000a26c  test    rcx, rcx
0x18000a26f  jz      short loc_18000A277
0x18000a271  call    cs:__imp_CloseHandle
0x18000a277  lea     rcx, [rsp+1B8h+var_140]; this
0x18000a27c  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000a281  lea     rcx, [rsp+1B8h+var_130]; this
0x18000a289  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000a28e  mov     eax, ebx
0x18000a290  mov     rcx, [rsp+1B8h+var_38]
0x18000a298  xor     rcx, rsp; StackCookie
0x18000a29b  call    __security_check_cookie
0x18000a2a0  lea     r11, [rsp+1B8h+var_28]
0x18000a2a8  mov     rbx, [r11+38h]
0x18000a2ac  mov     rsi, [r11+48h]
0x18000a2b0  mov     rsp, r11
  ... truncated ...
```
