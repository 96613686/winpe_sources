# RemoveAllEntries

- ea: `0x140008fb0`
- end: `0x140009074`
- name: `RemoveAllEntries`
- size: `196`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400163e4`
- `0x14001a334`

## callees

- `0x140008400`
- `0x140008fb0`
- `0x14000907c`

## pseudocode

```c
__int64 __fastcall RemoveAllEntries(__int64 a1, char a2)
{
  __int64 v2; // rax
  unsigned int v5; // edi
  __int64 **v6; // rsi
  unsigned __int64 v7; // r14
  __int64 *i; // rbx
  unsigned __int64 v9; // rax
  __int64 *v10; // rcx
  __int64 *v11; // rdx
  __int64 v12; // rax
  _QWORD *v13; // rdx

  v2 = *(_QWORD *)(a1 + 40);
  v5 = 0;
  v6 = *(__int64 ***)(v2 + 264);
  v7 = *(_QWORD *)(v2 + 296);
  for ( i = *v6; i != (__int64 *)v6; i = (__int64 *)*i )
  {
    if ( !a2 )
    {
      v9 = i[5];
      if ( !v9 || v7 <= v9 )
        continue;
    }
    v10 = i;
    *((_WORD *)i + 29) = 0;
    v11 = i;
    *((_OWORD *)i + 4) = 0;
    i = (__int64 *)i[1];
    v12 = v10[5];
    if ( *((_WORD *)v10 + 28) )
    {
      if ( !v12 )
      {
        ++v5;
        --*(_DWORD *)(*(_QWORD *)(a1 + 40) + 148LL);
      }
      v10[5] = v7;
      v11[4] = 0;
      RemoveEntry(v6, v11);
    }
    else
    {
      if ( !v12 )
      {
        ++v5;
        --*(_DWORD *)(*(_QWORD *)(a1 + 40) + 148LL);
      }
      RemoveEntry(v6, v11);
      DestroyEntry((__int64)v6, v13);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140008fb0  push    rbx
0x140008fb2  push    rbp
0x140008fb3  push    rsi
0x140008fb4  push    rdi
0x140008fb5  push    r12
0x140008fb7  push    r14
0x140008fb9  push    r15
0x140008fbb  sub     rsp, 20h
0x140008fbf  mov     rax, [rcx+28h]
0x140008fc3  xor     r12d, r12d
0x140008fc6  mov     r15b, dl
0x140008fc9  mov     rbp, rcx
0x140008fcc  mov     edi, r12d
0x140008fcf  mov     rsi, [rax+108h]
0x140008fd6  mov     r14, [rax+128h]
0x140008fdd  mov     rbx, [rsi]
0x140008fe0  jmp     short loc_14000905D
0x140008fe2  test    r15b, r15b
0x140008fe5  jnz     short loc_140008FF5
0x140008fe7  mov     rax, [rbx+28h]
0x140008feb  test    rax, rax
0x140008fee  jz      short loc_14000905A
0x140008ff0  cmp     r14, rax
0x140008ff3  jbe     short loc_14000905A
0x140008ff5  mov     rcx, rbx
0x140008ff8  mov     [rbx+3Ah], r12w
0x140008ffd  xorps   xmm0, xmm0
0x140009000  mov     rdx, rbx
0x140009003  movups  xmmword ptr [rbx+40h], xmm0
0x140009007  mov     rbx, [rbx+8]
0x14000900b  mov     rax, [rcx+28h]
0x14000900f  cmp     [rcx+38h], r12w
0x140009014  jnz     short loc_140009039
0x140009016  test    rax, rax
0x140009019  jnz     short loc_140009027
0x14000901b  mov     rax, [rbp+28h]
0x14000901f  inc     edi
0x140009021  dec     dword ptr [rax+94h]
0x140009027  mov     rcx, rsi
0x14000902a  call    RemoveEntry
0x14000902f  mov     rcx, rsi
0x140009032  call    DestroyEntry
0x140009037  jmp     short loc_14000905A
0x140009039  test    rax, rax
0x14000903c  jnz     short loc_14000904A
0x14000903e  mov     rax, [rbp+28h]
0x140009042  inc     edi
0x140009044  dec     dword ptr [rax+94h]
0x14000904a  mov     [rcx+28h], r14
0x14000904e  mov     rcx, rsi
0x140009051  mov     [rdx+20h], r12
0x140009055  call    RemoveEntry
0x14000905a  mov     rbx, [rbx]
0x14000905d  cmp     rbx, rsi
0x140009060  jnz     short loc_140008FE2
0x140009062  mov     eax, edi
0x140009064  add     rsp, 20h
0x140009068  pop     r15
0x14000906a  pop     r14
0x14000906c  pop     r12
0x14000906e  pop     rdi
0x14000906f  pop     rsi
0x140009070  pop     rbp
0x140009071  pop     rbx
0x140009072  retn
```
