# SdpSetWorkingDirectory(ushort const *)

- ea: `0x140005fec`
- end: `0x140006048`
- name: `?SdpSetWorkingDirectory@@YAJPEBG@Z`
- size: `92`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002af0`

## callees

- `0x140005964`
- `0x140005fec`

## import_xrefs

- `KERNEL32!SetCurrentDirectoryW` at `0x140006004`
- `KERNEL32!SetCurrentDirectoryW` at `0x140006004`
- `KERNEL32!GetLastError` at `0x140006012`
- `KERNEL32!GetLastError` at `0x140006012`

## string_xrefs

- `0x140006034`: `SdpSetWorkingDirectory`

## pseudocode

```c
__int64 __fastcall SdpSetWorkingDirectory(const unsigned __int16 *a1)
{
  unsigned int v1; // ebx
  unsigned int v2; // r8d
  signed int LastError; // eax

  if ( !a1 )
  {
    v1 = -2147024809;
    v2 = 2557;
LABEL_9:
    SdpDebugTrace((__int64)a1, (const char *)L"SdpSetWorkingDirectory", v2, v1);
    return v1;
  }
  if ( SetCurrentDirectoryW(a1) )
  {
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( (v1 & 0x80000000) != 0 )
    {
      v2 = 2560;
      goto LABEL_9;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140005fec  push    rbx
0x140005fee  sub     rsp, 20h
0x140005ff2  test    rcx, rcx
0x140005ff5  jnz     short loc_140006004
0x140005ff7  mov     ebx, 80070057h
0x140005ffc  mov     r8d, 9FDh
0x140006002  jmp     short loc_140006031
0x140006004  call    cs:__imp_SetCurrentDirectoryW
0x14000600a  test    eax, eax
0x14000600c  jz      short loc_140006012
0x14000600e  xor     ebx, ebx
0x140006010  jmp     short loc_140006040
0x140006012  call    cs:__imp_GetLastError
0x140006018  mov     ebx, eax
0x14000601a  test    eax, eax
0x14000601c  jle     short loc_140006027
0x14000601e  movzx   ebx, ax
0x140006021  or      ebx, 80070000h
0x140006027  test    ebx, ebx
0x140006029  jns     short loc_140006040
0x14000602b  mov     r8d, 0A00h; int
0x140006031  mov     r9d, ebx; int
0x140006034  lea     rdx, aSdpsetworkingd; "SdpSetWorkingDirectory"
0x14000603b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140006040  mov     eax, ebx
0x140006042  add     rsp, 20h
0x140006046  pop     rbx
0x140006047  retn
```
