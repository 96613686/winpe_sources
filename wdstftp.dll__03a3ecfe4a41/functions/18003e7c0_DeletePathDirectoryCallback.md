# DeletePathDirectoryCallback

- ea: `0x18003e7c0`
- end: `0x18003ead3`
- name: `DeletePathDirectoryCallback`
- size: `787`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callees

- `0x18003d150`
- `0x18003d5cc`
- `0x18003dbcc`
- `0x18003de88`
- `0x18003e0e4`
- `0x18003e138`
- `0x18003e7c0`
- `0x180040a18`
- `0x180060e70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18003ea01`
- `KERNEL32!HeapFree` at `0x18003ea01`
- `KERNEL32!GetLastError` at `0x18003e82f`
- `KERNEL32!GetLastError` at `0x18003e93b`
- `KERNEL32!GetLastError` at `0x18003e959`
- `KERNEL32!GetLastError` at `0x18003eaaa`
- `KERNEL32!GetLastError` at `0x18003e82f`
- `KERNEL32!GetLastError` at `0x18003e93b`
- `KERNEL32!GetLastError` at `0x18003e959`
- `KERNEL32!GetLastError` at `0x18003eaaa`
- `KERNEL32!CloseHandle` at `0x18003e99a`
- `KERNEL32!CloseHandle` at `0x18003e99a`
- `KERNEL32!CreateFileW` at `0x18003e925`
- `KERNEL32!CreateFileW` at `0x18003e925`
- `KERNEL32!SetLastError` at `0x18003e7fb`
- `KERNEL32!SetLastError` at `0x18003e848`
- `KERNEL32!SetLastError` at `0x18003e8b0`
- `KERNEL32!SetLastError` at `0x18003ea16`
- `KERNEL32!SetLastError` at `0x18003ea6c`
- `KERNEL32!SetLastError` at `0x18003e7fb`
- `KERNEL32!SetLastError` at `0x18003e848`
- `KERNEL32!SetLastError` at `0x18003e8b0`
- `KERNEL32!SetLastError` at `0x18003ea16`
- `KERNEL32!SetLastError` at `0x18003ea6c`
- `KERNEL32!GetProcessHeap` at `0x18003e9ed`
- `KERNEL32!GetProcessHeap` at `0x18003e9ed`

## string_xrefs

- `0x18003e9cb`: `DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]`

## pseudocode

