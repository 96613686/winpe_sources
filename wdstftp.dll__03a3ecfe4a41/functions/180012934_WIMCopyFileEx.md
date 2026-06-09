# WIMCopyFileEx

- ea: `0x180012934`
- end: `0x180012c15`
- name: `WIMCopyFileEx`
- size: `737`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, int, __int64, __int64, union _LARGE_INTEGER FileSize, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180013690`
- `0x180022010`

## callees

- `0x18000d938`
- `0x180011cc4`
- `0x180012934`
- `0x180014110`
- `0x1800143d8`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012b79`
- `KERNEL32!GetLastError` at `0x180012b79`
- `KERNEL32!CloseHandle` at `0x180012baa`
- `KERNEL32!CloseHandle` at `0x180012bd8`
- `KERNEL32!CloseHandle` at `0x180012baa`
- `KERNEL32!CloseHandle` at `0x180012bd8`
- `KERNEL32!CreateFileW` at `0x1800129ec`
- `KERNEL32!CreateFileW` at `0x1800129ec`
- `KERNEL32!SetLastError` at `0x180012bec`
- `KERNEL32!SetLastError` at `0x180012bec`
- `KERNEL32!GetFileSizeEx` at `0x180012a23`
- `KERNEL32!GetFileSizeEx` at `0x180012a23`

## pseudocode

```c
__int64 __fastcall WIMCopyFileEx(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 a6,
        __int64 a7,
        int a8,
        __int64 a9,
        __int64 a10,
        union _LARGE_INTEGER FileSize,
        __int64 a12,
        int a13,
        _QWORD *a14)
{
  DWORD LastError; // r12d
  __int64 FileW; // rsi
  __int64 *v18; // r14
  __int64 v19; // rdi
  unsigned int v20; // ebx
  unsigned int DestinationFile; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int dwCreationDisposition; // [rsp+28h] [rbp-99h]
  _BYTE v26[16]; // [rsp+80h] [rbp-41h] BYREF
  __int64 v27; // [rsp+90h] [rbp-31h]
  __int64 v28; // [rsp+98h] [rbp-29h]
  _BYTE v29[16]; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v30; // [rsp+B0h] [rbp-11h]
  __int64 v31; // [rsp+B8h] [rbp-9h]
  __int64 v32; // [rsp+110h] [rbp+4Fh] BYREF
  __int64 v33; // [rsp+118h] [rbp+57h] BYREF
  int v34; // [rsp+120h] [rbp+5Fh] BYREF

  v33 = a3;
  a7 = 0;
  v34 = 0;
  v32 = 0;
  LastError = 0;
  memset_0(v29, 0, 0x20u);
  memset_0(v26, 0, 0x20u);
  if ( a14 )
    *a14 = 0;
  if ( a2 )
    FileW = *a2;
  else
    FileW = -1;
  v18 = a5;
  if ( a5 )
    v19 = *a5;
  else
    v19 = -1;
  v33 = v19;
  if ( FileW != -1 || (FileW = (__int64)CreateFileW(0, 0x80000000, 7u, 0, 3u, 0, 0), FileW != -1) )
  {
    if ( FileSize.QuadPart == -1 )
    {
      if ( g_useFileIOCallbacks )
        WIMGetFileSizeEx((HANDLE)FileW, &FileSize);
      else
        GetFileSizeEx((HANDLE)FileW, &FileSize);
    }
  }
  v20 = 1;
  if ( v19 == -1 )
  {
    DestinationFile = CreateDestinationFile(a1, a6, 0, a8, dwCreationDisposition, (__int64)&FileSize, (__int64)&v33);
    v19 = v33;
    v20 = DestinationFile;
    if ( !DestinationFile )
    {
LABEL_34:
      LastError = GetLastError();
      if ( !v20 )
        goto LABEL_37;
      goto LABEL_35;
    }
  }
  if ( a1 )
  {
    v22 = *(_QWORD *)(a1 + 384);
    v23 = *(_QWORD *)(a1 + 392);
    if ( v22 && v23 )
      goto LABEL_23;
  }
  else
  {
    v23 = a7;
    v22 = 0;
  }
  v20 = 0;
LABEL_23:
  if ( !v20 )
    goto LABEL_34;
  v30 = a9;
  v27 = a10;
  v31 = v22;
  v28 = v23;
  if ( !(unsigned int)GetImageBuffers(a1, (unsigned int)&v32, (unsigned int)&v34, 0, 0) || !v32 || !v34 )
    v20 = 0;
  if ( !v20 )
    goto LABEL_34;
  v20 = 0;
  if ( !v32
    || FileW == -1
    || v19 == -1
    || !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))CopyFileData)(
                        a1,
                        FileW,
                        v29,
                        v19,
                        v26,
                        (union _LARGE_INTEGER)FileSize.QuadPart,
                        v32,
                        v34,
                        0,
                        0,
                        a12,
                        a13,
                        a14) )
  {
    goto LABEL_34;
  }
  v20 = 1;
LABEL_35:
  if ( a2 )
  {
    *a2 = FileW;
    goto LABEL_41;
  }
LABEL_37:
  if ( FileW != -1 && (!a2 || *a2 == -1) )
    CloseHandle((HANDLE)FileW);
LABEL_41:
  if ( v20 && v18 )
  {
    *v18 = v19;
  }
  else if ( v19 != -1 && (!v18 || *v18 == -1) )
  {
    CloseHandle((HANDLE)v19);
  }
  if ( LastError )
    SetLastError(LastError);
  return v20;
}

```

