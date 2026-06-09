# UbpmUtilsFreeTimerContext(void * *,uchar)

- ea: `0x180027994`
- end: `0x1800279e3`
- name: `?UbpmUtilsFreeTimerContext@@YAXPEAPEAXE@Z`
- size: `79`
- prototype: `void __fastcall(void **, unsigned __int8)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003684`
- `0x18000d5c0`
- `0x18002b2b0`

## callees

- `0x180027994`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800279bf`
- `ntdll!RtlFreeHeap` at `0x1800279bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800279db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800279db`

## pseudocode

```c
void __fastcall UbpmUtilsFreeTimerContext(PTP_TIMER **a1, char a2)
{
  PTP_TIMER *v2; // rbx

  v2 = *a1;
  if ( *a1 )
  {
    if ( a2 )
      CloseThreadpoolTimer(v2[5]);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180027994  mov     [rsp+arg_0], rbx
0x180027999  push    rdi
0x18002799a  sub     rsp, 20h
0x18002799e  mov     rbx, [rcx]
0x1800279a1  mov     rdi, rcx
0x1800279a4  test    rbx, rbx
0x1800279a7  jz      short loc_1800279CC
0x1800279a9  test    dl, dl
0x1800279ab  jnz     short loc_1800279D7
0x1800279ad  mov     rcx, gs:60h
0x1800279b6  mov     r8, rbx; P
0x1800279b9  xor     edx, edx; Flags
0x1800279bb  mov     rcx, [rcx+30h]; HeapHandle
0x1800279bf  call    cs:__imp_RtlFreeHeap
0x1800279c5  mov     qword ptr [rdi], 0
0x1800279cc  mov     rbx, [rsp+28h+arg_0]
0x1800279d1  add     rsp, 20h
0x1800279d5  pop     rdi
0x1800279d6  retn
0x1800279d7  mov     rcx, [rbx+28h]; pti
0x1800279db  call    cs:__imp_CloseThreadpoolTimer
0x1800279e1  jmp     short loc_1800279AD
```
