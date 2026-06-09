# GetConfigData(void *,ulong,_WINSTATIONCONFIGW *,ulong,ulong *)

- ea: `0x180001a10`
- end: `0x180001d78`
- name: `?GetConfigData@@YAJPEAXKPEAU_WINSTATIONCONFIGW@@KPEAK@Z`
- size: `872`
- prototype: `int(void *, unsigned int, struct _WINSTATIONCONFIGW *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180009dec`

## callees

- `0x180001a10`
- `0x1800032b4`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800066d0`
- `0x1800075a0`
- `0x1800249e8`
- `0x180024a1c`
- `0x180025cc6`
- `0x180032be6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001d36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b78`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032d91`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032d91`
- `RPCRT4!NdrClientCall3` at `0x180001c19`
- `RPCRT4!NdrClientCall3` at `0x180001c19`

## string_xrefs

- `0x180001ba7`: `StringCchCopy failed: %x`
- `0x180001c75`: `RpcGetConfigData threw an exception: 0x%x`
- `0x180001d58`: `GetConfigData`
- `0x180001d62`: `RpcGetConfigData failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall GetConfigData(void *a1, int a2, struct _WINSTATIONCONFIGW *a3, unsigned int a4, unsigned int *a5)
{
  size_t v5; // r14
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _WORD *v9; // rcx
  __int64 v10; // rax
  int *v11; // r8
  __int64 v12; // rdx
  __int16 v13; // r9
  int v14; // edi
  _WORD *v15; // rax
  signed int LastError; // eax
  CLIENT_CALL_RETURN v17; // rbx
  _BYTE *v18; // rax
  __int64 v19; // rcx
  __int64 v21; // rax
  unsigned int v22; // edi
  HLOCAL hMem; // [rsp+48h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v24; // [rsp+50h] [rbp-48h]
  __int64 v25; // [rsp+58h] [rbp-40h] BYREF
  void *v26; // [rsp+60h] [rbp-38h]
  size_t Size; // [rsp+A0h] [rbp+8h] BYREF
  void *v28; // [rsp+B0h] [rbp+18h]
  size_t v29; // [rsp+B8h] [rbp+20h]

  LODWORD(v29) = a4;
  v28 = a3;
  v5 = a4;
  hMem = 0;
  LODWORD(Size) = 0;
  v25 = 1;
  if ( a1 )
  {
    v26 = a1;
  }
  else
  {
    v7 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( v7 )
    {
      *v7 = 0;
      v7[1] = 0;
      v7[2] = 0;
      v7[3] = 0;
      v7[4] = 0;
      v7[5] = 0;
      v7[6] = 1;
      v7[7] = 0;
      v9 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      v8[5] = v9;
      if ( v9 )
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
          *v9++ = v13;
          --v10;
          --v12;
        }
        while ( v12 );
        v14 = v12 == 0 ? 0x8007007A : 0;
        v15 = v9 - 1;
        if ( v12 )
          v15 = v9;
        *v15 = 0;
        if ( v12 )
        {
          if ( !v8[3] && !*((_DWORD *)v8 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((CPublicBinding *)v8) == -2147023174 )
              *((_DWORD *)v8 + 13) = 1;
            CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v8);
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
      v8 = 0;
    }
    v26 = v8;
    if ( v8 )
    {
      HIDWORD(v25) = 1;
    }
    else
    {
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
  }
  if ( !CSmartPublicBinding::operator void *((unsigned __int16 *)&v25) )
  {
    LastError = GetLastError();
    LODWORD(v17.Pointer) = LastError;
    if ( LastError > 0 )
      LODWORD(v17.Pointer) = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
    if ( SLODWORD(v17.Simple) < 0 )
      goto LABEL_19;
    goto LABEL_31;
  }
  v21 = CSmartPublicBinding::operator void *((unsigned __int16 *)&v25);
  v24.Simple = 0;
  v17.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035078, 1u, 0, v21, a2, &hMem, &Size).Pointer;
  v24.Pointer = v17.Pointer;
  if ( LODWORD(v17.Pointer) == -2147022646 )
  {
    *a5 = v5;
    memset_0(v28, 0, v5);
    LODWORD(v17.Pointer) = 0;
  }
  if ( SLODWORD(v17.Simple) < 0 )
  {
    _DbgPrintMessage(8, "RpcGetConfigData failed: 0x%x in %s", LODWORD(v17.Pointer), "GetConfigData");
    goto LABEL_18;
  }
LABEL_31:
  if ( hMem )
  {
    v22 = Size;
    if ( (unsigned int)Size < (unsigned int)v5 )
      LODWORD(v5) = Size;
    memcpy_0(v28, hMem, (unsigned int)v5);
    *a5 = v22;
  }
LABEL_19:
  v18 = hMem;
  if ( hMem )
  {
    v19 = (unsigned int)Size;
    if ( (_DWORD)Size )
    {
      do
      {
        *v18++ = 0;
        --v19;
      }
      while ( v19 );
    }
    LocalFree(hMem);
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)&v25);
  return LODWORD(v17.Pointer);
}

