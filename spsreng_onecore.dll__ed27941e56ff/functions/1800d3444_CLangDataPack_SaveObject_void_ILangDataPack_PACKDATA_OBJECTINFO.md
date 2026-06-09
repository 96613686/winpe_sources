# CLangDataPack::SaveObject(void *,ILangDataPack::PACKDATA_OBJECTINFO *)

- ea: `0x1800d3444`
- end: `0x1800d34fe`
- name: `?SaveObject@CLangDataPack@@AEAAJPEAXPEAUPACKDATA_OBJECTINFO@ILangDataPack@@@Z`
- size: `186`
- prototype: `int(CLangDataPack *__hidden this, void *, struct ILangDataPack::PACKDATA_OBJECTINFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800d31f0`

## callees

- `0x180016f48`
- `0x1800d3444`
- `0x1800d3504`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d3489`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d34db`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d3489`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d34db`

## pseudocode

```c
__int64 __fastcall CLangDataPack::SaveObject(
        CLangDataPack *this,
        void *a2,
        struct ILangDataPack::PACKDATA_OBJECTINFO *a3)
{
  int Error; // ebx
  int v6; // eax
  DWORD v7; // r8d
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF
  int v10; // [rsp+44h] [rbp+Ch]
  __int64 Buffer; // [rsp+50h] [rbp+18h] BYREF

  v10 = HIDWORD(this);
  NumberOfBytesWritten = 0;
  Error = CLangDataPack::SaveObjectHeader(this, a2, a3);
  if ( Error >= 0 )
  {
    if ( WriteFile(a2, *((LPCVOID *)a3 + 5), *((_DWORD *)a3 + 8), &NumberOfBytesWritten, 0)
      || (Error = ATL::AtlHresultFromLastError(), Error >= 0) )
    {
      v6 = *((_DWORD *)a3 + 8) & 7;
      v7 = 8 - v6;
      if ( !v6 )
        v7 = 0;
      if ( v7 - 1 <= 7 )
      {
        Buffer = 0;
        if ( !WriteFile(a2, &Buffer, v7, &NumberOfBytesWritten, 0) )
          return (unsigned int)ATL::AtlHresultFromLastError();
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800d3444  mov     rax, rsp
0x1800d3447  mov     [rax+10h], rbx
0x1800d344b  mov     [rax+20h], rsi
0x1800d344f  mov     [rax+8], rcx
0x1800d3453  push    rdi
0x1800d3454  sub     rsp, 30h
0x1800d3458  mov     rdi, r8
0x1800d345b  mov     dword ptr [rax+8], 0
0x1800d3462  mov     rsi, rdx
0x1800d3465  call    ?SaveObjectHeader@CLangDataPack@@AEAAJPEAXPEAUPACKDATA_OBJECTHEADER@ILangDataPack@@@Z; CLangDataPack::SaveObjectHeader(void *,ILangDataPack::PACKDATA_OBJECTHEADER *)
0x1800d346a  mov     ebx, eax
0x1800d346c  test    eax, eax
0x1800d346e  js      short loc_1800D34EC
0x1800d3470  mov     r8d, [rdi+20h]; nNumberOfBytesToWrite
0x1800d3474  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d3479  mov     rdx, [rdi+28h]; lpBuffer
0x1800d347d  mov     rcx, rsi; hFile
0x1800d3480  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800d3489  call    cs:__imp_WriteFile
0x1800d348f  test    eax, eax
0x1800d3491  jnz     short loc_1800D349E
0x1800d3493  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800d3498  mov     ebx, eax
0x1800d349a  test    eax, eax
0x1800d349c  js      short loc_1800D34EC
0x1800d349e  mov     eax, [rdi+20h]
0x1800d34a1  mov     r8d, 8
0x1800d34a7  and     eax, 7
0x1800d34aa  sub     r8d, eax
0x1800d34ad  test    eax, eax
0x1800d34af  cmovz   r8d, eax; nNumberOfBytesToWrite
0x1800d34b3  lea     eax, [r8-1]
0x1800d34b7  cmp     eax, 7
0x1800d34ba  ja      short loc_1800D34EC
0x1800d34bc  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d34c1  mov     [rsp+38h+Buffer], 0
0x1800d34ca  lea     rdx, [rsp+38h+Buffer]; lpBuffer
0x1800d34cf  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800d34d8  mov     rcx, rsi; hFile
0x1800d34db  call    cs:__imp_WriteFile
0x1800d34e1  test    eax, eax
0x1800d34e3  jnz     short loc_1800D34EC
0x1800d34e5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800d34ea  mov     ebx, eax
0x1800d34ec  mov     rsi, [rsp+38h+arg_18]
0x1800d34f1  mov     eax, ebx
0x1800d34f3  mov     rbx, [rsp+38h+arg_8]
0x1800d34f8  add     rsp, 30h
0x1800d34fc  pop     rdi
0x1800d34fd  retn
```
