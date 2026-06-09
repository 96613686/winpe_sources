# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x18006bb00`
- end: `0x18006bc14`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800054fc`
- `0x18006bb00`

## import_xrefs

- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x18006bb27`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x18006bb27`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18006bbcd`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18006bbfa`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18006bbcd`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18006bbfa`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsgetn(__int64 a1, char *a2, __int64 a3)
{
  size_t v7; // rbp
  const void *v8; // rdx
  int v9; // ecx
  size_t v10; // rbx
  _QWORD *v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rdx
  size_t v14; // rax

  if ( a3 <= 0 )
    return 0;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsgetn();
  v7 = a3;
  v8 = **(const void ***)(a1 + 56);
  if ( v8 )
    v9 = **(_DWORD **)(a1 + 80);
  else
    v9 = 0;
  if ( v9 )
  {
    v10 = a3;
    if ( v9 < (unsigned __int64)a3 )
      v10 = v9;
    memcpy_0(a2, v8, v10);
    a2 += v10;
    v7 = a3 - v10;
    **(_DWORD **)(a1 + 80) -= v10;
    **(_QWORD **)(a1 + 56) += (int)v10;
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    v11 = *(_QWORD **)(a1 + 24);
    if ( *v11 == a1 + 112 )
    {
      v12 = *(_QWORD *)(a1 + 136);
      v13 = *(_QWORD *)(a1 + 144);
      *v11 = v12;
      **(_QWORD **)(a1 + 56) = v12;
      **(_DWORD **)(a1 + 80) = v13 - v12;
    }
    while ( v7 > 0xFFF )
    {
      v14 = fread(a2, 1u, 0xFFFu, *(FILE **)(a1 + 128));
      v7 -= v14;
      if ( v14 != 4095 )
        return a3 - v7;
      a2 += 4095;
    }
    if ( v7 )
      v7 -= fread(a2, 1u, v7, *(FILE **)(a1 + 128));
  }
  return a3 - v7;
}

```

## disassembly

```asm
0x18006bb00  push    rbx
0x18006bb02  push    rbp
0x18006bb03  push    rsi
0x18006bb04  push    rdi
0x18006bb05  push    r14
0x18006bb07  sub     rsp, 20h
0x18006bb0b  mov     rdi, r8
0x18006bb0e  mov     r14, rdx
0x18006bb11  mov     rsi, rcx
0x18006bb14  test    r8, r8
0x18006bb17  jg      short loc_18006BB20
0x18006bb19  xor     eax, eax
0x18006bb1b  jmp     loc_18006BC09
0x18006bb20  cmp     qword ptr [rcx+68h], 0
0x18006bb25  jz      short loc_18006BB32
0x18006bb27  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x18006bb2d  jmp     loc_18006BC09
0x18006bb32  mov     rax, [rcx+38h]
0x18006bb36  mov     rbp, rdi
0x18006bb39  mov     rdx, [rax]; Src
0x18006bb3c  test    rdx, rdx
0x18006bb3f  jz      short loc_18006BB49
0x18006bb41  mov     rax, [rcx+50h]
0x18006bb45  mov     ecx, [rax]
0x18006bb47  jmp     short loc_18006BB4B
0x18006bb49  xor     ecx, ecx
0x18006bb4b  movsxd  rax, ecx
0x18006bb4e  test    ecx, ecx
0x18006bb50  jz      short loc_18006BB7D
0x18006bb52  cmp     rax, rdi
0x18006bb55  mov     rbx, rdi
0x18006bb58  mov     rcx, r14; void *
0x18006bb5b  cmovb   rbx, rax
0x18006bb5f  mov     r8, rbx; Size
0x18006bb62  call    memcpy_0
0x18006bb67  mov     rax, [rsi+50h]
0x18006bb6b  add     r14, rbx
0x18006bb6e  sub     rbp, rbx
0x18006bb71  sub     [rax], ebx
0x18006bb73  mov     rcx, [rsi+38h]
0x18006bb77  movsxd  rax, ebx
0x18006bb7a  add     [rcx], rax
0x18006bb7d  cmp     qword ptr [rsi+80h], 0
0x18006bb85  jz      short loc_18006BC03
0x18006bb87  mov     r8, [rsi+18h]
0x18006bb8b  lea     rax, [rsi+70h]
0x18006bb8f  cmp     [r8], rax
0x18006bb92  jnz     short loc_18006BBB4
0x18006bb94  mov     rcx, [rsi+88h]
0x18006bb9b  mov     rdx, [rsi+90h]
0x18006bba2  mov     [r8], rcx
0x18006bba5  sub     edx, ecx
0x18006bba7  mov     rax, [rsi+38h]
0x18006bbab  mov     [rax], rcx
0x18006bbae  mov     rax, [rsi+50h]
0x18006bbb2  mov     [rax], edx
0x18006bbb4  mov     ebx, 0FFFh
0x18006bbb9  jmp     short loc_18006BBDE
0x18006bbbb  mov     r9, [rsi+80h]; Stream
0x18006bbc2  mov     r8, rbx; ElementCount
0x18006bbc5  mov     edx, 1; ElementSize
0x18006bbca  mov     rcx, r14; Buffer
0x18006bbcd  call    cs:__imp_fread
0x18006bbd3  sub     rbp, rax
0x18006bbd6  cmp     rax, rbx
0x18006bbd9  jnz     short loc_18006BC03
0x18006bbdb  add     r14, rbx
0x18006bbde  cmp     rbp, rbx
0x18006bbe1  ja      short loc_18006BBBB
0x18006bbe3  test    rbp, rbp
0x18006bbe6  jz      short loc_18006BC03
0x18006bbe8  mov     r9, [rsi+80h]; Stream
0x18006bbef  mov     r8, rbp; ElementCount
0x18006bbf2  mov     edx, 1; ElementSize
0x18006bbf7  mov     rcx, r14; Buffer
0x18006bbfa  call    cs:__imp_fread
0x18006bc00  sub     rbp, rax
0x18006bc03  sub     rdi, rbp
0x18006bc06  mov     rax, rdi
0x18006bc09  add     rsp, 20h
0x18006bc0d  pop     r14
0x18006bc0f  pop     rdi
0x18006bc10  pop     rsi
0x18006bc11  pop     rbp
0x18006bc12  pop     rbx
0x18006bc13  retn
```