```

## disassembly

```asm
0x180001a10  mov     rax, rsp
0x180001a13  mov     [rax+20h], r9d
0x180001a17  mov     [rax+18h], r8
0x180001a1b  push    rbx
0x180001a1c  push    rsi
0x180001a1d  push    rdi
0x180001a1e  push    r12
0x180001a20  push    r14
0x180001a22  sub     rsp, 70h
0x180001a26  mov     r14d, r9d
0x180001a29  mov     r12d, edx
0x180001a2c  xor     esi, esi
0x180001a2e  mov     [rax-50h], rsi
0x180001a32  mov     [rax+8], esi
0x180001a35  mov     qword ptr [rax-40h], 1
0x180001a3d  test    rcx, rcx
0x180001a40  jnz     loc_180001D13
0x180001a46  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001a4d  lea     ecx, [rsi+40h]; unsigned __int64
0x180001a50  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001a55  mov     rbx, rax
0x180001a58  test    rax, rax
0x180001a5b  jz      loc_180001D29
0x180001a61  mov     [rax], rsi
0x180001a64  mov     [rax+8], rsi
0x180001a68  mov     [rax+10h], rsi
0x180001a6c  mov     [rax+18h], rsi
0x180001a70  mov     [rax+20h], rsi
0x180001a74  mov     [rax+28h], rsi
0x180001a78  mov     qword ptr [rax+30h], 1
0x180001a80  mov     [rax+38h], rsi
0x180001a84  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001a8b  lea     ecx, [rsi+2]; unsigned __int64
0x180001a8e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180001a93  mov     rcx, rax
0x180001a96  mov     [rbx+28h], rax
0x180001a9a  test    rax, rax
0x180001a9d  jz      short loc_180001B05
0x180001a9f  mov     eax, 7FFFFFFEh
0x180001aa4  lea     r8, dword_18003FF34
0x180001aab  lea     edx, [rsi+1]
0x180001aae  test    rax, rax
0x180001ab1  jz      short loc_180001AD2
0x180001ab3  movzx   r9d, word ptr [r8]
0x180001ab7  test    r9w, r9w
0x180001abb  jz      short loc_180001AD2
0x180001abd  add     r8, 2
0x180001ac1  mov     [rcx], r9w
0x180001ac5  add     rcx, 2
0x180001ac9  dec     rax
0x180001acc  sub     rdx, 1
0x180001ad0  jnz     short loc_180001AAE
0x180001ad2  mov     rax, rdx
0x180001ad5  neg     rax
0x180001ad8  sbb     edi, edi
0x180001ada  not     edi
0x180001adc  and     edi, 8007007Ah
0x180001ae2  lea     rax, [rcx-2]
0x180001ae6  test    rdx, rdx
0x180001ae9  cmovnz  rax, rcx
0x180001aed  mov     [rax], si
0x180001af0  jz      loc_180001B9D
0x180001af6  cmp     [rbx+18h], rsi
0x180001afa  jnz     short loc_180001B05
0x180001afc  cmp     [rbx+30h], esi
0x180001aff  jz      loc_180001BBD
0x180001b05  mov     [rsp+98h+var_38], rbx
0x180001b0a  test    rbx, rbx
0x180001b0d  jz      loc_180001D31
0x180001b13  mov     [rsp+98h+var_3C], 1
0x180001b1b  lea     rcx, [rsp+98h+var_40]; unsigned __int16 *
0x180001b20  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180001b25  test    rax, rax
0x180001b28  jnz     loc_180001BDD
0x180001b2e  call    cs:__imp_GetLastError
0x180001b35  nop     dword ptr [rax+rax+00h]
0x180001b3a  mov     ebx, eax
0x180001b3c  test    eax, eax
0x180001b3e  jle     short loc_180001B49
0x180001b40  movzx   ebx, ax
0x180001b43  or      ebx, 80070000h
0x180001b49  test    ebx, ebx
0x180001b4b  jns     loc_180001CA8
0x180001b51  mov     rax, [rsp+98h+hMem]
0x180001b56  test    rax, rax
0x180001b59  jz      short loc_180001B84
0x180001b5b  mov     ecx, dword ptr [rsp+98h+Size]
0x180001b62  test    rcx, rcx
0x180001b65  jz      short loc_180001B73
0x180001b67  mov     [rax], sil
0x180001b6a  inc     rax
0x180001b6d  sub     rcx, 1
0x180001b71  jnz     short loc_180001B67
0x180001b73  mov     rcx, [rsp+98h+hMem]; hMem
0x180001b78  call    cs:__imp_LocalFree
0x180001b7f  nop     dword ptr [rax+rax+00h]
0x180001b84  lea     rcx, [rsp+98h+var_40]; this
0x180001b89  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180001b8e  mov     eax, ebx
0x180001b90  add     rsp, 70h
0x180001b94  pop     r14
0x180001b96  pop     r12
0x180001b98  pop     rdi
0x180001b99  pop     rsi
0x180001b9a  pop     rbx
0x180001b9b  retn
0x180001b9d  mov     ecx, edi; int
0x180001b9f  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180001ba4  mov     r8d, edi
0x180001ba7  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180001bae  mov     ecx, 8; int
0x180001bb3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001bb8  jmp     loc_180001B05
0x180001bbd  mov     rcx, rbx; this
0x180001bc0  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x180001bc5  cmp     eax, 800706BAh
0x180001bca  jz      loc_180001D1D
0x180001bd0  mov     rcx, rbx; this
0x180001bd3  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180001bd8  jmp     loc_180001B05
0x180001bdd  lea     rcx, [rsp+98h+var_40]; unsigned __int16 *
0x180001be2  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180001be7  mov     [rsp+98h+var_48], rsi
0x180001bec  lea     rcx, [rsp+98h+Size]
0x180001bf4  mov     [rsp+98h+var_68], rcx
0x180001bf9  lea     rcx, [rsp+98h+hMem]
0x180001bfe  mov     [rsp+98h+var_70], rcx
0x180001c03  mov     [rsp+98h+var_78], r12d
0x180001c08  mov     r9, rax
0x180001c0b  xor     r8d, r8d; pReturnValue
0x180001c0e  lea     edx, [r8+1]; nProcNum
0x180001c12  lea     rcx, stru_180035078; pProxyInfo
0x180001c19  call    cs:__imp_NdrClientCall3
0x180001c20  nop     dword ptr [rax+rax+00h]
0x180001c25  mov     rbx, rax
0x180001c28  mov     [rsp+98h+var_48], rax
0x180001c2d  mov     [rsp+98h+var_58], eax
0x180001c31  cmp     eax, 800708CAh
0x180001c36  jnz     short loc_180001C5B
0x180001c38  mov     rax, [rsp+98h+arg_20]
0x180001c40  mov     [rax], r14d
0x180001c43  mov     r8, r14; Size
0x180001c46  xor     edx, edx; Val
0x180001c48  mov     rcx, [rsp+98h+arg_10]; void *
0x180001c50  call    memset_0
0x180001c55  mov     ebx, esi
0x180001c57  mov     [rsp+98h+var_58], ebx
0x180001c5b  jmp     short loc_180001CA0
0x180001c5d  mov     edi, eax
0x180001c5f  test    eax, eax
0x180001c61  jle     short loc_180001C6C
0x180001c63  movzx   edi, ax
0x180001c66  or      edi, 80070000h
0x180001c6c  mov     ebx, edi
0x180001c6e  mov     [rsp+98h+var_58], ebx
0x180001c72  mov     r8d, edi
0x180001c75  lea     rdx, aRpcgetconfigda; "RpcGetConfigData threw an exception: 0x"...
0x180001c7c  mov     ecx, 8; int
0x180001c81  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001c86  cmp     edi, 800706B5h
0x180001c8c  jz      short loc_180001CE6
0x180001c8e  cmp     edi, 800706BAh
0x180001c94  jz      short loc_180001CE6
0x180001c96  mov     r14d, dword ptr [rsp+98h+arg_18]
0x180001c9e  xor     esi, esi
0x180001ca0  test    ebx, ebx
0x180001ca2  js      loc_180001D58
0x180001ca8  mov     rax, [rsp+98h+hMem]
0x180001cad  test    rax, rax
0x180001cb0  jz      loc_180001B51
0x180001cb6  mov     edi, dword ptr [rsp+98h+Size]
0x180001cbd  cmp     edi, r14d
0x180001cc0  cmovb   r14d, edi
0x180001cc4  mov     r8d, r14d; Size
0x180001cc7  mov     rdx, rax; Src
0x180001cca  mov     rcx, [rsp+98h+arg_10]; void *
0x180001cd2  call    memcpy_0
0x180001cd7  mov     rax, [rsp+98h+arg_20]
0x180001cdf  mov     [rax], edi
0x180001ce1  jmp     loc_180001B51
0x180001ce6  mov     r14d, dword ptr [rsp+98h+arg_18]
0x180001cee  mov     rax, [rsp+98h+arg_20]
0x180001cf6  mov     [rax], r14d
0x180001cf9  mov     r8d, r14d; Size
0x180001cfc  xor     edx, edx; Val
0x180001cfe  mov     rcx, [rsp+98h+arg_10]; void *
0x180001d06  call    memset_0
0x180001d0b  xor     ebx, ebx
0x180001d0d  mov     [rsp+98h+var_58], ebx
0x180001d11  jmp     short loc_180001C9E
0x180001d13  mov     [rsp+98h+var_38], rcx
0x180001d18  jmp     loc_180001B1B
0x180001d1d  mov     dword ptr [rbx+34h], 1
0x180001d24  jmp     loc_180001BD0
0x180001d29  mov     rbx, rsi
0x180001d2c  jmp     loc_180001B05
0x180001d31  mov     ecx, 0Eh; dwErrCode
0x180001d36  call    cs:__imp_SetLastError
0x180001d3d  nop     dword ptr [rax+rax+00h]
0x180001d42  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180001d49  mov     ecx, 8; int
0x180001d4e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001d53  jmp     loc_180001B1B
0x180001d58  lea     r9, aGetconfigdata; "GetConfigData"
0x180001d5f  mov     r8d, ebx
0x180001d62  lea     rdx, aRpcgetconfigda_0; "RpcGetConfigData failed: 0x%x in %s"
0x180001d69  mov     ecx, 8; int
0x180001d6e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001d73  jmp     loc_180001B49
0x180032d83  push    rbp
0x180032d85  sub     rsp, 40h
0x180032d89  mov     rbp, rdx
0x180032d8c  mov     rcx, [rcx]
0x180032d8f  mov     ecx, [rcx]; ExceptionCode
0x180032d91  call    cs:__imp_I_RpcExceptionFilter
0x180032d98  nop     dword ptr [rax+rax+00h]
0x180032d9d  nop
0x180032d9e  add     rsp, 40h
0x180032da2  pop     rbp
0x180032da3  retn
```
