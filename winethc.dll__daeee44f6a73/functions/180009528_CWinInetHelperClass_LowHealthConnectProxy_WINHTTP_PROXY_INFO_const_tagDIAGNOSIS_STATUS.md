# CWinInetHelperClass::LowHealthConnectProxy(_WINHTTP_PROXY_INFO * const,tagDIAGNOSIS_STATUS *)

- ea: `0x180009528`
- end: `0x18000984f`
- name: `?LowHealthConnectProxy@CWinInetHelperClass@@AEAAJQEAU_WINHTTP_PROXY_INFO@@PEAW4tagDIAGNOSIS_STATUS@@@Z`
- size: `807`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, struct _WINHTTP_PROXY_INFO *const, enum tagDIAGNOSIS_STATUS *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180008ec0`

## callees

- `0x1800048cc`
- `0x180009528`
- `0x18000eb64`
- `0x18000fce8`
- `0x180012d6e`
- `0x180014010`

## string_xrefs

- `0x1800096b2`: `WPAD cache indicates this is a non-proxied network. Skipping proxy auto-detection.`
- `0x1800095ba`: `No proxy is accessible.`
- `0x180009763`: `Direct connection failed. The proxy auto-detection thread timed out.`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::LowHealthConnectProxy(
        CWinInetHelperClass *this,
        struct _WINHTTP_PROXY_INFO *const a2,
        enum tagDIAGNOSIS_STATUS *a3)
{
  const unsigned __int16 *v6; // rcx
  unsigned int FirstProxy; // r14d
  __int64 v8; // rcx
  __int64 v9; // rax
  _DWORD *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  const wchar_t *v13; // rdx
  __int64 v14; // rcx
  char *v15; // rax
  unsigned int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rbx
  const wchar_t *v21; // [rsp+30h] [rbp-59h] BYREF
  int v22; // [rsp+38h] [rbp-51h]
  int v23; // [rsp+40h] [rbp-49h]
  __int64 v24; // [rsp+F8h] [rbp+6Fh] BYREF
  int v25; // [rsp+108h] [rbp+7Fh] BYREF

  memset_0(&v21, 0, 0x90u);
  v6 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
  if ( v6 && *((_DWORD *)this + 790) )
  {
    FirstProxy = GetFirstProxy(v6, (struct sockaddr_storage *)((char *)this + 3024), (int *)this + 788);
    if ( (FirstProxy & 0x80000000) == 0 )
    {
      if ( *((_DWORD *)this + 788) )
      {
        if ( *a3 == DS_CONFIRMED && *((_DWORD *)this + 755) && *((_DWORD *)this + 1214) )
          *a3 = DS_INDETERMINATE;
      }
      else
      {
        *a3 = DS_CONFIRMED;
        v8 = *((_QWORD *)this + 602);
        if ( v8 )
          (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 24LL))(
            v8,
            2,
            0,
            L"WinInetHelperClass",
            L"No proxy is accessible.");
      }
    }
    return FirstProxy;
  }
  FirstProxy = 0;
  if ( *((_DWORD *)this + 1214) )
    return FirstProxy;
  if ( *a3 == DS_REJECTED )
    return FirstProxy;
  if ( *a3 == DS_PASSTHROUGH )
    return FirstProxy;
  if ( *((_DWORD *)this + 791) )
    return FirstProxy;
  v9 = *((_QWORD *)this + 639);
  if ( v9 )
  {
    if ( *(_DWORD *)(v9 + 4) != 1 )
      return FirstProxy;
  }
  if ( *((_DWORD *)this + 789) )
    return FirstProxy;
  v10 = (_DWORD *)((char *)this + 5108);
  if ( this != (CWinInetHelperClass *)-5108LL )
    *v10 = 2;
  if ( *v10 )
  {
    if ( *v10 == 1 )
      return FirstProxy;
    v14 = 32;
    v15 = (char *)this + 4920;
    do
    {
      *v15++ = 0;
      --v14;
    }
    while ( v14 );
    *((_DWORD *)this + 1230) = 1;
    *((_DWORD *)this + 1231) = 3;
    *((_DWORD *)this + 1237) = 1;
    LODWORD(v24) = 0;
    v25 = 0;
    FirstProxy = CWinInetHelperClass::ExecuteProxyAutodetectionThread(this, 1, (int *)&v24, &v25, 0);
    if ( (FirstProxy & 0x80000000) != 0 )
      return FirstProxy;
    v12 = *((_QWORD *)this + 602);
    if ( !v12 )
      return FirstProxy;
    v16 = v24;
    if ( (int)v24 >= 0 )
    {
      v17 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
      v18 = *((_QWORD *)this + 613);
      v24 = v17 + 24;
      if ( v18 )
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v24,
          L"Direct connection failed. Auto-detected proxy string: '%s'.");
      else
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v24,
          L"Direct connection failed. No proxy auto-detected.");
    }
    else
    {
      if ( (_DWORD)v24 == -2147024638 )
      {
        v13 = L"Direct connection failed. The proxy auto-detection thread timed out.";
        goto LABEL_25;
      }
      v24 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v24,
        L"Auto proxy detection failed with error hr=0x%x.",
        v16);
    }
    v19 = v24;
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 602) + 24LL))(
      *((_QWORD *)this + 602),
      2,
      0,
      L"WinInetHelperClass",
      v24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v19 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v19 - 24) + 8LL))(*(_QWORD *)(v19 - 24));
  }
  else
  {
    v11 = *((_QWORD *)this + 603);
    *((_DWORD *)this + 793) = 0;
    if ( v11 )
    {
      v22 = 1;
      v21 = L"PossibleProxiedScenario";
      v23 = 0;
      (*(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v11 + 40LL))(v11, &v21);
    }
    v12 = *((_QWORD *)this + 602);
    if ( v12 )
    {
      v13 = L"WPAD cache indicates this is a non-proxied network. Skipping proxy auto-detection.";
LABEL_25:
      (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v12 + 24LL))(
        v12,
        2,
        0,
        L"WinInetHelperClass",
        v13);
    }
  }
  return FirstProxy;
}

```

