# CLangDataPack::SaveObjectHeader(void *,ILangDataPack::PACKDATA_OBJECTHEADER *)

- ea: `0x1800d3504`
- end: `0x1800d35b8`
- name: `?SaveObjectHeader@CLangDataPack@@AEAAJPEAXPEAUPACKDATA_OBJECTHEADER@ILangDataPack@@@Z`
- size: `180`
- prototype: `int(CLangDataPack *__hidden this, void *, struct ILangDataPack::PACKDATA_OBJECTHEADER *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800d31f0`
- `0x1800d3444`

## callees

- `0x180016f48`
- `0x1800d3504`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d3535`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d3565`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d3595`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d3535`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d3565`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d3595`

## pseudocode

```c
__int64 __fastcall CLangDataPack::SaveObjectHeader(
        CLangDataPack *this,
        void *a2,
        struct ILangDataPack::PACKDATA_OBJECTHEADER *a3)
{
  int Error; // ebx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+44h] [rbp+Ch]

  v8 = HIDWORD(this);
  Error = 0;
  NumberOfBytesWritten = 0;
  if ( WriteFile(a2, a3, 0x10u, &NumberOfBytesWritten, 0) || (Error = ATL::AtlHresultFromLastError(), Error >= 0) )
  {
    if ( WriteFile(a2, (char *)a3 + 16, 0x10u, &NumberOfBytesWritten, 0)
      || (Error = ATL::AtlHresultFromLastError(), Error >= 0) )
    {
      if ( !WriteFile(a2, (char *)a3 + 32, 8u, &NumberOfBytesWritten, 0) )
        return (unsigned int)ATL::AtlHresultFromLastError();
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800d3504  mov     rax, rsp
0x1800d3507  mov     [rax+10h], rbx
0x1800d350b  mov     [rax+18h], rsi
0x1800d350f  mov     [rax+8], rcx
0x1800d3513  push    rdi
0x1800d3514  sub     rsp, 30h
0x1800d3518  xor     ebx, ebx
0x1800d351a  lea     r9, [rax+8]; lpNumberOfBytesWritten
0x1800d351e  mov     rdi, r8
0x1800d3521  mov     [rax+8], ebx
0x1800d3524  mov     rsi, rdx
0x1800d3527  mov     [rax-18h], rbx
0x1800d352b  mov     rdx, rdi; lpBuffer
0x1800d352e  mov     rcx, rsi; hFile
0x1800d3531  lea     r8d, [rbx+10h]; nNumberOfBytesToWrite
0x1800d3535  call    cs:__imp_WriteFile
0x1800d353b  test    eax, eax
0x1800d353d  jnz     short loc_1800D354A
0x1800d353f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800d3544  mov     ebx, eax
0x1800d3546  test    eax, eax
0x1800d3548  js      short loc_1800D35A6
0x1800d354a  lea     rdx, [rdi+10h]; lpBuffer
0x1800d354e  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800d3557  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d355c  mov     r8d, 10h; nNumberOfBytesToWrite
0x1800d3562  mov     rcx, rsi; hFile
0x1800d3565  call    cs:__imp_WriteFile
0x1800d356b  test    eax, eax
0x1800d356d  jnz     short loc_1800D357A
0x1800d356f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800d3574  mov     ebx, eax
0x1800d3576  test    eax, eax
0x1800d3578  js      short loc_1800D35A6
0x1800d357a  lea     rdx, [rdi+20h]; lpBuffer
0x1800d357e  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800d3587  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d358c  mov     r8d, 8; nNumberOfBytesToWrite
0x1800d3592  mov     rcx, rsi; hFile
0x1800d3595  call    cs:__imp_WriteFile
0x1800d359b  test    eax, eax
0x1800d359d  jnz     short loc_1800D35A6
0x1800d359f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800d35a4  mov     ebx, eax
0x1800d35a6  mov     rsi, [rsp+38h+arg_10]
0x1800d35ab  mov     eax, ebx
0x1800d35ad  mov     rbx, [rsp+38h+arg_8]
0x1800d35b2  add     rsp, 30h
0x1800d35b6  pop     rdi
0x1800d35b7  retn
```
