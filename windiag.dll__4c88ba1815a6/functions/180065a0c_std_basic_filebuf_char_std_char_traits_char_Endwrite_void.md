# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x180065a0c`
- end: `0x180065ae3`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `215`
- prototype: `bool __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180067e9c`
- `0x18006b200`
- `0x18006b330`

## callees

- `0x180004510`
- `0x180065a0c`
- `0x18009d010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x180065a72`
- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x180065a72`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180065acb`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180065acb`

## pseudocode

```c
bool __fastcall std::filebuf::_Endwrite(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // eax
  __int64 v6; // rdi
  _BYTE *v7; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v9; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 113) )
    return 1;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFFFFFFLL) == -1 )
    return 0;
  v2 = *(_QWORD *)(a1 + 104);
  v7 = 0;
  v3 = std::codecvt<char,char,_Mbstatet>::unshift(v2, a1 + 116, v8, &v9, &v7);
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 2 )
      {
        *(_BYTE *)(a1 + 113) = 0;
        return 1;
      }
      return 0;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 113) = 0;
  }
  if ( v7 == v8 )
    return *(_BYTE *)(a1 + 113) == 0;
  v6 = v7 - v8;
  if ( v6 == _o_fwrite(v8, 1, v7 - v8, *(_QWORD *)(a1 + 128)) )
    return *(_BYTE *)(a1 + 113) == 0;
  return 0;
}

```

## disassembly

```asm
0x180065a0c  mov     [rsp+arg_8], rbx
0x180065a11  push    rdi
0x180065a12  sub     rsp, 60h
0x180065a16  mov     rax, cs:__security_cookie
0x180065a1d  xor     rax, rsp
0x180065a20  mov     [rsp+68h+var_10], rax
0x180065a25  cmp     qword ptr [rcx+68h], 0
0x180065a2a  mov     rbx, rcx
0x180065a2d  jz      short loc_180065A8A
0x180065a2f  cmp     byte ptr [rcx+71h], 0
0x180065a33  jz      short loc_180065A8A
0x180065a35  mov     rax, [rcx]
0x180065a38  or      edx, 0FFFFFFFFh
0x180065a3b  mov     rax, [rax+18h]
0x180065a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065a44  cmp     eax, 0FFFFFFFFh
0x180065a47  jz      loc_180065ADF
0x180065a4d  mov     rcx, [rbx+68h]
0x180065a51  lea     rax, [rsp+68h+var_38]
0x180065a56  lea     rdx, [rbx+74h]
0x180065a5a  mov     [rsp+68h+var_48], rax
0x180065a5f  lea     r9, [rsp+68h+var_10]
0x180065a64  mov     [rsp+68h+var_38], 0
0x180065a6d  lea     r8, [rsp+68h+var_30]
0x180065a72  call    cs:__imp_?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x180065a78  test    eax, eax
0x180065a7a  jz      short loc_180065AA4
0x180065a7c  sub     eax, 1
0x180065a7f  jz      short loc_180065AA8
0x180065a81  cmp     eax, 2
0x180065a84  jnz     short loc_180065ADF
0x180065a86  mov     byte ptr [rbx+71h], 0
0x180065a8a  mov     al, 1
0x180065a8c  mov     rcx, [rsp+68h+var_10]
0x180065a91  xor     rcx, rsp; StackCookie
0x180065a94  call    __security_check_cookie
0x180065a99  mov     rbx, [rsp+68h+arg_8]
0x180065a9e  add     rsp, 60h
0x180065aa2  pop     rdi
0x180065aa3  retn
0x180065aa4  mov     byte ptr [rbx+71h], 0
0x180065aa8  mov     rdi, [rsp+68h+var_38]
0x180065aad  lea     rax, [rsp+68h+var_30]
0x180065ab2  sub     rdi, rax
0x180065ab5  jz      short loc_180065AD6
0x180065ab7  mov     r9, [rbx+80h]
0x180065abe  lea     rcx, [rsp+68h+var_30]
0x180065ac3  mov     r8, rdi
0x180065ac6  mov     edx, 1
0x180065acb  call    cs:__imp__o_fwrite
0x180065ad1  cmp     rdi, rax
0x180065ad4  jnz     short loc_180065ADF
0x180065ad6  cmp     byte ptr [rbx+71h], 0
0x180065ada  setz    al
0x180065add  jmp     short loc_180065A8C
0x180065adf  xor     al, al
0x180065ae1  jmp     short loc_180065A8C
```
