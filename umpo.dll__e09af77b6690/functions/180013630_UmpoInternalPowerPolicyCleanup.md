# UmpoInternalPowerPolicyCleanup

- ea: `0x180013630`
- end: `0x180013801`
- name: `UmpoInternalPowerPolicyCleanup`
- size: `465`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015280`

## callees

- `0x18000db88`
- `0x18000e844`
- `0x18000f3dc`
- `0x180013630`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180013731`
- `ntdll!RtlFreeHeap` at `0x180013731`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800137c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800137e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800137c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800137e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013660`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001367e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001369c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800136ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800136d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800136f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001377e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001379e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013660`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001367e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001369c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800136ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800136d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800136f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001377e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001379e`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180013710`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180013710`

## pseudocode

```c
__int64 UmpoInternalPowerPolicyCleanup()
{
  __int64 v0; // rdi
  __int64 v1; // rbx
  HKEY v2; // rcx
  HKEY v3; // rcx

  UmpoPowerPolicyInitialized = 0;
  LODWORD(UmpoOverlaySchemeSuspendMask) = 0;
  if ( (unsigned __int64)UmpoSystemPowerRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(UmpoSystemPowerRootKey);
    UmpoSystemPowerRootKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)UmpoPpmProfileEventsRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(UmpoPpmProfileEventsRootKey);
    UmpoPpmProfileEventsRootKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)UmpoUserPowerRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(UmpoUserPowerRootKey);
    UmpoUserPowerRootKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)UmpoPowerSecurityDescriptorRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(UmpoPowerSecurityDescriptorRootKey);
    UmpoPowerSecurityDescriptorRootKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)UmpoPowerControlKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(UmpoPowerControlKey);
    UmpoPowerControlKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)UmpoUserPowerStateSepRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(UmpoUserPowerStateSepRootKey);
    UmpoUserPowerStateSepRootKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( UmpoUserPowerTlsSlot != -1 )
  {
    TlsFree(UmpoUserPowerTlsSlot);
    UmpoUserPowerTlsSlot = -1;
  }
  if ( UmpoDefaultSecurityDescriptor )
  {
    RtlFreeHeap(UmpoHeapHandle, 0, (PVOID)UmpoDefaultSecurityDescriptor);
    UmpoDefaultSecurityDescriptor = 0;
  }
  if ( UmpoIsPolicyManagerSupported )
  {
    UmpoInternalCleanupAdvancedPowerSettings();
  }
  else if ( UmpoAdvancedPowerSettingWnfSubscription )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v0 = 0;
  v1 = 0;
  do
  {
    v2 = *(HKEY *)((char *)&UmpoPowerSubGroupCache + v1 + 24);
    if ( (unsigned __int64)v2 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(v2);
      *(__int64 *)((char *)&UmpoPowerSubGroupCache + v1 + 24) = -1;
    }
    v3 = *(HKEY *)((char *)&UmpoPowerSettingCache + v1 + 24);
    if ( (unsigned __int64)v3 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(v3);
      *(__int64 *)((char *)&UmpoPowerSettingCache + v1 + 24) = -1;
    }
    ++v0;
    v1 += 32;
  }
  while ( v0 != 2 );
  if ( byte_180024DF0 )
  {
    DeleteCriticalSection(&CriticalSection);
    byte_180024DF0 = 0;
  }
  if ( byte_180024D30 )
  {
    DeleteCriticalSection(&stru_180024D08);
    byte_180024D30 = 0;
  }
  return UmpoCleanupPowerSettingOverrides();
}

