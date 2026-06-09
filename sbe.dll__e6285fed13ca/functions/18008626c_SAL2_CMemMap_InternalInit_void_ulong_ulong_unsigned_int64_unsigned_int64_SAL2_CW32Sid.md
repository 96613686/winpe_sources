# SAL2::CMemMap::InternalInit(void *,ulong,ulong,unsigned __int64,unsigned __int64,SAL2::CW32Sid *)

- ea: `0x18008626c`
- end: `0x18008649b`
- name: `?InternalInit@CMemMap@SAL2@@AEAAJPEAXKK_K1PEAVCW32Sid@2@@Z`
- size: `559`
- prototype: `int(SAL2::CMemMap *__hidden this, void *, unsigned int, unsigned int, unsigned __int64, unsigned __int64, struct SAL2::CW32Sid *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180084c48`

## callees

- `0x1800017a0`
- `0x180080a48`
- `0x18008626c`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x1800862e7`
- `KERNEL32!DuplicateHandle` at `0x1800862e7`
- `KERNEL32!CloseHandle` at `0x1800863cd`
- `KERNEL32!CloseHandle` at `0x1800863cd`
- `KERNEL32!GetLastError` at `0x1800862f1`
- `KERNEL32!GetLastError` at `0x1800863a6`
- `KERNEL32!GetLastError` at `0x180086453`
- `KERNEL32!GetLastError` at `0x1800862f1`
- `KERNEL32!GetLastError` at `0x1800863a6`
- `KERNEL32!GetLastError` at `0x180086453`
- `KERNEL32!GetCurrentProcess` at `0x18008628d`
- `KERNEL32!GetCurrentProcess` at `0x18008628d`
- `KERNEL32!OpenFileMappingW` at `0x180086391`
- `KERNEL32!OpenFileMappingW` at `0x1800863bf`
- `KERNEL32!OpenFileMappingW` at `0x180086391`
- `KERNEL32!OpenFileMappingW` at `0x1800863bf`
- `KERNEL32!MapViewOfFile` at `0x180086441`
- `KERNEL32!MapViewOfFile` at `0x180086441`
- `KERNEL32!CreateFileMappingW` at `0x18008640c`
- `KERNEL32!CreateFileMappingW` at `0x18008640c`

## pseudocode

```c
__int64 __fastcall SAL2::CMemMap::InternalInit(
        SAL2::CMemMap *this,
        void *a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int64 dwFileOffsetLow,
        unsigned __int64 a6,
        struct SAL2::CW32Sid *a7)
{
  HANDLE CurrentProcess; // rax
  unsigned __int64 v10; // rsi
  __int64 v11; // rbx
  unsigned int v12; // ebx
  signed int v13; // eax
  SAL2::CSALSecurityObject *v14; // rax
  enum _ACCESS_MODE v15; // r8d
  __int64 v16; // r14
  int v17; // ebx
  HANDLE v18; // rax
  void *v19; // rcx
  signed int LastError; // eax
  HANDLE v21; // rax
  DWORD v22; // r15d
  HANDLE FileMappingW; // rax
  LPVOID v24; // rax
  enum _ACCESS_MODE dwDesiredAccess; // [rsp+20h] [rbp-48h]
  unsigned int v27; // [rsp+88h] [rbp+20h] BYREF

