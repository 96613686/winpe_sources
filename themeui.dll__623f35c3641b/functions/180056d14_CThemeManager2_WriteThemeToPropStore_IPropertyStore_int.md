# CThemeManager2::_WriteThemeToPropStore(IPropertyStore *,int)

- ea: `0x180056d14`
- end: `0x180056ffe`
- name: `?_WriteThemeToPropStore@CThemeManager2@@AEAAJPEAUIPropertyStore@@H@Z`
- size: `746`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this, struct IPropertyStore *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180054070`

## callees

- `0x18000b328`
- `0x18003488c`
- `0x1800358c0`
- `0x180036318`
- `0x18003cf08`
- `0x180042f84`
- `0x180055f4c`
- `0x180056a04`
- `0x180056c4c`
- `0x180056d14`
- `0x180057108`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180056e7b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180056e7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056fad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056fad`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180056fa3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180056fa3`
- `OLEAUT32!__imp_SysFreeString` at `0x180056fb8`
- `OLEAUT32!__imp_SysFreeString` at `0x180056fb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThemeManager2::_WriteThemeToPropStore(const WCHAR *this, struct IPropertyStore *a2, int a3)
{
  int ThemepackFilePath; // ebx
  CThemeManager2 *v7; // rcx
  const WCHAR *v8; // rdi
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // r8
  HKEY v13; // rcx
  struct ITheme *v15; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v17; // [rsp+40h] [rbp-40h] BYREF
  int v18[3]; // [rsp+44h] [rbp-3Ch] BYREF
  GUID Buf1; // [rsp+50h] [rbp-30h] BYREF
  struct _GUID Buf2; // [rsp+60h] [rbp-20h] BYREF

  v17 = 0;
  ThemepackFilePath = (*(__int64 (__fastcall **)(const WCHAR *, unsigned int *))(*(_QWORD *)this + 88LL))(this, &v17);
  if ( ThemepackFilePath >= 0 )
  {
    ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&v15);
    ThemepackFilePath = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, struct ITheme **))(*(_QWORD *)this + 72LL))(
                          this,
                          v17,
                          &v15);
    if ( ThemepackFilePath >= 0 )
    {
      v18[0] = 0;
      ThemepackFilePath = (*(__int64 (__fastcall **)(struct ITheme *, int *))(*(_QWORD *)v15 + 384LL))(v15, v18);
      if ( ThemepackFilePath >= 0 )
      {
        if ( ((v18[0] - 1) & 0xFFFFFFFD) != 0 )
        {
          if ( v18[0] )
          {
            ThemepackFilePath = -2147467259;
            if ( v18[0] == 2 )
              ThemepackFilePath = 1;
          }
          else
          {
            *(_QWORD *)&v18[1] = 0;
            ThemepackFilePath = (*(__int64 (__fastcall **)(struct ITheme *, int *))(*(_QWORD *)v15 + 24LL))(
                                  v15,
                                  &v18[1]);
            if ( ThemepackFilePath >= 0 )
            {
              if ( (Buf1 = 0, (*(int (__fastcall **)(struct ITheme *, GUID *))(*(_QWORD *)v15 + 120LL))(v15, &Buf1) >= 0)
                && memcmp_0(&Buf1, &GUID_NULL, 0x10u)
                || (ThemepackFilePath = CoCreateGuid(&Buf1), ThemepackFilePath >= 0)
                && (ThemepackFilePath = (*(__int64 (__fastcall **)(struct ITheme *, GUID *))(*(_QWORD *)v15 + 128LL))(
                                          v15,
                                          &Buf1),
                    ThemepackFilePath >= 0) )
              {
                lpFileName = 0;
                v8 = &Default;
                v9 = &Default;
                if ( *(_QWORD *)&v18[1] )
                  v9 = *(const unsigned __int16 **)&v18[1];
                ThemepackFilePath = CThemeManager2::_GetThemepackFilePath(v7, v9, (unsigned __int16 **)&lpFileName);
                if ( ThemepackFilePath >= 0 )
                {
                  ThemepackFilePath = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD, LPCWSTR, _QWORD))(*(_QWORD *)this + 120LL))(
                                        this,
                                        0,
                                        lpFileName,
                                        (unsigned int)(a3 != 0) + 5);
                  if ( ThemepackFilePath >= 0 )
                  {
                    v10 = &Default;
                    if ( *(_QWORD *)&v18[1] )
                      v10 = *(const unsigned __int16 **)&v18[1];
                    ThemepackFilePath = CThemeManager2::_WriteCustomThemeToPropStore(this, v10, &Buf1, lpFileName, a2);
                    v13 = (HKEY)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      if ( *(_QWORD *)&v18[1] )
                        LODWORD(v8) = v18[1];
                      WPP_SF_SSd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        (_DWORD)lpFileName,
                        (_DWORD)v12,
                        (_DWORD)v8,
                        (__int64)lpFileName,
                        ThemepackFilePath);
                    }
                    if ( ThemepackFilePath >= 0 )
                    {
                      Buf2 = 0;
                      if ( SHRegGetGUID(v13, v11, v12, &Buf2) >= 0 && !memcmp_0(&Buf1, &Buf2, 0x10u) )
                        ThemepackFilePath = 1;
                    }
                  }
                  DeleteFileW(lpFileName);
                  CoTaskMemFree((LPVOID)lpFileName);
                }
              }
            }
            SysFreeString(*(BSTR *)&v18[1]);
          }
        }
        else
        {
          ThemepackFilePath = CThemeManager2::_WriteInboxThemeToPropStore(
                                (CThemeManager2 *)(unsigned int)v18[0],
                                v15,
                                v18[0],
                                a2);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids,
              (unsigned int)ThemepackFilePath);
        }
      }
    }
    ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&v15);
  }
  return (unsigned int)ThemepackFilePath;
}

