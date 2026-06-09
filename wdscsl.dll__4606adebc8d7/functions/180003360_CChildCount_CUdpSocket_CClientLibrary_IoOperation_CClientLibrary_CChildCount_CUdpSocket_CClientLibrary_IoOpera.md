# CChildCount<CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>>::~CChildCount<CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>>(void)

- ea: `0x180003360`
- end: `0x180003426`
- name: `??1?$CChildCount@V?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@@@QEAA@XZ`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000342c`

## callees

- `0x180003360`
- `0x18000e010`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x180003388`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003388`
- `KERNEL32!CloseHandle` at `0x1800033ed`
- `KERNEL32!CloseHandle` at `0x1800033ed`
- `WdsCommonLib!??1CMRSWLock@@QEAA@XZ` at `0x18000341a`
- `WdsCommonLib!?WriterLock@CMRSWLock@@QEAAXXZ` at `0x1800033d8`
- `WdsCommonLib!?WriterLock@CMRSWLock@@QEAAXXZ` at `0x1800033d8`
- `WdsCommonLib!?WriterRelease@CMRSWLock@@QEAAXXZ` at `0x180003401`
- `WdsCommonLib!?WriterRelease@CMRSWLock@@QEAAXXZ` at `0x180003401`

## pseudocode

```c
void __fastcall CChildCount<CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>>::~CChildCount<CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>>(
        __int64 a1)
{
  CMRSWLock *v2; // rdi
  signed __int32 i; // eax
  DWORD v4; // eax
  void *v5; // rcx

  v2 = (CMRSWLock *)(a1 + 16);
  for ( i = _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0);
        i;
        i = _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0) )
  {
    v4 = WaitForSingleObjectEx(*(HANDLE *)(a1 + 8), 0x1F4u, 1);
    if ( v4 && v4 != 258 && v4 != 192 )
    {
      if ( g_ErrLibTraceFunctionEx )
        g_ErrLibTraceFunctionEx(0x80000u, L"CChildCount::WaitForChildren failed; %u", v4);
      break;
    }
  }
  CMRSWLock::WriterLock(v2);
  v5 = *(void **)(a1 + 8);
  if ( v5 )
  {
    CloseHandle(v5);
    *(_QWORD *)(a1 + 8) = 0;
  }
  CMRSWLock::WriterRelease(v2);
  CMRSWLock::~CMRSWLock(v2);
}

```

## disassembly

```asm
0x180003360  mov     [rsp+arg_0], rbx
0x180003365  push    rdi
0x180003366  sub     rsp, 20h
0x18000336a  mov     rbx, rcx
0x18000336d  lea     rdi, [rcx+10h]
0x180003371  xor     eax, eax
0x180003373  lock xadd [rcx], eax
0x180003377  jmp     short loc_1800033AC
0x180003379  mov     rcx, [rbx+8]; hHandle
0x18000337d  mov     edx, 1F4h; dwMilliseconds
0x180003382  mov     r8d, 1; bAlertable
0x180003388  call    cs:__imp_WaitForSingleObjectEx
0x18000338f  nop     dword ptr [rax+rax+00h]
0x180003394  test    eax, eax
0x180003396  jz      short loc_1800033A6
0x180003398  cmp     eax, 102h
0x18000339d  jz      short loc_1800033A6
0x18000339f  cmp     eax, 0C0h
0x1800033a4  jnz     short loc_1800033B2
0x1800033a6  xor     eax, eax
0x1800033a8  lock xadd [rbx], eax
0x1800033ac  test    eax, eax
0x1800033ae  jnz     short loc_180003379
0x1800033b0  jmp     short loc_1800033D5
0x1800033b2  mov     r9, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800033b9  test    r9, r9
0x1800033bc  jz      short loc_1800033D5
0x1800033be  mov     r8d, eax
0x1800033c1  lea     rdx, aCchildcountWai; "CChildCount::WaitForChildren failed; %u"
0x1800033c8  mov     rax, r9
0x1800033cb  mov     ecx, 80000h
0x1800033d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d5  mov     rcx, rdi
0x1800033d8  call    cs:__imp_?WriterLock@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterLock(void)
0x1800033df  nop     dword ptr [rax+rax+00h]
0x1800033e4  mov     rcx, [rbx+8]; hObject
0x1800033e8  test    rcx, rcx
0x1800033eb  jz      short loc_1800033FE
0x1800033ed  call    cs:__imp_CloseHandle
0x1800033f4  nop     dword ptr [rax+rax+00h]
0x1800033f9  and     qword ptr [rbx+8], 0
0x1800033fe  mov     rcx, rdi
0x180003401  call    cs:__imp_?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180003408  nop     dword ptr [rax+rax+00h]
0x18000340d  mov     rcx, rdi
0x180003410  mov     rbx, [rsp+28h+arg_0]
0x180003415  add     rsp, 20h
0x180003419  pop     rdi
0x18000341a  jmp     cs:__imp_??1CMRSWLock@@QEAA@XZ; CMRSWLock::~CMRSWLock(void)
```
