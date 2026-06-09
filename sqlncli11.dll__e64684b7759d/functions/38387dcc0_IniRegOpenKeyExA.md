# IniRegOpenKeyExA

- ea: `0x38387dcc0`
- end: `0x38387dd06`
- name: `IniRegOpenKeyExA`
- size: `70`
- prototype: `__int64 __fastcall(HKEY hKey, LPCCH lpMultiByteStr, DWORD ulOptions, REGSAM samDesired, PHKEY)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x38387dae0`
- `0x383884c30`
- `0x38388f8a0`
- `0x383890710`
- `0x383894b20`
- `0x383894e80`
- `0x3838951a0`
- `0x383ad7260`
- `0x383ad74e0`

## callees

- `0x38387dcc0`
- `0x383addfe0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383910758`
- `KERNEL32!GetLastError` at `0x383910758`
- `KERNEL32!SetLastError` at `0x383910712`
- `KERNEL32!SetLastError` at `0x3839107a9`
- `KERNEL32!SetLastError` at `0x383910712`
- `KERNEL32!SetLastError` at `0x3839107a9`
- `KERNEL32!MultiByteToWideChar` at `0x38391074e`
- `KERNEL32!MultiByteToWideChar` at `0x38391074e`
- `KERNEL32!HeapAlloc` at `0x383910701`
- `KERNEL32!HeapAlloc` at `0x383910701`
- `KERNEL32!HeapFree` at `0x3839107a1`
- `KERNEL32!HeapFree` at `0x3839107a1`
- `KERNEL32!GetProcessHeap` at `0x3839106f3`
- `KERNEL32!GetProcessHeap` at `0x383910793`
- `KERNEL32!GetProcessHeap` at `0x3839106f3`
- `KERNEL32!GetProcessHeap` at `0x383910793`
- `ADVAPI32!RegOpenKeyExW` at `0x38391078b`
- `ADVAPI32!RegOpenKeyExW` at `0x38391078b`
- `ADVAPI32!RegOpenKeyExA` at `0x38387dcf1`
- `ADVAPI32!RegOpenKeyExA` at `0x38387dcf1`

## pseudocode

```c
LSTATUS __fastcall IniRegOpenKeyExA(
        HKEY hKey,
        LPCCH lpMultiByteStr,
        DWORD ulOptions,
        REGSAM samDesired,
        PHKEY phkResult)
{
  __int64 v10; // rax
  int cchWideChar; // r12d
  SIZE_T v12; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v14; // rax
  WCHAR *v15; // rsi
  DWORD LastError; // eax
  DWORD v17; // ebx
  HANDLE v18; // rax

  if ( !dword_383B1F178 )
    return RegOpenKeyExA(hKey, lpMultiByteStr, ulOptions, samDesired, phkResult);
  v10 = -1;
  do
    ++v10;
  while ( lpMultiByteStr[v10] );
  cchWideChar = v10 + 1;
  v12 = 2LL * (unsigned int)(v10 + 1);
  ProcessHeap = GetProcessHeap();
  v14 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v12);
  v15 = v14;
  if ( v14 )
  {
    if ( MultiByteToWideChar(0, 0, lpMultiByteStr, -1, v14, cchWideChar) )
    {
      if ( dword_383B1F178 )
        LastError = IniRegOpenKeyW(hKey, v15, phkResult);
      else
        LastError = RegOpenKeyExW(hKey, v15, ulOptions, samDesired, phkResult);
    }
    else
    {
      LastError = GetLastError();
    }
    v17 = LastError;
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v15);
    SetLastError(v17);
    return v17;
  }
  else
  {
    SetLastError(8u);
    return 8;
  }
}

```

## disassembly