```

## disassembly

```asm
0x180056d14  mov     [rsp-28h+arg_10], rbx
0x180056d19  push    rbp
0x180056d1a  push    rsi
0x180056d1b  push    rdi
0x180056d1c  push    r14
0x180056d1e  push    r15
0x180056d20  mov     rbp, rsp
0x180056d23  sub     rsp, 80h
0x180056d2a  mov     rax, cs:__security_cookie
0x180056d31  xor     rax, rsp
0x180056d34  mov     [rbp+var_10], rax
0x180056d38  mov     r15d, r8d
0x180056d3b  mov     r14, rdx
0x180056d3e  mov     rsi, rcx
0x180056d41  mov     [rbp+var_40], 0
0x180056d48  mov     rax, [rcx]
0x180056d4b  lea     rdx, [rbp+var_40]
0x180056d4f  mov     rax, [rax+58h]
0x180056d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d58  mov     ebx, eax
0x180056d5a  test    eax, eax
0x180056d5c  js      loc_180056FD9
0x180056d62  lea     rcx, [rbp+var_50]
0x180056d66  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180056d6b  nop
0x180056d6c  mov     rax, [rsi]
0x180056d6f  lea     r8, [rbp+var_50]
0x180056d73  mov     edx, [rbp+var_40]
0x180056d76  mov     rcx, rsi
0x180056d79  mov     rax, [rax+48h]
0x180056d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d82  mov     ebx, eax
0x180056d84  test    eax, eax
0x180056d86  js      loc_180056FD0
0x180056d8c  mov     dword ptr [rbp+var_3C], 0
0x180056d93  mov     rcx, [rbp+var_50]
0x180056d97  mov     rax, [rcx]
0x180056d9a  lea     rdx, [rbp+var_3C]
0x180056d9e  mov     rax, [rax+180h]
0x180056da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056daa  mov     ebx, eax
0x180056dac  test    eax, eax
0x180056dae  js      loc_180056FD0
0x180056db4  mov     ecx, dword ptr [rbp+var_3C]; this
0x180056db7  lea     eax, [rcx-1]
0x180056dba  test    eax, 0FFFFFFFDh
0x180056dbf  jnz     short loc_180056E10
0x180056dc1  mov     r9, r14; struct IPropertyStore *
0x180056dc4  mov     r8d, ecx; int
0x180056dc7  mov     rdx, [rbp+var_50]; struct ITheme *
0x180056dcb  call    ?_WriteInboxThemeToPropStore@CThemeManager2@@AEAAJPEAUITheme@@HPEAUIPropertyStore@@@Z; CThemeManager2::_WriteInboxThemeToPropStore(ITheme *,int,IPropertyStore *)
0x180056dd0  mov     ebx, eax
0x180056dd2  lea     rax, WPP_GLOBAL_Control
0x180056dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180056de0  cmp     rcx, rax
0x180056de3  jz      loc_180056FD0
0x180056de9  test    byte ptr [rcx+1Ch], 8
0x180056ded  jz      loc_180056FD0
0x180056df3  mov     edx, 1Ah
0x180056df8  mov     r9d, ebx
0x180056dfb  lea     r8, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids
0x180056e02  mov     rcx, [rcx+10h]
0x180056e06  call    WPP_SF_d
0x180056e0b  jmp     loc_180056FD0
0x180056e10  test    ecx, ecx
0x180056e12  jnz     loc_180056FC0
0x180056e18  mov     qword ptr [rbp+var_3C+4], 0
0x180056e20  mov     rcx, [rbp+var_50]
0x180056e24  mov     rax, [rcx]
0x180056e27  lea     rdx, [rbp+var_3C+4]
0x180056e2b  mov     rax, [rax+18h]
0x180056e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e34  mov     ebx, eax
0x180056e36  test    eax, eax
0x180056e38  js      loc_180056FB4
0x180056e3e  xorps   xmm0, xmm0
0x180056e41  movups  [rbp+Buf1], xmm0
0x180056e45  mov     rcx, [rbp+var_50]
0x180056e49  mov     rax, [rcx]
0x180056e4c  lea     rdx, [rbp+Buf1]
0x180056e50  mov     rax, [rax+78h]
0x180056e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e59  test    eax, eax
0x180056e5b  js      short loc_180056E77
0x180056e5d  mov     r8d, 10h; Size
0x180056e63  lea     rdx, GUID_NULL; Buf2
0x180056e6a  lea     rcx, [rbp+Buf1]; Buf1
0x180056e6e  call    memcmp_0
0x180056e73  test    eax, eax
0x180056e75  jnz     short loc_180056EAC
0x180056e77  lea     rcx, [rbp+Buf1]; pguid
0x180056e7b  call    cs:__imp_CoCreateGuid
0x180056e81  mov     ebx, eax
0x180056e83  test    eax, eax
0x180056e85  js      loc_180056FB4
0x180056e8b  mov     rcx, [rbp+var_50]
0x180056e8f  mov     rax, [rcx]
0x180056e92  lea     rdx, [rbp+Buf1]
0x180056e96  mov     rax, [rax+80h]
0x180056e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ea2  mov     ebx, eax
0x180056ea4  test    eax, eax
0x180056ea6  js      loc_180056FB4
0x180056eac  mov     [rbp+lpFileName], 0
0x180056eb4  lea     rdi, Default
0x180056ebb  mov     rdx, rdi
0x180056ebe  mov     rax, qword ptr [rbp+var_3C+4]
0x180056ec2  test    rax, rax
0x180056ec5  cmovnz  rdx, rax; unsigned __int16 *
0x180056ec9  lea     r8, [rbp+lpFileName]; unsigned __int16 **
0x180056ecd  call    ?_GetThemepackFilePath@CThemeManager2@@AEAAJPEBGPEAPEAG@Z; CThemeManager2::_GetThemepackFilePath(ushort const *,ushort * *)
0x180056ed2  mov     ebx, eax
0x180056ed4  test    eax, eax
0x180056ed6  js      loc_180056FB4
0x180056edc  mov     rax, [rsi]
0x180056edf  neg     r15d
0x180056ee2  sbb     r9d, r9d
0x180056ee5  neg     r9d
0x180056ee8  add     r9d, 5
0x180056eec  mov     r8, [rbp+lpFileName]
0x180056ef0  xor     edx, edx
0x180056ef2  mov     rcx, rsi
0x180056ef5  mov     rax, [rax+78h]
0x180056ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056efe  mov     ebx, eax
0x180056f00  test    eax, eax
0x180056f02  js      loc_180056F9F
0x180056f08  mov     rdx, rdi
0x180056f0b  mov     rax, qword ptr [rbp+var_3C+4]
0x180056f0f  test    rax, rax
0x180056f12  cmovnz  rdx, rax; unsigned __int16 *
0x180056f16  mov     [rsp+80h+var_60], r14; struct IPropertyStore *
0x180056f1b  mov     r9, [rbp+lpFileName]; unsigned __int16 *
0x180056f1f  lea     r8, [rbp+Buf1]; struct _GUID *
0x180056f23  mov     rcx, rsi; this
0x180056f26  call    ?_WriteCustomThemeToPropStore@CThemeManager2@@AEAAJPEBGAEBU_GUID@@0PEAUIPropertyStore@@@Z; CThemeManager2::_WriteCustomThemeToPropStore(ushort const *,_GUID const &,ushort const *,IPropertyStore *)
0x180056f2b  mov     ebx, eax
0x180056f2d  lea     rax, WPP_GLOBAL_Control
0x180056f34  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f3b  cmp     rcx, rax
0x180056f3e  jz      short loc_180056F6A
0x180056f40  test    byte ptr [rcx+1Ch], 8
0x180056f44  jz      short loc_180056F6A
0x180056f46  mov     rdx, [rbp+lpFileName]
0x180056f4a  mov     rax, qword ptr [rbp+var_3C+4]
0x180056f4e  test    rax, rax
0x180056f51  cmovnz  rdi, rax
0x180056f55  mov     [rsp+80h+var_58], ebx
0x180056f59  mov     [rsp+80h+var_60], rdx
0x180056f5e  mov     r9, rdi
0x180056f61  mov     rcx, [rcx+10h]
0x180056f65  call    WPP_SF_SSd
0x180056f6a  test    ebx, ebx
0x180056f6c  js      short loc_180056F9F
0x180056f6e  xorps   xmm0, xmm0
0x180056f71  movups  [rbp+Buf2], xmm0
0x180056f75  lea     r9, [rbp+Buf2]; struct _GUID *
0x180056f79  call    ?SHRegGetGUID@@YAJPEAUHKEY__@@PEBG1PEAU_GUID@@@Z; SHRegGetGUID(HKEY__ *,ushort const *,ushort const *,_GUID *)
0x180056f7e  test    eax, eax
0x180056f80  js      short loc_180056F9F
0x180056f82  mov     r8d, 10h; Size
0x180056f88  lea     rdx, [rbp+Buf2]; Buf2
0x180056f8c  lea     rcx, [rbp+Buf1]; Buf1
0x180056f90  call    memcmp_0
0x180056f95  mov     edx, 1
0x180056f9a  test    eax, eax
0x180056f9c  cmovz   ebx, edx
0x180056f9f  mov     rcx, [rbp+lpFileName]; lpFileName
0x180056fa3  call    cs:__imp_DeleteFileW
0x180056fa9  mov     rcx, [rbp+lpFileName]; pv
0x180056fad  call    cs:__imp_CoTaskMemFree
0x180056fb3  nop
0x180056fb4  mov     rcx, qword ptr [rbp+var_3C+4]; bstrString
0x180056fb8  call    cs:__imp_SysFreeString
0x180056fbe  jmp     short loc_180056FD0
0x180056fc0  mov     ebx, 80004005h
0x180056fc5  mov     edx, 1
0x180056fca  cmp     ecx, 2
0x180056fcd  cmovz   ebx, edx
0x180056fd0  lea     rcx, [rbp+var_50]
0x180056fd4  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x180056fd9  mov     eax, ebx
0x180056fdb  mov     rcx, [rbp+var_10]
0x180056fdf  xor     rcx, rsp; StackCookie
0x180056fe2  call    __security_check_cookie
0x180056fe7  mov     rbx, [rsp+80h+arg_10]
0x180056fef  add     rsp, 80h
0x180056ff6  pop     r15
0x180056ff8  pop     r14
0x180056ffa  pop     rdi
0x180056ffb  pop     rsi
0x180056ffc  pop     rbp
0x180056ffd  retn
```
