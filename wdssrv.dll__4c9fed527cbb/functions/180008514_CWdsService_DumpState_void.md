# CWdsService::DumpState(void)

- ea: `0x180008514`
- end: `0x18000863c`
- name: `?DumpState@CWdsService@@QEAAXXZ`
- size: `296`
- prototype: `void __fastcall(CWdsService *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000cc30`

## callees

- `0x180002358`
- `0x180008514`
- `0x18000fda8`
- `0x18001d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008572`
- `KERNEL32!LeaveCriticalSection` at `0x1800085eb`
- `KERNEL32!LeaveCriticalSection` at `0x180008572`
- `KERNEL32!LeaveCriticalSection` at `0x1800085eb`
- `KERNEL32!EnterCriticalSection` at `0x180008547`
- `KERNEL32!EnterCriticalSection` at `0x18000855f`
- `KERNEL32!EnterCriticalSection` at `0x1800085c0`
- `KERNEL32!EnterCriticalSection` at `0x1800085d8`
- `KERNEL32!EnterCriticalSection` at `0x180008547`
- `KERNEL32!EnterCriticalSection` at `0x18000855f`
- `KERNEL32!EnterCriticalSection` at `0x1800085c0`
- `KERNEL32!EnterCriticalSection` at `0x1800085d8`

## pseudocode

```c
void __fastcall CWdsService::DumpState(CWdsService *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rcx
  char *v8; // [rsp+20h] [rbp-18h] BYREF
  int v9; // [rsp+28h] [rbp-10h]

  CInterfaceMonitor::DumpState((LPCRITICAL_SECTION)((char *)this + 56));
  v8 = (char *)this + 1184;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 30);
  v9 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 30);
  v2 = *((_QWORD *)this + 148);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 30);
  if ( v2 )
  {
    v3 = *((_QWORD *)this + 148);
    while ( v3 )
    {
      v4 = v3;
      v3 = *(_QWORD *)(v3 + 2080);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
    }
  }
  CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(&v8);
  v8 = (char *)this + 66976;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 66992));
  v9 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 66992));
  v5 = *((_QWORD *)this + 8372);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 66992));
  if ( v5 )
  {
    v6 = *((_QWORD *)this + 8372);
    while ( v6 )
    {
      v7 = v6;
      v6 = *(_QWORD *)(v6 + 1824);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
    }
  }
  CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(&v8);
}

```

## disassembly

```asm
0x180008514  mov     [rsp+arg_0], rbx
0x180008519  mov     [rsp+arg_8], rbp
0x18000851e  mov     [rsp+arg_10], rsi
0x180008523  push    rdi
0x180008524  sub     rsp, 30h
0x180008528  mov     rbp, rcx
0x18000852b  add     rcx, 38h ; '8'; lpCriticalSection
0x18000852f  call    ?DumpState@CInterfaceMonitor@@QEAAXXZ; CInterfaceMonitor::DumpState(void)
0x180008534  lea     rsi, [rbp+4A0h]
0x18000853b  lea     rcx, [rbp+4B0h]; lpCriticalSection
0x180008542  mov     [rsp+38h+var_18], rsi
0x180008547  call    cs:__imp_EnterCriticalSection
0x18000854e  nop     dword ptr [rax+rax+00h]
0x180008553  lea     rcx, [rsi+10h]; lpCriticalSection
0x180008557  mov     [rsp+38h+var_10], 1
0x18000855f  call    cs:__imp_EnterCriticalSection
0x180008566  nop     dword ptr [rax+rax+00h]
0x18000856b  mov     rdi, [rsi]
0x18000856e  lea     rcx, [rsi+10h]; lpCriticalSection
0x180008572  call    cs:__imp_LeaveCriticalSection
0x180008579  nop     dword ptr [rax+rax+00h]
0x18000857e  test    rdi, rdi
0x180008581  jz      short loc_1800085A3
0x180008583  mov     rbx, [rsi]
0x180008586  jmp     short loc_18000859E
0x180008588  mov     rcx, rbx
0x18000858b  mov     rbx, [rbx+820h]
0x180008592  mov     rax, [rcx]
0x180008595  mov     rax, [rax+18h]
0x180008599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000859e  test    rbx, rbx
0x1800085a1  jnz     short loc_180008588
0x1800085a3  lea     rcx, [rsp+38h+var_18]
0x1800085a8  call    ??1?$CAutoTypeLock@V?$CList@VCRegUdpEndpoint@@VCCriticalSection@@@@@@QEAA@XZ; CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(void)
0x1800085ad  lea     rsi, [rbp+105A0h]
0x1800085b4  lea     rcx, [rbp+105B0h]; lpCriticalSection
0x1800085bb  mov     [rsp+38h+var_18], rsi
0x1800085c0  call    cs:__imp_EnterCriticalSection
0x1800085c7  nop     dword ptr [rax+rax+00h]
0x1800085cc  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800085d0  mov     [rsp+38h+var_10], 1
0x1800085d8  call    cs:__imp_EnterCriticalSection
0x1800085df  nop     dword ptr [rax+rax+00h]
0x1800085e4  mov     rbx, [rsi]
0x1800085e7  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800085eb  call    cs:__imp_LeaveCriticalSection
0x1800085f2  nop     dword ptr [rax+rax+00h]
0x1800085f7  test    rbx, rbx
0x1800085fa  jz      short loc_18000861C
0x1800085fc  mov     rbx, [rsi]
0x1800085ff  jmp     short loc_180008617
0x180008601  mov     rcx, rbx
0x180008604  mov     rbx, [rbx+720h]
0x18000860b  mov     rax, [rcx]
0x18000860e  mov     rax, [rax+18h]
0x180008612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008617  test    rbx, rbx
0x18000861a  jnz     short loc_180008601
0x18000861c  lea     rcx, [rsp+38h+var_18]
0x180008621  call    ??1?$CAutoTypeLock@V?$CList@VCRegUdpEndpoint@@VCCriticalSection@@@@@@QEAA@XZ; CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(void)
0x180008626  mov     rbx, [rsp+38h+arg_0]
0x18000862b  mov     rbp, [rsp+38h+arg_8]
0x180008630  mov     rsi, [rsp+38h+arg_10]
0x180008635  add     rsp, 30h
0x180008639  pop     rdi
0x18000863a  retn
```
