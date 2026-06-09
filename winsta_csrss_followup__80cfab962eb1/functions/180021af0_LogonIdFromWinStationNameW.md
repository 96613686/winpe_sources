# LogonIdFromWinStationNameW

- ea: `0x180021af0`
- end: `0x180021e30`
- name: `LogonIdFromWinStationNameW`
- size: `832`
- prototype: `__int64 __fastcall(CPublicBinding *this, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x1800083fc`
- `0x180008494`
- `0x180008508`
- `0x18000eaf0`
- `0x180021af0`
- `0x18002e008`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180021c43`
- `msvcrt!_wcsicmp` at `0x180021d4b`
- `msvcrt!_wcsicmp` at `0x180021c43`
- `msvcrt!_wcsicmp` at `0x180021d4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021bce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021dbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021de9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021bce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021dbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021dff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021dff`

## string_xrefs

- `0x180021b48`: `Failed to open binding`
- `0x180021baa`: `Enum->Open failed: 0x%x in %s`

## pseudocode

```c
char __fastcall LogonIdFromWinStationNameW(CPublicBinding *this, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned __int16 *v4; // rsi
  void *v6; // rax
  int EnumResult; // edi
  DWORD v8; // eax
  unsigned int i; // r15d
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r15
  DWORD v13; // eax
  unsigned int v15; // [rsp+20h] [rbp-78h] BYREF
  unsigned int v16; // [rsp+24h] [rbp-74h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-70h] BYREF
  int v18; // [rsp+30h] [rbp-68h]
  HLOCAL v19; // [rsp+38h] [rbp-60h] BYREF
  int v20; // [rsp+40h] [rbp-58h]
  __int64 v21; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int16 v22[8]; // [rsp+50h] [rbp-48h] BYREF
  unsigned __int16 v23[28]; // [rsp+60h] [rbp-38h] BYREF
  int v25; // [rsp+B8h] [rbp+20h]

  v4 = a2;
  v19 = 0;
  v15 = 0;
  v21 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v23, this, 0);
  if ( !CSmartPublicBinding::operator void *(v23) )
  {
    LOBYTE(v4) = 0;
    _DbgPrintMessage(8, "Failed to open binding");
    goto LABEL_30;
  }
  v6 = (void *)CSmartPublicBinding::operator void *(v23);
  EnumResult = CEnum::Open((CEnum *)&v21, v6);
  if ( EnumResult == -2147023174 )
  {
    LOBYTE(v4) = Legacy_LogonIdFromWinStationNameW(this, v4, a3);
    if ( !(_BYTE)v4 )
      GetLastError();
    goto LABEL_30;
  }
  if ( EnumResult < 0 )
  {
    _DbgPrintMessage(8, "Enum->Open failed: 0x%x in %s", (unsigned int)EnumResult, "LogonIdFromWinStationNameW");
LABEL_8:
    v8 = ConvertHRESULT2WIN32(EnumResult);
    SetLastError(v8);
    LOBYTE(v4) = 0;
    goto LABEL_30;
  }
  EnumResult = CEnum::GetEnumResult((CEnum *)&v21, 1u, (struct _SESSIONENUM **)&v19, &v15);
  v25 = EnumResult;
  if ( EnumResult < 0 )
  {
    _DbgPrintMessage(8, "GetEnumResult failed: 0x%x in %s", (unsigned int)EnumResult, "LogonIdFromWinStationNameW");
    goto LABEL_8;
  }
  LODWORD(v4) = 0;
  v18 = 0;
  for ( i = 0; i < v15; ++i )
  {
    hMem = (HLOCAL)(104LL * i);
    if ( !_wcsicmp(a2, (const wchar_t *)((char *)v19 + (_QWORD)hMem + 12)) )
    {
      LODWORD(v4) = 1;
      v18 = 1;
      *a3 = *(_DWORD *)((char *)v19 + (_QWORD)hMem + 4);
    }
  }
  if ( !(_DWORD)v4 )
  {
    CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v22, this, 1);
    hMem = 0;
    v16 = 0;
    if ( CSmartPublicBinding::operator void *(v22) )
    {
      v10 = CSmartPublicBinding::operator void *(v22);
      EnumResult = RpcGetAllListeners(v10, &hMem, v11, &v16);
      v25 = EnumResult;
      v20 = EnumResult;
    }
    if ( EnumResult >= 0 )
    {
      v12 = 0;
      if ( v16 )
      {
        do
        {
          if ( !_wcsicmp(a2, (const wchar_t *)hMem + 40 * v12 + 6) )
          {
            LODWORD(v4) = 1;
            *a3 = *((_DWORD *)hMem + 20 * v12 + 1);
          }
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (unsigned int)v12 < v16 );
        EnumResult = v25;
      }
    }
    if ( hMem )
      LocalFree(hMem);
    if ( EnumResult >= 0 )
    {
      CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v22);
      if ( !(_DWORD)v4 )
        SetLastError(0x1B6Eu);
    }
    else
    {
      _DbgPrintMessage(8, "RpcGetAllListeners failed: 0x%x in %s", EnumResult, "LogonIdFromWinStationNameW");
      v13 = ConvertHRESULT2WIN32(EnumResult);
      SetLastError(v13);
      LOBYTE(v4) = 0;
      CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v22);
    }
  }
