# IO::InputFile::ReadData(void *,unsigned __int64)

- ea: `0x140084970`
- end: `0x140084a10`
- name: `?ReadData@InputFile@IO@@UEAA_KPEAX_K@Z`
- size: `160`
- prototype: `unsigned __int64 __fastcall(IO::InputFile *__hidden this, void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x140006338`
- `0x140060f58`
- `0x140084970`
- `0x140084c24`

## import_xrefs

- `KERNEL32!ReadFile` at `0x140084996`
- `KERNEL32!ReadFile` at `0x140084996`
- `KERNEL32!GetLastError` at `0x1400849af`
- `KERNEL32!GetLastError` at `0x1400849af`

## pseudocode

```c
unsigned __int64 __fastcall IO::InputFile::ReadData(IO::InputFile *this, void *a2, __int64 a3)
{
  void *v3; // rcx
  signed int LastError; // eax
  __int64 v7; // r8
  unsigned int v8; // ebx
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  DWORD v10; // [rsp+70h] [rbp+8h] BYREF

  v3 = (void *)*((_QWORD *)this + 2);
  v10 = 0;
  if ( !ReadFile(v3, a2, a3, &v10, 0) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Pd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, v7, a3, v8);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return v10;
}

```

## disassembly

```asm
0x140084970  mov     rax, rsp
0x140084973  mov     [rax+10h], rbx
0x140084977  push    rdi
0x140084978  sub     rsp, 60h
0x14008497c  mov     rcx, [rcx+10h]; hFile
0x140084980  lea     r9, [rax+8]; lpNumberOfBytesRead
0x140084984  mov     rdi, r8
0x140084987  mov     dword ptr [rax+8], 0
0x14008498e  mov     qword ptr [rax-48h], 0
0x140084996  call    cs:__imp_ReadFile
0x14008499c  test    eax, eax
0x14008499e  jz      short loc_1400849AF
0x1400849a0  mov     eax, [rsp+68h+arg_0]
0x1400849a4  mov     rbx, [rsp+68h+arg_8]
0x1400849a9  add     rsp, 60h
0x1400849ad  pop     rdi
0x1400849ae  retn
0x1400849af  call    cs:__imp_GetLastError
0x1400849b5  mov     ebx, eax
0x1400849b7  test    eax, eax
0x1400849b9  jle     short loc_1400849C4
0x1400849bb  movzx   ebx, ax
0x1400849be  or      ebx, 80070000h
0x1400849c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400849cb  lea     rax, WPP_GLOBAL_Control
0x1400849d2  cmp     rcx, rax
0x1400849d5  jz      short loc_1400849F2
0x1400849d7  test    byte ptr [rcx+1Ch], 1
0x1400849db  jz      short loc_1400849F2
0x1400849dd  mov     rcx, [rcx+10h]
0x1400849e1  mov     edx, 10h
0x1400849e6  mov     r9, rdi
0x1400849e9  mov     [rsp+68h+var_48], ebx
0x1400849ed  call    WPP_SF_Pd
0x1400849f2  mov     edx, ebx; int
0x1400849f4  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1400849f9  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400849fe  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140084a05  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x140084a0a  call    _CxxThrowException_0
```
