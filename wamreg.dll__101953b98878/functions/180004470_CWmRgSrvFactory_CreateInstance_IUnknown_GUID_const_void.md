# CWmRgSrvFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004470`
- end: `0x180004516`
- name: `?CreateInstance@CWmRgSrvFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `166`
- prototype: `__int64 __fastcall(CWmRgSrvFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001044`
- `0x180004470`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CWmRgSrvFactory::CreateInstance(
        CWmRgSrvFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 (__fastcall ***v8)(void *, const struct _GUID *, void **); // rcx

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v8 = (__int64 (__fastcall ***)(void *, const struct _GUID *, void **))*((_QWORD *)this + 1);
  if ( v8 )
    return (**v8)(v8, a3, a4);
  v8 = (__int64 (__fastcall ***)(void *, const struct _GUID *, void **))operator new(0x18u);
  if ( v8 )
  {
    *((_DWORD *)v8 + 3) = 1;
    *v8 = (__int64 (__fastcall **)(void *, const struct _GUID *, void **))&CWmRgSrv::`vftable';
    v8[2] = 0;
    _InterlockedIncrement((volatile signed __int32 *)&g_dwRefCount);
    *((_QWORD *)this + 1) = v8;
    return (**v8)(v8, a3, a4);
  }
  *((_QWORD *)this + 1) = 0;
  return 2147942414LL;
}

```

## disassembly

```asm
0x180004470  mov     [rsp+arg_0], rbx
0x180004475  mov     [rsp+arg_8], rsi
0x18000447a  push    rdi
0x18000447b  sub     rsp, 20h
0x18000447f  mov     rdi, r9
0x180004482  mov     rsi, r8
0x180004485  mov     rbx, rcx
0x180004488  test    r9, r9
0x18000448b  jz      short loc_180004501
0x18000448d  mov     qword ptr [r9], 0
0x180004494  test    rdx, rdx
0x180004497  jz      short loc_1800044A0
0x180004499  mov     eax, 80040110h
0x18000449e  jmp     short loc_180004506
0x1800044a0  mov     rcx, [rcx+8]
0x1800044a4  test    rcx, rcx
0x1800044a7  jnz     short loc_1800044DF
0x1800044a9  mov     ecx, 18h; Size
0x1800044ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800044b3  mov     rcx, rax
0x1800044b6  test    rax, rax
0x1800044b9  jz      short loc_1800044F2
0x1800044bb  lea     rax, ??_7CWmRgSrv@@6B@; const CWmRgSrv::`vftable'
0x1800044c2  mov     dword ptr [rcx+0Ch], 1
0x1800044c9  mov     [rcx], rax
0x1800044cc  mov     qword ptr [rcx+10h], 0
0x1800044d4  lock inc cs:?g_dwRefCount@@3KA; ulong g_dwRefCount
0x1800044db  mov     [rbx+8], rcx
0x1800044df  mov     rax, [rcx]
0x1800044e2  mov     r8, rdi
0x1800044e5  mov     rdx, rsi
0x1800044e8  mov     rax, [rax]
0x1800044eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044f0  jmp     short loc_180004506
0x1800044f2  mov     qword ptr [rbx+8], 0
0x1800044fa  mov     eax, 8007000Eh
0x1800044ff  jmp     short loc_180004506
0x180004501  mov     eax, 80070057h
0x180004506  mov     rbx, [rsp+28h+arg_0]
0x18000450b  mov     rsi, [rsp+28h+arg_8]
0x180004510  add     rsp, 20h
0x180004514  pop     rdi
0x180004515  retn
```
