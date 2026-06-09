# SetAutoDetectProxyFlagForUser(HWND__ *,HINSTANCE__ *,char *,int)

- ea: `0x18000e650`
- end: `0x18000e7c9`
- name: `?SetAutoDetectProxyFlagForUser@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEADH@Z`
- size: `377`
- prototype: `void __fastcall(HWND, HINSTANCE, char *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000e650`
- `0x180012d6e`
- `0x180012db0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e77d`
- `KERNEL32!GetLastError` at `0x18000e77d`
- `KERNEL32!TerminateProcess` at `0x18000e79c`
- `KERNEL32!TerminateProcess` at `0x18000e79c`
- `KERNEL32!GetCurrentProcess` at `0x18000e78b`
- `KERNEL32!GetCurrentProcess` at `0x18000e78b`
- `WININET!InternetGetConnectedStateExW` at `0x18000e6b2`
- `WININET!InternetGetConnectedStateExW` at `0x18000e6b2`
- `WININET!InternetSetOptionW` at `0x18000e721`
- `WININET!InternetSetOptionW` at `0x18000e73d`
- `WININET!InternetSetOptionW` at `0x18000e759`
- `WININET!InternetSetOptionW` at `0x18000e721`
- `WININET!InternetSetOptionW` at `0x18000e73d`
- `WININET!InternetSetOptionW` at `0x18000e759`
- `WININET!InternetInitializeAutoProxyDll` at `0x18000e76d`
- `WININET!InternetInitializeAutoProxyDll` at `0x18000e76d`

## pseudocode

```c
void __fastcall SetAutoDetectProxyFlagForUser(HWND a1, HINSTANCE a2, char *a3)
{
  WCHAR *v3; // rbx
  WCHAR *v4; // rax
  UINT LastError; // ebx
  HANDLE CurrentProcess; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-E0h] BYREF
  __int128 Buffer; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v9; // [rsp+38h] [rbp-C8h]
  _DWORD v10[10]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR szConnectionName[264]; // [rsp+70h] [rbp-90h] BYREF

  dwFlags = 0;
  Buffer = 0;
  v9 = 0;
  memset_0(szConnectionName, 0, 0x202u);
  v3 = 0;
  if ( InternetGetConnectedStateExW(&dwFlags, szConnectionName, 0x100u, 0) )
  {
    v4 = szConnectionName;
    if ( (dwFlags & 2) != 0 )
      v4 = 0;
    v3 = v4;
  }
  v10[0] = 5;
  v10[2] = 0;
  v10[4] = 1;
  v10[6] = 9;
  LODWORD(Buffer) = 32;
  *((_QWORD *)&Buffer + 1) = v3;
  *(_QWORD *)&v9 = 2;
  *((_QWORD *)&v9 + 1) = v10;
  if ( !InternetSetOptionW(0, 0x4Bu, &Buffer, 0x20u)
    || !InternetSetOptionW(0, 0x27u, 0, 0)
    || !InternetSetOptionW(0, 0x25u, 0, 0)
    || (LastError = 0, !InternetInitializeAutoProxyDll(0)) )
  {
    LastError = GetLastError();
  }
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, LastError);
}

```

## disassembly

