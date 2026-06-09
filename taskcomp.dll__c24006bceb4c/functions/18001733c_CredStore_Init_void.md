# CredStore::Init(void)

- ea: `0x18001733c`
- end: `0x18001744e`
- name: `?Init@CredStore@@SAJXZ`
- size: `274`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010efc`

## callees

- `0x180007488`
- `0x18001733c`
- `0x180017f08`
- `0x180017f74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001740a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001740a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180017413`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180017413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173bd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017362`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800173b3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017362`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800173b3`

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
0x18001733c  mov     [rsp+arg_8], rbx
0x180017341  push    rdi
0x180017342  sub     rsp, 20h
0x180017346  xor     r9d, r9d; SecurityDescriptorSize
0x180017349  mov     [rsp+28h+SecurityDescriptor], 0
0x180017352  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180017357  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;KRSD;;;BA)(A;OICI;KA;;;SY)"
0x18001735e  lea     edx, [r9+1]; StringSDRevision
0x180017362  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180017368  mov     edi, 80070000h
0x18001736d  test    eax, eax
0x18001736f  jnz     short loc_18001738B
0x180017371  call    cs:__imp_GetLastError
0x180017377  mov     ebx, eax
0x180017379  test    eax, eax
0x18001737b  jle     short loc_180017382
0x18001737d  movzx   ebx, ax
0x180017380  or      ebx, edi
0x180017382  test    ebx, ebx
0x180017384  jns     short loc_180017397
0x180017386  jmp     loc_18001743C
0x18001738b  mov     rax, [rsp+28h+SecurityDescriptor]
0x180017390  mov     cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA, rax; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x180017397  xor     r9d, r9d; SecurityDescriptorSize
0x18001739a  mov     [rsp+28h+SecurityDescriptor], 0
0x1800173a3  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x1800173a8  lea     rcx, aDPAOiciKaBaAOi; "D:P(A;OICI;KA;;;BA)(A;OICI;KA;;;SY)"
0x1800173af  lea     edx, [r9+1]; StringSDRevision
0x1800173b3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800173b9  test    eax, eax
0x1800173bb  jnz     short loc_1800173D4
0x1800173bd  call    cs:__imp_GetLastError
0x1800173c3  mov     ebx, eax
0x1800173c5  test    eax, eax
0x1800173c7  jle     short loc_1800173CE
0x1800173c9  movzx   ebx, ax
0x1800173cc  or      ebx, edi
0x1800173ce  test    ebx, ebx
0x1800173d0  js      short loc_18001743C
0x1800173d2  jmp     short loc_1800173E2
0x1800173d4  mov     rax, [rsp+28h+SecurityDescriptor]
0x1800173d9  xor     ebx, ebx
0x1800173db  mov     cs:?g_pConfigKeySecurity@StoreSecurity@tsched@@3PEAXEA, rax; void * tsched::StoreSecurity::g_pConfigKeySecurity
0x1800173e2  mov     ecx, 58h ; 'X'; Size
0x1800173e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800173ec  mov     [rsp+28h+SecurityDescriptor], rax
0x1800173f1  mov     rdi, rax
0x1800173f4  test    rax, rax
0x1800173f7  jz      short loc_18001742C
0x1800173f9  lea     rcx, [rax+30h]; lpCriticalSection
0x1800173fd  mov     qword ptr [rax+28h], 0
0x180017405  xor     r8d, r8d; Flags
0x180017408  xor     edx, edx; dwSpinCount
0x18001740a  call    cs:__imp_InitializeCriticalSectionEx
0x180017410  mov     rcx, rdi; lpCriticalSection
0x180017413  call    cs:__imp_InitializeCriticalSection
0x180017419  mov     cs:?g_pCommonStore@CredStore@@0PEAV1@EA, rdi; CredStore * CredStore::g_pCommonStore
0x180017420  test    rdi, rdi
0x180017423  jz      short loc_180017437
0x180017425  call    ?Upgrade@CredStore@@AEAAJXZ; CredStore::Upgrade(void)
0x18001742a  jmp     short loc_180017441
0x18001742c  mov     cs:?g_pCommonStore@CredStore@@0PEAV1@EA, 0; CredStore * CredStore::g_pCommonStore
0x180017437  mov     ebx, 8007000Eh
0x18001743c  call    ?Uninit@CredStore@@SAJXZ; CredStore::Uninit(void)
0x180017441  mov     eax, ebx
0x180017443  mov     rbx, [rsp+28h+arg_8]
0x180017448  add     rsp, 20h
0x18001744c  pop     rdi
0x18001744d  retn
```
