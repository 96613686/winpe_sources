# CEntropyRecorder::Put(void)

- ea: `0x1800028f0`
- end: `0x180002974`
- name: `?Put@CEntropyRecorder@@QEAAXXZ`
- size: `132`
- prototype: `void __fastcall(CEntropyRecorder *__hidden this)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e28`
- `0x1800022d4`
- `0x180002488`
- `0x180006bf0`
- `0x180007cb0`
- `0x180008230`
- `0x180008460`
- `0x180008960`
- `0x180008d10`
- `0x180009f14`
- `0x18000edb0`
- `0x18000f548`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000292a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000292a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000295e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000295e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002910`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002910`

## pseudocode

```c
void __fastcall CEntropyRecorder::Put(CEntropyRecorder *this)
{
  __int16 v2; // di
  __int64 v3; // rdx
  __int64 v4; // rax
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp+8h] BYREF

  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v2 = LOWORD(PerformanceCount.LowPart)
     ^ WORD2(PerformanceCount.QuadPart)
     ^ ((PerformanceCount.LowPart ^ PerformanceCount.HighPart) >> 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v3 = (unsigned __int8)*((_DWORD *)this + 12);
  *((_BYTE *)this + v3 + 56) ^= HIBYTE(v2);
  ++*((_DWORD *)this + 13);
  *((_DWORD *)this + 12) = v3 + 1;
  v4 = (unsigned __int8)(v3 + 1);
  *((_BYTE *)this + v4 + 56) ^= v2;
  ++*((_DWORD *)this + 13);
  *((_DWORD *)this + 12) = v4 + 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800028f0  mov     [rsp+arg_8], rbx
0x1800028f5  mov     [rsp+arg_10], rsi
0x1800028fa  push    rdi
0x1800028fb  sub     rsp, 20h
0x1800028ff  mov     rsi, rcx
0x180002902  mov     qword ptr [rsp+28h+PerformanceCount], 0
0x18000290b  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x180002910  call    cs:__imp_QueryPerformanceCounter
0x180002916  mov     eax, dword ptr [rsp+28h+PerformanceCount+4]
0x18000291a  lea     rcx, [rsi+8]; lpCriticalSection
0x18000291e  xor     eax, dword ptr [rsp+28h+PerformanceCount]
0x180002922  mov     edi, eax
0x180002924  shr     edi, 10h
0x180002927  xor     di, ax
0x18000292a  call    cs:__imp_EnterCriticalSection
0x180002930  mov     eax, [rsi+30h]
0x180002933  lea     rcx, [rsi+8]; lpCriticalSection
0x180002937  movzx   edx, al
0x18000293a  movzx   eax, di
0x18000293d  shr     ax, 8
0x180002941  xor     [rdx+rsi+38h], al
0x180002945  lea     eax, [rdx+1]
0x180002948  inc     dword ptr [rsi+34h]
0x18000294b  mov     [rsi+30h], eax
0x18000294e  movzx   eax, al
0x180002951  xor     [rax+rsi+38h], dil
0x180002956  inc     dword ptr [rsi+34h]
0x180002959  inc     eax
0x18000295b  mov     [rsi+30h], eax
0x18000295e  call    cs:__imp_LeaveCriticalSection
0x180002964  mov     rbx, [rsp+28h+arg_8]
0x180002969  mov     rsi, [rsp+28h+arg_10]
0x18000296e  add     rsp, 20h
0x180002972  pop     rdi
0x180002973  retn
```
