# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x14003bf60`
- end: `0x14003c114`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000f7e0`
- `0x14003bf60`

## import_xrefs

- `msvcp_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x14003bfbd`
- `msvcp_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x14003bfbd`
- `msvcp_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x14003bfa3`
- `msvcp_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x14003bfa3`
- `msvcp_win!?setg@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAD00@Z` at `0x14003c001`
- `msvcp_win!?setg@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAD00@Z` at `0x14003c001`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x14003bf95`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x14003bfaf`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x14003bf95`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x14003bfaf`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x14003c06d`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x14003c06d`
- `msvcp_win!?eback@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x14003bfde`
- `msvcp_win!?eback@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x14003bfde`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x14003c01b`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x14003c08d`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x14003c01b`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x14003c08d`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x14003c0c4`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x14003c0c4`

## pseudocode

```c
__int64 __fastcall std::filebuf::overflow(__int64 a1, unsigned int a2)
{
  unsigned __int64 v5; // rbx
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ecx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ecx
  __int64 v13; // rbx
  unsigned int v14; // ecx
  char v15; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v16[7]; // [rsp+41h] [rbp-47h] BYREF
  _BYTE *v17; // [rsp+48h] [rbp-40h] BYREF
  char *v18; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v19[32]; // [rsp+58h] [rbp-30h] BYREF
  __int64 v20; // [rsp+78h] [rbp-10h] BYREF

  if ( a2 == -1 )
    return 0;
  if ( ((__int64 (*)(void))std::streambuf::pptr)() )
  {
    v5 = std::streambuf::epptr(a1);
    if ( std::streambuf::pptr(a1) < v5 )
    {
      *(_BYTE *)std::streambuf::_Pninc(a1) = a2;
      return a2;
    }
  }
  if ( !*(_QWORD *)(a1 + 128) )
    return 0xFFFFFFFFLL;
  if ( std::streambuf::eback(a1) == a1 + 112 )
    std::streambuf::setg(a1, *(_QWORD *)(a1 + 136), *(_QWORD *)(a1 + 136), *(_QWORD *)(a1 + 144));
  v6 = *(_QWORD *)(a1 + 104);
  if ( !v6 )
  {
    v7 = _o_fputc((unsigned int)(char)a2, *(_QWORD *)(a1 + 128));
    v8 = -1;
    if ( v7 != -1 )
      return a2;
    return v8;
  }
  v15 = a2;
  v9 = std::codecvt<char,char,_Mbstatet>::out(v6, a1 + 116, &v15, v16, &v18, v19, &v20, &v17);
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 == 2 )
      {
        v11 = _o_fputc((unsigned int)v15, *(_QWORD *)(a1 + 128));
        v12 = -1;
        if ( v11 != -1 )
          return a2;
        return v12;
      }
      return 0xFFFFFFFFLL;
    }
  }
  if ( v17 != v19 )
  {
    v13 = v17 - v19;
    if ( v13 != _o_fwrite(v19, 1, v17 - v19, *(_QWORD *)(a1 + 128)) )
      return 0xFFFFFFFFLL;
  }
  *(_BYTE *)(a1 + 113) = 1;
  v14 = -1;
  if ( v18 != &v15 )
    return a2;
  return v14;
}

