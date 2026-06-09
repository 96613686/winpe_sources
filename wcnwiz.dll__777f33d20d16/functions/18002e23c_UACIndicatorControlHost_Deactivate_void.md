# UACIndicatorControlHost::Deactivate(void)

- ea: `0x18002e23c`
- end: `0x18002e27c`
- name: `?Deactivate@UACIndicatorControlHost@@QEAAXXZ`
- size: `64`
- prototype: `void __fastcall(UACIndicatorControlHost *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800304d0`

## callees

- `0x18002e23c`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18002e268`
- `KERNEL32!WaitForSingleObject` at `0x18002e268`
- `USER32!PostThreadMessageW` at `0x18002e259`
- `USER32!PostThreadMessageW` at `0x18002e259`

## pseudocode

```c
void __fastcall UACIndicatorControlHost::Deactivate(UACIndicatorControlHost *this)
{
  if ( *((_QWORD *)this + 1) )
  {
    PostThreadMessageW(*((_DWORD *)this + 4), 0x12u, 0, 0);
    WaitForSingleObject(*((HANDLE *)this + 1), 0x1388u);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18002e23c  push    rbx
0x18002e23e  sub     rsp, 20h
0x18002e242  cmp     qword ptr [rcx+8], 0
0x18002e247  mov     rbx, rcx
0x18002e24a  jz      short loc_18002E276
0x18002e24c  mov     ecx, [rcx+10h]; idThread
0x18002e24f  xor     r9d, r9d; lParam
0x18002e252  xor     r8d, r8d; wParam
0x18002e255  lea     edx, [r9+12h]; Msg
0x18002e259  call    cs:__imp_PostThreadMessageW
0x18002e25f  mov     rcx, [rbx+8]; hHandle
0x18002e263  mov     edx, 1388h; dwMilliseconds
0x18002e268  call    cs:__imp_WaitForSingleObject
0x18002e26e  mov     qword ptr [rbx+8], 0
0x18002e276  add     rsp, 20h
0x18002e27a  pop     rbx
0x18002e27b  retn
```
