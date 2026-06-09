# OnProxySCPShutdown

- ea: `0x18003d234`
- end: `0x18003d2f2`
- name: `OnProxySCPShutdown`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002d27c`

## callees

- `0x18001c7c0`
- `0x18002c8d4`
- `0x18003a938`
- `0x18003d234`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18003d251`
- `KERNEL32!GetCurrentThreadId` at `0x18003d2be`
- `KERNEL32!GetCurrentThreadId` at `0x18003d251`
- `KERNEL32!GetCurrentThreadId` at `0x18003d2be`
- `KERNEL32!LeaveCriticalSection` at `0x18003d2e4`
- `KERNEL32!LeaveCriticalSection` at `0x18003d2e4`
- `KERNEL32!EnterCriticalSection` at `0x18003d241`
- `KERNEL32!EnterCriticalSection` at `0x18003d241`

## pseudocode

```c
__int64 OnProxySCPShutdown()
{
  size_t v0; // rdx
  unsigned int i; // ebx
  size_t v2; // rdx

  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 2580;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v0, "erver\\dspub.cpp");
  for ( i = 0; i < *(&gProxyScps + 1); ++i )
    RemoveProxySCP((STRSAFE_LPCWSTR)(*(&gProxyScps + 1) + 196LL * i));
  if ( *(&gProxyScps + 1) )
    ServerFree(*(&gProxyScps + 1));
  dword_1800519F8 = 2590;
  gProxyScps = 0;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v2, "erver\\dspub.cpp");
  LeaveCriticalSection(&CriticalSection);
  return 0;
}

```

## disassembly

```asm
0x18003d234  push    rbx
0x18003d236  sub     rsp, 20h
0x18003d23a  lea     rcx, CriticalSection; lpCriticalSection
0x18003d241  call    cs:__imp_EnterCriticalSection
0x18003d247  mov     cs:dword_1800519E0, 0A14h
0x18003d251  call    cs:__imp_GetCurrentThreadId
0x18003d257  lea     r8, aPrintscanTapiS_0+10h; pszSrc
0x18003d25e  mov     cs:dword_1800519E4, eax
0x18003d264  lea     rcx, pszDest; pszDest
0x18003d26b  call    StringCbCopyA
0x18003d270  xor     ebx, ebx
0x18003d272  cmp     dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+4, ebx; _PROXY_SCPS gProxyScps
0x18003d278  jbe     short loc_18003D299
0x18003d27a  mov     eax, ebx
0x18003d27c  imul    rcx, rax, 0C4h
0x18003d283  add     rcx, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; pszSrc
0x18003d28a  call    ?RemoveProxySCP@@YAJPEBG@Z; RemoveProxySCP(ushort const *)
0x18003d28f  inc     ebx
0x18003d291  cmp     ebx, dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+4; _PROXY_SCPS gProxyScps
0x18003d297  jb      short loc_18003D27A
0x18003d299  mov     rcx, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; lpMem
0x18003d2a0  test    rcx, rcx
0x18003d2a3  jz      short loc_18003D2AA
0x18003d2a5  call    ServerFree
0x18003d2aa  xorps   xmm0, xmm0
0x18003d2ad  mov     cs:dword_1800519F8, 0A1Eh
0x18003d2b7  movups  cs:?gProxyScps@@3U_PROXY_SCPS@@A, xmm0; _PROXY_SCPS gProxyScps
0x18003d2be  call    cs:__imp_GetCurrentThreadId
0x18003d2c4  lea     r8, aPrintscanTapiS_0+10h; pszSrc
0x18003d2cb  mov     cs:dword_1800519FC, eax
0x18003d2d1  lea     rcx, byte_1800519E8; pszDest
0x18003d2d8  call    StringCbCopyA
0x18003d2dd  lea     rcx, CriticalSection; lpCriticalSection
0x18003d2e4  call    cs:__imp_LeaveCriticalSection
0x18003d2ea  xor     eax, eax
0x18003d2ec  add     rsp, 20h
0x18003d2f0  pop     rbx
0x18003d2f1  retn
```