## disassembly

```asm
0x180012934  mov     rax, rsp
0x180012937  mov     [rax+8], rbx
0x18001293b  mov     [rax+20h], r9d
0x18001293f  mov     [rax+18h], r8
0x180012943  push    rbp
0x180012944  push    rsi
0x180012945  push    rdi
0x180012946  push    r12
0x180012948  push    r13
0x18001294a  push    r14
0x18001294c  push    r15
0x18001294e  lea     rbp, [rax-3Fh]
0x180012952  sub     rsp, 0C0h
0x180012959  xor     edi, edi
0x18001295b  mov     r15, rdx
0x18001295e  mov     r13, rcx
0x180012961  mov     [rbp+37h+var_80], rdi
0x180012965  xor     edx, edx; Val
0x180012967  mov     [rbp+37h+arg_30], rdi
0x18001296b  lea     rcx, [rbp+37h+var_58]; void *
0x18001296f  mov     [rbp+37h+arg_18], edi
0x180012972  lea     ebx, [rdi+20h]
0x180012975  mov     [rbp+37h+arg_8], rdi
0x180012979  mov     r8d, ebx; Size
0x18001297c  mov     r12d, edi
0x18001297f  call    memset_0
0x180012984  mov     r8d, ebx; Size
0x180012987  lea     rcx, [rbp+37h+var_78]; void *
0x18001298b  xor     edx, edx; Val
0x18001298d  call    memset_0
0x180012992  mov     rax, [rbp+37h+arg_68]
0x180012999  test    rax, rax
0x18001299c  jz      short loc_1800129A1
0x18001299e  mov     [rax], rdi
0x1800129a1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800129a5  test    r15, r15
0x1800129a8  jz      short loc_1800129AF
0x1800129aa  mov     rsi, [r15]
0x1800129ad  jmp     short loc_1800129B2
0x1800129af  mov     rsi, rbx
0x1800129b2  mov     r14, [rbp+37h+arg_20]
0x1800129b6  test    r14, r14
0x1800129b9  jz      short loc_1800129C0
0x1800129bb  mov     rdi, [r14]
0x1800129be  jmp     short loc_1800129C3
0x1800129c0  mov     rdi, rbx
0x1800129c3  mov     [rbp+37h+arg_10], rdi
0x1800129c7  cmp     rsi, rbx
0x1800129ca  jnz     short loc_180012A00
0x1800129cc  and     qword ptr [rsp+0F0h+var_C0], r12
0x1800129d1  xor     r9d, r9d; lpSecurityAttributes
0x1800129d4  and     dword ptr [rsp+0F0h+var_C8], r12d
0x1800129d9  mov     edx, 80000000h; dwDesiredAccess
0x1800129de  xor     ecx, ecx; lpFileName
0x1800129e0  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800129e8  lea     r8d, [r9+7]; dwShareMode
0x1800129ec  call    cs:__imp_CreateFileW
0x1800129f3  nop     dword ptr [rax+rax+00h]
0x1800129f8  mov     rsi, rax
0x1800129fb  cmp     rax, rbx
0x1800129fe  jz      short loc_180012A2F
0x180012a00  cmp     qword ptr [rbp+37h+FileSize], rbx
0x180012a07  jnz     short loc_180012A2F
0x180012a09  cmp     cs:g_useFileIOCallbacks, r12d
0x180012a10  lea     rdx, [rbp+37h+FileSize]; lpFileSize
0x180012a17  mov     rcx, rsi; hFile
0x180012a1a  jz      short loc_180012A23
0x180012a1c  call    WIMGetFileSizeEx
0x180012a21  jmp     short loc_180012A2F
0x180012a23  call    cs:__imp_GetFileSizeEx
0x180012a2a  nop     dword ptr [rax+rax+00h]
0x180012a2f  mov     ebx, 1
0x180012a34  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180012a38  jnz     short loc_180012A70
0x180012a3a  mov     r9d, [rbp+37h+arg_38]
0x180012a3e  lea     rax, [rbp+37h+arg_10]
0x180012a42  mov     rdx, [rbp+37h+arg_28]
0x180012a46  xor     r8d, r8d
0x180012a49  mov     qword ptr [rsp+0F0h+var_C0], rax
0x180012a4e  mov     rcx, r13
0x180012a51  lea     rax, [rbp+37h+FileSize]
0x180012a58  mov     [rsp+0F0h+var_C8], rax
0x180012a5d  call    CreateDestinationFile
0x180012a62  mov     rdi, [rbp+37h+arg_10]
0x180012a66  mov     ebx, eax
0x180012a68  test    eax, eax
0x180012a6a  jz      loc_180012B79
0x180012a70  test    r13, r13
0x180012a73  jz      short loc_180012A8F
0x180012a75  mov     rdx, [r13+180h]
0x180012a7c  mov     rcx, [r13+188h]
0x180012a83  test    rdx, rdx
0x180012a86  jz      short loc_180012A97
0x180012a88  test    rcx, rcx
0x180012a8b  jnz     short loc_180012A99
0x180012a8d  jmp     short loc_180012A97
0x180012a8f  mov     rcx, [rbp+37h+arg_30]
0x180012a93  mov     rdx, [rbp+37h+var_80]
0x180012a97  xor     ebx, ebx
0x180012a99  test    ebx, ebx
0x180012a9b  jz      loc_180012B79
0x180012aa1  mov     eax, dword ptr [rbp+37h+arg_40]
0x180012aa7  lea     r8, [rbp+37h+arg_18]
0x180012aab  and     qword ptr [rsp+0F0h+dwCreationDisposition], r12
0x180012ab0  xor     r9d, r9d
0x180012ab3  mov     dword ptr [rbp+37h+var_48], eax
0x180012ab6  mov     eax, dword ptr [rbp+37h+arg_40+4]
0x180012abc  mov     dword ptr [rbp+37h+var_48+4], eax
0x180012abf  mov     eax, dword ptr [rbp+37h+arg_48]
0x180012ac5  mov     dword ptr [rbp+37h+var_68], eax
0x180012ac8  mov     eax, dword ptr [rbp+37h+arg_48+4]
0x180012ace  mov     [rbp+37h+var_40], rdx
0x180012ad2  lea     rdx, [rbp+37h+arg_8]
0x180012ad6  mov     [rbp+37h+var_60], rcx
0x180012ada  mov     rcx, r13
0x180012add  mov     dword ptr [rbp+37h+var_68+4], eax
0x180012ae0  call    GetImageBuffers
0x180012ae5  mov     edx, [rbp+37h+arg_18]
0x180012ae8  mov     rcx, [rbp+37h+arg_8]
0x180012aec  test    eax, eax
0x180012aee  jz      short loc_180012AF9
0x180012af0  test    rcx, rcx
0x180012af3  jz      short loc_180012AF9
0x180012af5  test    edx, edx
0x180012af7  jnz     short loc_180012AFB
0x180012af9  xor     ebx, ebx
0x180012afb  test    ebx, ebx
0x180012afd  jz      short loc_180012B79
0x180012aff  xor     ebx, ebx
0x180012b01  test    rcx, rcx
0x180012b04  jz      short loc_180012B79
0x180012b06  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180012b0a  jz      short loc_180012B79
0x180012b0c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180012b10  jz      short loc_180012B79
0x180012b12  mov     rax, [rbp+37h+arg_68]
0x180012b19  lea     r8, [rbp+37h+var_58]
0x180012b1d  mov     [rsp+60h], rax
0x180012b22  mov     r9, rdi
0x180012b25  mov     eax, [rbp+37h+arg_60]
0x180012b2b  mov     dword ptr [rsp+0F0h+var_98], eax
0x180012b2f  mov     rax, [rbp+37h+arg_58]
0x180012b36  mov     qword ptr [rsp+0F0h+var_A0], rax
0x180012b3b  and     [rsp+0F0h+var_A8], rbx
0x180012b40  and     [rsp+0F0h+var_B0], rbx
0x180012b45  mov     rax, qword ptr [rbp+37h+FileSize]
0x180012b4c  mov     dword ptr [rsp+0F0h+var_B8], edx
0x180012b50  mov     rdx, rsi
0x180012b53  mov     qword ptr [rsp+0F0h+var_C0], rcx
0x180012b58  mov     rcx, r13
0x180012b5b  mov     [rsp+0F0h+var_C8], rax
0x180012b60  lea     rax, [rbp+37h+var_78]
0x180012b64  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax
0x180012b69  call    CopyFileData
0x180012b6e  test    eax, eax
0x180012b70  jz      short loc_180012B79
0x180012b72  mov     ebx, 1
0x180012b77  jmp     short loc_180012B8C
0x180012b79  call    cs:__imp_GetLastError
0x180012b80  nop     dword ptr [rax+rax+00h]
0x180012b85  mov     r12d, eax
0x180012b88  test    ebx, ebx
0x180012b8a  jz      short loc_180012B96
0x180012b8c  test    r15, r15
0x180012b8f  jz      short loc_180012B96
0x180012b91  mov     [r15], rsi
0x180012b94  jmp     short loc_180012BB6
0x180012b96  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180012b9a  jz      short loc_180012BB6
0x180012b9c  test    r15, r15
0x180012b9f  jz      short loc_180012BA7
0x180012ba1  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x180012ba5  jnz     short loc_180012BB6
0x180012ba7  mov     rcx, rsi; hObject
0x180012baa  call    cs:__imp_CloseHandle
0x180012bb1  nop     dword ptr [rax+rax+00h]
0x180012bb6  test    ebx, ebx
0x180012bb8  jz      short loc_180012BC4
0x180012bba  test    r14, r14
0x180012bbd  jz      short loc_180012BC4
0x180012bbf  mov     [r14], rdi
0x180012bc2  jmp     short loc_180012BE4
0x180012bc4  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180012bc8  jz      short loc_180012BE4
0x180012bca  test    r14, r14
0x180012bcd  jz      short loc_180012BD5
0x180012bcf  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180012bd3  jnz     short loc_180012BE4
0x180012bd5  mov     rcx, rdi; hObject
0x180012bd8  call    cs:__imp_CloseHandle
0x180012bdf  nop     dword ptr [rax+rax+00h]
0x180012be4  test    r12d, r12d
0x180012be7  jz      short loc_180012BF8
0x180012be9  mov     ecx, r12d; dwErrCode
0x180012bec  call    cs:__imp_SetLastError
0x180012bf3  nop     dword ptr [rax+rax+00h]
0x180012bf8  mov     eax, ebx
0x180012bfa  mov     rbx, [rsp+0F0h+arg_0]
0x180012c02  add     rsp, 0C0h
0x180012c09  pop     r15
0x180012c0b  pop     r14
0x180012c0d  pop     r13
0x180012c0f  pop     r12
0x180012c11  pop     rdi
0x180012c12  pop     rsi
0x180012c13  pop     rbp
0x180012c14  retn
```
