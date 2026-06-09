# CMulticastHandler::Initialize(CInterfaceMonitor *)

- ea: `0x1800174b8`
- end: `0x1800175e5`
- name: `?Initialize@CMulticastHandler@@QEAAKPEAVCInterfaceMonitor@@@Z`
- size: `301`
- prototype: `unsigned int __fastcall(CMulticastHandler *__hidden this, struct CInterfaceMonitor *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013638`

## callees

- `0x180016948`
- `0x1800174b8`
- `0x1800175ec`
- `0x180017810`
- `0x18001784c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800174f7`
- `ADVAPI32!RegOpenKeyExW` at `0x1800174f7`
- `ADVAPI32!RegCloseKey` at `0x1800175c6`
- `ADVAPI32!RegCloseKey` at `0x1800175c6`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x18001752e`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x18001752e`

## string_xrefs

- `0x1800174e6`: `System\CurrentControlSet\Services\WDSServer\Parameters`

## pseudocode

```c
__int64 __fastcall CMulticastHandler::Initialize(CMulticastHandler *this, struct CInterfaceMonitor *a2)
{
  __int64 ValueDwordWithDefault; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  int v10; // r8d
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // r8d
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  HKEY hKey[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v21; // [rsp+60h] [rbp+18h] BYREF

  v21 = 0;
  hKey[0] = 0;
  ValueDwordWithDefault = (unsigned int)RegOpenKeyExW(
                                          HKEY_LOCAL_MACHINE,
                                          L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
                                          0,
                                          0x20119u,
                                          hKey);
  if ( !(unsigned int)ElValidateWin32_9(ValueDwordWithDefault, v5, v6, 62) )
  {
    ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault((CRegKey *)hKey, L"UseMADCAP", 0, &v21);
    if ( !(unsigned int)ElValidateWin32_9(ValueDwordWithDefault, v7, v8, 69) )
    {
      v11 = v21;
      *(_DWORD *)this = v21;
      if ( v11 )
      {
        ValueDwordWithDefault = (unsigned int)CMadcapHandler::Initialize(
                                                (LPCRITICAL_SECTION)((char *)this + 248),
                                                v9,
                                                a2);
        if ( !(unsigned int)ElValidateWin32_9(ValueDwordWithDefault, v12, v13, 76) )
        {
          ValueDwordWithDefault = CMulticastHandler::InitializeStatic(this, 0, v14);
          ElValidateWin32_9(ValueDwordWithDefault, v15, v16, 80);
        }
      }
      else
      {
        ValueDwordWithDefault = CMulticastHandler::InitializeStatic(this, 1, v10);
        ElValidateWin32_9(ValueDwordWithDefault, v17, v18, 86);
      }
    }
  }
  if ( (_DWORD)ValueDwordWithDefault )
    CMulticastHandler::Shutdown(this);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return (unsigned int)ValueDwordWithDefault;
}

```

## disassembly

```asm
0x1800174b8  mov     rax, rsp
0x1800174bb  mov     [rax+8], rbx
0x1800174bf  mov     [rax+10h], rsi
0x1800174c3  push    rdi
0x1800174c4  sub     rsp, 40h
0x1800174c8  and     dword ptr [rax+18h], 0
0x1800174cc  mov     rsi, rdx
0x1800174cf  and     qword ptr [rax-18h], 0
0x1800174d4  lea     rax, [rax-18h]
0x1800174d8  mov     rdi, rcx
0x1800174db  mov     [rsp+48h+phkResult], rax; phkResult
0x1800174e0  mov     r9d, 20119h; samDesired
0x1800174e6  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x1800174ed  xor     r8d, r8d; ulOptions
0x1800174f0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800174f7  call    cs:__imp_RegOpenKeyExW
0x1800174fe  nop     dword ptr [rax+rax+00h]
0x180017503  mov     ecx, eax
0x180017505  mov     r9d, 3Eh ; '>'
0x18001750b  mov     ebx, eax
0x18001750d  call    ElValidateWin32_9
0x180017512  test    eax, eax
0x180017514  jnz     loc_1800175B0
0x18001751a  lea     r9, [rsp+48h+arg_10]
0x18001751f  xor     r8d, r8d
0x180017522  lea     rdx, aUsemadcap; "UseMADCAP"
0x180017529  lea     rcx, [rsp+48h+hKey]
0x18001752e  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180017535  nop     dword ptr [rax+rax+00h]
0x18001753a  mov     ecx, eax
0x18001753c  mov     r9d, 45h ; 'E'
0x180017542  mov     ebx, eax
0x180017544  call    ElValidateWin32_9
0x180017549  test    eax, eax
0x18001754b  jnz     short loc_1800175B0
0x18001754d  mov     eax, [rsp+48h+arg_10]
0x180017551  mov     [rdi], eax
0x180017553  test    eax, eax
0x180017555  jz      short loc_180017594
0x180017557  lea     rcx, [rdi+0F8h]; lpCriticalSection
0x18001755e  mov     r8, rsi; struct CInterfaceMonitor *
0x180017561  call    ?Initialize@CMadcapHandler@@QEAAKGPEAVCInterfaceMonitor@@@Z; CMadcapHandler::Initialize(ushort,CInterfaceMonitor *)
0x180017566  mov     r9d, 4Ch ; 'L'
0x18001756c  mov     ecx, eax
0x18001756e  mov     ebx, eax
0x180017570  call    ElValidateWin32_9
0x180017575  test    eax, eax
0x180017577  jnz     short loc_1800175B0
0x180017579  xor     edx, edx; int
0x18001757b  mov     rcx, rdi; this
0x18001757e  call    ?InitializeStatic@CMulticastHandler@@AEAAKHH@Z; CMulticastHandler::InitializeStatic(int,int)
0x180017583  mov     r9d, 50h ; 'P'
0x180017589  mov     ecx, eax
0x18001758b  mov     ebx, eax
0x18001758d  call    ElValidateWin32_9
0x180017592  jmp     short loc_1800175B0
0x180017594  mov     edx, 1; int
0x180017599  mov     rcx, rdi; this
0x18001759c  call    ?InitializeStatic@CMulticastHandler@@AEAAKHH@Z; CMulticastHandler::InitializeStatic(int,int)
0x1800175a1  mov     r9d, 56h ; 'V'
0x1800175a7  mov     ecx, eax
0x1800175a9  mov     ebx, eax
0x1800175ab  call    ElValidateWin32_9
0x1800175b0  test    ebx, ebx
0x1800175b2  jz      short loc_1800175BC
0x1800175b4  mov     rcx, rdi; this
0x1800175b7  call    ?Shutdown@CMulticastHandler@@QEAAKXZ; CMulticastHandler::Shutdown(void)
0x1800175bc  mov     rcx, [rsp+48h+hKey]; hKey
0x1800175c1  test    rcx, rcx
0x1800175c4  jz      short loc_1800175D2
0x1800175c6  call    cs:__imp_RegCloseKey
0x1800175cd  nop     dword ptr [rax+rax+00h]
0x1800175d2  mov     rsi, [rsp+48h+arg_8]
0x1800175d7  mov     eax, ebx
0x1800175d9  mov     rbx, [rsp+48h+arg_0]
0x1800175de  add     rsp, 40h
0x1800175e2  pop     rdi
0x1800175e3  retn
```