LABEL_30:
  if ( v19 )
    LocalFree(v19);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v23);
  CEnum::~CEnum((CEnum *)&v21);
  return (char)v4;
}

```

## disassembly

```asm
0x180021af0  mov     rax, rsp
0x180021af3  mov     [rax+18h], r8
0x180021af7  mov     [rax+10h], rdx
0x180021afb  push    rsi
0x180021afc  push    rdi
0x180021afd  push    r12
0x180021aff  push    r13
0x180021b01  push    r15
0x180021b03  sub     rsp, 70h
0x180021b07  mov     r13, r8
0x180021b0a  mov     rsi, rdx
0x180021b0d  mov     r12, rcx
0x180021b10  mov     qword ptr [rax-60h], 0
0x180021b18  mov     dword ptr [rax-78h], 0
0x180021b1f  mov     qword ptr [rax-50h], 0
0x180021b27  xor     r8d, r8d; int
0x180021b2a  mov     rdx, rcx; void *
0x180021b2d  lea     rcx, [rax-38h]; this
0x180021b31  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180021b36  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180021b3b  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021b40  test    rax, rax
0x180021b43  jnz     short loc_180021B5C
0x180021b45  xor     sil, sil
0x180021b48  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180021b4f  lea     ecx, [rax+8]; int
0x180021b52  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021b57  jmp     loc_180021DF5
0x180021b5c  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180021b61  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021b66  mov     rdx, rax; void *
0x180021b69  lea     rcx, [rsp+98h+var_50]; this
0x180021b6e  call    ?Open@CEnum@@QEAAJPEAX@Z; CEnum::Open(void *)
0x180021b73  mov     edi, eax
0x180021b75  cmp     eax, 800706BAh
0x180021b7a  jnz     short loc_180021BA6
0x180021b7c  mov     r8, r13; unsigned int *
0x180021b7f  mov     rdx, rsi; unsigned __int16 *
0x180021b82  mov     rcx, r12; this
0x180021b85  call    ?Legacy_LogonIdFromWinStationNameW@@YAEPEAXPEAGPEAK@Z; Legacy_LogonIdFromWinStationNameW(void *,ushort *,ulong *)
0x180021b8a  mov     sil, al
0x180021b8d  test    al, al
0x180021b8f  jnz     loc_180021DF5
0x180021b95  call    cs:__imp_GetLastError
0x180021b9c  nop     dword ptr [rax+rax+00h]
0x180021ba1  jmp     loc_180021DF5
0x180021ba6  test    edi, edi
0x180021ba8  jns     short loc_180021BE2
0x180021baa  lea     rdx, aEnumOpenFailed; "Enum->Open failed: 0x%x in %s"
0x180021bb1  mov     r8d, edi
0x180021bb4  lea     r9, aLogonidfromwin_2; "LogonIdFromWinStationNameW"
0x180021bbb  mov     ecx, 8; int
0x180021bc0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021bc5  mov     ecx, edi; int
0x180021bc7  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180021bcc  mov     ecx, eax; dwErrCode
0x180021bce  call    cs:__imp_SetLastError
0x180021bd5  nop     dword ptr [rax+rax+00h]
0x180021bda  xor     sil, sil
0x180021bdd  jmp     loc_180021DF5
0x180021be2  lea     r9, [rsp+98h+var_78]; unsigned int *
0x180021be7  lea     r8, [rsp+98h+var_60]; struct _SESSIONENUM **
0x180021bec  mov     edx, 1; unsigned int
0x180021bf1  lea     rcx, [rsp+98h+var_50]; this
0x180021bf6  call    ?GetEnumResult@CEnum@@QEAAJKPEAPEAU_SESSIONENUM@@PEAK@Z; CEnum::GetEnumResult(ulong,_SESSIONENUM * *,ulong *)
0x180021bfb  mov     edi, eax
0x180021bfd  mov     [rsp+98h+arg_18], eax
0x180021c04  test    eax, eax
0x180021c06  jns     short loc_180021C11
0x180021c08  lea     rdx, aGetenumresultF; "GetEnumResult failed: 0x%x in %s"
0x180021c0f  jmp     short loc_180021BB1
0x180021c11  xor     esi, esi
0x180021c13  mov     [rsp+98h+var_68], esi
0x180021c17  xor     r15d, r15d
0x180021c1a  cmp     [rsp+98h+var_78], esi
0x180021c1e  jbe     short loc_180021C7D
0x180021c20  mov     rdi, [rsp+98h+String1]
0x180021c28  mov     eax, r15d
0x180021c2b  imul    rcx, rax, 68h ; 'h'
0x180021c2f  mov     [rsp+98h+hMem], rcx
0x180021c34  mov     rdx, [rsp+98h+var_60]
0x180021c39  add     rdx, 0Ch
0x180021c3d  add     rdx, rcx; String2
0x180021c40  mov     rcx, rdi; String1
0x180021c43  call    cs:__imp__wcsicmp
0x180021c4a  nop     dword ptr [rax+rax+00h]
0x180021c4f  test    eax, eax
0x180021c51  jnz     short loc_180021C6C
0x180021c53  lea     esi, [rax+1]
0x180021c56  mov     [rsp+98h+var_68], esi
0x180021c5a  mov     rax, [rsp+98h+var_60]
0x180021c5f  mov     rcx, [rsp+98h+hMem]
0x180021c64  mov     ecx, [rcx+rax+4]
0x180021c68  mov     [r13+0], ecx
0x180021c6c  inc     r15d
0x180021c6f  cmp     r15d, [rsp+98h+var_78]
0x180021c74  jb      short loc_180021C28
0x180021c76  mov     edi, [rsp+98h+arg_18]
0x180021c7d  test    esi, esi
0x180021c7f  jnz     loc_180021DF5
0x180021c85  lea     r8d, [rsi+1]; int
0x180021c89  mov     rdx, r12; void *
0x180021c8c  lea     rcx, [rsp+98h+var_48]; this
0x180021c91  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180021c96  mov     [rsp+98h+hMem], 0
0x180021c9f  mov     [rsp+98h+var_74], esi
0x180021ca3  lea     rcx, [rsp+98h+var_48]; unsigned __int16 *
0x180021ca8  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021cad  test    rax, rax
0x180021cb0  jz      short loc_180021D1E
0x180021cb2  lea     rcx, [rsp+98h+var_48]; unsigned __int16 *
0x180021cb7  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021cbc  mov     rcx, rax
0x180021cbf  lea     r9, [rsp+98h+var_74]
0x180021cc4  lea     rdx, [rsp+98h+hMem]
0x180021cc9  call    RpcGetAllListeners
0x180021cce  mov     edi, eax
0x180021cd0  mov     [rsp+98h+arg_18], eax
0x180021cd7  mov     [rsp+98h+var_58], eax
0x180021cdb  jmp     short loc_180021D1E
0x180021cdd  mov     edi, eax
0x180021cdf  mov     [rsp+98h+arg_18], eax
0x180021ce6  test    eax, eax
0x180021ce8  jle     short loc_180021CFA
0x180021cea  movzx   edi, ax
0x180021ced  or      edi, 80070000h
0x180021cf3  mov     [rsp+98h+arg_18], edi
0x180021cfa  mov     [rsp+98h+var_58], edi
0x180021cfe  mov     r8d, edi
0x180021d01  lea     rdx, aRpcgetallliste_0; "RpcGetAllListeners threw an exception: "...
0x180021d08  mov     ecx, 8; int
0x180021d0d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021d12  mov     r13, [rsp+98h+arg_10]
0x180021d1a  mov     esi, [rsp+98h+var_68]
0x180021d1e  test    edi, edi
0x180021d20  js      short loc_180021D7D
0x180021d22  xor     r15d, r15d
0x180021d25  cmp     [rsp+98h+var_74], r15d
0x180021d2a  jbe     short loc_180021D7D
0x180021d2c  mov     rdi, [rsp+98h+String1]
0x180021d34  lea     r12, [r15+r15*4]
0x180021d38  shl     r12, 4
0x180021d3c  mov     rdx, [rsp+98h+hMem]
0x180021d41  add     rdx, 0Ch
0x180021d45  add     rdx, r12; String2
0x180021d48  mov     rcx, rdi; String1
0x180021d4b  call    cs:__imp__wcsicmp
0x180021d52  nop     dword ptr [rax+rax+00h]
0x180021d57  test    eax, eax
0x180021d59  jnz     short loc_180021D6C
0x180021d5b  lea     esi, [rax+1]
0x180021d5e  mov     rax, [rsp+98h+hMem]
0x180021d63  mov     ecx, [r12+rax+4]
0x180021d68  mov     [r13+0], ecx
0x180021d6c  inc     r15d
0x180021d6f  cmp     r15d, [rsp+98h+var_74]
0x180021d74  jb      short loc_180021D34
0x180021d76  mov     edi, [rsp+98h+arg_18]
0x180021d7d  mov     rcx, [rsp+98h+hMem]; hMem
0x180021d82  test    rcx, rcx
0x180021d85  jz      short loc_180021D93
0x180021d87  call    cs:__imp_LocalFree
0x180021d8e  nop     dword ptr [rax+rax+00h]
0x180021d93  test    edi, edi
0x180021d95  jns     short loc_180021DD6
0x180021d97  lea     r9, aLogonidfromwin_2; "LogonIdFromWinStationNameW"
0x180021d9e  mov     r8d, edi
0x180021da1  lea     rdx, aRpcgetallliste; "RpcGetAllListeners failed: 0x%x in %s"
0x180021da8  mov     ecx, 8; int
0x180021dad  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021db2  mov     ecx, edi; int
0x180021db4  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180021db9  mov     ecx, eax; dwErrCode
0x180021dbb  call    cs:__imp_SetLastError
0x180021dc2  nop     dword ptr [rax+rax+00h]
0x180021dc7  xor     sil, sil
0x180021dca  lea     rcx, [rsp+98h+var_48]; this
0x180021dcf  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180021dd4  jmp     short loc_180021DF5
0x180021dd6  lea     rcx, [rsp+98h+var_48]; this
0x180021ddb  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180021de0  test    esi, esi
0x180021de2  jnz     short loc_180021DF5
0x180021de4  mov     ecx, 1B6Eh; dwErrCode
0x180021de9  call    cs:__imp_SetLastError
0x180021df0  nop     dword ptr [rax+rax+00h]
0x180021df5  mov     rcx, [rsp+98h+var_60]; hMem
0x180021dfa  test    rcx, rcx
0x180021dfd  jz      short loc_180021E0B
0x180021dff  call    cs:__imp_LocalFree
0x180021e06  nop     dword ptr [rax+rax+00h]
0x180021e0b  lea     rcx, [rsp+98h+var_38]; this
0x180021e10  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180021e15  lea     rcx, [rsp+98h+var_50]; this
0x180021e1a  call    ??1CEnum@@QEAA@XZ; CEnum::~CEnum(void)
0x180021e1f  mov     al, sil
0x180021e22  add     rsp, 70h
0x180021e26  pop     r15
0x180021e28  pop     r13
0x180021e2a  pop     r12
0x180021e2c  pop     rdi
0x180021e2d  pop     rsi
0x180021e2e  retn
0x18003372f  push    rbp
0x180033731  sub     rsp, 20h
0x180033735  mov     rbp, rdx
0x180033738  mov     rcx, [rcx]
0x18003373b  mov     ecx, [rcx]; ExceptionCode
0x18003373d  call    cs:__imp_I_RpcExceptionFilter
0x180033744  nop     dword ptr [rax+rax+00h]
0x180033749  nop
0x18003374a  add     rsp, 20h
0x18003374e  pop     rbp
0x18003374f  retn
```
