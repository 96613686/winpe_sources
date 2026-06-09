# CRemoteConnectionManager::UpdateWddmModeSettings(void)

- ea: `0x18004e8a4`
- end: `0x18004ea89`
- name: `?UpdateWddmModeSettings@CRemoteConnectionManager@@AEAAJXZ`
- size: `485`
- prototype: `__int64 __fastcall(CRemoteConnectionManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004aeb0`

## callees

- `0x180001284`
- `0x180001688`
- `0x180013bf0`
- `0x1800148f0`
- `0x1800279a8`
- `0x180027a04`
- `0x180027b44`
- `0x18004e8a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004e8fb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004e8fb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004e8e9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004e8e9`

## string_xrefs

- `0x18004e8e2`: `udwm.dll`
- `0x18004e9f2`: `ID for Remote sessions is disabled on SKUs that don't enable dwm composition`
- `0x18004e94d`: `UpdateWddmModeSettings`
- `0x18004e95b`: `regHandler.OpenKey`
- `0x18004e9c5`: `ID for Remote sessions state override registry key is present`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRemoteConnectionManager::UpdateWddmModeSettings(CRemoteConnectionManager *this)
{
  HMODULE Library; // rax
  signed int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  unsigned int *v6; // rbx
  int v7; // eax
  const unsigned __int16 *v9; // [rsp+20h] [rbp-58h]
  _QWORD v10[2]; // [rsp+40h] [rbp-38h] BYREF
  int v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+60h] [rbp-18h]
  int v14; // [rsp+64h] [rbp-14h]
  const char *v15; // [rsp+90h] [rbp+18h] BYREF
  const char *v16; // [rsp+98h] [rbp+20h] BYREF
  const char *v17; // [rsp+A0h] [rbp+28h] BYREF
  const char *v18; // [rsp+A8h] [rbp+30h] BYREF

  v10[0] = &CRegistry::`vftable';
  v10[1] = 0;
  v11 = 0;
  v12 = 0;
  v13 = -1;
  v14 = -1;
  Library = LoadLibraryExW(L"udwm.dll", 0, 2u);
  if ( Library )
  {
    FreeLibrary(Library);
    v6 = (unsigned int *)((char *)this + 2556);
    *v6 = 1;
    v7 = CRegistry::OpenKey(
           (CRegistry *)v10,
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
           0x20019u,
           v9);
    v3 = v7;
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    if ( v3 >= 0 )
    {
      if ( !CRegistry::ReadRegDWord((CRegistry *)v10, L"LoadWddmIddDriver", v6) && (unsigned int)dword_180128170 > 4 )
      {
        v15 = "ID for Remote sessions state override registry key is present";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v3,
          (unsigned int)byte_1801066B9,
          v4,
          v5,
          (__int64)&v15);
      }
    }
    else if ( (unsigned int)dword_180128170 > 3 )
    {
      v16 = "UpdateWddmModeSettings";
      LODWORD(v15) = v3;
      v17 = "regHandler.OpenKey";
      v18 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)byte_1801066E5,
        v4,
        v5,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v15,
        (__int64)&v16);
    }
  }
  else
  {
    if ( (unsigned int)dword_180128170 > 4 )
    {
      v15 = "ID for Remote sessions is disabled on SKUs that don't enable dwm composition";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v3,
        (unsigned int)byte_18010672B,
        v4,
        v5,
        (__int64)&v15);
    }
    v6 = (unsigned int *)((char *)this + 2556);
    *v6 = 0;
  }
  if ( (unsigned int)dword_180128170 > 4 )
  {
    LODWORD(v15) = *v6;
    v16 = "ID for Remote sessions state is ";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)byte_180106679,
      v4,
      v5,
      (__int64)&v16,
      (__int64)&v15);
  }
  if ( *v6 )
    CrimsonHelper::RaiseEventInternal((CrimsonHelper *)&CrimsonHelper::s_instance, &EVENT_WDDM_GRAPHICS_MODE, 0, 0);
  CRegistry::~CRegistry((CRegistry *)v10);
  return 0;
}

```

## disassembly

