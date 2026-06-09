# GetCurrentSessionInformation(_WINSTATIONINFORMATIONW *,ulong,ulong *)

- ea: `0x180008640`
- end: `0x180009097`
- name: `?GetCurrentSessionInformation@@YAJPEAU_WINSTATIONINFORMATIONW@@KPEAK@Z`
- size: `2647`
- prototype: `__int64 __fastcall(struct _WINSTATIONINFORMATIONW *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800095b0`
- `0x1800096c0`

## callees

- `0x1800032b4`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800066d0`
- `0x1800075a0`
- `0x180008640`
- `0x18000a28c`
- `0x1800249e8`
- `0x180024a1c`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180008933`
- `msvcrt!_resetstkoflw` at `0x180008ca7`
- `msvcrt!_resetstkoflw` at `0x180008933`
- `msvcrt!_resetstkoflw` at `0x180008ca7`
- `ntdll!NtQuerySystemTime` at `0x180008bde`
- `ntdll!NtQuerySystemTime` at `0x180008bde`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000896c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ce0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000896c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ce0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009086`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009086`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008d4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008d4f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008c09`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008c09`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180008d68`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180008d68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008bea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b21`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800331c2`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033208`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800331c2`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033208`
- `RPCRT4!NdrClientCall3` at `0x180008909`
- `RPCRT4!NdrClientCall3` at `0x180008c8c`
- `RPCRT4!NdrClientCall3` at `0x180008909`
- `RPCRT4!NdrClientCall3` at `0x180008c8c`

## string_xrefs

