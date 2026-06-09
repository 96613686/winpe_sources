# PkCompleteRemoval

- ea: `0x1400150a0`
- end: `0x140015143`
- name: `PkCompleteRemoval`
- size: `163`
- prototype: ``
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
  unsigned int v3; // r11d
  unsigned int v4; // edi
  __int64 v5; // r10
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
  v3 = a2;
  v4 = *(_DWORD *)(a1 + 40);
  v5 = a1;
  if ( *v2 == (_DWORD)a2 )
  {
    LOBYTE(a2) = 1;
    PkpExpectInterrupt(a1, a2);
  }
  *(_DWORD *)(v5 + 68) = v3;
  v2[1] = v3;
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
0x1400150ae  mov     r11d, edx
0x1400150b1  mov     edi, [rcx+28h]
0x1400150b4  mov     r10, rcx
0x1400150b7  mov     eax, [rbx]
0x1400150b9  cmp     eax, edx
0x1400150bb  jnz     short loc_1400150C4
0x1400150bd  mov     dl, 1
0x1400150bf  call    PkpExpectInterrupt
0x1400150c4  mov     r9d, [r10+44h]
0x1400150c8  mov     [r10+44h], r11d
0x1400150cc  mov     [rbx+4], r11d
0x1400150d0  lock or [rsp+28h+var_28], 0
0x1400150d5  mov     r8d, [rbx+0Ch]
0x1400150d9  mov     ecx, edi
0x1400150db  mov     edx, [rbx]
0x1400150dd  call    PkpValidatePointer
0x1400150e2  test    al, al
0x1400150e4  jnz     short loc_1400150ED
0x1400150e6  mov     eax, 0C0000102h
0x1400150eb  jmp     short loc_140015137
0x1400150ed  mov     [r10+40h], edx
0x1400150f1  and     r8d, 0FFFFFFF8h
0x1400150f5  jz      short loc_14001512A
0x1400150f7  sub     r9d, edx
0x1400150fa  mov     ecx, r11d
0x1400150fd  add     r9d, 0FFFFFFF8h
0x140015101  cmp     r9d, edi
0x140015104  lea     eax, [r9+rdi]
0x140015108  cmovnb  r9d, eax
0x14001510c  sub     ecx, edx
0x14001510e  add     ecx, 0FFFFFFF8h
0x140015111  cmp     ecx, edi
0x140015113  lea     eax, [rcx+rdi]
0x140015116  cmovnb  ecx, eax
0x140015119  cmp     ecx, r8d
0x14001511c  jb      short loc_14001512A
0x14001511e  cmp     r9d, r8d
0x140015121  jnb     short loc_14001512A
0x140015123  mov     eax, 214h
0x140015128  jmp     short loc_140015137
0x14001512a  xor     eax, eax
0x14001512c  mov     ecx, 213h
0x140015131  cmp     r11d, edx
0x140015134  cmovz   eax, ecx
0x140015137  mov     rbx, [rsp+28h+arg_0]
0x14001513c  add     rsp, 20h
0x140015140  pop     rdi
0x140015141  retn
```
