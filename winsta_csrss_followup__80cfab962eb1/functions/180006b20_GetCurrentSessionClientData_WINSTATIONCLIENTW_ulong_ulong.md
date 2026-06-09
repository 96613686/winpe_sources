# GetCurrentSessionClientData(_WINSTATIONCLIENTW *,ulong,ulong *)

- ea: `0x180006b20`
- end: `0x180006ebc`
- name: `?GetCurrentSessionClientData@@YAJPEAU_WINSTATIONCLIENTW@@KPEAK@Z`
- size: `924`
- prototype: `__int64 __fastcall(struct _WINSTATIONCLIENTW *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800095b0`
- `0x1800096c0`

## callees

- `0x1800032b4`
- `0x180004558`
- `0x180005b40`
- `0x180006540`
- `0x1800066d0`
- `0x180006b20`
- `0x1800075a0`
- `0x1800249e8`
- `0x180024a1c`
- `0x180025cc6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006e7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006e7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d52`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003306e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003306e`
- `RPCRT4!NdrClientCall3` at `0x180006c97`
- `RPCRT4!NdrClientCall3` at `0x180006c97`

## string_xrefs

- `0x180006d8d`: `StringCchCopy failed: %x`

## pseudocode

```c
__int64 __fastcall GetCurrentSessionClientData(struct _WINSTATIONCLIENTW *a1, unsigned int a2, unsigned int *a3)
{
  int v6; // r13d
  _QWORD *v7; // rax
  __int64 v8; // rdx
  _QWORD *v9; // r12
  _WORD *v10; // rcx
  __int64 v11; // rax
  int *v12; // r8
  __int16 v13; // r9
  int v14; // ebx
  _WORD *v15; // rax
  void *v16; // rax
  CLIENT_CALL_RETURN v17; // rbx
  __int64 v18; // rax
  _BYTE *v19; // rax
  __int64 v20; // rcx
  __int64 v22; // rax
  char *v23; // rdi
  signed int LastError; // eax
  HLOCAL hMem; // [rsp+38h] [rbp-60h] BYREF
  CLIENT_CALL_RETURN v26; // [rsp+40h] [rbp-58h]
  __int64 v27; // [rsp+48h] [rbp-50h] BYREF
  _QWORD *v28; // [rsp+50h] [rbp-48h]
  size_t Size; // [rsp+B8h] [rbp+20h] BYREF

  hMem = 0;
  LODWORD(Size) = 0;
  v6 = 0;
  v27 = 1;
  v7 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v7;
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
    v10 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
    v9[5] = v10;
    if ( v10 )
    {
      v11 = 2147483646;
      v12 = &dword_18003FF34;
      v8 = 1;
      do
      {
        if ( !v11 )
          break;
        v13 = *(_WORD *)v12;
        if ( !*(_WORD *)v12 )
          break;
        v12 = (int *)((char *)v12 + 2);
        *v10++ = v13;
        --v11;
        --v8;
      }
      while ( v8 );
      v14 = -2147024774;
      if ( v8 )
        v14 = 0;
      v15 = v10 - 1;
      if ( v8 )
        v15 = v10;
      *v15 = 0;
      if ( v8 )
      {
        if ( !v9[3] && !*((_DWORD *)v9 + 12) )
        {
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v9) == -2147023174 )
            *((_DWORD *)v9 + 13) = 1;
          CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v9);
        }
      }
      else
      {
        ConvertHRESULT2WIN32(v14);
        _DbgPrintMessage(8, "StringCchCopy failed: %x", v14);
      }
    }
    v28 = v9;
  }
  else
  {
    v9 = 0;
    v28 = 0;
  }
  if ( v9 )
  {
    v6 = 1;
    HIDWORD(v27) = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  *a3 = 0;
  if ( a2 < 0x8F8 )
  {
    LODWORD(v17.Pointer) = -2147024809;
  }
  else if ( CSmartPublicBinding::operator void *((unsigned __int16 *)&v27) )
  {
    v16 = CSmartPublicBinding::operator void *((unsigned __int16 *)&v27);
    v26.Simple = 0;
    v17.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035018, 1u, 0, v16, &hMem, &Size).Pointer;
    v26.Pointer = v17.Pointer;
    if ( LODWORD(v17.Pointer) == -2147022646
      || LODWORD(v17.Pointer) == -2147023174
      || LODWORD(v17.Pointer) == -2147023179 )
    {
      *a3 = a2;
      v18 = a2;
      do
      {
        *(_BYTE *)a1 = 0;
        a1 = (struct _WINSTATIONCLIENTW *)((char *)a1 + 1);
        --v18;
      }
      while ( v18 );
      LODWORD(v17.Pointer) = 0;
    }
    else if ( SLODWORD(v17.Simple) < 0 )
    {
      _DbgPrintMessage(
        8,
        "RpcGetCurrentSessionClientData failed: 0x%x in %s",
        LODWORD(v17.Pointer),
        "GetCurrentSessionClientData");
    }
    else
    {
      if ( (unsigned int)Size < a2 )
        a2 = Size;
      memcpy_0(a1, hMem, a2);
      v22 = 30;
      v23 = (char *)a1 + 124;
      do
      {
        *v23++ = 0;
        --v22;
      }
      while ( v22 );
      *a3 = Size;
    }
  }
  else
  {
    LastError = GetLastError();
    LODWORD(v17.Pointer) = LastError;
    if ( LastError > 0 )
      LODWORD(v17.Pointer) = (unsigned __int16)LastError | 0x80070000;
  }
  v19 = hMem;
  if ( hMem )
  {
    v20 = (unsigned int)Size;
    if ( (_DWORD)Size )
    {
      do
      {
        *v19++ = 0;
        --v20;
      }
      while ( v20 );
    }
    LocalFree(hMem);
  }
  if ( v6 && v9 )
    CPublicBinding::`scalar deleting destructor'((RPC_BINDING_HANDLE *)v9, v8);
  return LODWORD(v17.Pointer);
}

```

