# DeletePathEngine

- ea: `0x18003eba8`
- end: `0x18003edd6`
- name: `DeletePathEngine`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18003eddc`

## callees

- `0x18003d150`
- `0x18003d5cc`
- `0x18003e138`
- `0x18003eba8`
- `0x18003fbfc`
- `0x18003fcdc`
- `0x18003ff18`
- `0x1800607b0`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18003ed57`
- `KERNEL32!HeapFree` at `0x18003ed77`
- `KERNEL32!HeapFree` at `0x18003ed97`
- `KERNEL32!HeapFree` at `0x18003ed57`
- `KERNEL32!HeapFree` at `0x18003ed77`
- `KERNEL32!HeapFree` at `0x18003ed97`
- `KERNEL32!GetLastError` at `0x18003ec77`
- `KERNEL32!GetLastError` at `0x18003ec77`
- `KERNEL32!GetCurrentDirectoryW` at `0x18003ecae`
- `KERNEL32!GetCurrentDirectoryW` at `0x18003ecae`
- `KERNEL32!SetLastError` at `0x18003ed34`
- `KERNEL32!SetLastError` at `0x18003ed34`
- `KERNEL32!GetProcessHeap` at `0x18003ed43`
- `KERNEL32!GetProcessHeap` at `0x18003ed63`
- `KERNEL32!GetProcessHeap` at `0x18003ed83`
- `KERNEL32!GetProcessHeap` at `0x18003ed43`
- `KERNEL32!GetProcessHeap` at `0x18003ed63`
- `KERNEL32!GetProcessHeap` at `0x18003ed83`

## string_xrefs

- `0x18003ecee`: `DeletePathEngine: Hit %d failure%s during recursive deletion of [%s]; 1st error = 0x%x, cd = [%s]`

## pseudocode

```c
__int64 __fastcall DeletePathEngine(const WCHAR *a1)
{
  unsigned __int16 *v1; // rax
  unsigned __int16 *v2; // rsi
  WCHAR *v3; // rax
  WCHAR *v4; // rdi
  const WCHAR *v5; // rax
  unsigned __int16 *v6; // rbx
  unsigned int v7; // r14d
  HANDLE ProcessHeap; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  __int64 dwErrCode; // [rsp+48h] [rbp-C0h] BYREF
  int v13[2]; // [rsp+50h] [rbp-B8h]
  __int64 v14; // [rsp+58h] [rbp-B0h]
  __int64 v15; // [rsp+60h] [rbp-A8h]
  WCHAR Buffer[264]; // [rsp+68h] [rbp-A0h] BYREF

  v13[0] = 1;
  dwErrCode = 0;
  v15 = 0;
  v14 = 0;
  v13[1] = 32;
  v1 = FormFullPathName(a1);
  v2 = v1;
  if ( !v1 )
    return 0;
  v3 = FormLongPathName(v1);
  v4 = v3;
  if ( !v3 )
    return 0;
  v5 = (const WCHAR *)FormFinalPathName(v3);
  v6 = (unsigned __int16 *)v5;
  if ( !v5 )
    return 0;
  v7 = EnumeratePathEx(
         v5,
         (__int64 (__fastcall *)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64))DeletePathDirectoryCallback,
         (__int64 (__fastcall *)(DWORD *, __int64))DeletePathFileCallback,
         (__int64)&dwErrCode,
         v13[0]);
  if ( !(unsigned int)DeleteFileEx2(v6, 32) )
  {
    ++HIDWORD(dwErrCode);
    if ( !(_DWORD)dwErrCode )
      LODWORD(dwErrCode) = GetLastError();
  }
  if ( HIDWORD(dwErrCode) )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( !GetCurrentDirectoryW(0x104u, Buffer) )
      Buffer[0] = 0;
    LibLog(
      &g_WdsLibLog,
      0x4000000,
      L"DeletePathEngine: Hit %d failure%s during recursive deletion of [%s]; 1st error = 0x%x, cd = [%s]");
    if ( (_DWORD)dwErrCode )
      SetLastError(dwErrCode);
    v7 = 0;
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v6);
  v9 = GetProcessHeap();
  HeapFree(v9, 0, v4);
  v10 = GetProcessHeap();
  HeapFree(v10, 0, v2);
  return v7;
}

```

