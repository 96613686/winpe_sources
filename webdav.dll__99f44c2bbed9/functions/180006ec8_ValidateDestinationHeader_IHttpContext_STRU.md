# ValidateDestinationHeader(IHttpContext *,STRU *)

- ea: `0x180006ec8`
- end: `0x18000728d`
- name: `?ValidateDestinationHeader@@YAJPEAVIHttpContext@@PEAVSTRU@@@Z`
- size: `965`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct STRU *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180002740`

## callees

- `0x180006194`
- `0x180006ec8`
- `0x18001a468`
- `0x18001c33c`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180007257`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007261`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007257`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007261`
- `iisutil!SAFE_snwprintf` at `0x180007186`
- `iisutil!SAFE_snwprintf` at `0x180007186`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006fa5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006feb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007026`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000705c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800070e6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000716c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006fa5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006feb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007026`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000705c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800070e6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000716c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800071bf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800071bf`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180006fbc`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180007002`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000703d`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180007073`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800070fd`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180006fbc`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180007002`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000703d`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180007073`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800070fd`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NPEBD@Z` at `0x180007148`
- `iisutil!?EqualsNoCase@STRA@@QEBA_NPEBD@Z` at `0x180007148`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180006f00`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180006f0a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180006f00`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180006f0a`

## string_xrefs

- `0x18000720e`: `Destination: Header Contains Invalid URI After Unescaping`
- `0x180007103`: `Destination: Header Protocol Scheme Mismatch`
- `0x180007043`: `Destination: Header URL Missing Host Component`
- `0x180007008`: `Destination: Header Contains Invalid Protocol Scheme`
- `0x180006fc2`: `Destination: Header Contains Invalid URI Stem`

## pseudocode

