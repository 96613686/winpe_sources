# GetChkdskRecoveryPath(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>,std::allocator<std::pair<DirQueItem,ushort const *>>> &)

- ea: `0x180021940`
- end: `0x180021b02`
- name: `?GetChkdskRecoveryPath@@YAJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z`
- size: `450`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x1800152d4`
- `0x180015bac`
- `0x180019590`
- `0x18001faac`
- `0x18001fc6c`
- `0x180021940`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800219cb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800219cb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002198e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002198e`

## pseudocode

```c
__int64 __fastcall GetChkdskRecoveryPath(__int64 *a1, __int64 a2)
{
  unsigned int LastWin32Error; // ebx
  __int64 v5; // rdx
  int i; // ebx
  _OWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned __int16 *v10; // rax
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int64 v19; // rdx
  int v20; // [rsp+20h] [rbp-658h]
  __int64 v21; // [rsp+28h] [rbp-650h]
  WCHAR Dst[264]; // [rsp+30h] [rbp-648h] BYREF
  _BYTE v23[520]; // [rsp+240h] [rbp-438h] BYREF
  __int64 v24; // [rsp+448h] [rbp-230h]
  unsigned __int16 v25[264]; // [rsp+450h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+678h] [rbp+0h]

  memset_0(Dst, 0, 0x208u);
  if ( !ExpandEnvironmentStringsW(L"%systemdrive%", Dst, 0x104u) )
  {
    LastWin32Error = GetLastWin32Error();
    if ( (LastWin32Error & 0x80000000) == 0 )
      return LastWin32Error;
    v5 = 1375;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\dirscanner.cpp",
      (const char *)LastWin32Error,
      v20);
    return LastWin32Error;
  }
  if ( GetFileAttributesW(Dst) == -1 )
  {
    LastWin32Error = -2147024893;
    v5 = 1377;
    goto LABEL_4;
  }
  for ( i = 0; i < 10; ++i )
  {
    memset_0(v25, 0, 0x208u);
    LODWORD(v21) = i;
    if ( StringCchPrintfW(v25, 0x104u, L"%s\\%s%d", Dst, L"FOUND.00", v21) >= 0 )
    {
      v8 = v23;
      v9 = 4;
      v10 = v25;
      do
      {
        v11 = *(_OWORD *)v10;
        v12 = *((_OWORD *)v10 + 1);
        v10 += 64;
        *v8 = v11;
        v13 = *((_OWORD *)v10 - 6);
        v8[1] = v12;
        v14 = *((_OWORD *)v10 - 5);
        v8[2] = v13;
        v15 = *((_OWORD *)v10 - 4);
        v8[3] = v14;
        v16 = *((_OWORD *)v10 - 3);
        v8[4] = v15;
        v17 = *((_OWORD *)v10 - 2);
        v8[5] = v16;
        v18 = *((_OWORD *)v10 - 1);
        v8[6] = v17;
        v8[7] = v18;
        v8 += 8;
        --v9;
      }
      while ( v9 );
      v19 = *(_QWORD *)(a2 + 8);
      *(_QWORD *)v8 = *(_QWORD *)v10;
      v24 = *a1;
      if ( v19 == *(_QWORD *)(a2 + 16) )
        std::vector<std::pair<DirQueItem,unsigned short const *>>::_Emplace_reallocate<std::pair<DirQueItem,unsigned short const *>>(
          a2,
          v19,
          v23);
      else
        std::vector<std::pair<DirQueItem,unsigned short const *>>::_Emplace_back_with_unused_capacity<std::pair<DirQueItem,unsigned short const *>>(
          a2,
          v23);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180021940  mov     [rsp+arg_0], rbx
0x180021945  mov     [rsp+arg_10], rsi
0x18002194a  push    rdi
0x18002194b  sub     rsp, 670h
0x180021952  mov     rax, cs:__security_cookie
0x180021959  xor     rax, rsp
0x18002195c  mov     [rsp+678h+var_18], rax
0x180021964  mov     rdi, rdx
0x180021967  mov     rsi, rcx
0x18002196a  xor     edx, edx; Val
0x18002196c  lea     rcx, [rsp+678h+Dst]; void *
0x180021971  mov     r8d, 208h; Size
0x180021977  call    memset_0
0x18002197c  mov     r8d, 104h; nSize
0x180021982  lea     rdx, [rsp+678h+Dst]; lpDst
0x180021987  lea     rcx, aSystemdrive; "%systemdrive%"
0x18002198e  call    cs:__imp_ExpandEnvironmentStringsW
0x180021994  test    eax, eax
0x180021996  jnz     short loc_1800219C6
0x180021998  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18002199d  mov     ebx, eax
0x18002199f  test    eax, eax
0x1800219a1  jns     short loc_1800219BF
0x1800219a3  mov     edx, 55Fh; void *
0x1800219a8  mov     rcx, [rsp+678h]; this
0x1800219b0  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800219b7  mov     r9d, ebx; char *
0x1800219ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800219bf  mov     eax, ebx
0x1800219c1  jmp     loc_180021ADD
0x1800219c6  lea     rcx, [rsp+678h+Dst]; lpFileName
0x1800219cb  call    cs:__imp_GetFileAttributesW
0x1800219d1  cmp     eax, 0FFFFFFFFh
0x1800219d4  jnz     short loc_1800219E2
0x1800219d6  mov     ebx, 80070003h
0x1800219db  mov     edx, 561h
0x1800219e0  jmp     short loc_1800219A8
0x1800219e2  xor     ebx, ebx
0x1800219e4  xor     edx, edx; Val
0x1800219e6  lea     rcx, [rsp+678h+var_228]; void *
0x1800219ee  mov     r8d, 208h; Size
0x1800219f4  call    memset_0
0x1800219f9  lea     rax, aFound00; "FOUND.00"
0x180021a00  mov     dword ptr [rsp+678h+var_650], ebx
0x180021a04  lea     r9, [rsp+678h+Dst]
0x180021a09  mov     [rsp+678h+var_658], rax
0x180021a0e  lea     r8, aSSD; "%s\\%s%d"
0x180021a15  mov     edx, 104h; unsigned __int64
0x180021a1a  lea     rcx, [rsp+678h+var_228]; unsigned __int16 *
0x180021a22  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021a27  test    eax, eax
0x180021a29  js      loc_180021AD0
0x180021a2f  lea     rcx, [rsp+678h+var_438]
0x180021a37  mov     edx, 4
0x180021a3c  lea     rax, [rsp+678h+var_228]
0x180021a44  movups  xmm0, xmmword ptr [rax]
0x180021a47  movups  xmm1, xmmword ptr [rax+10h]
0x180021a4b  lea     rax, [rax+80h]
0x180021a52  movups  xmmword ptr [rcx], xmm0
0x180021a55  movups  xmm0, xmmword ptr [rax-60h]
0x180021a59  movups  xmmword ptr [rcx+10h], xmm1
0x180021a5d  movups  xmm1, xmmword ptr [rax-50h]
0x180021a61  movups  xmmword ptr [rcx+20h], xmm0
0x180021a65  movups  xmm0, xmmword ptr [rax-40h]
0x180021a69  movups  xmmword ptr [rcx+30h], xmm1
0x180021a6d  movups  xmm1, xmmword ptr [rax-30h]
0x180021a71  movups  xmmword ptr [rcx+40h], xmm0
0x180021a75  movups  xmm0, xmmword ptr [rax-20h]
0x180021a79  movups  xmmword ptr [rcx+50h], xmm1
0x180021a7d  movups  xmm1, xmmword ptr [rax-10h]
0x180021a81  movups  xmmword ptr [rcx+60h], xmm0
0x180021a85  movups  xmmword ptr [rcx+70h], xmm1
0x180021a89  lea     rcx, [rcx+80h]
0x180021a90  sub     rdx, 1
0x180021a94  jnz     short loc_180021A44
0x180021a96  mov     rax, [rax]
0x180021a99  mov     rdx, [rdi+8]
0x180021a9d  mov     [rcx], rax
0x180021aa0  mov     rcx, rdi
0x180021aa3  mov     rax, [rsi]
0x180021aa6  mov     [rsp+678h+var_230], rax
0x180021aae  cmp     rdx, [rdi+10h]
0x180021ab2  jz      short loc_180021AC3
0x180021ab4  lea     rdx, [rsp+678h+var_438]
0x180021abc  call    ??$_Emplace_back_with_unused_capacity@U?$pair@UDirQueItem@@PEBG@std@@@?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@AEAAAEAU?$pair@UDirQueItem@@PEBG@1@$$QEAU21@@Z; std::vector<std::pair<DirQueItem,ushort const *>>::_Emplace_back_with_unused_capacity<std::pair<DirQueItem,ushort const *>>(std::pair<DirQueItem,ushort const *> &&)
0x180021ac1  jmp     short loc_180021AD0
0x180021ac3  lea     r8, [rsp+678h+var_438]
0x180021acb  call    ??$_Emplace_reallocate@U?$pair@UDirQueItem@@PEBG@std@@@?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@AEAAPEAU?$pair@UDirQueItem@@PEBG@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<DirQueItem,ushort const *>>::_Emplace_reallocate<std::pair<DirQueItem,ushort const *>>(std::pair<DirQueItem,ushort const *> * const,std::pair<DirQueItem,ushort const *> &&)
0x180021ad0  inc     ebx
0x180021ad2  cmp     ebx, 0Ah
0x180021ad5  jl      loc_1800219E4
0x180021adb  xor     eax, eax
0x180021add  mov     rcx, [rsp+678h+var_18]
0x180021ae5  xor     rcx, rsp; StackCookie
0x180021ae8  call    __security_check_cookie
0x180021aed  lea     r11, [rsp+678h+var_8]
0x180021af5  mov     rbx, [r11+10h]
0x180021af9  mov     rsi, [r11+20h]
0x180021afd  mov     rsp, r11
0x180021b00  pop     rdi
0x180021b01  retn
```
