# __get_entropy

- ea: `0x10003c87`
- end: `0x10003cd6`
- name: `__get_entropy`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x10003cdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10003caa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10003caa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10003cb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10003cb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x10003c9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x10003c9b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x10003cc0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x10003cc0`

## pseudocode

```c
unsigned int _get_entropy()
{
  LARGE_INTEGER PerformanceCount; // [esp+0h] [ebp-14h] BYREF
  _FILETIME SystemTimeAsFileTime; // [esp+8h] [ebp-Ch] BYREF
  DWORD v3; // [esp+10h] [ebp-4h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = SystemTimeAsFileTime.dwLowDateTime ^ SystemTimeAsFileTime.dwHighDateTime;
  v3 ^= GetCurrentThreadId();
  v3 ^= GetCurrentProcessId();
  QueryPerformanceCounter(&PerformanceCount);
  return (unsigned int)&v3 ^ v3 ^ PerformanceCount.LowPart ^ PerformanceCount.HighPart;
}

```

## disassembly

```asm
0x10003c87  mov     edi, edi
0x10003c89  push    ebp
0x10003c8a  mov     ebp, esp
0x10003c8c  sub     esp, 14h
0x10003c8f  lea     eax, [ebp+SystemTimeAsFileTime]
0x10003c92  xorps   xmm0, xmm0
0x10003c95  push    eax; lpSystemTimeAsFileTime
0x10003c96  movlpd  qword ptr [ebp+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x10003c9b  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x10003ca1  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x10003ca4  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x10003ca7  mov     [ebp+var_4], eax
0x10003caa  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10003cb0  xor     [ebp+var_4], eax
0x10003cb3  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x10003cb9  xor     [ebp+var_4], eax
0x10003cbc  lea     eax, [ebp+PerformanceCount]
0x10003cbf  push    eax; lpPerformanceCount
0x10003cc0  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x10003cc6  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x10003cc9  lea     ecx, [ebp+var_4]
0x10003ccc  xor     eax, dword ptr [ebp+PerformanceCount]
0x10003ccf  xor     eax, [ebp+var_4]
0x10003cd2  xor     eax, ecx
0x10003cd4  leave
0x10003cd5  retn
```
