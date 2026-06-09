# IconSize_Load(int *,int *,int *,int *)

- ea: `0x180003f80`
- end: `0x18000419f`
- name: `?IconSize_Load@@YAJPEAH000@Z`
- size: `543`
- prototype: `__int64 __fastcall(int *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003c60`

## callees

- `0x180003f80`
- `0x180004554`
- `0x18000470c`
- `0x1800089c0`
- `0x180032bfc`
- `0x180033b0c`
- `0x1800358c0`
- `0x180043d9c`

## import_xrefs

- `SHCORE!SHGetValueW` at `0x180004080`
- `SHCORE!SHGetValueW` at `0x1800040d9`
- `SHCORE!SHGetValueW` at `0x180004080`
- `SHCORE!SHGetValueW` at `0x1800040d9`
- `SHLWAPI!StrToIntW` at `0x18000409e`
- `SHLWAPI!StrToIntW` at `0x1800040f7`
- `SHLWAPI!StrToIntW` at `0x18000409e`
- `SHLWAPI!StrToIntW` at `0x1800040f7`
- `USER32!GetThreadDpiAwarenessContext` at `0x180004134`
- `USER32!GetThreadDpiAwarenessContext` at `0x180004134`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x18000403b`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x180004107`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x180004120`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x18000403b`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x180004107`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x180004120`

## string_xrefs

- `0x180004156`: `Icon=%d, SmallIcon=%d, IconWidthSpacing=%d, IconHeightSpacing=%d, ThreadDpiAwarenessContext=0x%x`

## pseudocode

```c
__int64 __fastcall IconSize_Load(int *a1, int *a2, int *a3, int *a4)
{
  __int64 *v8; // rax
  __int64 v9; // rbx
  int SystemMetrics; // eax
  LSTATUS v11; // eax
  bool v12; // sf
  LSTATUS v13; // eax
  bool v14; // sf
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  __int64 ThreadDpiAwarenessContext; // rax
  __int64 v20; // rcx
  void *pvData; // [rsp+20h] [rbp-4B8h]
  DWORD *pcbData; // [rsp+28h] [rbp-4B0h]
  int v24; // [rsp+30h] [rbp-4A8h]
  DWORD v25; // [rsp+40h] [rbp-498h] BYREF
  _QWORD v26[5]; // [rsp+48h] [rbp-490h] BYREF
  _BYTE v27[16]; // [rsp+70h] [rbp-468h] BYREF
  WCHAR pszSrc[8]; // [rsp+80h] [rbp-458h] BYREF
  unsigned __int16 v29[512]; // [rsp+90h] [rbp-448h] BYREF

  v26[1] = a1;
  v26[2] = a2;
  v26[3] = a3;
  v26[4] = a4;
  *(_OWORD *)pszSrc = 0;
  v25 = 16;
  v8 = (__int64 *)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ThemeUiDistributionOfIconSpacingTest,_tip_ThemeUiDistributionOfIconSpacingTest>,>(v27);
  v9 = *v8;
  *v8 = 0;
  v26[0] = v9;
  wil::com_ptr_t<tip2::details::merged_data<_tip_ThemeUiDistributionOfIconSpacingTest,_tip_ThemeUiDistributionOfIconSpacingTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ThemeUiDistributionOfIconSpacingTest,_tip_ThemeUiDistributionOfIconSpacingTest>,wil::err_returncode_policy>(v27);
  tip2::details::shared_data<0,0,0>::start(v9 + 8, v27);
  if ( v9 )
    tip2::details::shared_data<0,0,0>::complete_without_lock(v9 + 8);
  wil::com_ptr_t<tip2::details::merged_data<_tip_ThemeUiDistributionOfIconSpacingTest,_tip_ThemeUiDistributionOfIconSpacingTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ThemeUiDistributionOfIconSpacingTest,_tip_ThemeUiDistributionOfIconSpacingTest>,wil::err_returncode_policy>(v26);
  SystemMetrics = ClassicGetSystemMetrics(11);
  *a3 = SystemMetrics;
  *a4 = SystemMetrics / 2;
  v11 = SHGetValueW(HKEY_CURRENT_USER, L"Control Panel\\Desktop\\WindowMetrics", L"Shell Icon Size", 0, pszSrc, &v25);
  v12 = v11 < 0;
  if ( v11 > 0 )
    v12 = 1;
  if ( !v12 )
    *a3 = StrToIntW(pszSrc);
  v25 = 16;
  v13 = SHGetValueW(
          HKEY_CURRENT_USER,
          L"Control Panel\\Desktop\\WindowMetrics",
          L"Shell Small Icon Size",
          0,
          pszSrc,
          &v25);
  v14 = v13 < 0;
  if ( v13 > 0 )
    v14 = 1;
  if ( !v14 )
    *a4 = StrToIntW(pszSrc);
  v15 = *a3;
  v16 = ClassicGetSystemMetrics(38) - v15;
  *a1 = v16;
  if ( v16 < 0 )
    *a1 = 0;
  v17 = *a3;
  v18 = ClassicGetSystemMetrics(39) - v17;
  *a2 = v18;
  if ( v18 < 0 )
    *a2 = 0;
  ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
  v24 = *a2;
  LODWORD(pcbData) = *a1;
  LODWORD(pvData) = *a4;
  StringCchPrintfW(
    v29,
    0x200u,
    L"Icon=%d, SmallIcon=%d, IconWidthSpacing=%d, IconHeightSpacing=%d, ThreadDpiAwarenessContext=0x%x",
    (unsigned int)*a3,
    pvData,
    pcbData,
    v24,
    ThreadDpiAwarenessContext);
  ThemesTelemetry::SystemMetrics<unsigned short const (&)[14],unsigned short (&)[512]>(v20, v29);
  return 0;
}

```

