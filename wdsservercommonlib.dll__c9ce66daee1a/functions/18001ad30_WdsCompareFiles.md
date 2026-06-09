# WdsCompareFiles

- ea: `0x18001ad30`
- end: `0x18001b00d`
- name: `WdsCompareFiles`
- size: `733`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000179c`
- `0x18001a28c`
- `0x18001ad30`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ada6`
- `KERNEL32!GetLastError` at `0x18001adfc`
- `KERNEL32!GetLastError` at `0x18001ae2c`
- `KERNEL32!GetLastError` at `0x18001ae5c`
- `KERNEL32!GetLastError` at `0x18001af65`
- `KERNEL32!GetLastError` at `0x18001af7b`
- `KERNEL32!GetLastError` at `0x18001ada6`
- `KERNEL32!GetLastError` at `0x18001adfc`
- `KERNEL32!GetLastError` at `0x18001ae2c`
- `KERNEL32!GetLastError` at `0x18001ae5c`
- `KERNEL32!GetLastError` at `0x18001af65`
- `KERNEL32!GetLastError` at `0x18001af7b`
- `KERNEL32!CloseHandle` at `0x18001afb1`
- `KERNEL32!CloseHandle` at `0x18001afc6`
- `KERNEL32!CloseHandle` at `0x18001afb1`
- `KERNEL32!CloseHandle` at `0x18001afc6`
- `KERNEL32!GetFileSizeEx` at `0x18001ae1c`
- `KERNEL32!GetFileSizeEx` at `0x18001ae4c`
- `KERNEL32!GetFileSizeEx` at `0x18001ae1c`
- `KERNEL32!GetFileSizeEx` at `0x18001ae4c`
- `KERNEL32!CreateFileW` at `0x18001ad8d`
- `KERNEL32!CreateFileW` at `0x18001ade7`
- `KERNEL32!CreateFileW` at `0x18001ad8d`
- `KERNEL32!CreateFileW` at `0x18001ade7`
- `KERNEL32!ReadFile` at `0x18001aef3`
- `KERNEL32!ReadFile` at `0x18001af15`
- `KERNEL32!ReadFile` at `0x18001aef3`
- `KERNEL32!ReadFile` at `0x18001af15`

## pseudocode

