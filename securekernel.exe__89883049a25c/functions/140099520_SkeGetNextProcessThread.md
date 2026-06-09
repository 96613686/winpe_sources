# SkeGetNextProcessThread

- ea: `0x140099520`
- end: `0x1400995a8`
- name: `SkeGetNextProcessThread`
- size: `136`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1400afb08`
- `0x1400afebc`
- `0x1400bdd10`
- `0x1400bef5c`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x140034154`
- `0x140099520`
- `0x1400b5a84`

## pseudocode

```c
_QWORD *__fastcall SkeGetNextProcessThread(__int64 a1, _QWORD **a2)
{
  __int64 v2; // r14
  _QWORD **v4; // rsi
  char v5; // al
  __int64 v6; // rdx
  _QWORD **v7; // rcx
  char v8; // r9
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi

  v2 = a1 + 4;
  v4 = (_QWORD **)(a1 + 16);
  v5 = SkAcquireSpinLockExclusive(a1 + 4);
  v7 = a2;
  v8 = v5;
  if ( !a2 )
    v7 = v4;
  v9 = *v7;
  if ( v4 == *v7 )
  {
    v10 = 0;
  }
  else
  {
    do
    {
      v10 = v9;
      if ( (unsigned __int8)SkAcquireRundownProtection(v9 + 27) )
        break;
      v9 = (_QWORD *)*v9;
    }
    while ( v4 != v9 );
  }
  LOBYTE(v6) = v8;
  SkReleaseSpinLockExclusive(v2, v6);
  if ( a2 )
    SkReleaseRundownProtection(a2 + 27, 0);
  if ( v4 == v9 )
    return 0;
  return v10;
}

```

## disassembly

```asm
0x140099520  push    rbx
0x140099522  push    rbp
0x140099523  push    rsi
0x140099524  push    rdi
0x140099525  push    r14
0x140099527  sub     rsp, 20h
0x14009952b  lea     r14, [rcx+4]
0x14009952f  mov     rbp, rdx
0x140099532  lea     rsi, [rcx+10h]
0x140099536  mov     rcx, r14
0x140099539  call    SkAcquireSpinLockExclusive
0x14009953e  test    rbp, rbp
0x140099541  mov     rcx, rbp
0x140099544  mov     r9b, al
0x140099547  cmovz   rcx, rsi
0x14009954b  mov     rbx, [rcx]
0x14009954e  cmp     rsi, rbx
0x140099551  jz      short loc_140099570
0x140099553  lea     rcx, [rbx+0D8h]
0x14009955a  mov     rdi, rbx
0x14009955d  call    SkAcquireRundownProtection
0x140099562  test    al, al
0x140099564  jnz     short loc_140099572
0x140099566  mov     rbx, [rbx]
0x140099569  cmp     rsi, rbx
0x14009956c  jnz     short loc_140099553
0x14009956e  jmp     short loc_140099572
0x140099570  xor     edi, edi
0x140099572  mov     dl, r9b
0x140099575  mov     rcx, r14
0x140099578  call    SkReleaseSpinLockExclusive
0x14009957d  test    rbp, rbp
0x140099580  jz      short loc_140099590
0x140099582  lea     rcx, [rbp+0D8h]
0x140099589  xor     edx, edx
0x14009958b  call    SkReleaseRundownProtection
0x140099590  xor     ecx, ecx
0x140099592  cmp     rsi, rbx
0x140099595  cmovz   rdi, rcx
0x140099599  mov     rax, rdi
0x14009959c  add     rsp, 20h
0x1400995a0  pop     r14
0x1400995a2  pop     rdi
0x1400995a3  pop     rsi
0x1400995a4  pop     rbp
0x1400995a5  pop     rbx
0x1400995a6  retn
```
