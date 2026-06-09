# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x14001fc10`
- end: `0x14001fcfe`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `238`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14001a5b0`
- `0x14003e980`
- `0x14003ea60`

## callees

- `0x14000f7e0`
- `0x14001fc10`
- `0x140067010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x14001fc78`
- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x14001fc78`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x14001fcd1`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x14001fcd1`

## pseudocode

```c
bool __fastcall std::filebuf::_Endwrite(__int64 a1)
{
  int v2; // eax
  int v3; // eax
  __int64 v5; // rdi
  _BYTE *v6; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v7[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v8; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 113) )
    return 1;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFFFFFFLL) == -1 )
    return 0;
  v2 = std::codecvt<char,char,_Mbstatet>::unshift(*(_QWORD *)(a1 + 104), a1 + 116, v7, &v8, &v6);
  if ( !v2 )
  {
    *(_BYTE *)(a1 + 113) = 0;
    goto LABEL_10;
  }
  v3 = v2 - 1;
  if ( !v3 )
  {
LABEL_10:
    if ( v6 == v7 )
      return *(_BYTE *)(a1 + 113) == 0;
    v5 = v6 - v7;
    if ( v5 == _o_fwrite(v7, 1, v6 - v7, *(_QWORD *)(a1 + 128)) )
      return *(_BYTE *)(a1 + 113) == 0;
    return 0;
  }
  if ( v3 != 2 )
    return 0;
  *(_BYTE *)(a1 + 113) = 0;
  return 1;
}

```

## disassembly

```asm
0x14001fc10  push    rbx
0x14001fc12  sub     rsp, 60h
0x14001fc16  mov     rax, cs:__security_cookie
0x14001fc1d  xor     rax, rsp
0x14001fc20  mov     [rsp+68h+var_10], rax
0x14001fc25  cmp     qword ptr [rcx+68h], 0
0x14001fc2a  mov     rbx, rcx
0x14001fc2d  jz      loc_14001FCE9
0x14001fc33  cmp     byte ptr [rcx+71h], 0
0x14001fc37  jz      loc_14001FCE9
0x14001fc3d  mov     rax, [rcx]
0x14001fc40  mov     edx, 0FFFFFFFFh
0x14001fc45  mov     [rsp+68h+arg_8], rdi
0x14001fc4a  mov     rax, [rax+18h]
0x14001fc4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fc53  cmp     eax, 0FFFFFFFFh
0x14001fc56  jz      loc_14001FCE5
0x14001fc5c  mov     rcx, [rbx+68h]
0x14001fc60  lea     rax, [rsp+68h+var_38]
0x14001fc65  lea     rdx, [rbx+74h]
0x14001fc69  mov     [rsp+68h+var_48], rax
0x14001fc6e  lea     r9, [rsp+68h+var_10]
0x14001fc73  lea     r8, [rsp+68h+var_30]
0x14001fc78  call    cs:__imp_?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x14001fc7e  test    eax, eax
0x14001fc80  jz      short loc_14001FCAA
0x14001fc82  sub     eax, 1
0x14001fc85  jz      short loc_14001FCAE
0x14001fc87  cmp     eax, 2
0x14001fc8a  jnz     short loc_14001FCE5
0x14001fc8c  mov     byte ptr [rbx+71h], 0
0x14001fc90  mov     al, 1
0x14001fc92  mov     rdi, [rsp+68h+arg_8]
0x14001fc97  mov     rcx, [rsp+68h+var_10]
0x14001fc9c  xor     rcx, rsp; StackCookie
0x14001fc9f  call    __security_check_cookie
0x14001fca4  add     rsp, 60h
0x14001fca8  pop     rbx
0x14001fca9  retn
0x14001fcaa  mov     byte ptr [rbx+71h], 0
0x14001fcae  mov     rdi, [rsp+68h+var_38]
0x14001fcb3  lea     rax, [rsp+68h+var_30]
0x14001fcb8  sub     rdi, rax
0x14001fcbb  jz      short loc_14001FCDC
0x14001fcbd  mov     r9, [rbx+80h]
0x14001fcc4  lea     rcx, [rsp+68h+var_30]
0x14001fcc9  mov     r8, rdi
0x14001fccc  mov     edx, 1
0x14001fcd1  call    cs:__imp__o_fwrite
0x14001fcd7  cmp     rdi, rax
0x14001fcda  jnz     short loc_14001FCE5
0x14001fcdc  cmp     byte ptr [rbx+71h], 0
0x14001fce0  setz    al
0x14001fce3  jmp     short loc_14001FC92
0x14001fce5  xor     al, al
0x14001fce7  jmp     short loc_14001FC92
0x14001fce9  mov     al, 1
0x14001fceb  mov     rcx, [rsp+68h+var_10]
0x14001fcf0  xor     rcx, rsp; StackCookie
0x14001fcf3  call    __security_check_cookie
0x14001fcf8  add     rsp, 60h
0x14001fcfc  pop     rbx
0x14001fcfd  retn
```
