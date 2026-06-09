# SendTracker::CompleteAction(WebSocketProcessor *,ulong)

- ea: `0x18000cea0`
- end: `0x18000cef2`
- name: `?CompleteAction@SendTracker@@UEAAXPEAVWebSocketProcessor@@K@Z`
- size: `82`
- prototype: `void __fastcall(SendTracker *__hidden this, struct WebSocketProcessor *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002820`
- `0x18000cea0`
- `0x18000e010`

## pseudocode

```c
void __fastcall SendTracker::CompleteAction(SendTracker *this, struct WebSocketProcessor *a2)
{
  if ( *((_DWORD *)this + 23) == 3 )
  {
    Trace::OperationStop(*((_DWORD *)this + 10));
    (**(void (__fastcall ***)(SendTracker *, __int64))this)(this, 1);
  }
  else if ( *((_DWORD *)this + 23) == 2 )
  {
    *(_QWORD *)((char *)a2 + 76) = 0;
    if ( *((_DWORD *)this + 5) == *((_DWORD *)this + 6) )
      *((_DWORD *)this + 23) = 3;
  }
}

```

## disassembly

```asm
0x18000cea0  push    rbx
0x18000cea2  sub     rsp, 20h
0x18000cea6  cmp     dword ptr [rcx+5Ch], 3
0x18000ceaa  mov     rbx, rcx
0x18000cead  jnz     short loc_18000CECF
0x18000ceaf  mov     ecx, [rcx+28h]; unsigned int
0x18000ceb2  call    ?OperationStop@Trace@@SAXK@Z; Trace::OperationStop(ulong)
0x18000ceb7  mov     rax, [rbx]
0x18000ceba  mov     edx, 1
0x18000cebf  mov     rcx, rbx
0x18000cec2  mov     rax, [rax]
0x18000cec5  add     rsp, 20h
0x18000cec9  pop     rbx
0x18000ceca  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cecf  cmp     dword ptr [rcx+5Ch], 2
0x18000ced3  jnz     short loc_18000CEEC
0x18000ced5  mov     qword ptr [rdx+4Ch], 0
0x18000cedd  mov     eax, [rcx+14h]
0x18000cee0  cmp     eax, [rcx+18h]
0x18000cee3  jnz     short loc_18000CEEC
0x18000cee5  mov     dword ptr [rcx+5Ch], 3
0x18000ceec  add     rsp, 20h
0x18000cef0  pop     rbx
0x18000cef1  retn
```
