# UL_APP_POOL::AcquireLockExclusive(void)

- ea: `0x180014a4c`
- end: `0x180014a87`
- name: `?AcquireLockExclusive@UL_APP_POOL@@AEAAXXZ`
- size: `59`
- prototype: `void __fastcall(UL_APP_POOL *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001060`
- `0x180014a90`

## callees

- `0x180014a4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014a6c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014a6c`

## pseudocode

```c
void __fastcall UL_APP_POOL::AcquireLockExclusive(UL_APP_POOL *this)
{
  _QWORD *v1; // rbx
  unsigned int i; // edi

  v1 = (_QWORD *)*((_QWORD *)this + 1);
  for ( i = 0; (unsigned __int64)i < v1[2]; ++i )
    AcquireSRWLockExclusive((PSRWLOCK)(*v1 + v1[1] * i));
}

```

## disassembly

```asm
0x180014a4c  mov     [rsp+arg_0], rbx
0x180014a51  push    rdi
0x180014a52  sub     rsp, 20h
0x180014a56  mov     rbx, [rcx+8]
0x180014a5a  xor     edi, edi
0x180014a5c  cmp     [rbx+10h], rdi
0x180014a60  jbe     short loc_180014A7C
0x180014a62  mov     ecx, edi
0x180014a64  imul    rcx, [rbx+8]
0x180014a69  add     rcx, [rbx]; SRWLock
0x180014a6c  call    cs:__imp_AcquireSRWLockExclusive
0x180014a72  inc     edi
0x180014a74  mov     eax, edi
0x180014a76  cmp     rax, [rbx+10h]
0x180014a7a  jb      short loc_180014A62
0x180014a7c  mov     rbx, [rsp+28h+arg_0]
0x180014a81  add     rsp, 20h
0x180014a85  pop     rdi
0x180014a86  retn
```
