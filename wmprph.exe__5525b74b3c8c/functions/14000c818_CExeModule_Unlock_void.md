# CExeModule::Unlock(void)

- ea: `0x14000c818`
- end: `0x14000c84a`
- name: `?Unlock@CExeModule@@QEAAJXZ`
- size: `50`
- prototype: `__int64 __fastcall(CExeModule *__hidden this)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x140002080`
- `0x140002108`
- `0x140002190`
- `0x14000310c`
- `0x140004360`
- `0x1400079c0`
- `0x140007a40`
- `0x140007ab0`
- `0x140007b20`
- `0x140007ba0`
- `0x140009710`
- `0x14000ac24`
- `0x14000ad2c`
- `0x14000b080`
- `0x14000c550`
- `0x14000c630`

## callees

- `0x14000c818`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14000c83c`
- `KERNEL32!SetEvent` at `0x14000c83c`

## pseudocode

```c
__int64 __fastcall CExeModule::Unlock(CExeModule *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(&dword_1400153D8);
  if ( !v1 )
  {
    byte_1400154C0 = 1;
    SetEvent(hEvent);
  }
  return v1;
}

```

## disassembly

```asm
0x14000c818  push    rbx
0x14000c81a  sub     rsp, 20h
0x14000c81e  or      ebx, 0FFFFFFFFh
0x14000c821  lock xadd cs:dword_1400153D8, ebx
0x14000c829  sub     ebx, 1
0x14000c82c  jnz     short loc_14000C842
0x14000c82e  mov     rcx, qword ptr cs:hEvent; hEvent
0x14000c835  mov     cs:byte_1400154C0, 1
0x14000c83c  call    cs:__imp_SetEvent
0x14000c842  mov     eax, ebx
0x14000c844  add     rsp, 20h
0x14000c848  pop     rbx
0x14000c849  retn
```
