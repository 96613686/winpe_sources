# WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)

- ea: `0x180001890`
- end: `0x1800018ee`
- name: `?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z`
- size: `94`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180001720`
- `0x180003540`
- `0x1800067f4`
- `0x180007020`
- `0x180008128`
- `0x180008438`
- `0x180008514`
- `0x1800086a0`
- `0x180008818`
- `0x180008ad4`

## callees

- `0x180001890`
- `0x180007b48`

## import_xrefs

- `iisutil!?WriteMessage@IPM_MESSAGE_PIPE@@QEAAJW4IPM_OPCODE@@KPEAX@Z` at `0x1800018c7`
- `iisutil!?WriteMessage@IPM_MESSAGE_PIPE@@QEAAJW4IPM_OPCODE@@KPEAX@Z` at `0x1800018c7`

## pseudocode

```c
__int64 __fastcall WP_IPM::WriteMessage(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 72));
  if ( !*(_QWORD *)(a1 + 8) )
    return 0;
  if ( (g_dwDebugFlags & 0x80000) != 0 )
    WP_IPM::DumpMessageOpcode(a1, a2, 1);
  return IPM_MESSAGE_PIPE::WriteMessage(*(_QWORD *)(a1 + 8), a2, a3, a4);
}

```

## disassembly

```asm
0x180001890  push    rbx
0x180001892  push    rbp
0x180001893  push    rsi
0x180001894  push    rdi
0x180001895  sub     rsp, 28h
0x180001899  mov     rsi, r9
0x18000189c  mov     ebp, r8d
0x18000189f  mov     edi, edx
0x1800018a1  mov     rbx, rcx
0x1800018a4  lock inc dword ptr [rcx+48h]
0x1800018a8  cmp     qword ptr [rcx+8], 0
0x1800018ad  jz      short loc_1800018DD
0x1800018af  test    cs:g_dwDebugFlags, 80000h
0x1800018b9  jnz     short loc_1800018E1
0x1800018bb  mov     rcx, [rbx+8]
0x1800018bf  mov     r9, rsi
0x1800018c2  mov     r8d, ebp
0x1800018c5  mov     edx, edi
0x1800018c7  call    cs:__imp_?WriteMessage@IPM_MESSAGE_PIPE@@QEAAJW4IPM_OPCODE@@KPEAX@Z; IPM_MESSAGE_PIPE::WriteMessage(IPM_OPCODE,ulong,void *)
0x1800018ce  nop     dword ptr [rax+rax+00h]
0x1800018d3  add     rsp, 28h
0x1800018d7  pop     rdi
0x1800018d8  pop     rsi
0x1800018d9  pop     rbp
0x1800018da  pop     rbx
0x1800018db  retn
0x1800018dd  xor     eax, eax
0x1800018df  jmp     short loc_1800018D3
0x1800018e1  mov     r8d, 1
0x1800018e7  call    ?DumpMessageOpcode@WP_IPM@@AEAAXW4IPM_OPCODE@@H@Z; WP_IPM::DumpMessageOpcode(IPM_OPCODE,int)
0x1800018ec  jmp     short loc_1800018BB
```
