# Windows::Reboot::ClearStartAfterReboot(void)

- ea: `0x180093110`
- end: `0x18009329b`
- name: `?ClearStartAfterReboot@Reboot@Windows@@UEAAXXZ`
- size: `395`
- prototype: `void __fastcall(Windows::Reboot *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000f83c`
- `0x180010f24`
- `0x1800112d0`
- `0x180040160`
- `0x180093110`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800931b3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800931b3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180093180`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180093180`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093206`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093215`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093206`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180093215`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800931eb`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800931eb`

## string_xrefs

- `0x180093259`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x18009326b`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x18009327b`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x18009328a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Reboot::ClearStartAfterReboot(Windows::Reboot *this)
{
  int v1; // eax
  const char *v2; // r9
  SC_HANDLE v3; // rax
  const char *v4; // r9
  SC_HANDLE v5; // rbx
  bool v6; // si
  SC_HANDLE v7; // rax
  const char *v8; // r9
  SC_HANDLE v9; // rdi
  bool v10; // r14
  int v11; // [rsp+20h] [rbp-38h]
  int Info; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  try
  {
    v13 = 0;
    wil::CoCreateInstance<IUsoSvc,wil::err_exception_policy>(&v13);
    v1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 80LL))(v13);
    if ( v1 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
        (const char *)(unsigned int)v1,
        v11);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl) )
    {
      v3 = OpenSCManagerW(0, 0, 1u);
      v5 = v3;
      v6 = v3 != 0;
      if ( !v3 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x42,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
          v4);
      v7 = OpenServiceW(v3, L"UsoSvc", 2u);
      v9 = v7;
      v10 = v7 != 0;
      if ( !v7 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x45,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
          v8);
      Info = 1;
      if ( !ChangeServiceConfig2W(v7, 3u, &Info) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x4B,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
          v2);
      if ( v10 )
        CloseServiceHandle(v9);
      if ( v6 )
        CloseServiceHandle(v5);
    }
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
      v2);
  }
}

```

## disassembly

```asm
0x180093110  mov     r11, rsp
0x180093113  mov     [r11+8], rbx
0x180093117  mov     [r11+10h], rsi
0x18009311b  mov     [r11+18h], rdi
0x18009311f  push    r14
0x180093121  sub     rsp, 50h
0x180093125  mov     rax, cs:__security_cookie
0x18009312c  xor     rax, rsp
0x18009312f  mov     [rsp+58h+var_18], rax
0x180093134  mov     qword ptr [r11-20h], 0
0x18009313c  lea     rcx, [r11-20h]
0x180093140  call    ??$CoCreateInstance@UIUsoSvc@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUsoSvc@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IUsoSvc,wil::err_exception_policy>(_GUID const &,ulong)
0x180093145  nop
0x180093146  mov     rcx, [rsp+58h+var_20]
0x18009314b  mov     rax, [rcx]
0x18009314e  mov     rax, [rax+50h]
0x180093152  call    _guard_dispatch_icall
0x180093157  mov     rcx, [rsp+58h]; this
0x18009315c  test    eax, eax
0x18009315e  js      loc_180093256
0x180093164  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl(void)'::`2'::impl
0x18009316b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(void)
0x180093170  test    al, al
0x180093172  jz      loc_18009321C
0x180093178  xor     edx, edx; lpDatabaseName
0x18009317a  xor     ecx, ecx; lpMachineName
0x18009317c  lea     r8d, [rdx+1]; dwDesiredAccess
0x180093180  call    cs:__imp_OpenSCManagerW
0x180093186  mov     rbx, rax
0x180093189  mov     [rsp+58h+var_38], rax
0x18009318e  mov     rcx, [rsp+58h]; this
0x180093193  test    rax, rax
0x180093196  setnz   sil
0x18009319a  test    rax, rax
0x18009319d  jz      loc_18009326B
0x1800931a3  mov     r8d, 2; dwDesiredAccess
0x1800931a9  lea     rdx, aUsosvc; "UsoSvc"
0x1800931b0  mov     rcx, rbx; hSCManager
0x1800931b3  call    cs:__imp_OpenServiceW
0x1800931b9  mov     rdi, rax
0x1800931bc  mov     [rsp+58h+var_30], rax
0x1800931c1  mov     rcx, [rsp+58h]; this
0x1800931c6  test    rax, rax
0x1800931c9  setnz   r14b
0x1800931cd  test    rax, rax
0x1800931d0  jz      loc_18009327B
0x1800931d6  mov     [rsp+58h+Info], 1
0x1800931de  lea     r8, [rsp+58h+Info]; lpInfo
0x1800931e3  mov     edx, 3; dwInfoLevel
0x1800931e8  mov     rcx, rdi; hService
0x1800931eb  call    cs:__imp_ChangeServiceConfig2W
0x1800931f1  mov     rcx, [rsp+58h]; this
0x1800931f6  test    eax, eax
0x1800931f8  jz      loc_18009328A
0x1800931fe  test    r14b, r14b
0x180093201  jz      short loc_18009320D
0x180093203  mov     rcx, rdi; hSCObject
0x180093206  call    cs:__imp_CloseServiceHandle
0x18009320c  nop
0x18009320d  test    sil, sil
0x180093210  jz      short loc_18009321C
0x180093212  mov     rcx, rbx; hSCObject
0x180093215  call    cs:__imp_CloseServiceHandle
0x18009321b  nop
0x18009321c  mov     rcx, [rsp+58h+var_20]
0x180093221  test    rcx, rcx
0x180093224  jz      short loc_180093233
0x180093226  mov     rax, [rcx]
0x180093229  mov     rax, [rax+10h]
0x18009322d  call    _guard_dispatch_icall
0x180093232  nop
0x180093233  mov     rcx, [rsp+58h+var_18]
0x180093238  xor     rcx, rsp; StackCookie
0x18009323b  call    __security_check_cookie
0x180093240  mov     rbx, [rsp+58h+arg_0]
0x180093245  mov     rsi, [rsp+58h+arg_8]
0x18009324a  mov     rdi, [rsp+58h+arg_10]
0x18009324f  add     rsp, 50h
0x180093253  pop     r14
0x180093255  retn
0x180093256  mov     r9d, eax; char *
0x180093259  lea     r8, aCW1SSrcOrchest_27; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180093260  mov     edx, 3Bh ; ';'; void *
0x180093265  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009326b  lea     r8, aCW1SSrcOrchest_27; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180093272  lea     edx, [rax+42h]; void *
0x180093275  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009327b  lea     r8, aCW1SSrcOrchest_27; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180093282  lea     edx, [rax+45h]; void *
0x180093285  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009328a  lea     r8, aCW1SSrcOrchest_27; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180093291  lea     edx, [rax+4Bh]; void *
0x180093294  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
