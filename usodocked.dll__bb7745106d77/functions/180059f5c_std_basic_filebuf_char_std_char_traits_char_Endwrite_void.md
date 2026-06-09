# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x180059f5c`
- end: `0x18005a033`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `215`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800583a0`
- `0x18005a4c0`
- `0x18005a5d0`

## callees

- `0x180007660`
- `0x180059f5c`
- `0x180071010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x180059fc2`
- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x180059fc2`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18005a01b`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18005a01b`

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
0x180059f5c  mov     [rsp+arg_8], rbx
0x180059f61  push    rdi
0x180059f62  sub     rsp, 60h
0x180059f66  mov     rax, cs:__security_cookie
0x180059f6d  xor     rax, rsp
0x180059f70  mov     [rsp+68h+var_10], rax
0x180059f75  cmp     qword ptr [rcx+68h], 0
0x180059f7a  mov     rbx, rcx
0x180059f7d  jz      short loc_180059FDA
0x180059f7f  cmp     byte ptr [rcx+71h], 0
0x180059f83  jz      short loc_180059FDA
0x180059f85  mov     rax, [rcx]
0x180059f88  or      edx, 0FFFFFFFFh
0x180059f8b  mov     rax, [rax+18h]
0x180059f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f94  cmp     eax, 0FFFFFFFFh
0x180059f97  jz      loc_18005A02F
0x180059f9d  mov     rcx, [rbx+68h]
0x180059fa1  lea     rax, [rsp+68h+var_38]
0x180059fa6  lea     rdx, [rbx+74h]
0x180059faa  mov     [rsp+68h+var_48], rax
0x180059faf  lea     r9, [rsp+68h+var_10]
0x180059fb4  mov     [rsp+68h+var_38], 0
0x180059fbd  lea     r8, [rsp+68h+var_30]
0x180059fc2  call    cs:__imp_?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x180059fc8  test    eax, eax
0x180059fca  jz      short loc_180059FF4
0x180059fcc  sub     eax, 1
0x180059fcf  jz      short loc_180059FF8
0x180059fd1  cmp     eax, 2
0x180059fd4  jnz     short loc_18005A02F
0x180059fd6  mov     byte ptr [rbx+71h], 0
0x180059fda  mov     al, 1
0x180059fdc  mov     rcx, [rsp+68h+var_10]
0x180059fe1  xor     rcx, rsp; StackCookie
0x180059fe4  call    __security_check_cookie
0x180059fe9  mov     rbx, [rsp+68h+arg_8]
0x180059fee  add     rsp, 60h
0x180059ff2  pop     rdi
0x180059ff3  retn
0x180059ff4  mov     byte ptr [rbx+71h], 0
0x180059ff8  mov     rdi, [rsp+68h+var_38]
0x180059ffd  lea     rax, [rsp+68h+var_30]
0x18005a002  sub     rdi, rax
0x18005a005  jz      short loc_18005A026
0x18005a007  mov     r9, [rbx+80h]
0x18005a00e  lea     rcx, [rsp+68h+var_30]
0x18005a013  mov     r8, rdi
0x18005a016  mov     edx, 1
0x18005a01b  call    cs:__imp__o_fwrite
0x18005a021  cmp     rdi, rax
0x18005a024  jnz     short loc_18005A02F
0x18005a026  cmp     byte ptr [rbx+71h], 0
0x18005a02a  setz    al
0x18005a02d  jmp     short loc_180059FDC
0x18005a02f  xor     al, al
0x18005a031  jmp     short loc_180059FDC
```
