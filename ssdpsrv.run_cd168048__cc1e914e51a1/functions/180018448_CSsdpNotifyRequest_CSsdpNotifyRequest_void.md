# CSsdpNotifyRequest::CSsdpNotifyRequest(void)

- ea: `0x180018448`
- end: `0x180018589`
- name: `??0CSsdpNotifyRequest@@QEAA@XZ`
- size: `321`
- prototype: `CSsdpNotifyRequest *__fastcall(CSsdpNotifyRequest *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b2e8`

## callees

- `0x180019004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001845e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180018569`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001845e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180018569`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180018515`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180018532`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001854f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180018515`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180018532`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001854f`

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
0x180018448  mov     [rsp+arg_0], rbx
0x18001844d  mov     [rsp+arg_8], rsi
0x180018452  push    rdi
0x180018453  sub     rsp, 20h
0x180018457  mov     rdi, rcx
0x18001845a  add     rcx, 8; lpCriticalSection
0x18001845e  call    cs:__imp_InitializeCriticalSection
0x180018465  nop     dword ptr [rax+rax+00h]
0x18001846a  xor     esi, esi
0x18001846c  lea     rcx, [rdi+68h]; this
0x180018470  mov     [rdi+30h], rsi
0x180018474  mov     [rdi+38h], rsi
0x180018478  mov     [rdi+40h], esi
0x18001847b  mov     [rdi+48h], rsi
0x18001847f  mov     [rdi+50h], esi
0x180018482  call    ??0CTimerBase@@QEAA@XZ; CTimerBase::CTimerBase(void)
0x180018487  mov     [rdi+0C0h], rdi
0x18001848e  lea     rax, ??_7?$CTimer@VCSsdpNotifyRequest@@@@6B@; const CTimer<CSsdpNotifyRequest>::`vftable'
0x180018495  mov     [rdi+68h], rax
0x180018499  lea     ebx, [rsi+1]
0x18001849c  mov     qword ptr [rdi+0C8h], 0FFFFFFFFFFFFFFFFh
0x1800184a7  xor     eax, eax
0x1800184a9  mov     [rdi+0D0h], rsi
0x1800184b0  xor     r9d, r9d; lpName
0x1800184b3  mov     [rdi+0D8h], rsi
0x1800184ba  mov     r8d, ebx; bInitialState
0x1800184bd  mov     [rdi+0E0h], rsi
0x1800184c4  mov     edx, ebx; bManualReset
0x1800184c6  mov     [rdi+0E8h], esi
0x1800184cc  xor     ecx, ecx; lpEventAttributes
0x1800184ce  mov     [rdi+0ECh], esi
0x1800184d4  mov     [rdi+0F0h], esi
0x1800184da  mov     [rdi+148h], rsi
0x1800184e1  mov     [rdi+150h], rsi
0x1800184e8  mov     [rdi+158h], rsi
0x1800184ef  mov     [rdi+160h], rsi
0x1800184f6  mov     [rdi+168h], esi
0x1800184fc  mov     [rdi+0F4h], rax
0x180018503  mov     [rdi+0FCh], eax
0x180018509  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180018510  movdqu  xmmword ptr [rdi+54h], xmm0
0x180018515  call    cs:__imp_CreateEventA
0x18001851c  nop     dword ptr [rax+rax+00h]
0x180018521  xor     r9d, r9d; lpName
0x180018524  mov     r8d, ebx; bInitialState
0x180018527  xor     edx, edx; bManualReset
0x180018529  mov     [rdi+138h], rax
0x180018530  xor     ecx, ecx; lpEventAttributes
0x180018532  call    cs:__imp_CreateEventA
0x180018539  nop     dword ptr [rax+rax+00h]
0x18001853e  xor     r9d, r9d; lpName
0x180018541  xor     r8d, r8d; bInitialState
0x180018544  mov     edx, ebx; bManualReset
0x180018546  mov     [rdi+140h], rax
0x18001854d  xor     ecx, ecx; lpEventAttributes
0x18001854f  call    cs:__imp_CreateEventA
0x180018556  nop     dword ptr [rax+rax+00h]
0x18001855b  lea     rcx, [rdi+110h]; lpCriticalSection
0x180018562  mov     [rdi+170h], rax
0x180018569  call    cs:__imp_InitializeCriticalSection
0x180018570  nop     dword ptr [rax+rax+00h]
0x180018575  mov     rbx, [rsp+28h+arg_0]
0x18001857a  mov     rax, rdi
0x18001857d  mov     rsi, [rsp+28h+arg_8]
0x180018582  add     rsp, 20h
0x180018586  pop     rdi
0x180018587  retn
```
