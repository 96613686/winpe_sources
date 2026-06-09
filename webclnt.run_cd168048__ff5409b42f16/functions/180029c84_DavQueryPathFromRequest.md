# DavQueryPathFromRequest

- ea: `0x180029c84`
- end: `0x180029dc5`
- name: `DavQueryPathFromRequest`
- size: `321`
- prototype: `__int64 __fastcall(HINTERNET hInternet)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800135b4`
- `0x180013fec`
- `0x180029dcc`

## callees

- `0x18000b7dc`
- `0x180029c84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d80`
- `KERNEL32!LocalFree` at `0x180029d30`
- `KERNEL32!LocalFree` at `0x180029d30`
- `KERNEL32!LocalAlloc` at `0x180029cca`
- `KERNEL32!LocalAlloc` at `0x180029cca`
- `WINHTTP!WinHttpQueryOption` at `0x180029ca6`
- `WINHTTP!WinHttpQueryOption` at `0x180029ce8`
- `WINHTTP!WinHttpQueryOption` at `0x180029ca6`
- `WINHTTP!WinHttpQueryOption` at `0x180029ce8`

## pseudocode

```c
void *__fastcall DavQueryPathFromRequest(HINTERNET hInternet)
{
  void *v1; // rbx
  DWORD LastError; // eax
  HLOCAL v4; // rax
  DWORD v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  DWORD dwBufferLength; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  dwBufferLength = 0;
  if ( WinHttpQueryOption(hInternet, 0x22u, 0, &dwBufferLength) )
  {
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v1;
    v7 = 31;
LABEL_18:
    WPP_SF_d(v6[2], v7, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, LastError);
    return v1;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v1;
    v7 = 30;
    goto LABEL_18;
  }
  v4 = LocalAlloc(0x40u, dwBufferLength);
  v1 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v1;
    v7 = 29;
    goto LABEL_18;
  }
  if ( !WinHttpQueryOption(hInternet, 0x22u, v4, &dwBufferLength) )
  {
    v5 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids, v5);
    LocalFree(v1);
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x180029c84  mov     [rsp+arg_0], rbx
0x180029c89  push    rdi
0x180029c8a  sub     rsp, 20h
0x180029c8e  xor     ebx, ebx
0x180029c90  mov     [rsp+28h+dwBufferLength], 0
0x180029c98  lea     r9, [rsp+28h+dwBufferLength]; lpdwBufferLength
0x180029c9d  xor     r8d, r8d; lpBuffer
0x180029ca0  mov     rdi, rcx
0x180029ca3  lea     edx, [rbx+22h]; dwOption
0x180029ca6  call    cs:__imp_WinHttpQueryOption
0x180029cac  test    eax, eax
0x180029cae  jnz     loc_180029D80
0x180029cb4  call    cs:__imp_GetLastError
0x180029cba  cmp     eax, 7Ah ; 'z'
0x180029cbd  jnz     loc_180029D60
0x180029cc3  mov     edx, [rsp+28h+dwBufferLength]; uBytes
0x180029cc7  lea     ecx, [rbx+40h]; uFlags
0x180029cca  call    cs:__imp_LocalAlloc
0x180029cd0  mov     rbx, rax
0x180029cd3  test    rax, rax
0x180029cd6  jz      short loc_180029D3A
0x180029cd8  lea     r9, [rsp+28h+dwBufferLength]; lpdwBufferLength
0x180029cdd  mov     r8, rax; lpBuffer
0x180029ce0  mov     edx, 22h ; '"'; dwOption
0x180029ce5  mov     rcx, rdi; hInternet
0x180029ce8  call    cs:__imp_WinHttpQueryOption
0x180029cee  test    eax, eax
0x180029cf0  jnz     loc_180029DB7
0x180029cf6  call    cs:__imp_GetLastError
0x180029cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d03  lea     rdx, WPP_GLOBAL_Control
0x180029d0a  cmp     rcx, rdx
0x180029d0d  jz      short loc_180029D2D
0x180029d0f  test    byte ptr [rcx+1Ch], 1
0x180029d13  jz      short loc_180029D2D
0x180029d15  mov     rcx, [rcx+10h]
0x180029d19  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x180029d20  mov     edx, 1Ch
0x180029d25  mov     r9d, eax
0x180029d28  call    WPP_SF_d
0x180029d2d  mov     rcx, rbx; hMem
0x180029d30  call    cs:__imp_LocalFree
0x180029d36  xor     ebx, ebx
0x180029d38  jmp     short loc_180029DB7
0x180029d3a  call    cs:__imp_GetLastError
0x180029d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d47  lea     rdx, WPP_GLOBAL_Control
0x180029d4e  cmp     rcx, rdx
0x180029d51  jz      short loc_180029DB7
0x180029d53  test    byte ptr [rcx+1Ch], 1
0x180029d57  jz      short loc_180029DB7
0x180029d59  mov     edx, 1Dh
0x180029d5e  jmp     short loc_180029DA4
0x180029d60  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d67  lea     rdx, WPP_GLOBAL_Control
0x180029d6e  cmp     rcx, rdx
0x180029d71  jz      short loc_180029DB7
0x180029d73  test    byte ptr [rcx+1Ch], 1
0x180029d77  jz      short loc_180029DB7
0x180029d79  mov     edx, 1Eh
0x180029d7e  jmp     short loc_180029DA4
0x180029d80  call    cs:__imp_GetLastError
0x180029d86  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d8d  lea     rdx, WPP_GLOBAL_Control
0x180029d94  cmp     rcx, rdx
0x180029d97  jz      short loc_180029DB7
0x180029d99  test    byte ptr [rcx+1Ch], 1
0x180029d9d  jz      short loc_180029DB7
0x180029d9f  mov     edx, 1Fh
0x180029da4  mov     rcx, [rcx+10h]
0x180029da8  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x180029daf  mov     r9d, eax
0x180029db2  call    WPP_SF_d
0x180029db7  mov     rax, rbx
0x180029dba  mov     rbx, [rsp+28h+arg_0]
0x180029dbf  add     rsp, 20h
0x180029dc3  pop     rdi
0x180029dc4  retn
```
