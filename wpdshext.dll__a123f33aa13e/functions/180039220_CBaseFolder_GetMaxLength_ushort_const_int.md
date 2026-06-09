# CBaseFolder::GetMaxLength(ushort const *,int *)

- ea: `0x180039220`
- end: `0x180039484`
- name: `?GetMaxLength@CBaseFolder@@UEAAJPEBGPEAH@Z`
- size: `612`
- prototype: `int(CBaseFolder *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180004110`
- `0x180019270`
- `0x18001a5b0`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180039220`
- `0x18006d384`

## import_xrefs

- `SHLWAPI!PathStripPathW` at `0x18003936a`
- `SHLWAPI!PathStripPathW` at `0x18003936a`
- `SHLWAPI!PathAddBackslashW` at `0x1800393bb`
- `SHLWAPI!PathAddBackslashW` at `0x1800393bb`
- `SHLWAPI!PathAppendW` at `0x1800393cd`
- `SHLWAPI!PathAppendW` at `0x1800393cd`
- `SHELL32!SHGetSettings` at `0x1800392c8`
- `SHELL32!SHGetSettings` at `0x1800392c8`

## pseudocode

```c
__int64 __fastcall CBaseFolder::GetMaxLength(LPCITEMIDLIST *this, const unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int CCHMaxFromPath; // ebx
  int v7; // esi
  int v8; // eax
  PVOID *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax
  unsigned int v14; // [rsp+30h] [rbp-D0h] BYREF
  SHELLFLAGSTATE psfs; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v18[264]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(pszPath, 0, 0x208u);
  memset_0(v18, 0, 0x208u);
  v14 = 0;
  v16 = 0;
  if ( !a2 )
  {
    CCHMaxFromPath = -2147024809;
LABEL_30:
    v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_31:
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
      WPP_SF_d(v9[2], 23, WPP_f4dfe53786183352449e3e96734e584d_Traceguids, CCHMaxFromPath);
    return CCHMaxFromPath;
  }
  if ( !a3 )
  {
    CCHMaxFromPath = -2147467261;
    goto LABEL_30;
  }
  *a3 = 0;
  psfs = 0;
  SHGetSettings(&psfs, 2u);
  v7 = (unsigned __int8)(*(_BYTE *)&psfs & 2) >> 1;
  v8 = SHGetNameAndFlagsW(this[4], 0);
  CCHMaxFromPath = v8;
  if ( v8 < 0 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return CCHMaxFromPath;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_31;
    v10 = 19;
LABEL_9:
    v11 = (unsigned int)v8;
LABEL_29:
    WPP_SF_d(v9[2], v10, WPP_f4dfe53786183352449e3e96734e584d_Traceguids, v11);
    goto LABEL_30;
  }
  v8 = StringCchCopyW(pszPath, 0x104u, a2);
  CCHMaxFromPath = v8;
  if ( v8 < 0 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return CCHMaxFromPath;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_31;
    v10 = 20;
    goto LABEL_9;
  }
  PathStripPathW(pszPath);
  v8 = StringCchLengthW(pszPath, 0x104u, &v16);
  CCHMaxFromPath = v8;
  if ( v8 < 0 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return CCHMaxFromPath;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_31;
    v10 = 21;
    goto LABEL_9;
  }
  if ( !v16 )
    PathAddBackslashW(v18);
  if ( !PathAppendW(v18, pszPath) )
  {
    CCHMaxFromPath = -2147467259;
    goto LABEL_26;
  }
  CCHMaxFromPath = GetCCHMaxFromPath(v18, &v14, v7);
  if ( (CCHMaxFromPath & 0x80000000) != 0 )
  {
LABEL_26:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return CCHMaxFromPath;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_31;
    v10 = 22;
    v11 = CCHMaxFromPath;
    goto LABEL_29;
  }
  v12 = 128;
  if ( v14 < 0x80 )
    v12 = v14;
  *a3 = v12;
  return CCHMaxFromPath;
}

