# OnProxySCPInit

- ea: `0x18003d1ac`
- end: `0x18003d22d`
- name: `OnProxySCPInit`
- size: `129`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c8fc`

## callees

- `0x18001c7c0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18003d1c7`
- `KERNEL32!GetCurrentThreadId` at `0x18003d1fa`
- `KERNEL32!GetCurrentThreadId` at `0x18003d1c7`
- `KERNEL32!GetCurrentThreadId` at `0x18003d1fa`
- `KERNEL32!LeaveCriticalSection` at `0x18003d220`
- `KERNEL32!LeaveCriticalSection` at `0x18003d220`
- `KERNEL32!EnterCriticalSection` at `0x18003d1b7`
- `KERNEL32!EnterCriticalSection` at `0x18003d1b7`

## pseudocode

```c
__int64 OnProxySCPInit()
{
  size_t v0; // rdx
  size_t v1; // rdx

  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 2568;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v0, "erver\\dspub.cpp");
  dword_1800519F8 = 2570;
  gProxyScps = 0;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v1, "erver\\dspub.cpp");
  LeaveCriticalSection(&CriticalSection);
  return 0;
}

```

## disassembly

```asm
0x18003d1ac  sub     rsp, 28h
0x18003d1b0  lea     rcx, CriticalSection; lpCriticalSection
0x18003d1b7  call    cs:__imp_EnterCriticalSection
0x18003d1bd  mov     cs:dword_1800519E0, 0A08h
0x18003d1c7  call    cs:__imp_GetCurrentThreadId
0x18003d1cd  lea     r8, aPrintscanTapiS_0+10h; pszSrc
0x18003d1d4  mov     cs:dword_1800519E4, eax
0x18003d1da  lea     rcx, pszDest; pszDest
0x18003d1e1  call    StringCbCopyA
0x18003d1e6  xorps   xmm0, xmm0
0x18003d1e9  mov     cs:dword_1800519F8, 0A0Ah
0x18003d1f3  movups  cs:?gProxyScps@@3U_PROXY_SCPS@@A, xmm0; _PROXY_SCPS gProxyScps
0x18003d1fa  call    cs:__imp_GetCurrentThreadId
0x18003d200  lea     r8, aPrintscanTapiS_0+10h; pszSrc
0x18003d207  mov     cs:dword_1800519FC, eax
0x18003d20d  lea     rcx, byte_1800519E8; pszDest
0x18003d214  call    StringCbCopyA
0x18003d219  lea     rcx, CriticalSection; lpCriticalSection
0x18003d220  call    cs:__imp_LeaveCriticalSection
0x18003d226  xor     eax, eax
0x18003d228  add     rsp, 28h
0x18003d22c  retn
```
