# HashFileData

- ea: `0x18002f194`
- end: `0x18002f2f8`
- name: `HashFileData`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002f300`

## callees

- `0x180003950`
- `0x180003974`
- `0x180005f64`
- `0x18000a6d0`
- `0x18000deec`
- `0x18002f194`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f2d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f2d8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002f24f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002f24f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002f267`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002f284`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002f267`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002f284`

## pseudocode

```c
__int64 __fastcall HashFileData(const WCHAR *a1, HCRYPTHASH a2, HCRYPTHASH a3, struct _SECURITY_ATTRIBUTES *a4)
{
  BYTE *v4; // rbx
  void *FileRetryIfSharingViolation; // rsi
  const char *v8; // r9
  __int64 v9; // rdx
  unsigned int LastError; // edi
  int lpOverlapped; // [rsp+20h] [rbp-78h]
  void *v13; // [rsp+30h] [rbp-68h]
  unsigned int v14; // [rsp+38h] [rbp-60h]
  void *v15; // [rsp+40h] [rbp-58h]
  DWORD NumberOfBytesRead; // [rsp+64h] [rbp-34h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v4 = 0;
  NumberOfBytesRead = 0;
  FileRetryIfSharingViolation = SusCreateFileRetryIfSharingViolation(
                                  a1,
                                  1u,
                                  1u,
                                  a4,
                                  3u,
                                  0x8000000u,
                                  v13,
                                  v14,
                                  v15,
                                  0,
                                  0);
  if ( FileRetryIfSharingViolation == (void *)-1LL )
  {
    v9 = 249;
  }
  else
  {
    v4 = (BYTE *)SafeSusAllocArray(0x100000u, 1u);
    LastError = v4 == 0 ? 0x8007000E : 0;
    if ( !v4 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
        (const char *)LastError,
        lpOverlapped);
      goto LABEL_15;
    }
    while ( ReadFile(FileRetryIfSharingViolation, v4, 0x100000u, &NumberOfBytesRead, 0) )
    {
      if ( !CryptHashData(a2, v4, NumberOfBytesRead, 0) )
      {
        v9 = 270;
        goto LABEL_14;
      }
      if ( a3 && !CryptHashData(a3, v4, NumberOfBytesRead, 0) )
      {
        v9 = 277;
        goto LABEL_14;
      }
      if ( !NumberOfBytesRead )
      {
        LastError = 0;
        goto LABEL_16;
      }
    }
    v9 = 263;
  }
LABEL_14:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v9,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
                v8);
LABEL_15:
  if ( v4 )
LABEL_16:
    CSusBaseAllocTag<942762101>::operator delete(v4);
  if ( FileRetryIfSharingViolation != (void *)-1LL )
    CloseHandle(FileRetryIfSharingViolation);
  return LastError;
}

