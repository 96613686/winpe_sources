# ValidateLockTokenHeader(IHttpContext *,STRU *)

- ea: `0x180007294`
- end: `0x180007413`
- name: `?ValidateLockTokenHeader@@YAJPEAVIHttpContext@@PEAVSTRU@@@Z`
- size: `383`
- prototype: `int(struct IHttpContext *, struct STRU *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180010f50`

## callees

- `0x180007294`
- `0x18001c3c8`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x1800073bf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800073bf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007406`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007406`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800073d6`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800073d6`

## string_xrefs

- `0x1800072cd`: `Lock-Token`
- `0x1800073e6`: `Lock-Token: Header Invalid`
- `0x18000732c`: `Lock-Token: Header Missing`

## pseudocode

```c
__int64 __fastcall ValidateLockTokenHeader(struct IHttpContext *a1, struct STRU *a2)
{
  __int64 v4; // rax
  char *v5; // rax
  const char *v6; // r14
  char v7; // cl
  char *v8; // rdx
  __int64 v9; // rax
  int AngleBracketString; // ebp
  __int64 v12; // rsi
  __int64 v13; // rbx
  void (__fastcall *v14)(__int64, const wchar_t *, __int64, _QWORD, char); // rdi
  char v15; // [rsp+20h] [rbp-78h]
  char v16; // [rsp+20h] [rbp-78h]
  char *v17; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v18[32]; // [rsp+38h] [rbp-60h] BYREF
  __int64 v19; // [rsp+58h] [rbp-40h]

  v4 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v5 = (char *)(*(__int64 (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v4 + 24LL))(v4, "Lock-Token", 0);
  v6 = v5;
  if ( !v5 || !*v5 )
    goto LABEL_7;
  v7 = *v5;
  v8 = v5;
  while ( v7 == 32 || v7 == 9 )
  {
    v7 = *++v8;
    if ( !*v8 )
      goto LABEL_7;
  }
  v17 = v8;
  if ( !v7 )
  {
LABEL_7:
    v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    v15 = 3;
    (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, char))(*(_QWORD *)v9 + 32LL))(
      v9,
      L"Lock-Token: Header Missing",
      0,
      0,
      v15);
    return 2377062656LL;
  }
  if ( *v8 != 60 )
    goto LABEL_12;
  AngleBracketString = GetAngleBracketString((const char **)&v17, 0, a2);
  if ( AngleBracketString < 0 )
  {
LABEL_14:
    v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    STRU::STRU((STRU *)v18);
    v13 = 0;
    v14 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, char))(*(_QWORD *)v12 + 32LL);
    v16 = 3;
    if ( (int)STRU::CopyA((STRU *)v18, v6) >= 0 )
      v13 = v19;
    v14(v12, L"Lock-Token: Header Invalid", v13, (unsigned int)AngleBracketString, v16);
    STRU::~STRU((STRU *)v18);
    return (unsigned int)AngleBracketString;
  }
  if ( *v17 )
LABEL_12:
    AngleBracketString = -1917904640;
  if ( AngleBracketString < 0 )
    goto LABEL_14;
  return (unsigned int)AngleBracketString;
}

```

## disassembly

