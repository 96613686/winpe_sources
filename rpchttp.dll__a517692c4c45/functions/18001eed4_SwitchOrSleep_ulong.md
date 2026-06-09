# SwitchOrSleep(ulong)

- ea: `0x18001eed4`
- end: `0x18001eef8`
- name: `?SwitchOrSleep@@YAXK@Z`
- size: `36`
- prototype: `void __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ef00`

## callees

- `0x18001eed4`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x18001eee0`
- `KERNEL32!SwitchToThread` at `0x18001eee0`
- `KERNEL32!Sleep` at `0x18001eeec`
- `KERNEL32!Sleep` at `0x18001eeec`

## pseudocode

```c
void __fastcall SwitchOrSleep(DWORD dwMilliseconds)
{
  if ( dwMilliseconds || !SwitchToThread() )
    Sleep(dwMilliseconds);
}

```

## disassembly

```asm
0x18001eed4  push    rbx
0x18001eed6  sub     rsp, 20h
0x18001eeda  mov     ebx, ecx
0x18001eedc  test    ecx, ecx
0x18001eede  jnz     short loc_18001EEEA
0x18001eee0  call    cs:__imp_SwitchToThread
0x18001eee6  test    eax, eax
0x18001eee8  jnz     short loc_18001EEF2
0x18001eeea  mov     ecx, ebx; dwMilliseconds
0x18001eeec  call    cs:__imp_Sleep
0x18001eef2  add     rsp, 20h
0x18001eef6  pop     rbx
0x18001eef7  retn
```
