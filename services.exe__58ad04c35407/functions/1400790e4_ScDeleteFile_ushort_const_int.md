# ScDeleteFile(ushort const *,int)

- ea: `0x1400790e4`
- end: `0x14007914e`
- name: `?ScDeleteFile@@YAKPEBGH@Z`
- size: `106`
- prototype: `unsigned int __fastcall(LPCWSTR lpFileName, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140079154`

## callees

- `0x1400790e4`
- `0x14007be28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079139`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400790ff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14007912f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400790ff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14007912f`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1400790f7`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x140079127`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1400790f7`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x140079127`

## pseudocode

```c
unsigned int __fastcall ScDeleteFile(LPCWSTR lpFileName, int a2)
{
  BOOL v4; // eax
  unsigned int result; // eax
  BOOL v6; // eax

  if ( a2 )
    v4 = RemoveDirectoryW(lpFileName);
  else
    v4 = DeleteFileW(lpFileName);
  if ( v4 )
    return 0;
  result = GetLastError();
  if ( result == 5 )
  {
    result = ScTakeOwnershipFile(lpFileName);
    if ( !result )
    {
      if ( a2 )
        v6 = RemoveDirectoryW(lpFileName);
      else
        v6 = DeleteFileW(lpFileName);
      if ( !v6 )
        return GetLastError();
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400790e4  mov     [rsp+arg_0], rbx
0x1400790e9  push    rdi
0x1400790ea  sub     rsp, 20h
0x1400790ee  mov     edi, edx
0x1400790f0  mov     rbx, rcx
0x1400790f3  test    edx, edx
0x1400790f5  jz      short loc_1400790FF
0x1400790f7  call    cs:__imp_RemoveDirectoryW
0x1400790fd  jmp     short loc_140079105
0x1400790ff  call    cs:__imp_DeleteFileW
0x140079105  test    eax, eax
0x140079107  jnz     short loc_140079141
0x140079109  call    cs:__imp_GetLastError
0x14007910f  cmp     eax, 5
0x140079112  jnz     short loc_140079143
0x140079114  mov     rcx, rbx; lpFileName
0x140079117  call    ?ScTakeOwnershipFile@@YAKPEBG@Z; ScTakeOwnershipFile(ushort const *)
0x14007911c  test    eax, eax
0x14007911e  jnz     short loc_140079143
0x140079120  mov     rcx, rbx; lpFileName
0x140079123  test    edi, edi
0x140079125  jz      short loc_14007912F
0x140079127  call    cs:__imp_RemoveDirectoryW
0x14007912d  jmp     short loc_140079135
0x14007912f  call    cs:__imp_DeleteFileW
0x140079135  test    eax, eax
0x140079137  jnz     short loc_140079141
0x140079139  call    cs:__imp_GetLastError
0x14007913f  jmp     short loc_140079143
0x140079141  xor     eax, eax
0x140079143  mov     rbx, [rsp+28h+arg_0]
0x140079148  add     rsp, 20h
0x14007914c  pop     rdi
0x14007914d  retn
```
