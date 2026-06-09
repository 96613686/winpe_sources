# CWSHRemoteFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140001c60`
- end: `0x140001ce8`
- name: `?CreateInstance@CWSHRemoteFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(struct IClassFactory *this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001c60`
- `0x140002064`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall CWSHRemoteFactory::CreateInstance(
        struct IClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v7; // eax
  struct CWSHRemote *v8; // rbx
  unsigned int v9; // edi
  struct CWSHRemote *v10; // [rsp+68h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v10 = 0;
  v7 = CWSHRemote::Create((HINSTANCE)this[2].lpVtbl, this, &v10);
  v8 = v10;
  v9 = v7;
  if ( v7 >= 0 )
    v9 = (**(__int64 (__fastcall ***)(struct CWSHRemote *, const struct _GUID *, void **))v10)(v10, a3, a4);
  if ( v8 )
    (*(void (__fastcall **)(struct CWSHRemote *))(*(_QWORD *)v8 + 16LL))(v8);
  return v9;
}

```

## disassembly

```asm
0x140001c60  push    rbx
0x140001c62  push    rbp
0x140001c63  push    rsi
0x140001c64  push    rdi
0x140001c65  sub     rsp, 28h
0x140001c69  mov     rsi, r9
0x140001c6c  mov     rbp, r8
0x140001c6f  test    r9, r9
0x140001c72  jnz     short loc_140001C7B
0x140001c74  mov     eax, 80004003h
0x140001c79  jmp     short loc_140001CDF
0x140001c7b  mov     qword ptr [r9], 0
0x140001c82  test    rdx, rdx
0x140001c85  jz      short loc_140001C8E
0x140001c87  mov     eax, 80040110h
0x140001c8c  jmp     short loc_140001CDF
0x140001c8e  mov     rdx, rcx; struct IClassFactory *
0x140001c91  mov     [rsp+48h+arg_18], 0
0x140001c9a  mov     rcx, [rcx+10h]; HINSTANCE
0x140001c9e  lea     r8, [rsp+48h+arg_18]; struct CWSHRemote **
0x140001ca3  call    ?Create@CWSHRemote@@SAJPEAUHINSTANCE__@@PEAUIClassFactory@@PEAPEAV1@@Z; CWSHRemote::Create(HINSTANCE__ *,IClassFactory *,CWSHRemote * *)
0x140001ca8  mov     rbx, [rsp+48h+arg_18]
0x140001cad  mov     edi, eax
0x140001caf  test    eax, eax
0x140001cb1  js      short loc_140001CC9
0x140001cb3  mov     rax, [rbx]
0x140001cb6  mov     r8, rsi
0x140001cb9  mov     rdx, rbp
0x140001cbc  mov     rcx, rbx
0x140001cbf  mov     rax, [rax]
0x140001cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001cc7  mov     edi, eax
0x140001cc9  test    rbx, rbx
0x140001ccc  jz      short loc_140001CDD
0x140001cce  mov     rax, [rbx]
0x140001cd1  mov     rcx, rbx
0x140001cd4  mov     rax, [rax+10h]
0x140001cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001cdd  mov     eax, edi
0x140001cdf  add     rsp, 28h
0x140001ce3  pop     rdi
0x140001ce4  pop     rsi
0x140001ce5  pop     rbp
0x140001ce6  pop     rbx
0x140001ce7  retn
```
