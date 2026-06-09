# CUxThemeFile::OpenFromHandle(void *,void *,ulong,int)

- ea: `0x18000f700`
- end: `0x18000f830`
- name: `?OpenFromHandle@CUxThemeFile@@QEAAJPEAX0KH@Z`
- size: `304`
- prototype: `__int64 __fastcall(CUxThemeFile *this, HANDLE hFileMappingObject, HANDLE)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d524`

## callees

- `0x18000f2d4`
- `0x18000f300`
- `0x18000f5e0`
- `0x18000f700`
- `0x18000f838`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000f750`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000f79f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000f750`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000f79f`

## pseudocode

```c
__int64 __fastcall CUxThemeFile::OpenFromHandle(CUxThemeFile *this, HANDLE hFileMappingObject, HANDLE a3)
{
  _QWORD *v3; // rbx
  _QWORD *v5; // rsi
  _QWORD *v8; // r15
  LPVOID v9; // rax
  signed int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // r14
  LPVOID v13; // rax
  signed int ErrorLast; // eax
  int v15; // eax

  v3 = (_QWORD *)((char *)this + 8);
  v5 = (_QWORD *)((char *)this + 24);
  if ( *((_QWORD *)this + 1) || *v5 )
  {
    CUxThemeFile::CloseFile(this);
    v8 = (_QWORD *)((char *)this + 8);
  }
  else
  {
    v8 = (_QWORD *)((char *)this + 8);
  }
  v9 = MapViewOfFile(hFileMappingObject, 6u, 0, 0, 0);
  *v3 = v9;
  if ( v9 )
  {
    v12 = (_QWORD *)((char *)this + 16);
    *((_QWORD *)this + 2) = hFileMappingObject;
    v13 = MapViewOfFile(a3, 6u, 0, 0, 0);
    *v5 = v13;
    if ( v13 )
    {
      *((_QWORD *)this + 4) = a3;
      v15 = CUxThemeFile::ValidateThemeData(this, 0);
      v11 = v15;
      if ( v15 < 0 )
      {
        RecordError(v15, 0xD8u);
        *v12 = 0;
        *((_QWORD *)this + 4) = 0;
        CUxThemeFile::CloseFile(this);
        v11 = -2147024885;
        goto LABEL_13;
      }
    }
    else
    {
      ErrorLast = MakeErrorLast();
      v11 = ErrorLast;
      if ( ErrorLast < 0 )
      {
        RecordError(ErrorLast, 0xCFu);
        goto LABEL_13;
      }
    }
  }
  else
  {
    v10 = MakeErrorLast();
    v11 = v10;
    if ( v10 < 0 )
    {
      RecordError(v10, 0xC3u);
      v12 = (_QWORD *)((char *)this + 16);
LABEL_13:
      *v8 = 0;
      *v12 = 0;
      *v5 = 0;
      *((_QWORD *)this + 4) = 0;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18000f700  push    rbx
0x18000f702  push    rbp
0x18000f703  push    rsi
0x18000f704  push    rdi
0x18000f705  push    r12
0x18000f707  push    r14
0x18000f709  push    r15
0x18000f70b  sub     rsp, 30h
0x18000f70f  lea     rbx, [rcx+8]
0x18000f713  mov     rbp, r8
0x18000f716  cmp     qword ptr [rbx], 0
0x18000f71a  lea     rsi, [rcx+18h]
0x18000f71e  mov     r12, rdx
0x18000f721  mov     rdi, rcx
0x18000f724  jnz     short loc_18000F731
0x18000f726  cmp     qword ptr [rsi], 0
0x18000f72a  jnz     short loc_18000F731
0x18000f72c  mov     r15, rbx
0x18000f72f  jmp     short loc_18000F73A
0x18000f731  call    ?CloseFile@CUxThemeFile@@QEAAXXZ; CUxThemeFile::CloseFile(void)
0x18000f736  lea     r15, [rdi+8]
0x18000f73a  xor     r9d, r9d; dwFileOffsetLow
0x18000f73d  mov     [rsp+68h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x18000f746  xor     r8d, r8d; dwFileOffsetHigh
0x18000f749  mov     rcx, r12; hFileMappingObject
0x18000f74c  lea     edx, [r9+6]; dwDesiredAccess
0x18000f750  call    cs:__imp_MapViewOfFile
0x18000f756  mov     [rbx], rax
0x18000f759  test    rax, rax
0x18000f75c  jnz     short loc_18000F782
0x18000f75e  call    ?MakeErrorLast@@YAJXZ; MakeErrorLast(void)
0x18000f763  mov     ebx, eax
0x18000f765  test    eax, eax
0x18000f767  jns     loc_18000F81F
0x18000f76d  mov     edx, 0C3h; unsigned int
0x18000f772  mov     ecx, eax; int
0x18000f774  call    ?RecordError@@YAXJI@Z; RecordError(long,uint)
0x18000f779  lea     r14, [rdi+10h]
0x18000f77d  jmp     loc_18000F802
0x18000f782  xor     r9d, r9d; dwFileOffsetLow
0x18000f785  mov     [rsp+68h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x18000f78e  lea     r14, [rdi+10h]
0x18000f792  xor     r8d, r8d; dwFileOffsetHigh
0x18000f795  mov     rcx, rbp; hFileMappingObject
0x18000f798  mov     [r14], r12
0x18000f79b  lea     edx, [r9+6]; dwDesiredAccess
0x18000f79f  call    cs:__imp_MapViewOfFile
0x18000f7a5  mov     [rsi], rax
0x18000f7a8  test    rax, rax
0x18000f7ab  jnz     short loc_18000F7C6
0x18000f7ad  call    ?MakeErrorLast@@YAJXZ; MakeErrorLast(void)
0x18000f7b2  mov     ebx, eax
0x18000f7b4  test    eax, eax
0x18000f7b6  jns     short loc_18000F81F
0x18000f7b8  mov     edx, 0CFh; unsigned int
0x18000f7bd  mov     ecx, eax; int
0x18000f7bf  call    ?RecordError@@YAXJI@Z; RecordError(long,uint)
0x18000f7c4  jmp     short loc_18000F802
0x18000f7c6  xor     edx, edx; int
0x18000f7c8  mov     [rdi+20h], rbp
0x18000f7cc  mov     rcx, rdi; this
0x18000f7cf  call    ?ValidateThemeData@CUxThemeFile@@QEAAJH@Z; CUxThemeFile::ValidateThemeData(int)
0x18000f7d4  mov     ebx, eax
0x18000f7d6  test    eax, eax
0x18000f7d8  jns     short loc_18000F81F
0x18000f7da  mov     edx, 0D8h; unsigned int
0x18000f7df  mov     ecx, eax; int
0x18000f7e1  call    ?RecordError@@YAXJI@Z; RecordError(long,uint)
0x18000f7e6  mov     rcx, rdi; this
0x18000f7e9  mov     qword ptr [r14], 0
0x18000f7f0  mov     qword ptr [rdi+20h], 0
0x18000f7f8  call    ?CloseFile@CUxThemeFile@@QEAAXXZ; CUxThemeFile::CloseFile(void)
0x18000f7fd  mov     ebx, 8007000Bh
0x18000f802  mov     qword ptr [r15], 0
0x18000f809  mov     qword ptr [r14], 0
0x18000f810  mov     qword ptr [rsi], 0
0x18000f817  mov     qword ptr [rdi+20h], 0
0x18000f81f  mov     eax, ebx
0x18000f821  add     rsp, 30h
0x18000f825  pop     r15
0x18000f827  pop     r14
0x18000f829  pop     r12
0x18000f82b  pop     rdi
0x18000f82c  pop     rsi
0x18000f82d  pop     rbp
0x18000f82e  pop     rbx
0x18000f82f  retn
```