## disassembly

```asm
0x18003eba8  mov     rax, rsp
0x18003ebab  mov     [rax+10h], rbx
0x18003ebaf  mov     [rax+18h], rsi
0x18003ebb3  mov     [rax+20h], rdi
0x18003ebb7  push    rbp
0x18003ebb8  push    r14
0x18003ebba  push    r15
0x18003ebbc  lea     rbp, [rax-198h]
0x18003ebc3  sub     rsp, 280h
0x18003ebca  mov     rax, cs:__security_cookie
0x18003ebd1  xor     rax, rsp
0x18003ebd4  mov     [rbp+190h+var_20], rax
0x18003ebdb  xor     r15d, r15d
0x18003ebde  mov     [rsp+290h+var_248], 1
0x18003ebe6  mov     qword ptr [rsp+290h+dwErrCode], r15
0x18003ebeb  mov     [rsp+290h+var_238], r15
0x18003ebf0  mov     [rsp+290h+var_240], r15
0x18003ebf5  mov     [rsp+290h+var_248+4], 20h ; ' '
0x18003ebfd  call    FormFullPathName
0x18003ec02  mov     rsi, rax
0x18003ec05  test    rax, rax
0x18003ec08  jz      loc_18003EDA8
0x18003ec0e  mov     rcx, rax
0x18003ec11  call    FormLongPathName
0x18003ec16  mov     rdi, rax
0x18003ec19  test    rax, rax
0x18003ec1c  jz      loc_18003EDA8
0x18003ec22  mov     rcx, rax; String1
0x18003ec25  call    FormFinalPathName
0x18003ec2a  mov     rbx, rax
0x18003ec2d  test    rax, rax
0x18003ec30  jz      loc_18003EDA8
0x18003ec36  mov     ecx, [rsp+290h+var_248]
0x18003ec3a  lea     r9, [rsp+290h+dwErrCode]
0x18003ec3f  mov     [rsp+290h+var_270], ecx; int
0x18003ec43  lea     r8, DeletePathFileCallback
0x18003ec4a  mov     rcx, rax; lpFileName
0x18003ec4d  lea     rdx, DeletePathDirectoryCallback
0x18003ec54  call    EnumeratePathEx
0x18003ec59  lea     edx, [r15+20h]
0x18003ec5d  mov     rcx, rbx
0x18003ec60  mov     r14d, eax
0x18003ec63  call    DeleteFileEx2
0x18003ec68  test    eax, eax
0x18003ec6a  jnz     short loc_18003EC87
0x18003ec6c  inc     [rsp+290h+var_24C]
0x18003ec70  cmp     [rsp+290h+dwErrCode], r15d
0x18003ec75  jnz     short loc_18003EC87
0x18003ec77  call    cs:__imp_GetLastError
0x18003ec7e  nop     dword ptr [rax+rax+00h]
0x18003ec83  mov     [rsp+290h+dwErrCode], eax
0x18003ec87  cmp     [rsp+290h+var_24C], r15d
0x18003ec8c  jbe     loc_18003ED43
0x18003ec92  xor     edx, edx; Val
0x18003ec94  lea     rcx, [rsp+290h+Buffer]; void *
0x18003ec99  mov     r8d, 208h; Size
0x18003ec9f  call    memset_0
0x18003eca4  lea     rdx, [rsp+290h+Buffer]; lpBuffer
0x18003eca9  mov     ecx, 104h; nBufferLength
0x18003ecae  call    cs:__imp_GetCurrentDirectoryW
0x18003ecb5  nop     dword ptr [rax+rax+00h]
0x18003ecba  test    eax, eax
0x18003ecbc  jnz     short loc_18003ECC9
0x18003ecbe  movzx   ecx, r15w
0x18003ecc2  mov     [rsp+290h+Buffer], cx
0x18003ecc7  jmp     short loc_18003ECCE
0x18003ecc9  movzx   ecx, [rsp+290h+Buffer]
0x18003ecce  mov     r9d, [rsp+290h+var_24C]
0x18003ecd3  lea     rdx, aUnavailable; "<unavailable>"
0x18003ecda  cmp     r15w, cx
0x18003ecde  lea     rax, [rsp+290h+Buffer]
0x18003ece3  lea     rcx, word_1800684DC
0x18003ecea  cmovz   rax, rdx
0x18003ecee  lea     r8, aDeletepathengi; "DeletePathEngine: Hit %d failure%s duri"...
0x18003ecf5  mov     [rsp+290h+var_258], rax
0x18003ecfa  lea     rdx, aS; "s"
0x18003ed01  mov     eax, [rsp+290h+dwErrCode]
0x18003ed05  cmp     r9d, 1
0x18003ed09  mov     dword ptr [rsp+290h+var_260], eax
0x18003ed0d  cmovnz  rcx, rdx
0x18003ed11  mov     qword ptr [rsp+290h+var_268], rbx
0x18003ed16  mov     qword ptr [rsp+290h+var_270], rcx
0x18003ed1b  mov     edx, 4000000h
0x18003ed20  lea     rcx, g_WdsLibLog
0x18003ed27  call    LibLog
0x18003ed2c  mov     ecx, [rsp+290h+dwErrCode]; dwErrCode
0x18003ed30  test    ecx, ecx
0x18003ed32  jz      short loc_18003ED40
0x18003ed34  call    cs:__imp_SetLastError
0x18003ed3b  nop     dword ptr [rax+rax+00h]
0x18003ed40  mov     r14d, r15d
0x18003ed43  call    cs:__imp_GetProcessHeap
0x18003ed4a  nop     dword ptr [rax+rax+00h]
0x18003ed4f  mov     r8, rbx; lpMem
0x18003ed52  xor     edx, edx; dwFlags
0x18003ed54  mov     rcx, rax; hHeap
0x18003ed57  call    cs:__imp_HeapFree
0x18003ed5e  nop     dword ptr [rax+rax+00h]
0x18003ed63  call    cs:__imp_GetProcessHeap
0x18003ed6a  nop     dword ptr [rax+rax+00h]
0x18003ed6f  mov     r8, rdi; lpMem
0x18003ed72  xor     edx, edx; dwFlags
0x18003ed74  mov     rcx, rax; hHeap
0x18003ed77  call    cs:__imp_HeapFree
0x18003ed7e  nop     dword ptr [rax+rax+00h]
0x18003ed83  call    cs:__imp_GetProcessHeap
0x18003ed8a  nop     dword ptr [rax+rax+00h]
0x18003ed8f  mov     r8, rsi; lpMem
0x18003ed92  xor     edx, edx; dwFlags
0x18003ed94  mov     rcx, rax; hHeap
0x18003ed97  call    cs:__imp_HeapFree
0x18003ed9e  nop     dword ptr [rax+rax+00h]
0x18003eda3  mov     eax, r14d
0x18003eda6  jmp     short loc_18003EDAA
0x18003eda8  xor     eax, eax
0x18003edaa  mov     rcx, [rbp+190h+var_20]
0x18003edb1  xor     rcx, rsp; StackCookie
0x18003edb4  call    __security_check_cookie
0x18003edb9  lea     r11, [rsp+290h+var_10]
0x18003edc1  mov     rbx, [r11+28h]
0x18003edc5  mov     rsi, [r11+30h]
0x18003edc9  mov     rdi, [r11+38h]
0x18003edcd  mov     rsp, r11
0x18003edd0  pop     r15
0x18003edd2  pop     r14
0x18003edd4  pop     rbp
0x18003edd5  retn
```
