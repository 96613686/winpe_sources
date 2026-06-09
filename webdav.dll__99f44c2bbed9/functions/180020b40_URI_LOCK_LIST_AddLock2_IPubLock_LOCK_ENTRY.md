# URI_LOCK_LIST::AddLock2(IPubLock *,LOCK_ENTRY * *)

- ea: `0x180020b40`
- end: `0x180020c53`
- name: `?AddLock2@URI_LOCK_LIST@@QEAAJPEAVIPubLock@@PEAPEAULOCK_ENTRY@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(URI_LOCK_LIST *__hidden this, struct IPubLock *, struct LOCK_ENTRY **)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800209c0`
- `0x180020c60`
- `0x180020c90`
- `0x180020e10`

## callees

- `0x1800011d4`
- `0x180020b40`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180020b83`
- `msvcrt!_wcsicmp` at `0x180020b83`

## pseudocode

```c
__int64 __fastcall URI_LOCK_LIST::AddLock2(URI_LOCK_LIST *this, struct IPubLock *a2, struct LOCK_ENTRY **a3)
{
  __int64 v3; // rax
  const wchar_t *v7; // rbx
  const wchar_t *v8; // rax
  __int64 v10; // rsi
  _QWORD *v11; // rax
  _QWORD *v12; // rbx
  struct LOCK_ENTRY *v13; // rsi

  v3 = *(_QWORD *)a2;
  *a3 = 0;
  v7 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IPubLock *))(v3 + 32))(a2);
  v8 = (const wchar_t *)(*(__int64 (__fastcall **)(URI_LOCK_LIST *))(*(_QWORD *)this + 16LL))(this);
  if ( _wcsicmp(v8, v7) )
    return 2147942487LL;
  v10 = *((_QWORD *)this + 92);
  if ( *(_DWORD *)(v10 + 648) < 0x10u )
  {
    v12 = (_QWORD *)*((_QWORD *)this + 92);
  }
  else
  {
    v11 = operator new(0x290u);
    v12 = v11;
    if ( !v11 )
      return 2147942414LL;
    v11[80] = 0;
    *((_DWORD *)v11 + 162) = 0;
    *(_QWORD *)(v10 + 640) = v11;
  }
  v13 = (struct LOCK_ENTRY *)&v12[5 * *((unsigned int *)v12 + 162)];
  *(_QWORD *)v13 = a2;
  *((_QWORD *)v13 + 1) = this;
  *((_QWORD *)v13 + 2) = (*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 24LL))(a2);
  (*(void (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 8LL))(a2);
  ++*((_DWORD *)v12 + 162);
  if ( (*(unsigned int (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 72LL))(a2) )
    ++*((_DWORD *)this + 187);
  else
    ++*((_DWORD *)this + 186);
  *a3 = v13;
  return 0;
}

```

## disassembly

```asm
0x180020b40  push    rbx
0x180020b42  push    rsi
0x180020b43  push    rdi
0x180020b44  push    r14
0x180020b46  push    r15
0x180020b48  sub     rsp, 20h
0x180020b4c  mov     rax, [rdx]
0x180020b4f  mov     rdi, rcx
0x180020b52  mov     rcx, rdx
0x180020b55  mov     qword ptr [r8], 0
0x180020b5c  mov     r15, r8
0x180020b5f  mov     r14, rdx
0x180020b62  mov     rax, [rax+20h]
0x180020b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b6b  mov     r9, [rdi]
0x180020b6e  mov     rbx, rax
0x180020b71  mov     rcx, rdi
0x180020b74  mov     rax, [r9+10h]
0x180020b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b7d  mov     rdx, rbx; String2
0x180020b80  mov     rcx, rax; String1
0x180020b83  call    cs:__imp__wcsicmp
0x180020b89  test    eax, eax
0x180020b8b  jz      short loc_180020B97
0x180020b8d  mov     eax, 80070057h
0x180020b92  jmp     loc_180020C47
0x180020b97  mov     rsi, [rdi+2E0h]
0x180020b9e  cmp     dword ptr [rsi+288h], 10h
0x180020ba5  jb      short loc_180020BE1
0x180020ba7  mov     ecx, 290h; Size
0x180020bac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020bb1  mov     rbx, rax
0x180020bb4  test    rax, rax
0x180020bb7  jnz     short loc_180020BC3
0x180020bb9  mov     eax, 8007000Eh
0x180020bbe  jmp     loc_180020C47
0x180020bc3  mov     qword ptr [rax+280h], 0
0x180020bce  mov     dword ptr [rax+288h], 0
0x180020bd8  mov     [rsi+280h], rax
0x180020bdf  jmp     short loc_180020BE4
0x180020be1  mov     rbx, rsi
0x180020be4  mov     eax, [rbx+288h]
0x180020bea  lea     rcx, [rax+rax*4]
0x180020bee  lea     rsi, [rbx+rcx*8]
0x180020bf2  mov     rcx, r14
0x180020bf5  mov     [rsi], r14
0x180020bf8  mov     [rsi+8], rdi
0x180020bfc  mov     rax, [r14]
0x180020bff  mov     rax, [rax+18h]
0x180020c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c08  mov     [rsi+10h], rax
0x180020c0c  mov     rcx, r14
0x180020c0f  mov     rax, [r14]
0x180020c12  mov     rax, [rax+8]
0x180020c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c1b  inc     dword ptr [rbx+288h]
0x180020c21  mov     rcx, r14
0x180020c24  mov     rax, [r14]
0x180020c27  mov     rax, [rax+48h]
0x180020c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c30  test    eax, eax
0x180020c32  jnz     short loc_180020C3C
0x180020c34  inc     dword ptr [rdi+2E8h]
0x180020c3a  jmp     short loc_180020C42
0x180020c3c  inc     dword ptr [rdi+2ECh]
0x180020c42  mov     [r15], rsi
0x180020c45  xor     eax, eax
0x180020c47  add     rsp, 20h
0x180020c4b  pop     r15
0x180020c4d  pop     r14
0x180020c4f  pop     rdi
0x180020c50  pop     rsi
0x180020c51  pop     rbx
0x180020c52  retn
```