```

## disassembly

```asm
0x14003bf60  mov     [rsp+arg_18], rsi
0x14003bf65  push    rdi
0x14003bf66  sub     rsp, 80h
0x14003bf6d  mov     rax, cs:__security_cookie
0x14003bf74  xor     rax, rsp
0x14003bf77  mov     [rsp+88h+var_10], rax
0x14003bf7c  mov     esi, edx
0x14003bf7e  mov     rdi, rcx
0x14003bf81  cmp     edx, 0FFFFFFFFh
0x14003bf84  jnz     short loc_14003BF8D
0x14003bf86  xor     eax, eax
0x14003bf88  jmp     loc_14003C0F6
0x14003bf8d  mov     [rsp+88h+arg_10], rbx
0x14003bf95  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x14003bf9b  test    rax, rax
0x14003bf9e  jz      short loc_14003BFCD
0x14003bfa0  mov     rcx, rdi
0x14003bfa3  call    cs:__imp_?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::epptr(void)
0x14003bfa9  mov     rcx, rdi
0x14003bfac  mov     rbx, rax
0x14003bfaf  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x14003bfb5  cmp     rax, rbx
0x14003bfb8  jnb     short loc_14003BFCD
0x14003bfba  mov     rcx, rdi
0x14003bfbd  call    cs:__imp_?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ; std::streambuf::_Pninc(void)
0x14003bfc3  mov     [rax], sil
0x14003bfc6  mov     eax, esi
0x14003bfc8  jmp     loc_14003C0EE
0x14003bfcd  cmp     qword ptr [rdi+80h], 0
0x14003bfd5  jz      loc_14003C0E9
0x14003bfdb  mov     rcx, rdi
0x14003bfde  call    cs:__imp_?eback@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::eback(void)
0x14003bfe4  lea     rcx, [rdi+70h]
0x14003bfe8  cmp     rax, rcx
0x14003bfeb  jnz     short loc_14003C007
0x14003bfed  mov     rdx, [rdi+88h]
0x14003bff4  mov     rcx, rdi
0x14003bff7  mov     r9, [rdi+90h]
0x14003bffe  mov     r8, rdx
0x14003c001  call    cs:__imp_?setg@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAD00@Z; std::streambuf::setg(char *,char *,char *)
0x14003c007  mov     rcx, [rdi+68h]
0x14003c00b  test    rcx, rcx
0x14003c00e  jnz     short loc_14003C032
0x14003c010  mov     rdx, [rdi+80h]
0x14003c017  movsx   ecx, sil
0x14003c01b  call    cs:__imp__o_fputc
0x14003c021  mov     ecx, 0FFFFFFFFh
0x14003c026  cmp     eax, ecx
0x14003c028  cmovnz  ecx, esi
0x14003c02b  mov     eax, ecx
0x14003c02d  jmp     loc_14003C0EE
0x14003c032  lea     rax, [rsp+88h+var_40]
0x14003c037  mov     [rsp+88h+var_48], sil
0x14003c03c  mov     [rsp+88h+var_50], rax
0x14003c041  lea     rdx, [rdi+74h]
0x14003c045  lea     rax, [rsp+88h+var_10]
0x14003c04a  mov     [rsp+88h+var_58], rax
0x14003c04f  lea     r9, [rsp+88h+var_47]
0x14003c054  lea     rax, [rsp+88h+var_30]
0x14003c059  mov     [rsp+88h+var_60], rax
0x14003c05e  lea     r8, [rsp+88h+var_48]
0x14003c063  lea     rax, [rsp+88h+var_38]
0x14003c068  mov     [rsp+88h+var_68], rax
0x14003c06d  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x14003c073  test    eax, eax
0x14003c075  jz      short loc_14003C0A1
0x14003c077  sub     eax, 1
0x14003c07a  jz      short loc_14003C0A1
0x14003c07c  cmp     eax, 2
0x14003c07f  jnz     short loc_14003C0E9
0x14003c081  movsx   ecx, [rsp+88h+var_48]
0x14003c086  mov     rdx, [rdi+80h]
0x14003c08d  call    cs:__imp__o_fputc
0x14003c093  mov     ecx, 0FFFFFFFFh
0x14003c098  cmp     eax, ecx
0x14003c09a  cmovnz  ecx, esi
0x14003c09d  mov     eax, ecx
0x14003c09f  jmp     short loc_14003C0EE
0x14003c0a1  mov     rbx, [rsp+88h+var_40]
0x14003c0a6  lea     rax, [rsp+88h+var_30]
0x14003c0ab  sub     rbx, rax
0x14003c0ae  jz      short loc_14003C0CF
0x14003c0b0  mov     r9, [rdi+80h]
0x14003c0b7  lea     rcx, [rsp+88h+var_30]
0x14003c0bc  mov     r8, rbx
0x14003c0bf  mov     edx, 1
0x14003c0c4  call    cs:__imp__o_fwrite
0x14003c0ca  cmp     rbx, rax
0x14003c0cd  jnz     short loc_14003C0E9
0x14003c0cf  lea     rax, [rsp+88h+var_48]
0x14003c0d4  mov     byte ptr [rdi+71h], 1
0x14003c0d8  cmp     [rsp+88h+var_38], rax
0x14003c0dd  mov     ecx, 0FFFFFFFFh
0x14003c0e2  cmovnz  ecx, esi
0x14003c0e5  mov     eax, ecx
0x14003c0e7  jmp     short loc_14003C0EE
0x14003c0e9  mov     eax, 0FFFFFFFFh
0x14003c0ee  mov     rbx, [rsp+88h+arg_10]
0x14003c0f6  mov     rcx, [rsp+88h+var_10]
0x14003c0fb  xor     rcx, rsp; StackCookie
0x14003c0fe  call    __security_check_cookie
0x14003c103  mov     rsi, [rsp+88h+arg_18]
0x14003c10b  add     rsp, 80h
0x14003c112  pop     rdi
0x14003c113  retn
```
