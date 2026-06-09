# UL_APP_POOL::ReleaseLockExclusive(void)

- ea: `0x180014af8`
- end: `0x180014b33`
- name: `?ReleaseLockExclusive@UL_APP_POOL@@AEAAXXZ`
- size: `59`
- prototype: `void __fastcall(UL_APP_POOL *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001060`
- `0x180014a90`

## callees

- `0x180014af8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014b18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014b18`

## pseudocode

```c
void __fastcall UL_APP_POOL::ReleaseLockExclusive(UL_APP_POOL *this)
{
  _QWORD *v1; // rbx
  unsigned int i; // edi

  v1 = (_QWORD *)*((_QWORD *)this + 1);
  for ( i = 0; (unsigned __int64)i < v1[2]; ++i )
    ReleaseSRWLockExclusive((PSRWLOCK)(*v1 + v1[1] * i));
}

```

## disassembly

```asm
0x180014af8  mov     [rsp+arg_0], rbx
0x180014afd  push    rdi
0x180014afe  sub     rsp, 20h
0x180014b02  mov     rbx, [rcx+8]
0x180014b06  xor     edi, edi
0x180014b08  cmp     [rbx+10h], rdi
0x180014b0c  jbe     short loc_180014B28
0x180014b0e  mov     ecx, edi
0x180014b10  imul    rcx, [rbx+8]
0x180014b15  add     rcx, [rbx]; SRWLock
0x180014b18  call    cs:__imp_ReleaseSRWLockExclusive
0x180014b1e  inc     edi
0x180014b20  mov     eax, edi
0x180014b22  cmp     rax, [rbx+10h]
0x180014b26  jb      short loc_180014B0E
0x180014b28  mov     rbx, [rsp+28h+arg_0]
0x180014b2d  add     rsp, 20h
0x180014b31  pop     rdi
0x180014b32  retn
```
