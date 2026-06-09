# FileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x180012750`
- end: `0x1800127bb`
- name: `?Seek@FileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `107`
- prototype: `int(FileStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180012750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012799`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180012789`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180012789`

## pseudocode

```c
int __fastcall FileStream::Seek(HANDLE *this, LARGE_INTEGER a2, int a3, LARGE_INTEGER *a4)
{
  int v5; // r8d
  int result; // eax
  DWORD v7; // r9d

  if ( a3 )
  {
    v5 = a3 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
        return -2147287039;
      v7 = 2;
    }
    else
    {
      v7 = 1;
    }
  }
  else
  {
    v7 = 0;
  }
  if ( SetFilePointerEx(this[1], a2, a4, v7) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180012750  sub     rsp, 28h
0x180012754  mov     rax, r9
0x180012757  test    r8d, r8d
0x18001275a  jz      short loc_18001277F
0x18001275c  sub     r8d, 1
0x180012760  jz      short loc_180012777
0x180012762  cmp     r8d, 1
0x180012766  jz      short loc_18001276F
0x180012768  mov     eax, 80030001h
0x18001276d  jmp     short loc_1800127B5
0x18001276f  mov     r9d, 2
0x180012775  jmp     short loc_180012782
0x180012777  mov     r9d, 1
0x18001277d  jmp     short loc_180012782
0x18001277f  xor     r9d, r9d; dwMoveMethod
0x180012782  mov     rcx, [rcx+8]; hFile
0x180012786  mov     r8, rax; lpNewFilePointer
0x180012789  call    cs:__imp_SetFilePointerEx
0x180012790  nop     dword ptr [rax+rax+00h]
0x180012795  test    eax, eax
0x180012797  jnz     short loc_1800127B3
0x180012799  call    cs:__imp_GetLastError
0x1800127a0  nop     dword ptr [rax+rax+00h]
0x1800127a5  test    eax, eax
0x1800127a7  jle     short loc_1800127B5
0x1800127a9  movzx   eax, ax
0x1800127ac  or      eax, 80070000h
0x1800127b1  jmp     short loc_1800127B5
0x1800127b3  xor     eax, eax
0x1800127b5  add     rsp, 28h
0x1800127b9  retn
```
