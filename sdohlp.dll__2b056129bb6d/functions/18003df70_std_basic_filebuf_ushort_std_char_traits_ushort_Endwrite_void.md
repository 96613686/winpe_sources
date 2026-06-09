# std::basic_filebuf<ushort,std::char_traits<ushort>>::_Endwrite(void)

- ea: `0x18003df70`
- end: `0x18003e0d2`
- name: `?_Endwrite@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAA_NXZ`
- size: `354`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180039400`
- `0x18003fb90`
- `0x18003fca0`

## callees

- `0x180038ed4`
- `0x18003df70`
- `0x18003e6e4`
- `0x18003e7d8`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `msvcrt!fwrite` at `0x18003e06e`
- `msvcrt!fwrite` at `0x18003e06e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall std::basic_filebuf<unsigned short>::_Endwrite(__int64 a1)
{
  void **v3; // r11
  unsigned __int64 v4; // r10
  void **v5; // r9
  void **v6; // r8
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  char v10; // bl
  void **v11; // rax
  signed __int64 v12; // rdi
  void **v13; // rcx
  void **v14; // [rsp+30h] [rbp-38h] BYREF
  void *Buffer[3]; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int64 v16; // [rsp+50h] [rbp-18h]

  if ( !*(_QWORD *)(a1 + 120) || !*(_BYTE *)(a1 + 130) )
    return 1;
  v14 = 0;
  if ( (*(unsigned __int16 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFF) == 0xFFFF )
    return 0;
  std::string::string(Buffer, 8);
LABEL_6:
  v3 = (void **)Buffer[0];
  v4 = v16;
  while ( 1 )
  {
    v5 = Buffer;
    if ( v4 >= 0x10 )
      v5 = v3;
    v6 = Buffer;
    if ( v4 >= 0x10 )
      v6 = v3;
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, void **, char *, void ***))(**(_QWORD **)(a1 + 120) + 64LL))(
           *(_QWORD *)(a1 + 120),
           a1 + 132,
           v6,
           (char *)Buffer[2] + (unsigned __int64)v5,
           &v14);
    if ( !v7 )
    {
      *(_BYTE *)(a1 + 130) = 0;
      goto LABEL_16;
    }
    v9 = v7 - 1;
    if ( v9 )
      break;
LABEL_16:
    v11 = Buffer;
    v3 = (void **)Buffer[0];
    v4 = v16;
    if ( v16 >= 0x10 )
      v11 = (void **)Buffer[0];
    v12 = (char *)v14 - (char *)v11;
    if ( v14 != v11 )
    {
      v13 = Buffer;
      if ( v16 >= 0x10 )
        v13 = (void **)Buffer[0];
      if ( v12 != fwrite(v13, 1u, (char *)v14 - (char *)v11, *(FILE **)(a1 + 144)) )
        goto LABEL_14;
      v4 = v16;
      v3 = (void **)Buffer[0];
    }
    if ( !*(_BYTE *)(a1 + 130) )
      goto LABEL_26;
    if ( !v12 )
    {
      std::string::append(Buffer, 8, 0);
      goto LABEL_6;
    }
  }
  if ( v9 != 2 )
  {
LABEL_14:
    v10 = 0;
    goto LABEL_27;
  }
LABEL_26:
  v10 = 1;
LABEL_27:
  LOBYTE(v8) = 1;
  std::string::_Tidy(Buffer, v8, 0);
  return v10;
}

