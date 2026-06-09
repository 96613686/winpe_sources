# SubjectToBstr

- ea: `0x180001300`
- end: `0x18000141c`
- name: `SubjectToBstr`
- size: `284`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180001010`
- `0x1800093c0`

## callees

- `0x180001300`
- `0x1800019e0`
- `0x180001b30`
- `0x180001e20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800013b5`
- `KERNEL32!GetLastError` at `0x1800013e4`
- `KERNEL32!GetLastError` at `0x1800013b5`
- `KERNEL32!GetLastError` at `0x1800013e4`
- `KERNEL32!CloseHandle` at `0x180001351`
- `KERNEL32!CloseHandle` at `0x180001351`
- `KERNEL32!SetLastError` at `0x1800013de`
- `KERNEL32!SetLastError` at `0x180001411`
- `KERNEL32!SetLastError` at `0x1800013de`
- `KERNEL32!SetLastError` at `0x180001411`
- `KERNEL32!GetCurrentProcess` at `0x180001377`
- `KERNEL32!GetCurrentProcess` at `0x180001377`
- `KERNEL32!DuplicateHandle` at `0x18000139c`
- `KERNEL32!DuplicateHandle` at `0x18000139c`

## pseudocode

```c
__int64 __fastcall SubjectToBstr(__int64 a1, BSTR *a2)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int v7; // eax
  DWORD LastError; // edi
  HANDLE CurrentProcess; // rax
  BOOL FileHandleFromPath; // eax
  const WCHAR *v12; // rcx
  __int64 v13; // rcx
  HANDLE hObject; // [rsp+70h] [rbp+8h] BYREF

  *a2 = 0;
  v4 = *(_QWORD *)(a1 + 112);
  v5 = 0;
  hObject = 0;
  if ( v4 )
  {
    v6 = *(_QWORD *)(v4 + 8);
    if ( v6 )
    {
      v7 = ConvertTextToUnicode(v6, *(_DWORD *)(v4 + 4), a2);
    }
    else
    {
      v13 = *(_QWORD *)(v4 + 24);
      if ( !v13 )
      {
        LastError = 11;
LABEL_22:
        SetLastError(LastError);
        return v5;
      }
      v7 = ConvertTextToUnicode(v13, *(_DWORD *)(v4 + 16), a2);
    }
LABEL_4:
    if ( v7 )
    {
      LastError = 0;
      v5 = 1;
      goto LABEL_6;
    }
    goto LABEL_18;
  }
  if ( (unsigned __int64)(*(_QWORD *)(a1 + 16) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v12 = *(const WCHAR **)(a1 + 24);
    if ( !v12 )
    {
      SetLastError(0x57u);
      goto LABEL_18;
    }
    FileHandleFromPath = GetFileHandleFromPath(v12, 0x80000000, (__int64 *)&hObject);
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    FileHandleFromPath = DuplicateHandle(CurrentProcess, *(HANDLE *)(a1 + 16), CurrentProcess, &hObject, 0, 0, 2u);
  }
  if ( FileHandleFromPath )
  {
    v7 = FileToBstr(hObject, (__int64)a2);
    goto LABEL_4;
  }
LABEL_18:
  LastError = GetLastError();
LABEL_6:
  if ( hObject )
    CloseHandle(hObject);
  if ( !v5 )
    goto LABEL_22;
  return v5;
}

```

## disassembly

```asm
0x180001300  push    rbx
0x180001302  push    rbp
0x180001303  push    rsi
0x180001304  push    rdi
0x180001305  sub     rsp, 48h
0x180001309  xor     ebp, ebp
0x18000130b  mov     rsi, rdx
0x18000130e  mov     [rdx], rbp
0x180001311  mov     rdi, rcx
0x180001314  mov     rdx, [rcx+70h]
0x180001318  mov     ebx, ebp
0x18000131a  mov     [rsp+68h+hObject], rbp
0x18000131f  test    rdx, rdx
0x180001322  jz      short loc_18000136A
0x180001324  mov     rcx, [rdx+8]
0x180001328  test    rcx, rcx
0x18000132b  jz      loc_1800013F1
0x180001331  mov     edx, [rdx+4]
0x180001334  mov     r8, rsi
0x180001337  call    ConvertTextToUnicode
0x18000133c  test    eax, eax
0x18000133e  jz      short loc_1800013B5
0x180001340  mov     edi, ebp
0x180001342  mov     ebx, 1
0x180001347  mov     rcx, [rsp+68h+hObject]; hObject
0x18000134c  test    rcx, rcx
0x18000134f  jz      short loc_180001357
0x180001351  call    cs:__imp_CloseHandle
0x180001357  test    ebx, ebx
0x180001359  jz      loc_18000140F
0x18000135f  mov     eax, ebx
0x180001361  add     rsp, 48h
0x180001365  pop     rdi
0x180001366  pop     rsi
0x180001367  pop     rbp
0x180001368  pop     rbx
0x180001369  retn
0x18000136a  mov     rax, [rcx+10h]
0x18000136e  dec     rax
0x180001371  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001375  ja      short loc_1800013BF
0x180001377  call    cs:__imp_GetCurrentProcess
0x18000137d  mov     rdx, [rdi+10h]; hSourceHandle
0x180001381  lea     r9, [rsp+68h+hObject]; lpTargetHandle
0x180001386  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18000138e  mov     r8, rax; hTargetProcessHandle
0x180001391  mov     rcx, rax; hSourceProcessHandle
0x180001394  mov     [rsp+68h+bInheritHandle], ebp; bInheritHandle
0x180001398  mov     [rsp+68h+dwDesiredAccess], ebp; dwDesiredAccess
0x18000139c  call    cs:__imp_DuplicateHandle
0x1800013a2  test    eax, eax
0x1800013a4  jz      short loc_1800013E4
0x1800013a6  mov     rcx, [rsp+68h+hObject]; hFile
0x1800013ab  mov     rdx, rsi
0x1800013ae  call    FileToBstr
0x1800013b3  jmp     short loc_18000133C
0x1800013b5  call    cs:__imp_GetLastError
0x1800013bb  mov     edi, eax
0x1800013bd  jmp     short loc_180001347
0x1800013bf  mov     rcx, [rcx+18h]; lpWideCharStr
0x1800013c3  test    rcx, rcx
0x1800013c6  jz      short loc_1800013D9
0x1800013c8  lea     r8, [rsp+68h+hObject]
0x1800013cd  mov     edx, 80000000h; dwDesiredAccess
0x1800013d2  call    GetFileHandleFromPath
0x1800013d7  jmp     short loc_1800013A2
0x1800013d9  mov     ecx, 57h ; 'W'; dwErrCode
0x1800013de  call    cs:__imp_SetLastError
0x1800013e4  call    cs:__imp_GetLastError
0x1800013ea  mov     edi, eax
0x1800013ec  jmp     loc_180001347
0x1800013f1  mov     rcx, [rdx+18h]
0x1800013f5  test    rcx, rcx
0x1800013f8  jz      short loc_18000140A
0x1800013fa  mov     edx, [rdx+10h]
0x1800013fd  mov     r8, rsi
0x180001400  call    ConvertTextToUnicode
0x180001405  jmp     loc_18000133C
0x18000140a  mov     edi, 0Bh
0x18000140f  mov     ecx, edi; dwErrCode
0x180001411  call    cs:__imp_SetLastError
0x180001417  jmp     loc_18000135F
```
