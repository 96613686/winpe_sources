# HilbertLocationToTimeZone::Initialize(ushort const *)

- ea: `0x18001007c`
- end: `0x1800101b8`
- name: `?Initialize@HilbertLocationToTimeZone@@AEAAJPEBG@Z`
- size: `316`
- prototype: `__int64 __fastcall(HilbertLocationToTimeZone *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000fa60`

## callees

- `0x18000885c`
- `0x18000f928`
- `0x18001007c`
- `0x1800104a0`
- `0x180012f38`

## string_xrefs

- `0x18001019a`: `onecore\base\win32\winnls\tzautoupdate\hilbertlocationtotimezone.cpp`

## pseudocode

```c
__int64 __fastcall HilbertLocationToTimeZone::Initialize(HilbertLocationToTimeZone *this, const unsigned __int16 *a2)
{
  int v3; // ebp
  int v4; // ebx
  __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  __int64 v7; // rbx
  unsigned __int64 v8; // r14
  unsigned __int8 *v9; // rdi
  int v10; // r9d
  __int64 *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  int v16; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = 0;
  v4 = MemoryMappedFile::MapFile((HilbertLocationToTimeZone *)((char *)this + 16), a2);
  if ( v4 < 0 )
  {
    v5 = 91;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\hilbertlocationtotimezone.cpp",
      (const char *)(unsigned int)v4,
      v16);
    return (unsigned int)v4;
  }
  v6 = *((_QWORD *)this + 4);
  if ( v6 < 0xA )
  {
    v5 = 94;
LABEL_25:
    v4 = -2147024809;
    goto LABEL_26;
  }
  v7 = *((_QWORD *)this + 5);
  if ( !*(_BYTE *)(v7 + 3) )
  {
    v5 = 98;
    goto LABEL_25;
  }
  if ( *(__int16 *)(v7 + 4) <= 0 )
  {
    v5 = 99;
    goto LABEL_25;
  }
  if ( *(__int16 *)(v7 + 4) >= 255 )
  {
    v5 = 100;
    goto LABEL_25;
  }
  v8 = v7 + v6;
  *(_DWORD *)this = *(_DWORD *)(v7 + 6);
  *((_DWORD *)this + 1) = *(unsigned __int8 *)(v7 + 2);
  std::vector<std::wstring>::resize((char *)this + 48, *(__int16 *)(v7 + 4));
  v9 = (unsigned __int8 *)(v7 + 4 * (*(int *)(v7 + 6) + 2LL) + *(int *)(v7 + 6) + 2LL);
  while ( v3 < *(__int16 *)(v7 + 4) )
  {
    if ( (unsigned __int64)v9 >= v8 )
    {
      v5 = 114;
      goto LABEL_25;
    }
    v10 = (_DWORD)v9 + 1;
    v9 += *v9 + 1;
    if ( (unsigned __int64)v9 > v8 )
    {
      v5 = 118;
      goto LABEL_25;
    }
    v11 = (__int64 *)(*((_QWORD *)this + 6) + 32LL * v3);
    if ( (unsigned __int64)v11[3] < 8 )
      v12 = *((_QWORD *)this + 6) + 32LL * v3;
    else
      v12 = *v11;
    v13 = v12 + 2 * v11[2];
    if ( (unsigned __int64)v11[3] < 8 )
      v14 = *((_QWORD *)this + 6) + 32LL * v3;
    else
      v14 = *v11;
    std::wstring::replace<char const *>((_DWORD)v11, v14, v13, v10, (__int64)v9);
    ++v3;
  }
  *((_QWORD *)this + 1) = v7 + 10;
  return 0;
}

```

## disassembly

