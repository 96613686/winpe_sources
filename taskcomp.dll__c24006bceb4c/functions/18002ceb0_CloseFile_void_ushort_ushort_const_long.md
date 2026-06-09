# CloseFile(void *,ushort,ushort * const,long)

- ea: `0x18002ceb0`
- end: `0x18002cfc4`
- name: `?CloseFile@@YAJPEAXGQEAGJ@Z`
- size: `276`
- prototype: `__int64 __fastcall(HANDLE hObject, __int64, unsigned __int16 *const, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002cfcc`

## callees

- `0x18002ceb0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cfb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cfb1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002cef9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002cf36`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002cf7a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002cef9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002cf36`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002cf7a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cf14`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cf14`

## pseudocode

```c
__int64 __fastcall CloseFile(HANDLE hObject, __int64 a2, unsigned __int16 *const a3, int a4)
{
  unsigned int v4; // ebx
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int16 v9; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int16 Buffer; // [rsp+78h] [rbp+48h] BYREF

  v4 = a4;
  NumberOfBytesRead = 0;
  Buffer = 0;
  v9 = 0;
  if ( a4 >= 0 )
  {
    if ( ReadFile(hObject, &Buffer, 2u, &NumberOfBytesRead, 0)
      && SetFilePointer(hObject, Buffer, 0, 0) != -1
      && ReadFile(hObject, &v9, 2u, &NumberOfBytesRead, 0)
      && NumberOfBytesRead == 2 )
    {
      if ( !v9 )
      {
        *a3 = 0;
LABEL_13:
        v4 = 0;
        goto LABEL_15;
      }
      if ( v9 > 0x105u )
      {
        v4 = -2147418113;
        goto LABEL_15;
      }
      if ( ReadFile(hObject, a3, 2 * v9, &NumberOfBytesRead, 0) && NumberOfBytesRead == 2LL * v9 && !a3[v9 - 1] )
        goto LABEL_13;
    }
    v4 = -2147216626;
  }
LABEL_15:
  if ( hObject )
    CloseHandle(hObject);
  return v4;
}

```

## disassembly

```asm
0x18002ceb0  mov     [rsp-28h+arg_8], dx
0x18002ceb5  push    rbp
0x18002ceb6  push    rbx
0x18002ceb7  push    rsi
0x18002ceb8  push    rdi
0x18002ceb9  push    r14
0x18002cebb  mov     rbp, rsp
0x18002cebe  sub     rsp, 30h
0x18002cec2  xor     r14d, r14d
0x18002cec5  mov     ebx, r9d
0x18002cec8  mov     [rbp+NumberOfBytesRead], r14d
0x18002cecc  mov     rsi, r8
0x18002cecf  mov     [rbp+Buffer], r14w
0x18002ced4  mov     rdi, rcx
0x18002ced7  mov     [rbp+arg_8], r14w
0x18002cedc  test    r9d, r9d
0x18002cedf  js      loc_18002CFA9
0x18002cee5  lea     ebx, [r14+2]
0x18002cee9  mov     [rsp+30h+lpOverlapped], r14; lpOverlapped
0x18002ceee  mov     r8d, ebx; nNumberOfBytesToRead
0x18002cef1  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002cef5  lea     rdx, [rbp+Buffer]; lpBuffer
0x18002cef9  call    cs:__imp_ReadFile
0x18002ceff  test    eax, eax
0x18002cf01  jz      loc_18002CFA4
0x18002cf07  movzx   edx, [rbp+Buffer]; lDistanceToMove
0x18002cf0b  xor     r9d, r9d; dwMoveMethod
0x18002cf0e  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002cf11  mov     rcx, rdi; hFile
0x18002cf14  call    cs:__imp_SetFilePointer
0x18002cf1a  cmp     eax, 0FFFFFFFFh
0x18002cf1d  jz      loc_18002CFA4
0x18002cf23  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002cf27  mov     [rsp+30h+lpOverlapped], r14; lpOverlapped
0x18002cf2c  mov     r8d, ebx; nNumberOfBytesToRead
0x18002cf2f  lea     rdx, [rbp+arg_8]; lpBuffer
0x18002cf33  mov     rcx, rdi; hFile
0x18002cf36  call    cs:__imp_ReadFile
0x18002cf3c  test    eax, eax
0x18002cf3e  jz      short loc_18002CFA4
0x18002cf40  cmp     [rbp+NumberOfBytesRead], ebx
0x18002cf43  jnz     short loc_18002CFA4
0x18002cf45  movzx   eax, [rbp+arg_8]
0x18002cf49  test    ax, ax
0x18002cf4c  jnz     short loc_18002CF54
0x18002cf4e  mov     [rsi], r14w
0x18002cf52  jmp     short loc_18002CF9F
0x18002cf54  mov     ecx, 105h
0x18002cf59  cmp     ax, cx
0x18002cf5c  jbe     short loc_18002CF65
0x18002cf5e  mov     ebx, 8000FFFFh
0x18002cf63  jmp     short loc_18002CFA9
0x18002cf65  mov     r8d, eax
0x18002cf68  mov     [rsp+30h+lpOverlapped], r14; lpOverlapped
0x18002cf6d  add     r8d, r8d; nNumberOfBytesToRead
0x18002cf70  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002cf74  mov     rdx, rsi; lpBuffer
0x18002cf77  mov     rcx, rdi; hFile
0x18002cf7a  call    cs:__imp_ReadFile
0x18002cf80  test    eax, eax
0x18002cf82  jz      short loc_18002CFA4
0x18002cf84  movzx   ecx, [rbp+arg_8]
0x18002cf88  mov     eax, [rbp+NumberOfBytesRead]
0x18002cf8b  add     rcx, rcx
0x18002cf8e  cmp     rax, rcx
0x18002cf91  jnz     short loc_18002CFA4
0x18002cf93  movzx   eax, [rbp+arg_8]
0x18002cf97  cmp     [rsi+rax*2-2], r14w
0x18002cf9d  jnz     short loc_18002CFA4
0x18002cf9f  mov     ebx, r14d
0x18002cfa2  jmp     short loc_18002CFA9
0x18002cfa4  mov     ebx, 8004130Eh
0x18002cfa9  test    rdi, rdi
0x18002cfac  jz      short loc_18002CFB7
0x18002cfae  mov     rcx, rdi; hObject
0x18002cfb1  call    cs:__imp_CloseHandle
0x18002cfb7  mov     eax, ebx
0x18002cfb9  add     rsp, 30h
0x18002cfbd  pop     r14
0x18002cfbf  pop     rdi
0x18002cfc0  pop     rsi
0x18002cfc1  pop     rbx
0x18002cfc2  pop     rbp
0x18002cfc3  retn
```