## disassembly

```asm
0x180009528  mov     [rsp-8+arg_0], rbx
0x18000952d  push    rbp
0x18000952e  push    rsi
0x18000952f  push    rdi
0x180009530  push    r14
0x180009532  push    r15
0x180009534  lea     rbp, [rsp-37h]
0x180009539  sub     rsp, 0C0h
0x180009540  mov     rsi, r8
0x180009543  mov     rbx, rdx
0x180009546  mov     rdi, rcx
0x180009549  xor     edx, edx; Val
0x18000954b  mov     r8d, 90h; Size
0x180009551  lea     rcx, [rbp+57h+var_B0]; void *
0x180009555  call    memset_0
0x18000955a  mov     rcx, [rbx+8]; unsigned __int16 *
0x18000955e  xor     r15d, r15d
0x180009561  test    rcx, rcx
0x180009564  jz      loc_1800095FD
0x18000956a  cmp     [rdi+0C58h], r15d
0x180009571  jz      loc_1800095FD
0x180009577  lea     rbx, [rdi+0C50h]
0x18000957e  mov     r8, rbx; int *
0x180009581  lea     rdx, [rdi+0BD0h]; struct sockaddr_storage *
0x180009588  call    ?GetFirstProxy@@YAJQEBGPEAUsockaddr_storage@@PEAH@Z; GetFirstProxy(ushort const * const,sockaddr_storage *,int *)
0x18000958d  mov     r14d, eax
0x180009590  test    eax, eax
0x180009592  js      loc_180009834
0x180009598  cmp     [rbx], r15d
0x18000959b  jnz     short loc_1800095CF
0x18000959d  mov     dword ptr [rsi], 1
0x1800095a3  mov     rcx, [rdi+12D0h]
0x1800095aa  test    rcx, rcx
0x1800095ad  jz      loc_180009834
0x1800095b3  mov     rdx, [rcx]
0x1800095b6  mov     rax, [rdx+18h]
0x1800095ba  lea     rdx, aNoProxyIsAcces; "No proxy is accessible."
0x1800095c1  mov     [rsp+0E0h+var_C0], rdx
0x1800095c6  lea     edx, [r15+2]
0x1800095ca  jmp     loc_1800096C7
0x1800095cf  cmp     dword ptr [rsi], 1
0x1800095d2  jnz     loc_180009834
0x1800095d8  cmp     [rdi+0BCCh], r15d
0x1800095df  jz      loc_180009834
0x1800095e5  cmp     [rdi+12F8h], r15d
0x1800095ec  jz      loc_180009834
0x1800095f2  mov     dword ptr [rsi], 3
0x1800095f8  jmp     loc_180009834
0x1800095fd  mov     r14d, r15d
0x180009600  cmp     [rdi+12F8h], r15d
0x180009607  jnz     loc_180009834
0x18000960d  mov     eax, [rsi]
0x18000960f  mov     esi, 2
0x180009614  cmp     eax, esi
0x180009616  jz      loc_180009834
0x18000961c  cmp     eax, 5
0x18000961f  jz      loc_180009834
0x180009625  cmp     [rdi+0C5Ch], r15d
0x18000962c  jnz     loc_180009834
0x180009632  mov     rax, [rdi+13F8h]
0x180009639  test    rax, rax
0x18000963c  jz      short loc_180009648
0x18000963e  cmp     dword ptr [rax+4], 1
0x180009642  jnz     loc_180009834
0x180009648  cmp     [rdi+0C54h], r15d
0x18000964f  jnz     loc_180009834
0x180009655  lea     rax, [rdi+13F4h]
0x18000965c  test    rax, rax
0x18000965f  jz      short loc_180009663
0x180009661  mov     [rax], esi
0x180009663  mov     ecx, [rax]
0x180009665  test    ecx, ecx
0x180009667  jnz     short loc_1800096DB
0x180009669  mov     rcx, [rdi+12D8h]
0x180009670  mov     [rdi+0C64h], r15d
0x180009677  test    rcx, rcx
0x18000967a  jz      short loc_1800096A2
0x18000967c  lea     rax, aPossibleproxie; "PossibleProxiedScenario"
0x180009683  mov     [rbp+57h+var_A8], 1
0x18000968a  mov     [rbp+57h+var_B0], rax
0x18000968e  lea     rdx, [rbp+57h+var_B0]
0x180009692  mov     [rbp+57h+var_A0], r15d
0x180009696  mov     rax, [rcx]
0x180009699  mov     rax, [rax+28h]
0x18000969d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a2  mov     rcx, [rdi+12D0h]
0x1800096a9  test    rcx, rcx
0x1800096ac  jz      loc_180009834
0x1800096b2  lea     rdx, aWpadCacheIndic; "WPAD cache indicates this is a non-prox"...
0x1800096b9  mov     rax, [rcx]
0x1800096bc  mov     [rsp+0E0h+var_C0], rdx
0x1800096c1  mov     edx, esi
0x1800096c3  mov     rax, [rax+18h]
0x1800096c7  xor     r8d, r8d
0x1800096ca  lea     r9, aWininethelperc; "WinInetHelperClass"
0x1800096d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096d6  jmp     loc_180009834
0x1800096db  cmp     ecx, 1
0x1800096de  jz      loc_180009834
0x1800096e4  lea     rdx, [rdi+1338h]
0x1800096eb  mov     ecx, 20h ; ' '
0x1800096f0  mov     rax, rdx
0x1800096f3  mov     [rax], r15b
0x1800096f6  inc     rax
0x1800096f9  sub     rcx, 1
0x1800096fd  jnz     short loc_1800096F3
0x1800096ff  mov     dword ptr [rdx], 1
0x180009705  lea     r9, [rbp+57h+arg_18]; int *
0x180009709  lea     edx, [rcx+1]; int
0x18000970c  mov     dword ptr [rdi+133Ch], 3
0x180009716  mov     rcx, rdi; this
0x180009719  mov     dword ptr [rdi+1354h], 1
0x180009723  lea     r8, [rbp+57h+arg_8]; int *
0x180009727  mov     dword ptr [rbp+57h+arg_8], r15d
0x18000972b  mov     [rbp+57h+arg_18], r15d
0x18000972f  mov     [rsp+0E0h+var_C0], r15; enum ThreadExternalHostResolveResult *
0x180009734  call    ?ExecuteProxyAutodetectionThread@CWinInetHelperClass@@AEAAJHPEAJPEAHPEAW4ThreadExternalHostResolveResult@@@Z; CWinInetHelperClass::ExecuteProxyAutodetectionThread(int,long *,int *,ThreadExternalHostResolveResult *)
0x180009739  mov     r14d, eax
0x18000973c  test    eax, eax
0x18000973e  js      loc_180009834
0x180009744  mov     rcx, [rdi+12D0h]
0x18000974b  test    rcx, rcx
0x18000974e  jz      loc_180009834
0x180009754  mov     ebx, dword ptr [rbp+57h+arg_8]
0x180009757  test    ebx, ebx
0x180009759  jns     short loc_1800097A3
0x18000975b  cmp     ebx, 80070102h
0x180009761  jnz     short loc_18000976F
0x180009763  lea     rdx, aDirectConnecti; "Direct connection failed. The proxy aut"...
0x18000976a  jmp     loc_1800096B9
0x18000976f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009776  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000977d  mov     rax, [rax+18h]
0x180009781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009786  add     rax, 18h
0x18000978a  lea     rdx, aAutoProxyDetec_1; "Auto proxy detection failed with error "...
0x180009791  mov     r8d, ebx
0x180009794  mov     [rbp+57h+arg_8], rax
0x180009798  lea     rcx, [rbp+57h+arg_8]
0x18000979c  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800097a1  jmp     short loc_1800097EC
0x1800097a3  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800097aa  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800097b1  mov     rax, [rax+18h]
0x1800097b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097ba  mov     r8, [rdi+1328h]
0x1800097c1  lea     rcx, [rbp+57h+arg_8]
0x1800097c5  add     rax, 18h
0x1800097c9  mov     [rbp+57h+arg_8], rax
0x1800097cd  test    r8, r8
0x1800097d0  jz      short loc_1800097E0
0x1800097d2  lea     rdx, aDirectConnecti_0; "Direct connection failed. Auto-detected"...
0x1800097d9  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800097de  jmp     short loc_1800097EC
0x1800097e0  lea     rdx, aDirectConnecti_1; "Direct connection failed. No proxy auto"...
0x1800097e7  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800097ec  mov     rcx, [rdi+12D0h]
0x1800097f3  lea     r9, aWininethelperc; "WinInetHelperClass"
0x1800097fa  mov     rbx, [rbp+57h+arg_8]
0x1800097fe  xor     r8d, r8d
0x180009801  mov     edx, esi
0x180009803  mov     [rsp+0E0h+var_C0], rbx
0x180009808  mov     rax, [rcx]
0x18000980b  mov     rax, [rax+18h]
0x18000980f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009814  lea     rdx, [rbx-18h]
0x180009818  or      eax, 0FFFFFFFFh
0x18000981b  lock xadd [rdx+10h], eax
0x180009820  sub     eax, 1
0x180009823  jg      short loc_180009834
0x180009825  mov     rcx, [rdx]
0x180009828  mov     rax, [rcx]
0x18000982b  mov     rax, [rax+8]
0x18000982f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009834  mov     rbx, [rsp+0E0h+arg_0]
0x18000983c  mov     eax, r14d
0x18000983f  add     rsp, 0C0h
0x180009846  pop     r15
0x180009848  pop     r14
0x18000984a  pop     rdi
0x18000984b  pop     rsi
0x18000984c  pop     rbp
0x18000984d  retn
```
