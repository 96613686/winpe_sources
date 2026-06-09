# IniRegInitialize

- ea: `0x3838936f0`
- end: `0x38389376d`
- name: `IniRegInitialize`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x383893660`

## callees

- `0x3838427d0`
- `0x3838936f0`
- `0x383893780`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x383891bad`
- `KERNEL32!GetFileAttributesW` at `0x383891bad`
- `KERNEL32!GetModuleFileNameW` at `0x383891b45`
- `KERNEL32!GetModuleFileNameW` at `0x383891b45`
- `KERNEL32!CompareStringW` at `0x383891c0b`
- `KERNEL32!CompareStringW` at `0x383891c0b`

## pseudocode

```c
__int64 __fastcall IniRegInitialize(const CHAR *a1, const void *a2, int a3)
{
  WCHAR *v3; // r8
  DWORD ModuleFileNameW; // eax
  WCHAR *v5; // rcx
  int v6; // r11d
  WCHAR *v7; // rdx
  void *lpString2; // rcx
  void *v9; // rbp
  BOOL v10; // ebx
  __int64 v14; // rdx
  HMODULE v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rax
  int v18; // r14d
  __int64 v19; // rax
  __int64 v20; // rax
  bool v21; // zf
  CHAR *v22; // rax
  WCHAR *v23; // rdx

  if ( dword_383B1F178 )
    return 1;
  Trace(a1);
  v16 = -1;
  if ( v14 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)(v14 + 2 * v17) );
  }
  else
  {
    LODWORD(v17) = 3;
  }
  v18 = v17 + 1;
  ModuleFileNameW = GetModuleFileNameW(v15, &Src, 260 - (v17 + 1));
  if ( ModuleFileNameW )
  {
    Trace((LPCTSTR)&Src + 2 * ModuleFileNameW - 2);
    v7 = 0;
    v3 = 0;
    while ( v5 > &Src )
    {
      if ( v3 )
      {
        if ( *v5 == 92 )
          v7 = v5;
      }
      else if ( *v5 == 46 )
      {
        v3 = v5;
      }
      --v5;
      if ( v7 )
      {
        lpString2 = v7 + 1;
        v9 = v3 + 1;
        if ( a2 )
        {
          memcpy(lpString2, a2, (unsigned int)(2 * v18));
        }
        else
        {
          v10 = CompareStringW(
                  0x400u,
                  1u,
                  lpString1,
                  cchCount1,
                  (PCNZWCH)lpString2,
                  v6 - (((_BYTE *)lpString2 - (_BYTE *)&Src) >> 1)) == 2;
          memcpy(v9, L"ini", (unsigned int)(2 * v18));
          if ( v10 )
            return 0;
        }
        if ( GetFileAttributesW(&Src) == -1 )
          return 0;
        memcpy(byte_383B2C020, &Src, sizeof(byte_383B2C020));
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)&byte_383B2C020[2 * v19] );
        v20 = v19 - 1;
        v21 = *(_WORD *)&byte_383B2C020[2 * v20] == 92;
        v22 = &byte_383B2C020[2 * v20];
        if ( !v21 )
        {
          do
          {
            if ( v22 <= byte_383B2C020 )
              break;
            v22 -= 2;
          }
          while ( *(_WORD *)v22 != 92 );
        }
        *(_WORD *)v22 = 0;
        dword_383B2BE00 = ((v22 - byte_383B2C020) >> 1) + 1;
        Trace(byte_383B2C020);
        memcpy(&FileName, &Src, 0x208u);
        do
          ++v16;
        while ( *(&FileName + v16) );
        v23 = &FileName + (unsigned int)v16;
        *(_QWORD *)v23 = 0x7400780065002ELL;
        v23[4] = 0;
        Trace((LPCTSTR)&FileName);
        dword_383B2BE04 = a3;
        dword_383B1F178 = 1;
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x3838936f0  push    rbx
0x3838936f2  push    rsi
0x3838936f3  push    r15
0x3838936f5  sub     rsp, 40h
0x3838936f9  cmp     cs:dword_383B1F178, 0
0x383893700  mov     r15d, r8d
0x383893703  mov     rbx, rdx
0x383893706  jz      short loc_383893716
0x383893708  mov     eax, 1
0x38389370d  add     rsp, 40h
0x383893711  pop     r15
0x383893713  pop     rsi
0x383893714  pop     rbx
0x383893715  retn
0x383893716  mov     [rsp+58h+arg_8], rdi
0x38389371b  mov     [rsp+58h+arg_10], r12
0x383893720  mov     [rsp+58h+var_28], r14
0x383893725  call    Trace
0x38389372a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x38389372e  test    rdx, rdx
0x383893731  jz      short loc_383893742
0x383893733  mov     rax, rdi
0x383893736  inc     rax
0x383893739  cmp     word ptr [rdx+rax*2], 0
0x38389373e  jnz     short loc_383893736
0x383893740  jmp     short loc_383893747
0x383893742  mov     eax, 3
0x383893747  lea     r14d, [rax+1]
0x38389374b  mov     r8d, 104h
0x383893751  lea     r12, Src
0x383893758  sub     r8d, r14d; nSize
0x38389375b  mov     rdx, r12; lpFilename
0x38389375e  mov     [rsp+58h+arg_0], rbp
0x383893763  mov     [rsp+58h+var_20], r13
0x383893768  jmp     loc_383891B45
0x383891b3a  cmp     word ptr [rcx], 2Eh ; '.'
0x383891b3e  jnz     short loc_383891B7F
0x383891b40  mov     r8, rcx
0x383891b43  jmp     short loc_383891B7F
0x383891b45  call    cs:__imp_GetModuleFileNameW
0x383891b4b  mov     r11d, eax
0x383891b4e  test    eax, eax
0x383891b50  jz      short loc_383891BBC
0x383891b52  lea     rcx, [r12-2]
0x383891b57  lea     rcx, [rcx+r11*2]; Format
0x383891b5b  call    Trace
0x383891b60  xor     r13d, r13d
0x383891b63  mov     edx, r13d
0x383891b66  mov     r8d, r13d
0x383891b69  cmp     rcx, r12
0x383891b6c  jbe     loc_3839107B6
0x383891b72  test    r8, r8
0x383891b75  jz      short loc_383891B3A
0x383891b77  cmp     word ptr [rcx], 5Ch ; '\'
0x383891b7b  cmovz   rdx, rcx
0x383891b7f  sub     rcx, 2
0x383891b83  test    rdx, rdx
0x383891b86  jz      short loc_383891B69
0x383891b88  jmp     short $+2
0x383891b8a  lea     rcx, [rdx+2]; void *
0x383891b8e  lea     rbp, [r8+2]
0x383891b92  mov     esi, 1
0x383891b97  test    rbx, rbx
0x383891b9a  jz      short loc_383891BE0
0x383891b9c  lea     r8d, [r14+r14]; Size
0x383891ba0  mov     rdx, rbx; Src
0x383891ba3  call    memcpy
0x383891ba8  jmp     short $+2
0x383891baa  mov     rcx, r12; lpFileName
0x383891bad  call    cs:__imp_GetFileAttributesW
0x383891bb3  cmp     eax, 0FFFFFFFFh
0x383891bb6  jnz     loc_3839107C4
0x383891bbc  xor     eax, eax
0x383891bbe  mov     r13, [rsp+58h+var_20]
0x383891bc3  mov     rbp, [rsp+58h+arg_0]
0x383891bc8  mov     rdi, [rsp+58h+arg_8]
0x383891bcd  mov     r12, [rsp+58h+arg_10]
0x383891bd2  mov     r14, [rsp+58h+var_28]
0x383891bd7  add     rsp, 40h
0x383891bdb  pop     r15
0x383891bdd  pop     rsi
0x383891bde  pop     rbx
0x383891bdf  retn
0x383891be0  mov     r9d, cs:cchCount1; cchCount1
0x383891be7  mov     r8, cs:lpString1; lpString1
0x383891bee  mov     rax, rcx
0x383891bf1  sub     rax, r12
0x383891bf4  mov     edx, esi; dwCmpFlags
0x383891bf6  sar     rax, 1
0x383891bf9  sub     r11d, eax
0x383891bfc  mov     [rsp+58h+cchCount2], r11d; cchCount2
0x383891c01  mov     [rsp+58h+lpString2], rcx; lpString2
0x383891c06  mov     ecx, 400h; Locale
0x383891c0b  call    cs:__imp_CompareStringW
0x383891c11  lea     r8d, [r14+r14]; Size
0x383891c15  lea     rdx, aIni; "ini"
0x383891c1c  cmp     eax, 2
0x383891c1f  mov     ebx, r13d
0x383891c22  mov     rcx, rbp; void *
0x383891c25  cmovz   ebx, esi
0x383891c28  call    memcpy
0x383891c2d  test    ebx, ebx
0x383891c2f  jnz     short loc_383891BBC
0x383891c31  jmp     loc_383891BAA
0x3839107b6  test    rdx, rdx
0x3839107b9  jnz     loc_383891B8A
0x3839107bf  jmp     loc_383891BBC
0x3839107c4  lea     rbx, byte_383B2C020
0x3839107cb  mov     rdx, r12; Src
0x3839107ce  mov     r8d, 208h; Size
0x3839107d4  mov     rcx, rbx; void *
0x3839107d7  call    memcpy
0x3839107dc  mov     rax, rdi
0x3839107df  inc     rax
0x3839107e2  cmp     [rbx+rax*2], r13w
0x3839107e7  jnz     short loc_3839107DF
0x3839107e9  dec     rax
0x3839107ec  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x3839107f1  lea     rax, [rbx+rax*2]
0x3839107f5  jz      short loc_38391080F
0x3839107f7  nop     word ptr [rax+rax+00000000h]
0x383910800  cmp     rax, rbx
0x383910803  jbe     short loc_38391080F
0x383910805  sub     rax, 2
0x383910809  cmp     word ptr [rax], 5Ch ; '\'
0x38391080d  jnz     short loc_383910800
0x38391080f  mov     [rax], r13w
0x383910813  sub     rax, rbx
0x383910816  mov     rcx, rbx; Format
0x383910819  sar     rax, 1
0x38391081c  inc     eax
0x38391081e  mov     cs:dword_383B2BE00, eax
0x383910824  call    Trace
0x383910829  lea     rbx, FileName
0x383910830  mov     rcx, rbx; void *
0x383910833  mov     rdx, r12; Src
0x383910836  mov     r8d, 208h; Size
0x38391083c  call    memcpy
0x383910841  inc     rdi
0x383910844  cmp     [rbx+rdi*2], r13w
0x383910849  jnz     short loc_383910841
0x38391084b  mov     eax, edi
0x38391084d  mov     rcx, rbx; Format
0x383910850  lea     rdx, [rbx+rax*2]
0x383910854  mov     rax, cs:qword_383910888
0x38391085b  mov     [rdx], rax
0x38391085e  movzx   eax, cs:word_383910890
0x383910865  mov     [rdx+8], ax
0x383910869  call    Trace
0x38391086e  mov     cs:dword_383B2BE04, r15d
0x383910875  mov     cs:dword_383B1F178, esi
0x38391087b  mov     eax, esi
0x38391087d  jmp     loc_383891BBE
```