```

## disassembly

```asm
0x18003df70  push    rbp
0x18003df72  push    rbx
0x18003df73  push    rsi
0x18003df74  push    rdi
0x18003df75  mov     rbp, rsp
0x18003df78  sub     rsp, 68h
0x18003df7c  mov     rax, cs:__security_cookie
0x18003df83  xor     rax, rsp
0x18003df86  mov     [rbp+var_10], rax
0x18003df8a  mov     rbx, rcx
0x18003df8d  cmp     qword ptr [rcx+78h], 0
0x18003df92  jz      loc_18003E0BB
0x18003df98  cmp     byte ptr [rcx+82h], 0
0x18003df9f  jz      loc_18003E0BB
0x18003dfa5  mov     [rbp+var_38], 0
0x18003dfad  mov     rax, [rcx]
0x18003dfb0  mov     edi, 0FFFFh
0x18003dfb5  mov     edx, edi
0x18003dfb7  mov     rax, [rax+18h]
0x18003dfbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dfc0  cmp     di, ax
0x18003dfc3  jnz     short loc_18003DFCC
0x18003dfc5  xor     al, al
0x18003dfc7  jmp     loc_18003E0BD
0x18003dfcc  xor     r8d, r8d
0x18003dfcf  lea     edx, [r8+8]
0x18003dfd3  lea     rcx, [rbp+Buffer]
0x18003dfd7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x18003dfdc  nop
0x18003dfdd  mov     r11, [rbp+Buffer]
0x18003dfe1  mov     r10, [rbp+var_18]
0x18003dfe5  mov     rcx, [rbx+78h]
0x18003dfe9  lea     r9, [rbp+Buffer]
0x18003dfed  cmp     r10, 10h
0x18003dff1  cmovnb  r9, r11
0x18003dff5  lea     r8, [rbp+Buffer]
0x18003dff9  cmovnb  r8, r11
0x18003dffd  mov     rax, [rcx]
0x18003e000  add     r9, [rbp+var_20]
0x18003e004  lea     rdx, [rbp+var_38]
0x18003e008  mov     [rsp+68h+var_48], rdx
0x18003e00d  lea     rdx, [rbx+84h]
0x18003e014  mov     rax, [rax+40h]
0x18003e018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e01d  test    eax, eax
0x18003e01f  jz      short loc_18003E02F
0x18003e021  sub     eax, 1
0x18003e024  jz      short loc_18003E036
0x18003e026  cmp     eax, 2
0x18003e029  jz      short loc_18003E0A7
0x18003e02b  xor     ebx, ebx
0x18003e02d  jmp     short loc_18003E0A9
0x18003e02f  mov     byte ptr [rbx+82h], 0
0x18003e036  lea     rax, [rbp+Buffer]
0x18003e03a  mov     r11, [rbp+Buffer]
0x18003e03e  mov     r10, [rbp+var_18]
0x18003e042  cmp     r10, 10h
0x18003e046  cmovnb  rax, r11
0x18003e04a  mov     rdi, [rbp+var_38]
0x18003e04e  sub     rdi, rax
0x18003e051  jz      short loc_18003E081
0x18003e053  lea     rcx, [rbp+Buffer]
0x18003e057  cmp     r10, 10h
0x18003e05b  cmovnb  rcx, r11; Buffer
0x18003e05f  mov     r9, [rbx+90h]; Stream
0x18003e066  mov     r8, rdi; ElementCount
0x18003e069  mov     edx, 1; ElementSize
0x18003e06e  call    cs:__imp_fwrite
0x18003e074  cmp     rdi, rax
0x18003e077  jnz     short loc_18003E02B
0x18003e079  mov     r10, [rbp+var_18]
0x18003e07d  mov     r11, [rbp+Buffer]
0x18003e081  cmp     byte ptr [rbx+82h], 0
0x18003e088  jz      short loc_18003E0A7
0x18003e08a  test    rdi, rdi
0x18003e08d  jnz     loc_18003DFE5
0x18003e093  xor     r8d, r8d
0x18003e096  lea     edx, [rdi+8]
0x18003e099  lea     rcx, [rbp+Buffer]
0x18003e09d  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x18003e0a2  jmp     loc_18003DFDD
0x18003e0a7  mov     bl, 1
0x18003e0a9  xor     r8d, r8d
0x18003e0ac  mov     dl, 1
0x18003e0ae  lea     rcx, [rbp+Buffer]
0x18003e0b2  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18003e0b7  mov     al, bl
0x18003e0b9  jmp     short loc_18003E0BD
0x18003e0bb  mov     al, 1
0x18003e0bd  mov     rcx, [rbp+var_10]
0x18003e0c1  xor     rcx, rsp; StackCookie
0x18003e0c4  call    __security_check_cookie
0x18003e0c9  add     rsp, 68h
0x18003e0cd  pop     rdi
0x18003e0ce  pop     rsi
0x18003e0cf  pop     rbx
0x18003e0d0  pop     rbp
0x18003e0d1  retn
```
