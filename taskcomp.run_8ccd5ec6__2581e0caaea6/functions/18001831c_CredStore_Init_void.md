# CredStore::Init(void)

- ea: `0x18001831c`
- end: `0x180018453`
- name: `?Init@CredStore@@SAJXZ`
- size: `311`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011958`

## callees

- `0x180007948`
- `0x18001831c`
- `0x180018fec`
- `0x180019064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180018402`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180018402`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180018411`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180018411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183af`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180018342`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001839f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180018342`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001839f`

## pseudocode

```c
__int64 CredStore::Init(void)
{
  signed int LastError; // eax
  signed int v1; // ebx
  signed int v2; // eax
  char *v3; // rax
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  CredStore *v5; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp+8h] BYREF

  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:P(A;OICI;KRSD;;;BA)(A;OICI;KA;;;SY)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    tsched::StoreSecurity::g_pRestrictedKeySecurity = SecurityDescriptor;
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 < 0 )
      goto LABEL_16;
  }
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:P(A;OICI;KA;;;BA)(A;OICI;KA;;;SY)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v1 = 0;
    tsched::StoreSecurity::g_pConfigKeySecurity = SecurityDescriptor;
  }
  else
  {
    v2 = GetLastError();
    v1 = v2;
    if ( v2 > 0 )
      v1 = (unsigned __int16)v2 | 0x80070000;
    if ( v1 < 0 )
      goto LABEL_16;
  }
  v3 = (char *)operator new(0x58u);
  SecurityDescriptor = v3;
  v4 = (struct _RTL_CRITICAL_SECTION *)v3;
  if ( !v3 )
  {
    CredStore::g_pCommonStore = 0;
    v1 = -2147024882;
LABEL_16:
    CredStore::Uninit();
    return (unsigned int)v1;
  }
  *((_QWORD *)v3 + 5) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v3 + 48), 0, 0);
  InitializeCriticalSection(v4);
  CredStore::g_pCommonStore = v4;
  CredStore::Upgrade(v5);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001831c  mov     [rsp+arg_8], rbx
0x180018321  push    rdi
0x180018322  sub     rsp, 20h
0x180018326  xor     r9d, r9d; SecurityDescriptorSize
0x180018329  mov     [rsp+28h+SecurityDescriptor], 0
0x180018332  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180018337  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;KRSD;;;BA)(A;OICI;KA;;;SY)"
0x18001833e  lea     edx, [r9+1]; StringSDRevision
0x180018342  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180018349  nop     dword ptr [rax+rax+00h]
0x18001834e  mov     edi, 80070000h
0x180018353  test    eax, eax
0x180018355  jnz     short loc_180018377
0x180018357  call    cs:__imp_GetLastError
0x18001835e  nop     dword ptr [rax+rax+00h]
0x180018363  mov     ebx, eax
0x180018365  test    eax, eax
0x180018367  jle     short loc_18001836E
0x180018369  movzx   ebx, ax
0x18001836c  or      ebx, edi
0x18001836e  test    ebx, ebx
0x180018370  jns     short loc_180018383
0x180018372  jmp     loc_180018440
0x180018377  mov     rax, [rsp+28h+SecurityDescriptor]
0x18001837c  mov     cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA, rax; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x180018383  xor     r9d, r9d; SecurityDescriptorSize
0x180018386  mov     [rsp+28h+SecurityDescriptor], 0
0x18001838f  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180018394  lea     rcx, aDPAOiciKaBaAOi; "D:P(A;OICI;KA;;;BA)(A;OICI;KA;;;SY)"
0x18001839b  lea     edx, [r9+1]; StringSDRevision
0x18001839f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800183a6  nop     dword ptr [rax+rax+00h]
0x1800183ab  test    eax, eax
0x1800183ad  jnz     short loc_1800183CC
0x1800183af  call    cs:__imp_GetLastError
0x1800183b6  nop     dword ptr [rax+rax+00h]
0x1800183bb  mov     ebx, eax
0x1800183bd  test    eax, eax
0x1800183bf  jle     short loc_1800183C6
0x1800183c1  movzx   ebx, ax
0x1800183c4  or      ebx, edi
0x1800183c6  test    ebx, ebx
0x1800183c8  js      short loc_180018440
0x1800183ca  jmp     short loc_1800183DA
0x1800183cc  mov     rax, [rsp+28h+SecurityDescriptor]
0x1800183d1  xor     ebx, ebx
0x1800183d3  mov     cs:?g_pConfigKeySecurity@StoreSecurity@tsched@@3PEAXEA, rax; void * tsched::StoreSecurity::g_pConfigKeySecurity
0x1800183da  mov     ecx, 58h ; 'X'; Size
0x1800183df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800183e4  mov     [rsp+28h+SecurityDescriptor], rax
0x1800183e9  mov     rdi, rax
0x1800183ec  test    rax, rax
0x1800183ef  jz      short loc_180018430
0x1800183f1  lea     rcx, [rax+30h]; lpCriticalSection
0x1800183f5  mov     qword ptr [rax+28h], 0
0x1800183fd  xor     r8d, r8d; Flags
0x180018400  xor     edx, edx; dwSpinCount
0x180018402  call    cs:__imp_InitializeCriticalSectionEx
0x180018409  nop     dword ptr [rax+rax+00h]
0x18001840e  mov     rcx, rdi; lpCriticalSection
0x180018411  call    cs:__imp_InitializeCriticalSection
0x180018418  nop     dword ptr [rax+rax+00h]
0x18001841d  mov     cs:?g_pCommonStore@CredStore@@0PEAV1@EA, rdi; CredStore * CredStore::g_pCommonStore
0x180018424  test    rdi, rdi
0x180018427  jz      short loc_18001843B
0x180018429  call    ?Upgrade@CredStore@@AEAAJXZ; CredStore::Upgrade(void)
0x18001842e  jmp     short loc_180018445
0x180018430  mov     cs:?g_pCommonStore@CredStore@@0PEAV1@EA, 0; CredStore * CredStore::g_pCommonStore
0x18001843b  mov     ebx, 8007000Eh
0x180018440  call    ?Uninit@CredStore@@SAJXZ; CredStore::Uninit(void)
0x180018445  mov     eax, ebx
0x180018447  mov     rbx, [rsp+28h+arg_8]
0x18001844c  add     rsp, 20h
0x180018450  pop     rdi
0x180018451  retn
```
