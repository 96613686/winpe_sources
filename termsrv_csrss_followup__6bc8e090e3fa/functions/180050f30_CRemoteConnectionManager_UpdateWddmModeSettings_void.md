# CRemoteConnectionManager::UpdateWddmModeSettings(void)

- ea: `0x180050f30`
- end: `0x180051122`
- name: `?UpdateWddmModeSettings@CRemoteConnectionManager@@AEAAJXZ`
- size: `498`
- prototype: `__int64 __fastcall(CRemoteConnectionManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004d4d0`

## callees

- `0x180001294`
- `0x1800016a8`
- `0x1800142e0`
- `0x180015310`
- `0x180028dd8`
- `0x180028e44`
- `0x180028f88`
- `0x180050f30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180050f8d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180050f8d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180050f75`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180050f75`

## string_xrefs

- `0x180050f6e`: `udwm.dll`
- `0x18005108a`: `ID for Remote sessions is disabled on SKUs that don't enable dwm composition`
- `0x180050fe5`: `UpdateWddmModeSettings`
- `0x180050ff3`: `regHandler.OpenKey`
- `0x18005105d`: `ID for Remote sessions state override registry key is present`

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
      if ( !CRegistry::ReadRegDWord((CRegistry *)v10, L"LoadWddmIddDriver", v6) && (unsigned int)dword_18012E170 > 4 )
      {
        v15 = "ID for Remote sessions state override registry key is present";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v3,
          (unsigned int)byte_18010C739,
          v4,
          v5,
          (__int64)&v15);
      }
    }
    else if ( (unsigned int)dword_18012E170 > 3 )
    {
      v16 = "UpdateWddmModeSettings";
      LODWORD(v15) = v3;
      v17 = "regHandler.OpenKey";
      v18 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)byte_18010C765,
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
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      v15 = "ID for Remote sessions is disabled on SKUs that don't enable dwm composition";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v3,
        (unsigned int)byte_18010C7AB,
        v4,
        v5,
        (__int64)&v15);
    }
    v6 = (unsigned int *)((char *)this + 2556);
    *v6 = 0;
  }
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    LODWORD(v15) = *v6;
    v16 = "ID for Remote sessions state is ";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)byte_18010C6F9,
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
0x180050f30  push    rbp
0x180050f32  push    rbx
0x180050f33  mov     rbp, rsp
0x180050f36  sub     rsp, 78h
0x180050f3a  mov     rbx, rcx
0x180050f3d  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180050f44  mov     [rbp+var_38], rax
0x180050f48  mov     [rbp+var_30], 0
0x180050f50  mov     [rbp+var_28], 0
0x180050f57  mov     [rbp+var_20], 0
0x180050f5f  or      eax, 0FFFFFFFFh
0x180050f62  mov     [rbp+var_18], eax
0x180050f65  mov     [rbp+var_14], eax
0x180050f68  xor     edx, edx; hFile
0x180050f6a  lea     r8d, [rax+3]; dwFlags
0x180050f6e  lea     rcx, aUdwmDll; "udwm.dll"
0x180050f75  call    cs:__imp_LoadLibraryExW
0x180050f7c  nop     dword ptr [rax+rax+00h]
0x180050f81  test    rax, rax
0x180050f84  jz      loc_18005107F
0x180050f8a  mov     rcx, rax; hLibModule
0x180050f8d  call    cs:__imp_FreeLibrary
0x180050f94  nop     dword ptr [rax+rax+00h]
0x180050f99  add     rbx, 9FCh
0x180050fa0  mov     dword ptr [rbx], 1
0x180050fa6  mov     r9d, 20019h; unsigned int
0x180050fac  lea     r8, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180050fb3  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180050fba  lea     rcx, [rbp+var_38]; this
0x180050fbe  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180050fc3  mov     ecx, eax
0x180050fc5  test    eax, eax
0x180050fc7  jle     short loc_180050FD2
0x180050fc9  movzx   ecx, ax
0x180050fcc  or      ecx, 80070000h
0x180050fd2  test    ecx, ecx
0x180050fd4  jns     short loc_18005103B
0x180050fd6  mov     eax, cs:dword_18012E170
0x180050fdc  cmp     eax, 3
0x180050fdf  jbe     loc_1800510B7
0x180050fe5  lea     rax, aUpdatewddmmode_0; "UpdateWddmModeSettings"
0x180050fec  mov     [rbp+arg_8], rax
0x180050ff0  mov     dword ptr [rbp+arg_0], ecx
0x180050ff3  lea     rax, aReghandlerOpen; "regHandler.OpenKey"
0x180050ffa  mov     [rbp+arg_10], rax
0x180050ffe  lea     rax, aWarningHresult; "Warning HResult failed"
0x180051005  mov     [rbp+arg_18], rax
0x180051009  lea     rax, [rbp+arg_8]
0x18005100d  mov     [rsp+78h+var_40], rax
0x180051012  lea     rax, [rbp+arg_0]
0x180051016  mov     [rsp+78h+var_48], rax
0x18005101b  lea     rax, [rbp+arg_10]
0x18005101f  mov     [rsp+78h+var_50], rax
0x180051024  lea     rax, [rbp+arg_18]
0x180051028  mov     [rsp+78h+var_58], rax
0x18005102d  lea     rdx, byte_18010C765
0x180051034  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180051039  jmp     short loc_1800510B7
0x18005103b  mov     r8, rbx; unsigned int *
0x18005103e  lea     rdx, aLoadwddmidddri; "LoadWddmIddDriver"
0x180051045  lea     rcx, [rbp+var_38]; this
0x180051049  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18005104e  test    eax, eax
0x180051050  jnz     short loc_1800510B7
0x180051052  mov     eax, cs:dword_18012E170
0x180051058  cmp     eax, 4
0x18005105b  jbe     short loc_1800510B7
0x18005105d  lea     rax, aIdForRemoteSes_1; "ID for Remote sessions state override r"...
0x180051064  mov     [rbp+arg_0], rax
0x180051068  lea     rax, [rbp+arg_0]
0x18005106c  mov     [rsp+78h+var_58], rax
0x180051071  lea     rdx, byte_18010C739
0x180051078  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005107d  jmp     short loc_1800510B7
0x18005107f  mov     eax, cs:dword_18012E170
0x180051085  cmp     eax, 4
0x180051088  jbe     short loc_1800510AA
0x18005108a  lea     rax, aIdForRemoteSes_0; "ID for Remote sessions is disabled on S"...
0x180051091  mov     [rbp+arg_0], rax
0x180051095  lea     rax, [rbp+arg_0]
0x180051099  mov     [rsp+78h+var_58], rax
0x18005109e  lea     rdx, byte_18010C7AB
0x1800510a5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800510aa  add     rbx, 9FCh
0x1800510b1  mov     dword ptr [rbx], 0
0x1800510b7  mov     eax, cs:dword_18012E170
0x1800510bd  cmp     eax, 4
0x1800510c0  jbe     short loc_1800510F0
0x1800510c2  mov     eax, [rbx]
0x1800510c4  mov     dword ptr [rbp+arg_0], eax
0x1800510c7  lea     rax, aIdForRemoteSes; "ID for Remote sessions state is "
0x1800510ce  mov     [rbp+arg_8], rax
0x1800510d2  lea     rax, [rbp+arg_0]
0x1800510d6  mov     [rsp+78h+var_50], rax
0x1800510db  lea     rax, [rbp+arg_8]
0x1800510df  mov     [rsp+78h+var_58], rax
0x1800510e4  lea     rdx, byte_18010C6F9
0x1800510eb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800510f0  cmp     dword ptr [rbx], 0
0x1800510f3  jz      short loc_18005110F
0x1800510f5  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x1800510f8  xor     r8d, r8d; unsigned int
0x1800510fb  lea     rdx, EVENT_WDDM_GRAPHICS_MODE; struct _EVENT_DESCRIPTOR *
0x180051102  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x180051109  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x18005110e  nop
0x18005110f  lea     rcx, [rbp+var_38]; this
0x180051113  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180051118  xor     eax, eax
0x18005111a  add     rsp, 78h
0x18005111e  pop     rbx
0x18005111f  pop     rbp
0x180051120  retn
```
