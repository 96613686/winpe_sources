# CThemeManager2::_s_UpdateColorSettingForLogonUIWorkItem(void *)

- ea: `0x18001d990`
- end: `0x18001dc93`
- name: `?_s_UpdateColorSettingForLogonUIWorkItem@CThemeManager2@@CAKPEAX@Z`
- size: `771`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001d990`
- `0x18001dc9c`
- `0x18001de18`
- `0x18001dfc4`
- `0x18002fe3c`
- `0x18002fed4`
- `0x1800304b8`
- `0x180030520`
- `0x1800307fc`
- `0x180033da8`
- `0x1800358c0`
- `0x180053524`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001dc32`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001dc32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001db5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001db5e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001da8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001db14`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001da8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001db14`
- `USER32!GetSysColor` at `0x18001db31`
- `USER32!GetSysColor` at `0x18001dbeb`
- `USER32!GetSysColor` at `0x18001db31`
- `USER32!GetSysColor` at `0x18001dbeb`
- `USER32!SystemParametersInfoW` at `0x18001da19`
- `USER32!SystemParametersInfoW` at `0x18001da19`
- `ext-ms-win-com-sta-l1-1-0!CoInitialize` at `0x18001d9e0`
- `ext-ms-win-com-sta-l1-1-0!CoInitialize` at `0x18001d9e0`

## string_xrefs

- `0x18001d9b9`: `UpdateColorSettingsForLogonUIWorkItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CThemeManager2::_s_UpdateColorSettingForLogonUIWorkItem(void *a1)
{
  unsigned int v1; // esi
  const unsigned __int16 *v2; // rcx
  int v3; // edi
  LSTATUS ValueW; // eax
  signed int v5; // ebx
  bool v6; // al
  unsigned int v7; // r15d
  bool v8; // r14
  LSTATUS v9; // eax
  DWORD SysColor; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int i; // edi
  DWORD v14; // eax
  bool v16[8]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  char v20; // [rsp+61h] [rbp-9Fh]
  int pvParam; // [rsp+68h] [rbp-98h] BYREF
  __int64 v22; // [rsp+6Ch] [rbp-94h]
  int v23; // [rsp+74h] [rbp-8Ch]
  void **v24; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[272]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v26[8]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v27[48]; // [rsp+1A0h] [rbp+A0h] BYREF

  wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v24);
  v24 = &ThemesTelemetry::UpdateColorSettingsForLogonUIWorkItem::`vftable';
  ThemesTelemetry::UpdateColorSettingsForLogonUIWorkItem::StartActivity((ThemesTelemetry::UpdateColorSettingsForLogonUIWorkItem *)&v24);
  if ( CoInitialize(0) >= 0 )
  {
    v20 = 1;
    v16[0] = 0;
    v1 = 0;
    pvParam = 16;
    v22 = 0;
    v23 = 0;
    if ( SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) )
      v1 = v22 & 1;
    hkey = 0;
    v3 = OpenSystemDataRegistryPathForCurrentUser(v2, &hkey);
    pcbData[0] = v3;
    if ( v3 < 0 )
    {
      v8 = 0;
    }
    else
    {
      pvData = 0;
      pcbData[0] = 4;
      ValueW = RegGetValueW(hkey, 0, L"HighContrastEnabled", 0x10u, 0, &pvData, pcbData);
      v5 = ValueW;
      if ( ValueW > 0 )
        v5 = (unsigned __int16)ValueW | 0x80070000;
      pcbData[0] = v5;
      v6 = pvData != v1;
      v16[0] = pvData != v1;
      if ( v5 < 0 )
      {
        v8 = pvData != v1;
        v3 = v5;
      }
      else
      {
        v7 = 0;
        do
        {
          v3 = v5;
          v8 = v6;
          if ( v6 || v7 >= 0xD )
            break;
          pcbData[0] = 4;
          v9 = RegGetValueW(hkey, 0, (LPCWSTR)qword_18006EB80[2 * (int)v7 + 1], 0x10u, 0, &pvData, pcbData);
          v5 = v9;
          if ( v9 > 0 )
            v5 = (unsigned __int16)v9 | 0x80070000;
          pcbData[0] = v5;
          SysColor = GetSysColor(qword_18006EB80[2 * (int)v7]);
          v6 = pvData != SysColor;
          v16[0] = v6;
          ++v7;
          v3 = v5;
          v8 = v6;
        }
        while ( v5 >= 0 );
      }
      RegCloseKey(hkey);
    }
    ThemesTelemetry::UpdateColorSettingsForLogonUIWorkItem::UserSystemDataColorsResult<bool &,long &>(
      &v24,
      v16,
      pcbData);
    if ( v3 < 0 || v8 )
    {
      *(_QWORD *)pcbData = 0;
      if ( (int)CoCreateInstanceAsSystem(v12, v11, pcbData) >= 0 )
      {
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const WCHAR *, _QWORD, int))(**(_QWORD **)pcbData + 48LL))(
          *(_QWORD *)pcbData,
          L"Colors",
          L"HighContrastEnabled",
          v1,
          1);
        if ( v1 )
        {
          for ( i = 0; i < 0xD; ++i )
          {
            v14 = GetSysColor(qword_18006EB80[2 * (int)i]);
            (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, _QWORD, int))(**(_QWORD **)pcbData + 48LL))(
              *(_QWORD *)pcbData,
              L"Colors",
              qword_18006EB80[2 * (int)i + 1],
              v14,
              1);
          }
        }
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 16LL))(*(_QWORD *)pcbData);
      }
    }
    CoUninitialize();
  }
  wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v24, 0);
  v24 = &ThemesTelemetry::UpdateColorSettingsForLogonUIWorkItem::`vftable';
  wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v24);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v27);
  wil::details::shared_object<wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThemesLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v26);
  wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThemesLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThemesLogging,_TlgReflectorTag_Param0IsProviderType>(v25);
  return 0;
}

```

