# RADC::ShowMstscUninstalledWarningDialogIfNecessary(HWND__ *)

- ea: `0x180078e38`
- end: `0x18007919a`
- name: `?ShowMstscUninstalledWarningDialogIfNecessary@RADC@@YAXPEAUHWND__@@@Z`
- size: `866`
- prototype: `void __fastcall(RADC *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180022c78`

## callees

- `0x1800044bf`
- `0x18000b1d8`
- `0x18000ece0`
- `0x1800776d0`
- `0x18007774c`
- `0x180077770`
- `0x18007789c`
- `0x180078420`
- `0x180078e38`
- `0x180079b68`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x18007909b`
- `ADVAPI32!RegOpenKeyW` at `0x18007909b`
- `ADVAPI32!RegGetValueW` at `0x180078ebb`
- `ADVAPI32!RegGetValueW` at `0x180078ebb`
- `ADVAPI32!RegSetValueExW` at `0x180079111`
- `ADVAPI32!RegSetValueExW` at `0x180079111`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180078f70`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180078f70`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180078f91`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180078f91`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x180079006`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x180079006`

## string_xrefs

- `0x180078ea6`: `DisableMstscUninstalledDialog`
- `0x180079105`: `DisableMstscUninstalledDialog`
- `0x180078f69`: `radcui.dll`
- `0x1800790e2`: `RegOpenKeyW failed`
- `0x180079042`: `TaskDialogIndirect failed`
- `0x18007914c`: `RegSetValueExW failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall RADC::ShowMstscUninstalledWarningDialogIfNecessary(RADC *this, HWND a2)
{
  LSTATUS ValueW; // eax
  unsigned int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HMODULE Library; // rbx
  HRESULT v7; // ebx
  unsigned int v8; // eax
  HKEY *v9; // rax
  LSTATUS v10; // eax
  signed int v11; // ebx
  unsigned int v12; // eax
  int v13; // edx
  const char *v14; // rcx
  LSTATUS v15; // eax
  PVOID pvData; // [rsp+28h] [rbp-A1h]
  HKEY hKey; // [rsp+40h] [rbp-89h] BYREF
  HMODULE hLibModule[3]; // [rsp+48h] [rbp-81h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+60h] [rbp-69h] BYREF
  int Data; // [rsp+138h] [rbp+6Fh] BYREF
  BOOL pfVerificationFlagChecked; // [rsp+140h] [rbp+77h] BYREF
  DWORD pcbData; // [rsp+148h] [rbp+7Fh] BYREF

  hLibModule[1] = (HMODULE)-2LL;
  hLibModule[0] = 0;
  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  pfVerificationFlagChecked = 0;
  Data = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Workspaces",
             L"DisableMstscUninstalledDialog",
             0x18u,
             0,
             &Data,
             &pcbData);
  v4 = ValueW;
  if ( ValueW > 0 )
    v4 = (unsigned __int16)ValueW | 0x80070000;
  if ( (int)(v4 + 0x80000000) >= 0
    && v4 != -2147024894
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(pvData) = v4;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      (unsigned int)WPP_8f87464425bd38a0257d033d5861bd18_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"RegGetValueW failed",
      pvData);
  }
  if ( !Data )
  {
    if ( (unsigned __int8)RADC::_anonymous_namespace_::IsMstscUninstalled() )
    {
      if ( !_InterlockedExchange(&dword_1800EF71C, 1) )
      {
        Library = LoadLibraryExW(L"radcui.dll", 0, 0x860u);
        hLibModule[0] = Library;
        if ( Library )
        {
          pTaskConfig.cbSize = 160;
          pTaskConfig.hwndParent = (HWND)this;
          pTaskConfig.hInstance = Library;
          pTaskConfig.dwFlags = 16777217;
          pTaskConfig.pszWindowTitle = (PCWSTR)15357;
          pTaskConfig.pszContent = (PCWSTR)15358;
          pTaskConfig.pszVerificationText = (PCWSTR)15359;
          pTaskConfig.dwCommonButtons = 1;
          pTaskConfig.hMainIcon = (HICON)0xFFFF;
          pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)RADC::_anonymous_namespace_::TaskDialogWithHyperlinksCallback;
          v7 = TaskDialogIndirect(&pTaskConfig, 0, 0, &pfVerificationFlagChecked);
          if ( v7 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v8 = RdpWppGetCurrentThreadActivityIdPrefix();
              LODWORD(pvData) = v7;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                49,
                (unsigned int)WPP_8f87464425bd38a0257d033d5861bd18_Traceguids,
                v8,
                (__int64)"TaskDialogIndirect failed",
                pvData);
            }
            goto LABEL_35;
          }
          if ( !pfVerificationFlagChecked )
            goto LABEL_35;
          hKey = 0;
          v9 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
          v10 = RegOpenKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Workspaces", v9);
          v11 = v10;
          if ( v10 > 0 )
            v11 = (unsigned __int16)v10 | 0x80070000;
          if ( v11 >= 0 )
          {
            Data = 1;
            v15 = RegSetValueExW(hKey, L"DisableMstscUninstalledDialog", 0, 4u, (const BYTE *)&Data, 4u);
            v11 = v15;
            if ( v15 > 0 )
              v11 = (unsigned __int16)v15 | 0x80070000;
            if ( v11 >= 0
              || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_34;
            }
            v12 = RdpWppGetCurrentThreadActivityIdPrefix();
            v13 = 51;
            v14 = "RegSetValueExW failed";
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_34;
            }
            v12 = RdpWppGetCurrentThreadActivityIdPrefix();
            v13 = 50;
            v14 = "RegOpenKeyW failed";
          }
          LODWORD(pvData) = v11;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v13,
            (unsigned int)WPP_8f87464425bd38a0257d033d5861bd18_Traceguids,
            v12,
            (__int64)v14,
            pvData);
