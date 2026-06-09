# CWinInetHelperClass::LowHealth(ushort const *,ushort * *,long *,tagDIAGNOSIS_STATUS *)

- ea: `0x180008ec0`
- end: `0x180009295`
- name: `?LowHealth@CWinInetHelperClass@@UEAAJPEBGPEAPEAGPEAJPEAW4tagDIAGNOSIS_STATUS@@@Z`
- size: `981`
- prototype: `__int64 __usercall@<rax>(CWinInetHelperClass *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int16 **@<r8>, int *@<r9>, enum tagDIAGNOSIS_STATUS *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800048cc`
- `0x180004ef8`
- `0x180008ec0`
- `0x18000929c`
- `0x180009528`
- `0x180009e04`
- `0x18000a22c`
- `0x18000dd54`
- `0x18000e7d0`
- `0x180010324`
- `0x1800107dc`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009035`
- `KERNEL32!GetLastError` at `0x180009035`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180009025`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180009025`

## string_xrefs

- `0x18000901e`: `%systemroot%\system32\svchost.exe`
- `0x18000922f`: `NLA reports that we are behind a hotspot, will skip connection attempt and go straight to hotspot diagnosis.`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::LowHealth(
        CWinInetHelperClass *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        int *a4,
        enum tagDIAGNOSIS_STATUS *a5)
{
  enum tagDIAGNOSIS_STATUS *v5; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  int StringWithAlloc; // eax
  __int128 v12; // xmm0
  __int64 v13; // rcx
  signed int UserProxySetting; // ebx
  __int64 v15; // rcx
  _WORD *v16; // rax
  __int64 v17; // rdx
  _WORD *v18; // rcx
  signed int LastError; // eax
  _DWORD *v20; // r12
  _DWORD *v21; // r15
  _QWORD *v22; // rdx
  int AvailableConnectivity; // ebx
  const wchar_t *v24; // r9
  const wchar_t *v25; // r8
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int128 v31; // [rsp+30h] [rbp-28h] BYREF
  __int64 v32; // [rsp+40h] [rbp-18h]
  __int64 v33; // [rsp+A0h] [rbp+48h] BYREF

  v5 = a5;
  v32 = 0;
  *a5 = DS_REJECTED;
  LODWORD(a5) = 0;
  v31 = 0;
  _RunAsImpersonatedUser(L"ForceProxyDetectionOnNextRun");
  if ( !*((_DWORD *)this + 1274) )
  {
    v10 = *((_QWORD *)this + 602);
    if ( v10 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v10 + 24LL))(
        v10,
        2,
        0,
        L"WinInetHelperClass",
        L"Invalid URL passed in!");
    *v5 = DS_CONFIRMED;
    StringWithAlloc = AssembleStringsWithAlloc(a3, v9, (unsigned __int16 *)0x207, (unsigned __int16 *)this + 875);
    v12 = RCG_WINET_INVALIDURL;
    goto LABEL_5;
  }
  if ( *((_DWORD *)this + 287) == 3 )
  {
    v13 = *((_QWORD *)this + 602);
    UserProxySetting = 0;
    if ( v13 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v13 + 24LL))(
        v13,
        2,
        0,
        L"WinInetHelperClass",
        L"The URL is a share. Passing through to SMB Helper Class.");
    *v5 = DS_INDETERMINATE;
    goto LABEL_52;
  }
  if ( a2 )
  {
    v15 = 2147483646;
    v16 = (_WORD *)((char *)this + 632);
    v17 = 256;
    do
    {
      if ( !v15 )
        break;
      if ( !*a2 )
        break;
      *v16++ = *a2++;
      --v15;
      --v17;
    }
    while ( v17 );
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
    if ( !v17 )
      *((_WORD *)this + 316) = 0;
  }
  if ( *((_WORD *)this + 1174)
    || ExpandEnvironmentStringsW(L"%systemroot%\\system32\\svchost.exe", (LPWSTR)this + 1174, 0x104u) )
  {
    goto LABEL_24;
  }
  LastError = GetLastError();
  UserProxySetting = LastError;
  if ( LastError > 0 )
    UserProxySetting = (unsigned __int16)LastError | 0x80070000;
  if ( UserProxySetting >= 0 )
  {
LABEL_24:
    v20 = (_DWORD *)((char *)this + 4956);
    v21 = (_DWORD *)((char *)this + 4812);
    AvailableConnectivity = GetAvailableConnectivity((CWinInetHelperClass *)((char *)this + 4812), (int *)this + 1239);
    if ( *((_QWORD *)this + 602) )
    {
      v33 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      if ( AvailableConnectivity < 0 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v33,
          L"NLA connectivity query failed with error 0%x, will assume Internet connectivity.",
          (unsigned int)AvailableConnectivity);
      }
      else
      {
        v24 = L"TRUE";
        if ( !*v20 )
          v24 = L"FALSE";
        if ( *v21 == 2 )
        {
          v25 = L"No";
        }
        else
        {
          v25 = L"Local";
          if ( *v21 != 1 )
            v25 = L"Internet";
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v33,
          L"NLA reported %s connectivity. (Hotspot: %s)",
          v25,
          v24);
      }
      v26 = v33;
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 602) + 24LL))(
        *((_QWORD *)this + 602),
        2,
        0,
        L"WinInetHelperClass",
        v33);
      v22 = (_QWORD *)(v26 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 8LL))(*v22);
    }
    if ( *v21 == 2 )
    {
      v27 = *((_QWORD *)this + 602);
      if ( v27 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v27 + 24LL))(
          v27,
          2,
          0,
          L"WinInetHelperClass",
          L"NLA reported no connectivity available. Going straight to Address Acquisition.");
      *v5 = DS_CONFIRMED;
      StringWithAlloc = AssembleStringsWithAlloc(
                          a3,
                          (__int64)v22,
                          (unsigned __int16 *)0x1FA,
                          (unsigned __int16 *)this + 60);
      v12 = RCG_WINET_NOCONNECTIVITY;
      goto LABEL_5;
    }
    if ( *v20 )
    {
      v28 = *((_QWORD *)this + 602);
      if ( v28 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v28 + 24LL))(
          v28,
          2,
          0,
          L"WinInetHelperClass",
          L"NLA reports that we are behind a hotspot, will skip connection attempt and go straight to hotspot diagnosis.");
      goto LABEL_50;
    }
    UserProxySetting = CWinInetHelperClass::LowHealthGetUserProxySetting(
                         this,
                         (struct _WINHTTP_PROXY_INFO *)&v31,
                         v5,
                         (int *)&a5);
    if ( UserProxySetting >= 0 )
    {
      if ( *((_DWORD *)this + 1275) || (_DWORD)a5 )
      {
        StringWithAlloc = LoadStringWithAlloc(0x208u, (LPVOID *)a3);
        v12 = RCG_WINET_AUTOPROXYFAILURE;
LABEL_5:
        *((_OWORD *)this + 302) = v12;
LABEL_51:
        UserProxySetting = StringWithAlloc;
        goto LABEL_52;
      }
      UserProxySetting = CWinInetHelperClass::LowHealthConnectHost(this, (struct _WINHTTP_PROXY_INFO *const)&v31, v5);
      if ( UserProxySetting >= 0 )
      {
        UserProxySetting = CWinInetHelperClass::LowHealthConnectProxy(this, (struct _WINHTTP_PROXY_INFO *const)&v31, v5);
        if ( UserProxySetting >= 0 )
        {
LABEL_50:
          StringWithAlloc = CWinInetHelperClass::LowHealthSetDescriptionAndRootCause(
                              this,
                              (struct _WINHTTP_PROXY_INFO *const)&v31,
                              v5,
                              a3);
          goto LABEL_51;
        }
      }
    }
  }
LABEL_52:
  v29 = *((_QWORD *)this + 639);
  if ( v29 && *(_DWORD *)(v29 + 4) != 1 )
    FreeProxyInfo((struct _WINHTTP_PROXY_INFO *)&v31);
  return (unsigned int)UserProxySetting;
}

```

