# CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>(void)

- ea: `0x18000318c`
- end: `0x180003299`
- name: `??0?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAA@XZ`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800077f4`

## callees

- `0x18000d6d2`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x1800031fe`
- `KERNEL32!InitializeSListHead` at `0x1800031fe`
- `KERNEL32!InitializeCriticalSection` at `0x1800031ac`
- `KERNEL32!InitializeCriticalSection` at `0x1800031d2`
- `KERNEL32!InitializeCriticalSection` at `0x18000321b`
- `KERNEL32!InitializeCriticalSection` at `0x1800031ac`
- `KERNEL32!InitializeCriticalSection` at `0x1800031d2`
- `KERNEL32!InitializeCriticalSection` at `0x18000321b`
- `WdsCommonLib!??0CCompPort@@QEAA@XZ` at `0x1800031bf`
- `WdsCommonLib!??0CCompPort@@QEAA@XZ` at `0x1800031bf`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>(
        __int64 a1)
{
  *(_QWORD *)a1 = &CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  CCompPort::CCompPort((CCompPort *)(a1 + 288));
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 376));
  *(_QWORD *)(a1 + 360) = 0;
  *(_QWORD *)(a1 + 368) = 0;
  *(_DWORD *)(a1 + 416) = 0;
  InitializeSListHead((PSLIST_HEADER)(a1 + 432));
  *(_DWORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 464) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 496));
  *(_DWORD *)(a1 + 536) = 0;
  *(_QWORD *)(a1 + 544) = 0;
  *(_QWORD *)(a1 + 552) = 0;
  *(_QWORD *)(a1 + 560) = 0;
  *(_QWORD *)(a1 + 568) = 0;
  *(_QWORD *)(a1 + 576) = 0;
  *(_DWORD *)(a1 + 584) = 0;
  *(_QWORD *)(a1 + 592) = 0;
  *(_QWORD *)(a1 + 600) = 0;
  *(_DWORD *)(a1 + 608) = 0;
  *(_DWORD *)(a1 + 480) = 0;
  *(_QWORD *)(a1 + 488) = 0;
  *(_QWORD *)(a1 + 56) = -1;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 424) = 0;
  *(_DWORD *)(a1 + 428) = 0;
  memset_0((void *)(a1 + 72), 0, 0xD8u);
  return a1;
}

```

## disassembly

```asm
0x18000318c  mov     [rsp+arg_0], rbx
0x180003191  mov     [rsp+arg_8], rsi
0x180003196  push    rdi
0x180003197  sub     rsp, 20h
0x18000319b  lea     rax, ??_7?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@6B@; const CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::`vftable'
0x1800031a2  mov     rdi, rcx
0x1800031a5  mov     [rcx], rax
0x1800031a8  add     rcx, 8; lpCriticalSection
0x1800031ac  call    cs:__imp_InitializeCriticalSection
0x1800031b3  nop     dword ptr [rax+rax+00h]
0x1800031b8  lea     rcx, [rdi+120h]
0x1800031bf  call    cs:__imp_??0CCompPort@@QEAA@XZ; CCompPort::CCompPort(void)
0x1800031c6  nop     dword ptr [rax+rax+00h]
0x1800031cb  lea     rcx, [rdi+178h]; lpCriticalSection
0x1800031d2  call    cs:__imp_InitializeCriticalSection
0x1800031d9  nop     dword ptr [rax+rax+00h]
0x1800031de  xor     esi, esi
0x1800031e0  lea     rbx, [rdi+1B0h]
0x1800031e7  mov     rcx, rbx; ListHead
0x1800031ea  mov     [rdi+168h], rsi
0x1800031f1  mov     [rdi+170h], rsi
0x1800031f8  mov     [rdi+1A0h], esi
0x1800031fe  call    cs:__imp_InitializeSListHead
0x180003205  nop     dword ptr [rax+rax+00h]
0x18000320a  mov     [rbx+10h], esi
0x18000320d  mov     [rbx+20h], rsi
0x180003211  lea     rbx, [rdi+1F0h]
0x180003218  mov     rcx, rbx; lpCriticalSection
0x18000321b  call    cs:__imp_InitializeCriticalSection
0x180003222  nop     dword ptr [rax+rax+00h]
0x180003227  mov     [rbx+28h], esi
0x18000322a  lea     rcx, [rdi+48h]; void *
0x18000322e  mov     [rbx+30h], rsi
0x180003232  xor     eax, eax
0x180003234  mov     [rbx+38h], rsi
0x180003238  xor     edx, edx; Val
0x18000323a  mov     [rbx+40h], rsi
0x18000323e  mov     r8d, 0D8h; Size
0x180003244  mov     [rbx+48h], rax
0x180003248  mov     [rbx+50h], rax
0x18000324c  mov     [rbx+58h], esi
0x18000324f  mov     [rbx+60h], rsi
0x180003253  mov     [rbx+68h], rsi
0x180003257  mov     [rbx+70h], esi
0x18000325a  mov     [rdi+1E0h], esi
0x180003260  mov     [rdi+1E8h], rsi
0x180003267  or      qword ptr [rdi+38h], 0FFFFFFFFFFFFFFFFh
0x18000326c  mov     [rdi+30h], rsi
0x180003270  mov     [rdi+40h], rsi
0x180003274  mov     [rdi+1A8h], esi
0x18000327a  mov     [rdi+1ACh], esi
0x180003280  call    memset_0
0x180003285  mov     rbx, [rsp+28h+arg_0]
0x18000328a  mov     rax, rdi
0x18000328d  mov     rsi, [rsp+28h+arg_8]
0x180003292  add     rsp, 20h
0x180003296  pop     rdi
0x180003297  retn
```
