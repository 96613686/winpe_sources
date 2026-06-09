# CWebCrawler::ParseRobotsTxt(ushort const *,CWCStringList * *)

- ea: `0x1800215dc`
- end: `0x180021938`
- name: `?ParseRobotsTxt@CWebCrawler@@IEAAJPEBGPEAPEAVCWCStringList@@@Z`
- size: `860`
- prototype: `__int64 __fastcall(CWebCrawler *__hidden this, const unsigned __int16 *, struct CWCStringList **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180020b50`

## callees

- `0x18001ba08`
- `0x18002037c`
- `0x1800215dc`
- `0x18002924e`
- `0x180029280`
- `0x180029310`
- `0x18002a010`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x180021707`
- `KERNEL32!lstrcmpiA` at `0x18002173a`
- `KERNEL32!lstrcmpiA` at `0x1800217b0`
- `KERNEL32!lstrcmpiA` at `0x1800217c8`
- `KERNEL32!lstrcmpiA` at `0x1800217ed`
- `KERNEL32!lstrcmpiA` at `0x180021832`
- `KERNEL32!lstrcmpiA` at `0x18002184a`
- `KERNEL32!lstrcmpiA` at `0x180021862`
- `KERNEL32!lstrcmpiA` at `0x180021707`
- `KERNEL32!lstrcmpiA` at `0x18002173a`
- `KERNEL32!lstrcmpiA` at `0x1800217b0`
- `KERNEL32!lstrcmpiA` at `0x1800217c8`
- `KERNEL32!lstrcmpiA` at `0x1800217ed`
- `KERNEL32!lstrcmpiA` at `0x180021832`
- `KERNEL32!lstrcmpiA` at `0x18002184a`
- `KERNEL32!lstrcmpiA` at `0x180021862`
- `SHLWAPI!UrlCombineW` at `0x1800218a3`
- `SHLWAPI!UrlCombineW` at `0x1800218a3`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180021881`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180021881`

## string_xrefs

- `0x180021730`: `MSIECrawler`
- `0x1800216fd`: `User-Agent:`
- `0x1800217a6`: `User-Agent:`
- `0x180021828`: `User-Agent:`

## pseudocode

```c
__int64 __fastcall CWebCrawler::ParseRobotsTxt(
        CWebCrawler *this,
        const unsigned __int16 *a2,
        struct CWCStringList **a3)
{
  __int64 v5; // rbx
  unsigned int v6; // edi
  __int64 v7; // r14
  int v8; // esi
  int *v9; // r8
  const CHAR *Token; // rax
  char *v11; // rax
  _QWORD *v12; // rax
  CWCDwordStringList *v13; // rbx
  int *v14; // r8
  int v15; // r15d
  unsigned __int64 v16; // r14
  const CHAR *v17; // rax
  const CHAR *v18; // rsi
  const CHAR *v19; // rax
  const CHAR *v20; // rsi
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcchCombined[3]; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v24[16]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v25; // [rsp+50h] [rbp-B0h]
  int v26; // [rsp+54h] [rbp-ACh]
  WCHAR pwszDst[256]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszCombined[2088]; // [rsp+290h] [rbp+190h] BYREF
  char v29[8192]; // [rsp+12E0h] [rbp+11E0h] BYREF

