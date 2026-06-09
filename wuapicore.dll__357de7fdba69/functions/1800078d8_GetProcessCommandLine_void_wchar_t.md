# GetProcessCommandLine(void *,wchar_t * *)

- ea: `0x1800078d8`
- end: `0x180007ae3`
- name: `?GetProcessCommandLine@@YAJPEAXPEAPEA_W@Z`
- size: `523`
- prototype: `__int64 __fastcall(HANDLE hProcess, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800072f8`

## callees

- `0x180006ac4`
- `0x1800078d8`
- `0x180007d34`
- `0x180007e3c`
- `0x180081a38`
- `0x180081adc`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800079a6`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800079ff`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180007a72`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800079a6`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800079ff`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180007a72`
- `ntdll!NtQueryInformationProcess` at `0x18000795d`
- `ntdll!NtQueryInformationProcess` at `0x18000795d`

## string_xrefs

- `0x1800079b9`: `C:\__w\1\s\src\Client\comapi\CallerIdUtil.cpp`
- `0x180007aa2`: `C:\__w\1\s\src\Client\comapi\CallerIdUtil.cpp`

## pseudocode

```c
__int64 __fastcall GetProcessCommandLine(HANDLE hProcess, wchar_t **a2)
{
  wchar_t *v2; // rbx
  __int64 v5; // rdx
  unsigned int v6; // edi
  NTSTATUS v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  int LastError; // eax
  const char *v11; // r9
  __int64 v12; // rdx
  SIZE_T v13; // r15
  int ReturnLength; // [rsp+20h] [rbp-39h]
  __int64 Buffer; // [rsp+30h] [rbp-29h] BYREF
  LPCVOID lpBaseAddress[2]; // [rsp+38h] [rbp-21h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+48h] [rbp-11h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+78h] [rbp+1Fh] BYREF
  ULONG v20; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  Buffer = 0;
  v2 = 0;
  v20 = 0;
  NumberOfBytesRead = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  *(_OWORD *)lpBaseAddress = 0;
  if ( hProcess )
  {
    if ( !a2 )
    {
      v5 = 126;
      goto LABEL_5;
    }
    *a2 = 0;
    v7 = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, &v20);
    if ( v7 < 0 )
    {
      LastError = wil::details::in1diag3::Return_NtStatus(retaddr, v8, v9, (const char *)(unsigned int)v7, ReturnLength);
LABEL_13:
      v6 = LastError;
      goto LABEL_29;
    }
    if ( v20 == 48 && *((_QWORD *)&ProcessInformation[0] + 1) )
    {
      if ( !ReadProcessMemory(
              hProcess,
              (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 32LL),
              &Buffer,
              8u,
              &NumberOfBytesRead) )
      {
        v12 = 148;
LABEL_12:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v12,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\CallerIdUtil.cpp",
                      v11);
        goto LABEL_13;
      }
      if ( NumberOfBytesRead == 8 )
      {
        NumberOfBytesRead = 0;
        if ( !ReadProcessMemory(hProcess, (LPCVOID)(Buffer + 112), lpBaseAddress, 0x10u, &NumberOfBytesRead) )
        {
          v12 = 161;
          goto LABEL_12;
        }
        if ( NumberOfBytesRead == 16 && lpBaseAddress[1] )
        {
          v13 = LOWORD(lpBaseAddress[0]);
          v2 = (wchar_t *)SafeSusAllocArray(((unsigned __int64)LOWORD(lpBaseAddress[0]) >> 1) + 1, 2u);
          v6 = v2 == 0 ? 0x8007000E : 0;
          if ( !v2 )
          {
            v5 = 169;
            goto LABEL_28;
          }
          NumberOfBytesRead = 0;
          if ( ReadProcessMemory(hProcess, lpBaseAddress[1], v2, v13, &NumberOfBytesRead) )
          {
            *a2 = v2;
            return 0;
          }
          v12 = 180;
          goto LABEL_12;
        }
        v5 = 162;
      }
      else
      {
        v5 = 149;
      }
    }
    else
    {
      v5 = 138;
    }
    v6 = -2147467259;
    goto LABEL_28;
  }
  v5 = 125;
LABEL_5:
  v6 = -2147024809;
LABEL_28:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\CallerIdUtil.cpp",
    (const char *)v6,
    ReturnLength);
LABEL_29:
  if ( v2 )
    SusFree(v2);
  return v6;
}

```

