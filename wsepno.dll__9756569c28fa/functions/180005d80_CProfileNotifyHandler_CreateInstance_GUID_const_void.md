# CProfileNotifyHandler_CreateInstance(_GUID const &,void * *)

- ea: `0x180005d80`
- end: `0x180005e02`
- name: `?CProfileNotifyHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `130`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001b78`
- `0x180005d80`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall CProfileNotifyHandler_CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // edi
  _DWORD *v5; // rbx

  *a2 = 0;
  v4 = -2147024882;
  v5 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    ++g_cRefDll;
    *(_QWORD *)v5 = &CProfileNotifyHandler::`vftable';
    v5[2] = 1;
    v4 = ((__int64 (__fastcall *)(_DWORD *, const struct _GUID *, void **))CProfileNotifyHandler::`vftable')(v5, a1, a2);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return v4;
}

```

## disassembly

```asm
0x180005d80  push    rbx
0x180005d82  push    rbp
0x180005d83  push    rsi
0x180005d84  push    rdi
0x180005d85  sub     rsp, 28h
0x180005d89  mov     rsi, rdx
0x180005d8c  mov     qword ptr [rdx], 0
0x180005d93  mov     rbp, rcx
0x180005d96  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005d9d  mov     ecx, 10h; unsigned __int64
0x180005da2  mov     edi, 8007000Eh
0x180005da7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005dac  mov     [rsp+48h+arg_8], rax
0x180005db1  mov     rbx, rax
0x180005db4  test    rax, rax
0x180005db7  jz      short loc_180005DF7
0x180005db9  inc     cs:?g_cRefDll@@3JA; long g_cRefDll
0x180005dbf  lea     rax, ??_7CProfileNotifyHandler@@6B@; const CProfileNotifyHandler::`vftable'
0x180005dc6  mov     [rbx], rax
0x180005dc9  mov     dword ptr [rbx+8], 1
0x180005dd0  test    rbx, rbx
0x180005dd3  jz      short loc_180005DF7
0x180005dd5  mov     rax, [rax]
0x180005dd8  mov     r8, rsi
0x180005ddb  mov     rdx, rbp
0x180005dde  mov     rcx, rbx
0x180005de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de6  mov     rdx, [rbx]
0x180005de9  mov     edi, eax
0x180005deb  mov     rcx, rbx
0x180005dee  mov     rax, [rdx+10h]
0x180005df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df7  mov     eax, edi
0x180005df9  add     rsp, 28h
0x180005dfd  pop     rdi
0x180005dfe  pop     rsi
0x180005dff  pop     rbp
0x180005e00  pop     rbx
0x180005e01  retn
```
