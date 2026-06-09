# ETWWrite

- ea: `0x18002c560`
- end: `0x18002c5bb`
- name: `ETWWrite`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800297c0`
- `0x18002bfd0`
- `0x180033930`
- `0x1800354b0`
- `0x180039770`

## callees

- `0x18002c560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c5a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c5a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c583`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c583`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18002c59a`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18002c59a`

## pseudocode

```c
__int64 __fastcall ETWWrite(__int64 a1, const EVENT_DESCRIPTOR *a2, ULONG a3, struct _EVENT_DATA_DESCRIPTOR *a4)
{
  char *v4; // rsi
  ULONG v8; // ebx

  v4 = (char *)g_petwPro;
  v8 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_petwPro + 16));
  if ( !*(_DWORD *)v4 )
    v8 = EventWrite(*((_QWORD *)v4 + 1), a2, a3, a4);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 16));
  return v8;
}

```

## disassembly

```asm
0x18002c560  push    rbx
0x18002c562  push    rbp
0x18002c563  push    rsi
0x18002c564  push    rdi
0x18002c565  push    r14
0x18002c567  push    r15
0x18002c569  sub     rsp, 28h
0x18002c56d  mov     rsi, cs:g_petwPro
0x18002c574  mov     rbp, r9
0x18002c577  mov     r14d, r8d
0x18002c57a  mov     r15, rdx
0x18002c57d  xor     ebx, ebx
0x18002c57f  lea     rcx, [rsi+10h]; lpCriticalSection
0x18002c583  call    cs:__imp_EnterCriticalSection
0x18002c589  cmp     [rsi], ebx
0x18002c58b  jnz     short loc_18002C5A2
0x18002c58d  mov     rcx, [rsi+8]; RegHandle
0x18002c591  mov     r9, rbp; UserData
0x18002c594  mov     r8d, r14d; UserDataCount
0x18002c597  mov     rdx, r15; EventDescriptor
0x18002c59a  call    cs:__imp_EventWrite
0x18002c5a0  mov     ebx, eax
0x18002c5a2  lea     rcx, [rsi+10h]; lpCriticalSection
0x18002c5a6  call    cs:__imp_LeaveCriticalSection
0x18002c5ac  mov     eax, ebx
0x18002c5ae  add     rsp, 28h
0x18002c5b2  pop     r15
0x18002c5b4  pop     r14
0x18002c5b6  pop     rdi
0x18002c5b7  pop     rsi
0x18002c5b8  pop     rbp
0x18002c5b9  pop     rbx
0x18002c5ba  retn
```