```c
__int64 __fastcall WdsCompareFiles(const WCHAR *a1, const WCHAR *a2, _DWORD *a3)
{
  unsigned int v5; // edi
  void *v6; // r14
  void *v7; // r15
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  HANDLE FileW; // r12
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  DWORD v16; // esi
  void *v17; // rax
  union _LARGE_INTEGER v18; // rbx
  union _LARGE_INTEGER v19; // rcx
  DWORD v20; // edx
  _BYTE *v21; // rcx
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-20h] BYREF
  union _LARGE_INTEGER v24; // [rsp+48h] [rbp-18h]
  union _LARGE_INTEGER v25; // [rsp+50h] [rbp-10h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-8h]
  DWORD NumberOfBytesRead; // [rsp+A8h] [rbp+48h] BYREF

  FileSize.QuadPart = 0;
  v25.QuadPart = 0;
  v5 = 0;
  v24.QuadPart = 0;
  NumberOfBytesRead = 0;
  v6 = 0;
  v7 = 0;
  hFile = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( hFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    return (unsigned int)ElValidateWin32_8(LastError, v9, v10, 4601);
  }
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v13 = GetLastError();
    v15 = 4615;
LABEL_28:
    v5 = ElValidateWin32_8(v13, v12, v14, v15);
    goto LABEL_29;
  }
  if ( !GetFileSizeEx(hFile, &FileSize) )
  {
    v13 = GetLastError();
    v15 = 4621;
    goto LABEL_28;
  }
  if ( !GetFileSizeEx(FileW, &v25) )
  {
    v13 = GetLastError();
    v15 = 4627;
    goto LABEL_28;
  }
  if ( FileSize.QuadPart == v25.QuadPart )
  {
    v16 = 0x100000;
    v6 = operator new[](0x100000u, (const struct std::nothrow_t *)&std::nothrow);
    v17 = operator new[](0x100000u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v17;
    if ( !v6 || !v17 )
    {
      v13 = 8;
      v15 = 4641;
      goto LABEL_28;
    }
    v18 = v24;
    v19 = FileSize;
    if ( v24.QuadPart >= FileSize.QuadPart )
    {
LABEL_26:
      *a3 = 1;
      goto LABEL_29;
    }
    while ( 1 )
    {
      if ( v19.QuadPart - v18.QuadPart <= 0x100000 )
        v16 = FileSize.LowPart - v24.LowPart;
      if ( !ReadFile(hFile, v6, v16, &NumberOfBytesRead, 0) )
      {
        v13 = GetLastError();
        v15 = 4658;
        goto LABEL_28;
      }
      if ( !ReadFile(FileW, v7, v16, &NumberOfBytesRead, 0) )
      {
        v13 = GetLastError();
        v15 = 4664;
        goto LABEL_28;
      }
      v20 = 0;
      if ( v16 )
        break;
LABEL_22:
      v19 = FileSize;
      v18.QuadPart += v16;
      v24 = v18;
      if ( v18.QuadPart >= FileSize.QuadPart )
        goto LABEL_26;
      v16 = 0x100000;
    }
    v21 = v6;
    while ( *v21 == v21[(_BYTE *)v7 - (_BYTE *)v6] )
    {
      ++v20;
      ++v21;
      if ( v20 >= v16 )
        goto LABEL_22;
    }
  }
  *a3 = 0;
LABEL_29:
  CloseHandle(hFile);
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( v6 )
    operator delete(v6);
  if ( v7 )
    operator delete(v7);
  return v5;
}

```

## disassembly