```c
__int64 __fastcall ValidateDestinationHeader(struct IHttpContext *a1, struct STRU *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  const char *v6; // rax
  const char *v7; // r15
  int v8; // r14d
  __int64 (__fastcall *v9)(struct IHttpContext *); // rax
  __int64 v10; // rsi
  __int64 v11; // rbx
  void (__fastcall *v12)(__int64, const wchar_t *, __int64, _QWORD, int); // rdi
  int v13; // eax
  const wchar_t *v14; // rdx
  bool v15; // sf
  __int64 v16; // rcx
  void (__fastcall *v17)(__int64, const wchar_t *, __int64, _QWORD, int); // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rsi
  void (__fastcall *v22)(__int64, const wchar_t *, __int64, _QWORD, int); // rdi
  int v23; // eax
  __int64 v24; // rax
  const char *v25; // rax
  const char *v26; // rsi
  __int64 v27; // rdi
  int v28; // eax
  const unsigned __int16 *v29; // rsi
  __int64 v30; // rax
  const unsigned __int16 *v31; // r8
  const wchar_t *v32; // rdx
  int v34; // [rsp+20h] [rbp-99h]
  int v35; // [rsp+30h] [rbp-89h] BYREF
  int v36; // [rsp+34h] [rbp-85h] BYREF
  _BYTE v37[32]; // [rsp+38h] [rbp-81h] BYREF
  __int64 v38; // [rsp+58h] [rbp-61h]
  _BYTE v39[32]; // [rsp+70h] [rbp-49h] BYREF
  char *v40; // [rsp+90h] [rbp-29h]
  unsigned int v41; // [rsp+A0h] [rbp-19h]
  _BYTE v42[48]; // [rsp+A8h] [rbp-11h] BYREF
  int v43; // [rsp+D8h] [rbp+1Fh]

  v36 = 0;
  STRA::STRA((STRA *)v42);
  STRA::STRA((STRA *)v39);
  v4 = *(_QWORD *)a1;
  v35 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v4 + 24))(a1);
  v6 = (const char *)(*(__int64 (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v5 + 24LL))(
                       v5,
                       "Destination",
                       0);
  v7 = v6;
  if ( !v6 || !*v6 )
  {
    v30 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    v31 = 0;
    v32 = L"Destination: Header Required But Missing";
    v8 = -2147024809;
    goto LABEL_26;
  }
  v8 = ParseDestinationHeader(
         v6,
         &v36,
         (struct STRA *)v42,
         (struct STRA *)v39,
         (enum DESTINATION_HEADER_PARSE_ERROR *)&v35);
  if ( v8 >= 0 )
  {
    if ( v43 )
    {
      v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
      v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
      v20 = *(_QWORD *)a1;
      if ( (v36 == 0) != (*(_QWORD *)(v19 + 840) == 0) )
      {
        v21 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v20 + 272))(a1);
        STRU::STRU((STRU *)v37);
        v11 = 0;
        v22 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v21 + 32LL);
        v23 = STRU::CopyA((STRU *)v37, v7);
        v14 = L"Destination: Header Protocol Scheme Mismatch";
        v16 = v21;
        v15 = v23 < 0;
        v17 = v22;
LABEL_18:
        v8 = -2147024809;
        goto LABEL_19;
      }
      v24 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v20 + 24))(a1);
      v25 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 16LL))(v24, 28);
      v26 = v25;
      if ( !v25 || !STRA::EqualsNoCase((STRA *)v42, v25) )
      {
        v27 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
        STRU::STRU((STRU *)v37);
        v11 = 0;
        v28 = SAFE_snwprintf((struct STRU *)v37, L"Destination: %hs, Host: %hs", v7, v26);
        v14 = L"Destination: Header Does Not Match Host: Header";
        v16 = v27;
        v15 = v28 < 0;
        v17 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v27 + 32LL);
        goto LABEL_18;
      }
    }
    v8 = CanonicalizeUriPath(v40, v41, a2);
    if ( v8 < 0 )
      goto LABEL_27;
    v29 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
    if ( (unsigned int)IsValidUri(v29, *((_DWORD *)a2 + 12)) )
      goto LABEL_27;
    v8 = -2147024809;
    v30 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    v31 = v29;
    v32 = L"Destination: Header Contains Invalid URI After Unescaping";
LABEL_26:
    LOBYTE(v34) = 3;
    (*(void (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64, int))(*(_QWORD *)v30 + 32LL))(
      v30,
      v32,
      v31,
      2147942487LL,
      v34);
    goto LABEL_27;
  }
  v9 = *(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL);
  switch ( v35 )
  {
    case 1:
      v10 = v9(a1);
      STRU::STRU((STRU *)v37);
      v11 = 0;
      v12 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v10 + 32LL);
      v13 = STRU::CopyA((STRU *)v37, v7);
      v14 = L"Destination: Header Contains Invalid URI Stem";
      break;
    case 2:
      v10 = v9(a1);
      STRU::STRU((STRU *)v37);
      v11 = 0;
      v12 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v10 + 32LL);
      v13 = STRU::CopyA((STRU *)v37, v7);
      v14 = L"Destination: Header Contains Invalid Protocol Scheme";
      break;
    case 3:
      v10 = v9(a1);
      STRU::STRU((STRU *)v37);
      v11 = 0;
      v12 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v10 + 32LL);
      v13 = STRU::CopyA((STRU *)v37, v7);
      v14 = L"Destination: Header URL Missing Host Component";
      break;
    default:
      v10 = v9(a1);
      STRU::STRU((STRU *)v37);
      v11 = 0;
      v12 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v10 + 32LL);
      v13 = STRU::CopyA((STRU *)v37, v7);
      v14 = L"Destination: Header Cannot Be Parsed";
      break;
  }
  v15 = v13 < 0;
  v16 = v10;
  v17 = v12;
LABEL_19:
  if ( !v15 )
    v11 = v38;
  LOBYTE(v34) = 3;
  v17(v16, v14, v11, (unsigned int)v8, v34);
  STRU::~STRU((STRU *)v37);
LABEL_27:
  STRA::~STRA((STRA *)v39);
  STRA::~STRA((STRA *)v42);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006ec8  mov     [rsp-8+arg_10], rbx
0x180006ecd  push    rbp
0x180006ece  push    rsi
0x180006ecf  push    rdi
0x180006ed0  push    r14
0x180006ed2  push    r15
0x180006ed4  lea     rbp, [rsp-37h]
0x180006ed9  sub     rsp, 0F0h
0x180006ee0  mov     rax, cs:__security_cookie
0x180006ee7  xor     rax, rsp
0x180006eea  mov     [rbp+57h+var_30], rax
0x180006eee  mov     rbx, rcx
0x180006ef1  mov     [rsp+110h+var_DC], 0
0x180006ef9  lea     rcx, [rbp+57h+var_68]
0x180006efd  mov     rdi, rdx
0x180006f00  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180006f06  lea     rcx, [rbp+57h+var_A0]
0x180006f0a  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180006f10  mov     rax, [rbx]
0x180006f13  mov     rcx, rbx
0x180006f16  mov     [rsp+110h+var_E0], 0
0x180006f1e  mov     rax, [rax+18h]
0x180006f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f27  mov     r9, rax
0x180006f2a  lea     rdx, aDestination; "Destination"
0x180006f31  xor     r8d, r8d
0x180006f34  mov     rcx, [rax]
0x180006f37  mov     rax, [rcx+18h]
0x180006f3b  mov     rcx, r9
0x180006f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f43  mov     r15, rax
0x180006f46  test    rax, rax
0x180006f49  jz      loc_180007217
0x180006f4f  cmp     byte ptr [rax], 0
0x180006f52  jz      loc_180007217
0x180006f58  lea     rax, [rsp+110h+var_E0]
0x180006f5d  mov     rcx, r15; char *
0x180006f60  lea     r9, [rbp+57h+var_A0]; struct STRA *
0x180006f64  mov     qword ptr [rsp+110h+var_F0], rax; enum DESTINATION_HEADER_PARSE_ERROR *
0x180006f69  lea     r8, [rbp+57h+var_68]; struct STRA *
0x180006f6d  lea     rdx, [rsp+110h+var_DC]; int *
0x180006f72  call    ?ParseDestinationHeader@@YAJPEBDPEAHPEAVSTRA@@2PEAW4DESTINATION_HEADER_PARSE_ERROR@@@Z; ParseDestinationHeader(char const *,int *,STRA *,STRA *,DESTINATION_HEADER_PARSE_ERROR *)
0x180006f77  mov     r14d, eax
0x180006f7a  test    eax, eax
0x180006f7c  jns     loc_180007085
0x180006f82  mov     rax, [rbx]
0x180006f85  mov     ecx, [rsp+110h+var_E0]
0x180006f89  mov     rax, [rax+110h]
0x180006f90  cmp     ecx, 1
0x180006f93  jnz     short loc_180006FD6
0x180006f95  mov     rcx, rbx
0x180006f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f9d  lea     rcx, [rsp+110h+var_D8]
0x180006fa2  mov     rsi, rax
0x180006fa5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006fab  mov     rcx, [rsi]
0x180006fae  xor     ebx, ebx
0x180006fb0  mov     rdx, r15
0x180006fb3  mov     rdi, [rcx+20h]
0x180006fb7  lea     rcx, [rsp+110h+var_D8]
0x180006fbc  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180006fc2  lea     rdx, aDestinationHea_4; "Destination: Header Contains Invalid UR"...
0x180006fc9  test    eax, eax
0x180006fcb  mov     rcx, rsi
0x180006fce  mov     rax, rdi
0x180006fd1  jmp     loc_1800071A5
0x180006fd6  cmp     ecx, 2
0x180006fd9  jnz     short loc_180007011
0x180006fdb  mov     rcx, rbx
0x180006fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fe3  lea     rcx, [rsp+110h+var_D8]
0x180006fe8  mov     rsi, rax
0x180006feb  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006ff1  mov     rcx, [rsi]
0x180006ff4  xor     ebx, ebx
0x180006ff6  mov     rdx, r15
0x180006ff9  mov     rdi, [rcx+20h]
0x180006ffd  lea     rcx, [rsp+110h+var_D8]
0x180007002  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180007008  lea     rdx, aDestinationHea_3; "Destination: Header Contains Invalid Pr"...
0x18000700f  jmp     short loc_180006FC9
0x180007011  cmp     ecx, 3
0x180007014  mov     rcx, rbx
0x180007017  jnz     short loc_18000704F
0x180007019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000701e  lea     rcx, [rsp+110h+var_D8]
0x180007023  mov     rsi, rax
0x180007026  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000702c  mov     rcx, [rsi]
0x18000702f  xor     ebx, ebx
0x180007031  mov     rdx, r15
0x180007034  mov     rdi, [rcx+20h]
0x180007038  lea     rcx, [rsp+110h+var_D8]
0x18000703d  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180007043  lea     rdx, aDestinationHea_5; "Destination: Header URL Missing Host Co"...
0x18000704a  jmp     loc_180006FC9
0x18000704f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007054  lea     rcx, [rsp+110h+var_D8]
0x180007059  mov     rsi, rax
0x18000705c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180007062  mov     rcx, [rsi]
0x180007065  xor     ebx, ebx
0x180007067  mov     rdx, r15
0x18000706a  mov     rdi, [rcx+20h]
0x18000706e  lea     rcx, [rsp+110h+var_D8]
0x180007073  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180007079  lea     rdx, aDestinationHea; "Destination: Header Cannot Be Parsed"
0x180007080  jmp     loc_180006FC9
0x180007085  cmp     [rbp+57h+var_38], 0
0x180007089  jbe     loc_1800071CA
0x18000708f  mov     rax, [rbx]
0x180007092  mov     rcx, rbx
0x180007095  mov     rax, [rax+18h]
0x180007099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000709e  mov     rdx, rax
0x1800070a1  mov     rcx, [rax]
0x1800070a4  mov     rax, [rcx+8]
0x1800070a8  mov     rcx, rdx
0x1800070ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070b0  mov     r8, [rbx]
0x1800070b3  xor     edx, edx
0x1800070b5  cmp     [rsp+110h+var_DC], edx
0x1800070b9  mov     rcx, [rax+348h]
0x1800070c0  setz    dl
0x1800070c3  xor     eax, eax
0x1800070c5  test    rcx, rcx
0x1800070c8  mov     rcx, rbx
0x1800070cb  setz    al
0x1800070ce  cmp     edx, eax
0x1800070d0  jz      short loc_180007117
0x1800070d2  mov     rax, [r8+110h]
0x1800070d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070de  lea     rcx, [rsp+110h+var_D8]
0x1800070e3  mov     rsi, rax
0x1800070e6  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800070ec  mov     rcx, [rsi]
0x1800070ef  mov     rdx, r15
0x1800070f2  xor     ebx, ebx
0x1800070f4  mov     rdi, [rcx+20h]
0x1800070f8  lea     rcx, [rsp+110h+var_D8]
0x1800070fd  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180007103  lea     rdx, aDestinationHea_6; "Destination: Header Protocol Scheme Mis"...
0x18000710a  mov     rcx, rsi
0x18000710d  test    eax, eax
0x18000710f  mov     rax, rdi
0x180007112  jmp     loc_18000719F
0x180007117  mov     rax, [r8+18h]
0x18000711b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007120  mov     r9, rax
0x180007123  xor     r8d, r8d
0x180007126  mov     rcx, [rax]
0x180007129  lea     edx, [r8+1Ch]
0x18000712d  mov     rax, [rcx+10h]
0x180007131  mov     rcx, r9
0x180007134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007139  mov     rsi, rax
0x18000713c  test    rax, rax
0x18000713f  jz      short loc_180007152
0x180007141  mov     rdx, rax
0x180007144  lea     rcx, [rbp+57h+var_68]
0x180007148  call    cs:__imp_?EqualsNoCase@STRA@@QEBA_NPEBD@Z; STRA::EqualsNoCase(char const *)
0x18000714e  test    al, al
0x180007150  jnz     short loc_1800071CA
0x180007152  mov     rcx, [rbx]
0x180007155  mov     rax, [rcx+110h]
0x18000715c  mov     rcx, rbx
0x18000715f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007164  lea     rcx, [rsp+110h+var_D8]
0x180007169  mov     rdi, rax
0x18000716c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180007172  mov     r9, rsi
0x180007175  lea     rdx, aDestinationHsH; "Destination: %hs, Host: %hs"
0x18000717c  mov     r8, r15
0x18000717f  lea     rcx, [rsp+110h+var_D8]
0x180007184  xor     ebx, ebx
0x180007186  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x18000718c  lea     rdx, aDestinationHea_1; "Destination: Header Does Not Match Host"...
0x180007193  mov     rcx, rdi
0x180007196  test    eax, eax
0x180007198  mov     rax, [rdi]
0x18000719b  mov     rax, [rax+20h]
0x18000719f  mov     r14d, 80070057h
0x1800071a5  cmovns  rbx, [rbp+57h+var_B8]
0x1800071aa  mov     r9d, r14d
0x1800071ad  mov     r8, rbx
0x1800071b0  mov     byte ptr [rsp+110h+var_F0], 3
0x1800071b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071ba  lea     rcx, [rsp+110h+var_D8]
0x1800071bf  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800071c5  jmp     loc_180007253
0x1800071ca  mov     edx, [rbp+57h+var_70]; unsigned int
0x1800071cd  mov     r8, rdi; struct STRU *
0x1800071d0  mov     rcx, [rbp+57h+var_80]; char *
0x1800071d4  call    ?CanonicalizeUriPath@@YAJPEBDKPEAVSTRU@@@Z; CanonicalizeUriPath(char const *,ulong,STRU *)
0x1800071d9  mov     r14d, eax
0x1800071dc  test    eax, eax
0x1800071de  js      short loc_180007253
0x1800071e0  mov     rsi, [rdi+20h]
0x1800071e4  mov     edx, [rdi+30h]; unsigned int
0x1800071e7  mov     rcx, rsi; unsigned __int16 *
0x1800071ea  call    ?IsValidUri@@YAHPEBGK@Z; IsValidUri(ushort const *,ulong)
0x1800071ef  test    eax, eax
0x1800071f1  jnz     short loc_180007253
0x1800071f3  mov     rax, [rbx]
0x1800071f6  mov     rcx, rbx
0x1800071f9  mov     r14d, 80070057h
0x1800071ff  mov     rax, [rax+110h]
0x180007206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000720b  mov     r8, rsi
0x18000720e  lea     rdx, aDestinationHea_0; "Destination: Header Contains Invalid UR"...
0x180007215  jmp     short loc_180007239
0x180007217  mov     rax, [rbx]
0x18000721a  mov     rcx, rbx
0x18000721d  mov     rax, [rax+110h]
0x180007224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007229  xor     r8d, r8d
0x18000722c  lea     rdx, aDestinationHea_2; "Destination: Header Required But Missin"...
0x180007233  mov     r14d, 80070057h
0x180007239  mov     rcx, [rax]
0x18000723c  mov     r10, rax
0x18000723f  mov     r9d, r14d
0x180007242  mov     byte ptr [rsp+110h+var_F0], 3
0x180007247  mov     rax, [rcx+20h]
0x18000724b  mov     rcx, r10
0x18000724e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007253  lea     rcx, [rbp+57h+var_A0]
0x180007257  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000725d  lea     rcx, [rbp+57h+var_68]
0x180007261  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007267  mov     eax, r14d
0x18000726a  mov     rcx, [rbp+57h+var_30]
0x18000726e  xor     rcx, rsp; StackCookie
0x180007271  call    __security_check_cookie
0x180007276  mov     rbx, [rsp+110h+arg_10]
0x18000727e  add     rsp, 0F0h
0x180007285  pop     r15
0x180007287  pop     r14
0x180007289  pop     rdi
0x18000728a  pop     rsi
0x18000728b  pop     rbp
0x18000728c  retn
```
