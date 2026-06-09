# IF_STATE::ValidateResourceTag(IHttpContext *,char const *,STRU *)

- ea: `0x18000a9c4`
- end: `0x18000ad7d`
- name: `?ValidateResourceTag@IF_STATE@@AEAAJPEAVIHttpContext@@PEBDPEAVSTRU@@@Z`
- size: `953`
- prototype: `__int64 __fastcall(IF_STATE *this, struct IHttpContext *, const char *, struct STRU *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a7d4`

## callees

- `0x180006194`
- `0x18000a9c4`
- `0x18001a468`
- `0x18001c33c`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000ad48`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000ad52`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000ad48`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000ad52`
- `iisutil!SAFE_snwprintf` at `0x18000acbe`
- `iisutil!SAFE_snwprintf` at `0x18000acbe`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aa63`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aab4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aafe`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ab3d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000abf4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aca4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aa63`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aab4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aafe`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ab3d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000abf4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aca4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ab88`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ac44`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ab88`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ac44`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000aa7f`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000aad0`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000ab1a`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000ab59`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000ac10`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000aa7f`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000aad0`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000ab1a`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000ab59`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000ac10`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NPEBD@Z` at `0x18000ac80`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NPEBD@Z` at `0x18000ac80`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000a9ff`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000aa09`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000a9ff`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000aa09`

## string_xrefs

- `0x18000ad29`: `If: Header Contains Invalid URI After Unescaping`
- `0x18000ac1d`: `If: Header Protocol Scheme Mismatch`
- `0x18000ab27`: `If: Header URL Missing Host Component`
- `0x18000aadd`: `If: Header Contains Invalid Protocol Scheme`
- `0x18000aa8c`: `If: Header Contains Invalid URI Stem`

## pseudocode

