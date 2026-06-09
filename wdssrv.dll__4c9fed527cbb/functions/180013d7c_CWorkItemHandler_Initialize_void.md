# CWorkItemHandler::Initialize(void)

- ea: `0x180013d7c`
- end: `0x180013e5f`
- name: `?Initialize@CWorkItemHandler@@QEAAKXZ`
- size: `227`
- prototype: `unsigned int __fastcall(CWorkItemHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009da4`

## callees

- `0x180013d7c`
- `0x180013ee8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180013db4`
- `ADVAPI32!RegOpenKeyExW` at `0x180013db4`
- `ADVAPI32!RegCloseKey` at `0x180013e45`
- `ADVAPI32!RegCloseKey` at `0x180013e45`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180013de7`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180013de7`
- `WdsServerCommonLib!?Initialize@CCompPort@@QEAAKPEAXK@Z` at `0x180013e20`
- `WdsServerCommonLib!?Initialize@CCompPort@@QEAAKPEAXK@Z` at `0x180013e20`

## string_xrefs

- `0x180013da6`: `System\CurrentControlSet\Services\WDSServer\Parameters`
- `0x180013ddb`: `WorkerThreads`

## pseudocode

```c
__int64 __fastcall CWorkItemHandler::Initialize(CWorkItemHandler *this)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int ValueDwordWithDefault; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // r8d
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int v13; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v13 = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
         0,
         0x20119u,
         &hKey);
  ValueDwordWithDefault = ElValidateWin32_5(v2, v3, v4, 55);
  if ( !ValueDwordWithDefault )
  {
    ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault((CRegKey *)&hKey, L"WorkerThreads", 0, &v13);
    if ( !(unsigned int)ElValidateWin32_5(ValueDwordWithDefault, v6, v7, 64) )
    {
      v8 = v13;
      if ( v13 >= 0x40 )
      {
        v8 = 64;
        v13 = 64;
      }
      v9 = CCompPort::Initialize((CWorkItemHandler *)((char *)this + 8), 0, v8);
      ValueDwordWithDefault = ElValidateWin32_5(v9, v10, v11, 72);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return ValueDwordWithDefault;
}

```

## disassembly

```asm
0x180013d7c  mov     rax, rsp
0x180013d7f  mov     [rax+8], rbx
0x180013d83  push    rdi
0x180013d84  sub     rsp, 30h
0x180013d88  and     dword ptr [rax+10h], 0
0x180013d8c  mov     rdi, rcx
0x180013d8f  and     qword ptr [rax+18h], 0
0x180013d94  lea     rax, [rax+18h]
0x180013d98  mov     r9d, 20119h; samDesired
0x180013d9e  mov     [rsp+38h+phkResult], rax; phkResult
0x180013da3  xor     r8d, r8d; ulOptions
0x180013da6  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x180013dad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013db4  call    cs:__imp_RegOpenKeyExW
0x180013dbb  nop     dword ptr [rax+rax+00h]
0x180013dc0  mov     ecx, eax
0x180013dc2  mov     r9d, 37h ; '7'
0x180013dc8  call    ElValidateWin32_5
0x180013dcd  mov     ebx, eax
0x180013dcf  test    eax, eax
0x180013dd1  jnz     short loc_180013E3B
0x180013dd3  lea     r9, [rsp+38h+arg_8]
0x180013dd8  xor     r8d, r8d
0x180013ddb  lea     rdx, aWorkerthreads; "WorkerThreads"
0x180013de2  lea     rcx, [rsp+38h+hKey]
0x180013de7  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180013dee  nop     dword ptr [rax+rax+00h]
0x180013df3  mov     ecx, eax
0x180013df5  mov     r9d, 40h ; '@'
0x180013dfb  mov     ebx, eax
0x180013dfd  call    ElValidateWin32_5
0x180013e02  test    eax, eax
0x180013e04  jnz     short loc_180013E3B
0x180013e06  mov     r8d, [rsp+38h+arg_8]
0x180013e0b  cmp     r8d, 40h ; '@'
0x180013e0f  jb      short loc_180013E1A
0x180013e11  lea     r8d, [rax+40h]
0x180013e15  mov     [rsp+38h+arg_8], r8d
0x180013e1a  lea     rcx, [rdi+8]
0x180013e1e  xor     edx, edx
0x180013e20  call    cs:__imp_?Initialize@CCompPort@@QEAAKPEAXK@Z; CCompPort::Initialize(void *,ulong)
0x180013e27  nop     dword ptr [rax+rax+00h]
0x180013e2c  mov     ecx, eax
0x180013e2e  mov     r9d, 48h ; 'H'
0x180013e34  call    ElValidateWin32_5
0x180013e39  mov     ebx, eax
0x180013e3b  mov     rcx, [rsp+38h+hKey]; hKey
0x180013e40  test    rcx, rcx
0x180013e43  jz      short loc_180013E51
0x180013e45  call    cs:__imp_RegCloseKey
0x180013e4c  nop     dword ptr [rax+rax+00h]
0x180013e51  mov     eax, ebx
0x180013e53  mov     rbx, [rsp+38h+arg_0]
0x180013e58  add     rsp, 30h
0x180013e5c  pop     rdi
0x180013e5d  retn
```