```asm
0x38387dcc0  mov     [rsp+arg_18], rbp
0x38387dcc5  push    rdi
0x38387dcc6  push    r14
0x38387dcc8  push    r15
0x38387dcca  sub     rsp, 30h
0x38387dcce  cmp     cs:dword_383B1F178, 0
0x38387dcd5  mov     r14d, r9d
0x38387dcd8  mov     r15d, r8d
0x38387dcdb  mov     rdi, rdx
0x38387dcde  mov     rbp, rcx
0x38387dce1  jnz     loc_3839106C5
0x38387dce7  mov     rax, [rsp+48h+arg_20]
0x38387dcec  mov     [rsp+48h+phkResult], rax; phkResult
0x38387dcf1  call    cs:__imp_RegOpenKeyExA
0x38387dcf7  mov     rbp, [rsp+48h+arg_18]
0x38387dcfc  add     rsp, 30h
0x38387dd00  pop     r15
0x38387dd02  pop     r14
0x38387dd04  pop     rdi
0x38387dd05  retn
0x3839106c5  mov     [rsp+48h+arg_0], rbx
0x3839106ca  mov     [rsp+48h+arg_8], rsi
0x3839106cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x3839106d3  mov     [rsp+48h+arg_10], r12
0x3839106d8  nop     dword ptr [rax+rax+00000000h]
0x3839106e0  inc     rax
0x3839106e3  cmp     byte ptr [rdx+rax], 0
0x3839106e7  jnz     short loc_3839106E0
0x3839106e9  lea     r12d, [rax+1]
0x3839106ed  mov     ebx, r12d
0x3839106f0  add     rbx, rbx
0x3839106f3  call    cs:__imp_GetProcessHeap
0x3839106f9  mov     r8, rbx; dwBytes
0x3839106fc  mov     rcx, rax; hHeap
0x3839106ff  xor     edx, edx; dwFlags
0x383910701  call    cs:__imp_HeapAlloc
0x383910707  mov     rsi, rax
0x38391070a  test    rax, rax
0x38391070d  jnz     short loc_383910739
0x38391070f  lea     ecx, [rax+8]; dwErrCode
0x383910712  call    cs:__imp_SetLastError
0x383910718  lea     eax, [rsi+8]
0x38391071b  mov     rsi, [rsp+48h+arg_8]
0x383910720  mov     rbx, [rsp+48h+arg_0]
0x383910725  mov     r12, [rsp+48h+arg_10]
0x38391072a  mov     rbp, [rsp+48h+arg_18]
0x38391072f  add     rsp, 30h
0x383910733  pop     r15
0x383910735  pop     r14
0x383910737  pop     rdi
0x383910738  retn
0x383910739  or      r9d, 0FFFFFFFFh; cbMultiByte
0x38391073d  mov     r8, rdi; lpMultiByteStr
0x383910740  xor     edx, edx; dwFlags
0x383910742  xor     ecx, ecx; CodePage
0x383910744  mov     [rsp+48h+cchWideChar], r12d; cchWideChar
0x383910749  mov     [rsp+48h+phkResult], rax; lpWideCharStr
0x38391074e  call    cs:__imp_MultiByteToWideChar
0x383910754  test    eax, eax
0x383910756  jnz     short loc_383910760
0x383910758  call    cs:__imp_GetLastError
0x38391075e  jmp     short loc_383910791
0x383910760  cmp     cs:dword_383B1F178, 0
0x383910767  mov     rdx, rsi; lpSubKey
0x38391076a  mov     rcx, rbp; hKey
0x38391076d  jz      short loc_38391077B
0x38391076f  mov     r8, [rsp+48h+arg_20]
0x383910774  call    IniRegOpenKeyW
0x383910779  jmp     short loc_383910791
0x38391077b  mov     rax, [rsp+48h+arg_20]
0x383910780  mov     r9d, r14d; samDesired
0x383910783  mov     r8d, r15d; ulOptions
0x383910786  mov     [rsp+48h+phkResult], rax; phkResult
0x38391078b  call    cs:__imp_RegOpenKeyExW
0x383910791  mov     ebx, eax
0x383910793  call    cs:__imp_GetProcessHeap
0x383910799  mov     r8, rsi; lpMem
0x38391079c  mov     rcx, rax; hHeap
0x38391079f  xor     edx, edx; dwFlags
0x3839107a1  call    cs:__imp_HeapFree
0x3839107a7  mov     ecx, ebx; dwErrCode
0x3839107a9  call    cs:__imp_SetLastError
0x3839107af  mov     eax, ebx
0x3839107b1  jmp     loc_38391071B
```
