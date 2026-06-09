# FileStream::Read(void *,ulong,ulong *)

- ea: `0x1800125b0`
- end: `0x1800125f3`
- name: `?Read@FileStream@@UEAAJPEAXKPEAK@Z`
- size: `67`
- prototype: `__int64 __fastcall(FileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800125b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125d5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800125c1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800125c1`

## pseudocode

```c
signed int __fastcall FileStream::Read(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax

  if ( ReadFile(this[1], a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800125b0  sub     rsp, 38h
0x1800125b4  mov     rcx, [rcx+8]; hFile
0x1800125b8  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800125c1  call    cs:__imp_ReadFile
0x1800125c8  nop     dword ptr [rax+rax+00h]
0x1800125cd  test    eax, eax
0x1800125cf  jz      short loc_1800125D5
0x1800125d1  xor     eax, eax
0x1800125d3  jmp     short loc_1800125ED
0x1800125d5  call    cs:__imp_GetLastError
0x1800125dc  nop     dword ptr [rax+rax+00h]
0x1800125e1  test    eax, eax
0x1800125e3  jle     short loc_1800125ED
0x1800125e5  movzx   eax, ax
0x1800125e8  or      eax, 80070000h
0x1800125ed  add     rsp, 38h
0x1800125f1  retn
```
