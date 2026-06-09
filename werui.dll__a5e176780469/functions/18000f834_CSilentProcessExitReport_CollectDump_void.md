# CSilentProcessExitReport::CollectDump(void)

- ea: `0x18000f834`
- end: `0x18000fb1b`
- name: `?CollectDump@CSilentProcessExitReport@@AEAAJXZ`
- size: `743`
- prototype: `__int64 __fastcall(const unsigned __int16 **this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010234`

## callees

- `0x180003604`
- `0x180003fe4`
- `0x180005c80`
- `0x180007cdc`
- `0x180009580`
- `0x180009b40`
- `0x18000f834`
- `0x18000fb24`
- `0x180010df0`
- `0x180011720`
- `0x1800117fc`
- `0x180012cac`
- `0x18001326c`
- `0x180013e3c`
- `0x180016c1e`
- `0x180016c50`

## import_xrefs

- `SHELL32!SHCreateDirectoryExW` at `0x18000f8d0`
- `SHELL32!SHCreateDirectoryExW` at `0x18000f8d0`

## pseudocode

```c
__int64 __fastcall CSilentProcessExitReport::CollectDump(const unsigned __int16 **this)
{
  unsigned int v2; // eax
  int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned __int64 v6; // r11
  unsigned int DwordData; // eax
  unsigned __int8 *v9[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v11[32]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t String1; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v13[526]; // [rsp+92h] [rbp-6Eh] BYREF
  wchar_t v14; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v15[526]; // [rsp+2A2h] [rbp+1A2h] BYREF

  memset_0(v13, 0, 0x206u);
  memset_0(v15, 0, 0x206u);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v11);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v10);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v9);
  v14 = 0;
  String1 = 0;
  if ( UtilFolderExists(this[105]) || (v2 = SHCreateDirectoryExW(0, this[105], 0)) == 0 || v2 == 80 || v2 == 183 )
  {
    UtilEnableCompression(this[105]);
    v3 = StringCchCopyW(&String1, 0x104u, this[12]);
    if ( v3 >= 0 )
    {
      v3 = StringCchCopyW(&v14, v6, this[13]);
      if ( v3 >= 0 )
      {
        UtilSanitizeFileNameComponent(&String1);
        UtilSanitizeFileNameComponent(&v14);
        DwordData = CRegSetting::GetDwordData((CRegSetting *)(this + 66));
        v3 = CSilentProcessExitReport::PruneDumpFolder((CSilentProcessExitReport *)this, DwordData);
        if ( v3 >= 0 )
        {
          v3 = CSilentProcessExitReport::CreateDumpFolder(this, &String1, v9);
          if ( v3 >= 0 )
          {
            v3 = CSilentProcessExitReport::WriteDumps(
                   (CSilentProcessExitReport *)this,
                   (const unsigned __int16 *)v9[0],
                   &String1,
                   &v14);
            if ( v3 >= 0 )
            {
              CSilentProcessExitTestAutomation::WriteTestHookToRegistry(
                (CSilentProcessExitTestAutomation *)(this + 109),
                L"DumpFolderLocation",
                v9[0],
                2 * ((v9[1] - v9[0]) >> 1) + 2,
                1u);
              v3 = 0;
              goto LABEL_30;
            }
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v5 = 38;
              goto LABEL_8;
            }
          }
          else
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v5 = 37;
              goto LABEL_8;
            }
          }
        }
        else
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v5 = 36;
            goto LABEL_8;
          }
        }
      }
      else
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v5 = 35;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 34;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v3 = ERROR_HR_FROM_WIN32(v2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 33;
LABEL_8:
      WPP_SF_d(v4[2], v5, &WPP_0b9f8713f655331c3edd713292668335_Traceguids, (unsigned int)v3);
    }
  }
LABEL_30:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v9);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v10);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v11);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000f834  mov     [rsp-8+arg_8], rbx
0x18000f839  mov     [rsp-8+arg_10], rdi
0x18000f83e  push    rbp
0x18000f83f  lea     rbp, [rsp-3C0h]
0x18000f847  sub     rsp, 4C0h
0x18000f84e  mov     rax, cs:__security_cookie
0x18000f855  xor     rax, rsp
0x18000f858  mov     [rbp+3C0h+var_10], rax
0x18000f85f  mov     rdi, rcx
0x18000f862  mov     ebx, 206h
0x18000f867  mov     r8d, ebx; Size
0x18000f86a  xor     edx, edx; Val
0x18000f86c  lea     rcx, [rbp+3C0h+var_42E]; void *
0x18000f870  call    memset_0
0x18000f875  mov     r8d, ebx; Size
0x18000f878  xor     edx, edx; Val
0x18000f87a  lea     rcx, [rbp+3C0h+var_21E]; void *
0x18000f881  call    memset_0
0x18000f886  lea     rcx, [rsp+4C0h+var_450]; void *
0x18000f88b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000f890  nop
0x18000f891  lea     rcx, [rsp+4C0h+var_470]; void *
0x18000f896  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000f89b  nop
0x18000f89c  lea     rcx, [rsp+4C0h+var_490]; void *
0x18000f8a1  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000f8a6  nop
0x18000f8a7  xor     eax, eax
0x18000f8a9  mov     [rbp+3C0h+var_220], ax
0x18000f8b0  mov     [rbp+3C0h+String1], ax
0x18000f8b4  mov     rcx, [rdi+348h]; lpSrc
0x18000f8bb  call    ?UtilFolderExists@@YA_NPEBG@Z; UtilFolderExists(ushort const *)
0x18000f8c0  test    al, al
0x18000f8c2  jnz     short loc_18000F92D
0x18000f8c4  xor     r8d, r8d; psa
0x18000f8c7  mov     rdx, [rdi+348h]; pszPath
0x18000f8ce  xor     ecx, ecx; hwnd
0x18000f8d0  call    cs:__imp_SHCreateDirectoryExW
0x18000f8d6  test    eax, eax
0x18000f8d8  jz      short loc_18000F92D
0x18000f8da  cmp     eax, 50h ; 'P'
0x18000f8dd  jz      short loc_18000F92D
0x18000f8df  cmp     eax, 0B7h
0x18000f8e4  jz      short loc_18000F92D
0x18000f8e6  mov     ecx, eax; unsigned int
0x18000f8e8  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000f8ed  mov     ebx, eax
0x18000f8ef  lea     rax, WPP_GLOBAL_Control
0x18000f8f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8fd  cmp     rcx, rax
0x18000f900  jz      loc_18000FAD5
0x18000f906  test    byte ptr [rcx+1Ch], 1
0x18000f90a  jz      loc_18000FAD5
0x18000f910  mov     edx, 21h ; '!'
0x18000f915  mov     r9d, ebx
0x18000f918  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x18000f91f  mov     rcx, [rcx+10h]
0x18000f923  call    WPP_SF_d
0x18000f928  jmp     loc_18000FAD5
0x18000f92d  mov     rcx, [rdi+348h]; unsigned __int16 *
0x18000f934  call    ?UtilEnableCompression@@YAJPEBG@Z; UtilEnableCompression(ushort const *)
0x18000f939  mov     r8, [rdi+60h]; unsigned __int16 *
0x18000f93d  mov     r11d, 104h
0x18000f943  mov     edx, r11d; unsigned __int64
0x18000f946  lea     rcx, [rbp+3C0h+String1]; unsigned __int16 *
0x18000f94a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f94f  mov     ebx, eax
0x18000f951  test    eax, eax
0x18000f953  jns     short loc_18000F97D
0x18000f955  lea     rax, WPP_GLOBAL_Control
0x18000f95c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f963  cmp     rcx, rax
0x18000f966  jz      loc_18000FAD5
0x18000f96c  test    byte ptr [rcx+1Ch], 1
0x18000f970  jz      loc_18000FAD5
0x18000f976  mov     edx, 22h ; '"'
0x18000f97b  jmp     short loc_18000F915
0x18000f97d  mov     r8, [rdi+68h]; unsigned __int16 *
0x18000f981  mov     rdx, r11; unsigned __int64
0x18000f984  lea     rcx, [rbp+3C0h+var_220]; unsigned __int16 *
0x18000f98b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f990  mov     ebx, eax
0x18000f992  test    eax, eax
0x18000f994  jns     short loc_18000F9C1
0x18000f996  lea     rax, WPP_GLOBAL_Control
0x18000f99d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9a4  cmp     rcx, rax
0x18000f9a7  jz      loc_18000FAD5
0x18000f9ad  test    byte ptr [rcx+1Ch], 1
0x18000f9b1  jz      loc_18000FAD5
0x18000f9b7  mov     edx, 23h ; '#'
0x18000f9bc  jmp     loc_18000F915
0x18000f9c1  lea     rcx, [rbp+3C0h+String1]; String1
0x18000f9c5  call    ?UtilSanitizeFileNameComponent@@YAXPEAG@Z; UtilSanitizeFileNameComponent(ushort *)
0x18000f9ca  lea     rcx, [rbp+3C0h+var_220]; String1
0x18000f9d1  call    ?UtilSanitizeFileNameComponent@@YAXPEAG@Z; UtilSanitizeFileNameComponent(ushort *)
0x18000f9d6  lea     rcx, [rdi+210h]; this
0x18000f9dd  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18000f9e2  mov     edx, eax; unsigned int
0x18000f9e4  mov     rcx, rdi; this
0x18000f9e7  call    ?PruneDumpFolder@CSilentProcessExitReport@@AEAAJK@Z; CSilentProcessExitReport::PruneDumpFolder(ulong)
0x18000f9ec  mov     ebx, eax
0x18000f9ee  test    eax, eax
0x18000f9f0  jns     short loc_18000FA1D
0x18000f9f2  lea     rax, WPP_GLOBAL_Control
0x18000f9f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa00  cmp     rcx, rax
0x18000fa03  jz      loc_18000FAD5
0x18000fa09  test    byte ptr [rcx+1Ch], 1
0x18000fa0d  jz      loc_18000FAD5
0x18000fa13  mov     edx, 24h ; '$'
0x18000fa18  jmp     loc_18000F915
0x18000fa1d  lea     r8, [rsp+4C0h+var_490]
0x18000fa22  lea     rdx, [rbp+3C0h+String1]
0x18000fa26  mov     rcx, rdi
0x18000fa29  call    ?CreateDumpFolder@CSilentProcessExitReport@@AEAAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; CSilentProcessExitReport::CreateDumpFolder(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18000fa2e  mov     ebx, eax
0x18000fa30  test    eax, eax
0x18000fa32  jns     short loc_18000FA5F
0x18000fa34  lea     rax, WPP_GLOBAL_Control
0x18000fa3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa42  cmp     rcx, rax
0x18000fa45  jz      loc_18000FAD5
0x18000fa4b  test    byte ptr [rcx+1Ch], 1
0x18000fa4f  jz      loc_18000FAD5
0x18000fa55  mov     edx, 25h ; '%'
0x18000fa5a  jmp     loc_18000F915
0x18000fa5f  lea     r9, [rbp+3C0h+var_220]; unsigned __int16 *
0x18000fa66  lea     r8, [rbp+3C0h+String1]; unsigned __int16 *
0x18000fa6a  mov     rdx, [rsp+4C0h+var_490]; unsigned __int16 *
0x18000fa6f  mov     rcx, rdi; this
0x18000fa72  call    ?WriteDumps@CSilentProcessExitReport@@AEAAJPEBG00@Z; CSilentProcessExitReport::WriteDumps(ushort const *,ushort const *,ushort const *)
0x18000fa77  mov     ebx, eax
0x18000fa79  test    eax, eax
0x18000fa7b  jns     short loc_18000FAA0
0x18000fa7d  lea     rax, WPP_GLOBAL_Control
0x18000fa84  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa8b  cmp     rcx, rax
0x18000fa8e  jz      short loc_18000FAD5
0x18000fa90  test    byte ptr [rcx+1Ch], 1
0x18000fa94  jz      short loc_18000FAD5
0x18000fa96  mov     edx, 26h ; '&'
0x18000fa9b  jmp     loc_18000F915
0x18000faa0  mov     r9, [rsp+4C0h+var_488]
0x18000faa5  mov     r8, [rsp+4C0h+var_490]; unsigned __int8 *
0x18000faaa  sub     r9, r8
0x18000faad  sar     r9, 1
0x18000fab0  lea     r9d, ds:2[r9*2]; unsigned int
0x18000fab8  lea     rcx, [rdi+368h]; this
0x18000fabf  mov     [rsp+4C0h+var_4A0], 1; unsigned int
0x18000fac7  lea     rdx, aDumpfolderloca; "DumpFolderLocation"
0x18000face  call    ?WriteTestHookToRegistry@CSilentProcessExitTestAutomation@@QEAAXPEBGPEAEKK@Z; CSilentProcessExitTestAutomation::WriteTestHookToRegistry(ushort const *,uchar *,ulong,ulong)
0x18000fad3  xor     ebx, ebx
0x18000fad5  lea     rcx, [rsp+4C0h+var_490]
0x18000fada  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000fadf  nop
0x18000fae0  lea     rcx, [rsp+4C0h+var_470]
0x18000fae5  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000faea  nop
0x18000faeb  lea     rcx, [rsp+4C0h+var_450]
0x18000faf0  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000faf5  mov     eax, ebx
0x18000faf7  mov     rcx, [rbp+3C0h+var_10]
0x18000fafe  xor     rcx, rsp; StackCookie
0x18000fb01  call    __security_check_cookie
0x18000fb06  lea     r11, [rsp+4C0h+var_s0]
0x18000fb0e  mov     rbx, [r11+18h]
0x18000fb12  mov     rdi, [r11+20h]
0x18000fb16  mov     rsp, r11
0x18000fb19  pop     rbp
0x18000fb1a  retn
```
