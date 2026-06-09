# CProfileNotificationHandler_CreateInstance(_GUID const &,void * *)

- ea: `0x180006460`
- end: `0x1800064ce`
- name: `?CProfileNotificationHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `110`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001e00`
- `0x180006460`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CProfileNotificationHandler_CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // edi
  _DWORD *v5; // rax
  _DWORD *v6; // rbx

  v4 = -2147024882;
  v5 = operator new(0x10u);
  v6 = v5;
  if ( v5 )
  {
    v5[2] = 1;
    *(_QWORD *)v5 = &CProfileNotificationHandler::`vftable';
    _InterlockedIncrement(&g_cRefCount);
    v4 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v5)(v5, a1, a2);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x180006460  push    rbx
0x180006462  push    rbp
0x180006463  push    rsi
0x180006464  push    rdi
0x180006465  sub     rsp, 28h
0x180006469  mov     rbp, rcx
0x18000646c  mov     rsi, rdx
0x18000646f  mov     ecx, 10h; Size
0x180006474  mov     edi, 8007000Eh
0x180006479  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000647e  mov     rbx, rax
0x180006481  test    rax, rax
0x180006484  jz      short loc_1800064C3
0x180006486  lea     rax, ??_7CProfileNotificationHandler@@6B@; const CProfileNotificationHandler::`vftable'
0x18000648d  mov     dword ptr [rbx+8], 1
0x180006494  mov     [rbx], rax
0x180006497  lock inc cs:?g_cRefCount@@3JA; long g_cRefCount
0x18000649e  mov     rax, [rbx]
0x1800064a1  mov     r8, rsi
0x1800064a4  mov     rdx, rbp
0x1800064a7  mov     rcx, rbx
0x1800064aa  mov     rax, [rax]
0x1800064ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064b2  mov     rcx, [rbx]
0x1800064b5  mov     edi, eax
0x1800064b7  mov     rax, [rcx+10h]
0x1800064bb  mov     rcx, rbx
0x1800064be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064c3  mov     eax, edi
0x1800064c5  add     rsp, 28h
0x1800064c9  pop     rdi
0x1800064ca  pop     rsi
0x1800064cb  pop     rbp
0x1800064cc  pop     rbx
0x1800064cd  retn
```