## disassembly

```asm
0x180008ec0  push    rbp
0x180008ec2  push    rbx
0x180008ec3  push    rsi
0x180008ec4  push    rdi
0x180008ec5  push    r12
0x180008ec7  push    r13
0x180008ec9  push    r14
0x180008ecb  push    r15
0x180008ecd  mov     rbp, rsp
0x180008ed0  sub     rsp, 58h
0x180008ed4  mov     rsi, [rbp+arg_20]
0x180008ed8  mov     rdi, rcx
0x180008edb  xorps   xmm0, xmm0
0x180008ede  lea     rcx, aForceproxydete_0; "ForceProxyDetectionOnNextRun"
0x180008ee5  xor     eax, eax
0x180008ee7  mov     r15d, 2
0x180008eed  xor     r13d, r13d
0x180008ef0  mov     [rbp+var_18], rax
0x180008ef4  mov     [rsi], r15d
0x180008ef7  mov     r14, r8
0x180008efa  mov     rbx, rdx
0x180008efd  mov     dword ptr [rbp+arg_20], r13d
0x180008f01  movups  [rbp+var_28], xmm0
0x180008f05  call    ?_RunAsImpersonatedUser@@YAJPEBG@Z; _RunAsImpersonatedUser(ushort const *)
0x180008f0a  cmp     [rdi+13E8h], r13d
0x180008f11  jnz     short loc_180008F73
0x180008f13  mov     rcx, [rdi+12D0h]
0x180008f1a  test    rcx, rcx
0x180008f1d  jz      short loc_180008F44
0x180008f1f  mov     rax, [rcx]
0x180008f22  lea     r9, aInvalidUrlPass; "Invalid URL passed in!"
0x180008f29  mov     [rsp+58h+var_38], r9
0x180008f2e  xor     r8d, r8d
0x180008f31  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180008f38  mov     edx, r15d
0x180008f3b  mov     rax, [rax+18h]
0x180008f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f44  lea     r9, [rdi+6D6h]; unsigned __int16 *
0x180008f4b  mov     dword ptr [rsi], 1
0x180008f51  mov     r8d, 207h; unsigned __int16 *
0x180008f57  mov     rcx, r14; unsigned __int16 **
0x180008f5a  call    ?AssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1@Z; AssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *)
0x180008f5f  movups  xmm0, cs:RCG_WINET_INVALIDURL
0x180008f66  movdqu  xmmword ptr [rdi+12E0h], xmm0
0x180008f6e  jmp     loc_180009264
0x180008f73  cmp     dword ptr [rdi+47Ch], 3
0x180008f7a  jnz     short loc_180008FBB
0x180008f7c  mov     rcx, [rdi+12D0h]
0x180008f83  mov     ebx, r13d
0x180008f86  test    rcx, rcx
0x180008f89  jz      short loc_180008FB0
0x180008f8b  mov     rax, [rcx]
0x180008f8e  lea     rdx, aTheUrlIsAShare; "The URL is a share. Passing through to "...
0x180008f95  mov     [rsp+58h+var_38], rdx
0x180008f9a  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180008fa1  xor     r8d, r8d
0x180008fa4  mov     edx, r15d
0x180008fa7  mov     rax, [rax+18h]
0x180008fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fb0  mov     dword ptr [rsi], 3
0x180008fb6  jmp     loc_180009266
0x180008fbb  test    rbx, rbx
0x180008fbe  jz      short loc_18000900B
0x180008fc0  lea     r9, [rdi+278h]
0x180008fc7  mov     ecx, 7FFFFFFEh
0x180008fcc  mov     rax, r9
0x180008fcf  mov     edx, 100h
0x180008fd4  test    rcx, rcx
0x180008fd7  jz      short loc_180008FF6
0x180008fd9  movzx   r8d, word ptr [rbx]
0x180008fdd  test    r8w, r8w
0x180008fe1  jz      short loc_180008FF6
0x180008fe3  mov     [rax], r8w
0x180008fe7  add     rbx, r15
0x180008fea  add     rax, r15
0x180008fed  dec     rcx
0x180008ff0  sub     rdx, 1
0x180008ff4  jnz     short loc_180008FD4
0x180008ff6  test    rdx, rdx
0x180008ff9  lea     rcx, [rax-2]
0x180008ffd  cmovnz  rcx, rax
0x180009001  mov     [rcx], r13w
0x180009005  jnz     short loc_18000900B
0x180009007  mov     [r9], r13w
0x18000900b  lea     rdx, [rdi+92Ch]; lpDst
0x180009012  cmp     [rdx], r13w
0x180009016  jnz     short loc_180009058
0x180009018  mov     r8d, 104h; nSize
0x18000901e  lea     rcx, Src; "%systemroot%\\system32\\svchost.exe"
0x180009025  call    cs:__imp_ExpandEnvironmentStringsW
0x18000902c  nop     dword ptr [rax+rax+00h]
0x180009031  test    eax, eax
0x180009033  jnz     short loc_180009058
0x180009035  call    cs:__imp_GetLastError
0x18000903c  nop     dword ptr [rax+rax+00h]
0x180009041  mov     ebx, eax
0x180009043  test    eax, eax
0x180009045  jle     short loc_180009050
0x180009047  movzx   ebx, ax
0x18000904a  or      ebx, 80070000h
0x180009050  test    ebx, ebx
0x180009052  js      loc_180009266
0x180009058  lea     r12, [rdi+135Ch]
0x18000905f  lea     r15, [rdi+12CCh]
0x180009066  mov     rdx, r12; int *
0x180009069  mov     rcx, r15; enum WHCAvailableConnectivity *
0x18000906c  call    ?GetAvailableConnectivity@@YAJPEAW4WHCAvailableConnectivity@@PEAH@Z; GetAvailableConnectivity(WHCAvailableConnectivity *,int *)
0x180009071  mov     ebx, eax
0x180009073  cmp     [rdi+12D0h], r13
0x18000907a  jz      loc_18000914D
0x180009080  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009087  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000908e  mov     rax, [rax+18h]
0x180009092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009097  add     rax, 18h
0x18000909b  mov     [rbp+arg_0], rax
0x18000909f  test    ebx, ebx
0x1800090a1  js      short loc_1800090F0
0x1800090a3  cmp     [r12], r13d
0x1800090a7  lea     rax, aFalse; "FALSE"
0x1800090ae  lea     r9, aTrue; "TRUE"
0x1800090b5  cmovz   r9, rax
0x1800090b9  cmp     dword ptr [r15], 2
0x1800090bd  jnz     short loc_1800090C8
0x1800090bf  lea     r8, aNo; "No"
0x1800090c6  jmp     short loc_1800090DE
0x1800090c8  cmp     dword ptr [r15], 1
0x1800090cc  lea     r8, aLocal; "Local"
0x1800090d3  lea     rax, aInternet; "Internet"
0x1800090da  cmovnz  r8, rax
0x1800090de  lea     rdx, aNlaReportedSCo; "NLA reported %s connectivity. (Hotspot:"...
0x1800090e5  lea     rcx, [rbp+arg_0]
0x1800090e9  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800090ee  jmp     short loc_180009103
0x1800090f0  mov     r8d, ebx
0x1800090f3  lea     rdx, aNlaConnectivit; "NLA connectivity query failed with erro"...
0x1800090fa  lea     rcx, [rbp+arg_0]
0x1800090fe  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180009103  mov     rcx, [rdi+12D0h]
0x18000910a  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180009111  mov     rbx, [rbp+arg_0]
0x180009115  xor     r8d, r8d
0x180009118  mov     [rsp+58h+var_38], rbx
0x18000911d  mov     rax, [rcx]
0x180009120  lea     edx, [r8+2]
0x180009124  mov     rax, [rax+18h]
0x180009128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000912d  lea     rdx, [rbx-18h]
0x180009131  or      eax, 0FFFFFFFFh
0x180009134  lock xadd [rdx+10h], eax
0x180009139  sub     eax, 1
0x18000913c  jg      short loc_18000914D
0x18000913e  mov     rcx, [rdx]
0x180009141  mov     rax, [rcx]
0x180009144  mov     rax, [rax+8]
0x180009148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000914d  cmp     dword ptr [r15], 2
0x180009151  jnz     short loc_1800091A9
0x180009153  mov     rcx, [rdi+12D0h]
0x18000915a  test    rcx, rcx
0x18000915d  jz      short loc_180009185
0x18000915f  mov     rax, [rcx]
0x180009162  lea     rdx, aNlaReportedNoC; "NLA reported no connectivity available."...
0x180009169  xor     r8d, r8d
0x18000916c  mov     [rsp+58h+var_38], rdx
0x180009171  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180009178  mov     rax, [rax+18h]
0x18000917c  lea     edx, [r8+2]
0x180009180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009185  lea     r9, [rdi+78h]; unsigned __int16 *
0x180009189  mov     dword ptr [rsi], 1
0x18000918f  mov     r8d, 1FAh; unsigned __int16 *
0x180009195  mov     rcx, r14; unsigned __int16 **
0x180009198  call    ?AssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1@Z; AssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *)
0x18000919d  movups  xmm0, cs:RCG_WINET_NOCONNECTIVITY
0x1800091a4  jmp     loc_180008F66
0x1800091a9  cmp     [r12], r13d
0x1800091ad  jnz     short loc_180009220
0x1800091af  lea     r9, [rbp+arg_20]; int *
0x1800091b3  mov     r8, rsi; enum tagDIAGNOSIS_STATUS *
0x1800091b6  lea     rdx, [rbp+var_28]; struct _WINHTTP_PROXY_INFO *
0x1800091ba  mov     rcx, rdi; this
0x1800091bd  call    ?LowHealthGetUserProxySetting@CWinInetHelperClass@@AEAAJPEAU_WINHTTP_PROXY_INFO@@PEAW4tagDIAGNOSIS_STATUS@@PEAH@Z; CWinInetHelperClass::LowHealthGetUserProxySetting(_WINHTTP_PROXY_INFO *,tagDIAGNOSIS_STATUS *,int *)
0x1800091c2  mov     ebx, eax
0x1800091c4  test    eax, eax
0x1800091c6  js      loc_180009266
0x1800091cc  cmp     [rdi+13ECh], r13d
0x1800091d3  jnz     short loc_180009207
0x1800091d5  cmp     dword ptr [rbp+arg_20], r13d
0x1800091d9  jnz     short loc_180009207
0x1800091db  mov     r8, rsi; enum tagDIAGNOSIS_STATUS *
0x1800091de  lea     rdx, [rbp+var_28]; struct _WINHTTP_PROXY_INFO *
0x1800091e2  mov     rcx, rdi; this
0x1800091e5  call    ?LowHealthConnectHost@CWinInetHelperClass@@AEAAJQEAU_WINHTTP_PROXY_INFO@@PEAW4tagDIAGNOSIS_STATUS@@@Z; CWinInetHelperClass::LowHealthConnectHost(_WINHTTP_PROXY_INFO * const,tagDIAGNOSIS_STATUS *)
0x1800091ea  mov     ebx, eax
0x1800091ec  test    eax, eax
0x1800091ee  js      short loc_180009266
0x1800091f0  mov     r8, rsi; enum tagDIAGNOSIS_STATUS *
0x1800091f3  lea     rdx, [rbp+var_28]; struct _WINHTTP_PROXY_INFO *
0x1800091f7  mov     rcx, rdi; this
0x1800091fa  call    ?LowHealthConnectProxy@CWinInetHelperClass@@AEAAJQEAU_WINHTTP_PROXY_INFO@@PEAW4tagDIAGNOSIS_STATUS@@@Z; CWinInetHelperClass::LowHealthConnectProxy(_WINHTTP_PROXY_INFO * const,tagDIAGNOSIS_STATUS *)
0x1800091ff  mov     ebx, eax
0x180009201  test    eax, eax
0x180009203  js      short loc_180009266
0x180009205  jmp     short loc_180009252
0x180009207  mov     rdx, r14; unsigned __int16 **
0x18000920a  mov     ecx, 208h; uID
0x18000920f  call    ?LoadStringWithAlloc@@YAJIPEAPEAGI@Z; LoadStringWithAlloc(uint,ushort * *,uint)
0x180009214  movups  xmm0, cs:RCG_WINET_AUTOPROXYFAILURE
0x18000921b  jmp     loc_180008F66
0x180009220  mov     rcx, [rdi+12D0h]
0x180009227  test    rcx, rcx
0x18000922a  jz      short loc_180009252
0x18000922c  mov     rax, [rcx]
0x18000922f  lea     rdx, aNlaReportsThat; "NLA reports that we are behind a hotspo"...
0x180009236  xor     r8d, r8d
0x180009239  mov     [rsp+58h+var_38], rdx
0x18000923e  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180009245  mov     rax, [rax+18h]
0x180009249  lea     edx, [r8+2]
0x18000924d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009252  mov     r9, r14; unsigned __int16 **
0x180009255  lea     rdx, [rbp+var_28]; struct _WINHTTP_PROXY_INFO *
0x180009259  mov     r8, rsi; enum tagDIAGNOSIS_STATUS *
0x18000925c  mov     rcx, rdi; this
0x18000925f  call    ?LowHealthSetDescriptionAndRootCause@CWinInetHelperClass@@AEAAJQEAU_WINHTTP_PROXY_INFO@@PEAW4tagDIAGNOSIS_STATUS@@PEAPEAG@Z; CWinInetHelperClass::LowHealthSetDescriptionAndRootCause(_WINHTTP_PROXY_INFO * const,tagDIAGNOSIS_STATUS *,ushort * *)
0x180009264  mov     ebx, eax
0x180009266  mov     rax, [rdi+13F8h]
0x18000926d  test    rax, rax
0x180009270  jz      short loc_180009281
0x180009272  cmp     dword ptr [rax+4], 1
0x180009276  jz      short loc_180009281
0x180009278  lea     rcx, [rbp+var_28]; struct _WINHTTP_PROXY_INFO *
0x18000927c  call    ?FreeProxyInfo@@YAXPEAU_WINHTTP_PROXY_INFO@@@Z; FreeProxyInfo(_WINHTTP_PROXY_INFO *)
0x180009281  mov     eax, ebx
0x180009283  add     rsp, 58h
0x180009287  pop     r15
0x180009289  pop     r14
0x18000928b  pop     r13
0x18000928d  pop     r12
0x18000928f  pop     rdi
0x180009290  pop     rsi
0x180009291  pop     rbx
0x180009292  pop     rbp
0x180009293  retn
```
