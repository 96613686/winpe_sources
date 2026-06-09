# IO::InputFile::Peek(void)

- ea: `0x140084840`
- end: `0x14008495e`
- name: `?Peek@InputFile@IO@@UEBADXZ`
- size: `286`
- prototype: `char __fastcall(IO::InputFile *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x140006338`
- `0x14001f6b4`
- `0x140060f58`
- `0x140084840`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x140084882`
- `KERNEL32!SetFilePointerEx` at `0x140084882`
- `KERNEL32!ReadFile` at `0x140084867`
- `KERNEL32!ReadFile` at `0x140084867`
- `KERNEL32!GetLastError` at `0x140084896`
- `KERNEL32!GetLastError` at `0x1400848fa`
- `KERNEL32!GetLastError` at `0x140084896`
- `KERNEL32!GetLastError` at `0x1400848fa`

## pseudocode

```c
char __fastcall IO::InputFile::Peek(HANDLE *this)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  signed int v5; // eax
  unsigned int v6; // ebx
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  char Buffer; // [rsp+70h] [rbp+8h] BYREF

  Buffer = 0;
  if ( !ReadFile(this[2], &Buffer, 1u, 0, 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_fc52131781a63b563a504d48059c77ca_Traceguids, v4);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v4);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( !SetFilePointerEx(this[2], (LARGE_INTEGER)-1LL, 0, 1u) )
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_fc52131781a63b563a504d48059c77ca_Traceguids, v6);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v6);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return Buffer;
}

```

## disassembly

```asm
0x140084840  push    rbx
0x140084842  sub     rsp, 60h
0x140084846  xor     r9d, r9d; lpNumberOfBytesRead
0x140084849  mov     [rsp+68h+Buffer], 0
0x14008484e  mov     rbx, rcx
0x140084851  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x14008485a  mov     rcx, [rcx+10h]; hFile
0x14008485e  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x140084863  lea     r8d, [r9+1]; nNumberOfBytesToRead
0x140084867  call    cs:__imp_ReadFile
0x14008486d  test    eax, eax
0x14008486f  jz      short loc_140084896
0x140084871  mov     rcx, [rbx+10h]; hFile
0x140084875  mov     r9d, 1; dwMoveMethod
0x14008487b  xor     r8d, r8d; lpNewFilePointer
0x14008487e  or      rdx, 0FFFFFFFFFFFFFFFFh; liDistanceToMove
0x140084882  call    cs:__imp_SetFilePointerEx
0x140084888  test    eax, eax
0x14008488a  jz      short loc_1400848FA
0x14008488c  mov     al, [rsp+68h+Buffer]
0x140084890  add     rsp, 60h
0x140084894  pop     rbx
0x140084895  retn
0x140084896  call    cs:__imp_GetLastError
0x14008489c  mov     ebx, eax
0x14008489e  test    eax, eax
0x1400848a0  jle     short loc_1400848AB
0x1400848a2  movzx   ebx, ax
0x1400848a5  or      ebx, 80070000h
0x1400848ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400848b2  lea     rax, WPP_GLOBAL_Control
0x1400848b9  cmp     rcx, rax
0x1400848bc  jz      short loc_1400848DC
0x1400848be  test    byte ptr [rcx+1Ch], 1
0x1400848c2  jz      short loc_1400848DC
0x1400848c4  mov     rcx, [rcx+10h]
0x1400848c8  lea     r8, WPP_fc52131781a63b563a504d48059c77ca_Traceguids
0x1400848cf  mov     edx, 0Ch
0x1400848d4  mov     r9d, ebx
0x1400848d7  call    WPP_SF_d
0x1400848dc  mov     edx, ebx; int
0x1400848de  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1400848e3  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400848e8  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400848ef  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1400848f4  call    _CxxThrowException_0
0x1400848fa  call    cs:__imp_GetLastError
0x140084900  mov     ebx, eax
0x140084902  test    eax, eax
0x140084904  jle     short loc_14008490F
0x140084906  movzx   ebx, ax
0x140084909  or      ebx, 80070000h
0x14008490f  mov     rcx, cs:WPP_GLOBAL_Control
0x140084916  lea     rax, WPP_GLOBAL_Control
0x14008491d  cmp     rcx, rax
0x140084920  jz      short loc_140084940
0x140084922  test    byte ptr [rcx+1Ch], 1
0x140084926  jz      short loc_140084940
0x140084928  mov     rcx, [rcx+10h]
0x14008492c  lea     r8, WPP_fc52131781a63b563a504d48059c77ca_Traceguids
0x140084933  mov     edx, 0Dh
0x140084938  mov     r9d, ebx
0x14008493b  call    WPP_SF_d
0x140084940  mov     edx, ebx; int
0x140084942  lea     rcx, [rsp+68h+pExceptionObject]; this
0x140084947  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14008494c  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140084953  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x140084958  call    _CxxThrowException_0
```
