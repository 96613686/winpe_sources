# FlushWriteBuffer

- ea: `0x180023940`
- end: `0x1800239a8`
- name: `FlushWriteBuffer`
- size: `104`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180019454`
- `0x18001fdb8`
- `0x1800239b0`

## callees

- `0x180023940`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18002396e`
- `KERNEL32!WriteFile` at `0x18002396e`
- `KERNEL32!SetLastError` at `0x18002398c`
- `KERNEL32!SetLastError` at `0x18002398c`

## pseudocode

```c
BOOL __fastcall FlushWriteBuffer(__int64 a1)
{
  DWORD v1; // r8d
  BOOL result; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_DWORD *)(a1 + 8);
  result = 1;
  if ( v1 )
  {
    NumberOfBytesWritten = 0;
    result = WriteFile(*(HANDLE *)a1, (LPCVOID)(a1 + 24), v1, &NumberOfBytesWritten, 0);
    if ( result )
    {
      if ( NumberOfBytesWritten != *(_DWORD *)(a1 + 8) )
      {
        SetLastError(0xEAu);
        result = 0;
      }
      if ( result )
        *(_DWORD *)(a1 + 8) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180023940  push    rbx
0x180023942  sub     rsp, 30h
0x180023946  mov     r8d, [rcx+8]; nNumberOfBytesToWrite
0x18002394a  mov     rbx, rcx
0x18002394d  mov     eax, 1
0x180023952  test    r8d, r8d
0x180023955  jz      short loc_1800239A2
0x180023957  and     [rsp+38h+NumberOfBytesWritten], 0
0x18002395c  lea     rdx, [rcx+18h]; lpBuffer
0x180023960  mov     rcx, [rcx]; hFile
0x180023963  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180023968  and     [rsp+38h+var_18], 0
0x18002396e  call    cs:__imp_WriteFile
0x180023975  nop     dword ptr [rax+rax+00h]
0x18002397a  test    eax, eax
0x18002397c  jz      short loc_1800239A2
0x18002397e  mov     ecx, [rbx+8]
0x180023981  cmp     [rsp+38h+NumberOfBytesWritten], ecx
0x180023985  jz      short loc_18002399A
0x180023987  mov     ecx, 0EAh; dwErrCode
0x18002398c  call    cs:__imp_SetLastError
0x180023993  nop     dword ptr [rax+rax+00h]
0x180023998  xor     eax, eax
0x18002399a  test    eax, eax
0x18002399c  jz      short loc_1800239A2
0x18002399e  and     dword ptr [rbx+8], 0
0x1800239a2  add     rsp, 30h
0x1800239a6  pop     rbx
0x1800239a7  retn
```
