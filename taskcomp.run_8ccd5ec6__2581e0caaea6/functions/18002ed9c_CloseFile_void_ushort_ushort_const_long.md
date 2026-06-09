# CloseFile(void *,ushort,ushort * const,long)

- ea: `0x18002ed9c`
- end: `0x18002eecf`
- name: `?CloseFile@@YAJPEAXGQEAGJ@Z`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE hObject, unsigned __int16, unsigned __int16 *const, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002eed8`

## callees

- `0x18002ed9c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eeb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eeb5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ede5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ee2e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ee78`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ede5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ee2e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ee78`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ee06`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ee06`

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
0x18002ed9c  mov     [rsp-28h+arg_8], dx
0x18002eda1  push    rbp
0x18002eda2  push    rbx
0x18002eda3  push    rsi
0x18002eda4  push    rdi
0x18002eda5  push    r14
0x18002eda7  mov     rbp, rsp
0x18002edaa  sub     rsp, 30h
0x18002edae  xor     r14d, r14d
0x18002edb1  mov     ebx, r9d
0x18002edb4  mov     [rbp+NumberOfBytesRead], r14d
0x18002edb8  mov     rsi, r8
0x18002edbb  mov     [rbp+Buffer], r14w
0x18002edc0  mov     rdi, rcx
0x18002edc3  mov     [rbp+arg_8], r14w
0x18002edc8  test    r9d, r9d
0x18002edcb  js      loc_18002EEAD
0x18002edd1  lea     ebx, [r14+2]
0x18002edd5  mov     [rsp+30h+lpOverlapped], r14; lpOverlapped
0x18002edda  mov     r8d, ebx; nNumberOfBytesToRead
0x18002eddd  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002ede1  lea     rdx, [rbp+Buffer]; lpBuffer
0x18002ede5  call    cs:__imp_ReadFile
0x18002edec  nop     dword ptr [rax+rax+00h]
0x18002edf1  test    eax, eax
0x18002edf3  jz      loc_18002EEA8
0x18002edf9  movzx   edx, [rbp+Buffer]; lDistanceToMove
0x18002edfd  xor     r9d, r9d; dwMoveMethod
0x18002ee00  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002ee03  mov     rcx, rdi; hFile
0x18002ee06  call    cs:__imp_SetFilePointer
0x18002ee0d  nop     dword ptr [rax+rax+00h]
0x18002ee12  cmp     eax, 0FFFFFFFFh
0x18002ee15  jz      loc_18002EEA8
0x18002ee1b  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002ee1f  mov     [rsp+30h+lpOverlapped], r14; lpOverlapped
0x18002ee24  mov     r8d, ebx; nNumberOfBytesToRead
0x18002ee27  lea     rdx, [rbp+arg_8]; lpBuffer
0x18002ee2b  mov     rcx, rdi; hFile
0x18002ee2e  call    cs:__imp_ReadFile
0x18002ee35  nop     dword ptr [rax+rax+00h]
0x18002ee3a  test    eax, eax
0x18002ee3c  jz      short loc_18002EEA8
0x18002ee3e  cmp     [rbp+NumberOfBytesRead], ebx
0x18002ee41  jnz     short loc_18002EEA8
0x18002ee43  movzx   eax, [rbp+arg_8]
0x18002ee47  test    ax, ax
0x18002ee4a  jnz     short loc_18002EE52
0x18002ee4c  mov     [rsi], r14w
0x18002ee50  jmp     short loc_18002EEA3
0x18002ee52  mov     ecx, 105h
0x18002ee57  cmp     ax, cx
0x18002ee5a  jbe     short loc_18002EE63
0x18002ee5c  mov     ebx, 8000FFFFh
0x18002ee61  jmp     short loc_18002EEAD
0x18002ee63  mov     r8d, eax
0x18002ee66  mov     [rsp+30h+lpOverlapped], r14; lpOverlapped
0x18002ee6b  add     r8d, r8d; nNumberOfBytesToRead
0x18002ee6e  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002ee72  mov     rdx, rsi; lpBuffer
0x18002ee75  mov     rcx, rdi; hFile
0x18002ee78  call    cs:__imp_ReadFile
0x18002ee7f  nop     dword ptr [rax+rax+00h]
0x18002ee84  test    eax, eax
0x18002ee86  jz      short loc_18002EEA8
0x18002ee88  movzx   ecx, [rbp+arg_8]
0x18002ee8c  mov     eax, [rbp+NumberOfBytesRead]
0x18002ee8f  add     rcx, rcx
0x18002ee92  cmp     rax, rcx
0x18002ee95  jnz     short loc_18002EEA8
0x18002ee97  movzx   eax, [rbp+arg_8]
0x18002ee9b  cmp     [rsi+rax*2-2], r14w
0x18002eea1  jnz     short loc_18002EEA8
0x18002eea3  mov     ebx, r14d
0x18002eea6  jmp     short loc_18002EEAD
0x18002eea8  mov     ebx, 8004130Eh
0x18002eead  test    rdi, rdi
0x18002eeb0  jz      short loc_18002EEC1
0x18002eeb2  mov     rcx, rdi; hObject
0x18002eeb5  call    cs:__imp_CloseHandle
0x18002eebc  nop     dword ptr [rax+rax+00h]
0x18002eec1  mov     eax, ebx
0x18002eec3  add     rsp, 30h
0x18002eec7  pop     r14
0x18002eec9  pop     rdi
0x18002eeca  pop     rsi
0x18002eecb  pop     rbx
0x18002eecc  pop     rbp
0x18002eecd  retn
```
