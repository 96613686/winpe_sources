# CChildCount<CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>>::~CChildCount<CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>>(void)

- ea: `0x18000fc48`
- end: `0x18000fd0e`
- name: `??1?$CChildCount@V?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@@@QEAA@XZ`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fd14`
- `0x1800181bc`

## callees

- `0x18000fc48`
- `0x18001d010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000fcd5`
- `KERNEL32!CloseHandle` at `0x18000fcd5`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000fc70`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000fc70`
- `WdsServerCommonLib!??1CMRSWLock@@QEAA@XZ` at `0x18000fd02`
- `WdsServerCommonLib!?WriterLock@CMRSWLock@@QEAAXXZ` at `0x18000fcc0`
- `WdsServerCommonLib!?WriterLock@CMRSWLock@@QEAAXXZ` at `0x18000fcc0`
- `WdsServerCommonLib!?WriterRelease@CMRSWLock@@QEAAXXZ` at `0x18000fce9`
- `WdsServerCommonLib!?WriterRelease@CMRSWLock@@QEAAXXZ` at `0x18000fce9`

## pseudocode

```c
void __fastcall CChildCount<CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>>::~CChildCount<CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>>(
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
0x18000fc48  mov     [rsp+arg_0], rbx
0x18000fc4d  push    rdi
0x18000fc4e  sub     rsp, 20h
0x18000fc52  mov     rbx, rcx
0x18000fc55  lea     rdi, [rcx+10h]
0x18000fc59  xor     eax, eax
0x18000fc5b  lock xadd [rcx], eax
0x18000fc5f  jmp     short loc_18000FC94
0x18000fc61  mov     rcx, [rbx+8]; hHandle
0x18000fc65  mov     edx, 1F4h; dwMilliseconds
0x18000fc6a  mov     r8d, 1; bAlertable
0x18000fc70  call    cs:__imp_WaitForSingleObjectEx
0x18000fc77  nop     dword ptr [rax+rax+00h]
0x18000fc7c  test    eax, eax
0x18000fc7e  jz      short loc_18000FC8E
0x18000fc80  cmp     eax, 102h
0x18000fc85  jz      short loc_18000FC8E
0x18000fc87  cmp     eax, 0C0h
0x18000fc8c  jnz     short loc_18000FC9A
0x18000fc8e  xor     eax, eax
0x18000fc90  lock xadd [rbx], eax
0x18000fc94  test    eax, eax
0x18000fc96  jnz     short loc_18000FC61
0x18000fc98  jmp     short loc_18000FCBD
0x18000fc9a  mov     r9, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000fca1  test    r9, r9
0x18000fca4  jz      short loc_18000FCBD
0x18000fca6  mov     r8d, eax
0x18000fca9  lea     rdx, aCchildcountWai; "CChildCount::WaitForChildren failed; %u"
0x18000fcb0  mov     rax, r9
0x18000fcb3  mov     ecx, 80000h
0x18000fcb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcbd  mov     rcx, rdi
0x18000fcc0  call    cs:__imp_?WriterLock@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterLock(void)
0x18000fcc7  nop     dword ptr [rax+rax+00h]
0x18000fccc  mov     rcx, [rbx+8]; hObject
0x18000fcd0  test    rcx, rcx
0x18000fcd3  jz      short loc_18000FCE6
0x18000fcd5  call    cs:__imp_CloseHandle
0x18000fcdc  nop     dword ptr [rax+rax+00h]
0x18000fce1  and     qword ptr [rbx+8], 0
0x18000fce6  mov     rcx, rdi
0x18000fce9  call    cs:__imp_?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x18000fcf0  nop     dword ptr [rax+rax+00h]
0x18000fcf5  mov     rcx, rdi
0x18000fcf8  mov     rbx, [rsp+28h+arg_0]
0x18000fcfd  add     rsp, 20h
0x18000fd01  pop     rdi
0x18000fd02  jmp     cs:__imp_??1CMRSWLock@@QEAA@XZ; CMRSWLock::~CMRSWLock(void)
```
