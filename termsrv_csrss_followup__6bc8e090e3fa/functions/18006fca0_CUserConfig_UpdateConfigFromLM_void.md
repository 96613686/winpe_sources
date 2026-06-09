# CUserConfig::UpdateConfigFromLM(void)

- ea: `0x18006fca0`
- end: `0x18006fda1`
- name: `?UpdateConfigFromLM@CUserConfig@@UEAAJXZ`
- size: `257`
- prototype: `__int64 __fastcall(CUserConfig *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callees

- `0x180009940`
- `0x1800260ec`
- `0x180029bc4`
- `0x180033f60`
- `0x180034e64`
- `0x18006fca0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006fd71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006fd71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006fd1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006fd1a`
- `REGAPI!QueryUserConfig` at `0x18006fd5b`
- `REGAPI!QueryUserConfig` at `0x18006fd5b`

## string_xrefs

- `0x18006fcc4`: `CUserConfig::UpdateConfigFromLM`
- `0x18006fccb`: `UpdateConfig from LM`
- `0x18006fd0c`: `System\CurrentControlSet\Control\Terminal Server\DefaultUserConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserConfig::UpdateConfigFromLM(CUserConfig *this)
{
  char *v2; // rbx
  __int64 v3; // rcx
  HKEY hKey; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v6[56]; // [rsp+38h] [rbp-50h] BYREF

  hKey = 0;
  CGenericTrace::CGenericTrace((CGenericTrace *)v6, 4u, "UpdateConfig from LM", "CUserConfig::UpdateConfigFromLM");
  v2 = (char *)this + 1600;
  memset_0(v2, 0, 0x9E8u);
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\DefaultUserConfiguration",
         0,
         0x20019u,
         &hKey) )
  {
    _DbgPrintMessage(1, ".... DefaultUserCfg doesn't exist on local machine...using hard-code defaults.");
    v3 = -2147483646;
  }
  else
  {
    _DbgPrintMessage(1, ".... querying DefaultUserCfg from local machine.");
    v3 = (__int64)hKey;
  }
  QueryUserConfig(v3, v2, 0);
  if ( hKey )
    RegCloseKey(hKey);
  CGenericTrace::~CGenericTrace((CGenericTrace *)v6);
  return 0;
}

```

## disassembly

```asm
0x18006fca0  push    rbx
0x18006fca2  sub     rsp, 80h
0x18006fca9  mov     rax, cs:__security_cookie
0x18006fcb0  xor     rax, rsp
0x18006fcb3  mov     [rsp+88h+var_18], rax
0x18006fcb8  mov     rbx, rcx
0x18006fcbb  mov     [rsp+88h+hKey], 0
0x18006fcc4  lea     r9, aCuserconfigUpd_0; "CUserConfig::UpdateConfigFromLM"
0x18006fccb  lea     r8, aUpdateconfigFr; "UpdateConfig from LM"
0x18006fcd2  mov     edx, 4; unsigned int
0x18006fcd7  lea     rcx, [rsp+88h+var_50]; this
0x18006fcdc  call    ??0CGenericTrace@@QEAA@KPEBD0@Z; CGenericTrace::CGenericTrace(ulong,char const *,char const *)
0x18006fce1  nop
0x18006fce2  add     rbx, 640h
0x18006fce9  xor     edx, edx; Val
0x18006fceb  mov     r8d, 9E8h; Size
0x18006fcf1  mov     rcx, rbx; void *
0x18006fcf4  call    memset_0
0x18006fcf9  lea     rax, [rsp+88h+hKey]
0x18006fcfe  mov     [rsp+88h+phkResult], rax; phkResult
0x18006fd03  mov     r9d, 20019h; samDesired
0x18006fd09  xor     r8d, r8d; ulOptions
0x18006fd0c  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Control\\Ter"...
0x18006fd13  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006fd1a  call    cs:__imp_RegOpenKeyExW
0x18006fd21  nop     dword ptr [rax+rax+00h]
0x18006fd26  mov     ecx, 1; int
0x18006fd2b  test    eax, eax
0x18006fd2d  jnz     short loc_18006FD42
0x18006fd2f  lea     rdx, aQueryingDefaul; ".... querying DefaultUserCfg from local"...
0x18006fd36  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006fd3b  mov     rcx, [rsp+88h+hKey]
0x18006fd40  jmp     short loc_18006FD55
0x18006fd42  lea     rdx, aDefaultusercfg; ".... DefaultUserCfg doesn't exist on lo"...
0x18006fd49  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006fd4e  mov     rcx, 0FFFFFFFF80000002h
0x18006fd55  xor     r8d, r8d
0x18006fd58  mov     rdx, rbx
0x18006fd5b  call    cs:__imp_QueryUserConfig
0x18006fd62  nop     dword ptr [rax+rax+00h]
0x18006fd67  mov     rcx, [rsp+88h+hKey]; hKey
0x18006fd6c  test    rcx, rcx
0x18006fd6f  jz      short loc_18006FD7E
0x18006fd71  call    cs:__imp_RegCloseKey
0x18006fd78  nop     dword ptr [rax+rax+00h]
0x18006fd7d  nop
0x18006fd7e  lea     rcx, [rsp+88h+var_50]; this
0x18006fd83  call    ??1CGenericTrace@@UEAA@XZ; CGenericTrace::~CGenericTrace(void)
0x18006fd88  xor     eax, eax
0x18006fd8a  mov     rcx, [rsp+88h+var_18]
0x18006fd8f  xor     rcx, rsp; StackCookie
0x18006fd92  call    __security_check_cookie
0x18006fd97  add     rsp, 80h
0x18006fd9e  pop     rbx
0x18006fd9f  retn
```
