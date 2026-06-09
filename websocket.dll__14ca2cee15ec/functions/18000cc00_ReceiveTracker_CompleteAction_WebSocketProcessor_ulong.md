# ReceiveTracker::CompleteAction(WebSocketProcessor *,ulong)

- ea: `0x18000cc00`
- end: `0x18000cc5b`
- name: `?CompleteAction@ReceiveTracker@@UEAAXPEAVWebSocketProcessor@@K@Z`
- size: `91`
- prototype: `void __fastcall(ReceiveTracker *__hidden this, struct WebSocketProcessor *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002820`
- `0x18000cc00`
- `0x18000e010`

## pseudocode

```c
void __fastcall ReceiveTracker::CompleteAction(ReceiveTracker *this, struct WebSocketProcessor *a2, unsigned int a3)
{
  int v4; // ecx

  if ( *((_DWORD *)this + 16) == 1 )
  {
    Trace::OperationStop(*((_DWORD *)this + 10));
    (**(void (__fastcall ***)(ReceiveTracker *, __int64))this)(this, 1);
  }
  else if ( !*((_DWORD *)this + 16) )
  {
    v4 = *((_DWORD *)a2 + 13);
    if ( a3 <= *((_DWORD *)a2 + 12) - v4 )
      *((_DWORD *)a2 + 13) = v4 + a3;
    else
      *((_DWORD *)a2 + 60) = 5;
  }
}

```

## disassembly

```asm
0x18000cc00  push    rbx
0x18000cc02  sub     rsp, 20h
0x18000cc06  cmp     dword ptr [rcx+40h], 1
0x18000cc0a  mov     rbx, rcx
0x18000cc0d  jnz     short loc_18000CC2F
0x18000cc0f  mov     ecx, [rcx+28h]; unsigned int
0x18000cc12  call    ?OperationStop@Trace@@SAXK@Z; Trace::OperationStop(ulong)
0x18000cc17  mov     rax, [rbx]
0x18000cc1a  mov     edx, 1
0x18000cc1f  mov     rcx, rbx
0x18000cc22  mov     rax, [rax]
0x18000cc25  add     rsp, 20h
0x18000cc29  pop     rbx
0x18000cc2a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc2f  cmp     dword ptr [rcx+40h], 0
0x18000cc33  jnz     short loc_18000CC55
0x18000cc35  mov     eax, [rdx+30h]
0x18000cc38  mov     ecx, [rdx+34h]
0x18000cc3b  sub     eax, ecx
0x18000cc3d  cmp     r8d, eax
0x18000cc40  jbe     short loc_18000CC4E
0x18000cc42  mov     dword ptr [rdx+0F0h], 5
0x18000cc4c  jmp     short loc_18000CC55
0x18000cc4e  lea     eax, [rcx+r8]
0x18000cc52  mov     [rdx+34h], eax
0x18000cc55  add     rsp, 20h
0x18000cc59  pop     rbx
0x18000cc5a  retn
```
