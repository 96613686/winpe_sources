# WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)

- ea: `0x180001830`
- end: `0x180001887`
- name: `?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z`
- size: `87`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800016e0`
- `0x180003340`
- `0x1800061dc`
- `0x180006980`
- `0x180007958`
- `0x180007c18`
- `0x180007ce8`
- `0x180007e48`
- `0x180007f8c`
- `0x1800081fc`

## callees

- `0x180001830`
- `0x1800073c0`

## import_xrefs

- `iisutil!?WriteMessage@IPM_MESSAGE_PIPE@@QEAAJW4IPM_OPCODE@@KPEAX@Z` at `0x180001867`
- `iisutil!?WriteMessage@IPM_MESSAGE_PIPE@@QEAAJW4IPM_OPCODE@@KPEAX@Z` at `0x180001867`

## pseudocode

```c
__int64 __fastcall WP_IPM::WriteMessage(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v6; // edi

  v6 = a2;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 72));
  if ( !*(_QWORD *)(a1 + 8) )
    return 0;
  if ( (g_dwDebugFlags & 0x80000) != 0 )
    WP_IPM::DumpMessageOpcode(a1, a2, 1);
  return IPM_MESSAGE_PIPE::WriteMessage(*(_QWORD *)(a1 + 8), v6, a3, a4);
}

```

## disassembly

```asm
0x180001830  push    rbx
0x180001832  push    rbp
0x180001833  push    rsi
0x180001834  push    rdi
0x180001835  sub     rsp, 28h
0x180001839  mov     rsi, r9
0x18000183c  mov     ebp, r8d
0x18000183f  mov     edi, edx
0x180001841  mov     rbx, rcx
0x180001844  lock inc dword ptr [rcx+48h]
0x180001848  cmp     qword ptr [rcx+8], 0
0x18000184d  jz      short loc_180001876
0x18000184f  test    cs:g_dwDebugFlags, 80000h
0x180001859  jnz     short loc_18000187A
0x18000185b  mov     rcx, [rbx+8]
0x18000185f  mov     r9, rsi
0x180001862  mov     r8d, ebp
0x180001865  mov     edx, edi
0x180001867  call    cs:__imp_?WriteMessage@IPM_MESSAGE_PIPE@@QEAAJW4IPM_OPCODE@@KPEAX@Z; IPM_MESSAGE_PIPE::WriteMessage(IPM_OPCODE,ulong,void *)
0x18000186d  add     rsp, 28h
0x180001871  pop     rdi
0x180001872  pop     rsi
0x180001873  pop     rbp
0x180001874  pop     rbx
0x180001875  retn
0x180001876  xor     eax, eax
0x180001878  jmp     short loc_18000186D
0x18000187a  mov     r8d, 1
0x180001880  call    ?DumpMessageOpcode@WP_IPM@@AEAAXW4IPM_OPCODE@@H@Z; WP_IPM::DumpMessageOpcode(IPM_OPCODE,int)
0x180001885  jmp     short loc_18000185B
```