```c
__int64 __fastcall DeletePathDirectoryCallback(__int64 a1, __int64 (__fastcall *a2)(DWORD *, __int64), __int64 a3)
{
  unsigned int v4; // r15d
  __int64 (__fastcall *v5)(DWORD *, __int64); // r12
  __int64 (__fastcall *v8)(_QWORD, _QWORD); // rax
  __int64 v9; // rcx
  int v10; // esi
  BOOL v11; // edi
  int v12; // eax
  int v13; // eax
  unsigned __int16 *v14; // rcx
  int v15; // edx
  int v16; // eax
  WCHAR *v17; // r15
  int v18; // r13d
  WCHAR *v19; // r12
  HANDLE FileW; // rax
  signed int LastError; // eax
  signed int v22; // ecx
  signed int v23; // eax
  int v24; // r15d
  HANDLE ProcessHeap; // rax
  int v26; // eax
  unsigned __int16 *v27; // rcx
  int v28; // edx
  int v29; // eax
  WCHAR *v30; // [rsp+40h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-8h]
  int v33; // [rsp+A0h] [rbp+50h] BYREF
  int v34; // [rsp+A8h] [rbp+58h]

  v34 = 1;
  v4 = 1;
  v5 = a2;
  if ( !a3 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v8 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(a3 + 16);
  if ( v8 )
  {
    v34 = v8(*(_QWORD *)(a1 + 40), *(_QWORD *)(a3 + 24));
    v4 = v34;
    if ( !v34 )
    {
      if ( !GetLastError() )
        SetLastError(0x4C7u);
LABEL_50:
      ++*(_DWORD *)(a3 + 4);
      if ( !*(_DWORD *)a3 )
        *(_DWORD *)a3 = GetLastError();
      return v4;
    }
  }
  v9 = *(_QWORD *)(a1 + 40);
  v33 = 0;
  v10 = 1;
  v11 = 0;
  if ( !(unsigned int)ReparsePointExists(v9, &v33) )
    goto LABEL_19;
  if ( !v33 )
    goto LABEL_19;
  v10 = 0;
  v12 = *(_DWORD *)(a3 + 8) & 2;
  v33 = 0;
  if ( !(_BYTE)v12 )
  {
    v13 = ShouldEnumerateReparsePoint(*(_QWORD *)(a1 + 40), &v33);
    v10 = v33;
    if ( v13 )
    {
      if ( v33 )
        goto LABEL_19;
    }
  }
  v14 = *(unsigned __int16 **)(a1 + 40);
  if ( v14 )
  {
    v15 = *(_DWORD *)(a3 + 12) & 0x21;
    v16 = v15 ? DeleteFileEx2(v14, v15) : WdsRemoveDirectory(v14);
    v11 = v16;
  }
  else
  {
    SetLastError(0x57u);
    v11 = 0;
  }
  if ( v10 )
  {
LABEL_19:
    if ( (*(_BYTE *)(a3 + 12) & 0x20) != 0 )
    {
      v17 = *(WCHAR **)(a1 + 40);
      v18 = 0;
      v19 = 0;
      v33 = 0;
      v30 = 0;
      if ( v17 )
      {
        FileW = CreateFileW(v17, 0, 7u, 0, 3u, 0x2200000u, 0);
        hObject = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          v22 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v22 = LastError;
          if ( v22 >= 0 )
          {
            v24 = -2147467259;
          }
          else
          {
            v23 = GetLastError();
            v24 = (unsigned __int16)v23 | 0x80070000;
            if ( v23 <= 0 )
              v24 = v23;
          }
        }
        else
        {
          v24 = ValidateRedirectedHandle((char *)FileW, v17, &v33, &v30);
          CloseHandle(hObject);
          v18 = v33;
          v19 = v30;
        }
      }
      else
      {
        v24 = -2147024809;
      }
      if ( v24 < 0 )
        v18 = 1;
      if ( !v18 )
      {
        LibLog(
          &g_WdsLibLog,
          50331648,
          L"DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]",
          *(_QWORD *)(a1 + 40),
          v19);
        if ( v19 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v19);
        }
        v10 = 0;
        v11 = 0;
        SetLastError(0x2A9u);
      }
      v5 = a2;
    }
    if ( v10 )
    {
      v26 = EnumeratePathEx(
              *(LPCWSTR *)(a1 + 40),
              (__int64 (__fastcall *)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64))DeletePathDirectoryCallback,
              v5,
              a3,
              *(_DWORD *)(a3 + 8));
      v11 = v26 == 1;
      v4 = v11;
      if ( v26 == 1 )
      {
        v27 = *(unsigned __int16 **)(a1 + 40);
        if ( v27 )
        {
          v28 = *(_DWORD *)(a3 + 12) & 0x21;
          if ( v28 )
            v29 = DeleteFileEx2(v27, v28);
          else
            v29 = WdsRemoveDirectory(v27);
          if ( v29 == 1 && v11 )
            return v4;
        }
        else
        {
          SetLastError(0x57u);
        }
        v11 = 0;
      }
    }
    else
    {
      v4 = v34;
    }
  }
  if ( !v11 )
    goto LABEL_50;
  return v4;
}

```

## disassembly