  v27 = a4;
  CurrentProcess = GetCurrentProcess();
  v10 = dwFileOffsetLow;
  v11 = a6 - dwFileOffsetLow;
  if ( ((a6 - dwFileOffsetLow) & 0xFFFFFFFF00000000uLL) != 0 )
    return (unsigned int)-2147024809;
  if ( DuplicateHandle(CurrentProcess, a2, CurrentProcess, (LPHANDLE)this + 70, 0, 0, 2u) )
  {
    *((_QWORD *)this + 69) = v11;
    v27 = 0;
    v14 = (SAL2::CSALSecurityObject *)operator new(0x40u);
    if ( !v14 )
      return (unsigned int)-2147024882;
    v16 = SAL2::CSALSecurityObject::CSALSecurityObject(v14, a7, v15, 0xF001Fu, dwDesiredAccess, 0xF001Fu, &v27);
    if ( !v16 )
      return (unsigned int)-2147024882;
    v12 = v27;
    if ( v27 )
    {
      if ( (int)v27 > 0 )
      {
        v17 = (unsigned __int16)v27;
LABEL_22:
        v12 = v17 | 0x80070000;
        goto LABEL_23;
      }
      goto LABEL_23;
    }
    v18 = OpenFileMappingW(6u, 0, (LPCWSTR)this + 8);
    *((_QWORD *)this + 67) = v18;
    v19 = v18;
    if ( v18 )
    {
      v22 = v10;
    }
    else
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError != 2 )
        goto LABEL_20;
      v21 = OpenFileMappingW(6u, 0, (LPCWSTR)this + 8);
      if ( v21 )
      {
        CloseHandle(v21);
        v12 = -2147024713;
        goto LABEL_23;
      }
      v22 = v10;
      FileMappingW = CreateFileMappingW(
                       a2,
                       *(LPSECURITY_ATTRIBUTES *)(v16 + 48),
                       4u,
                       (v10 + *((_QWORD *)this + 69)) >> 32,
                       (int)v10 + *((_DWORD *)this + 138),
                       (LPCWSTR)this + 8);
      *((_QWORD *)this + 67) = FileMappingW;
      v19 = FileMappingW;
      if ( !FileMappingW )
      {
LABEL_19:
        LastError = GetLastError();
        v12 = LastError;
LABEL_20:
        if ( LastError > 0 )
        {
          v17 = (unsigned __int16)LastError;
          goto LABEL_22;
        }
LABEL_23:
        (**(void (__fastcall ***)(__int64, __int64))v16)(v16, 1);
        return v12;
      }
    }
    v12 = 0;
    v24 = MapViewOfFile(v19, 6u, HIDWORD(v10), v22, *((_QWORD *)this + 69));
    *((_QWORD *)this + 68) = v24;
    if ( v24 )
      goto LABEL_23;
    goto LABEL_19;
  }
  v13 = GetLastError();
  v12 = v13;
  if ( v13 > 0 )
    return (unsigned __int16)v13 | 0x80070000;
  return v12;
}

