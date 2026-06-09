# TestHookPolicyReader::AreTestHooksEnabled(void)

- ea: `0x180018ac8`
- end: `0x180018bbb`
- name: `?AreTestHooksEnabled@TestHookPolicyReader@@SA_NXZ`
- size: `243`
- prototype: `char(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180010c1c`
- `0x1800188fc`
- `0x18001a320`

## callees

- `0x180018ac8`
- `0x180018bc4`
- `0x1800196a4`
- `0x180019ff4`
- `0x180026f9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018b1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018b1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018b33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018b3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018b33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018b3e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018b47`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018b47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018b63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018b81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018b63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018b81`

## pseudocode

```c
char TestHookPolicyReader::AreTestHooksEnabled(void)
{
  char IsEnabled; // al
  const wchar_t *v1; // rdx
  const wchar_t *v2; // rcx
  char v3; // bl
  char result; // al
  RTL_SRWLOCK *v5; // [rsp+40h] [rbp+8h] BYREF

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks>::GetImpl'::`2'::impl);
  v3 = 0;
  LOBYTE(v5) = 0;
  if ( !IsEnabled )
  {
    if ( (int)PolicyRegistryHelper::HKLMKeyExists(v2, v1, (bool *)&v5) >= 0 )
    {
      result = 1;
      if ( (_BYTE)v5 )
        return result;
    }
    return v3;
  }
  PolicyRegistryHelper::HKLMKeyExists(v2, v1, (bool *)&v5);
  if ( !(_BYTE)v5 )
  {
    if ( byte_18004EDD9 )
      byte_18004EDD9 = 0;
    return 0;
  }
  AcquireSRWLockShared(&TestHookPolicyReader::s_testHooksInitLock);
  if ( byte_18004EDD9 )
  {
    v3 = TestHookPolicyReader::s_areTestHooksEnabled;
    ReleaseSRWLockShared(&TestHookPolicyReader::s_testHooksInitLock);
    return v3;
  }
  ReleaseSRWLockShared(&TestHookPolicyReader::s_testHooksInitLock);
  AcquireSRWLockExclusive(&TestHookPolicyReader::s_testHooksInitLock);
  v5 = &TestHookPolicyReader::s_testHooksInitLock;
  if ( byte_18004EDD9 )
  {
    v3 = TestHookPolicyReader::s_areTestHooksEnabled;
    ReleaseSRWLockExclusive(&TestHookPolicyReader::s_testHooksInitLock);
    return v3;
  }
  TestHookPolicyReader::s_areTestHooksEnabled = TestHookPolicyReader::ValidateAUTestCab();
  byte_18004EDD9 = 1;
  ReleaseSRWLockExclusive(&TestHookPolicyReader::s_testHooksInitLock);
  if ( !byte_18004EDD9 )
    std::_Throw_bad_optional_access();
  return TestHookPolicyReader::s_areTestHooksEnabled;
}

```

## disassembly

```asm
0x180018ac8  mov     [rsp+arg_8], rbx
0x180018acd  push    rdi
0x180018ace  sub     rsp, 30h
0x180018ad2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks> `wil::Feature<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks>::GetImpl(void)'::`2'::impl
0x180018ad9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks>::__private_IsEnabled(void)
0x180018ade  xor     ebx, ebx
0x180018ae0  mov     byte ptr [rsp+38h+arg_0], bl
0x180018ae4  lea     r8, [rsp+38h+arg_0]; bool *
0x180018ae9  test    al, al
0x180018aeb  jz      loc_180018B97
0x180018af1  call    ?HKLMKeyExists@PolicyRegistryHelper@@SAJPEB_W0AEA_N@Z; PolicyRegistryHelper::HKLMKeyExists(wchar_t const *,wchar_t const *,bool &)
0x180018af6  cmp     byte ptr [rsp+38h+arg_0], bl
0x180018afa  jnz     short loc_180018B11
0x180018afc  cmp     cs:byte_18004EDD9, bl
0x180018b02  jz      short loc_180018B0A
0x180018b04  mov     cs:byte_18004EDD9, bl
0x180018b0a  xor     al, al
0x180018b0c  jmp     loc_180018BAA
0x180018b11  lea     rdi, ?s_testHooksInitLock@TestHookPolicyReader@@2Vsrwlock@wil@@A; wil::srwlock TestHookPolicyReader::s_testHooksInitLock
0x180018b18  mov     rcx, rdi; SRWLock
0x180018b1b  call    cs:__imp_AcquireSRWLockShared
0x180018b21  nop
0x180018b22  cmp     cs:byte_18004EDD9, bl
0x180018b28  jz      short loc_180018B3B
0x180018b2a  mov     bl, cs:?s_areTestHooksEnabled@TestHookPolicyReader@@2V?$optional@_N@std@@A; std::optional<bool> TestHookPolicyReader::s_areTestHooksEnabled
0x180018b30  mov     rcx, rdi; SRWLock
0x180018b33  call    cs:__imp_ReleaseSRWLockShared
0x180018b39  jmp     short loc_180018BA8
0x180018b3b  mov     rcx, rdi; SRWLock
0x180018b3e  call    cs:__imp_ReleaseSRWLockShared
0x180018b44  mov     rcx, rdi; SRWLock
0x180018b47  call    cs:__imp_AcquireSRWLockExclusive
0x180018b4d  mov     [rsp+38h+arg_0], rdi
0x180018b52  cmp     cs:byte_18004EDD9, bl
0x180018b58  jz      short loc_180018B6B
0x180018b5a  mov     bl, cs:?s_areTestHooksEnabled@TestHookPolicyReader@@2V?$optional@_N@std@@A; std::optional<bool> TestHookPolicyReader::s_areTestHooksEnabled
0x180018b60  mov     rcx, rdi; SRWLock
0x180018b63  call    cs:__imp_ReleaseSRWLockExclusive
0x180018b69  jmp     short loc_180018BA8
0x180018b6b  call    ?ValidateAUTestCab@TestHookPolicyReader@@CA_NXZ; TestHookPolicyReader::ValidateAUTestCab(void)
0x180018b70  mov     cs:?s_areTestHooksEnabled@TestHookPolicyReader@@2V?$optional@_N@std@@A, al; std::optional<bool> TestHookPolicyReader::s_areTestHooksEnabled
0x180018b76  mov     al, 1
0x180018b78  mov     cs:byte_18004EDD9, al
0x180018b7e  mov     rcx, rdi; SRWLock
0x180018b81  call    cs:__imp_ReleaseSRWLockExclusive
0x180018b87  cmp     cs:byte_18004EDD9, bl
0x180018b8d  jz      short loc_180018BB5
0x180018b8f  mov     al, cs:?s_areTestHooksEnabled@TestHookPolicyReader@@2V?$optional@_N@std@@A; std::optional<bool> TestHookPolicyReader::s_areTestHooksEnabled
0x180018b95  jmp     short loc_180018BAA
0x180018b97  call    ?HKLMKeyExists@PolicyRegistryHelper@@SAJPEB_W0AEA_N@Z; PolicyRegistryHelper::HKLMKeyExists(wchar_t const *,wchar_t const *,bool &)
0x180018b9c  test    eax, eax
0x180018b9e  js      short loc_180018BA8
0x180018ba0  cmp     byte ptr [rsp+38h+arg_0], bl
0x180018ba4  mov     al, 1
0x180018ba6  jnz     short loc_180018BAA
0x180018ba8  mov     al, bl
0x180018baa  mov     rbx, [rsp+38h+arg_8]
0x180018baf  add     rsp, 30h
0x180018bb3  pop     rdi
0x180018bb4  retn
0x180018bb5  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
```