```

## disassembly

```asm
0x180039220  mov     [rsp-8+arg_18], rbx
0x180039225  push    rbp
0x180039226  push    rsi
0x180039227  push    rdi
0x180039228  push    r13
0x18003922a  push    r14
0x18003922c  lea     rbp, [rsp-370h]
0x180039234  sub     rsp, 470h
0x18003923b  mov     rax, cs:__security_cookie
0x180039242  xor     rax, rsp
0x180039245  mov     [rbp+390h+var_30], rax
0x18003924c  mov     rdi, r8
0x18003924f  mov     r14, rdx
0x180039252  mov     rbx, rcx
0x180039255  mov     esi, 208h
0x18003925a  mov     r8d, esi; Size
0x18003925d  lea     rcx, [rsp+490h+pszPath]; void *
0x180039262  xor     edx, edx; Val
0x180039264  call    memset_0
0x180039269  mov     r8d, esi; Size
0x18003926c  lea     rcx, [rbp+390h+var_240]; void *
0x180039273  xor     edx, edx; Val
0x180039275  call    memset_0
0x18003927a  mov     [rsp+490h+var_460], 0
0x180039282  lea     r13, WPP_GLOBAL_Control
0x180039289  mov     [rsp+490h+var_458], 0
0x180039292  test    r14, r14
0x180039295  jnz     short loc_1800392A1
0x180039297  mov     ebx, 80070057h
0x18003929c  jmp     loc_180039432
0x1800392a1  test    rdi, rdi
0x1800392a4  jnz     short loc_1800392B0
0x1800392a6  mov     ebx, 80004003h
0x1800392ab  jmp     loc_180039432
0x1800392b0  mov     edx, 2; dwMask
0x1800392b5  mov     dword ptr [rdi], 0
0x1800392bb  lea     rcx, [rsp+490h+psfs]; psfs
0x1800392c0  mov     dword ptr [rsp+490h+psfs.fShowAllObjects], 0
0x1800392c8  call    cs:__imp_SHGetSettings
0x1800392ce  mov     esi, dword ptr [rsp+490h+psfs.fShowAllObjects]
0x1800392d2  lea     r8, [rbp+390h+var_240]
0x1800392d9  mov     rcx, [rbx+20h]; pidl
0x1800392dd  and     esi, 2
0x1800392e0  mov     r9d, 104h
0x1800392e6  shr     esi, 1
0x1800392e8  mov     edx, 0C000h
0x1800392ed  mov     [rsp+490h+var_470], 0; __int64
0x1800392f6  call    SHGetNameAndFlagsW
0x1800392fb  mov     ebx, eax
0x1800392fd  test    eax, eax
0x1800392ff  jns     short loc_180039328
0x180039301  mov     rcx, cs:WPP_GLOBAL_Control
0x180039308  cmp     rcx, r13
0x18003930b  jz      loc_18003945C
0x180039311  test    byte ptr [rcx+1Ch], 2
0x180039315  jz      loc_180039439
0x18003931b  mov     edx, 13h
0x180039320  mov     r9d, eax
0x180039323  jmp     loc_180039422
0x180039328  mov     r8, r14; unsigned __int16 *
0x18003932b  lea     rcx, [rsp+490h+pszPath]; unsigned __int16 *
0x180039330  mov     r14d, 104h
0x180039336  mov     edx, r14d; unsigned __int64
0x180039339  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003933e  mov     ebx, eax
0x180039340  test    eax, eax
0x180039342  jns     short loc_180039365
0x180039344  mov     rcx, cs:WPP_GLOBAL_Control
0x18003934b  cmp     rcx, r13
0x18003934e  jz      loc_18003945C
0x180039354  test    byte ptr [rcx+1Ch], 2
0x180039358  jz      loc_180039439
0x18003935e  mov     edx, 14h
0x180039363  jmp     short loc_180039320
0x180039365  lea     rcx, [rsp+490h+pszPath]; pszPath
0x18003936a  call    cs:__imp_PathStripPathW
0x180039370  lea     r8, [rsp+490h+var_458]; unsigned __int64 *
0x180039375  mov     rdx, r14; unsigned __int64
0x180039378  lea     rcx, [rsp+490h+pszPath]; unsigned __int16 *
0x18003937d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180039382  mov     ebx, eax
0x180039384  test    eax, eax
0x180039386  jns     short loc_1800393AC
0x180039388  mov     rcx, cs:WPP_GLOBAL_Control
0x18003938f  cmp     rcx, r13
0x180039392  jz      loc_18003945C
0x180039398  test    byte ptr [rcx+1Ch], 2
0x18003939c  jz      loc_180039439
0x1800393a2  mov     edx, 15h
0x1800393a7  jmp     loc_180039320
0x1800393ac  cmp     [rsp+490h+var_458], 0
0x1800393b2  jnz     short loc_1800393C1
0x1800393b4  lea     rcx, [rbp+390h+var_240]; pszPath
0x1800393bb  call    cs:__imp_PathAddBackslashW
0x1800393c1  lea     rdx, [rsp+490h+pszPath]; pszMore
0x1800393c6  lea     rcx, [rbp+390h+var_240]; pszPath
0x1800393cd  call    cs:__imp_PathAppendW
0x1800393d3  test    eax, eax
0x1800393d5  jz      short loc_180039403
0x1800393d7  mov     r8d, esi; int
0x1800393da  lea     rdx, [rsp+490h+var_460]; unsigned int *
0x1800393df  lea     rcx, [rbp+390h+var_240]; unsigned __int16 *
0x1800393e6  call    ?GetCCHMaxFromPath@@YAJPEBGPEAIH@Z; GetCCHMaxFromPath(ushort const *,uint *,int)
0x1800393eb  mov     ebx, eax
0x1800393ed  test    eax, eax
0x1800393ef  js      short loc_180039408
0x1800393f1  mov     eax, 80h
0x1800393f6  cmp     [rsp+490h+var_460], eax
0x1800393fa  cmovb   eax, [rsp+490h+var_460]
0x1800393ff  mov     [rdi], eax
0x180039401  jmp     short loc_18003945C
0x180039403  mov     ebx, 80004005h
0x180039408  mov     rcx, cs:WPP_GLOBAL_Control
0x18003940f  cmp     rcx, r13
0x180039412  jz      short loc_18003945C
0x180039414  test    byte ptr [rcx+1Ch], 2
0x180039418  jz      short loc_180039439
0x18003941a  mov     edx, 16h
0x18003941f  mov     r9d, ebx
0x180039422  mov     rcx, [rcx+10h]
0x180039426  lea     r8, WPP_f4dfe53786183352449e3e96734e584d_Traceguids
0x18003942d  call    WPP_SF_d
0x180039432  mov     rcx, cs:WPP_GLOBAL_Control
0x180039439  cmp     rcx, r13
0x18003943c  jz      short loc_18003945C
0x18003943e  test    byte ptr [rcx+1Ch], 2
0x180039442  jz      short loc_18003945C
0x180039444  mov     rcx, [rcx+10h]
0x180039448  lea     r8, WPP_f4dfe53786183352449e3e96734e584d_Traceguids
0x18003944f  mov     edx, 17h
0x180039454  mov     r9d, ebx
0x180039457  call    WPP_SF_d
0x18003945c  mov     eax, ebx
0x18003945e  mov     rcx, [rbp+390h+var_30]
0x180039465  xor     rcx, rsp; StackCookie
0x180039468  call    __security_check_cookie
0x18003946d  mov     rbx, [rsp+490h+arg_18]
0x180039475  add     rsp, 470h
0x18003947c  pop     r14
0x18003947e  pop     r13
0x180039480  pop     rdi
0x180039481  pop     rsi
0x180039482  pop     rbp
0x180039483  retn
```
