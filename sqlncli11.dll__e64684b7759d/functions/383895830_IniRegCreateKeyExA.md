# IniRegCreateKeyExA

- ea: `0x383895830`
- end: `0x38389589d`
- name: `IniRegCreateKeyExA`
- size: `109`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCCH lpMultiByteStr@<rdx>, DWORD ulOptions, REGSAM, LPSECURITY_ATTRIBUTES, PHKEY, LPDWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x38387dae0`

## callees

- `0x383895830`
- `0x383adc710`

## import_xrefs

- `KERNEL32!GetLastError` at `0x3839103fc`
- `KERNEL32!GetLastError` at `0x3839103fc`
- `KERNEL32!SetLastError` at `0x3839103b9`
- `KERNEL32!SetLastError` at `0x383910466`
- `KERNEL32!SetLastError` at `0x3839103b9`
- `KERNEL32!SetLastError` at `0x383910466`
- `KERNEL32!MultiByteToWideChar` at `0x3839103f2`
- `KERNEL32!MultiByteToWideChar` at `0x3839103f2`
- `KERNEL32!HeapAlloc` at `0x3839103a8`
- `KERNEL32!HeapAlloc` at `0x3839103a8`
- `KERNEL32!HeapFree` at `0x38391045e`
- `KERNEL32!HeapFree` at `0x38391045e`
- `KERNEL32!GetProcessHeap` at `0x38391039a`
- `KERNEL32!GetProcessHeap` at `0x383910450`
- `KERNEL32!GetProcessHeap` at `0x38391039a`
- `KERNEL32!GetProcessHeap` at `0x383910450`
- `KERNEL32!DebugBreak` at `0x38391036e`
- `KERNEL32!DebugBreak` at `0x38391037f`
- `KERNEL32!DebugBreak` at `0x38391036e`
- `KERNEL32!DebugBreak` at `0x38391037f`
- `ADVAPI32!RegCreateKeyExA` at `0x38389588d`
- `ADVAPI32!RegCreateKeyExA` at `0x38389588d`

## pseudocode

```c
LSTATUS __fastcall IniRegCreateKeyExA(
        HKEY hKey,
        LPCCH lpMultiByteStr,
        DWORD a3,
        CHAR *a4,
        DWORD ulOptions,
        REGSAM samDesired,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        PHKEY phkResult,
        LPDWORD lpdwDisposition)
{
  __int64 v13; // rax
  int v14; // ebp
  SIZE_T v15; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v17; // rax
  WCHAR *v18; // rsi
  DWORD Key; // eax
  DWORD v20; // ebx
  HANDLE v21; // rax

  if ( !dword_383B1F178 )
    return RegCreateKeyExA(
             hKey,
             lpMultiByteStr,
             a3,
             a4,
             ulOptions,
             samDesired,
             lpSecurityAttributes,
             phkResult,
             lpdwDisposition);
  if ( a4 )
    DebugBreak();
  if ( lpSecurityAttributes )
    DebugBreak();
  v13 = -1;
  do
    ++v13;
  while ( lpMultiByteStr[v13] );
  v14 = v13 + 1;
  v15 = 2LL * (unsigned int)(v13 + 1);
  ProcessHeap = GetProcessHeap();
  v17 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v15);
  v18 = v17;
  if ( v17 )
  {
    if ( MultiByteToWideChar(0, 0, lpMultiByteStr, -1, v17, v14) )
      Key = IniRegCreateKeyExW(hKey, v18, a3, 0, ulOptions, samDesired, 0, phkResult, lpdwDisposition);
    else
      Key = GetLastError();
    v20 = Key;
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v18);
    SetLastError(v20);
    return v20;
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
0x383895830  push    rdi
0x383895832  push    r14
0x383895834  push    r15
0x383895836  sub     rsp, 50h
0x38389583a  cmp     cs:dword_383B1F178, 0
0x383895841  mov     r14d, r8d
0x383895844  mov     rdi, rdx
0x383895847  mov     r15, rcx
0x38389584a  jnz     loc_383910357
0x383895850  mov     rax, [rsp+68h+arg_40]
0x383895858  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x38389585d  mov     rax, [rsp+68h+arg_38]
0x383895865  mov     [rsp+68h+phkResult], rax; phkResult
0x38389586a  mov     rax, [rsp+68h+arg_30]
0x383895872  mov     [rsp+68h+lpSecurityAttributes], rax; lpSecurityAttributes
0x383895877  mov     eax, [rsp+68h+arg_28]
0x38389587e  mov     [rsp+68h+samDesired], eax; samDesired
0x383895882  mov     eax, [rsp+68h+ulOptions]
0x383895889  mov     [rsp+68h+dwOptions], eax; dwOptions
0x38389588d  call    cs:__imp_RegCreateKeyExA
0x383895893  add     rsp, 50h
0x383895897  pop     r15
0x383895899  pop     r14
0x38389589b  pop     rdi
0x38389589c  retn
0x383910357  mov     [rsp+68h+arg_0], rbx
0x38391035c  mov     [rsp+68h+arg_8], rbp
0x383910361  mov     [rsp+68h+arg_10], rsi
0x383910369  test    r9, r9
0x38391036c  jz      short loc_383910374
0x38391036e  call    cs:__imp_DebugBreak
0x383910374  cmp     [rsp+68h+arg_30], 0
0x38391037d  jz      short loc_383910385
0x38391037f  call    cs:__imp_DebugBreak
0x383910385  or      rax, 0FFFFFFFFFFFFFFFFh
0x383910389  inc     rax
0x38391038c  cmp     byte ptr [rax+rdi], 0
0x383910390  jnz     short loc_383910389
0x383910392  lea     ebp, [rax+1]
0x383910395  mov     ebx, ebp
0x383910397  add     rbx, rbx
0x38391039a  call    cs:__imp_GetProcessHeap
0x3839103a0  mov     r8, rbx; dwBytes
0x3839103a3  mov     rcx, rax; hHeap
0x3839103a6  xor     edx, edx; dwFlags
0x3839103a8  call    cs:__imp_HeapAlloc
0x3839103ae  mov     rsi, rax
0x3839103b1  test    rax, rax
0x3839103b4  jnz     short loc_3839103DE
0x3839103b6  lea     ecx, [rax+8]; dwErrCode
0x3839103b9  call    cs:__imp_SetLastError
0x3839103bf  lea     eax, [rsi+8]
0x3839103c2  mov     rbp, [rsp+68h+arg_8]
0x3839103c7  mov     rbx, [rsp+68h+arg_0]
0x3839103cc  mov     rsi, [rsp+68h+arg_10]
0x3839103d4  add     rsp, 50h
0x3839103d8  pop     r15
0x3839103da  pop     r14
0x3839103dc  pop     rdi
0x3839103dd  retn
0x3839103de  or      r9d, 0FFFFFFFFh; cbMultiByte
0x3839103e2  mov     r8, rdi; lpMultiByteStr
0x3839103e5  xor     edx, edx; dwFlags
0x3839103e7  xor     ecx, ecx; CodePage
0x3839103e9  mov     [rsp+68h+samDesired], ebp; cchWideChar
0x3839103ed  mov     qword ptr [rsp+68h+dwOptions], rax; lpWideCharStr
0x3839103f2  call    cs:__imp_MultiByteToWideChar
0x3839103f8  test    eax, eax
0x3839103fa  jnz     short loc_383910404
0x3839103fc  call    cs:__imp_GetLastError
0x383910402  jmp     short loc_38391044E
0x383910404  mov     rax, [rsp+68h+arg_40]
0x38391040c  xor     r9d, r9d
0x38391040f  mov     r8d, r14d
0x383910412  mov     [rsp+68h+lpdwDisposition], rax; LPDWORD
0x383910417  mov     rax, [rsp+68h+arg_38]
0x38391041f  mov     rdx, rsi; lpSubKey
0x383910422  mov     [rsp+68h+phkResult], rax; PHKEY
0x383910427  mov     eax, [rsp+68h+arg_28]
0x38391042e  mov     [rsp+68h+lpSecurityAttributes], 0; LPSECURITY_ATTRIBUTES
0x383910437  mov     [rsp+68h+samDesired], eax; samDesired
0x38391043b  mov     eax, [rsp+68h+ulOptions]
0x383910442  mov     rcx, r15; hKey
0x383910445  mov     [rsp+68h+dwOptions], eax; ulOptions
0x383910449  call    IniRegCreateKeyExW
0x38391044e  mov     ebx, eax
0x383910450  call    cs:__imp_GetProcessHeap
0x383910456  mov     r8, rsi; lpMem
0x383910459  mov     rcx, rax; hHeap
0x38391045c  xor     edx, edx; dwFlags
0x38391045e  call    cs:__imp_HeapFree
0x383910464  mov     ecx, ebx; dwErrCode
0x383910466  call    cs:__imp_SetLastError
0x38391046c  mov     eax, ebx
0x38391046e  jmp     loc_3839103C2
```
