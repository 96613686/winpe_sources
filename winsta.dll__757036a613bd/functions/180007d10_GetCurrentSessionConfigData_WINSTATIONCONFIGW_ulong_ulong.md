# GetCurrentSessionConfigData(_WINSTATIONCONFIGW *,ulong,ulong *)

- ea: `0x180007d10`
- end: `0x18000813c`
- name: `?GetCurrentSessionConfigData@@YAJPEAU_WINSTATIONCONFIGW@@KPEAK@Z`
- size: `1068`
- prototype: `__int64 __fastcall(struct _WINSTATIONCONFIGW *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18000b2b0`
- `0x18000c820`

## callees

- `0x180005374`
- `0x180005fcc`
- `0x180007890`
- `0x180007d10`
- `0x180008150`
- `0x180008340`
- `0x1800230b8`
- `0x1800230ec`
- `0x180024376`
- `0x18002bf2c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007fca`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007fca`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007f74`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007f74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800080e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800080e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000809e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000809e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f52`
- `RPCRT4!RpcBindingFree` at `0x180007f84`
- `RPCRT4!RpcBindingFree` at `0x180007f95`
- `RPCRT4!RpcBindingFree` at `0x18000811c`
- `RPCRT4!RpcBindingFree` at `0x180008127`
- `RPCRT4!RpcBindingFree` at `0x180007f84`
- `RPCRT4!RpcBindingFree` at `0x180007f95`
- `RPCRT4!RpcBindingFree` at `0x18000811c`
- `RPCRT4!RpcBindingFree` at `0x180008127`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800302be`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800302be`
- `RPCRT4!NdrClientCall3` at `0x180007e94`
- `RPCRT4!NdrClientCall3` at `0x180007e94`

## string_xrefs

- `0x180007fec`: `StringCchCopy failed: %x`
- `0x180007ebd`: `RpcGetCurrentSessionConfigData threw an exception: 0x%x`
- `0x1800080fc`: `GetCurrentSessionConfigData`
- `0x180008106`: `RpcGetCurrentSessionConfigData failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall GetCurrentSessionConfigData(struct _WINSTATIONCONFIGW *a1, unsigned int a2, unsigned int *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // r12
  int v8; // r13d
  _WORD *v9; // rcx
  __int64 v10; // rax
  int *v11; // r8
  __int64 v12; // rdx
  __int16 v13; // r9
  int v14; // ebx
  _WORD *v15; // rax
  void **v16; // rbx
  void *v17; // rax
  void *RCMBinding; // rax
  CLIENT_CALL_RETURN v19; // rbx
  __int64 v20; // rax
  _BYTE *v21; // rax
  __int64 v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  __int64 v26; // rax
  char *v27; // rdi
  signed int LastError; // eax
  int v29; // [rsp+30h] [rbp-58h]
  HLOCAL hMem; // [rsp+38h] [rbp-50h] BYREF
  _QWORD *v31; // [rsp+40h] [rbp-48h]
  CLIENT_CALL_RETURN v32; // [rsp+48h] [rbp-40h]
  size_t Size; // [rsp+A8h] [rbp+20h] BYREF

  hMem = 0;
  LODWORD(Size) = 0;
  v6 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  v8 = 1;
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
    v9 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
    v7[5] = v9;
    if ( v9 )
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
        *v9++ = v13;
        --v10;
        --v12;
      }
      while ( v12 );
      v14 = -2147024774;
      if ( v12 )
        v14 = 0;
      v15 = v9 - 1;
      if ( v12 )
        v15 = v9;
      *v15 = 0;
      if ( v12 )
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
        ConvertHRESULT2WIN32(v14);
        _DbgPrintMessage(8, "StringCchCopy failed: %x", v14);
      }
    }
    v31 = v7;
  }
  else
  {
    v7 = 0;
    v31 = 0;
  }
  if ( v7 )
  {
    v29 = 1;
  }
  else
  {
    v8 = 0;
    v29 = 0;
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  *a3 = 0;
  if ( a2 < 0xA68 )
  {
    LODWORD(v19.Pointer) = -2147024809;
    goto LABEL_30;
  }
  v16 = (void **)(v7 + 3);
  if ( v7 )
  {
    if ( *v16 )
    {
LABEL_22:
      if ( v7 )
      {
        RCMBinding = *v16;
        if ( !*v16 )
          RCMBinding = CPublicBinding::GetRCMBinding((CPublicBinding *)v7);
      }
      else
      {
        RCMBinding = 0;
      }
      v32.Simple = 0;
      v19.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032080, 2u, 0, RCMBinding, &hMem, &Size, v29).Pointer;
      v32.Pointer = v19.Pointer;
      if ( LODWORD(v19.Pointer) == -2147022646
        || LODWORD(v19.Pointer) == -2147023174
        || LODWORD(v19.Pointer) == -2147023179 )
      {
        *a3 = a2;
        v20 = a2;
        do
        {
          *(_BYTE *)a1 = 0;
          a1 = (struct _WINSTATIONCONFIGW *)((char *)a1 + 1);
          --v20;
        }
        while ( v20 );
        LODWORD(v19.Pointer) = 0;
      }
      else if ( SLODWORD(v19.Simple) < 0 )
      {
        _DbgPrintMessage(
          8,
          "RpcGetCurrentSessionConfigData failed: 0x%x in %s",
          LODWORD(v19.Pointer),
          "GetCurrentSessionConfigData");
      }
      else
      {
        if ( (unsigned int)Size < a2 )
          a2 = Size;
        memcpy_0(a1, hMem, a2);
        v26 = 30;
        v27 = (char *)a1 + 210;
        do
        {
          *v27++ = 0;
          --v26;
        }
        while ( v26 );
        *a3 = Size;
      }
      goto LABEL_30;
    }
    v17 = CPublicBinding::GetRCMBinding((CPublicBinding *)v7);
  }
  else
  {
    v17 = 0;
  }
  if ( v17 )
    goto LABEL_22;
  LastError = GetLastError();
  LODWORD(v19.Pointer) = LastError;
  if ( LastError > 0 )
    LODWORD(v19.Pointer) = (unsigned __int16)LastError | 0x80070000;
