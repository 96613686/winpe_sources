# Subscription::Subscription(SubscriptionManager &,ushort const *)

- ea: `0x180007c00`
- end: `0x180007e09`
- name: `??0Subscription@@QEAA@AEAVSubscriptionManager@@PEBG@Z`
- size: `521`
- prototype: `Subscription *__fastcall(Subscription *this, struct SubscriptionManager *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007b64`
- `0x18000a938`

## callees

- `0x180003810`
- `0x180003be8`
- `0x180003e6c`
- `0x180007c00`
- `0x180007e10`
- `0x180012424`
- `0x18001259c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007c43`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007c43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007d47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007d47`
- `ADVAPI32!PerfCreateInstance` at `0x180007cfa`
- `ADVAPI32!PerfCreateInstance` at `0x180007cfa`
- `ADVAPI32!PerfSetULongCounterValue` at `0x180007d9a`
- `ADVAPI32!PerfSetULongCounterValue` at `0x180007db1`
- `ADVAPI32!PerfSetULongCounterValue` at `0x180007d9a`
- `ADVAPI32!PerfSetULongCounterValue` at `0x180007db1`
- `ADVAPI32!PerfSetULongLongCounterValue` at `0x180007dc8`
- `ADVAPI32!PerfSetULongLongCounterValue` at `0x180007ddf`
- `ADVAPI32!PerfSetULongLongCounterValue` at `0x180007dc8`
- `ADVAPI32!PerfSetULongLongCounterValue` at `0x180007ddf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Subscription *__fastcall Subscription::Subscription(
        Subscription *this,
        struct SubscriptionManager *a2,
        const unsigned __int16 *a3)
{
  Subscription *v5; // r14
  __int64 v6; // rdx
  PPERF_COUNTERSET_INSTANCE Instance; // rax
  PPERF_COUNTERSET_INSTANCE *v8; // rbx
  _BYTE v10[16]; // [rsp+30h] [rbp-48h] BYREF
  HKEY v11; // [rsp+40h] [rbp-38h]
  HKEY phkResult; // [rsp+88h] [rbp+10h] BYREF
  PPERF_COUNTERSET_INSTANCE *v15; // [rsp+98h] [rbp+20h]

  v5 = this;
  *(_QWORD *)this = &wmi::RefBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &Subscription::`vftable';
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 16), 0, 0);
  std::wstring::wstring((__int64)v5 + 56, (__int64)a3);
  *((_BYTE *)v5 + 96) = 0;
  *((_QWORD *)v5 + 13) = a2;
  *((_QWORD *)v5 + 14) = 0;
  *((_QWORD *)v5 + 15) = 0;
  *((_QWORD *)v5 + 16) = 0;
  *((_QWORD *)v5 + 17) = 0;
  *((_DWORD *)v5 + 36) = 5;
  *((_QWORD *)v5 + 19) = 0;
  *((_QWORD *)v5 + 20) = 0;
  *((_QWORD *)v5 + 21) = 0;
  *((_QWORD *)v5 + 22) = 0;
  *((_QWORD *)v5 + 23) = 0;
  *((_DWORD *)v5 + 48) = 2000;
  SubscriptionGlobalsReader::SubscriptionGlobalsReader((SubscriptionGlobalsReader *)v10);
  RegReadMultiStringValue(v11, v6, (char *)v5 + 120);
  RegReadDWORDValue(v11, L"LasterrorRetryCount", (unsigned int *)v5 + 36);
  *((_QWORD *)v5 + 11) = 0;
  Instance = PerfCreateInstance(WecPerfCounter, &WEF_COLLECT_EVENTSGuid, a3, 0);
  v8 = (PPERF_COUNTERSET_INSTANCE *)((char *)v5 + 200);
  v15 = (PPERF_COUNTERSET_INSTANCE *)((char *)v5 + 200);
  *((_QWORD *)v5 + 25) = Instance;
  if ( Instance )
  {
    try
    {
      phkResult = 0;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector\\Globals",
              0,
              0x20019u,
              &phkResult) )
        RegReadDWORDValue(phkResult, L"PerfBatchReportInterval", (unsigned int *)v5 + 48);
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
    }
    catch ( ... )
    {
      v5 = this;
      v8 = v15;
    }
    PerfSetULongCounterValue(WecPerfCounter, *v8, 3u, 0);
    PerfSetULongCounterValue(WecPerfCounter, *v8, 4u, 0);
    PerfSetULongLongCounterValue(WecPerfCounter, *v8, 1u, 0);
    PerfSetULongLongCounterValue(WecPerfCounter, *v8, 2u, 0);
  }
  ConfigBase::~ConfigBase((ConfigBase *)v10);
  return v5;
}

```

## disassembly

```asm
0x180007c00  mov     [rsp+arg_10], rbx
0x180007c05  mov     [rsp+arg_0], rcx
0x180007c0a  push    rsi
0x180007c0b  push    rdi
0x180007c0c  push    r12
0x180007c0e  push    r14
0x180007c10  push    r15
0x180007c12  sub     rsp, 50h
0x180007c16  mov     rsi, r8
0x180007c19  mov     rbx, rdx
0x180007c1c  mov     r14, rcx
0x180007c1f  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180007c26  mov     [rcx], rax
0x180007c29  xor     r12d, r12d
0x180007c2c  mov     [rcx+8], r12d
0x180007c30  lea     rax, ??_7Subscription@@6B@; const Subscription::`vftable'
0x180007c37  mov     [rcx], rax
0x180007c3a  add     rcx, 10h; lpCriticalSection
0x180007c3e  xor     r8d, r8d; Flags
0x180007c41  xor     edx, edx; dwSpinCount
0x180007c43  call    cs:__imp_InitializeCriticalSectionEx
0x180007c49  nop
0x180007c4a  lea     rcx, [r14+38h]
0x180007c4e  mov     rdx, rsi
0x180007c51  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180007c56  nop
0x180007c57  mov     [r14+60h], r12b
0x180007c5b  mov     [r14+68h], rbx
0x180007c5f  mov     [r14+70h], r12
0x180007c63  mov     [r14+78h], r12
0x180007c67  mov     [r14+80h], r12
0x180007c6e  mov     [r14+88h], r12
0x180007c75  lea     rbx, [r14+90h]
0x180007c7c  mov     dword ptr [rbx], 5
0x180007c82  mov     [r14+98h], r12
0x180007c89  mov     [r14+0A0h], r12
0x180007c90  mov     [r14+0A8h], r12
0x180007c97  mov     [r14+0B0h], r12
0x180007c9e  mov     [r14+0B8h], r12
0x180007ca5  lea     r15, [r14+0C0h]
0x180007cac  mov     dword ptr [r15], 7D0h
0x180007cb3  lea     rcx, [rsp+78h+var_48]; this
0x180007cb8  call    ??0SubscriptionGlobalsReader@@QEAA@XZ; SubscriptionGlobalsReader::SubscriptionGlobalsReader(void)
0x180007cbd  nop
0x180007cbe  lea     r8, [r14+78h]
0x180007cc2  mov     rcx, [rsp+78h+var_38]
0x180007cc7  call    ?RegReadMultiStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; RegReadMultiStringValue(HKEY__ *,ushort const *,std::vector<std::wstring> &)
0x180007ccc  mov     r8, rbx; unsigned int *
0x180007ccf  lea     rdx, aLasterrorretry; "LasterrorRetryCount"
0x180007cd6  mov     rcx, [rsp+78h+var_38]; HKEY
0x180007cdb  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180007ce0  xor     eax, eax
0x180007ce2  mov     [r14+58h], rax
0x180007ce6  xor     r9d, r9d; Id
0x180007ce9  mov     r8, rsi; Name
0x180007cec  lea     rdx, WEF_COLLECT_EVENTSGuid; CounterSetGuid
0x180007cf3  mov     rcx, cs:WecPerfCounter; ProviderHandle
0x180007cfa  call    cs:__imp_PerfCreateInstance
0x180007d00  lea     rbx, [r14+0C8h]
0x180007d07  mov     [rsp+78h+arg_18], rbx
0x180007d0f  mov     [rbx], rax
0x180007d12  test    rax, rax
0x180007d15  jz      loc_180007DE6
0x180007d1b  mov     [rsp+78h+arg_8], r12
0x180007d23  lea     rax, [rsp+78h+arg_8]
0x180007d2b  mov     [rsp+78h+phkResult], rax; phkResult
0x180007d30  mov     r9d, 20019h; samDesired
0x180007d36  xor     r8d, r8d; ulOptions
0x180007d39  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180007d40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007d47  call    cs:__imp_RegOpenKeyExW
0x180007d4d  test    eax, eax
0x180007d4f  jnz     short loc_180007D69
0x180007d51  mov     r8, r15; unsigned int *
0x180007d54  lea     rdx, aPerfbatchrepor; "PerfBatchReportInterval"
0x180007d5b  mov     rcx, [rsp+78h+arg_8]; HKEY
0x180007d63  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180007d68  nop
0x180007d69  lea     rcx, [rsp+78h+arg_8]; this
0x180007d71  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180007d76  nop
0x180007d77  jmp     short loc_180007D89
0x180007d79  mov     r14, [rsp+78h+arg_0]
0x180007d81  mov     rbx, [rsp+78h+arg_18]
0x180007d89  xor     r9d, r9d; Value
0x180007d8c  lea     r8d, [r9+3]; CounterId
0x180007d90  mov     rdx, [rbx]; Instance
0x180007d93  mov     rcx, cs:WecPerfCounter; Provider
0x180007d9a  call    cs:__imp_PerfSetULongCounterValue
0x180007da0  xor     r9d, r9d; Value
0x180007da3  lea     r8d, [r9+4]; CounterId
0x180007da7  mov     rdx, [rbx]; Instance
0x180007daa  mov     rcx, cs:WecPerfCounter; Provider
0x180007db1  call    cs:__imp_PerfSetULongCounterValue
0x180007db7  xor     r9d, r9d; Value
0x180007dba  lea     r8d, [r9+1]; CounterId
0x180007dbe  mov     rdx, [rbx]; Instance
0x180007dc1  mov     rcx, cs:WecPerfCounter; Provider
0x180007dc8  call    cs:__imp_PerfSetULongLongCounterValue
0x180007dce  xor     r9d, r9d; Value
0x180007dd1  lea     r8d, [r9+2]; CounterId
0x180007dd5  mov     rdx, [rbx]; Instance
0x180007dd8  mov     rcx, cs:WecPerfCounter; Provider
0x180007ddf  call    cs:__imp_PerfSetULongLongCounterValue
0x180007de5  nop
0x180007de6  lea     rcx, [rsp+78h+var_48]; this
0x180007deb  call    ??1ConfigBase@@UEAA@XZ; ConfigBase::~ConfigBase(void)
0x180007df0  nop
0x180007df1  mov     rax, r14
0x180007df4  mov     rbx, [rsp+78h+arg_10]
0x180007dfc  add     rsp, 50h
0x180007e00  pop     r15
0x180007e02  pop     r14
0x180007e04  pop     r12
0x180007e06  pop     rdi
0x180007e07  pop     rsi
0x180007e08  retn
```
