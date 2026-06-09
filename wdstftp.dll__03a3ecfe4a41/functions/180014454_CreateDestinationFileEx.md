# CreateDestinationFileEx

- ea: `0x180014454`
- end: `0x180014772`
- name: `CreateDestinationFileEx`
- size: `798`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800143d8`

## callees

- `0x180014454`
- `0x180017344`
- `0x180020cc8`
- `0x180021194`
- `0x180021484`
- `0x1800607b0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1800145e2`
- `KERNEL32!DeviceIoControl` at `0x180014628`
- `KERNEL32!DeviceIoControl` at `0x1800145e2`
- `KERNEL32!DeviceIoControl` at `0x180014628`
- `KERNEL32!GetLastError` at `0x18001463a`
- `KERNEL32!GetLastError` at `0x180014646`
- `KERNEL32!GetLastError` at `0x1800146ae`
- `KERNEL32!GetLastError` at `0x18001463a`
- `KERNEL32!GetLastError` at `0x180014646`
- `KERNEL32!GetLastError` at `0x1800146ae`
- `KERNEL32!GetFileAttributesW` at `0x1800144b7`
- `KERNEL32!GetFileAttributesW` at `0x1800144b7`
- `KERNEL32!CloseHandle` at `0x18001470f`
- `KERNEL32!CloseHandle` at `0x18001470f`
- `KERNEL32!SetLastError` at `0x180014731`
- `KERNEL32!SetLastError` at `0x180014746`
- `KERNEL32!SetLastError` at `0x180014731`
- `KERNEL32!SetLastError` at `0x180014746`
- `KERNEL32!SetFilePointerEx` at `0x180014539`
- `KERNEL32!SetFilePointerEx` at `0x180014574`
- `KERNEL32!SetFilePointerEx` at `0x180014539`
- `KERNEL32!SetFilePointerEx` at `0x180014574`
- `KERNEL32!SetEndOfFile` at `0x180014550`
- `KERNEL32!SetEndOfFile` at `0x180014550`
- `KERNEL32!DeleteFileW` at `0x18001471f`
- `KERNEL32!DeleteFileW` at `0x18001471f`

## string_xrefs

- `0x1800146d7`: `CreateFile failed`
- `0x18001466a`: `CreateDestinationFileEx`
- `0x1800146cd`: `CreateDestinationFileEx`
- `0x180014675`: `SetFileSize failed`

## pseudocode

```c
__int64 __fastcall CreateDestinationFileEx(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        LARGE_INTEGER *a5,
        _QWORD *a6,
        int a7)
{
  unsigned int v7; // ebp
  int LastError; // edi
  __int64 v12; // rdx
  int v13; // r15d
  __int64 v14; // r8
  __int64 v15; // rax
  void *File; // rax
  void *v17; // rsi
  LARGE_INTEGER v18; // rax
  signed int v19; // eax
  NTSTATUS Status; // r8d
  NTSTATUS v21; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-68h] BYREF
  _QWORD InBuffer[2]; // [rsp+48h] [rbp-60h] BYREF

  v7 = 0;
  LastError = 0;
  if ( !a2 || !a6 )
  {
    SetLastError(0x57u);
    return 0;
  }
  if ( a4 == 2 && (a3 & 0x100) == 0 && GetFileAttributesW(*(LPCWSTR *)(a2 + 8)) != -1 )
    WimDeleteFile(*(LPCWSTR *)(a2 + 8));
  v12 = *(_QWORD *)(a2 + 8);
  v13 = a3 | 0x2200000;
  v14 = 3239903488LL;
  v15 = a1;
  if ( *(_QWORD *)(a1 + 64) )
    v15 = *(_QWORD *)(a1 + 64);
  BytesReturned = *(_DWORD *)(v15 + 36);
  if ( (BytesReturned & 0x30000) != 0x10000 )
    v14 = 3222339840LL;
  File = (void *)WimImageCreateFile(a1, v12, v14);
  v17 = File;
  if ( File == (void *)-1LL )
  {
    LastError = GetLastError();
    if ( !a7 )
      goto LABEL_35;
    v21 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v21 = LastError;
    WIMLogMsg(1, a1, *(_QWORD *)(a2 + 8), (int)L"CreateFile failed", v21, (__int64)L"CreateDestinationFileEx", 3500);
  }
  else
  {
    if ( !a5 || SetFilePointerEx(File, *a5, 0, 0) && SetEndOfFile(v17) && SetFilePointerEx(v17, g_liZero, 0, 0) )
    {
      v7 = 1;
      if ( !a5
        || (BytesReturned & 0x1000000) == 0
        || (v13 & 0x4000100) != 0
        || *(_DWORD *)(a2 + 32)
        || (v7 = 0, DeviceIoControl(v17, 0x900C4u, 0, 0, 0, 0, &BytesReturned, 0))
        && (v18 = *a5,
            InBuffer[0] = 0,
            InBuffer[1] = v18.QuadPart,
            (v7 = DeviceIoControl(v17, 0x980C8u, InBuffer, 0x10u, 0, 0, &BytesReturned, 0)) != 0) )
      {
        *a6 = v17;
        WIMSetFileShortName(a1, v17, *(_QWORD *)(a2 + 8), *(_QWORD *)(a2 + 24));
        goto LABEL_32;
      }
      GetLastError();
    }
    v19 = GetLastError();
    LastError = v19;
    if ( !a7 )
      goto LABEL_33;
    Status = (unsigned __int16)v19 | 0x80070000;
    if ( v19 <= 0 )
      Status = v19;
    WIMLogMsg(1, a1, *(_QWORD *)(a2 + 8), (int)L"SetFileSize failed", Status, (__int64)L"CreateDestinationFileEx", 3489);
  }
