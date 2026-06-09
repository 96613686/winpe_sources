# CSilentProcessExitReport::CreateShellNotification(void)

- ea: `0x18000fc94`
- end: `0x18000ff36`
- name: `?CreateShellNotification@CSilentProcessExitReport@@AEAAJXZ`
- size: `674`
- prototype: `__int64 __fastcall(CSilentProcessExitReport *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180010234`

## callees

- `0x1800024e4`
- `0x1800035dc`
- `0x180003604`
- `0x180003fe4`
- `0x180005c20`
- `0x180005c80`
- `0x180007cdc`
- `0x180008f3c`
- `0x180009580`
- `0x18000fc94`
- `0x180013e3c`
- `0x18001405c`
- `0x180016c1e`
- `0x180016c50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000fd6d`
- `KERNEL32!GetLastError` at `0x18000fd6d`
- `USER32!LoadStringW` at `0x18000fd63`
- `USER32!LoadStringW` at `0x18000fd63`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000fd1b`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000fd1b`

## pseudocode

```c
__int64 __fastcall CSilentProcessExitReport::CreateShellNotification(CSilentProcessExitReport *this)
{
  DWORD LastError; // eax
  int String; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  int v6; // eax
  HINSTANCE v7; // rdx
  __int64 (*v8)(HWND, unsigned int, unsigned __int64, __int64, void *); // r9
  void *v10; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v11[8]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v12[4]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v13[5]; // [rsp+58h] [rbp-A8h] BYREF
  struct _NOTIFYICONDATAW v14; // [rsp+80h] [rbp-80h] BYREF

  memset_0(&v14, 0, sizeof(v14));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v13);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v12);
  *(_QWORD *)v11 = 0;
  v14.cbSize = 976;
  v14.hWnd = 0;
  v14.uID = 0;
  if ( (unsigned __int8)IsLoadIconWPresent() )
    v14.hIcon = LoadIconW(&_ImageBase, (LPCWSTR)0x194);
  else
    v14.hIcon = 0;
  v14.uFlags = 22;
  v14.uTimeout = 0;
  v14.dwInfoFlags = 4;
  if ( !LoadStringW(&_ImageBase, 0x13CFu, v14.szInfoTitle, 64) )
  {
    LastError = GetLastError();
    String = ERROR_HR_FROM_WIN32(LastError);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 10;
LABEL_8:
      WPP_SF_d(v4[2], v5, &WPP_0b9f8713f655331c3edd713292668335_Traceguids, (unsigned int)String);
      goto LABEL_23;
    }
    goto LABEL_23;
  }
  StringCchCopyW(v14.szTip, 0x80u, v14.szInfoTitle);
  if ( *((_DWORD *)this + 1) == *(_DWORD *)this )
  {
    String = UtilLoadString(v12, 5072);
    if ( String >= 0 )
    {
      v6 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
             v13,
             v12[0],
             *((_QWORD *)this + 12),
             *((unsigned int *)this + 1));
      goto LABEL_14;
    }
LABEL_20:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_0b9f8713f655331c3edd713292668335_Traceguids);
    goto LABEL_23;
  }
  String = UtilLoadString(v12, 5073);
  if ( String < 0 )
    goto LABEL_20;
  v10 = (void *)*((_QWORD *)this + 13);
  v6 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
         v13,
         v12[0],
         *((_QWORD *)this + 12),
         *((unsigned int *)this + 1));
LABEL_14:
  String = v6;
  if ( v6 < 0 )
    goto LABEL_20;
  StringCchCopyW(v14.szInfo, 0x100u, v13[0]);
  String = CShellNotification::Create((CSilentProcessExitReport *)((char *)this + 880), v7, &v14, v8, v10);
  if ( String >= 0 )
  {
    *(_QWORD *)v11 = v14.hWnd;
    CSilentProcessExitTestAutomation::WriteTestHookToRegistry(
      (CSilentProcessExitReport *)((char *)this + 872),
      L"ShellNotificationHandle",
      v11,
      8u,
      0xBu);
    goto LABEL_23;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v5 = 12;
    goto LABEL_8;
  }
LABEL_23:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v12);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v13);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18000fc94  mov     [rsp-8+arg_8], rbx
0x18000fc99  mov     [rsp-8+arg_10], rdi
0x18000fc9e  push    rbp
0x18000fc9f  lea     rbp, [rsp-360h]
0x18000fca7  sub     rsp, 460h
0x18000fcae  mov     rax, cs:__security_cookie
0x18000fcb5  xor     rax, rsp
0x18000fcb8  mov     [rbp+360h+var_10], rax
0x18000fcbf  mov     rdi, rcx
0x18000fcc2  mov     ebx, 3D0h
0x18000fcc7  mov     r8d, ebx; Size
0x18000fcca  xor     edx, edx; Val
0x18000fccc  lea     rcx, [rbp+360h+var_3E0]; void *
0x18000fcd0  call    memset_0
0x18000fcd5  lea     rcx, [rsp+460h+var_408]; void *
0x18000fcda  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000fcdf  nop
0x18000fce0  lea     rcx, [rsp+460h+var_428]; void *
0x18000fce5  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000fcea  nop
0x18000fceb  mov     qword ptr [rsp+460h+var_430], 0
0x18000fcf4  mov     [rbp+360h+var_3E0.cbSize], ebx
0x18000fcf7  mov     [rbp+360h+var_3E0.hWnd], 0
0x18000fcff  mov     [rbp+360h+var_3E0.uID], 0
0x18000fd06  call    IsLoadIconWPresent
0x18000fd0b  test    al, al
0x18000fd0d  jz      short loc_18000FD27
0x18000fd0f  mov     edx, 194h; lpIconName
0x18000fd14  lea     rcx, __ImageBase; hInstance
0x18000fd1b  call    cs:__imp_LoadIconW
0x18000fd21  mov     [rbp+360h+var_3E0.hIcon], rax
0x18000fd25  jmp     short loc_18000FD2F
0x18000fd27  mov     [rbp+360h+var_3E0.hIcon], 0
0x18000fd2f  mov     [rbp+360h+var_3E0.uFlags], 16h
0x18000fd36  mov     dword ptr [rbp+360h+var_3E0.330h], 0
0x18000fd40  mov     [rbp+360h+var_3E0.dwInfoFlags], 4
0x18000fd4a  mov     r9d, 40h ; '@'; cchBufferMax
0x18000fd50  lea     r8, [rbp+360h+var_3E0.szInfoTitle]; lpBuffer
0x18000fd57  mov     edx, 13CFh; uID
0x18000fd5c  lea     rcx, __ImageBase; hInstance
0x18000fd63  call    cs:__imp_LoadStringW
0x18000fd69  test    eax, eax
0x18000fd6b  jnz     short loc_18000FDBA
0x18000fd6d  call    cs:__imp_GetLastError
0x18000fd73  mov     ecx, eax; unsigned int
0x18000fd75  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000fd7a  mov     ebx, eax
0x18000fd7c  lea     rax, WPP_GLOBAL_Control
0x18000fd83  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd8a  cmp     rcx, rax
0x18000fd8d  jz      loc_18000FEFB
0x18000fd93  test    byte ptr [rcx+1Ch], 1
0x18000fd97  jz      loc_18000FEFB
0x18000fd9d  mov     edx, 0Ah
0x18000fda2  mov     r9d, ebx
0x18000fda5  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x18000fdac  mov     rcx, [rcx+10h]
0x18000fdb0  call    WPP_SF_d
0x18000fdb5  jmp     loc_18000FEFB
0x18000fdba  lea     r8, [rbp+360h+var_3E0.szInfoTitle]; unsigned __int16 *
0x18000fdc1  mov     edx, 80h; unsigned __int64
0x18000fdc6  lea     rcx, [rbp+360h+var_3E0.szTip]; unsigned __int16 *
0x18000fdca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fdcf  mov     eax, [rdi]
0x18000fdd1  lea     rcx, [rsp+460h+var_428]
0x18000fdd6  cmp     [rdi+4], eax
0x18000fdd9  jnz     short loc_18000FE08
0x18000fddb  mov     edx, 13D0h
0x18000fde0  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x18000fde5  mov     ebx, eax
0x18000fde7  test    eax, eax
0x18000fde9  js      loc_18000FECC
0x18000fdef  mov     r9d, [rdi+4]
0x18000fdf3  mov     r8, [rdi+60h]
0x18000fdf7  mov     rdx, [rsp+460h+var_428]
0x18000fdfc  lea     rcx, [rsp+460h+var_408]
0x18000fe01  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x18000fe06  jmp     short loc_18000FE42
0x18000fe08  mov     edx, 13D1h
0x18000fe0d  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x18000fe12  mov     ebx, eax
0x18000fe14  test    eax, eax
0x18000fe16  js      loc_18000FECC
0x18000fe1c  mov     eax, [rdi]
0x18000fe1e  mov     [rsp+460h+var_438], eax
0x18000fe22  mov     rax, [rdi+68h]
0x18000fe26  mov     [rsp+460h+var_440], rax; void *
0x18000fe2b  mov     r9d, [rdi+4]
0x18000fe2f  mov     r8, [rdi+60h]
0x18000fe33  mov     rdx, [rsp+460h+var_428]
0x18000fe38  lea     rcx, [rsp+460h+var_408]
0x18000fe3d  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x18000fe42  mov     ebx, eax
0x18000fe44  test    eax, eax
0x18000fe46  js      loc_18000FECC
0x18000fe4c  mov     r8, [rsp+460h+var_408]; unsigned __int16 *
0x18000fe51  mov     edx, 100h; unsigned __int64
0x18000fe56  lea     rcx, [rbp+360h+var_3E0.szInfo]; unsigned __int16 *
0x18000fe5d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fe62  lea     rcx, [rdi+370h]; this
0x18000fe69  lea     r8, [rbp+360h+var_3E0]; struct _NOTIFYICONDATAW *
0x18000fe6d  call    ?Create@CShellNotification@@QEAAJPEAUHINSTANCE__@@PEAU_NOTIFYICONDATAW@@P6A_JPEAUHWND__@@I_K_JPEAX@Z5@Z; CShellNotification::Create(HINSTANCE__ *,_NOTIFYICONDATAW *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64,void *),void *)
0x18000fe72  mov     ebx, eax
0x18000fe74  test    eax, eax
0x18000fe76  jns     short loc_18000FE9B
0x18000fe78  lea     rax, WPP_GLOBAL_Control
0x18000fe7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe86  cmp     rcx, rax
0x18000fe89  jz      short loc_18000FEFB
0x18000fe8b  test    byte ptr [rcx+1Ch], 4
0x18000fe8f  jz      short loc_18000FEFB
0x18000fe91  mov     edx, 0Ch
0x18000fe96  jmp     loc_18000FDA2
0x18000fe9b  mov     rax, [rbp+360h+var_3E0.hWnd]
0x18000fe9f  mov     qword ptr [rsp+460h+var_430], rax
0x18000fea4  lea     rcx, [rdi+368h]; this
0x18000feab  mov     dword ptr [rsp+460h+var_440], 0Bh; unsigned int
0x18000feb3  mov     r9d, 8; unsigned int
0x18000feb9  lea     r8, [rsp+460h+var_430]; unsigned __int8 *
0x18000febe  lea     rdx, aShellnotificat; "ShellNotificationHandle"
0x18000fec5  call    ?WriteTestHookToRegistry@CSilentProcessExitTestAutomation@@QEAAXPEBGPEAEKK@Z; CSilentProcessExitTestAutomation::WriteTestHookToRegistry(ushort const *,uchar *,ulong,ulong)
0x18000feca  jmp     short loc_18000FEFB
0x18000fecc  lea     rax, WPP_GLOBAL_Control
0x18000fed3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000feda  cmp     rcx, rax
0x18000fedd  jz      short loc_18000FEFB
0x18000fedf  test    byte ptr [rcx+1Ch], 1
0x18000fee3  jz      short loc_18000FEFB
0x18000fee5  mov     edx, 0Bh
0x18000feea  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x18000fef1  mov     rcx, [rcx+10h]
0x18000fef5  call    WPP_SF_
0x18000fefa  nop
0x18000fefb  lea     rcx, [rsp+460h+var_428]
0x18000ff00  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000ff05  nop
0x18000ff06  lea     rcx, [rsp+460h+var_408]
0x18000ff0b  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000ff10  mov     eax, ebx
0x18000ff12  mov     rcx, [rbp+360h+var_10]
0x18000ff19  xor     rcx, rsp; StackCookie
0x18000ff1c  call    __security_check_cookie
0x18000ff21  lea     r11, [rsp+460h+var_s0]
0x18000ff29  mov     rbx, [r11+18h]
0x18000ff2d  mov     rdi, [r11+20h]
0x18000ff31  mov     rsp, r11
0x18000ff34  pop     rbp
0x18000ff35  retn
```