LABEL_30:
  v21 = hMem;
  if ( hMem )
  {
    v22 = (unsigned int)Size;
    if ( (_DWORD)Size )
    {
      do
      {
        *v21++ = 0;
        --v22;
      }
      while ( v22 );
    }
    LocalFree(hMem);
  }
  if ( v8 && v7 )
  {
    CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v7);
    v23 = (void *)v7[5];
    if ( v23 )
      operator delete[](v23);
    if ( *v7 )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7);
    if ( v7[1] )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 1);
    if ( v7[2] )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 2);
    if ( v7[3] )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 3);
    v24 = (void *)v7[4];
    if ( v24 )
      Legacy_WinStationCloseServer(v24);
    operator delete(v7);
  }
  return LODWORD(v19.Pointer);
}

```

## disassembly

```asm
0x180007d10  mov     rax, rsp
0x180007d13  mov     [rax+18h], r8
0x180007d17  mov     [rax+10h], edx
0x180007d1a  mov     [rax+8], rcx
0x180007d1e  push    rbx
0x180007d1f  push    rsi
0x180007d20  push    rdi
0x180007d21  push    r12
0x180007d23  push    r13
0x180007d25  push    r14
0x180007d27  push    r15
0x180007d29  sub     rsp, 50h
0x180007d2d  mov     r14, r8
0x180007d30  mov     esi, edx
0x180007d32  mov     rdi, rcx
0x180007d35  xor     r15d, r15d
0x180007d38  mov     [rax-50h], r15
0x180007d3c  mov     [rax+20h], r15d
0x180007d40  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007d47  mov     ecx, 40h ; '@'; unsigned __int64
0x180007d4c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007d51  mov     r12, rax
0x180007d54  mov     r13d, 1
0x180007d5a  test    rax, rax
0x180007d5d  jz      loc_1800080C6
0x180007d63  mov     [rax], r15
0x180007d66  mov     [rax+8], r15
0x180007d6a  mov     [rax+10h], r15
0x180007d6e  mov     [rax+18h], r15
0x180007d72  mov     [rax+20h], r15
0x180007d76  mov     [rax+28h], r15
0x180007d7a  mov     [rax+30h], r13
0x180007d7e  mov     [rax+38h], r15
0x180007d82  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007d89  mov     ecx, 2; unsigned __int64
0x180007d8e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007d93  mov     rcx, rax
0x180007d96  mov     [r12+28h], rax
0x180007d9b  test    rax, rax
0x180007d9e  jz      short loc_180007E03
0x180007da0  mov     eax, 7FFFFFFEh
0x180007da5  lea     r8, dword_18003D0CC
0x180007dac  mov     edx, r13d
0x180007daf  nop
0x180007db0  test    rax, rax
0x180007db3  jz      short loc_180007DD3
0x180007db5  movzx   r9d, word ptr [r8]
0x180007db9  test    r9w, r9w
0x180007dbd  jz      short loc_180007DD3
0x180007dbf  add     r8, 2
0x180007dc3  mov     [rcx], r9w
0x180007dc7  add     rcx, 2
0x180007dcb  dec     rax
0x180007dce  sub     rdx, r13
0x180007dd1  jnz     short loc_180007DB0
0x180007dd3  mov     ebx, 8007007Ah
0x180007dd8  test    rdx, rdx
0x180007ddb  cmovnz  ebx, r15d
0x180007ddf  lea     rax, [rcx-2]
0x180007de3  cmovnz  rax, rcx
0x180007de7  mov     [rax], r15w
0x180007deb  jz      loc_180007FE2
0x180007df1  cmp     [r12+18h], r15
0x180007df6  jnz     short loc_180007E03
0x180007df8  cmp     [r12+30h], r15d
0x180007dfd  jz      loc_180008002
0x180007e03  mov     [rsp+88h+var_48], r12
0x180007e08  test    r12, r12
0x180007e0b  jz      loc_1800080D3
0x180007e11  mov     [rsp+88h+var_58], r13d
0x180007e16  mov     [r14], r15d
0x180007e19  cmp     esi, 0A68h
0x180007e1f  jb      loc_180008094
0x180007e25  lea     rbx, [r12+18h]
0x180007e2a  test    r12, r12
0x180007e2d  jz      loc_18000808C
0x180007e33  mov     rax, [rbx]
0x180007e36  test    rax, rax
0x180007e39  jnz     short loc_180007E4C
0x180007e3b  mov     rcx, r12; this
0x180007e3e  call    ?GetRCMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetRCMBinding(void)
0x180007e43  test    rax, rax
0x180007e46  jz      loc_18000809E
0x180007e4c  test    r12, r12
0x180007e4f  jz      short loc_180007E63
0x180007e51  mov     rax, [rbx]
0x180007e54  test    rax, rax
0x180007e57  jnz     short loc_180007E66
0x180007e59  mov     rcx, r12; this
0x180007e5c  call    ?GetRCMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetRCMBinding(void)
0x180007e61  jmp     short loc_180007E66
0x180007e63  mov     rax, r15
0x180007e66  mov     [rsp+88h+var_40], r15
0x180007e6b  lea     rcx, [rsp+88h+Size]
0x180007e73  mov     [rsp+88h+var_60], rcx
0x180007e78  lea     rcx, [rsp+88h+hMem]
0x180007e7d  mov     [rsp+88h+var_68], rcx
0x180007e82  mov     r9, rax
0x180007e85  xor     r8d, r8d; pReturnValue
0x180007e88  mov     edx, 2; nProcNum
0x180007e8d  lea     rcx, stru_180032080; pProxyInfo
0x180007e94  call    cs:__imp_NdrClientCall3
0x180007e9a  mov     rbx, rax
0x180007e9d  mov     [rsp+88h+var_40], rax
0x180007ea2  mov     [rsp+88h+var_54], eax
0x180007ea6  jmp     short loc_180007EF2
0x180007ea8  test    eax, eax
0x180007eaa  jle     short loc_180007EB4
0x180007eac  movzx   eax, ax
0x180007eaf  or      eax, 80070000h
0x180007eb4  mov     ebx, eax
0x180007eb6  mov     [rsp+88h+var_54], eax
0x180007eba  mov     r8d, eax
0x180007ebd  lea     rdx, aRpcgetcurrents_2; "RpcGetCurrentSessionConfigData threw an"...
0x180007ec4  mov     ecx, 8; int
0x180007ec9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007ece  xor     r15d, r15d
0x180007ed1  mov     r14, [rsp+88h+arg_10]
0x180007ed9  mov     esi, [rsp+88h+arg_8]
0x180007ee0  mov     rdi, [rsp+88h+arg_0]
0x180007ee8  mov     r13d, [rsp+88h+var_58]
0x180007eed  mov     r12, [rsp+88h+var_48]
0x180007ef2  cmp     ebx, 800708CAh
0x180007ef8  jnz     loc_180008022
0x180007efe  mov     [r14], esi
0x180007f01  mov     eax, esi
0x180007f03  test    esi, esi
0x180007f05  jz      short loc_180007F1D
0x180007f07  nop     word ptr [rax+rax+00000000h]
0x180007f10  mov     byte ptr [rdi], 0
0x180007f13  lea     rdi, [rdi+1]
0x180007f17  sub     rax, 1
0x180007f1b  jnz     short loc_180007F10
0x180007f1d  mov     ebx, r15d
0x180007f20  mov     rax, [rsp+88h+hMem]
0x180007f25  test    rax, rax
0x180007f28  jz      short loc_180007F58
0x180007f2a  mov     ecx, dword ptr [rsp+88h+Size]
0x180007f31  test    rcx, rcx
0x180007f34  jz      short loc_180007F4D
0x180007f36  nop     word ptr [rax+rax+00000000h]
0x180007f40  mov     byte ptr [rax], 0
0x180007f43  lea     rax, [rax+1]
0x180007f47  sub     rcx, 1
0x180007f4b  jnz     short loc_180007F40
0x180007f4d  mov     rcx, [rsp+88h+hMem]; hMem
0x180007f52  call    cs:__imp_LocalFree
0x180007f58  test    r13d, r13d
0x180007f5b  jz      short loc_180007FD0
0x180007f5d  test    r12, r12
0x180007f60  jz      short loc_180007FD0
0x180007f62  mov     rcx, r12; this
0x180007f65  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180007f6a  mov     rcx, [r12+28h]
0x180007f6f  test    rcx, rcx
0x180007f72  jz      short loc_180007F7A
0x180007f74  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007f7a  cmp     qword ptr [r12], 0
0x180007f7f  jz      short loc_180007F8A
0x180007f81  mov     rcx, r12; Binding
0x180007f84  call    cs:__imp_RpcBindingFree
0x180007f8a  lea     rcx, [r12+8]; Binding
0x180007f8f  cmp     qword ptr [rcx], 0
0x180007f93  jz      short loc_180007F9B
0x180007f95  call    cs:__imp_RpcBindingFree
0x180007f9b  lea     rcx, [r12+10h]; Binding
0x180007fa0  cmp     qword ptr [rcx], 0
0x180007fa4  jnz     loc_18000811C
0x180007faa  lea     rcx, [r12+18h]; Binding
0x180007faf  cmp     qword ptr [rcx], 0
0x180007fb3  jnz     loc_180008127
0x180007fb9  mov     rcx, [r12+20h]; void *
0x180007fbe  test    rcx, rcx
0x180007fc1  jnz     loc_180008132
0x180007fc7  mov     rcx, r12
0x180007fca  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007fd0  mov     eax, ebx
0x180007fd2  add     rsp, 50h
0x180007fd6  pop     r15
0x180007fd8  pop     r14
0x180007fda  pop     r13
0x180007fdc  pop     r12
0x180007fde  pop     rdi
0x180007fdf  pop     rsi
0x180007fe0  pop     rbx
0x180007fe1  retn
0x180007fe2  mov     ecx, ebx; int
0x180007fe4  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180007fe9  mov     r8d, ebx
0x180007fec  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180007ff3  mov     ecx, 8; int
0x180007ff8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007ffd  jmp     loc_180007E03
0x180008002  mov     rcx, r12; this
0x180008005  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000800a  cmp     eax, 800706BAh
0x18000800f  jz      loc_1800080BC
0x180008015  mov     rcx, r12; this
0x180008018  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000801d  jmp     loc_180007E03
0x180008022  cmp     ebx, 800706BAh
0x180008028  jz      loc_180007EFE
0x18000802e  cmp     ebx, 800706B5h
0x180008034  jz      loc_180007EFE
0x18000803a  test    ebx, ebx
0x18000803c  js      loc_1800080FC
0x180008042  cmp     dword ptr [rsp+88h+Size], esi
0x180008049  cmovb   esi, dword ptr [rsp+88h+Size]
0x180008051  mov     r8d, esi; Size
0x180008054  mov     rdx, [rsp+88h+hMem]; Src
0x180008059  mov     rcx, rdi; void *
0x18000805c  call    memcpy_0
0x180008061  mov     eax, 1Eh
0x180008066  add     rdi, 0D2h
0x18000806d  nop     dword ptr [rax]
0x180008070  mov     byte ptr [rdi], 0
0x180008073  lea     rdi, [rdi+1]
0x180008077  sub     rax, 1
0x18000807b  jnz     short loc_180008070
0x18000807d  mov     eax, dword ptr [rsp+88h+Size]
0x180008084  mov     [r14], eax
0x180008087  jmp     loc_180007F20
0x18000808c  mov     rax, r15
0x18000808f  jmp     loc_180007E43
0x180008094  mov     ebx, 80070057h
0x180008099  jmp     loc_180007F20
0x18000809e  call    cs:__imp_GetLastError
0x1800080a4  mov     ebx, eax
0x1800080a6  test    eax, eax
0x1800080a8  jle     loc_180007F20
0x1800080ae  movzx   ebx, ax
0x1800080b1  or      ebx, 80070000h
0x1800080b7  jmp     loc_180007F20
0x1800080bc  mov     [r12+34h], r13d
0x1800080c1  jmp     loc_180008015
0x1800080c6  mov     r12, r15
0x1800080c9  mov     [rsp+88h+var_48], r15
0x1800080ce  jmp     loc_180007E08
0x1800080d3  mov     r13d, r15d
0x1800080d6  mov     [rsp+88h+var_58], r15d
0x1800080db  mov     ecx, 0Eh; dwErrCode
0x1800080e0  call    cs:__imp_SetLastError
0x1800080e6  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x1800080ed  mov     ecx, 8; int
0x1800080f2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800080f7  jmp     loc_180007E16
0x1800080fc  lea     r9, aGetcurrentsess_3; "GetCurrentSessionConfigData"
0x180008103  mov     r8d, ebx
0x180008106  lea     rdx, aRpcgetcurrents_8; "RpcGetCurrentSessionConfigData failed: "...
0x18000810d  mov     ecx, 8; int
0x180008112  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008117  jmp     loc_180007F20
0x18000811c  call    cs:__imp_RpcBindingFree
0x180008122  jmp     loc_180007FAA
0x180008127  call    cs:__imp_RpcBindingFree
0x18000812d  jmp     loc_180007FB9
0x180008132  call    ?Legacy_WinStationCloseServer@@YAEPEAX@Z; Legacy_WinStationCloseServer(void *)
0x180008137  jmp     loc_180007FC7
0x1800302b0  push    rbp
0x1800302b2  sub     rsp, 30h
0x1800302b6  mov     rbp, rdx
0x1800302b9  mov     rcx, [rcx]
0x1800302bc  mov     ecx, [rcx]; ExceptionCode
0x1800302be  call    cs:__imp_I_RpcExceptionFilter
0x1800302c4  nop
0x1800302c5  add     rsp, 30h
0x1800302c9  pop     rbp
0x1800302ca  retn
```
