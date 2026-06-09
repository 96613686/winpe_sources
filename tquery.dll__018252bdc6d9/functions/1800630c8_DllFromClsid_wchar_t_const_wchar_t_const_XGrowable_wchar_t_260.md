# DllFromClsid(wchar_t const *,wchar_t const *,XGrowable<wchar_t,260> &)

- ea: `0x1800630c8`
- end: `0x1800634db`
- name: `?DllFromClsid@@YAXPEB_W0AEAV?$XGrowable@_W$0BAE@@@@Z`
- size: `1043`
- prototype: `LSTATUS __fastcall(wchar_t *, wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180062e38`

## callees

- `0x180038f08`
- `0x18006242c`
- `0x1800630c8`
- `0x180063848`
- `0x1800740f4`
- `0x1800db68c`
- `0x180188d90`
- `0x18018e8cb`
- `0x1801b9afc`
- `0x1801b9c34`
- `0x1801fd540`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800633b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800633b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800634ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800634ab`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18006335a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18006335a`

## string_xrefs

- `0x1800631f0`: `Software\Classes\CLSID\`
- `0x180063256`: `onecoreuap\base\appmodel\Search\common\include\strsafeex.hxx`
- `0x180063286`: `onecoreuap\base\appmodel\Search\common\include\strsafeex.hxx`
- `0x180063339`: `onecoreuap\base\appmodel\Search\common\include\strsafeex.hxx`

## pseudocode

```c
LSTATUS __fastcall DllFromClsid(wchar_t *a1, wchar_t *a2, __int64 a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // esi
  LSTATUS result; // eax
  __int64 v9; // rdx
  wchar_t *v10; // rax
  char v11; // si
  const char *v12; // r9
  __int64 v13; // r8
  __int64 v14; // r14
  __int64 v15; // rcx
  const wchar_t *v16; // r9
  __int64 v17; // rdx
  wchar_t *v18; // rax
  wchar_t v19; // r8
  wchar_t *v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  wchar_t *v23; // rax
  const char *v24; // r9
  __int64 v25; // r8
  const wchar_t *v26; // rcx
  __int64 v27; // rbx
  wchar_t *v28; // rax
  wchar_t *v29; // rcx
  const wchar_t *v30; // rcx
  unsigned int v31; // r9d
  wchar_t *v32; // rdx
  int v33; // eax
  const wchar_t *v34; // rdx
  unsigned int v35; // ecx
  unsigned __int64 v36; // r9
  unsigned int v37; // eax
  unsigned __int64 v38; // r9
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int v42[2]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v44; // [rsp+40h] [rbp-C0h]
  struct CSearchRegistryRedirectHelper *v45; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v46[104]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v6 = 0;
  v42[0] = 0;
  if ( a2 )
  {
    *(_QWORD *)v42 = 0;
    if ( (int)StringCchLengthW(a2, 0x104u, (unsigned __int64 *)v42) < 0 )
    {
      if ( *(_DWORD *)a3 < 2u )
        XGrowable<wchar_t,260>::SetSize(a3, 2);
      **(_WORD **)(a3 + 8) = 0;
      v7 = 0;
    }
    else
    {
      v6 = v42[0] + 1;
      v7 = v42[0] + 1;
    }
    if ( *(_DWORD *)a3 < v7 )
      XGrowable<wchar_t,260>::SetSize(a3, v6);
    return (unsigned int)memcpy_0(*(void **)(a3 + 8), a2, 2LL * v7);
  }
  else
  {
    v46[0] = 0;
    v9 = 100;
    v10 = v46;
    v11 = 1;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v9;
    }
    while ( v9 );
    v12 = v9 == 0 ? (const char *)0x80070057LL : 0LL;
    v13 = (100 - v9) & -(__int64)(v9 != 0);
    v14 = 2147483646;
    if ( v9 )
    {
      v15 = 2147483646;
      v16 = L"Software\\Classes\\CLSID\\";
      v17 = 100 - v13;
      v18 = &v46[v13];
      if ( v13 != 100 )
      {
        do
        {
          if ( !v15 )
            break;
          v19 = *v16;
          if ( !*v16 )
            break;
          ++v16;
          *v18++ = v19;
          --v15;
          --v17;
        }
        while ( v17 );
      }
      v20 = v18 - 1;
      if ( v17 )
        v20 = v18;
      *v20 = 0;
      v12 = v17 == 0 ? (const char *)0x8007007ALL : 0LL;
    }
    if ( (int)v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\strsafeex.hxx",
        v12,
        phkResult);
    v21 = StringCchCatW(v46, 0x64u, a1);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\strsafeex.hxx",
        (const char *)(unsigned int)v21,
        phkResult);
    v22 = 100;
    v23 = v46;
    do
    {
      if ( !*v23 )
        break;
      ++v23;
      --v22;
    }
    while ( v22 );
    v24 = v22 == 0 ? (const char *)0x80070057LL : 0LL;
    v25 = (100 - v22) & -(__int64)(v22 != 0);
    if ( v22 )
    {
      v26 = L"\\InprocServer32";
      v27 = 100 - v25;
      v28 = &v46[v25];
      if ( 100 != v25 )
      {
        do
        {
          if ( !v14 )
            break;
          v22 = *v26;
          if ( !(_WORD)v22 )
            break;
          ++v26;
          *v28++ = v22;
          --v14;
          --v27;
        }
        while ( v27 );
      }
      v29 = v28 - 1;
      if ( v27 )
        v29 = v28;
      *v29 = 0;
      v24 = v27 == 0 ? (const char *)0x8007007ALL : 0LL;
    }
    if ( (int)v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\strsafeex.hxx",
        v24,
        phkResult);
    hKey = 0;
    v44 = 0;
    v45 = 0;
    if ( !(unsigned __int8)RtlIsStateSeparationEnabled(retaddr, v22, v25)
      || !GetSearchRegistryRedirect(v30, &v45)
      || CSearchRegistryRedirectHelper::MapRegistryKeyPath(v45, v46, SubKey, v31) < 0 )
    {
      v11 = 0;
    }
    v32 = v46;
    if ( v11 )
      v32 = SubKey;
    v33 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v32, 0, 0x20019u, &hKey);
    LODWORD(v44) = v33;
    if ( v33 > 0 )
      v35 = (unsigned __int16)v33 | 0x80070000;
    else
      v35 = v33;
    if ( v35 )
    {
      if ( v33 > 0 )
        v33 = (unsigned __int16)v33 | 0x80070000;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\filtereg\\languageresources.cxx",
        (const char *)(unsigned int)v33,
        phkResulta);
    }
    result = CWin32RegAccess::GetValueAndSize((CWin32RegAccess *)&hKey, v34, *(wchar_t **)(a3 + 8), *(_DWORD *)a3, v42);
    if ( !result )
    {
      v36 = (unsigned int)v44;
      if ( (int)v44 > 0 )
        v37 = (unsigned __int16)v44 | 0x80070000;
      else
        v37 = v44;
      if ( v37 != -2147024662 )
      {
        if ( (int)v44 > 0 )
          v36 = (unsigned __int16)v44 | 0x80070000;
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x147,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\filtereg\\languageresources.cxx",
          (const char *)v36,
          phkResultb);
      }
      XGrowable<wchar_t,260>::SetSize(a3, v42[0]);
      CWin32RegAccess::Get((CWin32RegAccess *)&hKey, 0, *(wchar_t **)(a3 + 8), v42[0]);
      v38 = (unsigned int)v44;
      if ( (int)v44 > 0 )
        result = (unsigned __int16)v44 | 0x80070000;
      else
        result = v44;
      if ( result )
      {
        if ( (int)v44 > 0 )
          v38 = (unsigned __int16)v44 | 0x80070000;
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x144,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\filtereg\\languageresources.cxx",
          (const char *)v38,
          phkResultb);
      }
    }
    if ( hKey )
      return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x1800630c8  mov     [rsp-8+arg_18], rbx
