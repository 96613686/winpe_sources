# SclMultiSzFindNextString

- ea: `0x18000a7f0`
- end: `0x18000a8bb`
- name: `SclMultiSzFindNextString`
- size: `203`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, unsigned __int64, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002cc8`
- `0x180004c88`
- `0x1800109f0`

## callees

- `0x180005938`
- `0x18000a7f0`

## pseudocode

```c
__int64 __fastcall SclMultiSzFindNextString(
        unsigned __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        _QWORD *a5)
{
  _QWORD *v7; // rbx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  __int64 result; // rax
  _WORD *v11; // r9
  int v12; // eax
  __int64 v13; // r11
  __int64 v14; // rcx
  __int64 v15; // [rsp+30h] [rbp+8h] BYREF

  if ( !a1 || a3 && (a3 < a1 || a3 > a1 + 2 * a2) )
    return 3221225485LL;
  if ( !a4 )
    return 3221225485LL;
  v7 = a5;
  if ( !a5 )
    return 3221225485LL;
  if ( !a3 )
  {
    v8 = 0;
    goto LABEL_15;
  }
  v9 = (__int64)(a3 - a1) >> 1;
  v8 = v9;
  if ( v9 >= a2 )
    return 2147483674LL;
  while ( *(_WORD *)(a1 + 2 * v8) )
  {
    if ( ++v8 >= a2 )
      return 2147483674LL;
  }
  if ( v8 > v9 )
  {
    ++v8;
LABEL_15:
    if ( v8 < a2 )
      goto LABEL_16;
    return 2147483674LL;
  }
LABEL_16:
  v11 = (_WORD *)(a1 + 2 * v8);
  if ( !*v11 )
    return 2147483674LL;
  v15 = 0;
  *a4 = v11;
  v12 = RtlStringCchLengthW(a1 + 2 * v8, a2 - v8, &v15);
  v14 = v15;
  if ( v12 < 0 )
    v14 = v13;
  result = 0;
  *v7 = v14;
  return result;
}

```

## disassembly

```asm
0x18000a7f0  mov     [rsp+arg_8], rbx
0x18000a7f5  push    rdi
0x18000a7f6  sub     rsp, 20h
0x18000a7fa  mov     rdi, r9
0x18000a7fd  mov     r11, rdx
0x18000a800  mov     r10, rcx
0x18000a803  test    rcx, rcx
0x18000a806  jz      loc_18000A8AB
0x18000a80c  test    r8, r8
0x18000a80f  jz      short loc_18000A827
0x18000a811  cmp     r8, rcx
0x18000a814  jb      loc_18000A8AB
0x18000a81a  lea     rax, [rcx+rdx*2]
0x18000a81e  cmp     r8, rax
0x18000a821  ja      loc_18000A8AB
0x18000a827  test    rdi, rdi
0x18000a82a  jz      short loc_18000A8AB
0x18000a82c  mov     rbx, [rsp+28h+arg_20]
0x18000a831  test    rbx, rbx
0x18000a834  jz      short loc_18000A8AB
0x18000a836  test    r8, r8
0x18000a839  jnz     short loc_18000A83F
0x18000a83b  xor     ecx, ecx
0x18000a83d  jmp     short loc_18000A86D
0x18000a83f  sub     r8, r10
0x18000a842  sar     r8, 1
0x18000a845  mov     rcx, r8
0x18000a848  cmp     r8, r11
0x18000a84b  jnb     short loc_18000A85E
0x18000a84d  xor     eax, eax
0x18000a84f  cmp     ax, [r10+rcx*2]
0x18000a854  jz      short loc_18000A865
0x18000a856  inc     rcx
0x18000a859  cmp     rcx, r11
0x18000a85c  jb      short loc_18000A84D
0x18000a85e  mov     eax, 8000001Ah
0x18000a863  jmp     short loc_18000A8B0
0x18000a865  cmp     rcx, r8
0x18000a868  jbe     short loc_18000A872
0x18000a86a  inc     rcx
0x18000a86d  cmp     rcx, r11
0x18000a870  jnb     short loc_18000A85E
0x18000a872  lea     r9, [r10+rcx*2]
0x18000a876  xor     eax, eax
0x18000a878  cmp     ax, [r9]
0x18000a87c  jz      short loc_18000A85E
0x18000a87e  sub     r11, rcx
0x18000a881  mov     [rsp+28h+arg_0], rax
0x18000a886  mov     rdx, r11
0x18000a889  mov     [rdi], r9
0x18000a88c  lea     r8, [rsp+28h+arg_0]
0x18000a891  mov     rcx, r9
0x18000a894  call    RtlStringCchLengthW
0x18000a899  mov     rcx, [rsp+28h+arg_0]
0x18000a89e  test    eax, eax
0x18000a8a0  cmovs   rcx, r11
0x18000a8a4  xor     eax, eax
0x18000a8a6  mov     [rbx], rcx
0x18000a8a9  jmp     short loc_18000A8B0
0x18000a8ab  mov     eax, 0C000000Dh
0x18000a8b0  mov     rbx, [rsp+28h+arg_8]
0x18000a8b5  add     rsp, 20h
0x18000a8b9  pop     rdi
0x18000a8ba  retn
```
