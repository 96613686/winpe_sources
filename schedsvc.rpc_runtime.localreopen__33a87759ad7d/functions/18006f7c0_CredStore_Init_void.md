# CredStore::Init(void)

- ea: `0x18006f7c0`
- end: `0x18006f8d2`
- name: `?Init@CredStore@@SAJXZ`
- size: `274`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004f190`

## callees

- `0x180030f80`
- `0x18006f7c0`
- `0x18006fb64`
- `0x18006fbd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f7f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f7f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f841`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18006f88e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18006f88e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006f897`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006f897`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006f7e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006f837`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006f7e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006f837`

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
0x18006f7c0  mov     [rsp+arg_8], rbx
0x18006f7c5  push    rdi
0x18006f7c6  sub     rsp, 20h
0x18006f7ca  xor     r9d, r9d; SecurityDescriptorSize
0x18006f7cd  mov     [rsp+28h+SecurityDescriptor], 0
0x18006f7d6  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x18006f7db  lea     rcx, aDPAOiciKrsdBaA; "D:P(A;OICI;KRSD;;;BA)(A;OICI;KA;;;SY)"
0x18006f7e2  lea     edx, [r9+1]; StringSDRevision
0x18006f7e6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18006f7ec  mov     edi, 80070000h
0x18006f7f1  test    eax, eax
0x18006f7f3  jnz     short loc_18006F80F
0x18006f7f5  call    cs:__imp_GetLastError
0x18006f7fb  mov     ebx, eax
0x18006f7fd  test    eax, eax
0x18006f7ff  jle     short loc_18006F806
0x18006f801  movzx   ebx, ax
0x18006f804  or      ebx, edi
0x18006f806  test    ebx, ebx
0x18006f808  jns     short loc_18006F81B
0x18006f80a  jmp     loc_18006F8C0
0x18006f80f  mov     rax, [rsp+28h+SecurityDescriptor]
0x18006f814  mov     cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA, rax; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x18006f81b  xor     r9d, r9d; SecurityDescriptorSize
0x18006f81e  mov     [rsp+28h+SecurityDescriptor], 0
0x18006f827  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x18006f82c  lea     rcx, aDPAOiciKaBaAOi; "D:P(A;OICI;KA;;;BA)(A;OICI;KA;;;SY)"
0x18006f833  lea     edx, [r9+1]; StringSDRevision
0x18006f837  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18006f83d  test    eax, eax
0x18006f83f  jnz     short loc_18006F858
0x18006f841  call    cs:__imp_GetLastError
0x18006f847  mov     ebx, eax
0x18006f849  test    eax, eax
0x18006f84b  jle     short loc_18006F852
0x18006f84d  movzx   ebx, ax
0x18006f850  or      ebx, edi
0x18006f852  test    ebx, ebx
0x18006f854  js      short loc_18006F8C0
0x18006f856  jmp     short loc_18006F866
0x18006f858  mov     rax, [rsp+28h+SecurityDescriptor]
0x18006f85d  xor     ebx, ebx
0x18006f85f  mov     cs:?g_pConfigKeySecurity@StoreSecurity@tsched@@3PEAXEA, rax; void * tsched::StoreSecurity::g_pConfigKeySecurity
0x18006f866  mov     ecx, 58h ; 'X'; dwBytes
0x18006f86b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006f870  mov     [rsp+28h+SecurityDescriptor], rax
0x18006f875  mov     rdi, rax
0x18006f878  test    rax, rax
0x18006f87b  jz      short loc_18006F8B0
0x18006f87d  lea     rcx, [rax+30h]; lpCriticalSection
0x18006f881  mov     qword ptr [rax+28h], 0
0x18006f889  xor     r8d, r8d; Flags
0x18006f88c  xor     edx, edx; dwSpinCount
0x18006f88e  call    cs:__imp_InitializeCriticalSectionEx
0x18006f894  mov     rcx, rdi; lpCriticalSection
0x18006f897  call    cs:__imp_InitializeCriticalSection
0x18006f89d  mov     cs:?g_pCommonStore@CredStore@@0PEAV1@EA, rdi; CredStore * CredStore::g_pCommonStore
0x18006f8a4  test    rdi, rdi
0x18006f8a7  jz      short loc_18006F8BB
0x18006f8a9  call    ?Upgrade@CredStore@@AEAAJXZ; CredStore::Upgrade(void)
0x18006f8ae  jmp     short loc_18006F8C5
0x18006f8b0  mov     cs:?g_pCommonStore@CredStore@@0PEAV1@EA, 0; CredStore * CredStore::g_pCommonStore
0x18006f8bb  mov     ebx, 8007000Eh
0x18006f8c0  call    ?Uninit@CredStore@@SAJXZ; CredStore::Uninit(void)
0x18006f8c5  mov     eax, ebx
0x18006f8c7  mov     rbx, [rsp+28h+arg_8]
0x18006f8cc  add     rsp, 20h
0x18006f8d0  pop     rdi
0x18006f8d1  retn
```