## disassembly

```asm
0x1800078d8  mov     [rsp-8+arg_10], rbx
0x1800078dd  push    rbp
0x1800078de  push    rsi
0x1800078df  push    rdi
0x1800078e0  push    r14
0x1800078e2  push    r15
0x1800078e4  lea     rbp, [rsp-37h]
0x1800078e9  sub     rsp, 90h
0x1800078f0  mov     rax, cs:__security_cookie
0x1800078f7  xor     rax, rsp
0x1800078fa  mov     [rbp+57h+var_28], rax
0x1800078fe  xorps   xmm0, xmm0
0x180007901  mov     [rbp+57h+Buffer], 0
0x180007909  xor     ebx, ebx
0x18000790b  mov     r14, rdx
0x18000790e  mov     [rbp+57h+var_30], ebx
0x180007911  mov     rsi, rcx
0x180007914  mov     [rbp+57h+NumberOfBytesRead], rbx
0x180007918  movups  [rbp+57h+ProcessInformation], xmm0
0x18000791c  movups  [rbp+57h+var_58], xmm0
0x180007920  movups  [rbp+57h+var_48], xmm0
0x180007924  movups  xmmword ptr [rbp+57h+lpBaseAddress], xmm0
0x180007928  test    rcx, rcx
0x18000792b  jnz     short loc_180007932
0x18000792d  lea     edx, [rcx+7Dh]
0x180007930  jmp     short loc_18000793B
0x180007932  test    r14, r14
0x180007935  jnz     short loc_180007945
0x180007937  lea     edx, [r14+7Eh]
0x18000793b  mov     edi, 80070057h
0x180007940  jmp     loc_180007A9E
0x180007945  mov     [rdx], rbx
0x180007948  lea     rax, [rbp+57h+var_30]
0x18000794c  xor     edx, edx; ProcessInformationClass
0x18000794e  mov     qword ptr [rsp+0B0h+ReturnLength], rax; int
0x180007953  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180007959  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x18000795d  call    cs:__imp_NtQueryInformationProcess
0x180007963  test    eax, eax
0x180007965  jns     short loc_180007975
0x180007967  mov     rcx, [rbp+5Fh]; this
0x18000796b  mov     r9d, eax; char *
0x18000796e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180007973  jmp     short loc_1800079C5
0x180007975  cmp     [rbp+57h+var_30], 30h ; '0'
0x180007979  jnz     loc_180007A94
0x18000797f  mov     rdx, qword ptr [rbp+57h+ProcessInformation+8]
0x180007983  test    rdx, rdx
0x180007986  jz      loc_180007A94
0x18000798c  lea     rax, [rbp+57h+NumberOfBytesRead]
0x180007990  add     rdx, 20h ; ' '; lpBaseAddress
0x180007994  mov     r9d, 8; nSize
0x18000799a  mov     qword ptr [rsp+0B0h+ReturnLength], rax; lpNumberOfBytesRead
0x18000799f  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800079a3  mov     rcx, rsi; hProcess
0x1800079a6  call    cs:__imp_ReadProcessMemory
0x1800079ac  test    eax, eax
0x1800079ae  jnz     short loc_1800079CC
0x1800079b0  mov     edx, 94h; void *
0x1800079b5  mov     rcx, [rbp+5Fh]; this
0x1800079b9  lea     r8, aCW1SSrcClientC_3; "C:\\__w\\1\\s\\src\\Client\\comapi\\Cal"...
0x1800079c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800079c5  mov     edi, eax
0x1800079c7  jmp     loc_180007AB1
0x1800079cc  cmp     [rbp+57h+NumberOfBytesRead], 8
0x1800079d1  jz      short loc_1800079DD
0x1800079d3  mov     edx, 95h
0x1800079d8  jmp     loc_180007A99
0x1800079dd  mov     rdx, [rbp+57h+Buffer]
0x1800079e1  lea     rax, [rbp+57h+NumberOfBytesRead]
0x1800079e5  add     rdx, 70h ; 'p'; lpBaseAddress
0x1800079e9  mov     [rbp+57h+NumberOfBytesRead], rbx
0x1800079ed  mov     r9d, 10h; nSize
0x1800079f3  mov     qword ptr [rsp+0B0h+ReturnLength], rax; lpNumberOfBytesRead
0x1800079f8  lea     r8, [rbp+57h+lpBaseAddress]; lpBuffer
0x1800079fc  mov     rcx, rsi; hProcess
0x1800079ff  call    cs:__imp_ReadProcessMemory
0x180007a05  test    eax, eax
0x180007a07  jnz     short loc_180007A10
0x180007a09  mov     edx, 0A1h
0x180007a0e  jmp     short loc_1800079B5
0x180007a10  cmp     [rbp+57h+NumberOfBytesRead], 10h
0x180007a15  jnz     short loc_180007A8D
0x180007a17  cmp     [rbp+57h+lpBaseAddress+8], rbx
0x180007a1b  jz      short loc_180007A8D
0x180007a1d  movzx   r15d, word ptr [rbp+57h+lpBaseAddress]
0x180007a22  mov     edx, 2; unsigned __int64
0x180007a27  mov     ecx, r15d
0x180007a2a  shr     rcx, 1
0x180007a2d  inc     rcx; unsigned __int64
0x180007a30  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180007a35  mov     rcx, rax
0x180007a38  mov     rbx, rax
0x180007a3b  neg     rcx
0x180007a3e  sbb     edi, edi
0x180007a40  not     edi
0x180007a42  and     edi, 8007000Eh
0x180007a48  test    rax, rax
0x180007a4b  jnz     short loc_180007A54
0x180007a4d  mov     edx, 0A9h
0x180007a52  jmp     short loc_180007A9E
0x180007a54  mov     rdx, [rbp+57h+lpBaseAddress+8]; lpBaseAddress
0x180007a58  lea     rax, [rbp+57h+NumberOfBytesRead]
0x180007a5c  mov     r9, r15; nSize
0x180007a5f  mov     qword ptr [rsp+0B0h+ReturnLength], rax; lpNumberOfBytesRead
0x180007a64  mov     r8, rbx; lpBuffer
0x180007a67  mov     [rbp+57h+NumberOfBytesRead], 0
0x180007a6f  mov     rcx, rsi; hProcess
0x180007a72  call    cs:__imp_ReadProcessMemory
0x180007a78  test    eax, eax
0x180007a7a  jnz     short loc_180007A86
0x180007a7c  mov     edx, 0B4h
0x180007a81  jmp     loc_1800079B5
0x180007a86  mov     [r14], rbx
0x180007a89  xor     edi, edi
0x180007a8b  jmp     short loc_180007ABE
0x180007a8d  mov     edx, 0A2h
0x180007a92  jmp     short loc_180007A99
0x180007a94  mov     edx, 8Ah; void *
0x180007a99  mov     edi, 80004005h
0x180007a9e  mov     rcx, [rbp+5Fh]; this
0x180007aa2  lea     r8, aCW1SSrcClientC_3; "C:\\__w\\1\\s\\src\\Client\\comapi\\Cal"...
0x180007aa9  mov     r9d, edi; char *
0x180007aac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ab1  test    rbx, rbx
0x180007ab4  jz      short loc_180007ABE
0x180007ab6  mov     rcx, rbx; lpMem
0x180007ab9  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180007abe  mov     eax, edi
0x180007ac0  mov     rcx, [rbp+57h+var_28]
0x180007ac4  xor     rcx, rsp; StackCookie
0x180007ac7  call    __security_check_cookie
0x180007acc  mov     rbx, [rsp+0B0h+arg_10]
0x180007ad4  add     rsp, 90h
0x180007adb  pop     r15
0x180007add  pop     r14
0x180007adf  pop     rdi
0x180007ae0  pop     rsi
0x180007ae1  pop     rbp
0x180007ae2  retn
```
