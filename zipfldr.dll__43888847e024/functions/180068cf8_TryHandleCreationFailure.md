# TryHandleCreationFailure

- ea: `0x180068cf8`
- end: `0x180068e39`
- name: `TryHandleCreationFailure`
- size: `321`
- prototype: `__int64 __fastcall(__int64, __int64, char, _BYTE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180065834`
- `0x180066210`

## callees

- `0x180020cbc`
- `0x180034fbc`
- `0x180062684`
- `0x180068cf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068df7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180068dc6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180068dc6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180068d24`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180068d24`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180068dbe`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180068dbe`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180068da5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180068da5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall TryHandleCreationFailure(__int64 a1, __int64 a2, char a3, _BYTE *a4)
{
  signed int LastError; // edi
  __int64 v9; // rdx
  __int64 v10; // r8
  const WCHAR *v11; // rax
  DWORD FileAttributesW; // eax
  __int64 v13; // r8
  __int64 v14; // rdx
  int v15; // ebp
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  const WCHAR *v19; // rax
  int v20; // edx
  const WCHAR *v21; // rcx
  BOOL v22; // eax
  _BYTE v24[96]; // [rsp+28h] [rbp-60h] BYREF

  LastError = GetLastError();
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v9, v10);
  FileAttributesW = GetFileAttributesW(v11);
  v14 = FileAttributesW;
  if ( FileAttributesW == -1 || *a4 )
    goto LABEL_18;
  *a4 = 1;
  v15 = FileAttributesW & 0x10;
  if ( (FileAttributesW & 0x10) != 0 && (FileAttributesW & 0x400) == 0 )
  {
    v16 = std::wstring::wstring(v24, a2);
    LOBYTE(v17) = 5;
    v18 = 2150039564LL;
LABEL_22:
    ExtractResult::ExtractResult(a1, v18, v17, v16);
    return a1;
  }
  if ( (a3 & 1) == 0 )
  {
    v16 = std::wstring::wstring(v24, a2);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LOBYTE(v17) = 4;
LABEL_21:
    v18 = (unsigned int)LastError;
    goto LABEL_22;
  }
  if ( (FileAttributesW & 1) != 0
    && (v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, FileAttributesW, v13),
        !SetFileAttributesW(v19, v20 & 0xFFFFFFFE))
    || ((v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v14, v13), !v15)
      ? (v22 = DeleteFileW(v21))
      : (v22 = RemoveDirectoryW(v21)),
        !v22) )
  {
    LastError = GetLastError();
LABEL_18:
    v16 = std::wstring::wstring(v24, a2);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LOBYTE(v17) = 2;
    goto LABEL_21;
  }
  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_DWORD *)a1 = 0;
  *(_BYTE *)(a1 + 4) = 0;
  *(_OWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 7;
  *(_WORD *)(a1 + 8) = 0;
  return a1;
}

```

## disassembly

```asm
0x180068cf8  push    rbx
0x180068cfa  push    rbp
0x180068cfb  push    rsi
0x180068cfc  push    rdi
0x180068cfd  push    r14
0x180068cff  push    r15
0x180068d01  sub     rsp, 58h
0x180068d05  mov     r14, r9
0x180068d08  mov     r15b, r8b
0x180068d0b  mov     rsi, rdx
0x180068d0e  mov     rbx, rcx
0x180068d11  call    cs:__imp_GetLastError
0x180068d17  mov     rcx, rsi
0x180068d1a  mov     edi, eax
0x180068d1c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180068d21  mov     rcx, rax; lpFileName
0x180068d24  call    cs:__imp_GetFileAttributesW
0x180068d2a  mov     edx, eax
0x180068d2c  cmp     eax, 0FFFFFFFFh
0x180068d2f  jz      loc_180068DFF
0x180068d35  cmp     byte ptr [r14], 0
0x180068d39  jnz     loc_180068DFF
0x180068d3f  mov     ebp, eax
0x180068d41  mov     byte ptr [r14], 1
0x180068d45  and     ebp, 10h
0x180068d48  jz      short loc_180068D6A
0x180068d4a  bt      eax, 0Ah
0x180068d4e  jb      short loc_180068D6A
0x180068d50  mov     rdx, rsi
0x180068d53  lea     rcx, [rsp+88h+var_60]
0x180068d58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180068d5d  mov     r8b, 5
0x180068d60  mov     edx, 8027000Ch
0x180068d65  jmp     loc_180068E1E
0x180068d6a  test    r15b, 1
0x180068d6e  jnz     short loc_180068D92
0x180068d70  mov     rdx, rsi
0x180068d73  lea     rcx, [rsp+88h+var_60]
0x180068d78  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180068d7d  test    edi, edi
0x180068d7f  jle     short loc_180068D8A
0x180068d81  movzx   edi, di
0x180068d84  or      edi, 80070000h
0x180068d8a  mov     r8b, 4
0x180068d8d  jmp     loc_180068E1C
0x180068d92  test    dl, 1
0x180068d95  jz      short loc_180068DAF
0x180068d97  mov     rcx, rsi
0x180068d9a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180068d9f  mov     rcx, rax; lpFileName
0x180068da2  and     edx, 0FFFFFFFEh; dwFileAttributes
0x180068da5  call    cs:__imp_SetFileAttributesW
0x180068dab  test    eax, eax
0x180068dad  jz      short loc_180068DF7
0x180068daf  mov     rcx, rsi
0x180068db2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180068db7  mov     rcx, rax; lpFileName
0x180068dba  test    ebp, ebp
0x180068dbc  jz      short loc_180068DC6
0x180068dbe  call    cs:__imp_RemoveDirectoryW
0x180068dc4  jmp     short loc_180068DCC
0x180068dc6  call    cs:__imp_DeleteFileW
0x180068dcc  test    eax, eax
0x180068dce  jz      short loc_180068DF7
0x180068dd0  xor     eax, eax
0x180068dd2  xorps   xmm0, xmm0
0x180068dd5  movups  xmmword ptr [rbx], xmm0
0x180068dd8  movups  xmmword ptr [rbx+10h], xmm0
0x180068ddc  mov     [rbx], eax
0x180068dde  mov     [rbx+4], al
0x180068de1  movups  xmmword ptr [rbx+8], xmm0
0x180068de5  mov     [rbx+18h], rax
0x180068de9  mov     qword ptr [rbx+20h], 7
0x180068df1  mov     [rbx+8], ax
0x180068df5  jmp     short loc_180068E29
0x180068df7  call    cs:__imp_GetLastError
0x180068dfd  mov     edi, eax
0x180068dff  mov     rdx, rsi
0x180068e02  lea     rcx, [rsp+88h+var_60]
0x180068e07  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180068e0c  test    edi, edi
0x180068e0e  jle     short loc_180068E19
0x180068e10  movzx   edi, di
0x180068e13  or      edi, 80070000h
0x180068e19  mov     r8b, 2
0x180068e1c  mov     edx, edi
0x180068e1e  mov     r9, rax
0x180068e21  mov     rcx, rbx
0x180068e24  call    ??0ExtractResult@@QEAA@JW4ExtractFailureReason@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractResult::ExtractResult(long,ExtractFailureReason,std::wstring)
0x180068e29  mov     rax, rbx
0x180068e2c  add     rsp, 58h
0x180068e30  pop     r15
0x180068e32  pop     r14
0x180068e34  pop     rdi
0x180068e35  pop     rsi
0x180068e36  pop     rbp
0x180068e37  pop     rbx
0x180068e38  retn
```