## disassembly

```asm
0x18001d990  push    rbp
0x18001d992  push    rbx
0x18001d993  push    rsi
0x18001d994  push    rdi
0x18001d995  push    r14
0x18001d997  push    r15
0x18001d999  lea     rbp, [rsp-0E8h]
0x18001d9a1  sub     rsp, 1E8h
0x18001d9a8  mov     rax, cs:__security_cookie
0x18001d9af  xor     rax, rsp
0x18001d9b2  mov     [rbp+110h+var_40], rax
0x18001d9b9  lea     rdx, aUpdatecolorset; "UpdateColorSettingsForLogonUIWorkItem"
0x18001d9c0  lea     rcx, [rbp+110h+var_190]; struct wil::details::IFailureCallback *
0x18001d9c4  call    ??0?$ActivityBase@VThemesLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001d9c9  lea     r15, ??_7UpdateColorSettingsForLogonUIWorkItem@ThemesTelemetry@@6B@; const ThemesTelemetry::UpdateColorSettingsForLogonUIWorkItem::`vftable'
0x18001d9d0  mov     [rbp+110h+var_190], r15
0x18001d9d4  lea     rcx, [rbp+110h+var_190]; this
0x18001d9d8  call    ?StartActivity@UpdateColorSettingsForLogonUIWorkItem@ThemesTelemetry@@QEAAXXZ; ThemesTelemetry::UpdateColorSettingsForLogonUIWorkItem::StartActivity(void)
0x18001d9dd  nop
0x18001d9de  xor     ecx, ecx; pvReserved
0x18001d9e0  call    cs:__imp_CoInitialize
0x18001d9e6  test    eax, eax
0x18001d9e8  js      loc_18001DC38
0x18001d9ee  mov     [rsp+210h+var_1AF], 1
0x18001d9f3  mov     [rsp+210h+var_1D0], 0
0x18001d9f8  xor     esi, esi
0x18001d9fa  lea     ebx, [rsi+10h]
0x18001d9fd  mov     [rsp+210h+pvParam], ebx
0x18001da01  xor     eax, eax
0x18001da03  mov     [rsp+210h+var_1A4], rax
0x18001da08  mov     [rsp+210h+var_19C], eax
0x18001da0c  xor     r9d, r9d; fWinIni
0x18001da0f  lea     r8, [rsp+210h+pvParam]; pvParam
0x18001da14  mov     edx, ebx; uiParam
0x18001da16  lea     ecx, [rsi+42h]; uiAction
0x18001da19  call    cs:__imp_SystemParametersInfoW
0x18001da1f  test    eax, eax
0x18001da21  jz      short loc_18001DA2B
0x18001da23  movzx   esi, byte ptr [rsp+210h+var_1A4]
0x18001da28  and     esi, 1
0x18001da2b  mov     [rsp+210h+hkey], 0
0x18001da34  lea     rdx, [rsp+210h+hkey]; HKEY *
0x18001da39  call    ?OpenSystemDataRegistryPathForCurrentUser@@YAJPEBGPEAPEAUHKEY__@@@Z; OpenSystemDataRegistryPathForCurrentUser(ushort const *,HKEY__ * *)
0x18001da3e  mov     edi, eax
0x18001da40  mov     [rsp+210h+var_1C8], eax
0x18001da44  test    eax, eax
0x18001da46  js      loc_18001DB6D
0x18001da4c  mov     [rsp+210h+var_1C0], 0
0x18001da54  mov     [rsp+210h+var_1C8], 4
0x18001da5c  lea     rax, [rsp+210h+var_1C8]
0x18001da61  mov     [rsp+210h+pcbData], rax; pcbData
0x18001da66  lea     rax, [rsp+210h+var_1C0]
0x18001da6b  mov     [rsp+210h+pvData], rax; pvData
0x18001da70  mov     [rsp+210h+pdwType], 0; pdwType
0x18001da79  mov     r9d, ebx; dwFlags
0x18001da7c  lea     r8, aHighcontrasten; "HighContrastEnabled"
0x18001da83  xor     edx, edx; lpSubKey
0x18001da85  mov     rcx, [rsp+210h+hkey]; hkey
0x18001da8a  call    cs:__imp_RegGetValueW
0x18001da90  mov     ebx, eax
0x18001da92  test    eax, eax
0x18001da94  jle     short loc_18001DA9F
0x18001da96  movzx   ebx, ax
0x18001da99  or      ebx, 80070000h
0x18001da9f  mov     [rsp+210h+var_1C8], ebx
0x18001daa3  cmp     [rsp+210h+var_1C0], esi
0x18001daa7  setnz   al
0x18001daaa  mov     [rsp+210h+var_1D0], al
0x18001daae  test    ebx, ebx
0x18001dab0  js      loc_18001DB66
0x18001dab6  xor     r15d, r15d
0x18001dab9  mov     edi, ebx
0x18001dabb  mov     r14b, al
0x18001dabe  test    al, al
0x18001dac0  jnz     loc_18001DB52
0x18001dac6  cmp     r15d, 0Dh
0x18001daca  jnb     loc_18001DB52
0x18001dad0  movsxd  rdi, r15d
0x18001dad3  add     rdi, rdi
0x18001dad6  mov     [rsp+210h+var_1C8], 4
0x18001dade  lea     rax, [rsp+210h+var_1C8]
0x18001dae3  mov     [rsp+210h+pcbData], rax; pcbData
0x18001dae8  lea     rax, [rsp+210h+var_1C0]
0x18001daed  mov     [rsp+210h+pvData], rax; pvData
0x18001daf2  mov     [rsp+210h+pdwType], 0; pdwType
0x18001dafb  mov     r9d, 10h; dwFlags
0x18001db01  lea     r14, qword_18006EB80
0x18001db08  mov     r8, [r14+rdi*8+8]; lpValue
0x18001db0d  xor     edx, edx; lpSubKey
0x18001db0f  mov     rcx, [rsp+210h+hkey]; hkey
0x18001db14  call    cs:__imp_RegGetValueW
0x18001db1a  mov     ebx, eax
0x18001db1c  test    eax, eax
0x18001db1e  jle     short loc_18001DB29
0x18001db20  movzx   ebx, ax
0x18001db23  or      ebx, 80070000h
0x18001db29  mov     [rsp+210h+var_1C8], ebx
0x18001db2d  mov     ecx, [r14+rdi*8]; nIndex
0x18001db31  call    cs:__imp_GetSysColor
0x18001db37  cmp     [rsp+210h+var_1C0], eax
0x18001db3b  setnz   al
0x18001db3e  mov     [rsp+210h+var_1D0], al
0x18001db42  inc     r15d
0x18001db45  mov     edi, ebx
0x18001db47  mov     r14b, al
0x18001db4a  test    ebx, ebx
0x18001db4c  jns     loc_18001DAB9
0x18001db52  lea     r15, ??_7UpdateColorSettingsForLogonUIWorkItem@ThemesTelemetry@@6B@; const ThemesTelemetry::UpdateColorSettingsForLogonUIWorkItem::`vftable'
0x18001db59  mov     rcx, [rsp+210h+hkey]; hKey
0x18001db5e  call    cs:__imp_RegCloseKey
0x18001db64  jmp     short loc_18001DB70
0x18001db66  mov     r14b, al
0x18001db69  mov     edi, ebx
0x18001db6b  jmp     short loc_18001DB59
0x18001db6d  xor     r14b, r14b
0x18001db70  lea     r8, [rsp+210h+var_1C8]
0x18001db75  lea     rdx, [rsp+210h+var_1D0]
0x18001db7a  lea     rcx, [rbp+110h+var_190]
0x18001db7e  call    ??$UserSystemDataColorsResult@AEA_NAEAJ@UpdateColorSettingsForLogonUIWorkItem@ThemesTelemetry@@QEAAXAEA_NAEAJ@Z; ThemesTelemetry::UpdateColorSettingsForLogonUIWorkItem::UserSystemDataColorsResult<bool &,long &>(bool &,long &)
0x18001db83  test    edi, edi
0x18001db85  js      short loc_18001DB90
0x18001db87  test    r14b, r14b
0x18001db8a  jz      loc_18001DC32
0x18001db90  mov     qword ptr [rsp+210h+var_1C8], 0
0x18001db99  lea     r8, [rsp+210h+var_1C8]
0x18001db9e  call    CoCreateInstanceAsSystem
0x18001dba3  test    eax, eax
0x18001dba5  js      loc_18001DC32
0x18001dbab  mov     rcx, qword ptr [rsp+210h+var_1C8]
0x18001dbb0  mov     rax, [rcx]
0x18001dbb3  mov     dword ptr [rsp+210h+pdwType], 1
0x18001dbbb  mov     r9d, esi
0x18001dbbe  lea     r8, aHighcontrasten; "HighContrastEnabled"
0x18001dbc5  lea     rdx, aColors; "Colors"
0x18001dbcc  mov     rax, [rax+30h]
0x18001dbd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbd5  test    esi, esi
0x18001dbd7  jz      short loc_18001DC20
0x18001dbd9  xor     edi, edi
0x18001dbdb  lea     rsi, qword_18006EB80
0x18001dbe2  movsxd  rbx, edi
0x18001dbe5  add     rbx, rbx
0x18001dbe8  mov     ecx, [rsi+rbx*8]; nIndex
0x18001dbeb  call    cs:__imp_GetSysColor
0x18001dbf1  mov     r9d, eax
0x18001dbf4  mov     rcx, qword ptr [rsp+210h+var_1C8]
0x18001dbf9  mov     rdx, [rcx]
0x18001dbfc  mov     rax, [rdx+30h]
0x18001dc00  mov     dword ptr [rsp+210h+pdwType], 1
0x18001dc08  mov     r8, [rsi+rbx*8+8]
0x18001dc0d  lea     rdx, aColors; "Colors"
0x18001dc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc19  inc     edi
0x18001dc1b  cmp     edi, 0Dh
0x18001dc1e  jb      short loc_18001DBE2
0x18001dc20  mov     rcx, qword ptr [rsp+210h+var_1C8]
0x18001dc25  mov     rax, [rcx]
0x18001dc28  mov     rax, [rax+10h]
0x18001dc2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc31  nop
0x18001dc32  call    cs:__imp_CoUninitialize
0x18001dc38  xor     edx, edx
0x18001dc3a  lea     rcx, [rbp+110h+var_190]
0x18001dc3e  call    ?Stop@?$ActivityBase@VThemesLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001dc43  nop
0x18001dc44  mov     [rbp+110h+var_190], r15
0x18001dc48  lea     rcx, [rbp+110h+var_190]
0x18001dc4c  call    ?Destroy@?$ActivityBase@VThemesLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001dc51  lea     rcx, [rbp+110h+var_70]; this
0x18001dc58  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001dc5d  lea     rcx, [rbp+110h+var_78]
0x18001dc64  call    ?reset@?$shared_object@V?$ActivityData@VThemesLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThemesLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThemesLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001dc69  lea     rcx, [rbp+110h+var_188]
0x18001dc6d  call    ??1?$ActivityData@VThemesLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThemesLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThemesLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThemesLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001dc72  xor     eax, eax
0x18001dc74  mov     rcx, [rbp+110h+var_40]
0x18001dc7b  xor     rcx, rsp; StackCookie
0x18001dc7e  call    __security_check_cookie
0x18001dc83  add     rsp, 1E8h
0x18001dc8a  pop     r15
0x18001dc8c  pop     r14
0x18001dc8e  pop     rdi
0x18001dc8f  pop     rsi
0x18001dc90  pop     rbx
0x18001dc91  pop     rbp
0x18001dc92  retn
```
