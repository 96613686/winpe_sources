# CWLIDCCHelper::SetClockReliabilityDataHelper(IExecutionContextLite *,HKEY__ *)

- ea: `0x18005100c`
- end: `0x180051190`
- name: `?SetClockReliabilityDataHelper@CWLIDCCHelper@@CAJPEAVIExecutionContextLite@@PEAUHKEY__@@@Z`
- size: `388`
- prototype: `static int(struct IExecutionContextLite *, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180050d58`

## callees

- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x180016c0c`
- `0x18005100c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800510f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800510f8`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180051074`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180051074`

## string_xrefs

- `0x180051138`: `hr = registryHelper.WriteBufferToRegistry( hKey, nullptr, WLID_REG_TICKCOUNT, REG_QWORD, reinterpret_cast<PBYTE>(&ticksSinceBoot), sizeof(ticksSinceBoot))`
- `0x1800510b0`: `hr = registryHelper.WriteBufferToRegistry( hKey, nullptr, WLID_REG_CLOCKTIME_SEC, REG_QWORD, reinterpret_cast<PBYTE>(&currentTime), sizeof(currentTime))`
- `0x1800510de`: `WriteBufferToRegistry wrote current time = %I64d`
- `0x180051158`: `WriteBufferToRegistry wrote tick count = %I64d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWLIDCCHelper::SetClockReliabilityDataHelper(struct IExecutionContextLite *a1, HKEY a2)
{
  int v3; // eax
  int v4; // eax
  unsigned int v5; // ebx
  char *v7; // [rsp+20h] [rbp-50h]
  unsigned __int8 v8[8]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v9[5]; // [rsp+48h] [rbp-28h] BYREF
  int v10; // [rsp+90h] [rbp+20h] BYREF
  __time64_t Time; // [rsp+A0h] [rbp+30h] BYREF
  struct IExecutionContextLite *v12; // [rsp+A8h] [rbp+38h] BYREF

  v10 = 0;
  v12 = a1;
  v9[0] = "CWLIDCCHelper::SetClockReliabilityDataHelper";
  v9[1] = &v10;
  v9[2] = 0;
  v9[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
    "CWLIDCCHelper::SetClockReliabilityDataHelper",
    (const char *)0x2E4,
    0,
    (const unsigned __int16 *)v7);
  Time = 0;
  _time64(&Time);
  v3 = RegistryHelper::WriteBufferToRegistry(
         (RegistryHelper *)&v12,
         a2,
         0,
         L"ClockTimeSeconds",
         0xBu,
         (unsigned __int8 *)&Time,
         8u);
  v10 = v3;
  if ( v3 >= 0 )
  {
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
      0x2F2u,
      L"WriteBufferToRegistry wrote current time = %I64d",
      Time);
    *(_QWORD *)v8 = GetTickCount64();
    v4 = RegistryHelper::WriteBufferToRegistry((RegistryHelper *)&v12, a2, 0, L"TickCount", 0xBu, v8, 8u);
    v10 = v4;
    if ( v4 >= 0 )
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
        0x2FFu,
        L"WriteBufferToRegistry wrote tick count = %I64d",
        *(_QWORD *)v8);
    else
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
        "CWLIDCCHelper::SetClockReliabilityDataHelper",
        0x2FDu,
        v4,
        "hr = registryHelper.WriteBufferToRegistry( hKey, nullptr, WLID_REG_TICKCOUNT, REG_QWORD, reinterpret_cast<PBYTE>"
        "(&ticksSinceBoot), sizeof(ticksSinceBoot))");
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
      "CWLIDCCHelper::SetClockReliabilityDataHelper",
      0x2F0u,
      v3,
      "hr = registryHelper.WriteBufferToRegistry( hKey, nullptr, WLID_REG_CLOCKTIME_SEC, REG_QWORD, reinterpret_cast<PBYT"
      "E>(&currentTime), sizeof(currentTime))");
  }
  v5 = v10;
  CTraceFuncW<long>::~CTraceFuncW<long>(v9);
  return v5;
}