```asm
0x18000e650  mov     [rsp-8+arg_0], rbx
0x18000e655  push    rbp
0x18000e656  lea     rbp, [rsp-190h]
0x18000e65e  sub     rsp, 290h
0x18000e665  mov     rax, cs:__security_cookie
0x18000e66c  xor     rax, rsp
0x18000e66f  mov     [rbp+190h+var_10], rax
0x18000e676  xorps   xmm0, xmm0
0x18000e679  mov     [rsp+290h+dwFlags], 0
0x18000e681  xor     edx, edx; Val
0x18000e683  lea     rcx, [rsp+290h+szConnectionName]; void *
0x18000e688  mov     r8d, 202h; Size
0x18000e68e  movups  [rsp+290h+Buffer], xmm0
0x18000e693  movups  [rsp+290h+var_258], xmm0
0x18000e698  call    memset_0
0x18000e69d  xor     r9d, r9d; dwReserved
0x18000e6a0  lea     rdx, [rsp+290h+szConnectionName]; lpszConnectionName
0x18000e6a5  mov     r8d, 100h; cchNameLen
0x18000e6ab  lea     rcx, [rsp+290h+dwFlags]; lpdwFlags
0x18000e6b0  xor     ebx, ebx
0x18000e6b2  call    cs:__imp_InternetGetConnectedStateExW
0x18000e6b9  nop     dword ptr [rax+rax+00h]
0x18000e6be  test    eax, eax
0x18000e6c0  jz      short loc_18000E6D3
0x18000e6c2  test    byte ptr [rsp+290h+dwFlags], 2
0x18000e6c7  lea     rax, [rsp+290h+szConnectionName]
0x18000e6cc  cmovnz  rax, rbx
0x18000e6d0  mov     rbx, rax
0x18000e6d3  mov     r9d, 20h ; ' '; dwBufferLength
0x18000e6d9  mov     [rsp+290h+var_248], 5
0x18000e6e1  lea     rax, [rsp+290h+var_248]
0x18000e6e6  mov     [rsp+290h+var_240], 0
0x18000e6ee  lea     r8, [rsp+290h+Buffer]; lpBuffer
0x18000e6f3  mov     [rsp+290h+var_238], 1
0x18000e6fb  xor     ecx, ecx; hInternet
0x18000e6fd  mov     [rsp+290h+var_230], 9
0x18000e705  lea     edx, [r9+2Bh]; dwOption
0x18000e709  mov     dword ptr [rsp+290h+Buffer], r9d
0x18000e70e  mov     qword ptr [rsp+290h+Buffer+8], rbx
0x18000e713  mov     qword ptr [rsp+290h+var_258], 2
0x18000e71c  mov     qword ptr [rsp+290h+var_258+8], rax
0x18000e721  call    cs:__imp_InternetSetOptionW
0x18000e728  nop     dword ptr [rax+rax+00h]
0x18000e72d  test    eax, eax
0x18000e72f  jz      short loc_18000E77D
0x18000e731  xor     r9d, r9d; dwBufferLength
0x18000e734  xor     r8d, r8d; lpBuffer
0x18000e737  xor     ecx, ecx; hInternet
0x18000e739  lea     edx, [r9+27h]; dwOption
0x18000e73d  call    cs:__imp_InternetSetOptionW
0x18000e744  nop     dword ptr [rax+rax+00h]
0x18000e749  test    eax, eax
0x18000e74b  jz      short loc_18000E77D
0x18000e74d  xor     r9d, r9d; dwBufferLength
0x18000e750  xor     r8d, r8d; lpBuffer
0x18000e753  xor     ecx, ecx; hInternet
0x18000e755  lea     edx, [r9+25h]; dwOption
0x18000e759  call    cs:__imp_InternetSetOptionW
0x18000e760  nop     dword ptr [rax+rax+00h]
0x18000e765  test    eax, eax
0x18000e767  jz      short loc_18000E77D
0x18000e769  xor     ecx, ecx; dwReserved
0x18000e76b  xor     ebx, ebx
0x18000e76d  call    cs:__imp_InternetInitializeAutoProxyDll
0x18000e774  nop     dword ptr [rax+rax+00h]
0x18000e779  test    eax, eax
0x18000e77b  jnz     short loc_18000E78B
0x18000e77d  call    cs:__imp_GetLastError
0x18000e784  nop     dword ptr [rax+rax+00h]
0x18000e789  mov     ebx, eax
0x18000e78b  call    cs:__imp_GetCurrentProcess
0x18000e792  nop     dword ptr [rax+rax+00h]
0x18000e797  mov     rcx, rax; hProcess
0x18000e79a  mov     edx, ebx; uExitCode
0x18000e79c  call    cs:__imp_TerminateProcess
0x18000e7a3  nop     dword ptr [rax+rax+00h]
0x18000e7a8  mov     rcx, [rbp+190h+var_10]
0x18000e7af  xor     rcx, rsp; StackCookie
0x18000e7b2  call    __security_check_cookie
0x18000e7b7  mov     rbx, [rsp+290h+arg_0]
0x18000e7bf  add     rsp, 290h
0x18000e7c6  pop     rbp
0x18000e7c7  retn
```
