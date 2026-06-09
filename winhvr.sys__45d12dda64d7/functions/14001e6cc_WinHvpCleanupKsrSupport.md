# WinHvpCleanupKsrSupport

- ea: `0x14001e6cc`
- end: `0x14001e737`
- name: `WinHvpCleanupKsrSupport`
- size: `107`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001e5ec`
- `0x14001e7e4`
- `0x14002a804`

## callees

- `0x14000a040`
- `0x14001e6cc`

## import_xrefs

- `ntoskrnl!ExUnregisterCallback` at `0x14001e6f7`
- `ntoskrnl!ExUnregisterCallback` at `0x14001e6f7`
- `ntoskrnl!ObfDereferenceObject` at `0x14001e71a`
- `ntoskrnl!ObfDereferenceObject` at `0x14001e71a`

## pseudocode

```c
void WinHvpCleanupKsrSupport()
{
  if ( byte_140016208 )
  {
    memset(&WinHvpKsrContext, 0, 0x40u);
    if ( CallbackRegistration )
    {
      ExUnregisterCallback(CallbackRegistration);
      CallbackRegistration = 0;
    }
    if ( CallbackObject )
    {
      ObfDereferenceObject(CallbackObject);
      CallbackObject = 0;
    }
  }
}

```

## disassembly

```asm
0x14001e6cc  sub     rsp, 28h
0x14001e6d0  cmp     cs:byte_140016208, 0
0x14001e6d7  jz      short loc_14001E731
0x14001e6d9  xor     edx, edx; Val
0x14001e6db  lea     rcx, WinHvpKsrContext; void *
0x14001e6e2  lea     r8d, [rdx+40h]; Size
0x14001e6e6  call    memset
0x14001e6eb  mov     rcx, cs:CallbackRegistration; CallbackRegistration
0x14001e6f2  test    rcx, rcx
0x14001e6f5  jz      short loc_14001E70E
0x14001e6f7  call    cs:__imp_ExUnregisterCallback
0x14001e6fe  nop     dword ptr [rax+rax+00h]
0x14001e703  mov     cs:CallbackRegistration, 0
0x14001e70e  mov     rcx, cs:CallbackObject; Object
0x14001e715  test    rcx, rcx
0x14001e718  jz      short loc_14001E731
0x14001e71a  call    cs:__imp_ObfDereferenceObject
0x14001e721  nop     dword ptr [rax+rax+00h]
0x14001e726  mov     cs:CallbackObject, 0
0x14001e731  add     rsp, 28h
0x14001e735  retn
```
