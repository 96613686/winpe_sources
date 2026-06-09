# DeleteGroupEntry

- ea: `0x18001d1ec`
- end: `0x18001d299`
- name: `DeleteGroupEntry`
- size: `173`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c1a8`
- `0x18001d378`
- `0x18001decc`

## callees

- `0x180014d2c`
- `0x180015178`
- `0x18001d1ec`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001d28b`

## pseudocode

```c
BOOL __fastcall DeleteGroupEntry(_QWORD *a1)
{
  _QWORD *v1; // rax
  __int64 v3; // rdx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  _QWORD *v6; // rax

  v1 = a1 + 2;
  v3 = a1[2];
  if ( *(_QWORD **)(v3 + 8) != a1 + 2 )
    goto LABEL_6;
  v4 = (_QWORD *)a1[3];
  if ( (_QWORD *)*v4 != v1
    || (*v4 = v3,
        *(_QWORD *)(v3 + 8) = v4,
        AcquireWriteLock(&qword_18002BA10),
        AcquireWriteLock(&qword_18002BA30),
        AcquireWriteLock(a1 + 5),
        v5 = *a1,
        *(_QWORD **)(*a1 + 8LL) != a1)
    || (v6 = (_QWORD *)a1[1], (_QWORD *)*v6 != a1) )
  {
LABEL_6:
    __fastfail(3u);
  }
  *v6 = v5;
  *(_QWORD *)(v5 + 8) = v6;
  ReleaseWriteLock((__int64)(a1 + 5));
  ReleaseWriteLock((__int64)&qword_18002BA30);
  ReleaseWriteLock((__int64)&qword_18002BA10);
  return HeapFree(hHeap, 0, a1);
}

```

## disassembly

```asm
0x18001d1ec  mov     [rsp+arg_0], rbx
0x18001d1f1  push    rdi
0x18001d1f2  sub     rsp, 20h
0x18001d1f6  lea     rax, [rcx+10h]
0x18001d1fa  mov     rbx, rcx
0x18001d1fd  mov     rdx, [rax]
0x18001d200  cmp     [rdx+8], rax
0x18001d204  jnz     loc_18001D292
0x18001d20a  mov     rcx, [rax+8]
0x18001d20e  cmp     [rcx], rax
0x18001d211  jnz     short loc_18001D292
0x18001d213  mov     [rcx], rdx
0x18001d216  mov     [rdx+8], rcx
0x18001d21a  lea     rcx, qword_18002BA10
0x18001d221  call    AcquireWriteLock
0x18001d226  lea     rcx, qword_18002BA30
0x18001d22d  call    AcquireWriteLock
0x18001d232  lea     rcx, [rbx+28h]
0x18001d236  call    AcquireWriteLock
0x18001d23b  mov     rdx, [rbx]
0x18001d23e  cmp     [rdx+8], rbx
0x18001d242  jnz     short loc_18001D292
0x18001d244  mov     rax, [rbx+8]
0x18001d248  cmp     [rax], rbx
0x18001d24b  jnz     short loc_18001D292
0x18001d24d  mov     [rax], rdx
0x18001d250  lea     rcx, [rbx+28h]
0x18001d254  mov     [rdx+8], rax
0x18001d258  call    ReleaseWriteLock
0x18001d25d  lea     rcx, qword_18002BA30
0x18001d264  call    ReleaseWriteLock
0x18001d269  lea     rcx, qword_18002BA10
0x18001d270  call    ReleaseWriteLock
0x18001d275  mov     rcx, cs:hHeap
0x18001d27c  mov     r8, rbx
0x18001d27f  xor     edx, edx
0x18001d281  mov     rbx, [rsp+28h+arg_0]
0x18001d286  add     rsp, 20h
0x18001d28a  pop     rdi
0x18001d28b  jmp     cs:__imp_HeapFree
0x18001d292  mov     ecx, 3
0x18001d297  int     29h; Win8: RtlFailFast(ecx)
```
