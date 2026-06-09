# CUserConfig::UpdateConfigFromLM(void)

- ea: `0x18006c810`
- end: `0x18006c8fe`
- name: `?UpdateConfigFromLM@CUserConfig@@UEAAJXZ`
- size: `238`
- prototype: `__int64 __fastcall(CUserConfig *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callees

- `0x18000a210`
- `0x180024d80`
- `0x18002869c`
- `0x1800321f0`
- `0x1800330c4`
- `0x18006c810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c8d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c8d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c88a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c88a`
- `REGAPI!QueryUserConfig` at `0x18006c8c5`
- `REGAPI!QueryUserConfig` at `0x18006c8c5`

## string_xrefs

- `0x18006c834`: `CUserConfig::UpdateConfigFromLM`
- `0x18006c83b`: `UpdateConfig from LM`
- `0x18006c87c`: `System\CurrentControlSet\Control\Terminal Server\DefaultUserConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserConfig::UpdateConfigFromLM(CUserConfig *this)
{
  char *v2; // rbx
  __int64 v3; // rcx
  HKEY hKey; // [rsp+30h] [rbp-58h] BYREF
  const char *v6[7]; // [rsp+38h] [rbp-50h] BYREF

  hKey = 0;
  CGenericTrace::CGenericTrace((CGenericTrace *)v6, 4, "UpdateConfig from LM", "CUserConfig::UpdateConfigFromLM");
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
  CGenericTrace::~CGenericTrace(v6);
  return 0;
}

```

## disassembly

```asm
0x18006c810  push    rbx
0x18006c812  sub     rsp, 80h
0x18006c819  mov     rax, cs:__security_cookie
0x18006c820  xor     rax, rsp
0x18006c823  mov     [rsp+88h+var_18], rax
0x18006c828  mov     rbx, rcx
0x18006c82b  mov     [rsp+88h+hKey], 0
0x18006c834  lea     r9, aCuserconfigUpd_0; "CUserConfig::UpdateConfigFromLM"
0x18006c83b  lea     r8, aUpdateconfigFr; "UpdateConfig from LM"
0x18006c842  mov     edx, 4; unsigned int
0x18006c847  lea     rcx, [rsp+88h+var_50]; this
0x18006c84c  call    ??0CGenericTrace@@QEAA@KPEBD0@Z; CGenericTrace::CGenericTrace(ulong,char const *,char const *)
0x18006c851  nop
0x18006c852  add     rbx, 640h
0x18006c859  xor     edx, edx; Val
0x18006c85b  mov     r8d, 9E8h; Size
0x18006c861  mov     rcx, rbx; void *
0x18006c864  call    memset_0
0x18006c869  lea     rax, [rsp+88h+hKey]
0x18006c86e  mov     [rsp+88h+phkResult], rax; phkResult
0x18006c873  mov     r9d, 20019h; samDesired
0x18006c879  xor     r8d, r8d; ulOptions
0x18006c87c  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Control\\Ter"...
0x18006c883  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006c88a  call    cs:__imp_RegOpenKeyExW
0x18006c890  mov     ecx, 1; int
0x18006c895  test    eax, eax
0x18006c897  jnz     short loc_18006C8AC
0x18006c899  lea     rdx, aQueryingDefaul; ".... querying DefaultUserCfg from local"...
0x18006c8a0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c8a5  mov     rcx, [rsp+88h+hKey]
0x18006c8aa  jmp     short loc_18006C8BF
0x18006c8ac  lea     rdx, aDefaultusercfg; ".... DefaultUserCfg doesn't exist on lo"...
0x18006c8b3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c8b8  mov     rcx, 0FFFFFFFF80000002h
0x18006c8bf  xor     r8d, r8d
0x18006c8c2  mov     rdx, rbx
0x18006c8c5  call    cs:__imp_QueryUserConfig
0x18006c8cb  mov     rcx, [rsp+88h+hKey]; hKey
0x18006c8d0  test    rcx, rcx
0x18006c8d3  jz      short loc_18006C8DC
0x18006c8d5  call    cs:__imp_RegCloseKey
0x18006c8db  nop
0x18006c8dc  lea     rcx, [rsp+88h+var_50]; this
0x18006c8e1  call    ??1CGenericTrace@@UEAA@XZ; CGenericTrace::~CGenericTrace(void)
0x18006c8e6  xor     eax, eax
0x18006c8e8  mov     rcx, [rsp+88h+var_18]
0x18006c8ed  xor     rcx, rsp; StackCookie
0x18006c8f0  call    __security_check_cookie
0x18006c8f5  add     rsp, 80h
0x18006c8fc  pop     rbx
0x18006c8fd  retn
```
