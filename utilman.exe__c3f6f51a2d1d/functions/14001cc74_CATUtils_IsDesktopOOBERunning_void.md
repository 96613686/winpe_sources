# CATUtils::IsDesktopOOBERunning(void)

- ea: `0x14001cc74`
- end: `0x14001cca8`
- name: `?IsDesktopOOBERunning@CATUtils@@SA_NXZ`
- size: `52`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140015fb8`
- `0x14001ccb0`

## callees

- `0x14001cc74`

## import_xrefs

- `KERNEL32!OOBEComplete` at `0x14001cc85`
- `KERNEL32!OOBEComplete` at `0x14001cc85`

## pseudocode

```c
bool CATUtils::IsDesktopOOBERunning(void)
{
  int v1; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  return (unsigned int)OOBEComplete(&v1) && !v1;
}

```

## disassembly

```asm
0x14001cc74  sub     rsp, 28h
0x14001cc78  lea     rcx, [rsp+28h+arg_0]
0x14001cc7d  mov     [rsp+28h+arg_0], 0
0x14001cc85  call    cs:__imp_OOBEComplete
0x14001cc8c  nop     dword ptr [rax+rax+00h]
0x14001cc91  test    eax, eax
0x14001cc93  jz      short loc_14001CCA0
0x14001cc95  cmp     [rsp+28h+arg_0], 0
0x14001cc9a  jnz     short loc_14001CCA0
0x14001cc9c  mov     al, 1
0x14001cc9e  jmp     short loc_14001CCA2
0x14001cca0  xor     al, al
0x14001cca2  add     rsp, 28h
0x14001cca6  retn
```
