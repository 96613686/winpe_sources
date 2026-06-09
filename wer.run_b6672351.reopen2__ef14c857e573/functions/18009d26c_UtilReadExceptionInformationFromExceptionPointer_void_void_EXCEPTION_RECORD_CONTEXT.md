# UtilReadExceptionInformationFromExceptionPointer(void *,void *,_EXCEPTION_RECORD *,_CONTEXT *)

- ea: `0x18009d26c`
- end: `0x18009d329`
- name: `?UtilReadExceptionInformationFromExceptionPointer@@YAJPEAX0PEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(HANDLE hProcess, void *, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180084fdc`

## callees

- `0x18009d26c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d2b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d2b4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18009d2a4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18009d2f1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18009d2a4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18009d2f1`

## pseudocode

```c
signed int __fastcall UtilReadExceptionInformationFromExceptionPointer(
        HANDLE hProcess,
        void *a2,
        struct _EXCEPTION_RECORD *a3,
        struct _CONTEXT *a4)
{
  signed int result; // eax
  LPCVOID lpBaseAddress[3]; // [rsp+30h] [rbp-18h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+68h] [rbp+20h] BYREF

  NumberOfBytesRead = 0;
  *(_OWORD *)lpBaseAddress = 0;
  if ( ReadProcessMemory(hProcess, a2, lpBaseAddress, 0x10u, &NumberOfBytesRead) )
  {
    if ( NumberOfBytesRead != 16 )
      return -2147024597;
    if ( ReadProcessMemory(hProcess, lpBaseAddress[0], a3, 0x98u, &NumberOfBytesRead) )
      return NumberOfBytesRead != 152 ? 0x8007012B : 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18009d26c  mov     r11, rsp
0x18009d26f  mov     [r11+8], rbx
0x18009d273  mov     [r11+20h], r9
0x18009d277  push    rdi
0x18009d278  sub     rsp, 40h
0x18009d27c  mov     rdi, r8
0x18009d27f  mov     qword ptr [r11+20h], 0
0x18009d287  xorps   xmm0, xmm0
0x18009d28a  lea     rax, [r11+20h]
0x18009d28e  lea     r8, [r11-18h]; lpBuffer
0x18009d292  mov     [r11-28h], rax
0x18009d296  mov     r9d, 10h; nSize
0x18009d29c  mov     rbx, rcx
0x18009d29f  movups  xmmword ptr [rsp+48h+lpBaseAddress], xmm0
0x18009d2a4  call    cs:__imp_ReadProcessMemory
0x18009d2ab  nop     dword ptr [rax+rax+00h]
0x18009d2b0  test    eax, eax
0x18009d2b2  jnz     short loc_18009D2CE
0x18009d2b4  call    cs:__imp_GetLastError
0x18009d2bb  nop     dword ptr [rax+rax+00h]
0x18009d2c0  test    eax, eax
0x18009d2c2  jle     short loc_18009D31D
0x18009d2c4  movzx   eax, ax
0x18009d2c7  or      eax, 80070000h
0x18009d2cc  jmp     short loc_18009D31D
0x18009d2ce  cmp     [rsp+48h+NumberOfBytesRead], 10h
0x18009d2d4  jnz     short loc_18009D318
0x18009d2d6  mov     rdx, [rsp+48h+lpBaseAddress]; lpBaseAddress
0x18009d2db  lea     rax, [rsp+48h+NumberOfBytesRead]
0x18009d2e0  mov     r9d, 98h; nSize
0x18009d2e6  mov     [rsp+48h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18009d2eb  mov     r8, rdi; lpBuffer
0x18009d2ee  mov     rcx, rbx; hProcess
0x18009d2f1  call    cs:__imp_ReadProcessMemory
0x18009d2f8  nop     dword ptr [rax+rax+00h]
0x18009d2fd  test    eax, eax
0x18009d2ff  jz      short loc_18009D2B4
0x18009d301  mov     rax, [rsp+48h+NumberOfBytesRead]
0x18009d306  sub     rax, 98h
0x18009d30c  neg     rax
0x18009d30f  sbb     eax, eax
0x18009d311  and     eax, 8007012Bh
0x18009d316  jmp     short loc_18009D31D
0x18009d318  mov     eax, 8007012Bh
0x18009d31d  mov     rbx, [rsp+48h+arg_0]
0x18009d322  add     rsp, 40h
0x18009d326  pop     rdi
0x18009d327  retn
```