  *a3 = 0;
  v5 = *(_QWORD *)(*((_QWORD *)this + 43) + 176LL);
  if ( !v5 )
    return (unsigned int)-2147467259;
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 8LL))(*(_QWORD *)(*((_QWORD *)this + 43) + 176LL));
  memset_0(v24, 0, 0x50u);
  (*(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v5 + 96LL))(v5, v24, 1);
  v6 = -2147467259;
  if ( v26 || (v7 = v25, v25 >= 0x2000) )
  {
    v29[0] = 0;
    v8 = -2147467259;
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, _QWORD))(*(_QWORD *)v5 + 24LL))(v5, v29, v25, 0);
    v29[v7] = 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v8 < 0 )
    return (unsigned int)v8;
  v22 = 0;
  pcchCombined[0] = 0;
  while ( 1 )
  {
    Token = GetToken(v29, &v22, v9);
    if ( !Token )
      return v6;
    if ( !lstrcmpiA(Token, "User-Agent:") )
    {
      v11 = GetToken(v29, &v22, v9);
      if ( !v11 )
        return v6;
      if ( *v11 == 42 || !lstrcmpiA(v11, "MSIECrawler") )
        break;
    }
  }
  v12 = operator new(0x438u);
  v13 = (CWCDwordStringList *)v12;
  if ( !v12 )
    return v6;
  v12[1] = 0;
  *((_DWORD *)v12 + 4) = 0;
  v12[4] = 0;
  v12[3] = 0;
  v12[5] = 0;
  memset_0(v12 + 6, 0, 0x3F8u);
  *((_QWORD *)v13 + 134) = 0;
  *(_QWORD *)v13 = &CWCDwordStringList::`vftable';
  CWCDwordStringList::Init(v13, 2048);
  while ( 1 )
  {
    v19 = GetToken(v29, &v22, v14);
    v20 = v19;
    if ( !v19 || !lstrcmpiA(v19, "User-Agent:") )
      break;
    v15 = lstrcmpiA(v20, "Allow:");
    v16 = v15 != 0 ? 0 : 0x80000000uLL;
    if ( lstrcmpiA(v20, "Disallow:") )
    {
      if ( !v15 )
        goto LABEL_21;
    }
    else
    {
      v16 = 0x40000000;
LABEL_21:
      v17 = GetToken(v29, &v22, v14);
      v18 = v17;
      if ( !v17 || !lstrcmpiA(v17, "User-Agent:") || !lstrcmpiA(v18, "Allow:") || !lstrcmpiA(v18, "Disallow:") )
        break;
      pcchCombined[0] = 2084;
      if ( SHAnsiToUnicode(v18, pwszDst, 256) )
      {
        if ( UrlCombineW(a2, pwszDst, pszCombined, pcchCombined, 0) >= 0 )
          (*(void (__fastcall **)(CWCDwordStringList *, WCHAR *, unsigned __int64, _QWORD))(*(_QWORD *)v13 + 16LL))(
            v13,
            pszCombined,
            v16,
            0);
      }
    }
  }
  if ( *((int *)v13 + 3) > 0 )
  {
    *a3 = v13;
    return 0;
  }
  (**(void (__fastcall ***)(CWCDwordStringList *, __int64))v13)(v13, 1);
  return v6;
}

```

## disassembly

