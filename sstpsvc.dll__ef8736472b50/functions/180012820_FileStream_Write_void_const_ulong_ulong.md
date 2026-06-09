# FileStream::Write(void const *,ulong,ulong *)

- ea: `0x180012820`
- end: `0x180012863`
- name: `?Write@FileStream@@UEAAJPEBXKPEAK@Z`
- size: `67`
- prototype: `__int64 __fastcall(FileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180012820`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012845`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012831`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012831`

## pseudocode

```c
signed int __fastcall FileStream::Write(HANDLE *this, const void *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax

  if ( WriteFile(this[1], a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180012820  sub     rsp, 38h
0x180012824  mov     rcx, [rcx+8]; hFile
0x180012828  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180012831  call    cs:__imp_WriteFile
0x180012838  nop     dword ptr [rax+rax+00h]
0x18001283d  test    eax, eax
0x18001283f  jz      short loc_180012845
0x180012841  xor     eax, eax
0x180012843  jmp     short loc_18001285D
0x180012845  call    cs:__imp_GetLastError
0x18001284c  nop     dword ptr [rax+rax+00h]
0x180012851  test    eax, eax
0x180012853  jle     short loc_18001285D
0x180012855  movzx   eax, ax
0x180012858  or      eax, 80070000h
0x18001285d  add     rsp, 38h
0x180012861  retn
```