```asm
0x18004e8a4  push    rbp
0x18004e8a6  push    rbx
0x18004e8a7  mov     rbp, rsp
0x18004e8aa  sub     rsp, 78h
0x18004e8ae  mov     rbx, rcx
0x18004e8b1  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18004e8b8  mov     [rbp+var_38], rax
0x18004e8bc  mov     [rbp+var_30], 0
0x18004e8c4  mov     [rbp+var_28], 0
0x18004e8cb  mov     [rbp+var_20], 0
0x18004e8d3  or      eax, 0FFFFFFFFh
0x18004e8d6  mov     [rbp+var_18], eax
0x18004e8d9  mov     [rbp+var_14], eax
0x18004e8dc  xor     edx, edx; hFile
0x18004e8de  lea     r8d, [rax+3]; dwFlags
0x18004e8e2  lea     rcx, aUdwmDll; "udwm.dll"
0x18004e8e9  call    cs:__imp_LoadLibraryExW
0x18004e8ef  test    rax, rax
0x18004e8f2  jz      loc_18004E9E7
0x18004e8f8  mov     rcx, rax; hLibModule
0x18004e8fb  call    cs:__imp_FreeLibrary
0x18004e901  add     rbx, 9FCh
0x18004e908  mov     dword ptr [rbx], 1
0x18004e90e  mov     r9d, 20019h; unsigned int
0x18004e914  lea     r8, aSystemCurrentc_10; "System\\CurrentControlSet\\Control\\Ter"...
0x18004e91b  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18004e922  lea     rcx, [rbp+var_38]; this
0x18004e926  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18004e92b  mov     ecx, eax
0x18004e92d  test    eax, eax
0x18004e92f  jle     short loc_18004E93A
0x18004e931  movzx   ecx, ax
0x18004e934  or      ecx, 80070000h
0x18004e93a  test    ecx, ecx
0x18004e93c  jns     short loc_18004E9A3
0x18004e93e  mov     eax, cs:dword_180128170
0x18004e944  cmp     eax, 3
0x18004e947  jbe     loc_18004EA1F
0x18004e94d  lea     rax, aUpdatewddmmode_0; "UpdateWddmModeSettings"
0x18004e954  mov     [rbp+arg_8], rax
0x18004e958  mov     dword ptr [rbp+arg_0], ecx
0x18004e95b  lea     rax, aReghandlerOpen; "regHandler.OpenKey"
0x18004e962  mov     [rbp+arg_10], rax
0x18004e966  lea     rax, aWarningHresult; "Warning HResult failed"
0x18004e96d  mov     [rbp+arg_18], rax
0x18004e971  lea     rax, [rbp+arg_8]
0x18004e975  mov     [rsp+78h+var_40], rax
0x18004e97a  lea     rax, [rbp+arg_0]
0x18004e97e  mov     [rsp+78h+var_48], rax
0x18004e983  lea     rax, [rbp+arg_10]
0x18004e987  mov     [rsp+78h+var_50], rax
0x18004e98c  lea     rax, [rbp+arg_18]
0x18004e990  mov     [rsp+78h+var_58], rax
0x18004e995  lea     rdx, byte_1801066E5
0x18004e99c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004e9a1  jmp     short loc_18004EA1F
0x18004e9a3  mov     r8, rbx; unsigned int *
0x18004e9a6  lea     rdx, aLoadwddmidddri; "LoadWddmIddDriver"
0x18004e9ad  lea     rcx, [rbp+var_38]; this
0x18004e9b1  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18004e9b6  test    eax, eax
0x18004e9b8  jnz     short loc_18004EA1F
0x18004e9ba  mov     eax, cs:dword_180128170
0x18004e9c0  cmp     eax, 4
0x18004e9c3  jbe     short loc_18004EA1F
0x18004e9c5  lea     rax, aIdForRemoteSes_1; "ID for Remote sessions state override r"...
0x18004e9cc  mov     [rbp+arg_0], rax
0x18004e9d0  lea     rax, [rbp+arg_0]
0x18004e9d4  mov     [rsp+78h+var_58], rax
0x18004e9d9  lea     rdx, byte_1801066B9
0x18004e9e0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18004e9e5  jmp     short loc_18004EA1F
0x18004e9e7  mov     eax, cs:dword_180128170
0x18004e9ed  cmp     eax, 4
0x18004e9f0  jbe     short loc_18004EA12
0x18004e9f2  lea     rax, aIdForRemoteSes_0; "ID for Remote sessions is disabled on S"...
0x18004e9f9  mov     [rbp+arg_0], rax
0x18004e9fd  lea     rax, [rbp+arg_0]
0x18004ea01  mov     [rsp+78h+var_58], rax
0x18004ea06  lea     rdx, byte_18010672B
0x18004ea0d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18004ea12  add     rbx, 9FCh
0x18004ea19  mov     dword ptr [rbx], 0
0x18004ea1f  mov     eax, cs:dword_180128170
0x18004ea25  cmp     eax, 4
0x18004ea28  jbe     short loc_18004EA58
0x18004ea2a  mov     eax, [rbx]
0x18004ea2c  mov     dword ptr [rbp+arg_0], eax
0x18004ea2f  lea     rax, aIdForRemoteSes; "ID for Remote sessions state is "
0x18004ea36  mov     [rbp+arg_8], rax
0x18004ea3a  lea     rax, [rbp+arg_0]
0x18004ea3e  mov     [rsp+78h+var_50], rax
0x18004ea43  lea     rax, [rbp+arg_8]
0x18004ea47  mov     [rsp+78h+var_58], rax
0x18004ea4c  lea     rdx, byte_180106679
0x18004ea53  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004ea58  cmp     dword ptr [rbx], 0
0x18004ea5b  jz      short loc_18004EA77
0x18004ea5d  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x18004ea60  xor     r8d, r8d; unsigned int
0x18004ea63  lea     rdx, EVENT_WDDM_GRAPHICS_MODE; struct _EVENT_DESCRIPTOR *
0x18004ea6a  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x18004ea71  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x18004ea76  nop
0x18004ea77  lea     rcx, [rbp+var_38]; this
0x18004ea7b  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18004ea80  xor     eax, eax
0x18004ea82  add     rsp, 78h
0x18004ea86  pop     rbx
0x18004ea87  pop     rbp
0x18004ea88  retn
```
