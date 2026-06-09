# GetCachedItemFromShellItem(IUnknown *,_GUID const &,void * *)

- ea: `0x180004ad0`
- end: `0x180004bd3`
- name: `?GetCachedItemFromShellItem@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `259`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004614`

## callees

- `0x180004ad0`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004b7c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004b7c`
- `SHELL32!SHGetTemporaryPropertyForItem` at `0x180004b47`
- `SHELL32!SHGetTemporaryPropertyForItem` at `0x180004b47`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetCachedItemFromShellItem(struct IUnknown *a1, const struct _GUID *a2, void **a3)
{
  HRESULT v4; // ebx
  IShellItem *psi; // [rsp+20h] [rbp-38h] BYREF
  PROPVARIANT ppropvar[2]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v8; // [rsp+38h] [rbp-20h]

  *a3 = 0;
  v4 = -2147467259;
  if ( a1 )
  {
    psi = 0;
    v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, IShellItem **))a1->lpVtbl->QueryInterface)(
           a1,
           &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
           &psi);
    if ( v4 >= 0 )
    {
      *(_OWORD *)ppropvar = 0;
      v8 = 0;
      v4 = SHGetTemporaryPropertyForItem(psi, &PKEY_ItemContext, ppropvar);
      if ( v4 >= 0 )
      {
        *a3 = 0;
        if ( LOWORD(ppropvar[0]) == 13 || (v4 = -2147467262, LOWORD(ppropvar[0]) == 66) )
          v4 = (**(__int64 (__fastcall ***)(PROPVARIANT, GUID *, void **))ppropvar[1])(
                 ppropvar[1],
                 &GUID_00000000_0000_0000_c000_000000000046,
                 a3);
      }
      PropVariantClear(ppropvar);
    }
    if ( psi )
      ((void (__fastcall *)(IShellItem *))psi->lpVtbl->Release)(psi);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004ad0  mov     [rsp+arg_8], rbx
0x180004ad5  push    rdi
0x180004ad6  sub     rsp, 50h
0x180004ada  mov     rax, cs:__security_cookie
0x180004ae1  xor     rax, rsp
0x180004ae4  mov     [rsp+58h+var_18], rax
0x180004ae9  mov     rdi, r8
0x180004aec  mov     qword ptr [r8], 0
0x180004af3  mov     ebx, 80004005h
0x180004af8  test    rcx, rcx
0x180004afb  jz      loc_180004B9A
0x180004b01  mov     [rsp+58h+psi], 0
0x180004b0a  mov     rax, [rcx]
0x180004b0d  lea     r8, [rsp+58h+psi]
0x180004b12  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180004b19  mov     rax, [rax]
0x180004b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b21  mov     ebx, eax
0x180004b23  test    eax, eax
0x180004b25  js      short loc_180004B83
0x180004b27  xorps   xmm0, xmm0
0x180004b2a  xor     eax, eax
0x180004b2c  movups  xmmword ptr [rsp+58h+ppropvar], xmm0
0x180004b31  mov     [rsp+58h+var_20], rax
0x180004b36  lea     r8, [rsp+58h+ppropvar]; ppropvar
0x180004b3b  lea     rdx, PKEY_ItemContext; propkey
0x180004b42  mov     rcx, [rsp+58h+psi]; psi
0x180004b47  call    cs:__imp_SHGetTemporaryPropertyForItem
0x180004b4d  mov     ebx, eax
0x180004b4f  test    eax, eax
0x180004b51  js      short loc_180004B77
0x180004b53  mov     qword ptr [rdi], 0
0x180004b5a  mov     eax, 0Dh
0x180004b5f  cmp     ax, word ptr [rsp+58h+ppropvar]
0x180004b64  jz      short loc_180004BB4
0x180004b66  mov     ebx, 80004002h
0x180004b6b  mov     eax, 42h ; 'B'
0x180004b70  cmp     ax, word ptr [rsp+58h+ppropvar]
0x180004b75  jz      short loc_180004BB4
0x180004b77  lea     rcx, [rsp+58h+ppropvar]; pvar
0x180004b7c  call    cs:__imp_PropVariantClear
0x180004b82  nop
0x180004b83  mov     rcx, [rsp+58h+psi]
0x180004b88  test    rcx, rcx
0x180004b8b  jz      short loc_180004B9A
0x180004b8d  mov     rax, [rcx]
0x180004b90  mov     rax, [rax+10h]
0x180004b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b99  nop
0x180004b9a  mov     eax, ebx
0x180004b9c  mov     rcx, [rsp+58h+var_18]
0x180004ba1  xor     rcx, rsp; StackCookie
0x180004ba4  call    __security_check_cookie
0x180004ba9  mov     rbx, [rsp+58h+arg_8]
0x180004bae  add     rsp, 50h
0x180004bb2  pop     rdi
0x180004bb3  retn
0x180004bb4  mov     rcx, [rsp+58h+ppropvar+8]
0x180004bb9  mov     rax, [rcx]
0x180004bbc  mov     r8, rdi
0x180004bbf  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004bc6  mov     rax, [rax]
0x180004bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bce  mov     ebx, eax
0x180004bd0  jmp     short loc_180004B77
```