LABEL_34:
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(&hKey);
        }
      }
    }
  }
LABEL_35:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>(hLibModule);
}

```

## disassembly

```asm
0x180078e38  push    rbp
0x180078e3a  push    rbx
0x180078e3b  push    rsi
0x180078e3c  push    rdi
0x180078e3d  push    r13
0x180078e3f  lea     rbp, [rsp-37h]
0x180078e44  sub     rsp, 100h
0x180078e4b  mov     [rbp+57h+var_D0], 0FFFFFFFFFFFFFFFEh
0x180078e53  mov     rsi, rcx
0x180078e56  mov     [rsp+120h+hLibModule], 0
0x180078e5f  xor     edx, edx; Val
0x180078e61  mov     r8d, 0A0h; Size
0x180078e67  lea     rcx, [rbp+57h+pTaskConfig]; void *
0x180078e6b  call    memset_0
0x180078e70  mov     [rbp+57h+pfVerificationFlagChecked], 0
0x180078e77  mov     [rbp+57h+Data], 0
0x180078e7e  mov     [rbp+57h+arg_18], 4
0x180078e85  lea     rax, [rbp+57h+arg_18]
0x180078e89  mov     [rsp+120h+pcbData], rax; pcbData
0x180078e8e  lea     rax, [rbp+57h+Data]
0x180078e92  mov     [rsp+120h+pvData], rax; pvData
0x180078e97  mov     [rsp+120h+pdwType], 0; pdwType
0x180078ea0  mov     r9d, 18h; dwFlags
0x180078ea6  lea     r8, aDisablemstscun; "DisableMstscUninstalledDialog"
0x180078ead  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Workspaces"
0x180078eb4  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180078ebb  call    cs:__imp_RegGetValueW
0x180078ec1  mov     ebx, eax
0x180078ec3  test    eax, eax
0x180078ec5  jle     short loc_180078ED0
0x180078ec7  movzx   ebx, ax
0x180078eca  or      ebx, 80070000h
0x180078ed0  mov     ecx, 80000000h
0x180078ed5  lea     eax, [rbx+rcx]
0x180078ed8  lea     r13, WPP_GLOBAL_Control
0x180078edf  test    ecx, eax
0x180078ee1  jnz     short loc_180078F37
0x180078ee3  cmp     ebx, 80070002h
0x180078ee9  jz      short loc_180078F37
0x180078eeb  mov     rax, cs:WPP_GLOBAL_Control
0x180078ef2  cmp     rax, r13
0x180078ef5  jz      short loc_180078F37
0x180078ef7  test    byte ptr [rax+1Ch], 8
0x180078efb  jz      short loc_180078F37
0x180078efd  cmp     byte ptr [rax+19h], 2
0x180078f01  jb      short loc_180078F37
0x180078f03  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078f08  mov     edx, 30h ; '0'
0x180078f0d  mov     dword ptr [rsp+120h+pvData], ebx
0x180078f11  lea     rcx, aReggetvaluewFa; "RegGetValueW failed"
0x180078f18  mov     [rsp+120h+pdwType], rcx
0x180078f1d  mov     r9d, eax
0x180078f20  lea     r8, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids
0x180078f27  mov     rcx, cs:WPP_GLOBAL_Control
0x180078f2e  mov     rcx, [rcx+10h]
0x180078f32  call    WPP_SF_DsD
0x180078f37  cmp     [rbp+57h+Data], 0
0x180078f3b  jnz     loc_180079182
0x180078f41  call    RADC___anonymous_namespace___IsMstscUninstalled
0x180078f46  test    al, al
0x180078f48  jz      loc_180079182
0x180078f4e  mov     eax, 1
0x180078f53  xchg    eax, cs:dword_1800EF71C
0x180078f59  test    eax, eax
0x180078f5b  jnz     loc_180079182
0x180078f61  xor     edx, edx; hFile
0x180078f63  mov     r8d, 860h; dwFlags
0x180078f69  lea     rcx, aRadcuiDll; "radcui.dll"
0x180078f70  call    cs:__imp_LoadLibraryExW
0x180078f76  mov     rbx, rax
0x180078f79  mov     rdi, [rsp+120h+hLibModule]
0x180078f7e  test    rdi, rdi
0x180078f81  jz      short loc_180078FA2
0x180078f83  lea     rcx, [rsp+120h+hKey]; this
0x180078f88  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180078f8d  nop
0x180078f8e  mov     rcx, rdi; hLibModule
0x180078f91  call    cs:__imp_FreeLibrary
0x180078f97  nop
0x180078f98  lea     rcx, [rsp+120h+hKey]; this
0x180078f9d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180078fa2  mov     [rsp+120h+hLibModule], rbx
0x180078fa7  test    rbx, rbx
0x180078faa  jz      loc_180079182
0x180078fb0  mov     [rbp+57h+pTaskConfig.cbSize], 0A0h
0x180078fb7  mov     [rbp+57h+pTaskConfig.hwndParent], rsi
0x180078fbb  mov     [rbp+57h+pTaskConfig.hInstance], rbx
0x180078fbf  mov     [rbp+57h+pTaskConfig.dwFlags], 1000001h
0x180078fc6  mov     [rbp+57h+pTaskConfig.pszWindowTitle], 3BFDh
0x180078fce  mov     [rbp+57h+pTaskConfig.pszContent], 3BFEh
0x180078fd6  mov     [rbp+57h+pTaskConfig.pszVerificationText], 3BFFh
0x180078fde  mov     edi, 1
0x180078fe3  mov     [rbp+57h+pTaskConfig.dwCommonButtons], edi
0x180078fe6  mov     qword ptr [rbp+57h+pTaskConfig.24h], 0FFFFh
0x180078fee  lea     rax, RADC___anonymous_namespace___TaskDialogWithHyperlinksCallback
0x180078ff5  mov     [rbp+57h+pTaskConfig.pfCallback], rax
0x180078ff9  lea     r9, [rbp+57h+pfVerificationFlagChecked]; pfVerificationFlagChecked
0x180078ffd  xor     r8d, r8d; pnRadioButton
0x180079000  xor     edx, edx; pnButton
0x180079002  lea     rcx, [rbp+57h+pTaskConfig]; pTaskConfig
0x180079006  call    cs:__imp_TaskDialogIndirect
0x18007900c  mov     ebx, eax
0x18007900e  test    eax, eax
0x180079010  jns     short loc_18007906D
0x180079012  mov     rcx, cs:WPP_GLOBAL_Control
0x180079019  cmp     rcx, r13
0x18007901c  jz      loc_180079182
0x180079022  test    byte ptr [rcx+1Ch], 8
0x180079026  jz      loc_180079182
0x18007902c  cmp     byte ptr [rcx+19h], 2
0x180079030  jb      loc_180079182
0x180079036  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007903b  lea     edx, [rdi+30h]
0x18007903e  mov     dword ptr [rsp+120h+pvData], ebx
0x180079042  lea     rcx, aTaskdialogindi; "TaskDialogIndirect failed"
0x180079049  mov     [rsp+120h+pdwType], rcx
0x18007904e  mov     r9d, eax
0x180079051  lea     r8, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids
0x180079058  mov     rcx, cs:WPP_GLOBAL_Control
0x18007905f  mov     rcx, [rcx+10h]
0x180079063  call    WPP_SF_DsD
0x180079068  jmp     loc_180079182
0x18007906d  cmp     [rbp+57h+pfVerificationFlagChecked], 0
0x180079071  jz      loc_180079182
0x180079077  mov     [rsp+120h+hKey], 0
0x180079080  lea     rcx, [rsp+120h+hKey]
0x180079085  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18007908a  mov     r8, rax; phkResult
0x18007908d  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Workspaces"
0x180079094  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18007909b  call    cs:__imp_RegOpenKeyW
0x1800790a1  mov     ebx, eax
0x1800790a3  test    eax, eax
0x1800790a5  jle     short loc_1800790B0
0x1800790a7  movzx   ebx, ax
0x1800790aa  or      ebx, 80070000h
0x1800790b0  test    ebx, ebx
0x1800790b2  jns     short loc_1800790EB
0x1800790b4  mov     rax, cs:WPP_GLOBAL_Control
0x1800790bb  cmp     rax, r13
0x1800790be  jz      loc_180079177
0x1800790c4  test    byte ptr [rax+1Ch], 8
0x1800790c8  jz      loc_180079177
0x1800790ce  cmp     byte ptr [rax+19h], 2
0x1800790d2  jb      loc_180079177
0x1800790d8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800790dd  mov     edx, 32h ; '2'
0x1800790e2  lea     rcx, aRegopenkeywFai; "RegOpenKeyW failed"
0x1800790e9  jmp     short loc_180079153
0x1800790eb  mov     [rbp+57h+Data], edi
0x1800790ee  mov     r9d, 4; dwType
0x1800790f4  mov     dword ptr [rsp+120h+pvData], r9d; cbData
0x1800790f9  lea     rax, [rbp+57h+Data]
0x1800790fd  mov     [rsp+120h+pdwType], rax; lpData
0x180079102  xor     r8d, r8d; Reserved
0x180079105  lea     rdx, aDisablemstscun; "DisableMstscUninstalledDialog"
0x18007910c  mov     rcx, [rsp+120h+hKey]; hKey
0x180079111  call    cs:__imp_RegSetValueExW
0x180079117  mov     ebx, eax
0x180079119  test    eax, eax
0x18007911b  jle     short loc_180079126
0x18007911d  movzx   ebx, ax
0x180079120  or      ebx, 80070000h
0x180079126  test    ebx, ebx
0x180079128  jns     short loc_180079177
0x18007912a  mov     rax, cs:WPP_GLOBAL_Control
0x180079131  cmp     rax, r13
0x180079134  jz      short loc_180079177
0x180079136  test    byte ptr [rax+1Ch], 8
0x18007913a  jz      short loc_180079177
0x18007913c  cmp     byte ptr [rax+19h], 2
0x180079140  jb      short loc_180079177
0x180079142  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079147  mov     edx, 33h ; '3'
0x18007914c  lea     rcx, aRegsetvalueexw; "RegSetValueExW failed"
0x180079153  mov     dword ptr [rsp+120h+pvData], ebx
0x180079157  mov     [rsp+120h+pdwType], rcx
0x18007915c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079163  mov     r9d, eax
0x180079166  lea     r8, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids
0x18007916d  mov     rcx, [rcx+10h]
0x180079171  call    WPP_SF_DsD
0x180079176  nop
0x180079177  lea     rcx, [rsp+120h+hKey]
0x18007917c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x180079181  nop
0x180079182  lea     rcx, [rsp+120h+hLibModule]
0x180079187  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>(void)
0x18007918c  add     rsp, 100h
0x180079193  pop     r13
0x180079195  pop     rdi
0x180079196  pop     rsi
0x180079197  pop     rbx
0x180079198  pop     rbp
0x180079199  retn
```