```asm
0x180007294  mov     [rsp+arg_10], rbx
0x180007299  mov     [rsp+arg_18], rbp
0x18000729e  push    rsi
0x18000729f  push    rdi
0x1800072a0  push    r14
0x1800072a2  sub     rsp, 80h
0x1800072a9  mov     rax, cs:__security_cookie
0x1800072b0  xor     rax, rsp
0x1800072b3  mov     [rsp+98h+var_28], rax
0x1800072b8  mov     rax, [rcx]
0x1800072bb  mov     rdi, rdx
0x1800072be  mov     rbx, rcx
0x1800072c1  mov     rax, [rax+18h]
0x1800072c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072ca  mov     r9, rax
0x1800072cd  lea     rdx, aLockToken; "Lock-Token"
0x1800072d4  xor     r8d, r8d
0x1800072d7  mov     rcx, [rax]
0x1800072da  mov     rax, [rcx+18h]
0x1800072de  mov     rcx, r9
0x1800072e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072e6  mov     r14, rax
0x1800072e9  test    rax, rax
0x1800072ec  jz      short loc_18000730F
0x1800072ee  cmp     byte ptr [rax], 0
0x1800072f1  jz      short loc_18000730F
0x1800072f3  mov     cl, [rax]
0x1800072f5  test    cl, cl
0x1800072f7  jz      short loc_18000730F
0x1800072f9  mov     rdx, rax
0x1800072fc  cmp     cl, 20h ; ' '
0x1800072ff  jz      short loc_180007306
0x180007301  cmp     cl, 9
0x180007304  jnz     short loc_18000736F
0x180007306  inc     rdx
0x180007309  mov     cl, [rdx]
0x18000730b  test    cl, cl
0x18000730d  jnz     short loc_1800072FC
0x18000730f  mov     rax, [rbx]
0x180007312  mov     rcx, rbx
0x180007315  mov     rax, [rax+110h]
0x18000731c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007321  mov     r10, rax
0x180007324  mov     [rsp+98h+var_78], 3
0x180007329  xor     r9d, r9d
0x18000732c  lea     rdx, aLockTokenHeade_0; "Lock-Token: Header Missing"
0x180007333  xor     r8d, r8d
0x180007336  mov     rcx, [rax]
0x180007339  mov     rax, [rcx+20h]
0x18000733d  mov     rcx, r10
0x180007340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007345  mov     eax, 8DAF1900h
0x18000734a  mov     rcx, [rsp+98h+var_28]
0x18000734f  xor     rcx, rsp; StackCookie
0x180007352  call    __security_check_cookie
0x180007357  lea     r11, [rsp+98h+var_18]
0x18000735f  mov     rbx, [r11+30h]
0x180007363  mov     rbp, [r11+38h]
0x180007367  mov     rsp, r11
0x18000736a  pop     r14
0x18000736c  pop     rdi
0x18000736d  pop     rsi
0x18000736e  retn
0x18000736f  mov     [rsp+98h+var_68], rdx
0x180007374  test    cl, cl
0x180007376  jz      short loc_18000730F
0x180007378  cmp     byte ptr [rdx], 3Ch ; '<'
0x18000737b  jnz     short loc_18000739C
0x18000737d  mov     r8, rdi; struct STRU *
0x180007380  lea     rcx, [rsp+98h+var_68]; char **
0x180007385  xor     edx, edx; struct STRA *
0x180007387  call    ?GetAngleBracketString@@YAJPEAPEBDPEAVSTRA@@PEAVSTRU@@@Z; GetAngleBracketString(char const * *,STRA *,STRU *)
0x18000738c  mov     ebp, eax
0x18000738e  test    eax, eax
0x180007390  js      short loc_1800073A5
0x180007392  mov     rcx, [rsp+98h+var_68]
0x180007397  cmp     byte ptr [rcx], 0
0x18000739a  jz      short loc_1800073A1
0x18000739c  mov     ebp, 8DAF1900h
0x1800073a1  test    ebp, ebp
0x1800073a3  jns     short loc_18000740C
0x1800073a5  mov     rax, [rbx]
0x1800073a8  mov     rcx, rbx
0x1800073ab  mov     rax, [rax+110h]
0x1800073b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b7  lea     rcx, [rsp+98h+var_60]
0x1800073bc  mov     rsi, rax
0x1800073bf  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800073c5  mov     rcx, [rsi]
0x1800073c8  mov     rdx, r14
0x1800073cb  xor     ebx, ebx
0x1800073cd  mov     rdi, [rcx+20h]
0x1800073d1  lea     rcx, [rsp+98h+var_60]
0x1800073d6  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x1800073dc  mov     r9d, ebp
0x1800073df  mov     [rsp+98h+var_78], 3
0x1800073e4  test    eax, eax
0x1800073e6  lea     rdx, aLockTokenHeade; "Lock-Token: Header Invalid"
0x1800073ed  mov     rcx, rsi
0x1800073f0  mov     rax, rdi
0x1800073f3  cmovns  rbx, [rsp+98h+var_40]
0x1800073f9  mov     r8, rbx
0x1800073fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007401  lea     rcx, [rsp+98h+var_60]
0x180007406  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000740c  mov     eax, ebp
0x18000740e  jmp     loc_18000734A
```
