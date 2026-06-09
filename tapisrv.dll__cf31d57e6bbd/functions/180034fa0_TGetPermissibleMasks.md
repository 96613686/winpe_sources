# TGetPermissibleMasks

- ea: `0x180034fa0`
- end: `0x18003503f`
- name: `TGetPermissibleMasks`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180028100`

## callees

- `0x18001c7c0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180034fc0`
- `KERNEL32!GetCurrentThreadId` at `0x180035002`
- `KERNEL32!GetCurrentThreadId` at `0x180034fc0`
- `KERNEL32!GetCurrentThreadId` at `0x180035002`
- `KERNEL32!LeaveCriticalSection` at `0x180035028`
- `KERNEL32!LeaveCriticalSection` at `0x180035028`
- `KERNEL32!EnterCriticalSection` at `0x180034fb0`
- `KERNEL32!EnterCriticalSection` at `0x180034fb0`

## pseudocode

```c
_DWORD *__fastcall TGetPermissibleMasks(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  size_t v6; // rdx
  size_t v7; // rdx
  _DWORD *result; // rax

  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 1319;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v6, "\\server\\event.c");
  *(_DWORD *)(a2 + 16) = qword_1800519A0;
  *(_DWORD *)(a2 + 24) = HIDWORD(qword_1800519A0);
  dword_1800519F8 = 1322;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v7, "\\server\\event.c");
  LeaveCriticalSection(&CriticalSection);
  result = a5;
  *a5 = 32;
  return result;
}

```

## disassembly

```asm
0x180034fa0  push    rbx
0x180034fa2  sub     rsp, 20h
0x180034fa6  lea     rcx, CriticalSection; lpCriticalSection
0x180034fad  mov     rbx, rdx
0x180034fb0  call    cs:__imp_EnterCriticalSection
0x180034fb6  mov     cs:dword_1800519E0, 527h
0x180034fc0  call    cs:__imp_GetCurrentThreadId
0x180034fc6  lea     r8, aPrintscanTapiS+0Eh; pszSrc
0x180034fcd  mov     cs:dword_1800519E4, eax
0x180034fd3  lea     rcx, pszDest; pszDest
0x180034fda  call    StringCbCopyA
0x180034fdf  mov     r10d, dword ptr cs:qword_1800519A0
0x180034fe6  mov     [rbx+10h], r10d
0x180034fea  mov     rax, cs:qword_1800519A0
0x180034ff1  shr     rax, 20h
0x180034ff5  mov     [rbx+18h], eax
0x180034ff8  mov     cs:dword_1800519F8, 52Ah
0x180035002  call    cs:__imp_GetCurrentThreadId
0x180035008  lea     r8, aPrintscanTapiS+0Eh; pszSrc
0x18003500f  mov     cs:dword_1800519FC, eax
0x180035015  lea     rcx, byte_1800519E8; pszDest
0x18003501c  call    StringCbCopyA
0x180035021  lea     rcx, CriticalSection; lpCriticalSection
0x180035028  call    cs:__imp_LeaveCriticalSection
0x18003502e  mov     rax, [rsp+28h+arg_20]
0x180035033  mov     dword ptr [rax], 20h ; ' '
0x180035039  add     rsp, 20h
0x18003503d  pop     rbx
0x18003503e  retn
```
