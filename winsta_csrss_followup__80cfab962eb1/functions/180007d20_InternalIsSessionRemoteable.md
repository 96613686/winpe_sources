# InternalIsSessionRemoteable

- ea: `0x180007d20`
- end: `0x180007fce`
- name: `InternalIsSessionRemoteable`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180003f90`

## callees

- `0x1800032b4`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800066d0`
- `0x1800075a0`
- `0x180007d20`
- `0x180008590`
- `0x1800249e8`
- `0x180024a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f97`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800330ce`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800330ce`
- `RPCRT4!NdrClientCall3` at `0x180007e7e`
- `RPCRT4!NdrClientCall3` at `0x180007e7e`

## string_xrefs

- `0x180007ef4`: `StringCchCopy failed: %x`

## pseudocode

```c
__int64 __fastcall InternalIsSessionRemoteable(__int64 a1, ULONG SessionId, _BYTE *a3)
{
  unsigned __int8 v5; // bl
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  _WORD *v8; // r9
  __int64 v9; // rcx
  int *v10; // rdx
  __int64 v11; // r10
  __int16 v12; // ax
  int v13; // esi
  _WORD *v14; // rcx
  void *v15; // rax
  int Pointer; // ebx
  DWORD v18; // ecx
  DWORD v19; // eax
  unsigned __int16 v20[4]; // [rsp+38h] [rbp-30h] BYREF
  _QWORD *v21; // [rsp+40h] [rbp-28h]

  v5 = 0;
  if ( a1 || !a3 )
  {
    v18 = 87;
LABEL_27:
    SetLastError(v18);
    return v5;
  }
  *a3 = 0;
  if ( !TestServiceStarted() )
  {
    v18 = 1352;
    goto LABEL_27;
  }
  *(_QWORD *)v20 = 0;
  v6 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    *v6 = 0;
    v6[1] = 0;
    v6[2] = 0;
    v6[3] = 0;
    v6[4] = 0;
    v6[5] = 0;
    v6[6] = 1;
    v6[7] = 0;
    v8 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
    v7[5] = v8;
    if ( v8 )
    {
      v9 = 2147483646;
      v10 = &dword_18003FF34;
      v11 = 1;
      do
      {
        if ( !v9 )
          break;
        v12 = *(_WORD *)v10;
        if ( !*(_WORD *)v10 )
          break;
        v10 = (int *)((char *)v10 + 2);
        *v8++ = v12;
        --v9;
        --v11;
      }
      while ( v11 );
      v13 = -2147024774;
      if ( v11 )
        v13 = 0;
      v14 = v8 - 1;
      if ( v11 )
        v14 = v8;
      *v14 = 0;
      if ( v11 )
      {
        if ( !v7[3] && !*((_DWORD *)v7 + 12) )
        {
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v7) == -2147023174 )
            *((_DWORD *)v7 + 13) = 1;
          CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v7);
        }
      }
      else
      {
        ConvertHRESULT2WIN32(v13);
        _DbgPrintMessage(8, "StringCchCopy failed: %x", v13);
      }
    }
  }
  else
  {
    v7 = 0;
  }
  v21 = v7;
  if ( v7 )
  {
    *(_DWORD *)&v20[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( SessionId == -1 )
    SessionId = NtCurrentPeb()->SessionId;
  if ( CSmartPublicBinding::operator void *(v20)
    && (v15 = CSmartPublicBinding::operator void *(v20),
        Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x12u, 0, v15, SessionId, a3).Pointer,
        Pointer < 0) )
  {
    _DbgPrintMessage(8, "RpcIsTerminalRemote failed: 0x%x in %s", Pointer, "InternalIsSessionRemoteable");
    v19 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v19);
    v5 = 0;
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v20);
  }
  else
  {
    v5 = 1;
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v20);
  }
  return v5;
}

```

## disassembly