```

## disassembly

```asm
0x18008626c  mov     [rsp+arg_0], rbx
0x180086271  mov     [rsp+arg_8], rbp
0x180086276  mov     [rsp+arg_18], r9d
0x18008627b  push    rsi
0x18008627c  push    rdi
0x18008627d  push    r12
0x18008627f  push    r14
0x180086281  push    r15
0x180086283  sub     rsp, 40h
0x180086287  mov     r12, rdx
0x18008628a  mov     rdi, rcx
0x18008628d  call    cs:__imp_GetCurrentProcess
0x180086293  mov     rbx, [rsp+68h+arg_28]
0x18008629b  mov     rcx, 0FFFFFFFF00000000h
0x1800862a5  mov     rsi, [rsp+68h+dwFileOffsetLow]
0x1800862ad  sub     rbx, rsi
0x1800862b0  test    rcx, rbx
0x1800862b3  jz      short loc_1800862BF
0x1800862b5  mov     ebx, 80070057h
0x1800862ba  jmp     loc_180086482
0x1800862bf  mov     [rsp+68h+dwOptions], 2; dwOptions
0x1800862c7  lea     r9, [rdi+230h]; lpTargetHandle
0x1800862ce  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x1800862d6  mov     r8, rax; hTargetProcessHandle
0x1800862d9  mov     rdx, r12; hSourceHandle
0x1800862dc  mov     [rsp+68h+dwDesiredAccess], 0; enum _ACCESS_MODE
0x1800862e4  mov     rcx, rax; hSourceProcessHandle
0x1800862e7  call    cs:__imp_DuplicateHandle
0x1800862ed  test    eax, eax
0x1800862ef  jnz     short loc_18008630F
0x1800862f1  call    cs:__imp_GetLastError
0x1800862f7  mov     ebx, eax
0x1800862f9  test    eax, eax
0x1800862fb  jle     loc_180086482
0x180086301  movzx   ebx, ax
0x180086304  or      ebx, 80070000h
0x18008630a  jmp     loc_180086482
0x18008630f  mov     ecx, 40h ; '@'; Size
0x180086314  mov     [rdi+228h], rbx
0x18008631b  mov     [rsp+68h+arg_18], 0
0x180086326  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008632b  test    rax, rax
0x18008632e  jz      loc_18008647D
0x180086334  mov     rdx, [rsp+68h+arg_30]; struct SAL2::CW32Sid *
0x18008633c  lea     rcx, [rsp+68h+arg_18]
0x180086344  mov     qword ptr [rsp+68h+dwOptions], rcx; unsigned int *
0x180086349  mov     r9d, 0F001Fh; unsigned int
0x18008634f  mov     rcx, rax; this
0x180086352  mov     [rsp+68h+bInheritHandle], r9d; unsigned int
0x180086357  call    ??0CSALSecurityObject@SAL2@@QEAA@PEAVCW32Sid@1@W4_ACCESS_MODE@@K1KPEAK@Z; SAL2::CSALSecurityObject::CSALSecurityObject(SAL2::CW32Sid *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,ulong *)
0x18008635c  mov     r14, rax
0x18008635f  test    rax, rax
0x180086362  jz      loc_18008647D
0x180086368  mov     ebx, [rsp+68h+arg_18]
0x18008636f  test    ebx, ebx
0x180086371  jz      short loc_180086381
0x180086373  jle     loc_180086468
0x180086379  movzx   ebx, bx
0x18008637c  jmp     loc_180086462
0x180086381  xor     edx, edx; bInheritHandle
0x180086383  lea     rbp, [rdi+10h]
0x180086387  mov     r8, rbp; lpName
0x18008638a  lea     r15d, [rdx+6]
0x18008638e  mov     ecx, r15d; dwDesiredAccess
0x180086391  call    cs:__imp_OpenFileMappingW
0x180086397  mov     [rdi+218h], rax
0x18008639e  mov     rcx, rax; hFileMappingObject
0x1800863a1  test    rax, rax
0x1800863a4  jnz     short loc_180086423
0x1800863a6  call    cs:__imp_GetLastError
0x1800863ac  mov     ebx, eax
0x1800863ae  cmp     eax, 2
0x1800863b1  jnz     loc_18008645B
0x1800863b7  mov     r8, rbp; lpName
0x1800863ba  xor     edx, edx; bInheritHandle
0x1800863bc  mov     ecx, r15d; dwDesiredAccess
0x1800863bf  call    cs:__imp_OpenFileMappingW
0x1800863c5  test    rax, rax
0x1800863c8  jz      short loc_1800863DD
0x1800863ca  mov     rcx, rax; hObject
0x1800863cd  call    cs:__imp_CloseHandle
0x1800863d3  mov     ebx, 800700B7h
0x1800863d8  jmp     loc_180086468
0x1800863dd  mov     ecx, [rdi+228h]
0x1800863e3  mov     r8d, 4; flProtect
0x1800863e9  mov     r9, [rdi+228h]
0x1800863f0  add     ecx, esi
0x1800863f2  mov     rdx, [r14+30h]; lpFileMappingAttributes
0x1800863f6  add     r9, rsi
0x1800863f9  mov     qword ptr [rsp+68h+bInheritHandle], rbp; lpName
0x1800863fe  mov     r15d, esi
0x180086401  mov     [rsp+68h+dwDesiredAccess], ecx; dwMaximumSizeLow
0x180086405  mov     rcx, r12; hFile
0x180086408  shr     r9, 20h; dwMaximumSizeHigh
0x18008640c  call    cs:__imp_CreateFileMappingW
0x180086412  mov     [rdi+218h], rax
0x180086419  mov     rcx, rax
0x18008641c  test    rax, rax
0x18008641f  jnz     short loc_180086426
0x180086421  jmp     short loc_180086453
0x180086423  mov     r15d, esi
0x180086426  mov     rax, [rdi+228h]
0x18008642d  xor     ebx, ebx
0x18008642f  shr     rsi, 20h
0x180086433  mov     r9d, r15d; dwFileOffsetLow
0x180086436  mov     r8d, esi; dwFileOffsetHigh
0x180086439  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; dwNumberOfBytesToMap
0x18008643e  lea     edx, [rbx+6]; dwDesiredAccess
0x180086441  call    cs:__imp_MapViewOfFile
0x180086447  mov     [rdi+220h], rax
0x18008644e  test    rax, rax
0x180086451  jnz     short loc_180086468
0x180086453  call    cs:__imp_GetLastError
0x180086459  mov     ebx, eax
0x18008645b  test    eax, eax
0x18008645d  jle     short loc_180086468
0x18008645f  movzx   ebx, ax
0x180086462  or      ebx, 80070000h
0x180086468  mov     rax, [r14]
0x18008646b  mov     edx, 1
0x180086470  mov     rcx, r14
0x180086473  mov     rax, [rax]
0x180086476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008647b  jmp     short loc_180086482
0x18008647d  mov     ebx, 8007000Eh
0x180086482  mov     rbp, [rsp+68h+arg_8]
0x180086487  mov     eax, ebx
0x180086489  mov     rbx, [rsp+68h+arg_0]
0x18008648e  add     rsp, 40h
0x180086492  pop     r15
0x180086494  pop     r14
0x180086496  pop     r12
0x180086498  pop     rdi
0x180086499  pop     rsi
0x18008649a  retn
```