LABEL_32:
  if ( !v7 )
  {
LABEL_33:
    if ( v17 != (void *)-1LL )
    {
      CloseHandle(v17);
      DeleteFileW(*(LPCWSTR *)(a2 + 8));
    }
  }
LABEL_35:
  if ( LastError )
    SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x180014454  push    rbx
0x180014456  push    rbp
0x180014457  push    rsi
0x180014458  push    rdi
0x180014459  push    r12
0x18001445b  push    r13
0x18001445d  push    r14
0x18001445f  push    r15
0x180014461  sub     rsp, 68h
0x180014465  mov     rax, cs:__security_cookie
0x18001446c  xor     rax, rsp
0x18001446f  mov     [rsp+0A8h+var_50], rax
0x180014474  mov     r14, [rsp+0A8h+arg_20]
0x18001447c  xor     ebp, ebp
0x18001447e  mov     r13, [rsp+0A8h+arg_28]
0x180014486  xor     edi, edi
0x180014488  mov     esi, r9d
0x18001448b  mov     r15d, r8d
0x18001448e  mov     rbx, rdx
0x180014491  mov     r12, rcx
0x180014494  test    rdx, rdx
0x180014497  jz      loc_180014741
0x18001449d  test    r13, r13
0x1800144a0  jz      loc_180014741
0x1800144a6  cmp     r9d, 2
0x1800144aa  jnz     short loc_1800144D1
0x1800144ac  bt      r8d, 8
0x1800144b1  jb      short loc_1800144D1
0x1800144b3  mov     rcx, [rdx+8]; lpFileName
0x1800144b7  call    cs:__imp_GetFileAttributesW
0x1800144be  nop     dword ptr [rax+rax+00h]
0x1800144c3  cmp     eax, 0FFFFFFFFh
0x1800144c6  jz      short loc_1800144D1
0x1800144c8  mov     rcx, [rbx+8]; lpFileName
0x1800144cc  call    WimDeleteFile
0x1800144d1  mov     rdx, [rbx+8]
0x1800144d5  or      r15d, 2200000h
0x1800144dc  cmp     [r12+40h], rdi
0x1800144e1  mov     ecx, 0C0110100h
0x1800144e6  mov     r8d, 0C11D0100h
0x1800144ec  mov     dword ptr [rsp+0A8h+lpBytesReturned], r15d
0x1800144f1  mov     rax, r12
0x1800144f4  mov     [rsp+0A8h+nOutBufferSize], esi; nOutBufferSize
0x1800144f8  cmovnz  rax, [r12+40h]
0x1800144fe  mov     eax, [rax+24h]
0x180014501  mov     [rsp+0A8h+BytesReturned], eax
0x180014505  and     eax, 30000h
0x18001450a  cmp     eax, 10000h
0x18001450f  cmovnz  r8d, ecx
0x180014513  mov     rcx, r12
0x180014516  call    WimImageCreateFile
0x18001451b  mov     rsi, rax
0x18001451e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014522  jz      loc_1800146AE
0x180014528  test    r14, r14
0x18001452b  jz      short loc_180014588
0x18001452d  mov     rdx, [r14]; liDistanceToMove
0x180014530  xor     r9d, r9d; dwMoveMethod
0x180014533  xor     r8d, r8d; lpNewFilePointer
0x180014536  mov     rcx, rax; hFile
0x180014539  call    cs:__imp_SetFilePointerEx
0x180014540  nop     dword ptr [rax+rax+00h]
0x180014545  test    eax, eax
0x180014547  jz      loc_180014646
0x18001454d  mov     rcx, rsi; hFile
0x180014550  call    cs:__imp_SetEndOfFile
0x180014557  nop     dword ptr [rax+rax+00h]
0x18001455c  test    eax, eax
0x18001455e  jz      loc_180014646
0x180014564  mov     rdx, qword ptr cs:g_liZero; liDistanceToMove
0x18001456b  xor     r9d, r9d; dwMoveMethod
0x18001456e  xor     r8d, r8d; lpNewFilePointer
0x180014571  mov     rcx, rsi; hFile
0x180014574  call    cs:__imp_SetFilePointerEx
0x18001457b  nop     dword ptr [rax+rax+00h]
0x180014580  test    eax, eax
0x180014582  jz      loc_180014646
0x180014588  mov     ebp, 1
0x18001458d  test    r14, r14
0x180014590  jz      loc_180014695
0x180014596  test    [rsp+0A8h+BytesReturned], 1000000h
0x18001459e  jz      loc_180014695
0x1800145a4  test    r15d, 4000100h
0x1800145ab  jnz     loc_180014695
0x1800145b1  cmp     [rbx+20h], edi
0x1800145b4  jnz     loc_180014695
0x1800145ba  and     [rsp+0A8h+var_70], rdi
0x1800145bf  lea     rax, [rsp+0A8h+BytesReturned]
0x1800145c4  mov     [rsp+0A8h+lpBytesReturned], rax; lpBytesReturned
0x1800145c9  xor     r9d, r9d; nInBufferSize
0x1800145cc  and     [rsp+0A8h+nOutBufferSize], edi
0x1800145d0  xor     r8d, r8d; lpInBuffer
0x1800145d3  and     qword ptr [rsp+0A8h+Status], rdi
0x1800145d8  mov     edx, 900C4h; dwIoControlCode
0x1800145dd  mov     rcx, rsi; hDevice
0x1800145e0  xor     ebp, ebp
0x1800145e2  call    cs:__imp_DeviceIoControl
0x1800145e9  nop     dword ptr [rax+rax+00h]
0x1800145ee  test    eax, eax
0x1800145f0  jz      short loc_18001463A
0x1800145f2  mov     rax, [r14]
0x1800145f5  lea     r9d, [rbp+10h]; nInBufferSize
0x1800145f9  and     [rsp+0A8h+var_70], rdi
0x1800145fe  lea     r8, [rsp+0A8h+InBuffer]; lpInBuffer
0x180014603  and     [rsp+0A8h+InBuffer], rdi
0x180014608  mov     edx, 980C8h; dwIoControlCode
0x18001460d  mov     [rsp+0A8h+var_58], rax
0x180014612  mov     rcx, rsi; hDevice
0x180014615  lea     rax, [rsp+0A8h+BytesReturned]
0x18001461a  mov     [rsp+0A8h+lpBytesReturned], rax; lpBytesReturned
0x18001461f  and     [rsp+0A8h+nOutBufferSize], edi
0x180014623  and     qword ptr [rsp+0A8h+Status], rdi
0x180014628  call    cs:__imp_DeviceIoControl
0x18001462f  nop     dword ptr [rax+rax+00h]
0x180014634  mov     ebp, eax
0x180014636  test    eax, eax
0x180014638  jnz     short loc_180014695
0x18001463a  call    cs:__imp_GetLastError
0x180014641  nop     dword ptr [rax+rax+00h]
0x180014646  call    cs:__imp_GetLastError
0x18001464d  nop     dword ptr [rax+rax+00h]
0x180014652  cmp     [rsp+0A8h+arg_30], 0
0x18001465a  mov     edi, eax
0x18001465c  jz      loc_180014706
0x180014662  mov     dword ptr [rsp+0A8h+lpBytesReturned], 0DA1h
0x18001466a  lea     rcx, aCreatedestinat; "CreateDestinationFileEx"
0x180014671  movzx   r8d, ax
0x180014675  lea     r9, aSetfilesizeFai; "SetFileSize failed"
0x18001467c  or      r8d, 80070000h
0x180014683  mov     qword ptr [rsp+0A8h+nOutBufferSize], rcx
0x180014688  test    eax, eax
0x18001468a  cmovle  r8d, eax
0x18001468e  mov     [rsp+0A8h+Status], r8d
0x180014693  jmp     short loc_1800146F1
0x180014695  mov     [r13+0], rsi
0x180014699  mov     rdx, rsi
0x18001469c  mov     r9, [rbx+18h]
0x1800146a0  mov     rcx, r12
0x1800146a3  mov     r8, [rbx+8]
0x1800146a7  call    WIMSetFileShortName
0x1800146ac  jmp     short loc_180014702
0x1800146ae  call    cs:__imp_GetLastError
0x1800146b5  nop     dword ptr [rax+rax+00h]
0x1800146ba  mov     edi, eax
0x1800146bc  cmp     [rsp+0A8h+arg_30], ebp
0x1800146c3  jz      short loc_18001472B
0x1800146c5  mov     dword ptr [rsp+0A8h+lpBytesReturned], 0DACh; int
0x1800146cd  lea     rcx, aCreatedestinat; "CreateDestinationFileEx"
0x1800146d4  movzx   eax, di
0x1800146d7  lea     r9, aCreatefileFail; "CreateFile failed"
0x1800146de  or      eax, 80070000h
0x1800146e3  mov     qword ptr [rsp+0A8h+nOutBufferSize], rcx; __int64
0x1800146e8  test    edi, edi
0x1800146ea  cmovle  eax, edi
0x1800146ed  mov     [rsp+0A8h+Status], eax; Status
0x1800146f1  mov     r8, [rbx+8]; int
0x1800146f5  mov     rdx, r12; int
0x1800146f8  mov     ecx, 1; int
0x1800146fd  call    _WIMLogMsg
0x180014702  test    ebp, ebp
0x180014704  jnz     short loc_18001472B
0x180014706  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001470a  jz      short loc_18001472B
0x18001470c  mov     rcx, rsi; hObject
0x18001470f  call    cs:__imp_CloseHandle
0x180014716  nop     dword ptr [rax+rax+00h]
0x18001471b  mov     rcx, [rbx+8]; lpFileName
0x18001471f  call    cs:__imp_DeleteFileW
0x180014726  nop     dword ptr [rax+rax+00h]
0x18001472b  test    edi, edi
0x18001472d  jz      short loc_18001473D
0x18001472f  mov     ecx, edi; dwErrCode
0x180014731  call    cs:__imp_SetLastError
0x180014738  nop     dword ptr [rax+rax+00h]
0x18001473d  mov     eax, ebp
0x18001473f  jmp     short loc_180014754
0x180014741  mov     ecx, 57h ; 'W'; dwErrCode
0x180014746  call    cs:__imp_SetLastError
0x18001474d  nop     dword ptr [rax+rax+00h]
0x180014752  xor     eax, eax
0x180014754  mov     rcx, [rsp+0A8h+var_50]
0x180014759  xor     rcx, rsp; StackCookie
0x18001475c  call    __security_check_cookie
0x180014761  add     rsp, 68h
0x180014765  pop     r15
0x180014767  pop     r14
0x180014769  pop     r13
0x18001476b  pop     r12
0x18001476d  pop     rdi
0x18001476e  pop     rsi
0x18001476f  pop     rbp
0x180014770  pop     rbx
0x180014771  retn
```