```

## disassembly

```asm
0x180013630  push    rbx
0x180013632  push    rbp
0x180013633  push    rdi
0x180013634  push    r14
0x180013636  sub     rsp, 28h
0x18001363a  mov     rcx, cs:UmpoSystemPowerRootKey; hKey
0x180013641  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180013645  mov     cs:UmpoPowerPolicyInitialized, 0
0x18001364c  mov     cs:UmpoOverlaySchemeSuspendMask, 0
0x180013656  lea     rax, [rcx-1]
0x18001365a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001365e  ja      short loc_18001366D
0x180013660  call    cs:__imp_RegCloseKey
0x180013666  mov     cs:UmpoSystemPowerRootKey, rbp
0x18001366d  mov     rcx, cs:UmpoPpmProfileEventsRootKey; hKey
0x180013674  lea     rax, [rcx-1]
0x180013678  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001367c  ja      short loc_18001368B
0x18001367e  call    cs:__imp_RegCloseKey
0x180013684  mov     cs:UmpoPpmProfileEventsRootKey, rbp
0x18001368b  mov     rcx, cs:UmpoUserPowerRootKey; hKey
0x180013692  lea     rax, [rcx-1]
0x180013696  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001369a  ja      short loc_1800136A9
0x18001369c  call    cs:__imp_RegCloseKey
0x1800136a2  mov     cs:UmpoUserPowerRootKey, rbp
0x1800136a9  mov     rcx, cs:UmpoPowerSecurityDescriptorRootKey; hKey
0x1800136b0  lea     rax, [rcx-1]
0x1800136b4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800136b8  ja      short loc_1800136C7
0x1800136ba  call    cs:__imp_RegCloseKey
0x1800136c0  mov     cs:UmpoPowerSecurityDescriptorRootKey, rbp
0x1800136c7  mov     rcx, cs:UmpoPowerControlKey; hKey
0x1800136ce  lea     rax, [rcx-1]
0x1800136d2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800136d6  ja      short loc_1800136E5
0x1800136d8  call    cs:__imp_RegCloseKey
0x1800136de  mov     cs:UmpoPowerControlKey, rbp
0x1800136e5  mov     rcx, cs:UmpoUserPowerStateSepRootKey; hKey
0x1800136ec  lea     rax, [rcx-1]
0x1800136f0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800136f4  ja      short loc_180013703
0x1800136f6  call    cs:__imp_RegCloseKey
0x1800136fc  mov     cs:UmpoUserPowerStateSepRootKey, rbp
0x180013703  mov     ecx, cs:UmpoUserPowerTlsSlot; dwTlsIndex
0x180013709  or      ebx, 0FFFFFFFFh
0x18001370c  cmp     ecx, ebx
0x18001370e  jz      short loc_18001371C
0x180013710  call    cs:__imp_TlsFree
0x180013716  mov     cs:UmpoUserPowerTlsSlot, ebx
0x18001371c  mov     r8, cs:UmpoDefaultSecurityDescriptor; P
0x180013723  test    r8, r8
0x180013726  jz      short loc_180013742
0x180013728  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x18001372f  xor     edx, edx; Flags
0x180013731  call    cs:__imp_RtlFreeHeap
0x180013737  mov     cs:UmpoDefaultSecurityDescriptor, 0
0x180013742  cmp     cs:UmpoIsPolicyManagerSupported, 0
0x180013749  jz      short loc_180013752
0x18001374b  call    UmpoInternalCleanupAdvancedPowerSettings
0x180013750  jmp     short loc_180013761
0x180013752  cmp     cs:UmpoAdvancedPowerSettingWnfSubscription, 0
0x18001375a  jz      short loc_180013761
0x18001375c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180013761  xor     edi, edi
0x180013763  lea     r14, __ImageBase
0x18001376a  xor     ebx, ebx
0x18001376c  mov     rcx, [rbx+r14+24D98h]; hKey
0x180013774  lea     rax, [rcx-1]
0x180013778  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001377c  ja      short loc_18001378C
0x18001377e  call    cs:__imp_RegCloseKey
0x180013784  mov     [rbx+r14+24D98h], rbp
0x18001378c  mov     rcx, [rbx+r14+24CD8h]; hKey
0x180013794  lea     rax, [rcx-1]
0x180013798  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001379c  ja      short loc_1800137AC
0x18001379e  call    cs:__imp_RegCloseKey
0x1800137a4  mov     [rbx+r14+24CD8h], rbp
0x1800137ac  inc     rdi
0x1800137af  add     rbx, 20h ; ' '
0x1800137b3  cmp     rdi, 2
0x1800137b7  jnz     short loc_18001376C
0x1800137b9  cmp     cs:byte_180024DF0, 0
0x1800137c0  jz      short loc_1800137D6
0x1800137c2  lea     rcx, CriticalSection; lpCriticalSection
0x1800137c9  call    cs:__imp_DeleteCriticalSection
0x1800137cf  mov     cs:byte_180024DF0, 0
0x1800137d6  cmp     cs:byte_180024D30, 0
0x1800137dd  jz      short loc_1800137F3
0x1800137df  lea     rcx, stru_180024D08; lpCriticalSection
0x1800137e6  call    cs:__imp_DeleteCriticalSection
0x1800137ec  mov     cs:byte_180024D30, 0
0x1800137f3  add     rsp, 28h
0x1800137f7  pop     r14
0x1800137f9  pop     rdi
0x1800137fa  pop     rbp
0x1800137fb  pop     rbx
0x1800137fc  jmp     UmpoCleanupPowerSettingOverrides
```
