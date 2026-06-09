# Windows::Power::IsSleepOnACEnabled(void)

- ea: `0x1800b24c0`
- end: `0x1800b2608`
- name: `?IsSleepOnACEnabled@Power@Windows@@UEAA_NXZ`
- size: `328`
- prototype: `bool __fastcall(Windows::Power *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x180010e80`
- `0x1800b24c0`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b252f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b25a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b252f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b25a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b253d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b25b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b253d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b25b4`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1800b2505`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1800b2505`
- `api-ms-win-power-setting-l1-1-0!PowerReadACValue` at `0x1800b2580`
- `api-ms-win-power-setting-l1-1-0!PowerReadACValue` at `0x1800b2580`

## string_xrefs

- `0x1800b25e1`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Power.cpp`
- `0x1800b25f6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Power.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall Windows::Power::IsSleepOnACEnabled(Windows::Power *this)
{
  DWORD ActiveScheme; // eax
  GUID *v2; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v4; // eax
  bool v5; // di
  GUID *v6; // rbx
  HANDLE v7; // rax
  unsigned int Type; // [rsp+20h] [rbp-60h]
  unsigned int Typea; // [rsp+20h] [rbp-60h]
  GUID *ActivePolicyGuid; // [rsp+48h] [rbp-38h] BYREF
  char v12; // [rsp+50h] [rbp-30h]
  BYTE Buffer[8]; // [rsp+58h] [rbp-28h] BYREF
  GUID *SchemeGuid; // [rsp+60h] [rbp-20h]
  DWORD BufferSize; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  SchemeGuid = 0;
  ActivePolicyGuid = 0;
  v12 = 1;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  if ( ActiveScheme )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xD3,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Power.cpp",
      (const char *)ActiveScheme,
      Type);
  if ( v12 )
  {
    v2 = SchemeGuid;
    SchemeGuid = ActivePolicyGuid;
    if ( v2 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
  }
  *(_DWORD *)Buffer = 0;
  BufferSize = 4;
  v4 = PowerReadACValue(0, SchemeGuid, &GUID_SLEEP_SUBGROUP, &GUID_STANDBY_TIMEOUT, 0, Buffer, &BufferSize);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xDE,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Power.cpp",
      (const char *)v4,
      Typea);
  v5 = *(_DWORD *)Buffer != 0;
  v6 = SchemeGuid;
  SchemeGuid = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  return v5;
}

```

## disassembly

```asm
0x1800b24c0  mov     [rsp-8+arg_0], rbx
0x1800b24c5  mov     [rsp-8+arg_8], rdi
0x1800b24ca  push    rbp
0x1800b24cb  mov     rbp, rsp
0x1800b24ce  sub     rsp, 80h
0x1800b24d5  mov     rax, cs:__security_cookie
0x1800b24dc  xor     rax, rsp
0x1800b24df  mov     [rbp+var_10], rax
0x1800b24e3  mov     [rbp+SchemeGuid], 0
0x1800b24eb  lea     rax, [rbp+SchemeGuid]
0x1800b24ef  mov     [rbp+var_40], rax
0x1800b24f3  mov     [rbp+ActivePolicyGuid], 0
0x1800b24fb  mov     [rbp+var_30], 1
0x1800b24ff  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x1800b2503  xor     ecx, ecx; UserRootPowerKey
0x1800b2505  call    cs:__imp_PowerGetActiveScheme
0x1800b250b  mov     rcx, [rbp+8]; this
0x1800b250f  test    eax, eax
0x1800b2511  jnz     loc_1800B25F3
0x1800b2517  cmp     [rbp+var_30], al
0x1800b251a  jz      short loc_1800B2543
0x1800b251c  mov     rcx, [rbp+var_40]
0x1800b2520  mov     rbx, [rcx]
0x1800b2523  mov     rax, [rbp+ActivePolicyGuid]
0x1800b2527  mov     [rcx], rax
0x1800b252a  test    rbx, rbx
0x1800b252d  jz      short loc_1800B2543
0x1800b252f  call    cs:__imp_GetProcessHeap
0x1800b2535  mov     rcx, rax; hHeap
0x1800b2538  mov     r8, rbx; lpMem
0x1800b253b  xor     edx, edx; dwFlags
0x1800b253d  call    cs:__imp_HeapFree
0x1800b2543  mov     dword ptr [rbp+var_28], 0
0x1800b254a  mov     [rbp+var_18], 4
0x1800b2551  lea     rax, [rbp+var_18]
0x1800b2555  mov     [rsp+80h+BufferSize], rax; BufferSize
0x1800b255a  lea     rax, [rbp+var_28]
0x1800b255e  mov     [rsp+80h+Buffer], rax; Buffer
0x1800b2563  mov     [rsp+80h+Type], 0; unsigned int
0x1800b256c  lea     r9, GUID_STANDBY_TIMEOUT; PowerSettingGuid
0x1800b2573  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800b257a  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x1800b257e  xor     ecx, ecx; RootPowerKey
0x1800b2580  call    cs:__imp_PowerReadACValue
0x1800b2586  mov     rcx, [rbp+8]; this
0x1800b258a  test    eax, eax
0x1800b258c  jnz     short loc_1800B25DE
0x1800b258e  cmp     dword ptr [rbp+var_28], eax
0x1800b2591  setnz   dil
0x1800b2595  mov     rbx, [rbp+SchemeGuid]
0x1800b2599  mov     [rbp+SchemeGuid], 0
0x1800b25a1  test    rbx, rbx
0x1800b25a4  jz      short loc_1800B25BA
0x1800b25a6  call    cs:__imp_GetProcessHeap
0x1800b25ac  mov     rcx, rax; hHeap
0x1800b25af  mov     r8, rbx; lpMem
0x1800b25b2  xor     edx, edx; dwFlags
0x1800b25b4  call    cs:__imp_HeapFree
0x1800b25ba  mov     al, dil
0x1800b25bd  mov     rcx, [rbp+var_10]
0x1800b25c1  xor     rcx, rsp; StackCookie
0x1800b25c4  call    __security_check_cookie
0x1800b25c9  lea     r11, [rsp+80h+var_s0]
0x1800b25d1  mov     rbx, [r11+10h]
0x1800b25d5  mov     rdi, [r11+18h]
0x1800b25d9  mov     rsp, r11
0x1800b25dc  pop     rbp
0x1800b25dd  retn
0x1800b25de  mov     r9d, eax; char *
0x1800b25e1  lea     r8, aCW1SSrcOrchest_15; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800b25e8  mov     edx, 0DEh; void *
0x1800b25ed  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800b25f3  mov     r9d, eax; char *
0x1800b25f6  lea     r8, aCW1SSrcOrchest_15; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800b25fd  mov     edx, 0D3h; void *
0x1800b2602  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