```asm
0x180007d20  mov     [rsp+arg_8], rbx
0x180007d25  mov     [rsp+arg_10], rsi
0x180007d2a  push    rdi
0x180007d2b  push    r14
0x180007d2d  push    r15
0x180007d2f  sub     rsp, 50h
0x180007d33  mov     rdi, r8
0x180007d36  mov     r14d, edx
0x180007d39  xor     bl, bl
0x180007d3b  test    rcx, rcx
0x180007d3e  jnz     loc_180007F0A
0x180007d44  test    r8, r8
0x180007d47  jz      loc_180007F0A
0x180007d4d  mov     [r8], bl
0x180007d50  call    ?TestServiceStarted@@YAHK@Z; TestServiceStarted(ulong)
0x180007d55  test    eax, eax
0x180007d57  jz      loc_180007F7A
0x180007d5d  xor     r15d, r15d
0x180007d60  mov     qword ptr [rsp+68h+var_30], r15
0x180007d65  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007d6c  mov     ecx, 40h ; '@'; unsigned __int64
0x180007d71  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007d76  mov     rbx, rax
0x180007d79  test    rax, rax
0x180007d7c  jz      loc_180007F8A
0x180007d82  mov     [rax], r15
0x180007d85  mov     [rax+8], r15
0x180007d89  mov     [rax+10h], r15
0x180007d8d  mov     [rax+18h], r15
0x180007d91  mov     [rax+20h], r15
0x180007d95  mov     [rax+28h], r15
0x180007d99  mov     qword ptr [rax+30h], 1
0x180007da1  mov     [rax+38h], r15
0x180007da5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007dac  mov     ecx, 2; unsigned __int64
0x180007db1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007db6  mov     r9, rax
0x180007db9  mov     [rbx+28h], rax
0x180007dbd  test    rax, rax
0x180007dc0  jz      short loc_180007E24
0x180007dc2  mov     ecx, 7FFFFFFEh
0x180007dc7  lea     rdx, dword_18003FF34
0x180007dce  mov     r10d, 1
0x180007dd4  test    rcx, rcx
0x180007dd7  jz      short loc_180007DF6
0x180007dd9  movzx   eax, word ptr [rdx]
0x180007ddc  test    ax, ax
0x180007ddf  jz      short loc_180007DF6
0x180007de1  add     rdx, 2
0x180007de5  mov     [r9], ax
0x180007de9  add     r9, 2
0x180007ded  dec     rcx
0x180007df0  sub     r10, 1
0x180007df4  jnz     short loc_180007DD4
0x180007df6  mov     esi, 8007007Ah
0x180007dfb  test    r10, r10
0x180007dfe  cmovnz  esi, r15d
0x180007e02  lea     rcx, [r9-2]
0x180007e06  cmovnz  rcx, r9
0x180007e0a  mov     [rcx], r15w
0x180007e0e  jz      loc_180007EEA
0x180007e14  cmp     [rbx+18h], r15
0x180007e18  jnz     short loc_180007E24
0x180007e1a  cmp     [rbx+30h], r15d
0x180007e1e  jz      loc_180007F1D
0x180007e24  mov     [rsp+68h+var_28], rbx
0x180007e29  test    rbx, rbx
0x180007e2c  jz      loc_180007F92
0x180007e32  mov     dword ptr [rsp+68h+var_30+4], 1
0x180007e3a  cmp     r14d, 0FFFFFFFFh
0x180007e3e  jz      loc_180007FB9
0x180007e44  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x180007e49  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180007e4e  test    rax, rax
0x180007e51  jz      short loc_180007EC3
0x180007e53  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x180007e58  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180007e5d  mov     [rsp+68h+arg_0], r15
0x180007e62  mov     [rsp+68h+var_40], rdi
0x180007e67  mov     [rsp+68h+var_48], r14d
0x180007e6c  mov     r9, rax
0x180007e6f  xor     r8d, r8d; pReturnValue
0x180007e72  mov     edx, 12h; nProcNum
0x180007e77  lea     rcx, pProxyInfo; pProxyInfo
0x180007e7e  call    cs:__imp_NdrClientCall3
0x180007e85  nop     dword ptr [rax+rax+00h]
0x180007e8a  mov     rbx, rax
0x180007e8d  mov     [rsp+68h+arg_0], rax
0x180007e92  mov     [rsp+68h+var_38], eax
0x180007e96  jmp     short loc_180007EBF
0x180007e98  test    eax, eax
0x180007e9a  jle     short loc_180007EA4
0x180007e9c  movzx   eax, ax
0x180007e9f  or      eax, 80070000h
0x180007ea4  mov     ebx, eax
0x180007ea6  mov     [rsp+68h+var_38], eax
0x180007eaa  mov     r8d, eax
0x180007ead  lea     rdx, aRpcisterminalr_0; "RpcIsTerminalRemote threw an exception:"...
0x180007eb4  mov     ecx, 8; int
0x180007eb9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007ebe  nop
0x180007ebf  test    ebx, ebx
0x180007ec1  js      short loc_180007F39
0x180007ec3  mov     bl, 1
0x180007ec5  lea     rcx, [rsp+68h+var_30]; this
0x180007eca  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180007ecf  movzx   eax, bl
0x180007ed2  mov     rbx, [rsp+68h+arg_8]
0x180007ed7  mov     rsi, [rsp+68h+arg_10]
0x180007edf  add     rsp, 50h
0x180007ee3  pop     r15
0x180007ee5  pop     r14
0x180007ee7  pop     rdi
0x180007ee8  retn
0x180007eea  mov     ecx, esi; int
0x180007eec  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180007ef1  mov     r8d, esi
0x180007ef4  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180007efb  mov     ecx, 8; int
0x180007f00  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007f05  jmp     loc_180007E24
0x180007f0a  mov     ecx, 57h ; 'W'; dwErrCode
0x180007f0f  call    cs:__imp_SetLastError
0x180007f16  nop     dword ptr [rax+rax+00h]
0x180007f1b  jmp     short loc_180007ECF
0x180007f1d  mov     rcx, rbx; this
0x180007f20  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x180007f25  cmp     eax, 800706BAh
0x180007f2a  jz      short loc_180007F81
0x180007f2c  mov     rcx, rbx; this
0x180007f2f  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180007f34  jmp     loc_180007E24
0x180007f39  lea     r9, aInternalissess; "InternalIsSessionRemoteable"
0x180007f40  mov     r8d, ebx
0x180007f43  lea     rdx, aRpcisterminalr; "RpcIsTerminalRemote failed: 0x%x in %s"
0x180007f4a  mov     ecx, 8; int
0x180007f4f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007f54  mov     ecx, ebx; int
0x180007f56  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180007f5b  mov     ecx, eax; dwErrCode
0x180007f5d  call    cs:__imp_SetLastError
0x180007f64  nop     dword ptr [rax+rax+00h]
0x180007f69  xor     bl, bl
0x180007f6b  lea     rcx, [rsp+68h+var_30]; this
0x180007f70  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180007f75  jmp     loc_180007ECF
0x180007f7a  mov     ecx, 548h
0x180007f7f  jmp     short loc_180007F0F
0x180007f81  mov     dword ptr [rbx+34h], 1
0x180007f88  jmp     short loc_180007F2C
0x180007f8a  mov     rbx, r15
0x180007f8d  jmp     loc_180007E24
0x180007f92  mov     ecx, 0Eh; dwErrCode
0x180007f97  call    cs:__imp_SetLastError
0x180007f9e  nop     dword ptr [rax+rax+00h]
0x180007fa3  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180007faa  mov     ecx, 8; int
0x180007faf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007fb4  jmp     loc_180007E3A
0x180007fb9  mov     rax, gs:60h
0x180007fc2  mov     r14d, [rax+2C0h]
0x180007fc9  jmp     loc_180007E44
0x1800330c0  push    rbp
0x1800330c2  sub     rsp, 30h
0x1800330c6  mov     rbp, rdx
0x1800330c9  mov     rcx, [rcx]
0x1800330cc  mov     ecx, [rcx]; ExceptionCode
0x1800330ce  call    cs:__imp_I_RpcExceptionFilter
0x1800330d5  nop     dword ptr [rax+rax+00h]
0x1800330da  nop
0x1800330db  add     rsp, 30h
0x1800330df  pop     rbp
0x1800330e0  retn
```