```asm
0x18001ad30  mov     rax, rsp
0x18001ad33  mov     [rax+8], rbx
0x18001ad37  mov     [rax+10h], rsi
0x18001ad3b  mov     [rax+18h], rdi
0x18001ad3f  push    rbp
0x18001ad40  push    r12
0x18001ad42  push    r13
0x18001ad44  push    r14
0x18001ad46  push    r15
0x18001ad48  mov     rbp, rsp
0x18001ad4b  sub     rsp, 60h
0x18001ad4f  xor     r12d, r12d
0x18001ad52  mov     r13, r8
0x18001ad55  mov     [rax-58h], r12
0x18001ad59  mov     rbx, rdx
0x18001ad5c  mov     [rax-60h], r12d
0x18001ad60  xor     r9d, r9d; lpSecurityAttributes
0x18001ad63  mov     edx, 80000000h; dwDesiredAccess
0x18001ad68  mov     qword ptr [rbp+FileSize], r12
0x18001ad6c  lea     r8d, [r12+1]; dwShareMode
0x18001ad71  mov     qword ptr [rbp+var_10], r12
0x18001ad75  mov     edi, r12d
0x18001ad78  mov     [rbp+var_18], r12
0x18001ad7c  mov     [rbp+NumberOfBytesRead], r12d
0x18001ad80  mov     r14d, r12d
0x18001ad83  mov     r15d, r12d
0x18001ad86  mov     dword ptr [rax-68h], 3
0x18001ad8d  call    cs:__imp_CreateFileW
0x18001ad94  nop     dword ptr [rax+rax+00h]
0x18001ad99  mov     [rbp+hFile], rax
0x18001ad9d  mov     rsi, rax
0x18001ada0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ada4  jnz     short loc_18001ADC6
0x18001ada6  call    cs:__imp_GetLastError
0x18001adad  nop     dword ptr [rax+rax+00h]
0x18001adb2  mov     ecx, eax
0x18001adb4  mov     r9d, 11F9h
0x18001adba  call    ElValidateWin32_8
0x18001adbf  mov     edi, eax
0x18001adc1  jmp     loc_18001AFEC
0x18001adc6  xor     r9d, r9d; lpSecurityAttributes
0x18001adc9  mov     [rsp+60h+hTemplateFile], r12; hTemplateFile
0x18001adce  mov     [rsp+60h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18001add3  mov     edx, 80000000h; dwDesiredAccess
0x18001add8  mov     rcx, rbx; lpFileName
0x18001addb  mov     [rsp+60h+dwCreationDisposition], 3; lpOverlapped
0x18001ade3  lea     r8d, [r9+1]; dwShareMode
0x18001ade7  call    cs:__imp_CreateFileW
0x18001adee  nop     dword ptr [rax+rax+00h]
0x18001adf3  mov     r12, rax
0x18001adf6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001adfa  jnz     short loc_18001AE15
0x18001adfc  call    cs:__imp_GetLastError
0x18001ae03  nop     dword ptr [rax+rax+00h]
0x18001ae08  mov     ecx, eax
0x18001ae0a  mov     r9d, 1207h
0x18001ae10  jmp     loc_18001AFA6
0x18001ae15  lea     rdx, [rbp+FileSize]; lpFileSize
0x18001ae19  mov     rcx, rsi; hFile
0x18001ae1c  call    cs:__imp_GetFileSizeEx
0x18001ae23  nop     dword ptr [rax+rax+00h]
0x18001ae28  test    eax, eax
0x18001ae2a  jnz     short loc_18001AE45
0x18001ae2c  call    cs:__imp_GetLastError
0x18001ae33  nop     dword ptr [rax+rax+00h]
0x18001ae38  mov     ecx, eax
0x18001ae3a  mov     r9d, 120Dh
0x18001ae40  jmp     loc_18001AFA6
0x18001ae45  lea     rdx, [rbp+var_10]; lpFileSize
0x18001ae49  mov     rcx, r12; hFile
0x18001ae4c  call    cs:__imp_GetFileSizeEx
0x18001ae53  nop     dword ptr [rax+rax+00h]
0x18001ae58  test    eax, eax
0x18001ae5a  jnz     short loc_18001AE75
0x18001ae5c  call    cs:__imp_GetLastError
0x18001ae63  nop     dword ptr [rax+rax+00h]
0x18001ae68  mov     ecx, eax
0x18001ae6a  mov     r9d, 1213h
0x18001ae70  jmp     loc_18001AFA6
0x18001ae75  mov     rax, qword ptr [rbp+var_10]
0x18001ae79  cmp     qword ptr [rbp+FileSize], rax
0x18001ae7d  jz      short loc_18001AE88
0x18001ae7f  and     [r13+0], edi
0x18001ae83  jmp     loc_18001AFAD
0x18001ae88  mov     esi, 100000h
0x18001ae8d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ae94  mov     ecx, esi; unsigned __int64
0x18001ae96  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ae9b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001aea2  mov     ecx, esi; unsigned __int64
0x18001aea4  mov     r14, rax
0x18001aea7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001aeac  mov     r15, rax
0x18001aeaf  test    r14, r14
0x18001aeb2  jz      loc_18001AF9B
0x18001aeb8  test    rax, rax
0x18001aebb  jz      loc_18001AF9B
0x18001aec1  mov     rbx, [rbp+var_18]
0x18001aec5  mov     rcx, qword ptr [rbp+FileSize]
0x18001aec9  cmp     rbx, rcx
0x18001aecc  jge     loc_18001AF91
0x18001aed2  sub     rcx, rbx
0x18001aed5  cmp     rcx, rsi
0x18001aed8  jg      short loc_18001AEE0
0x18001aeda  mov     esi, dword ptr [rbp+FileSize]
0x18001aedd  sub     esi, dword ptr [rbp+var_18]
0x18001aee0  mov     rcx, [rbp+hFile]; hFile
0x18001aee4  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001aee8  and     qword ptr [rsp+60h+dwCreationDisposition], rdi
0x18001aeed  mov     r8d, esi; nNumberOfBytesToRead
0x18001aef0  mov     rdx, r14; lpBuffer
0x18001aef3  call    cs:__imp_ReadFile
0x18001aefa  nop     dword ptr [rax+rax+00h]
0x18001aeff  test    eax, eax
0x18001af01  jz      short loc_18001AF7B
0x18001af03  and     qword ptr [rsp+60h+dwCreationDisposition], rdi
0x18001af08  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001af0c  mov     r8d, esi; nNumberOfBytesToRead
0x18001af0f  mov     rdx, r15; lpBuffer
0x18001af12  mov     rcx, r12; hFile
0x18001af15  call    cs:__imp_ReadFile
0x18001af1c  nop     dword ptr [rax+rax+00h]
0x18001af21  test    eax, eax
0x18001af23  jz      short loc_18001AF65
0x18001af25  xor     edx, edx
0x18001af27  test    esi, esi
0x18001af29  jz      short loc_18001AF49
0x18001af2b  mov     r8, r15
0x18001af2e  mov     rcx, r14
0x18001af31  sub     r8, r14
0x18001af34  mov     al, [r8+rcx]
0x18001af38  cmp     [rcx], al
0x18001af3a  jnz     loc_18001AE7F
0x18001af40  inc     edx
0x18001af42  inc     rcx
0x18001af45  cmp     edx, esi
0x18001af47  jb      short loc_18001AF34
0x18001af49  mov     rcx, qword ptr [rbp+FileSize]
0x18001af4d  mov     eax, esi
0x18001af4f  add     rbx, rax
0x18001af52  mov     [rbp+var_18], rbx
0x18001af56  cmp     rbx, rcx
0x18001af59  jge     short loc_18001AF91
0x18001af5b  mov     esi, 100000h
0x18001af60  jmp     loc_18001AED2
0x18001af65  call    cs:__imp_GetLastError
0x18001af6c  nop     dword ptr [rax+rax+00h]
0x18001af71  mov     ecx, eax
0x18001af73  mov     r9d, 1238h
0x18001af79  jmp     short loc_18001AFA6
0x18001af7b  call    cs:__imp_GetLastError
0x18001af82  nop     dword ptr [rax+rax+00h]
0x18001af87  mov     ecx, eax
0x18001af89  mov     r9d, 1232h
0x18001af8f  jmp     short loc_18001AFA6
0x18001af91  mov     dword ptr [r13+0], 1
0x18001af99  jmp     short loc_18001AFAD
0x18001af9b  mov     ecx, 8
0x18001afa0  mov     r9d, 1221h
0x18001afa6  call    ElValidateWin32_8
0x18001afab  mov     edi, eax
0x18001afad  mov     rcx, [rbp+hFile]; hObject
0x18001afb1  call    cs:__imp_CloseHandle
0x18001afb8  nop     dword ptr [rax+rax+00h]
0x18001afbd  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18001afc1  jz      short loc_18001AFD2
0x18001afc3  mov     rcx, r12; hObject
0x18001afc6  call    cs:__imp_CloseHandle
0x18001afcd  nop     dword ptr [rax+rax+00h]
0x18001afd2  test    r14, r14
0x18001afd5  jz      short loc_18001AFDF
0x18001afd7  mov     rcx, r14; lpMem
0x18001afda  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001afdf  test    r15, r15
0x18001afe2  jz      short loc_18001AFEC
0x18001afe4  mov     rcx, r15; lpMem
0x18001afe7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001afec  lea     r11, [rsp+60h+var_s0]
0x18001aff1  mov     eax, edi
0x18001aff3  mov     rbx, [r11+30h]
0x18001aff7  mov     rsi, [r11+38h]
0x18001affb  mov     rdi, [r11+40h]
0x18001afff  mov     rsp, r11
0x18001b002  pop     r15
0x18001b004  pop     r14
0x18001b006  pop     r13
0x18001b008  pop     r12
0x18001b00a  pop     rbp
0x18001b00b  retn
```
