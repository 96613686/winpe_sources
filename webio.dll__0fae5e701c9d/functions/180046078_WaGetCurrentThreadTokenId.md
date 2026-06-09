# WaGetCurrentThreadTokenId

- ea: `0x180046078`
- end: `0x18004614c`
- name: `WaGetCurrentThreadTokenId`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180045bcc`
- `0x180045d54`

## callees

- `0x18002e460`
- `0x180046078`
- `0x180046160`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004610d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004610d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800460f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800460f2`

## pseudocode

```c
__int64 __fastcall WaGetCurrentThreadTokenId(__int64 a1)
{
  unsigned int CurrentThreadToken; // esi
  __int64 v3; // rcx
  HANDLE TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  DWORD TokenInformationLength; // [rsp+38h] [rbp-48h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v8; // [rsp+70h] [rbp-10h]

  TokenInformationLength = 56;
  *(_QWORD *)a1 = 0;
  *(_BYTE *)(a1 + 8) = 0;
  v8 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  TokenHandle = 0;
  CurrentThreadToken = WapGetCurrentThreadToken(&TokenHandle);
  if ( !CurrentThreadToken )
  {
    if ( TokenHandle )
    {
      if ( GetTokenInformation(
             TokenHandle,
             TokenStatistics,
             TokenInformation,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        *(_QWORD *)a1 = *(_QWORD *)&TokenInformation[0];
      }
      else
      {
        CurrentThreadToken = WaGetLastError(v3);
      }
      CloseHandle(TokenHandle);
    }
    else
    {
      *(_BYTE *)(a1 + 8) = 1;
    }
  }
  return CurrentThreadToken;
}

```

## disassembly

```asm
0x180046078  mov     [rsp-8+arg_8], rbx
0x18004607d  mov     [rsp-8+arg_10], rsi
0x180046082  push    rbp
0x180046083  mov     rbp, rsp
0x180046086  sub     rsp, 80h
0x18004608d  mov     rax, cs:__security_cookie
0x180046094  xor     rax, rsp
0x180046097  mov     [rbp+var_8], rax
0x18004609b  xor     eax, eax
0x18004609d  mov     [rbp+TokenInformationLength], 38h ; '8'
0x1800460a4  xorps   xmm0, xmm0
0x1800460a7  mov     [rcx], rax
0x1800460aa  mov     [rcx+8], al
0x1800460ad  mov     rbx, rcx
0x1800460b0  lea     rcx, [rbp+TokenHandle]
0x1800460b4  mov     [rbp+var_10], rax
0x1800460b8  movups  [rbp+TokenInformation], xmm0
0x1800460bc  mov     [rbp+TokenHandle], rax
0x1800460c0  movups  [rbp+var_30], xmm0
0x1800460c4  movups  [rbp+var_20], xmm0
0x1800460c8  call    WapGetCurrentThreadToken
0x1800460cd  mov     esi, eax
0x1800460cf  test    eax, eax
0x1800460d1  jnz     short loc_180046119
0x1800460d3  cmp     [rbp+TokenHandle], 0
0x1800460d8  jz      short loc_180046146
0x1800460da  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800460de  lea     rax, [rbp+TokenInformationLength]
0x1800460e2  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800460e6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800460ea  lea     edx, [rsi+0Ah]; TokenInformationClass
0x1800460ed  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x1800460f2  call    cs:__imp_GetTokenInformation
0x1800460f9  nop     dword ptr [rax+rax+00h]
0x1800460fe  test    eax, eax
0x180046100  jz      short loc_18004613D
0x180046102  mov     rax, qword ptr [rbp+TokenInformation]
0x180046106  mov     [rbx], rax
0x180046109  mov     rcx, [rbp+TokenHandle]; hObject
0x18004610d  call    cs:__imp_CloseHandle
0x180046114  nop     dword ptr [rax+rax+00h]
0x180046119  mov     eax, esi
0x18004611b  mov     rcx, [rbp+var_8]
0x18004611f  xor     rcx, rsp; StackCookie
0x180046122  call    __security_check_cookie
0x180046127  lea     r11, [rsp+80h+var_s0]
0x18004612f  mov     rbx, [r11+18h]
0x180046133  mov     rsi, [r11+20h]
0x180046137  mov     rsp, r11
0x18004613a  pop     rbp
0x18004613b  retn
0x18004613d  call    WaGetLastError
0x180046142  mov     esi, eax
0x180046144  jmp     short loc_180046109
0x180046146  mov     byte ptr [rbx+8], 1
0x18004614a  jmp     short loc_180046119
```