0x1800630cd  push    rbp
0x1800630ce  push    rsi
0x1800630cf  push    rdi
0x1800630d0  push    r14
0x1800630d2  push    r15
0x1800630d4  lea     rbp, [rsp-240h]
0x1800630dc  sub     rsp, 340h
0x1800630e3  mov     rax, cs:__security_cookie
0x1800630ea  xor     rax, rsp
0x1800630ed  mov     [rbp+260h+var_30], rax
0x1800630f4  mov     rdi, r8
0x1800630f7  mov     r14, rdx
0x1800630fa  mov     r10, rcx
0x1800630fd  xor     r15d, r15d
0x180063100  mov     ebx, r15d
0x180063103  mov     [rsp+360h+var_330], ebx
0x180063107  test    rdx, rdx
0x18006310a  jz      loc_180063199
0x180063110  mov     qword ptr [rsp+360h+var_330], r15
0x180063115  lea     r8, [rsp+360h+var_330]; unsigned __int64 *
0x18006311a  mov     edx, 104h; unsigned __int64
0x18006311f  mov     rcx, r14; wchar_t *
0x180063122  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180063127  test    eax, eax
0x180063129  js      short loc_180063135
0x18006312b  mov     ebx, [rsp+360h+var_330]
0x18006312f  inc     ebx
0x180063131  mov     esi, ebx
0x180063133  jmp     short loc_180063153
0x180063135  cmp     dword ptr [rdi], 2
0x180063138  jnb     short loc_180063147
0x18006313a  mov     edx, 2
0x18006313f  mov     rcx, rdi
0x180063142  call    ?SetSize@?$XGrowable@_W$0BAE@@@QEAAPEA_WI@Z; XGrowable<wchar_t,260>::SetSize(uint)
0x180063147  xor     ecx, ecx
0x180063149  mov     rax, [rdi+8]
0x18006314d  mov     [rax], cx
0x180063150  mov     esi, r15d
0x180063153  cmp     [rdi], esi
0x180063155  jnb     short loc_180063161
0x180063157  mov     edx, ebx
0x180063159  mov     rcx, rdi
0x18006315c  call    ?SetSize@?$XGrowable@_W$0BAE@@@QEAAPEA_WI@Z; XGrowable<wchar_t,260>::SetSize(uint)
0x180063161  mov     r8d, esi
0x180063164  add     r8, r8; Size
0x180063167  mov     rdx, r14; Src
0x18006316a  mov     rcx, [rdi+8]; void *
0x18006316e  call    memcpy_0
0x180063173  mov     rcx, [rbp+260h+var_30]
0x18006317a  xor     rcx, rsp; StackCookie
0x18006317d  call    __security_check_cookie
0x180063182  mov     rbx, [rsp+360h+arg_18]
0x18006318a  add     rsp, 340h
0x180063191  pop     r15
0x180063193  pop     r14
0x180063195  pop     rdi
0x180063196  pop     rsi
0x180063197  pop     rbp
0x180063198  retn
0x180063199  mov     [rsp+360h+var_310], r15w
0x18006319f  mov     ebx, 64h ; 'd'
0x1800631a4  mov     edx, ebx
0x1800631a6  lea     rax, [rsp+360h+var_310]
0x1800631ab  lea     esi, [rbx-63h]
0x1800631ae  cmp     [rax], r15w
0x1800631b2  jz      short loc_1800631BD
0x1800631b4  add     rax, 2
0x1800631b8  sub     rdx, rsi
0x1800631bb  jnz     short loc_1800631AE
0x1800631bd  mov     rax, rdx
0x1800631c0  neg     rax
0x1800631c3  sbb     r9d, r9d
0x1800631c6  not     r9d
0x1800631c9  and     r9d, 80070057h
0x1800631d0  mov     rax, rdx
0x1800631d3  mov     rcx, rbx
0x1800631d6  sub     rcx, rdx
0x1800631d9  neg     rax
0x1800631dc  sbb     r8, r8
0x1800631df  and     r8, rcx
0x1800631e2  mov     r14d, 7FFFFFFEh
0x1800631e8  test    rdx, rdx
0x1800631eb  jz      short loc_18006324A
0x1800631ed  mov     ecx, r14d
0x1800631f0  lea     r9, aSoftwareClasse_0; "Software\\Classes\\CLSID\\"
0x1800631f7  mov     rdx, rbx
0x1800631fa  sub     rdx, r8
0x1800631fd  lea     rax, [rsp+360h+var_310]
0x180063202  lea     rax, [rax+r8*2]
0x180063206  jz      short loc_18006322B
0x180063208  test    rcx, rcx
0x18006320b  jz      short loc_18006322B
0x18006320d  movzx   r8d, word ptr [r9]
0x180063211  test    r8w, r8w
0x180063215  jz      short loc_18006322B
0x180063217  add     r9, 2
0x18006321b  mov     [rax], r8w
0x18006321f  add     rax, 2
0x180063223  sub     rcx, rsi
0x180063226  sub     rdx, rsi
0x180063229  jnz     short loc_180063208
0x18006322b  lea     rcx, [rax-2]
0x18006322f  test    rdx, rdx
0x180063232  cmovnz  rcx, rax
0x180063236  mov     [rcx], r15w
0x18006323a  neg     rdx
0x18006323d  sbb     r9d, r9d
0x180063240  not     r9d
0x180063243  and     r9d, 8007007Ah; char *
0x18006324a  mov     rcx, [rbp+268h]; this
0x180063251  test    r9d, r9d
0x180063254  jns     short loc_180063268
0x180063256  lea     r8, aOnecoreuapBase_256; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18006325d  mov     edx, 51h ; 'Q'; void *
0x180063262  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180063268  mov     r8, r10; wchar_t *
0x18006326b  mov     rdx, rbx; unsigned __int64
0x18006326e  lea     rcx, [rsp+360h+var_310]; wchar_t *
0x180063273  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180063278  mov     rcx, [rbp+268h]; this
0x18006327f  test    eax, eax
0x180063281  jns     short loc_180063298
0x180063283  mov     r9d, eax; char *
0x180063286  lea     r8, aOnecoreuapBase_256; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18006328d  mov     edx, 51h ; 'Q'; void *
0x180063292  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180063298  mov     rdx, rbx
0x18006329b  lea     rax, [rsp+360h+var_310]
0x1800632a0  cmp     [rax], r15w
0x1800632a4  jz      short loc_1800632AF
0x1800632a6  add     rax, 2
0x1800632aa  sub     rdx, rsi
0x1800632ad  jnz     short loc_1800632A0
0x1800632af  mov     rax, rdx
0x1800632b2  neg     rax
0x1800632b5  sbb     r9d, r9d
0x1800632b8  not     r9d
0x1800632bb  and     r9d, 80070057h
0x1800632c2  mov     rax, rdx
0x1800632c5  mov     rcx, rbx
0x1800632c8  sub     rcx, rdx
0x1800632cb  neg     rax
0x1800632ce  sbb     r8, r8
0x1800632d1  and     r8, rcx
0x1800632d4  test    rdx, rdx
0x1800632d7  jz      short loc_18006332D
0x1800632d9  lea     rcx, aInprocserver32; "\\InprocServer32"
0x1800632e0  sub     rbx, r8
0x1800632e3  lea     rax, [rsp+360h+var_310]
0x1800632e8  lea     rax, [rax+r8*2]
0x1800632ec  jz      short loc_18006330E
0x1800632ee  test    r14, r14
0x1800632f1  jz      short loc_18006330E
0x1800632f3  movzx   edx, word ptr [rcx]
0x1800632f6  test    dx, dx
0x1800632f9  jz      short loc_18006330E
0x1800632fb  add     rcx, 2
0x1800632ff  mov     [rax], dx
0x180063302  add     rax, 2
0x180063306  sub     r14, rsi
0x180063309  sub     rbx, rsi
0x18006330c  jnz     short loc_1800632EE
0x18006330e  lea     rcx, [rax-2]
0x180063312  test    rbx, rbx
0x180063315  cmovnz  rcx, rax
0x180063319  mov     [rcx], r15w
0x18006331d  neg     rbx
0x180063320  sbb     r9d, r9d
0x180063323  not     r9d
0x180063326  and     r9d, 8007007Ah; char *
0x18006332d  mov     rcx, [rbp+268h]; this
0x180063334  test    r9d, r9d
0x180063337  jns     short loc_18006334B
0x180063339  lea     r8, aOnecoreuapBase_256; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180063340  mov     edx, 51h ; 'Q'; void *
0x180063345  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006334b  mov     [rsp+360h+hKey], r15
0x180063350  mov     [rsp+360h+var_320], r15
0x180063355  mov     [rsp+360h+var_318], r15
0x18006335a  call    cs:__imp_RtlIsStateSeparationEnabled
0x180063360  test    al, al
0x180063362  jz      short loc_180063389
0x180063364  lea     rdx, [rsp+360h+var_318]; struct CSearchRegistryRedirectHelper **
0x180063369  call    ?GetSearchRegistryRedirect@@YA_NPEB_WPEAPEAVCSearchRegistryRedirectHelper@@@Z; GetSearchRegistryRedirect(wchar_t const *,CSearchRegistryRedirectHelper * *)
0x18006336e  test    al, al
0x180063370  jz      short loc_180063389
0x180063372  lea     r8, [rbp+260h+SubKey]; wchar_t *
0x180063376  lea     rdx, [rsp+360h+var_310]; wchar_t *
0x18006337b  mov     rcx, [rsp+360h+var_318]; this
0x180063380  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x180063385  test    eax, eax
0x180063387  jns     short loc_18006338C
0x180063389  mov     sil, r15b
0x18006338c  lea     rdx, [rsp+360h+var_310]
0x180063391  lea     rax, [rbp+260h+SubKey]
0x180063395  test    sil, sil
0x180063398  cmovnz  rdx, rax; lpSubKey
0x18006339c  lea     rax, [rsp+360h+hKey]
0x1800633a1  mov     qword ptr [rsp+360h+phkResult], rax; int
0x1800633a6  mov     r9d, 20019h; samDesired
0x1800633ac  xor     r8d, r8d; ulOptions
0x1800633af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800633b6  call    cs:__imp_RegOpenKeyExW
0x1800633bc  mov     dword ptr [rsp+360h+var_320], eax
0x1800633c0  mov     ebx, 80070000h
0x1800633c5  test    eax, eax
0x1800633c7  jg      short loc_1800633CD
0x1800633c9  mov     ecx, eax
0x1800633cb  jmp     short loc_1800633D2
0x1800633cd  movzx   ecx, ax
0x1800633d0  or      ecx, ebx
0x1800633d2  test    ecx, ecx
0x1800633d4  jnz     loc_1800634B6
0x1800633da  lea     rax, [rsp+360h+var_330]
0x1800633df  mov     qword ptr [rsp+360h+phkResult], rax; int
0x1800633e4  mov     r9d, [rdi]; unsigned int
0x1800633e7  mov     r8, [rdi+8]; wchar_t *
0x1800633eb  lea     rcx, [rsp+360h+hKey]; this
0x1800633f0  call    ?GetValueAndSize@CWin32RegAccess@@QEAAHPEB_WPEA_WIAEAI@Z; CWin32RegAccess::GetValueAndSize(wchar_t const *,wchar_t *,uint,uint &)
0x1800633f5  test    eax, eax
0x1800633f7  jnz     loc_18006349D
0x1800633fd  mov     r9d, dword ptr [rsp+360h+var_320]
0x180063402  test    r9d, r9d
0x180063405  jg      short loc_18006340C
0x180063407  mov     eax, r9d
0x18006340a  jmp     short loc_180063412
0x18006340c  movzx   eax, r9w
0x180063410  or      eax, ebx
0x180063412  cmp     eax, 800700EAh
0x180063417  jnz     short loc_180063478
0x180063419  mov     edx, [rsp+360h+var_330]
0x18006341d  mov     rcx, rdi
0x180063420  call    ?SetSize@?$XGrowable@_W$0BAE@@@QEAAPEA_WI@Z; XGrowable<wchar_t,260>::SetSize(uint)
0x180063425  mov     r9d, [rsp+360h+var_330]; unsigned int
0x18006342a  mov     r8, [rdi+8]; wchar_t *
0x18006342e  xor     edx, edx; wchar_t *
0x180063430  lea     rcx, [rsp+360h+hKey]; this
0x180063435  call    ?Get@CWin32RegAccess@@QEAAHPEB_WPEA_WI@Z; CWin32RegAccess::Get(wchar_t const *,wchar_t *,uint)
0x18006343a  mov     r9d, dword ptr [rsp+360h+var_320]
0x18006343f  test    r9d, r9d
0x180063442  jg      short loc_180063449
0x180063444  mov     eax, r9d
0x180063447  jmp     short loc_18006344F
0x180063449  movzx   eax, r9w
0x18006344d  or      eax, ebx
0x18006344f  test    eax, eax
0x180063451  jz      short loc_18006349D
0x180063453  test    r9d, r9d
0x180063456  jle     short loc_18006345F
0x180063458  movzx   r9d, r9w
0x18006345c  or      r9d, ebx; char *
0x18006345f  mov     rcx, [rbp+268h]; this
0x180063466  lea     r8, aOnecoreuapBase_293; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18006346d  mov     edx, 144h; void *
0x180063472  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180063478  test    r9d, r9d
0x18006347b  jle     short loc_180063484
0x18006347d  movzx   r9d, r9w
0x180063481  or      r9d, ebx; char *
0x180063484  mov     rcx, [rbp+268h]; this
0x18006348b  lea     r8, aOnecoreuapBase_293; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180063492  mov     edx, 147h; void *
0x180063497  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006349d  mov     rcx, [rsp+360h+hKey]; hKey
0x1800634a2  test    rcx, rcx
0x1800634a5  jz      loc_180063173
0x1800634ab  call    cs:__imp_RegCloseKey
0x1800634b1  jmp     loc_180063173
0x1800634b6  test    eax, eax
0x1800634b8  jle     short loc_1800634BF
0x1800634ba  movzx   eax, ax
0x1800634bd  or      eax, ebx
0x1800634bf  mov     rcx, [rbp+268h]; this
0x1800634c6  mov     r9d, eax; char *
0x1800634c9  lea     r8, aOnecoreuapBase_293; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800634d0  mov     edx, 14Bh; void *
0x1800634d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