```asm
0x1800215dc  mov     [rsp-8+arg_18], rbx
0x1800215e1  push    rbp
0x1800215e2  push    rsi
0x1800215e3  push    rdi
0x1800215e4  push    r12
0x1800215e6  push    r13
0x1800215e8  push    r14
0x1800215ea  push    r15
0x1800215ec  lea     rbp, [rsp-31F0h]
0x1800215f4  mov     eax, 32F0h
0x1800215f9  call    _alloca_probe
0x1800215fe  sub     rsp, rax
0x180021601  mov     rax, cs:__security_cookie
0x180021608  xor     rax, rsp
0x18002160b  mov     [rbp+3220h+var_40], rax
0x180021612  xor     r15d, r15d
0x180021615  mov     r12, r8
0x180021618  mov     [r8], r15
0x18002161b  mov     r13, rdx
0x18002161e  mov     rax, [rcx+158h]
0x180021625  mov     rbx, [rax+0B0h]
0x18002162c  test    rbx, rbx
0x18002162f  jnz     short loc_18002163B
0x180021631  mov     edi, 80004005h
0x180021636  jmp     loc_18002190C
0x18002163b  mov     rax, [rbx]
0x18002163e  mov     rcx, rbx
0x180021641  mov     rax, [rax+8]
0x180021645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002164a  xor     edx, edx; Val
0x18002164c  lea     rcx, [rsp+3320h+var_32E0]; void *
0x180021651  lea     r8d, [rdx+50h]; Size
0x180021655  call    memset_0
0x18002165a  mov     rax, [rbx]
0x18002165d  lea     rdx, [rsp+3320h+var_32E0]
0x180021662  mov     r8d, 1
0x180021668  mov     rcx, rbx
0x18002166b  mov     rax, [rax+60h]
0x18002166f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021674  mov     edi, 80004005h
0x180021679  cmp     [rsp+3320h+var_32CC], r15d
0x18002167e  jnz     short loc_1800216B6
0x180021680  mov     r14d, [rsp+3320h+var_32D0]
0x180021685  cmp     r14d, 2000h
0x18002168c  jnb     short loc_1800216B6
0x18002168e  mov     rax, [rbx]
0x180021691  lea     rdx, [rbp+3220h+var_2040]
0x180021698  xor     r9d, r9d
0x18002169b  mov     r8d, r14d
0x18002169e  mov     rcx, rbx
0x1800216a1  mov     rax, [rax+18h]
0x1800216a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216aa  mov     esi, eax
0x1800216ac  mov     [rbp+r14+3220h+var_2040], r15b
0x1800216b4  jmp     short loc_1800216BF
0x1800216b6  mov     [rbp+3220h+var_2040], r15b
0x1800216bd  mov     esi, edi
0x1800216bf  mov     rax, [rbx]
0x1800216c2  mov     rcx, rbx
0x1800216c5  mov     rax, [rax+10h]
0x1800216c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216ce  test    esi, esi
0x1800216d0  jns     short loc_1800216D9
0x1800216d2  mov     edi, esi
0x1800216d4  jmp     loc_18002190C
0x1800216d9  mov     [rsp+3320h+var_32F0], r15d
0x1800216de  mov     [rsp+3320h+pcchCombined], r15d
0x1800216e3  lea     rdx, [rsp+3320h+var_32F0]; int *
0x1800216e8  lea     rcx, [rbp+3220h+var_2040]; char *
0x1800216ef  call    ?GetToken@@YAPEADPEADPEAH1@Z; GetToken(char *,int *,int *)
0x1800216f4  test    rax, rax
0x1800216f7  jz      loc_18002190C
0x1800216fd  lea     rdx, aUserAgent_0; "User-Agent:"
0x180021704  mov     rcx, rax; lpString1
0x180021707  call    cs:__imp_lstrcmpiA
0x18002170d  test    eax, eax
0x18002170f  jnz     short loc_1800216E3
0x180021711  lea     rdx, [rsp+3320h+var_32F0]; int *
0x180021716  lea     rcx, [rbp+3220h+var_2040]; char *
0x18002171d  call    ?GetToken@@YAPEADPEADPEAH1@Z; GetToken(char *,int *,int *)
0x180021722  test    rax, rax
0x180021725  jz      loc_18002190C
0x18002172b  cmp     byte ptr [rax], 2Ah ; '*'
0x18002172e  jz      short loc_180021744
0x180021730  lea     rdx, aMsiecrawler_0; "MSIECrawler"
0x180021737  mov     rcx, rax; lpString1
0x18002173a  call    cs:__imp_lstrcmpiA
0x180021740  test    eax, eax
0x180021742  jnz     short loc_1800216E3
0x180021744  mov     ecx, 438h; dwBytes
0x180021749  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002174e  mov     rbx, rax
0x180021751  test    rax, rax
0x180021754  jz      loc_18002190C
0x18002175a  lea     rcx, [rax+30h]; void *
0x18002175e  mov     [rax+8], r15
0x180021762  xor     edx, edx; Val
0x180021764  mov     [rax+10h], r15d
0x180021768  mov     r8d, 3F8h; Size
0x18002176e  mov     [rax+20h], r15
0x180021772  mov     [rax+18h], r15
0x180021776  mov     [rax+28h], r15
0x18002177a  call    memset_0
0x18002177f  lea     rax, ??_7CWCDwordStringList@@6B@; const CWCDwordStringList::`vftable'
0x180021786  mov     [rbx+430h], r15
0x18002178d  mov     [rbx], rax
0x180021790  mov     edx, 800h
0x180021795  mov     rax, [rax+8]
0x180021799  mov     rcx, rbx
0x18002179c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217a1  jmp     loc_1800218CE
0x1800217a6  lea     rdx, aUserAgent_0; "User-Agent:"
0x1800217ad  mov     rcx, rsi; lpString1
0x1800217b0  call    cs:__imp_lstrcmpiA
0x1800217b6  test    eax, eax
0x1800217b8  jz      loc_1800218EB
0x1800217be  lea     rdx, aAllow; "Allow:"
0x1800217c5  mov     rcx, rsi; lpString1
0x1800217c8  call    cs:__imp_lstrcmpiA
0x1800217ce  mov     ecx, eax
0x1800217d0  lea     rdx, aDisallow; "Disallow:"
0x1800217d7  neg     ecx
0x1800217d9  mov     r15d, eax
0x1800217dc  mov     eax, 80000000h
0x1800217e1  mov     rcx, rsi; lpString1
0x1800217e4  sbb     r14, r14
0x1800217e7  not     r14
0x1800217ea  and     r14, rax
0x1800217ed  call    cs:__imp_lstrcmpiA
0x1800217f3  test    eax, eax
0x1800217f5  jnz     short loc_1800217FF
0x1800217f7  mov     r14d, 40000000h
0x1800217fd  jmp     short loc_180021808
0x1800217ff  test    r15d, r15d
0x180021802  jnz     loc_1800218CB
0x180021808  lea     rdx, [rsp+3320h+var_32F0]; int *
0x18002180d  lea     rcx, [rbp+3220h+var_2040]; char *
0x180021814  call    ?GetToken@@YAPEADPEADPEAH1@Z; GetToken(char *,int *,int *)
0x180021819  xor     r15d, r15d
0x18002181c  mov     rsi, rax
0x18002181f  test    rax, rax
0x180021822  jz      loc_1800218EB
0x180021828  lea     rdx, aUserAgent_0; "User-Agent:"
0x18002182f  mov     rcx, rax; lpString1
0x180021832  call    cs:__imp_lstrcmpiA
0x180021838  test    eax, eax
0x18002183a  jz      loc_1800218EB
0x180021840  lea     rdx, aAllow; "Allow:"
0x180021847  mov     rcx, rsi; lpString1
0x18002184a  call    cs:__imp_lstrcmpiA
0x180021850  test    eax, eax
0x180021852  jz      loc_1800218EB
0x180021858  lea     rdx, aDisallow; "Disallow:"
0x18002185f  mov     rcx, rsi; lpString1
0x180021862  call    cs:__imp_lstrcmpiA
0x180021868  test    eax, eax
0x18002186a  jz      short loc_1800218EB
0x18002186c  mov     r8d, 100h; cwchBuf
0x180021872  mov     [rsp+3320h+pcchCombined], 824h
0x18002187a  lea     rdx, [rbp+3220h+pwszDst]; pwszDst
0x18002187e  mov     rcx, rsi; pszSrc
0x180021881  call    cs:__imp_SHAnsiToUnicode
0x180021887  test    eax, eax
0x180021889  jz      short loc_1800218CE
0x18002188b  lea     r9, [rsp+3320h+pcchCombined]; pcchCombined
0x180021890  mov     [rsp+3320h+dwFlags], r15d; dwFlags
0x180021895  lea     r8, [rbp+3220h+pszCombined]; pszCombined
0x18002189c  mov     rcx, r13; pszBase
0x18002189f  lea     rdx, [rbp+3220h+pwszDst]; pszRelative
0x1800218a3  call    cs:__imp_UrlCombineW
0x1800218a9  test    eax, eax
0x1800218ab  js      short loc_1800218CE
0x1800218ad  mov     rax, [rbx]
0x1800218b0  lea     rdx, [rbp+3220h+pszCombined]
0x1800218b7  xor     r9d, r9d
0x1800218ba  mov     r8, r14
0x1800218bd  mov     rcx, rbx
0x1800218c0  mov     rax, [rax+10h]
0x1800218c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218c9  jmp     short loc_1800218CE
0x1800218cb  xor     r15d, r15d
0x1800218ce  lea     rdx, [rsp+3320h+var_32F0]; int *
0x1800218d3  lea     rcx, [rbp+3220h+var_2040]; char *
0x1800218da  call    ?GetToken@@YAPEADPEADPEAH1@Z; GetToken(char *,int *,int *)
0x1800218df  mov     rsi, rax
0x1800218e2  test    rax, rax
0x1800218e5  jnz     loc_1800217A6
0x1800218eb  cmp     [rbx+0Ch], r15d
0x1800218ef  jle     short loc_1800218F9
0x1800218f1  mov     [r12], rbx
0x1800218f5  xor     eax, eax
0x1800218f7  jmp     short loc_18002190E
0x1800218f9  mov     rax, [rbx]
0x1800218fc  mov     edx, 1
0x180021901  mov     rcx, rbx
0x180021904  mov     rax, [rax]
0x180021907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002190c  mov     eax, edi
0x18002190e  mov     rcx, [rbp+3220h+var_40]
0x180021915  xor     rcx, rsp; StackCookie
0x180021918  call    __security_check_cookie
0x18002191d  mov     rbx, [rsp+3320h+arg_18]
0x180021925  add     rsp, 32F0h
0x18002192c  pop     r15
0x18002192e  pop     r14
0x180021930  pop     r13
0x180021932  pop     r12
0x180021934  pop     rdi
0x180021935  pop     rsi
0x180021936  pop     rbp
0x180021937  retn
```
