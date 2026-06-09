# SIPObjectCAB_::SkipStringInFile(void)

- ea: `0x180015610`
- end: `0x18001566a`
- name: `?SkipStringInFile@SIPObjectCAB_@@AEAAHXZ`
- size: `90`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180015308`
- `0x180015564`

## callees

- `0x180015610`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180015643`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180015643`

## pseudocode

```c
__int64 __fastcall SIPObjectCAB_::SkipStringInFile(HANDLE *this)
{
  char Buffer; // [rsp+40h] [rbp+8h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp+10h] BYREF

  Buffer = 0;
  NumberOfBytesRead = 0;
  while ( ReadFile(this[1], &Buffer, 1u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 1 )
  {
    if ( !Buffer )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180015610  push    rbx
0x180015612  sub     rsp, 30h
0x180015616  mov     rbx, rcx
0x180015619  mov     [rsp+38h+Buffer], 0
0x18001561e  mov     [rsp+38h+NumberOfBytesRead], 0
0x180015626  mov     rcx, [rbx+8]; hFile
0x18001562a  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001562f  mov     r8d, 1; nNumberOfBytesToRead
0x180015635  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18001563e  lea     rdx, [rsp+38h+Buffer]; lpBuffer
0x180015643  call    cs:__imp_ReadFile
0x180015649  test    eax, eax
0x18001564b  jz      short loc_180015662
0x18001564d  cmp     [rsp+38h+NumberOfBytesRead], 1
0x180015652  jnz     short loc_180015662
0x180015654  cmp     [rsp+38h+Buffer], 0
0x180015659  jnz     short loc_180015626
0x18001565b  mov     eax, 1
0x180015660  jmp     short loc_180015664
0x180015662  xor     eax, eax
0x180015664  add     rsp, 30h
0x180015668  pop     rbx
0x180015669  retn
```
