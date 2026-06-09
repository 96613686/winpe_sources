# Subscription::~Subscription(void)

- ea: `0x1800081e4`
- end: `0x180008327`
- name: `??1Subscription@@UEAA@XZ`
- size: `323`
- prototype: `void __fastcall(Subscription *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180008160`
- `0x180008188`
- `0x180008770`
- `0x180020e26`
- `0x18002146c`

## callees

- `0x180003e6c`
- `0x18000526c`
- `0x1800062d4`
- `0x180006370`
- `0x1800081e4`
- `0x18000ef44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000830e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000830e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800082cb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800082cb`
- `ADVAPI32!PerfSetULongCounterValue` at `0x18000824b`
- `ADVAPI32!PerfSetULongCounterValue` at `0x180008266`
- `ADVAPI32!PerfSetULongCounterValue` at `0x18000824b`
- `ADVAPI32!PerfSetULongCounterValue` at `0x180008266`
- `ADVAPI32!PerfSetULongLongCounterValue` at `0x180008281`
- `ADVAPI32!PerfSetULongLongCounterValue` at `0x18000829c`
- `ADVAPI32!PerfSetULongLongCounterValue` at `0x180008281`
- `ADVAPI32!PerfSetULongLongCounterValue` at `0x18000829c`
- `ADVAPI32!PerfDeleteInstance` at `0x1800082b0`
- `ADVAPI32!PerfDeleteInstance` at `0x1800082b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Subscription::~Subscription(Subscription *this)
{
  Subscription *v1; // rdi
  char **v2; // rsi
  char *v3; // rcx
  HKEY v4; // rbx
  struct _PERF_COUNTERSET_INSTANCE *v5; // rdx
  __int64 v6; // rdx
  HKEY v9; // [rsp+48h] [rbp+10h] BYREF
  char **v10; // [rsp+50h] [rbp+18h]

  v1 = this;
  *(_QWORD *)this = &Subscription::`vftable';
  v2 = (char **)((char *)this + 56);
  v10 = (char **)((char *)this + 56);
  if ( *((_QWORD *)this + 10) < 8u )
    v3 = (char *)this + 56;
  else
    v3 = *v2;
  try
  {
    v4 = OpenSubscriptionEventSourceKey((__int64)v3, 0, 0x20006u, 0);
    v9 = v4;
    v5 = (struct _PERF_COUNTERSET_INSTANCE *)*((_QWORD *)v1 + 25);
    if ( v5 )
    {
      PerfSetULongCounterValue(WecPerfCounter, v5, 3u, 0);
      PerfSetULongCounterValue(WecPerfCounter, *((PPERF_COUNTERSET_INSTANCE *)v1 + 25), 4u, 0);
      PerfSetULongLongCounterValue(WecPerfCounter, *((PPERF_COUNTERSET_INSTANCE *)v1 + 25), 1u, 0);
      PerfSetULongLongCounterValue(WecPerfCounter, *((PPERF_COUNTERSET_INSTANCE *)v1 + 25), 2u, 0);
      PerfDeleteInstance(WecPerfCounter, *((PPERF_COUNTERSET_INSTANCE *)v1 + 25));
      *((_QWORD *)v1 + 25) = 0;
    }
    RegDeleteValueW(v4, L"FirstEventBatchTime");
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&v9);
  }
  catch ( ... )
  {
    v1 = this;
    v2 = v10;
  }
  std::vector<std::wstring>::_Tidy((char *)v1 + 120);
  wmi::AutoRef<AbstractEventProcessor>::Release((char *)v1 + 112);
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v2, v6, 0);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 16));
  *(_QWORD *)v1 = &wmi::RefBase::`vftable';
}

```

## disassembly

