# URI_LOCK_LIST::AddLock2(IPubLock *,LOCK_ENTRY * *)

- ea: `0x180003058`
- end: `0x18000316b`
- name: `?AddLock2@URI_LOCK_LIST@@QEAAJPEAVIPubLock@@PEAPEAULOCK_ENTRY@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(URI_LOCK_LIST *__hidden this, struct IPubLock *, struct LOCK_ENTRY **)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002dc0`
- `0x180003180`
- `0x1800031b0`
- `0x180003450`

## callees

- `0x180001008`
- `0x180003058`
- `0x180004010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000309b`
- `msvcrt!_wcsicmp` at `0x18000309b`

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
0x180003058  push    rbx
0x18000305a  push    rsi
0x18000305b  push    rdi
0x18000305c  push    r14
0x18000305e  push    r15
0x180003060  sub     rsp, 20h
0x180003064  mov     rax, [rdx]
0x180003067  mov     rdi, rcx
0x18000306a  mov     rcx, rdx
0x18000306d  mov     qword ptr [r8], 0
0x180003074  mov     r15, r8
0x180003077  mov     r14, rdx
0x18000307a  mov     rax, [rax+20h]
0x18000307e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003083  mov     r9, [rdi]
0x180003086  mov     rbx, rax
0x180003089  mov     rcx, rdi
0x18000308c  mov     rax, [r9+10h]
0x180003090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003095  mov     rdx, rbx; String2
0x180003098  mov     rcx, rax; String1
0x18000309b  call    cs:__imp__wcsicmp
0x1800030a1  test    eax, eax
0x1800030a3  jz      short loc_1800030AF
0x1800030a5  mov     eax, 80070057h
0x1800030aa  jmp     loc_18000315F
0x1800030af  mov     rsi, [rdi+2E0h]
0x1800030b6  cmp     dword ptr [rsi+288h], 10h
0x1800030bd  jb      short loc_1800030F9
0x1800030bf  mov     ecx, 290h; Size
0x1800030c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800030c9  mov     rbx, rax
0x1800030cc  test    rax, rax
0x1800030cf  jnz     short loc_1800030DB
0x1800030d1  mov     eax, 8007000Eh
0x1800030d6  jmp     loc_18000315F
0x1800030db  mov     qword ptr [rax+280h], 0
0x1800030e6  mov     dword ptr [rax+288h], 0
0x1800030f0  mov     [rsi+280h], rax
0x1800030f7  jmp     short loc_1800030FC
0x1800030f9  mov     rbx, rsi
0x1800030fc  mov     eax, [rbx+288h]
0x180003102  lea     rcx, [rax+rax*4]
0x180003106  lea     rsi, [rbx+rcx*8]
0x18000310a  mov     rcx, r14
0x18000310d  mov     [rsi], r14
0x180003110  mov     [rsi+8], rdi
0x180003114  mov     rax, [r14]
0x180003117  mov     rax, [rax+18h]
0x18000311b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003120  mov     [rsi+10h], rax
0x180003124  mov     rcx, r14
0x180003127  mov     rax, [r14]
0x18000312a  mov     rax, [rax+8]
0x18000312e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003133  inc     dword ptr [rbx+288h]
0x180003139  mov     rcx, r14
0x18000313c  mov     rax, [r14]
0x18000313f  mov     rax, [rax+48h]
0x180003143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003148  test    eax, eax
0x18000314a  jnz     short loc_180003154
0x18000314c  inc     dword ptr [rdi+2E8h]
0x180003152  jmp     short loc_18000315A
0x180003154  inc     dword ptr [rdi+2ECh]
0x18000315a  mov     [r15], rsi
0x18000315d  xor     eax, eax
0x18000315f  add     rsp, 20h
0x180003163  pop     r15
0x180003165  pop     r14
0x180003167  pop     rdi
0x180003168  pop     rsi
0x180003169  pop     rbx
0x18000316a  retn
```
