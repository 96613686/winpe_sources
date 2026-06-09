# IsInteractiveUserSession

- ea: `0x180005c30`
- end: `0x180005c4d`
- name: `IsInteractiveUserSession`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x180005c38`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180005c38`

## pseudocode

```c
_BOOL8 __fastcall IsInteractiveUserSession(int a1)
{
  return a1 != (unsigned int)RtlGetCurrentServiceSessionId();
}

```

## disassembly

```asm
0x180005c30  push    rbx
0x180005c32  sub     rsp, 20h
0x180005c36  mov     ebx, ecx
0x180005c38  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180005c3e  xor     edx, edx
0x180005c40  cmp     ebx, eax
0x180005c42  setnz   dl
0x180005c45  mov     eax, edx
0x180005c47  add     rsp, 20h
0x180005c4b  pop     rbx
0x180005c4c  retn
```