```

## disassembly

```asm
0x18005100c  mov     [rsp-18h+arg_8], rbx
0x180051011  push    rbp
0x180051012  push    rsi
0x180051013  push    rdi
0x180051014  mov     rbp, rsp
0x180051017  sub     rsp, 70h
0x18005101b  mov     rbx, rdx
0x18005101e  mov     [rbp+arg_0], 0
0x180051025  mov     [rbp+arg_18], rcx
0x180051029  lea     rsi, aCwlidcchelperS; "CWLIDCCHelper::SetClockReliabilityDataH"...
0x180051030  mov     [rbp+var_28], rsi
0x180051034  lea     rax, [rbp+arg_0]
0x180051038  mov     [rbp+var_20], rax
0x18005103c  mov     [rbp+var_18], 0
0x180051044  mov     [rbp+var_10], 0
0x18005104c  xor     r9d, r9d; unsigned int
0x18005104f  mov     r8d, 2E4h; char *
0x180051055  mov     rdx, rsi; char *
0x180051058  lea     rdi, aOnecoreuapDsEx_18; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18005105f  mov     rcx, rdi; this
0x180051062  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180051067  nop
0x180051068  mov     [rbp+Time], 0
0x180051070  lea     rcx, [rbp+Time]; Time
0x180051074  call    cs:__imp__time64
0x18005107a  mov     [rsp+70h+var_40], 8; unsigned int
0x180051082  lea     rax, [rbp+Time]
0x180051086  mov     [rsp+70h+var_48], rax; unsigned __int8 *
0x18005108b  mov     dword ptr [rsp+70h+var_50], 0Bh; unsigned int
0x180051093  lea     r9, aClocktimesecon; "ClockTimeSeconds"
0x18005109a  xor     r8d, r8d; unsigned __int16 *
0x18005109d  mov     rdx, rbx; HKEY
0x1800510a0  lea     rcx, [rbp+arg_18]; this
0x1800510a4  call    ?WriteBufferToRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAEK@Z; RegistryHelper::WriteBufferToRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)
0x1800510a9  mov     [rbp+arg_0], eax
0x1800510ac  test    eax, eax
0x1800510ae  jns     short loc_1800510D5
0x1800510b0  lea     r8, aHrRegistryhelp_2; "hr = registryHelper.WriteBufferToRegist"...
0x1800510b7  mov     [rsp+70h+var_50], r8; char *
0x1800510bc  mov     r8d, 2F0h; unsigned int
0x1800510c2  mov     r9d, eax; int
0x1800510c5  mov     rdx, rsi; char *
0x1800510c8  mov     rcx, rdi; char *
0x1800510cb  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800510d0  jmp     loc_180051172
0x1800510d5  mov     rax, [rbp+Time]
0x1800510d9  mov     [rsp+70h+var_50], rax
0x1800510de  lea     r9, aWritebuffertor; "WriteBufferToRegistry wrote current tim"...
0x1800510e5  mov     r8d, 2F2h; unsigned int
0x1800510eb  mov     rdx, rdi; char *
0x1800510ee  mov     ecx, 5; unsigned __int8
0x1800510f3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800510f8  call    cs:__imp_GetTickCount64
0x1800510fe  mov     qword ptr [rbp+var_30], rax
0x180051102  mov     [rsp+70h+var_40], 8; unsigned int
0x18005110a  lea     rax, [rbp+var_30]
0x18005110e  mov     [rsp+70h+var_48], rax; unsigned __int8 *
0x180051113  mov     dword ptr [rsp+70h+var_50], 0Bh; unsigned int
0x18005111b  lea     r9, aTickcount; "TickCount"
0x180051122  xor     r8d, r8d; unsigned __int16 *
0x180051125  mov     rdx, rbx; HKEY
0x180051128  lea     rcx, [rbp+arg_18]; this
0x18005112c  call    ?WriteBufferToRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAEK@Z; RegistryHelper::WriteBufferToRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)
0x180051131  mov     [rbp+arg_0], eax
0x180051134  test    eax, eax
0x180051136  jns     short loc_18005114F
0x180051138  lea     rcx, aHrRegistryhelp_7; "hr = registryHelper.WriteBufferToRegist"...
0x18005113f  mov     [rsp+70h+var_50], rcx
0x180051144  mov     r8d, 2FDh
0x18005114a  jmp     loc_1800510C2
0x18005114f  mov     rax, qword ptr [rbp+var_30]
0x180051153  mov     [rsp+70h+var_50], rax
0x180051158  lea     r9, aWritebuffertor_0; "WriteBufferToRegistry wrote tick count "...
0x18005115f  mov     r8d, 2FFh; unsigned int
0x180051165  mov     rdx, rdi; char *
0x180051168  mov     ecx, 5; unsigned __int8
0x18005116d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180051172  mov     ebx, [rbp+arg_0]
0x180051175  lea     rcx, [rbp+var_28]
0x180051179  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18005117e  mov     eax, ebx
0x180051180  mov     rbx, [rsp+70h+arg_8]
0x180051188  add     rsp, 70h
0x18005118c  pop     rdi
0x18005118d  pop     rsi
0x18005118e  pop     rbp
0x18005118f  retn
```