```

## disassembly

```asm
0x18002f194  push    rbx
0x18002f196  push    rbp
0x18002f197  push    rsi
0x18002f198  push    rdi
0x18002f199  push    r14
0x18002f19b  sub     rsp, 70h
0x18002f19f  mov     rax, cs:__security_cookie
0x18002f1a6  xor     rax, rsp
0x18002f1a9  mov     [rsp+98h+var_30], rax
0x18002f1ae  xor     ebx, ebx
0x18002f1b0  mov     rbp, r8
0x18002f1b3  mov     [rsp+98h+var_48], ebx; unsigned int
0x18002f1b7  mov     r14, rdx
0x18002f1ba  mov     [rsp+98h+var_50], ebx; int
0x18002f1be  mov     [rsp+98h+var_70], 8000000h; DWORD
0x18002f1c6  lea     edi, [rbx+1]
0x18002f1c9  mov     [rsp+98h+NumberOfBytesRead], ebx
0x18002f1cd  mov     r8d, edi; dwShareMode
0x18002f1d0  mov     dword ptr [rsp+98h+lpOverlapped], 3; int
0x18002f1d8  mov     edx, edi; dwDesiredAccess
0x18002f1da  call    ?SusCreateFileRetryIfSharingViolation@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXK2HK@Z; SusCreateFileRetryIfSharingViolation(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,void *,int,ulong)
0x18002f1df  mov     rsi, rax
0x18002f1e2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002f1e6  jnz     short loc_18002F1F2
0x18002f1e8  mov     edx, 0F9h
0x18002f1ed  jmp     loc_18002F2AC
0x18002f1f2  mov     rdx, rdi; unsigned __int64
0x18002f1f5  mov     ecx, 100000h; unsigned __int64
0x18002f1fa  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18002f1ff  mov     rbx, rax
0x18002f202  neg     rax
0x18002f205  sbb     edi, edi
0x18002f207  not     edi
0x18002f209  and     edi, 8007000Eh
0x18002f20f  test    rbx, rbx
0x18002f212  jnz     short loc_18002F235
0x18002f214  mov     rcx, [rsp+98h]; this
0x18002f21c  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18002f223  mov     r9d, edi; char *
0x18002f226  mov     edx, 0FCh; void *
0x18002f22b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f230  jmp     loc_18002F2C2
0x18002f235  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002f23a  mov     [rsp+98h+lpOverlapped], 0; lpOverlapped
0x18002f243  mov     r8d, 100000h; nNumberOfBytesToRead
0x18002f249  mov     rdx, rbx; lpBuffer
0x18002f24c  mov     rcx, rsi; hFile
0x18002f24f  call    cs:__imp_ReadFile
0x18002f255  test    eax, eax
0x18002f257  jz      short loc_18002F2A7
0x18002f259  mov     r8d, [rsp+98h+NumberOfBytesRead]; dwDataLen
0x18002f25e  xor     r9d, r9d; dwFlags
0x18002f261  mov     rdx, rbx; pbData
0x18002f264  mov     rcx, r14; hHash
0x18002f267  call    cs:__imp_CryptHashData
0x18002f26d  test    eax, eax
0x18002f26f  jz      short loc_18002F2A0
0x18002f271  test    rbp, rbp
0x18002f274  jz      short loc_18002F28E
0x18002f276  mov     r8d, [rsp+98h+NumberOfBytesRead]; dwDataLen
0x18002f27b  xor     r9d, r9d; dwFlags
0x18002f27e  mov     rdx, rbx; pbData
0x18002f281  mov     rcx, rbp; hHash
0x18002f284  call    cs:__imp_CryptHashData
0x18002f28a  test    eax, eax
0x18002f28c  jz      short loc_18002F299
0x18002f28e  cmp     [rsp+98h+NumberOfBytesRead], 0
0x18002f293  jnz     short loc_18002F235
0x18002f295  xor     edi, edi
0x18002f297  jmp     short loc_18002F2C7
0x18002f299  mov     edx, 115h
0x18002f29e  jmp     short loc_18002F2AC
0x18002f2a0  mov     edx, 10Eh
0x18002f2a5  jmp     short loc_18002F2AC
0x18002f2a7  mov     edx, 107h; void *
0x18002f2ac  mov     rcx, [rsp+98h]; this
0x18002f2b4  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18002f2bb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f2c0  mov     edi, eax
0x18002f2c2  test    rbx, rbx
0x18002f2c5  jz      short loc_18002F2CF
0x18002f2c7  mov     rcx, rbx; lpMem
0x18002f2ca  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002f2cf  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002f2d3  jz      short loc_18002F2DE
0x18002f2d5  mov     rcx, rsi; hObject
0x18002f2d8  call    cs:__imp_CloseHandle
0x18002f2de  mov     eax, edi
0x18002f2e0  mov     rcx, [rsp+98h+var_30]
0x18002f2e5  xor     rcx, rsp; StackCookie
0x18002f2e8  call    __security_check_cookie
0x18002f2ed  add     rsp, 70h
0x18002f2f1  pop     r14
0x18002f2f3  pop     rdi
0x18002f2f4  pop     rsi
0x18002f2f5  pop     rbp
0x18002f2f6  pop     rbx
0x18002f2f7  retn
```
