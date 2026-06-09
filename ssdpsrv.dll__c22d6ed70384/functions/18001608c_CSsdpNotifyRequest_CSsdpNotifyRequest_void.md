# CSsdpNotifyRequest::CSsdpNotifyRequest(void)

- ea: `0x18001608c`
- end: `0x1800161ae`
- name: `??0CSsdpNotifyRequest@@QEAA@XZ`
- size: `290`
- prototype: `CSsdpNotifyRequest *__fastcall(CSsdpNotifyRequest *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a034`

## callees

- `0x180016bc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800160a2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016195`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800160a2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016195`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180016153`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001616a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180016181`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180016153`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001616a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180016181`

## pseudocode

```c
CSsdpNotifyRequest *__fastcall CSsdpNotifyRequest::CSsdpNotifyRequest(CSsdpNotifyRequest *this)
{
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  CTimerBase::CTimerBase((CSsdpNotifyRequest *)((char *)this + 104));
  *((_QWORD *)this + 24) = this;
  *((_QWORD *)this + 13) = &CTimer<CSsdpNotifyRequest>::`vftable';
  *((_QWORD *)this + 25) = -1;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_DWORD *)this + 59) = 0;
  *((_DWORD *)this + 60) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_DWORD *)this + 90) = 0;
  *(_QWORD *)((char *)this + 244) = 0;
  *((_DWORD *)this + 63) = 0;
  *(GUID *)((char *)this + 84) = GUID_NULL;
  *((_QWORD *)this + 39) = CreateEventA(0, 1, 1, 0);
  *((_QWORD *)this + 40) = CreateEventA(0, 0, 1, 0);
  *((_QWORD *)this + 46) = CreateEventA(0, 1, 0, 0);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  return this;
}

```

## disassembly

```asm
0x18001608c  mov     [rsp+arg_0], rbx
0x180016091  mov     [rsp+arg_8], rsi
0x180016096  push    rdi
0x180016097  sub     rsp, 20h
0x18001609b  mov     rdi, rcx
0x18001609e  add     rcx, 8; lpCriticalSection
0x1800160a2  call    cs:__imp_InitializeCriticalSection
0x1800160a8  xor     esi, esi
0x1800160aa  lea     rcx, [rdi+68h]; this
0x1800160ae  mov     [rdi+30h], rsi
0x1800160b2  mov     [rdi+38h], rsi
0x1800160b6  mov     [rdi+40h], esi
0x1800160b9  mov     [rdi+48h], rsi
0x1800160bd  mov     [rdi+50h], esi
0x1800160c0  call    ??0CTimerBase@@QEAA@XZ; CTimerBase::CTimerBase(void)
0x1800160c5  mov     [rdi+0C0h], rdi
0x1800160cc  lea     rax, ??_7?$CTimer@VCSsdpNotifyRequest@@@@6B@; const CTimer<CSsdpNotifyRequest>::`vftable'
0x1800160d3  mov     [rdi+68h], rax
0x1800160d7  lea     ebx, [rsi+1]
0x1800160da  mov     qword ptr [rdi+0C8h], 0FFFFFFFFFFFFFFFFh
0x1800160e5  xor     eax, eax
0x1800160e7  mov     [rdi+0D0h], rsi
0x1800160ee  xor     r9d, r9d; lpName
0x1800160f1  mov     [rdi+0D8h], rsi
0x1800160f8  mov     r8d, ebx; bInitialState
0x1800160fb  mov     [rdi+0E0h], rsi
0x180016102  mov     edx, ebx; bManualReset
0x180016104  mov     [rdi+0E8h], esi
0x18001610a  xor     ecx, ecx; lpEventAttributes
0x18001610c  mov     [rdi+0ECh], esi
0x180016112  mov     [rdi+0F0h], esi
0x180016118  mov     [rdi+148h], rsi
0x18001611f  mov     [rdi+150h], rsi
0x180016126  mov     [rdi+158h], rsi
0x18001612d  mov     [rdi+160h], rsi
0x180016134  mov     [rdi+168h], esi
0x18001613a  mov     [rdi+0F4h], rax
0x180016141  mov     [rdi+0FCh], eax
0x180016147  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001614e  movdqu  xmmword ptr [rdi+54h], xmm0
0x180016153  call    cs:__imp_CreateEventA
0x180016159  xor     r9d, r9d; lpName
0x18001615c  mov     r8d, ebx; bInitialState
0x18001615f  xor     edx, edx; bManualReset
0x180016161  mov     [rdi+138h], rax
0x180016168  xor     ecx, ecx; lpEventAttributes
0x18001616a  call    cs:__imp_CreateEventA
0x180016170  xor     r9d, r9d; lpName
0x180016173  xor     r8d, r8d; bInitialState
0x180016176  mov     edx, ebx; bManualReset
0x180016178  mov     [rdi+140h], rax
0x18001617f  xor     ecx, ecx; lpEventAttributes
0x180016181  call    cs:__imp_CreateEventA
0x180016187  lea     rcx, [rdi+110h]; lpCriticalSection
0x18001618e  mov     [rdi+170h], rax
0x180016195  call    cs:__imp_InitializeCriticalSection
0x18001619b  mov     rbx, [rsp+28h+arg_0]
0x1800161a0  mov     rax, rdi
0x1800161a3  mov     rsi, [rsp+28h+arg_8]
0x1800161a8  add     rsp, 20h
0x1800161ac  pop     rdi
0x1800161ad  retn
```
