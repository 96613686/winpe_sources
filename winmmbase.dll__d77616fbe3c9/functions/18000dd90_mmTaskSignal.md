# mmTaskSignal

- ea: `0x18000dd90`
- end: `0x18000ddc2`
- name: `mmTaskSignal`
- size: `50`
- prototype: `BOOL __stdcall(DWORD h)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000dd90`
- `0x180011690`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x18000ddb3`

## pseudocode

```c
BOOL __stdcall mmTaskSignal(DWORD h)
{
  return (unsigned __int8)IsPostThreadMessageWPresent() && PostThreadMessageA(h, 0x400u, 0, 0);
}

```

## disassembly

```asm
0x18000dd90  push    rbx
0x18000dd92  sub     rsp, 20h
0x18000dd96  mov     ebx, ecx
0x18000dd98  call    IsPostThreadMessageWPresent
0x18000dd9d  test    al, al
0x18000dd9f  jz      short loc_18000DDBA
0x18000dda1  xor     r9d, r9d
0x18000dda4  xor     r8d, r8d
0x18000dda7  mov     edx, 400h
0x18000ddac  mov     ecx, ebx
0x18000ddae  add     rsp, 20h
0x18000ddb2  pop     rbx
0x18000ddb3  jmp     cs:__imp_PostThreadMessageA
0x18000ddba  xor     eax, eax
0x18000ddbc  add     rsp, 20h
0x18000ddc0  pop     rbx
0x18000ddc1  retn
```
