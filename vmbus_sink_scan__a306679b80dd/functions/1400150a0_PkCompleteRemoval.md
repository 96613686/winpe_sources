# PkCompleteRemoval

- ea: `0x1400150a0`
- end: `0x140015145`
- name: `PkCompleteRemoval`
- size: `165`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002000`
- `0x14000aae0`
- `0x140015a60`
- `0x14001661c`

## callees

- `0x1400150a0`
- `0x1400154bc`
- `0x1400155c8`

## pseudocode

```c
__int64 __fastcall PkCompleteRemoval(__int64 a1, __int64 a2)
{
  unsigned int *v2; // rbx
  __int64 v3; // r10
  unsigned int v4; // edi
  unsigned int v5; // r11d
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // r10
  int v10; // r11d
  __int64 result; // rax
  unsigned int v12; // r8d
  unsigned int v13; // r9d
  unsigned int v14; // ecx
  signed __int32 v15[10]; // [rsp+0h] [rbp-28h] BYREF

  v2 = *(unsigned int **)(a1 + 24);
  v3 = a1;
  v4 = *(_DWORD *)(a1 + 40);
  v5 = a2;
  if ( *v2 == (unsigned __int64)(unsigned int)a2 )
  {
    LOBYTE(a2) = 1;
    PkpExpectInterrupt(a1, a2);
  }
  *(_DWORD *)(v3 + 68) = v5;
  v2[1] = v5;
  _InterlockedOr(v15, 0);
  if ( !(unsigned __int8)PkpValidatePointer(v4, *v2) )
    return 3221225730LL;
  *(_DWORD *)(v9 + 64) = v6;
  v12 = v7 & 0xFFFFFFF8;
  if ( v12 )
  {
    v13 = v8 - v6 - 8;
    if ( v13 >= v4 )
      v13 += v4;
    v14 = v10 - v6 - 8;
    if ( v14 >= v4 )
      v14 += v4;
    if ( v14 >= v12 && v13 < v12 )
      return 532;
  }
  result = 0;
  if ( v10 == v6 )
    return 531;
  return result;
}

```

## disassembly

```asm
0x1400150a0  mov     [rsp+arg_0], rbx
0x1400150a5  push    rdi
0x1400150a6  sub     rsp, 20h
0x1400150aa  mov     rbx, [rcx+18h]
0x1400150ae  mov     r10, rcx
0x1400150b1  mov     edi, [rcx+28h]
0x1400150b4  mov     r11d, edx
0x1400150b7  movsxd  rax, dword ptr [rbx]
0x1400150ba  cmp     rax, r11
0x1400150bd  jnz     short loc_1400150C6
0x1400150bf  mov     dl, 1
0x1400150c1  call    PkpExpectInterrupt
0x1400150c6  mov     r9d, [r10+44h]
0x1400150ca  mov     [r10+44h], r11d
0x1400150ce  mov     [rbx+4], r11d
0x1400150d2  lock or [rsp+28h+var_28], 0
0x1400150d7  mov     r8d, [rbx+0Ch]
0x1400150db  mov     ecx, edi
0x1400150dd  mov     edx, [rbx]
0x1400150df  call    PkpValidatePointer
0x1400150e4  test    al, al
0x1400150e6  jnz     short loc_1400150EF
0x1400150e8  mov     eax, 0C0000102h
0x1400150ed  jmp     short loc_140015139
0x1400150ef  mov     [r10+40h], edx
0x1400150f3  and     r8d, 0FFFFFFF8h
0x1400150f7  jz      short loc_14001512C
0x1400150f9  sub     r9d, edx
0x1400150fc  mov     ecx, r11d
0x1400150ff  add     r9d, 0FFFFFFF8h
0x140015103  cmp     r9d, edi
0x140015106  lea     eax, [r9+rdi]
0x14001510a  cmovnb  r9d, eax
0x14001510e  sub     ecx, edx
0x140015110  add     ecx, 0FFFFFFF8h
0x140015113  cmp     ecx, edi
0x140015115  lea     eax, [rcx+rdi]
0x140015118  cmovnb  ecx, eax
0x14001511b  cmp     ecx, r8d
0x14001511e  jb      short loc_14001512C
0x140015120  cmp     r9d, r8d
0x140015123  jnb     short loc_14001512C
0x140015125  mov     eax, 214h
0x14001512a  jmp     short loc_140015139
0x14001512c  xor     eax, eax
0x14001512e  mov     ecx, 213h
0x140015133  cmp     r11d, edx
0x140015136  cmovz   eax, ecx
0x140015139  mov     rbx, [rsp+28h+arg_0]
0x14001513e  add     rsp, 20h
0x140015142  pop     rdi
0x140015143  retn
```
