# ETWWrite

- ea: `0x18002c7f0`
- end: `0x18002c85e`
- name: `ETWWrite`
- size: `110`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180029930`
- `0x18002c260`
- `0x180033ee0`
- `0x180035a80`
- `0x180039e90`

## callees

- `0x18002c7f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c842`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c842`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c813`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c813`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18002c830`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18002c830`

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
0x18002c7f0  push    rbx
0x18002c7f2  push    rbp
0x18002c7f3  push    rsi
0x18002c7f4  push    rdi
0x18002c7f5  push    r14
0x18002c7f7  push    r15
0x18002c7f9  sub     rsp, 28h
0x18002c7fd  mov     rsi, cs:g_petwPro
0x18002c804  mov     rbp, r9
0x18002c807  mov     r14d, r8d
0x18002c80a  mov     r15, rdx
0x18002c80d  xor     ebx, ebx
0x18002c80f  lea     rcx, [rsi+10h]; lpCriticalSection
0x18002c813  call    cs:__imp_EnterCriticalSection
0x18002c81a  nop     dword ptr [rax+rax+00h]
0x18002c81f  cmp     [rsi], ebx
0x18002c821  jnz     short loc_18002C83E
0x18002c823  mov     rcx, [rsi+8]; RegHandle
0x18002c827  mov     r9, rbp; UserData
0x18002c82a  mov     r8d, r14d; UserDataCount
0x18002c82d  mov     rdx, r15; EventDescriptor
0x18002c830  call    cs:__imp_EventWrite
0x18002c837  nop     dword ptr [rax+rax+00h]
0x18002c83c  mov     ebx, eax
0x18002c83e  lea     rcx, [rsi+10h]; lpCriticalSection
0x18002c842  call    cs:__imp_LeaveCriticalSection
0x18002c849  nop     dword ptr [rax+rax+00h]
0x18002c84e  mov     eax, ebx
0x18002c850  add     rsp, 28h
0x18002c854  pop     r15
0x18002c856  pop     r14
0x18002c858  pop     rdi
0x18002c859  pop     rsi
0x18002c85a  pop     rbp
0x18002c85b  pop     rbx
0x18002c85c  retn
```