```c
__int64 __fastcall IF_STATE::ValidateResourceTag(
        IF_STATE *this,
        struct IHttpContext *a2,
        const char *a3,
        struct STRU *a4)
{
  int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // r14
  __int64 v10; // rbx
  void (__fastcall *v11)(__int64, const wchar_t *, __int64, _QWORD, int); // r15
  const wchar_t *v12; // rdx
  __int64 (__fastcall *v13)(struct IHttpContext *); // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 v18; // rbx
  void (__fastcall *v19)(__int64, const wchar_t *, __int64, __int64, int); // r14
  const wchar_t *v20; // rdx
  void (__fastcall *v21)(__int64, const wchar_t *, __int64, __int64, int); // rax
  int v22; // esi
  __int64 v23; // rax
  const char *v24; // rax
  const char *v25; // r15
  int v26; // eax
  const unsigned __int16 *v27; // rdi
  __int64 v28; // rax
  int v30; // [rsp+20h] [rbp-99h]
  int v31; // [rsp+30h] [rbp-89h] BYREF
  int v32; // [rsp+34h] [rbp-85h] BYREF
  _BYTE v33[32]; // [rsp+38h] [rbp-81h] BYREF
  __int64 v34; // [rsp+58h] [rbp-61h]
  _BYTE v35[32]; // [rsp+70h] [rbp-49h] BYREF
  char *v36; // [rsp+90h] [rbp-29h]
  unsigned int v37; // [rsp+A0h] [rbp-19h]
  _BYTE v38[48]; // [rsp+A8h] [rbp-11h] BYREF
  int v39; // [rsp+D8h] [rbp+1Fh]

  v32 = 0;
  STRA::STRA((STRA *)v38);
  STRA::STRA((STRA *)v35);
  v31 = 0;
  v7 = ParseDestinationHeader(
         a3,
         &v32,
         (struct STRA *)v38,
         (struct STRA *)v35,
         (enum DESTINATION_HEADER_PARSE_ERROR *)&v31);
  if ( v7 >= 0 )
  {
    if ( v39 )
    {
      v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
      v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      v16 = *(_QWORD *)a2;
      if ( (v32 == 0) != (*(_QWORD *)(v15 + 840) == 0) )
      {
        v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v16 + 272))(a2);
        STRU::STRU((STRU *)v33);
        v18 = 0;
        v19 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, __int64, int))(*(_QWORD *)v17 + 32LL);
        if ( a3 && (int)STRU::CopyA((STRU *)v33, a3) >= 0 )
          v18 = v34;
        v20 = L"If: Header Protocol Scheme Mismatch";
        v21 = v19;
LABEL_28:
        v22 = -2147024809;
        LOBYTE(v30) = 3;
        v21(v17, v20, v18, 2147942487LL, v30);
        STRU::~STRU((STRU *)v33);
LABEL_37:
        v7 = v22;
        goto LABEL_38;
      }
      v23 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v16 + 24))(a2);
      v24 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 16LL))(v23, 28);
      v25 = v24;
      if ( !v24 || !STRA::EqualsNoCase((STRA *)v38, v24) )
      {
        v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
        STRU::STRU((STRU *)v33);
        v18 = 0;
        v26 = SAFE_snwprintf((struct STRU *)v33, L"If: %hs, Host: %hs", a3, v25);
        v20 = L"If: Header Does Not Match Host: Header";
        if ( v26 >= 0 )
          v18 = v34;
        v21 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, __int64, int))(*(_QWORD *)v17 + 32LL);
        goto LABEL_28;
      }
    }
    v22 = CanonicalizeUriPath(v36, v37, a4);
    if ( v22 >= 0 )
    {
      v27 = (const unsigned __int16 *)*((_QWORD *)a4 + 4);
      if ( !(unsigned int)IsValidUri(v27, *((_DWORD *)a4 + 12)) )
      {
        v22 = -2147024809;
        v28 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
        LOBYTE(v30) = 3;
        (*(void (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64, int))(*(_QWORD *)v28 + 32LL))(
          v28,
          L"If: Header Contains Invalid URI After Unescaping",
          v27,
          2147942487LL,
          v30);
      }
    }
    goto LABEL_37;
  }
  v8 = *(_QWORD *)a2;
  if ( v31 == 1 )
  {
    v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v8 + 272))(a2);
    STRU::STRU((STRU *)v33);
    v10 = 0;
    v11 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v9 + 32LL);
    if ( a3 && (int)STRU::CopyA((STRU *)v33, a3) >= 0 )
      v10 = v34;
    v12 = L"If: Header Contains Invalid URI Stem";
  }
  else
  {
    v13 = *(__int64 (__fastcall **)(struct IHttpContext *))(v8 + 272);
    if ( v31 == 2 )
    {
      v9 = v13(a2);
      STRU::STRU((STRU *)v33);
      v10 = 0;
      v11 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v9 + 32LL);
      if ( a3 && (int)STRU::CopyA((STRU *)v33, a3) >= 0 )
        v10 = v34;
      v12 = L"If: Header Contains Invalid Protocol Scheme";
    }
    else if ( v31 == 3 )
    {
      v9 = v13(a2);
      STRU::STRU((STRU *)v33);
      v10 = 0;
      v11 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v9 + 32LL);
      if ( a3 && (int)STRU::CopyA((STRU *)v33, a3) >= 0 )
        v10 = v34;
      v12 = L"If: Header URL Missing Host Component";
    }
    else
    {
      v9 = v13(a2);
      STRU::STRU((STRU *)v33);
      v10 = 0;
      v11 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v9 + 32LL);
      if ( a3 && (int)STRU::CopyA((STRU *)v33, a3) >= 0 )
        v10 = v34;
      v12 = L"If: Header Cannot Be Parsed";
    }
  }
  LOBYTE(v30) = 3;
  v11(v9, v12, v10, (unsigned int)v7, v30);
  STRU::~STRU((STRU *)v33);
LABEL_38:
  STRA::~STRA((STRA *)v35);
  STRA::~STRA((STRA *)v38);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000a9c4  mov     [rsp-8+arg_0], rbx
0x18000a9c9  push    rbp
0x18000a9ca  push    rsi
0x18000a9cb  push    rdi
0x18000a9cc  push    r14
0x18000a9ce  push    r15
0x18000a9d0  lea     rbp, [rsp-37h]
0x18000a9d5  sub     rsp, 0F0h
0x18000a9dc  mov     rax, cs:__security_cookie
0x18000a9e3  xor     rax, rsp
0x18000a9e6  mov     [rbp+57h+var_30], rax
0x18000a9ea  lea     rcx, [rbp+57h+var_68]
0x18000a9ee  mov     [rsp+110h+var_DC], 0
0x18000a9f6  mov     r14, r9
0x18000a9f9  mov     rsi, r8
0x18000a9fc  mov     rbx, rdx
0x18000a9ff  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000aa05  lea     rcx, [rbp+57h+var_A0]
0x18000aa09  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000aa0f  lea     rax, [rsp+110h+var_E0]
0x18000aa14  mov     [rsp+110h+var_E0], 0
0x18000aa1c  lea     r9, [rbp+57h+var_A0]; struct STRA *
0x18000aa20  mov     qword ptr [rsp+110h+var_F0], rax; enum DESTINATION_HEADER_PARSE_ERROR *
0x18000aa25  lea     r8, [rbp+57h+var_68]; struct STRA *
0x18000aa29  mov     rcx, rsi; char *
0x18000aa2c  lea     rdx, [rsp+110h+var_DC]; int *
0x18000aa31  call    ?ParseDestinationHeader@@YAJPEBDPEAHPEAVSTRA@@2PEAW4DESTINATION_HEADER_PARSE_ERROR@@@Z; ParseDestinationHeader(char const *,int *,STRA *,STRA *,DESTINATION_HEADER_PARSE_ERROR *)
0x18000aa36  mov     edi, eax
0x18000aa38  test    eax, eax
0x18000aa3a  jns     loc_18000AB93
0x18000aa40  mov     eax, [rsp+110h+var_E0]
0x18000aa44  mov     rcx, rbx
0x18000aa47  mov     rdx, [rbx]
0x18000aa4a  cmp     eax, 1
0x18000aa4d  jnz     short loc_18000AA98
0x18000aa4f  mov     rax, [rdx+110h]
0x18000aa56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa5b  lea     rcx, [rsp+110h+var_D8]
0x18000aa60  mov     r14, rax
0x18000aa63  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000aa69  mov     rcx, [r14]
0x18000aa6c  xor     ebx, ebx
0x18000aa6e  mov     r15, [rcx+20h]
0x18000aa72  test    rsi, rsi
0x18000aa75  jz      short loc_18000AA8C
0x18000aa77  mov     rdx, rsi
0x18000aa7a  lea     rcx, [rsp+110h+var_D8]
0x18000aa7f  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18000aa85  test    eax, eax
0x18000aa87  cmovns  rbx, [rbp+57h+var_B8]
0x18000aa8c  lea     rdx, aIfHeaderContai; "If: Header Contains Invalid URI Stem"
0x18000aa93  jmp     loc_18000AB6D
0x18000aa98  mov     rdx, [rdx+110h]
0x18000aa9f  cmp     eax, 2
0x18000aaa2  jnz     short loc_18000AAE9
0x18000aaa4  mov     rax, rdx
0x18000aaa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaac  lea     rcx, [rsp+110h+var_D8]
0x18000aab1  mov     r14, rax
0x18000aab4  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000aaba  mov     rcx, [r14]
0x18000aabd  xor     ebx, ebx
0x18000aabf  mov     r15, [rcx+20h]
0x18000aac3  test    rsi, rsi
0x18000aac6  jz      short loc_18000AADD
0x18000aac8  mov     rdx, rsi
0x18000aacb  lea     rcx, [rsp+110h+var_D8]
0x18000aad0  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18000aad6  test    eax, eax
0x18000aad8  cmovns  rbx, [rbp+57h+var_B8]
0x18000aadd  lea     rdx, aIfHeaderContai_1; "If: Header Contains Invalid Protocol Sc"...
0x18000aae4  jmp     loc_18000AB6D
0x18000aae9  cmp     eax, 3
0x18000aaec  mov     rax, rdx
0x18000aaef  jnz     short loc_18000AB30
0x18000aaf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaf6  lea     rcx, [rsp+110h+var_D8]
0x18000aafb  mov     r14, rax
0x18000aafe  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000ab04  mov     rcx, [r14]
0x18000ab07  xor     ebx, ebx
0x18000ab09  mov     r15, [rcx+20h]
0x18000ab0d  test    rsi, rsi
0x18000ab10  jz      short loc_18000AB27
0x18000ab12  mov     rdx, rsi
0x18000ab15  lea     rcx, [rsp+110h+var_D8]
0x18000ab1a  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18000ab20  test    eax, eax
0x18000ab22  cmovns  rbx, [rbp+57h+var_B8]
0x18000ab27  lea     rdx, aIfHeaderUrlMis; "If: Header URL Missing Host Component"
0x18000ab2e  jmp     short loc_18000AB6D
0x18000ab30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab35  lea     rcx, [rsp+110h+var_D8]
0x18000ab3a  mov     r14, rax
0x18000ab3d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000ab43  mov     rcx, [r14]
0x18000ab46  xor     ebx, ebx
0x18000ab48  mov     r15, [rcx+20h]
0x18000ab4c  test    rsi, rsi
0x18000ab4f  jz      short loc_18000AB66
0x18000ab51  mov     rdx, rsi
0x18000ab54  lea     rcx, [rsp+110h+var_D8]
0x18000ab59  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18000ab5f  test    eax, eax
0x18000ab61  cmovns  rbx, [rbp+57h+var_B8]
0x18000ab66  lea     rdx, aIfHeaderCannot; "If: Header Cannot Be Parsed"
0x18000ab6d  mov     r8, rbx
0x18000ab70  mov     byte ptr [rsp+110h+var_F0], 3
0x18000ab75  mov     r9d, edi
0x18000ab78  mov     rcx, r14
0x18000ab7b  mov     rax, r15
0x18000ab7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab83  lea     rcx, [rsp+110h+var_D8]
0x18000ab88  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ab8e  jmp     loc_18000AD44
0x18000ab93  cmp     [rbp+57h+var_38], 0
0x18000ab97  jbe     loc_18000ACDE
0x18000ab9d  mov     rax, [rbx]
0x18000aba0  mov     rcx, rbx
0x18000aba3  mov     rax, [rax+18h]
0x18000aba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abac  mov     rdx, rax
0x18000abaf  mov     rcx, [rax]
0x18000abb2  mov     rax, [rcx+8]
0x18000abb6  mov     rcx, rdx
0x18000abb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abbe  mov     r8, [rbx]
0x18000abc1  xor     edx, edx
0x18000abc3  cmp     [rsp+110h+var_DC], edx
0x18000abc7  mov     rcx, [rax+348h]
0x18000abce  setz    dl
0x18000abd1  xor     eax, eax
0x18000abd3  test    rcx, rcx
0x18000abd6  mov     rcx, rbx
0x18000abd9  setz    al
0x18000abdc  cmp     edx, eax
0x18000abde  jz      short loc_18000AC4F
0x18000abe0  mov     rax, [r8+110h]
0x18000abe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abec  lea     rcx, [rsp+110h+var_D8]
0x18000abf1  mov     rdi, rax
0x18000abf4  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000abfa  mov     rcx, [rdi]
0x18000abfd  xor     ebx, ebx
0x18000abff  mov     r14, [rcx+20h]
0x18000ac03  test    rsi, rsi
0x18000ac06  jz      short loc_18000AC1D
0x18000ac08  mov     rdx, rsi
0x18000ac0b  lea     rcx, [rsp+110h+var_D8]
0x18000ac10  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18000ac16  test    eax, eax
0x18000ac18  cmovns  rbx, [rbp+57h+var_B8]
0x18000ac1d  lea     rdx, aIfHeaderProtoc; "If: Header Protocol Scheme Mismatch"
0x18000ac24  mov     rax, r14
0x18000ac27  mov     esi, 80070057h
0x18000ac2c  mov     byte ptr [rsp+110h+var_F0], 3
0x18000ac31  mov     r9d, esi
0x18000ac34  mov     rcx, rdi
0x18000ac37  mov     r8, rbx
0x18000ac3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac3f  lea     rcx, [rsp+110h+var_D8]
0x18000ac44  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ac4a  jmp     loc_18000AD42
0x18000ac4f  mov     rax, [r8+18h]
0x18000ac53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac58  mov     r9, rax
0x18000ac5b  xor     r8d, r8d
0x18000ac5e  mov     rcx, [rax]
0x18000ac61  lea     edx, [r8+1Ch]
0x18000ac65  mov     rax, [rcx+10h]
0x18000ac69  mov     rcx, r9
0x18000ac6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac71  mov     r15, rax
0x18000ac74  test    rax, rax
0x18000ac77  jz      short loc_18000AC8A
0x18000ac79  mov     rdx, rax
0x18000ac7c  lea     rcx, [rbp+57h+var_68]
0x18000ac80  call    cs:__imp_?EqualsNoCase@STRA@@QEBA_NPEBD@Z; STRA::EqualsNoCase(char const *)
0x18000ac86  test    al, al
0x18000ac88  jnz     short loc_18000ACDE
0x18000ac8a  mov     rcx, [rbx]
0x18000ac8d  mov     rax, [rcx+110h]
0x18000ac94  mov     rcx, rbx
0x18000ac97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac9c  lea     rcx, [rsp+110h+var_D8]
0x18000aca1  mov     rdi, rax
0x18000aca4  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000acaa  mov     r9, r15
0x18000acad  lea     rdx, aIfHsHostHs; "If: %hs, Host: %hs"
0x18000acb4  mov     r8, rsi
0x18000acb7  lea     rcx, [rsp+110h+var_D8]
0x18000acbc  xor     ebx, ebx
0x18000acbe  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x18000acc4  test    eax, eax
0x18000acc6  lea     rdx, aIfHeaderDoesNo; "If: Header Does Not Match Host: Header"
0x18000accd  mov     rax, [rdi]
0x18000acd0  cmovns  rbx, [rbp+57h+var_B8]
0x18000acd5  mov     rax, [rax+20h]
0x18000acd9  jmp     loc_18000AC27
0x18000acde  mov     edx, [rbp+57h+var_70]; unsigned int
0x18000ace1  mov     r8, r14; struct STRU *
0x18000ace4  mov     rcx, [rbp+57h+var_80]; char *
0x18000ace8  call    ?CanonicalizeUriPath@@YAJPEBDKPEAVSTRU@@@Z; CanonicalizeUriPath(char const *,ulong,STRU *)
0x18000aced  mov     esi, eax
0x18000acef  test    eax, eax
0x18000acf1  js      short loc_18000AD42
0x18000acf3  mov     rdi, [r14+20h]
0x18000acf7  mov     edx, [r14+30h]; unsigned int
0x18000acfb  mov     rcx, rdi; unsigned __int16 *
0x18000acfe  call    ?IsValidUri@@YAHPEBGK@Z; IsValidUri(ushort const *,ulong)
0x18000ad03  test    eax, eax
0x18000ad05  jnz     short loc_18000AD42
0x18000ad07  mov     rax, [rbx]
0x18000ad0a  mov     rcx, rbx
0x18000ad0d  mov     esi, 80070057h
0x18000ad12  mov     rax, [rax+110h]
0x18000ad19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad1e  mov     r10, rax
0x18000ad21  mov     byte ptr [rsp+110h+var_F0], 3
0x18000ad26  mov     r9d, esi
0x18000ad29  lea     rdx, aIfHeaderContai_0; "If: Header Contains Invalid URI After U"...
0x18000ad30  mov     r8, rdi
0x18000ad33  mov     rcx, [rax]
0x18000ad36  mov     rax, [rcx+20h]
0x18000ad3a  mov     rcx, r10
0x18000ad3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad42  mov     edi, esi
0x18000ad44  lea     rcx, [rbp+57h+var_A0]
0x18000ad48  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000ad4e  lea     rcx, [rbp+57h+var_68]
0x18000ad52  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000ad58  mov     eax, edi
0x18000ad5a  mov     rcx, [rbp+57h+var_30]
0x18000ad5e  xor     rcx, rsp; StackCookie
0x18000ad61  call    __security_check_cookie
0x18000ad66  mov     rbx, [rsp+110h+arg_0]
0x18000ad6e  add     rsp, 0F0h
0x18000ad75  pop     r15
0x18000ad77  pop     r14
0x18000ad79  pop     rdi
0x18000ad7a  pop     rsi
0x18000ad7b  pop     rbp
0x18000ad7c  retn
```