## disassembly

```asm
0x180006b20  mov     rax, rsp
0x180006b23  mov     [rax+18h], r8
0x180006b27  mov     [rax+10h], edx
0x180006b2a  mov     [rax+8], rcx
0x180006b2e  push    rbx
0x180006b2f  push    rsi
0x180006b30  push    rdi
0x180006b31  push    r12
0x180006b33  push    r13
0x180006b35  push    r14
0x180006b37  push    r15
0x180006b39  sub     rsp, 60h
0x180006b3d  mov     r14, r8
0x180006b40  mov     esi, edx
0x180006b42  mov     rdi, rcx
0x180006b45  xor     r15d, r15d
0x180006b48  mov     [rax-60h], r15
0x180006b4c  mov     [rax+20h], r15d
0x180006b50  mov     r13d, r15d
0x180006b53  mov     qword ptr [rax-50h], 1
0x180006b5b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006b62  mov     ecx, 40h ; '@'; unsigned __int64
0x180006b67  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006b6c  mov     r12, rax
0x180006b6f  test    rax, rax
0x180006b72  jz      loc_180006E68
0x180006b78  mov     [rax], r15
0x180006b7b  mov     [rax+8], r15
0x180006b7f  mov     [rax+10h], r15
0x180006b83  mov     [rax+18h], r15
0x180006b87  mov     [rax+20h], r15
0x180006b8b  mov     [rax+28h], r15
0x180006b8f  mov     qword ptr [rax+30h], 1
0x180006b97  mov     [rax+38h], r15
0x180006b9b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006ba2  mov     ecx, 2; unsigned __int64
0x180006ba7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006bac  mov     rcx, rax
0x180006baf  mov     [r12+28h], rax
0x180006bb4  test    rax, rax
0x180006bb7  jz      short loc_180006C24
0x180006bb9  mov     eax, 7FFFFFFEh
0x180006bbe  lea     r8, dword_18003FF34
0x180006bc5  mov     edx, 1
0x180006bca  nop     word ptr [rax+rax+00h]
0x180006bd0  test    rax, rax
0x180006bd3  jz      short loc_180006BF4
0x180006bd5  movzx   r9d, word ptr [r8]
0x180006bd9  test    r9w, r9w
0x180006bdd  jz      short loc_180006BF4
0x180006bdf  add     r8, 2
0x180006be3  mov     [rcx], r9w
0x180006be7  add     rcx, 2
0x180006beb  dec     rax
0x180006bee  sub     rdx, 1
0x180006bf2  jnz     short loc_180006BD0
0x180006bf4  mov     ebx, 8007007Ah
0x180006bf9  test    rdx, rdx
0x180006bfc  cmovnz  ebx, r15d
0x180006c00  lea     rax, [rcx-2]
0x180006c04  cmovnz  rax, rcx
0x180006c08  mov     [rax], r15w
0x180006c0c  jz      loc_180006D83
0x180006c12  cmp     [r12+18h], r13
0x180006c17  jnz     short loc_180006C24
0x180006c19  cmp     [r12+30h], r13d
0x180006c1e  jz      loc_180006DA3
0x180006c24  mov     [rsp+98h+var_48], r12
0x180006c29  test    r12, r12
0x180006c2c  jz      loc_180006E75
0x180006c32  mov     r13d, 1
0x180006c38  mov     [rsp+98h+var_4C], r13d
0x180006c3d  mov     [r14], r15d
0x180006c40  cmp     esi, 8F8h
0x180006c46  jb      loc_180006E50
0x180006c4c  lea     rcx, [rsp+98h+var_50]; unsigned __int16 *
0x180006c51  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180006c56  test    rax, rax
0x180006c59  jz      loc_180006E2C
0x180006c5f  lea     rcx, [rsp+98h+var_50]; unsigned __int16 *
0x180006c64  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180006c69  mov     [rsp+98h+var_58], r15
0x180006c6e  lea     rcx, [rsp+98h+Size]
0x180006c76  mov     [rsp+98h+var_70], rcx
0x180006c7b  lea     rcx, [rsp+98h+hMem]
0x180006c80  mov     [rsp+98h+var_78], rcx
0x180006c85  mov     r9, rax
0x180006c88  xor     r8d, r8d; pReturnValue
0x180006c8b  mov     edx, 1; nProcNum
0x180006c90  lea     rcx, stru_180035018; pProxyInfo
0x180006c97  call    cs:__imp_NdrClientCall3
0x180006c9e  nop     dword ptr [rax+rax+00h]
0x180006ca3  mov     rbx, rax
0x180006ca6  mov     [rsp+98h+var_58], rax
0x180006cab  mov     [rsp+98h+var_68], eax
0x180006caf  jmp     short loc_180006CFB
0x180006cb1  test    eax, eax
0x180006cb3  jle     short loc_180006CBD
0x180006cb5  movzx   eax, ax
0x180006cb8  or      eax, 80070000h
0x180006cbd  mov     ebx, eax
0x180006cbf  mov     [rsp+98h+var_68], eax
0x180006cc3  mov     r8d, eax
0x180006cc6  lea     rdx, aRpcgetcurrents_5; "RpcGetCurrentSessionClientData threw an"...
0x180006ccd  mov     ecx, 8; int
0x180006cd2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006cd7  xor     r15d, r15d
0x180006cda  mov     r14, [rsp+98h+arg_10]
0x180006ce2  mov     esi, [rsp+98h+arg_8]
0x180006ce9  mov     rdi, [rsp+98h+arg_0]
0x180006cf1  mov     r12, [rsp+98h+var_48]
0x180006cf6  mov     r13d, [rsp+98h+var_4C]
0x180006cfb  cmp     ebx, 800708CAh
0x180006d01  jnz     loc_180006DC3
0x180006d07  mov     [r14], esi
0x180006d0a  mov     eax, esi
0x180006d0c  test    esi, esi
0x180006d0e  jz      short loc_180006D1D
0x180006d10  mov     byte ptr [rdi], 0
0x180006d13  lea     rdi, [rdi+1]
0x180006d17  sub     rax, 1
0x180006d1b  jnz     short loc_180006D10
0x180006d1d  mov     ebx, r15d
0x180006d20  mov     rax, [rsp+98h+hMem]
0x180006d25  test    rax, rax
0x180006d28  jz      short loc_180006D5E
0x180006d2a  mov     ecx, dword ptr [rsp+98h+Size]
0x180006d31  test    rcx, rcx
0x180006d34  jz      short loc_180006D4D
0x180006d36  nop     word ptr [rax+rax+00000000h]
0x180006d40  mov     byte ptr [rax], 0
0x180006d43  lea     rax, [rax+1]
0x180006d47  sub     rcx, 1
0x180006d4b  jnz     short loc_180006D40
0x180006d4d  mov     rcx, [rsp+98h+hMem]; hMem
0x180006d52  call    cs:__imp_LocalFree
0x180006d59  nop     dword ptr [rax+rax+00h]
0x180006d5e  test    r13d, r13d
0x180006d61  jz      short loc_180006D70
0x180006d63  test    r12, r12
0x180006d66  jz      short loc_180006D70
0x180006d68  mov     rcx, r12; Binding
0x180006d6b  call    ??_GCPublicBinding@@QEAAPEAXI@Z; CPublicBinding::`scalar deleting destructor'(uint)
0x180006d70  mov     eax, ebx
0x180006d72  add     rsp, 60h
0x180006d76  pop     r15
0x180006d78  pop     r14
0x180006d7a  pop     r13
0x180006d7c  pop     r12
0x180006d7e  pop     rdi
0x180006d7f  pop     rsi
0x180006d80  pop     rbx
0x180006d81  retn
0x180006d83  mov     ecx, ebx; int
0x180006d85  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180006d8a  mov     r8d, ebx
0x180006d8d  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180006d94  mov     ecx, 8; int
0x180006d99  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006d9e  jmp     loc_180006C24
0x180006da3  mov     rcx, r12; this
0x180006da6  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x180006dab  cmp     eax, 800706BAh
0x180006db0  jz      loc_180006E5A
0x180006db6  mov     rcx, r12; this
0x180006db9  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180006dbe  jmp     loc_180006C24
0x180006dc3  cmp     ebx, 800706BAh
0x180006dc9  jz      loc_180006D07
0x180006dcf  cmp     ebx, 800706B5h
0x180006dd5  jz      loc_180006D07
0x180006ddb  test    ebx, ebx
0x180006ddd  js      loc_180006E9C
0x180006de3  cmp     dword ptr [rsp+98h+Size], esi
0x180006dea  cmovb   esi, dword ptr [rsp+98h+Size]
0x180006df2  mov     r8d, esi; Size
0x180006df5  mov     rdx, [rsp+98h+hMem]; Src
0x180006dfa  mov     rcx, rdi; void *
0x180006dfd  call    memcpy_0
0x180006e02  mov     eax, 1Eh
0x180006e07  add     rdi, 7Ch ; '|'
0x180006e0b  nop     dword ptr [rax+rax+00h]
0x180006e10  mov     byte ptr [rdi], 0
0x180006e13  lea     rdi, [rdi+1]
0x180006e17  sub     rax, 1
0x180006e1b  jnz     short loc_180006E10
0x180006e1d  mov     eax, dword ptr [rsp+98h+Size]
0x180006e24  mov     [r14], eax
0x180006e27  jmp     loc_180006D20
0x180006e2c  call    cs:__imp_GetLastError
0x180006e33  nop     dword ptr [rax+rax+00h]
0x180006e38  mov     ebx, eax
0x180006e3a  test    eax, eax
0x180006e3c  jle     loc_180006D20
0x180006e42  movzx   ebx, ax
0x180006e45  or      ebx, 80070000h
0x180006e4b  jmp     loc_180006D20
0x180006e50  mov     ebx, 80070057h
0x180006e55  jmp     loc_180006D20
0x180006e5a  mov     dword ptr [r12+34h], 1
0x180006e63  jmp     loc_180006DB6
0x180006e68  mov     r12, r15
0x180006e6b  mov     [rsp+98h+var_48], r15
0x180006e70  jmp     loc_180006C29
0x180006e75  mov     ecx, 0Eh; dwErrCode
0x180006e7a  call    cs:__imp_SetLastError
0x180006e81  nop     dword ptr [rax+rax+00h]
0x180006e86  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180006e8d  mov     ecx, 8; int
0x180006e92  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006e97  jmp     loc_180006C3D
0x180006e9c  lea     r9, aGetcurrentsess_4; "GetCurrentSessionClientData"
0x180006ea3  mov     r8d, ebx
0x180006ea6  lea     rdx, aRpcgetcurrents_13; "RpcGetCurrentSessionClientData failed: "...
0x180006ead  mov     ecx, 8; int
0x180006eb2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006eb7  jmp     loc_180006D20
0x180033060  push    rbp
0x180033062  sub     rsp, 30h
0x180033066  mov     rbp, rdx
0x180033069  mov     rcx, [rcx]
0x18003306c  mov     ecx, [rcx]; ExceptionCode
0x18003306e  call    cs:__imp_I_RpcExceptionFilter
0x180033075  nop     dword ptr [rax+rax+00h]
0x18003307a  nop
0x18003307b  add     rsp, 30h
0x18003307f  pop     rbp
0x180033080  retn
```