## disassembly

```asm
0x180003f80  push    rbx
0x180003f82  push    rsi
0x180003f83  push    rdi
0x180003f84  push    r12
0x180003f86  push    r14
0x180003f88  push    r15
0x180003f8a  sub     rsp, 4A8h
0x180003f91  mov     rax, cs:__security_cookie
0x180003f98  xor     rax, rsp
0x180003f9b  mov     [rsp+4D8h+var_48], rax
0x180003fa3  mov     r15, r9
0x180003fa6  mov     rdi, r8
0x180003fa9  mov     r14, rdx
0x180003fac  mov     rsi, rcx
0x180003faf  mov     [rsp+4D8h+var_488], rcx
0x180003fb4  mov     [rsp+4D8h+var_480], rdx
0x180003fb9  mov     [rsp+4D8h+var_478], r8
0x180003fbe  mov     [rsp+4D8h+var_470], r9
0x180003fc3  xorps   xmm0, xmm0
0x180003fc6  movups  xmmword ptr [rsp+4D8h+pszSrc], xmm0
0x180003fce  mov     [rsp+4D8h+var_498], 10h
0x180003fd6  lea     rcx, [rsp+4D8h+var_468]
0x180003fdb  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_ThemeUiDistributionOfIconSpacingTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_ThemeUiDistributionOfIconSpacingTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ThemeUiDistributionOfIconSpacingTest,_tip_ThemeUiDistributionOfIconSpacingTest>,>(void)
0x180003fe0  mov     rbx, [rax]
0x180003fe3  mov     qword ptr [rax], 0
0x180003fea  mov     [rsp+4D8h+var_490], rbx
0x180003fef  lea     rcx, [rsp+4D8h+var_468]
0x180003ff4  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ThemeUiDistributionOfIconSpacingTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ThemeUiDistributionOfIconSpacingTest,_tip_ThemeUiDistributionOfIconSpacingTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ThemeUiDistributionOfIconSpacingTest,_tip_ThemeUiDistributionOfIconSpacingTest>,wil::err_returncode_policy>(void)
0x180003ff9  lea     rdx, [rsp+4D8h+var_468]
0x180003ffe  lea     rcx, [rbx+8]
0x180004002  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180004007  test    rbx, rbx
0x18000400a  jz      short loc_180004015
0x18000400c  lea     rcx, [rbx+8]
0x180004010  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x180004015  lea     rcx, [rsp+4D8h+var_490]
0x18000401a  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ThemeUiDistributionOfIconSpacingTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ThemeUiDistributionOfIconSpacingTest,_tip_ThemeUiDistributionOfIconSpacingTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ThemeUiDistributionOfIconSpacingTest,_tip_ThemeUiDistributionOfIconSpacingTest>,wil::err_returncode_policy>(void)
0x18000401f  nop
0x180004020  jmp     short loc_180004036
0x180004022  mov     rsi, [rsp+4D8h+var_488]
0x180004027  mov     r14, [rsp+4D8h+var_480]
0x18000402c  mov     rdi, [rsp+4D8h+var_478]
0x180004031  mov     r15, [rsp+4D8h+var_470]
0x180004036  mov     ecx, 0Bh
0x18000403b  call    cs:__imp_ClassicGetSystemMetrics
0x180004041  mov     [rdi], eax
0x180004043  cdq
0x180004044  mov     ecx, 2
0x180004049  idiv    ecx
0x18000404b  mov     [r15], eax
0x18000404e  lea     rax, [rsp+4D8h+var_498]
0x180004053  mov     [rsp+4D8h+pcbData], rax; pcbData
0x180004058  lea     rax, [rsp+4D8h+pszSrc]
0x180004060  mov     [rsp+4D8h+pvData], rax; pvData
0x180004065  xor     r9d, r9d; pdwType
0x180004068  lea     r8, pszValue; "Shell Icon Size"
0x18000406f  lea     rdx, pszSubKey; "Control Panel\\Desktop\\WindowMetrics"
0x180004076  mov     rbx, 0FFFFFFFF80000001h
0x18000407d  mov     rcx, rbx; hkey
0x180004080  call    cs:__imp_SHGetValueW
0x180004086  test    eax, eax
0x180004088  jle     short loc_180004094
0x18000408a  movzx   eax, ax
0x18000408d  or      eax, 80070000h
0x180004092  test    eax, eax
0x180004094  js      short loc_1800040A6
0x180004096  lea     rcx, [rsp+4D8h+pszSrc]; pszSrc
0x18000409e  call    cs:__imp_StrToIntW
0x1800040a4  mov     [rdi], eax
0x1800040a6  mov     [rsp+4D8h+var_498], 10h
0x1800040ae  lea     rax, [rsp+4D8h+var_498]
0x1800040b3  mov     [rsp+4D8h+pcbData], rax; pcbData
0x1800040b8  lea     rax, [rsp+4D8h+pszSrc]
0x1800040c0  mov     [rsp+4D8h+pvData], rax; pvData
0x1800040c5  xor     r9d, r9d; pdwType
0x1800040c8  lea     r8, aShellSmallIcon; "Shell Small Icon Size"
0x1800040cf  lea     rdx, pszSubKey; "Control Panel\\Desktop\\WindowMetrics"
0x1800040d6  mov     rcx, rbx; hkey
0x1800040d9  call    cs:__imp_SHGetValueW
0x1800040df  test    eax, eax
0x1800040e1  jle     short loc_1800040ED
0x1800040e3  movzx   eax, ax
0x1800040e6  or      eax, 80070000h
0x1800040eb  test    eax, eax
0x1800040ed  js      short loc_180004100
0x1800040ef  lea     rcx, [rsp+4D8h+pszSrc]; pszSrc
0x1800040f7  call    cs:__imp_StrToIntW
0x1800040fd  mov     [r15], eax
0x180004100  mov     ebx, [rdi]
0x180004102  mov     ecx, 26h ; '&'
0x180004107  call    cs:__imp_ClassicGetSystemMetrics
0x18000410d  sub     eax, ebx
0x18000410f  mov     [rsi], eax
0x180004111  jns     short loc_180004119
0x180004113  mov     dword ptr [rsi], 0
0x180004119  mov     ebx, [rdi]
0x18000411b  mov     ecx, 27h ; '''
0x180004120  call    cs:__imp_ClassicGetSystemMetrics
0x180004126  sub     eax, ebx
0x180004128  mov     [r14], eax
0x18000412b  jns     short loc_180004134
0x18000412d  mov     dword ptr [r14], 0
0x180004134  call    cs:__imp_GetThreadDpiAwarenessContext
0x18000413a  mov     [rsp+4D8h+var_4A0], rax
0x18000413f  mov     eax, [r14]
0x180004142  mov     [rsp+4D8h+var_4A8], eax
0x180004146  mov     eax, [rsi]
0x180004148  mov     dword ptr [rsp+4D8h+pcbData], eax
0x18000414c  mov     eax, [r15]
0x18000414f  mov     dword ptr [rsp+4D8h+pvData], eax
0x180004153  mov     r9d, [rdi]
0x180004156  lea     r8, aIconDSmallicon; "Icon=%d, SmallIcon=%d, IconWidthSpacing"...
0x18000415d  mov     edx, 200h; unsigned __int64
0x180004162  lea     rcx, [rsp+4D8h+var_448]; unsigned __int16 *
0x18000416a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000416f  lea     rdx, [rsp+4D8h+var_448]
0x180004177  call    ??$SystemMetrics@AEAY0O@$$CBGAEAY0CAA@G@ThemesTelemetry@@SAXAEAY0O@$$CBGAEAY0CAA@G@Z; ThemesTelemetry::SystemMetrics<ushort const (&)[14],ushort (&)[512]>(ushort const (&)[14],ushort (&)[512])
0x18000417c  xor     eax, eax
0x18000417e  mov     rcx, [rsp+4D8h+var_48]
0x180004186  xor     rcx, rsp; StackCookie
0x180004189  call    __security_check_cookie
0x18000418e  add     rsp, 4A8h
0x180004195  pop     r15
0x180004197  pop     r14
0x180004199  pop     r12
0x18000419b  pop     rdi
0x18000419c  pop     rsi
0x18000419d  pop     rbx
0x18000419e  retn
```