```asm
0x18001007c  push    rbx
0x18001007e  push    rbp
0x18001007f  push    rsi
0x180010080  push    rdi
0x180010081  push    r14
0x180010083  push    r15
0x180010085  sub     rsp, 38h
0x180010089  mov     rsi, rcx
0x18001008c  add     rcx, 10h; this
0x180010090  call    ?MapFile@MemoryMappedFile@@QEAAJPEBG@Z; MemoryMappedFile::MapFile(ushort const *)
0x180010095  xor     ebp, ebp
0x180010097  mov     ebx, eax
0x180010099  test    eax, eax
0x18001009b  jns     short loc_1800100A5
0x18001009d  lea     edx, [rbp+5Bh]
0x1800100a0  jmp     loc_180010195
0x1800100a5  mov     rcx, [rsi+20h]
0x1800100a9  cmp     rcx, 0Ah
0x1800100ad  jnb     short loc_1800100B9
0x1800100af  mov     edx, 5Eh ; '^'
0x1800100b4  jmp     loc_180010190
0x1800100b9  mov     rbx, [rsi+28h]
0x1800100bd  cmp     [rbx+3], bpl
0x1800100c1  jz      loc_18001018B
0x1800100c7  cmp     [rbx+4], bp
0x1800100cb  jle     loc_180010184
0x1800100d1  mov     eax, 0FFh
0x1800100d6  cmp     [rbx+4], ax
0x1800100da  jge     loc_18001017D
0x1800100e0  mov     eax, [rbx+6]
0x1800100e3  lea     r14, [rbx+rcx]
0x1800100e7  mov     [rsi], eax
0x1800100e9  lea     rcx, [rsi+30h]
0x1800100ed  movzx   eax, byte ptr [rbx+2]
0x1800100f1  mov     [rsi+4], eax
0x1800100f4  movsx   rdx, word ptr [rbx+4]
0x1800100f9  call    ?resize@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::wstring>::resize(unsigned __int64)
0x1800100fe  movsxd  rdi, dword ptr [rbx+6]
0x180010102  add     rdi, 2
0x180010106  lea     rax, [rbx+rdi*4]
0x18001010a  add     rdi, rax
0x18001010d  movsx   eax, word ptr [rbx+4]
0x180010111  cmp     ebp, eax
0x180010113  jge     short loc_180010171
0x180010115  cmp     rdi, r14
0x180010118  jnb     short loc_18001016A
0x18001011a  lea     r9, [rdi+1]
0x18001011e  movzx   edi, byte ptr [rdi]
0x180010121  add     rdi, r9
0x180010124  cmp     rdi, r14
0x180010127  ja      short loc_180010163
0x180010129  movsxd  rcx, ebp
0x18001012c  shl     rcx, 5
0x180010130  add     rcx, [rsi+30h]
0x180010134  cmp     qword ptr [rcx+18h], 8
0x180010139  jb      short loc_180010140
0x18001013b  mov     rdx, [rcx]
0x18001013e  jmp     short loc_180010143
0x180010140  mov     rdx, rcx
0x180010143  mov     rax, [rcx+10h]
0x180010147  lea     r8, [rdx+rax*2]
0x18001014b  jb      short loc_180010152
0x18001014d  mov     rdx, [rcx]
0x180010150  jmp     short loc_180010155
0x180010152  mov     rdx, rcx
0x180010155  mov     qword ptr [rsp+68h+var_48], rdi
0x18001015a  call    ??$replace@PEBD@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0PEBD1@Z; std::wstring::replace<char const *>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,char const *,char const *)
0x18001015f  inc     ebp
0x180010161  jmp     short loc_18001010D
0x180010163  mov     edx, 76h ; 'v'
0x180010168  jmp     short loc_180010190
0x18001016a  mov     edx, 72h ; 'r'
0x18001016f  jmp     short loc_180010190
0x180010171  lea     rax, [rbx+0Ah]
0x180010175  mov     [rsi+8], rax
0x180010179  xor     eax, eax
0x18001017b  jmp     short loc_1800101AB
0x18001017d  mov     edx, 64h ; 'd'
0x180010182  jmp     short loc_180010190
0x180010184  mov     edx, 63h ; 'c'
0x180010189  jmp     short loc_180010190
0x18001018b  mov     edx, 62h ; 'b'; void *
0x180010190  mov     ebx, 80070057h
0x180010195  mov     rcx, [rsp+68h]; this
0x18001019a  lea     r8, aOnecoreBaseWin_1; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x1800101a1  mov     r9d, ebx; char *
0x1800101a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800101a9  mov     eax, ebx
0x1800101ab  add     rsp, 38h
0x1800101af  pop     r15
0x1800101b1  pop     r14
0x1800101b3  pop     rdi
0x1800101b4  pop     rsi
0x1800101b5  pop     rbp
0x1800101b6  pop     rbx
0x1800101b7  retn
```
