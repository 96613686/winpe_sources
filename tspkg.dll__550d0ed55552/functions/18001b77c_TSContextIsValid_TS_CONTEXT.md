# TSContextIsValid(_TS_CONTEXT *)

- ea: `0x18001b77c`
- end: `0x18001b7de`
- name: `?TSContextIsValid@@YAEPEAU_TS_CONTEXT@@@Z`
- size: `98`
- prototype: `unsigned __int8 __fastcall(struct _TS_CONTEXT *)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a3e0`
- `0x18001a820`
- `0x18001aa90`
- `0x18001ac70`
- `0x18001acf0`
- `0x18001ae50`
- `0x18001b000`

## callees

- `0x180004440`
- `0x18001b77c`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18001b790`
- `ntdll!RtlEnterCriticalSection` at `0x18001b790`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b7cb`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b7cb`

## pseudocode

```c
bool __fastcall TSContextIsValid(struct _TS_CONTEXT *a1)
{
  _QWORD *v2; // rbx
  int v3; // eax

  RtlEnterCriticalSection(&CriticalSection);
  v2 = qword_1800258C8;
  while ( v2 )
  {
    v3 = TSContextCompareCallback((unsigned __int64)a1, (__int64)v2);
    if ( v3 >= 0 )
    {
      if ( v3 <= 0 )
        break;
      v2 = (_QWORD *)v2[1];
    }
    else
    {
      v2 = (_QWORD *)*v2;
    }
  }
  RtlLeaveCriticalSection(&CriticalSection);
  return v2 != 0;
}

```

## disassembly

```asm
0x18001b77c  mov     [rsp+arg_0], rbx
0x18001b781  push    rdi
0x18001b782  sub     rsp, 20h
0x18001b786  mov     rdi, rcx
0x18001b789  lea     rcx, CriticalSection; CriticalSection
0x18001b790  call    cs:__imp_RtlEnterCriticalSection
0x18001b796  mov     rbx, cs:qword_1800258C8
0x18001b79d  jmp     short loc_18001B7B9
0x18001b79f  mov     rdx, rbx
0x18001b7a2  mov     rcx, rdi
0x18001b7a5  call    TSContextCompareCallback
0x18001b7aa  test    eax, eax
0x18001b7ac  jns     short loc_18001B7B3
0x18001b7ae  mov     rbx, [rbx]
0x18001b7b1  jmp     short loc_18001B7B9
0x18001b7b3  jle     short loc_18001B7BE
0x18001b7b5  mov     rbx, [rbx+8]
0x18001b7b9  test    rbx, rbx
0x18001b7bc  jnz     short loc_18001B79F
0x18001b7be  test    rbx, rbx
0x18001b7c1  lea     rcx, CriticalSection; CriticalSection
0x18001b7c8  setnz   bl
0x18001b7cb  call    cs:__imp_RtlLeaveCriticalSection
0x18001b7d1  mov     al, bl
0x18001b7d3  mov     rbx, [rsp+28h+arg_0]
0x18001b7d8  add     rsp, 20h
0x18001b7dc  pop     rdi
0x18001b7dd  retn
```