- `0x180008df4`: `StringCchCopy failed: %x`
- `0x180008e14`: `StringCchCopy failed: %x`
- `0x180008ae0`: `StringCchCopy failed: 0x%x in %s`
- `0x180008d99`: `OpenProcessToken failed: 0x%x`
- `0x180008ebc`: `OpenThreadToken failed: 0x%x`
- `0x180008d16`: `RpcGetSessionProtocolLastInputTime failed: 0x%x`
- `0x180008cc3`: `Stack Overflow occured at RpcGetCurrentSessionProtocolLastInputTime(): 0x%x`
- `0x180008dde`: `RpcGetCurrentSessionProtocolLastInputTime failed: 0x%x in %s`
- `0x180008f91`: `RpcGetCurrentSessionProtocolLastInputTime returned NULL pBuffStatus`
- `0x180008fc0`: `RpcGetCurrentSessionProtocolLastInputTime returned %d bytes, expected %d`

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
    v9 = &dword_18003FF34;
    if ( v7 )
    {
      v10 = 2147483646;
      v11 = &dword_18003FF34;
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
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((CPublicBinding *)v6) == -2147023174 )
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
    v9 = &dword_18003FF34;
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
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((CPublicBinding *)v18) == -2147023174 )
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
    v25.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035230, 2u, 0, v24, 1, v70).Pointer;
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
                                                    (MIDL_STUBLESS_PROXY_INFO *)&stru_180035018,
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
0x180008640  mov     [rsp+arg_8], rbx
0x180008645  mov     [rsp+arg_18], rsi
0x18000864a  push    rdi
0x18000864b  push    r12
0x18000864d  push    r13
0x18000864f  push    r14
0x180008651  push    r15
0x180008653  sub     rsp, 190h
0x18000865a  mov     rax, cs:__security_cookie
0x180008661  xor     rax, rsp
0x180008664  mov     [rsp+1B8h+var_38], rax
0x18000866c  mov     r12d, edx
0x18000866f  mov     [rsp+1B8h+var_148], rcx
0x180008674  mov     [rsp+1B8h+var_170], rcx
0x180008679  mov     r13, rcx
0x18000867c  mov     [rsp+1B8h+var_168], rcx
0x180008681  mov     [rsp+1B8h+var_120], r8
0x180008689  xor     edi, edi
0x18000868b  mov     qword ptr [rsp+1B8h+var_130], rdi
0x180008693  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000869a  mov     ecx, 40h ; '@'; unsigned __int64
0x18000869f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800086a4  mov     rbx, rax
0x1800086a7  test    rax, rax
0x1800086aa  jz      loc_180008EDE
0x1800086b0  mov     [rax], rdi
0x1800086b3  mov     [rax+8], rdi
0x1800086b7  mov     [rax+10h], rdi
0x1800086bb  mov     [rax+18h], rdi
0x1800086bf  mov     [rax+20h], rdi
0x1800086c3  mov     [rax+28h], rdi
0x1800086c7  mov     qword ptr [rax+30h], 1
0x1800086cf  mov     [rax+38h], rdi
0x1800086d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800086da  mov     ecx, 2; unsigned __int64
0x1800086df  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800086e4  mov     r9, rax
0x1800086e7  mov     [rbx+28h], rax
0x1800086eb  mov     r14d, 7FFFFFFEh
0x1800086f1  lea     r15, dword_18003FF34
0x1800086f8  test    rax, rax
0x1800086fb  jz      short loc_18000875D
0x1800086fd  mov     ecx, r14d
0x180008700  mov     rdx, r15
0x180008703  mov     r10d, 1
0x180008709  nop     dword ptr [rax+00000000h]
0x180008710  test    rcx, rcx
0x180008713  jz      short loc_180008732
0x180008715  movzx   eax, word ptr [rdx]
0x180008718  test    ax, ax
0x18000871b  jz      short loc_180008732
0x18000871d  add     rdx, 2
0x180008721  mov     [r9], ax
0x180008725  add     r9, 2
0x180008729  dec     rcx
0x18000872c  sub     r10, 1
0x180008730  jnz     short loc_180008710
0x180008732  mov     esi, 8007007Ah
0x180008737  test    r10, r10
0x18000873a  cmovnz  esi, edi
0x18000873d  lea     rax, [r9-2]
0x180008741  cmovnz  rax, r9
0x180008745  mov     [rax], di
0x180008748  jz      loc_180008DEA
0x18000874e  cmp     [rbx+18h], rdi
0x180008752  jnz     short loc_18000875D
0x180008754  cmp     [rbx+30h], edi
0x180008757  jz      loc_180008E2A
0x18000875d  mov     esi, 8007007Ah
0x180008762  mov     [rsp+1B8h+var_128], rbx
0x18000876a  test    rbx, rbx
0x18000876d  jz      loc_180008EF3
0x180008773  mov     dword ptr [rsp+1B8h+var_130+4], 1
0x18000877e  mov     qword ptr [rsp+1B8h+var_140], 1
0x180008787  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000878e  mov     ecx, 40h ; '@'; unsigned __int64
0x180008793  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008798  mov     rbx, rax
0x18000879b  test    rax, rax
0x18000879e  jz      loc_180008F26
0x1800087a4  mov     [rax], rdi
0x1800087a7  mov     [rax+8], rdi
0x1800087ab  mov     [rax+10h], rdi
0x1800087af  mov     [rax+18h], rdi
0x1800087b3  mov     [rax+20h], rdi
0x1800087b7  mov     [rax+28h], rdi
0x1800087bb  mov     qword ptr [rax+30h], 1
0x1800087c3  mov     [rax+38h], rdi
0x1800087c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800087ce  mov     ecx, 2; unsigned __int64
0x1800087d3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800087d8  mov     r9, rax
0x1800087db  mov     [rbx+28h], rax
0x1800087df  test    rax, rax
0x1800087e2  jz      short loc_180008839
0x1800087e4  mov     rcx, r14
0x1800087e7  mov     r10d, 1
0x1800087ed  nop     dword ptr [rax]
0x1800087f0  test    rcx, rcx
0x1800087f3  jz      short loc_180008813
0x1800087f5  movzx   eax, word ptr [r15]
0x1800087f9  test    ax, ax
0x1800087fc  jz      short loc_180008813
0x1800087fe  add     r15, 2
0x180008802  mov     [r9], ax
0x180008806  add     r9, 2
0x18000880a  dec     rcx
0x18000880d  sub     r10, 1
0x180008811  jnz     short loc_1800087F0
0x180008813  test    r10, r10
0x180008816  cmovnz  esi, edi
0x180008819  lea     rax, [r9-2]
0x18000881d  cmovnz  rax, r9
0x180008821  mov     [rax], di
0x180008824  jz      loc_180008E0A
0x18000882a  cmp     [rbx+18h], rdi
0x18000882e  jnz     short loc_180008839
0x180008830  cmp     [rbx+30h], edi
0x180008833  jz      loc_180008E4A
0x180008839  mov     [rsp+1B8h+var_138], rbx
0x180008841  test    rbx, rbx
0x180008844  jz      loc_180008F2E
0x18000884a  mov     dword ptr [rsp+1B8h+var_140+4], 1
0x180008852  xor     edx, edx; Val
0x180008854  mov     r8d, 0D0h; Size
0x18000885a  lea     rcx, [rsp+1B8h+var_108]; void *
0x180008862  call    memset_0
0x180008867  mov     [rsp+1B8h+hMem], rdi
0x18000886c  mov     [rsp+1B8h+var_174], edi
0x180008870  mov     [rsp+1B8h+hObject], rdi
0x180008875  mov     rax, [rsp+1B8h+var_120]
0x18000887d  mov     [rax], edi
0x18000887f  cmp     r12d, 4C0h
0x180008886  jb      loc_180008F55
0x18000888c  xor     edx, edx; Val
0x18000888e  mov     r8d, 4C0h; Size
0x180008894  mov     rcx, r13; void *
0x180008897  call    memset_0
0x18000889c  lea     rcx, [rsp+1B8h+var_130]; unsigned __int16 *
0x1800088a4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800088a9  test    rax, rax
0x1800088ac  jz      loc_180008E7B
0x1800088b2  mov     [rsp+1B8h+var_178], 80004001h
0x1800088ba  lea     rcx, [rsp+1B8h+var_140]; unsigned __int16 *
0x1800088bf  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800088c4  test    rax, rax
0x1800088c7  jz      loc_180008E7B
0x1800088cd  lea     rcx, [rsp+1B8h+var_130]; unsigned __int16 *
0x1800088d5  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800088da  mov     [rsp+1B8h+var_118], rdi
0x1800088e2  lea     rcx, [rsp+1B8h+var_108]
0x1800088ea  mov     [rsp+1B8h+var_190], rcx
0x1800088ef  mov     dword ptr [rsp+1B8h+var_198], 1
0x1800088f7  mov     r9, rax
0x1800088fa  xor     r8d, r8d; pReturnValue
0x1800088fd  mov     edx, 2; nProcNum
0x180008902  lea     rcx, stru_180035230; pProxyInfo
0x180008909  call    cs:__imp_NdrClientCall3
0x180008910  nop     dword ptr [rax+rax+00h]
0x180008915  mov     rbx, rax
0x180008918  mov     [rsp+1B8h+var_118], rax
0x180008920  mov     [rsp+1B8h+var_178], eax
0x180008924  mov     r11d, 8007007Ah
0x18000892a  mov     r15, [rsp+1B8h+var_148]
0x18000892f  jmp     short loc_180008992
0x180008931  mov     ebx, eax
0x180008933  call    cs:__imp__resetstkoflw
0x18000893a  nop     dword ptr [rax+rax+00h]
0x18000893f  test    eax, eax
0x180008941  jz      short loc_180008962
0x180008943  mov     ebx, 800703E9h
0x180008948  mov     [rsp+1B8h+var_178], ebx
0x18000894c  mov     r8d, ebx
0x18000894f  lea     rdx, aStackOverflowO; "Stack Overflow occured at RpcGetCurrent"...
0x180008956  mov     ecx, 8; int
0x18000895b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008960  jmp     short loc_18000897C
0x180008962  mov     ecx, ebx; dwExceptionCode
0x180008964  xor     r9d, r9d; lpArguments
0x180008967  xor     r8d, r8d; nNumberOfArguments
0x18000896a  xor     edx, edx; dwExceptionFlags
0x18000896c  call    cs:__imp_RaiseException
0x180008973  nop     dword ptr [rax+rax+00h]
0x180008978  mov     ebx, [rsp+1B8h+var_178]
0x18000897c  xor     edi, edi
0x18000897e  mov     r14d, 7FFFFFFEh
0x180008984  mov     r11d, 8007007Ah
0x18000898a  mov     r15, [rsp+1B8h+var_170]
0x18000898f  mov     r13, r15
0x180008992  jmp     short loc_1800089D0
0x180008994  test    eax, eax
0x180008996  jle     short loc_1800089A0
0x180008998  movzx   eax, ax
0x18000899b  or      eax, 80070000h
0x1800089a0  mov     ebx, eax
0x1800089a2  mov     [rsp+1B8h+var_178], eax
0x1800089a6  mov     r8d, eax
0x1800089a9  lea     rdx, aRpcgetcurrents_10; "RpcGetCurrentSessionInformation threw a"...
0x1800089b0  mov     ecx, 8; int
0x1800089b5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800089ba  xor     edi, edi
0x1800089bc  mov     r14d, 7FFFFFFEh
0x1800089c2  mov     r11d, 8007007Ah
0x1800089c8  mov     r15, [rsp+1B8h+var_170]
0x1800089cd  mov     r13, r15
0x1800089d0  test    ebx, ebx
0x1800089d2  js      loc_180008F5F
0x1800089d8  mov     rcx, r14
0x1800089db  lea     rdx, [rsp+1B8h+var_92]
0x1800089e3  mov     r9d, 15h
0x1800089e9  lea     r10, [r13+488h]
0x1800089f0  test    rcx, rcx
0x1800089f3  jz      short loc_180008A12
0x1800089f5  movzx   eax, word ptr [rdx]
0x1800089f8  test    ax, ax
0x1800089fb  jz      short loc_180008A12
0x1800089fd  add     rdx, 2
0x180008a01  mov     [r10], ax
0x180008a05  add     r10, 2
0x180008a09  dec     rcx
0x180008a0c  sub     r9, 1
0x180008a10  jnz     short loc_1800089F0
0x180008a12  mov     r8d, r11d
0x180008a15  test    r9, r9
0x180008a18  cmovnz  r8d, edi
0x180008a1c  lea     rax, [r10-2]
0x180008a20  cmovnz  rax, r10
0x180008a24  mov     [rax], di
0x180008a27  jz      loc_180008F7F
0x180008a2d  mov     rcx, r14
0x180008a30  lea     rdx, [rsp+1B8h+var_B6]
0x180008a38  mov     r9d, 12h
0x180008a3e  lea     r10, [r13+464h]
0x180008a45  test    rcx, rcx
0x180008a48  jz      short loc_180008A67
0x180008a4a  movzx   eax, word ptr [rdx]
0x180008a4d  test    ax, ax
0x180008a50  jz      short loc_180008A67
0x180008a52  add     rdx, 2
0x180008a56  mov     [r10], ax
0x180008a5a  add     r10, 2
0x180008a5e  dec     rcx
0x180008a61  sub     r9, 1
0x180008a65  jnz     short loc_180008A45
0x180008a67  mov     r8d, r11d
0x180008a6a  test    r9, r9
0x180008a6d  cmovnz  r8d, edi
0x180008a71  lea     rax, [r10-2]
0x180008a75  cmovnz  rax, r10
0x180008a79  mov     [rax], di
0x180008a7c  jz      loc_180008F7F
0x180008a82  mov     eax, [rsp+1B8h+var_100]
0x180008a89  mov     [r15], eax
0x180008a8c  lea     rcx, [rsp+1B8h+var_F8]
0x180008a94  mov     edx, 21h ; '!'
0x180008a99  lea     r9, [r13+4]
0x180008a9d  nop     dword ptr [rax]
0x180008aa0  test    r14, r14
0x180008aa3  jz      short loc_180008AC2
0x180008aa5  movzx   eax, word ptr [rcx]
0x180008aa8  test    ax, ax
0x180008aab  jz      short loc_180008AC2
0x180008aad  add     rcx, 2
0x180008ab1  mov     [r9], ax
0x180008ab5  add     r9, 2
0x180008ab9  dec     r14
0x180008abc  sub     rdx, 1
0x180008ac0  jnz     short loc_180008AA0
0x180008ac2  test    rdx, rdx
0x180008ac5  cmovnz  r11d, edi
0x180008ac9  lea     rax, [r9-2]
0x180008acd  cmovnz  rax, r9
0x180008ad1  mov     [rax], di
0x180008ad4  jnz     loc_180008B74
0x180008ada  mov     ebx, r11d
0x180008add  mov     r8d, r11d
0x180008ae0  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x180008ae7  lea     r9, aGetcurrentsess_2; "GetCurrentSessionInformation"
0x180008aee  mov     ecx, 8; int
0x180008af3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008af8  mov     rcx, [rsp+1B8h+hMem]; hMem
0x180008afd  test    rcx, rcx
0x180008b00  jnz     loc_180008E6A
0x180008b06  mov     rcx, [rsp+1B8h+var_40]; hMem
0x180008b0e  test    rcx, rcx
0x180008b11  jnz     loc_180009086
0x180008b17  mov     rcx, [rsp+1B8h+hObject]; hObject
0x180008b1c  test    rcx, rcx
0x180008b1f  jz      short loc_180008B2D
0x180008b21  call    cs:__imp_CloseHandle
0x180008b28  nop     dword ptr [rax+rax+00h]
0x180008b2d  lea     rcx, [rsp+1B8h+var_140]; this
0x180008b32  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180008b37  lea     rcx, [rsp+1B8h+var_130]; this
0x180008b3f  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180008b44  mov     eax, ebx
0x180008b46  mov     rcx, [rsp+1B8h+var_38]
0x180008b4e  xor     rcx, rsp; StackCookie
0x180008b51  call    __security_check_cookie
0x180008b56  lea     r11, [rsp+1B8h+var_28]
  ... truncated ...
```
