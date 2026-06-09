# IO::OutputFile::WriteData(void const *,unsigned __int64)

- ea: `0x140084b80`
- end: `0x140084c1c`
- name: `?WriteData@OutputFile@IO@@MEAAXPEBX_K@Z`
- size: `156`
- prototype: `void __fastcall(IO::OutputFile *__hidden this, const void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x140006338`
- `0x140060f58`
- `0x140084b80`
- `0x140084c24`

## import_xrefs

- `KERNEL32!WriteFile` at `0x140084ba6`
- `KERNEL32!WriteFile` at `0x140084ba6`
- `KERNEL32!GetLastError` at `0x140084bbb`
- `KERNEL32!GetLastError` at `0x140084bbb`

## pseudocode

```c
void __fastcall IO::OutputFile::WriteData(IO::OutputFile *this, const void *a2, __int64 a3)
{
  void *v3; // rcx
  signed int LastError; // eax
  __int64 v6; // r8
  unsigned int v7; // ebx
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  DWORD v9; // [rsp+70h] [rbp+8h] BYREF

  v3 = (void *)*((_QWORD *)this + 2);
  v9 = 0;
  if ( !WriteFile(v3, a2, a3, &v9, 0) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Pd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, v6, a3, v7);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v7);
    throw (ErrorCodeException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x140084b80  mov     rax, rsp
0x140084b83  mov     [rax+10h], rbx
0x140084b87  push    rdi
0x140084b88  sub     rsp, 60h
0x140084b8c  mov     rcx, [rcx+10h]; hFile
0x140084b90  lea     r9, [rax+8]; lpNumberOfBytesWritten
0x140084b94  mov     rdi, r8
0x140084b97  mov     dword ptr [rax+8], 0
0x140084b9e  mov     qword ptr [rax-48h], 0
0x140084ba6  call    cs:__imp_WriteFile
0x140084bac  test    eax, eax
0x140084bae  jz      short loc_140084BBB
0x140084bb0  mov     rbx, [rsp+68h+arg_8]
0x140084bb5  add     rsp, 60h
0x140084bb9  pop     rdi
0x140084bba  retn
0x140084bbb  call    cs:__imp_GetLastError
0x140084bc1  mov     ebx, eax
0x140084bc3  test    eax, eax
0x140084bc5  jle     short loc_140084BD0
0x140084bc7  movzx   ebx, ax
0x140084bca  or      ebx, 80070000h
0x140084bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x140084bd7  lea     rax, WPP_GLOBAL_Control
0x140084bde  cmp     rcx, rax
0x140084be1  jz      short loc_140084BFE
0x140084be3  test    byte ptr [rcx+1Ch], 1
0x140084be7  jz      short loc_140084BFE
0x140084be9  mov     rcx, [rcx+10h]
0x140084bed  mov     edx, 12h
0x140084bf2  mov     r9, rdi
0x140084bf5  mov     [rsp+68h+var_48], ebx
0x140084bf9  call    WPP_SF_Pd
0x140084bfe  mov     edx, ebx; int
0x140084c00  lea     rcx, [rsp+68h+pExceptionObject]; this
0x140084c05  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140084c0a  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140084c11  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x140084c16  call    _CxxThrowException_0
```
