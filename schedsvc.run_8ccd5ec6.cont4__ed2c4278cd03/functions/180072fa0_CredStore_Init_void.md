# CredStore::Init(void)

- ea: `0x180072fa0`
- end: `0x1800730d7`
- name: `?Init@CredStore@@SAJXZ`
- size: `311`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800519e0`

## callees

- `0x180027910`
- `0x180072fa0`
- `0x180073390`
- `0x180073408`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073033`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180073086`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180073086`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180073095`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180073095`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180072fc6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180073023`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180072fc6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180073023`

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
0x180072fa0  mov     [rsp+arg_8], rbx
0x180072fa5  push    rdi
0x180072fa6  sub     rsp, 20h
0x180072faa  xor     r9d, r9d; SecurityDescriptorSize
0x180072fad  mov     [rsp+28h+SecurityDescriptor], 0
0x180072fb6  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180072fbb  lea     rcx, aDPAOiciKrsdBaA; "D:P(A;OICI;KRSD;;;BA)(A;OICI;KA;;;SY)"
0x180072fc2  lea     edx, [r9+1]; StringSDRevision
0x180072fc6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180072fcd  nop     dword ptr [rax+rax+00h]
0x180072fd2  mov     edi, 80070000h
0x180072fd7  test    eax, eax
0x180072fd9  jnz     short loc_180072FFB
0x180072fdb  call    cs:__imp_GetLastError
0x180072fe2  nop     dword ptr [rax+rax+00h]
0x180072fe7  mov     ebx, eax
0x180072fe9  test    eax, eax
0x180072feb  jle     short loc_180072FF2
0x180072fed  movzx   ebx, ax
0x180072ff0  or      ebx, edi
0x180072ff2  test    ebx, ebx
0x180072ff4  jns     short loc_180073007
0x180072ff6  jmp     loc_1800730C4
0x180072ffb  mov     rax, [rsp+28h+SecurityDescriptor]
0x180073000  mov     cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA, rax; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x180073007  xor     r9d, r9d; SecurityDescriptorSize
0x18007300a  mov     [rsp+28h+SecurityDescriptor], 0
0x180073013  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180073018  lea     rcx, aDPAOiciKaBaAOi; "D:P(A;OICI;KA;;;BA)(A;OICI;KA;;;SY)"
0x18007301f  lea     edx, [r9+1]; StringSDRevision
0x180073023  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18007302a  nop     dword ptr [rax+rax+00h]
0x18007302f  test    eax, eax
0x180073031  jnz     short loc_180073050
0x180073033  call    cs:__imp_GetLastError
0x18007303a  nop     dword ptr [rax+rax+00h]
0x18007303f  mov     ebx, eax
0x180073041  test    eax, eax
0x180073043  jle     short loc_18007304A
0x180073045  movzx   ebx, ax
0x180073048  or      ebx, edi
0x18007304a  test    ebx, ebx
0x18007304c  js      short loc_1800730C4
0x18007304e  jmp     short loc_18007305E
0x180073050  mov     rax, [rsp+28h+SecurityDescriptor]
0x180073055  xor     ebx, ebx
0x180073057  mov     cs:?g_pConfigKeySecurity@StoreSecurity@tsched@@3PEAXEA, rax; void * tsched::StoreSecurity::g_pConfigKeySecurity
0x18007305e  mov     ecx, 58h ; 'X'; dwBytes
0x180073063  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180073068  mov     [rsp+28h+SecurityDescriptor], rax
0x18007306d  mov     rdi, rax
0x180073070  test    rax, rax
0x180073073  jz      short loc_1800730B4
0x180073075  lea     rcx, [rax+30h]; lpCriticalSection
0x180073079  mov     qword ptr [rax+28h], 0
0x180073081  xor     r8d, r8d; Flags
0x180073084  xor     edx, edx; dwSpinCount
0x180073086  call    cs:__imp_InitializeCriticalSectionEx
0x18007308d  nop     dword ptr [rax+rax+00h]
0x180073092  mov     rcx, rdi; lpCriticalSection
0x180073095  call    cs:__imp_InitializeCriticalSection
0x18007309c  nop     dword ptr [rax+rax+00h]
0x1800730a1  mov     cs:?g_pCommonStore@CredStore@@0PEAV1@EA, rdi; CredStore * CredStore::g_pCommonStore
0x1800730a8  test    rdi, rdi
0x1800730ab  jz      short loc_1800730BF
0x1800730ad  call    ?Upgrade@CredStore@@AEAAJXZ; CredStore::Upgrade(void)
0x1800730b2  jmp     short loc_1800730C9
0x1800730b4  mov     cs:?g_pCommonStore@CredStore@@0PEAV1@EA, 0; CredStore * CredStore::g_pCommonStore
0x1800730bf  mov     ebx, 8007000Eh
0x1800730c4  call    ?Uninit@CredStore@@SAJXZ; CredStore::Uninit(void)
0x1800730c9  mov     eax, ebx
0x1800730cb  mov     rbx, [rsp+28h+arg_8]
0x1800730d0  add     rsp, 20h
0x1800730d4  pop     rdi
0x1800730d5  retn
```