```asm
0x1800081e4  mov     [rsp+arg_0], rcx
0x1800081e9  push    rbx
0x1800081ea  push    rsi
0x1800081eb  push    rdi
0x1800081ec  sub     rsp, 20h
0x1800081f0  mov     rdi, rcx
0x1800081f3  lea     rax, ??_7Subscription@@6B@; const Subscription::`vftable'
0x1800081fa  mov     [rcx], rax
0x1800081fd  lea     rsi, [rcx+38h]
0x180008201  mov     [rsp+38h+arg_10], rsi
0x180008206  cmp     qword ptr [rsi+18h], 8
0x18000820b  jb      short loc_180008212
0x18000820d  mov     rcx, [rsi]
0x180008210  jmp     short loc_180008215
0x180008212  mov     rcx, rsi
0x180008215  xor     r9d, r9d
0x180008218  xor     edx, edx
0x18000821a  mov     r8d, 20006h
0x180008220  call    OpenSubscriptionEventSourceKey
0x180008225  mov     rbx, rax
0x180008228  mov     [rsp+38h+arg_8], rax
0x18000822d  mov     rdx, [rdi+0C8h]; Instance
0x180008234  test    rdx, rdx
0x180008237  jz      loc_1800082C1
0x18000823d  xor     r9d, r9d; Value
0x180008240  lea     r8d, [r9+3]; CounterId
0x180008244  mov     rcx, cs:WecPerfCounter; Provider
0x18000824b  call    cs:__imp_PerfSetULongCounterValue
0x180008251  xor     r9d, r9d; Value
0x180008254  lea     r8d, [r9+4]; CounterId
0x180008258  mov     rdx, [rdi+0C8h]; Instance
0x18000825f  mov     rcx, cs:WecPerfCounter; Provider
0x180008266  call    cs:__imp_PerfSetULongCounterValue
0x18000826c  xor     r9d, r9d; Value
0x18000826f  lea     r8d, [r9+1]; CounterId
0x180008273  mov     rdx, [rdi+0C8h]; Instance
0x18000827a  mov     rcx, cs:WecPerfCounter; Provider
0x180008281  call    cs:__imp_PerfSetULongLongCounterValue
0x180008287  xor     r9d, r9d; Value
0x18000828a  lea     r8d, [r9+2]; CounterId
0x18000828e  mov     rdx, [rdi+0C8h]; Instance
0x180008295  mov     rcx, cs:WecPerfCounter; Provider
0x18000829c  call    cs:__imp_PerfSetULongLongCounterValue
0x1800082a2  mov     rdx, [rdi+0C8h]; InstanceBlock
0x1800082a9  mov     rcx, cs:WecPerfCounter; Provider
0x1800082b0  call    cs:__imp_PerfDeleteInstance
0x1800082b6  mov     qword ptr [rdi+0C8h], 0
0x1800082c1  lea     rdx, aFirsteventbatc; "FirstEventBatchTime"
0x1800082c8  mov     rcx, rbx; hKey
0x1800082cb  call    cs:__imp_RegDeleteValueW
0x1800082d1  lea     rcx, [rsp+38h+arg_8]; this
0x1800082d6  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800082db  nop
0x1800082dc  jmp     short loc_1800082E8
0x1800082de  mov     rdi, [rsp+38h+arg_0]
0x1800082e3  mov     rsi, [rsp+38h+arg_10]
0x1800082e8  lea     rcx, [rdi+78h]
0x1800082ec  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800082f1  nop
0x1800082f2  lea     rcx, [rdi+70h]
0x1800082f6  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x1800082fb  nop
0x1800082fc  xor     r8d, r8d
0x1800082ff  mov     dl, 1
0x180008301  mov     rcx, rsi
0x180008304  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180008309  nop
0x18000830a  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000830e  call    cs:__imp_DeleteCriticalSection
0x180008314  nop
0x180008315  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x18000831c  mov     [rdi], rax
0x18000831f  add     rsp, 20h
0x180008323  pop     rdi
0x180008324  pop     rsi
0x180008325  pop     rbx
0x180008326  retn
```