```asm
0x18003e7c0  mov     [rsp-38h+arg_0], rbx
0x18003e7c5  mov     [rsp-38h+arg_8], rdx
0x18003e7ca  push    rbp
0x18003e7cb  push    rsi
0x18003e7cc  push    rdi
0x18003e7cd  push    r12
0x18003e7cf  push    r13
0x18003e7d1  push    r14
0x18003e7d3  push    r15
0x18003e7d5  mov     rbp, rsp
0x18003e7d8  sub     rsp, 50h
0x18003e7dc  mov     r13d, 1
0x18003e7e2  mov     rbx, r8
0x18003e7e5  mov     [rbp+arg_18], r13d
0x18003e7e9  mov     r15d, r13d
0x18003e7ec  mov     r12, rdx
0x18003e7ef  mov     r14, rcx
0x18003e7f2  test    r8, r8
0x18003e7f5  jnz     short loc_18003E80E
0x18003e7f7  lea     ecx, [r8+57h]; dwErrCode
0x18003e7fb  call    cs:__imp_SetLastError
0x18003e802  nop     dword ptr [rax+rax+00h]
0x18003e807  xor     eax, eax
0x18003e809  jmp     loc_18003EABB
0x18003e80e  mov     rax, [r8+10h]
0x18003e812  test    rax, rax
0x18003e815  jz      short loc_18003E859
0x18003e817  mov     rdx, [r8+18h]
0x18003e81b  mov     rcx, [rcx+28h]
0x18003e81f  call    cs:__guard_dispatch_icall_fptr
0x18003e825  mov     [rbp+arg_18], eax
0x18003e828  mov     r15d, eax
0x18003e82b  test    eax, eax
0x18003e82d  jnz     short loc_18003E859
0x18003e82f  call    cs:__imp_GetLastError
0x18003e836  nop     dword ptr [rax+rax+00h]
0x18003e83b  test    eax, eax
0x18003e83d  jnz     loc_18003EAA1
0x18003e843  mov     ecx, 4C7h; dwErrCode
0x18003e848  call    cs:__imp_SetLastError
0x18003e84f  nop     dword ptr [rax+rax+00h]
0x18003e854  jmp     loc_18003EAA1
0x18003e859  mov     rcx, [r14+28h]
0x18003e85d  lea     rdx, [rbp+arg_10]
0x18003e861  and     [rbp+arg_10], 0
0x18003e865  mov     esi, r13d
0x18003e868  xor     edi, edi
0x18003e86a  call    ReparsePointExists
0x18003e86f  test    eax, eax
0x18003e871  jz      short loc_18003E8DB
0x18003e873  cmp     [rbp+arg_10], edi
0x18003e876  jz      short loc_18003E8DB
0x18003e878  mov     eax, [rbx+8]
0x18003e87b  xor     esi, esi
0x18003e87d  and     eax, 2
0x18003e880  mov     [rbp+arg_10], esi
0x18003e883  test    al, al
0x18003e885  jnz     short loc_18003E89F
0x18003e887  mov     rcx, [r14+28h]
0x18003e88b  lea     rdx, [rbp+arg_10]
0x18003e88f  call    ShouldEnumerateReparsePoint
0x18003e894  mov     esi, [rbp+arg_10]
0x18003e897  test    eax, eax
0x18003e899  jz      short loc_18003E89F
0x18003e89b  test    esi, esi
0x18003e89d  jnz     short loc_18003E8DB
0x18003e89f  mov     rcx, [r14+28h]
0x18003e8a3  mov     edx, [rbx+0Ch]
0x18003e8a6  test    rcx, rcx
0x18003e8a9  jnz     short loc_18003E8C0
0x18003e8ab  mov     ecx, 57h ; 'W'; dwErrCode
0x18003e8b0  call    cs:__imp_SetLastError
0x18003e8b7  nop     dword ptr [rax+rax+00h]
0x18003e8bc  xor     edi, edi
0x18003e8be  jmp     short loc_18003E8D3
0x18003e8c0  and     edx, 21h
0x18003e8c3  jnz     short loc_18003E8CC
0x18003e8c5  call    WdsRemoveDirectory
0x18003e8ca  jmp     short loc_18003E8D1
0x18003e8cc  call    DeleteFileEx2
0x18003e8d1  mov     edi, eax
0x18003e8d3  test    esi, esi
0x18003e8d5  jz      loc_18003EA9D
0x18003e8db  mov     eax, [rbx+0Ch]
0x18003e8de  and     eax, 20h
0x18003e8e1  test    al, al
0x18003e8e3  jz      loc_18003EA2C
0x18003e8e9  mov     r15, [r14+28h]
0x18003e8ed  xor     r13d, r13d
0x18003e8f0  xor     r12d, r12d
0x18003e8f3  mov     [rbp+arg_10], r13d
0x18003e8f7  mov     [rbp+var_10], r12
0x18003e8fb  test    r15, r15
0x18003e8fe  jz      loc_18003E9B0
0x18003e904  and     [rsp+50h+var_20], r12
0x18003e909  lea     r8d, [r13+7]; dwShareMode
0x18003e90d  mov     [rsp+50h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003e915  xor     r9d, r9d; lpSecurityAttributes
0x18003e918  xor     edx, edx; dwDesiredAccess
0x18003e91a  mov     [rsp+50h+dwCreationDisposition], 3; dwCreationDisposition
0x18003e922  mov     rcx, r15; lpFileName
0x18003e925  call    cs:__imp_CreateFileW
0x18003e92c  nop     dword ptr [rax+rax+00h]
0x18003e931  mov     [rbp+hObject], rax
0x18003e935  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003e939  jnz     short loc_18003E980
0x18003e93b  call    cs:__imp_GetLastError
0x18003e942  nop     dword ptr [rax+rax+00h]
0x18003e947  movzx   ecx, ax
0x18003e94a  or      ecx, 80070000h
0x18003e950  test    eax, eax
0x18003e952  cmovle  ecx, eax
0x18003e955  test    ecx, ecx
0x18003e957  jns     short loc_18003E978
0x18003e959  call    cs:__imp_GetLastError
0x18003e960  nop     dword ptr [rax+rax+00h]
0x18003e965  movzx   r15d, ax
0x18003e969  or      r15d, 80070000h
0x18003e970  test    eax, eax
0x18003e972  cmovle  r15d, eax
0x18003e976  jmp     short loc_18003E9B6
0x18003e978  mov     r15d, 80004005h
0x18003e97e  jmp     short loc_18003E9B6
0x18003e980  lea     r9, [rbp+var_10]
0x18003e984  mov     rdx, r15; String2
0x18003e987  lea     r8, [rbp+arg_10]
0x18003e98b  mov     rcx, rax; hFile
0x18003e98e  call    ValidateRedirectedHandle
0x18003e993  mov     rcx, [rbp+hObject]; hObject
0x18003e997  mov     r15d, eax
0x18003e99a  call    cs:__imp_CloseHandle
0x18003e9a1  nop     dword ptr [rax+rax+00h]
0x18003e9a6  mov     r13d, [rbp+arg_10]
0x18003e9aa  mov     r12, [rbp+var_10]
0x18003e9ae  jmp     short loc_18003E9B6
0x18003e9b0  mov     r15d, 80070057h
0x18003e9b6  test    r15d, r15d
0x18003e9b9  mov     eax, 1
0x18003e9be  cmovs   r13d, eax
0x18003e9c2  test    r13d, r13d
0x18003e9c5  jnz     short loc_18003EA22
0x18003e9c7  mov     r9, [r14+28h]
0x18003e9cb  lea     r8, aDeletepathdire; "DeletePathDirectoryCallback: Spoofing d"...
0x18003e9d2  mov     edx, 3000000h
0x18003e9d7  mov     qword ptr [rsp+50h+dwCreationDisposition], r12
0x18003e9dc  lea     rcx, g_WdsLibLog
0x18003e9e3  call    LibLog
0x18003e9e8  test    r12, r12
0x18003e9eb  jz      short loc_18003EA0D
0x18003e9ed  call    cs:__imp_GetProcessHeap
0x18003e9f4  nop     dword ptr [rax+rax+00h]
0x18003e9f9  mov     r8, r12; lpMem
0x18003e9fc  xor     edx, edx; dwFlags
0x18003e9fe  mov     rcx, rax; hHeap
0x18003ea01  call    cs:__imp_HeapFree
0x18003ea08  nop     dword ptr [rax+rax+00h]
0x18003ea0d  xor     esi, esi
0x18003ea0f  xor     edi, edi
0x18003ea11  mov     ecx, 2A9h; dwErrCode
0x18003ea16  call    cs:__imp_SetLastError
0x18003ea1d  nop     dword ptr [rax+rax+00h]
0x18003ea22  mov     r12, [rbp+arg_8]
0x18003ea26  mov     r13d, 1
0x18003ea2c  test    esi, esi
0x18003ea2e  jz      short loc_18003EA99
0x18003ea30  mov     eax, [rbx+8]
0x18003ea33  lea     rdx, DeletePathDirectoryCallback
0x18003ea3a  mov     rcx, [r14+28h]; lpFileName
0x18003ea3e  mov     r9, rbx
0x18003ea41  mov     r8, r12
0x18003ea44  mov     [rsp+50h+dwCreationDisposition], eax; int
0x18003ea48  call    EnumeratePathEx
0x18003ea4d  xor     edi, edi
0x18003ea4f  cmp     eax, r13d
0x18003ea52  setz    dil
0x18003ea56  mov     r15d, edi
0x18003ea59  jnz     short loc_18003EA9D
0x18003ea5b  mov     rcx, [r14+28h]
0x18003ea5f  mov     edx, [rbx+0Ch]
0x18003ea62  test    rcx, rcx
0x18003ea65  jnz     short loc_18003EA7A
0x18003ea67  mov     ecx, 57h ; 'W'; dwErrCode
0x18003ea6c  call    cs:__imp_SetLastError
0x18003ea73  nop     dword ptr [rax+rax+00h]
0x18003ea78  jmp     short loc_18003EA95
0x18003ea7a  and     edx, 21h
0x18003ea7d  jnz     short loc_18003EA86
0x18003ea7f  call    WdsRemoveDirectory
0x18003ea84  jmp     short loc_18003EA8B
0x18003ea86  call    DeleteFileEx2
0x18003ea8b  cmp     eax, r13d
0x18003ea8e  jnz     short loc_18003EA95
0x18003ea90  cmp     edi, r13d
0x18003ea93  jz      short loc_18003EAB8
0x18003ea95  xor     edi, edi
0x18003ea97  jmp     short loc_18003EA9D
0x18003ea99  mov     r15d, [rbp+arg_18]
0x18003ea9d  test    edi, edi
0x18003ea9f  jnz     short loc_18003EAB8
0x18003eaa1  add     [rbx+4], r13d
0x18003eaa5  cmp     dword ptr [rbx], 0
0x18003eaa8  jnz     short loc_18003EAB8
0x18003eaaa  call    cs:__imp_GetLastError
0x18003eab1  nop     dword ptr [rax+rax+00h]
0x18003eab6  mov     [rbx], eax
0x18003eab8  mov     eax, r15d
0x18003eabb  mov     rbx, [rsp+50h+arg_0]
0x18003eac3  add     rsp, 50h
0x18003eac7  pop     r15
0x18003eac9  pop     r14
0x18003eacb  pop     r13
0x18003eacd  pop     r12
0x18003eacf  pop     rdi
0x18003ead0  pop     rsi
0x18003ead1  pop     rbp
0x18003ead2  retn
```
