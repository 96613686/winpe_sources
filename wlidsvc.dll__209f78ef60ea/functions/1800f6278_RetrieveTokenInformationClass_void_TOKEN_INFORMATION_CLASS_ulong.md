# RetrieveTokenInformationClass(void *,_TOKEN_INFORMATION_CLASS,ulong *)

- ea: `0x1800f6278`
- end: `0x1800f6368`
- name: `?RetrieveTokenInformationClass@@YAPEAXPEAXW4_TOKEN_INFORMATION_CLASS@@PEAK@Z`
- size: `240`
- prototype: `void *__fastcall(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009b1f0`

## callees

- `0x180019690`
- `0x1800f6278`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f634d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f634d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f62e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f62e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f62a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f62b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f62f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f62a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f62b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f62f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6323`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f62a3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f6319`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f62a3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f6319`

## string_xrefs

- `0x1800f62bc`: `GetTokenInformation failed with %d`
- `0x1800f632f`: `GetTokenInformation failed with %d`
- `0x1800f62c7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\kiosk.cpp`
- `0x1800f6336`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\kiosk.cpp`

## pseudocode

```c
void *__fastcall RetrieveTokenInformationClass(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS a2, unsigned int *a3)
{
  void *v5; // rbx
  DWORD LastError; // eax
  const unsigned __int16 *v7; // r9
  unsigned int v8; // r8d
  HLOCAL v9; // rax
  PDWORD ReturnLength; // [rsp+20h] [rbp-18h]
  PDWORD ReturnLengtha; // [rsp+20h] [rbp-18h]

  *a3 = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, a3);
  if ( GetLastError() != 122 )
  {
    v5 = 0;
    LastError = GetLastError();
    v7 = L"GetTokenInformation failed with %d";
    v8 = 51;
LABEL_3:
    LODWORD(ReturnLength) = LastError;
    TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\kiosk.cpp", v8, v7, ReturnLength);
    return v5;
  }
  v9 = LocalAlloc(0x40u, *a3);
  v5 = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    v7 = L"LocalAlloc failed with %d";
    v8 = 61;
    goto LABEL_3;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v9, *a3, a3) )
  {
    LODWORD(ReturnLengtha) = GetLastError();
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\kiosk.cpp",
      0x47u,
      L"GetTokenInformation failed with %d",
      ReturnLengtha);
    LocalFree(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800f6278  mov     [rsp+arg_0], rbx
0x1800f627d  mov     [rsp+arg_8], rsi
0x1800f6282  push    rdi
0x1800f6283  sub     rsp, 30h
0x1800f6287  xor     r9d, r9d; TokenInformationLength
0x1800f628a  mov     dword ptr [r8], 0
0x1800f6291  mov     rdi, r8
0x1800f6294  mov     [rsp+38h+ReturnLength], r8; ReturnLength
0x1800f6299  xor     r8d, r8d; TokenInformation
0x1800f629c  mov     rsi, rcx
0x1800f629f  lea     edx, [r9+1]; TokenInformationClass
0x1800f62a3  call    cs:__imp_GetTokenInformation
0x1800f62a9  call    cs:__imp_GetLastError
0x1800f62af  cmp     eax, 7Ah ; 'z'
0x1800f62b2  jz      short loc_1800F62DE
0x1800f62b4  xor     ebx, ebx
0x1800f62b6  call    cs:__imp_GetLastError
0x1800f62bc  lea     r9, aGettokeninform_1; "GetTokenInformation failed with %d"
0x1800f62c3  lea     r8d, [rbx+33h]; unsigned int
0x1800f62c7  lea     rdx, aOnecoreuapDsEx_20; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f62ce  mov     dword ptr [rsp+38h+ReturnLength], eax
0x1800f62d2  mov     ecx, 2; unsigned __int8
0x1800f62d7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800f62dc  jmp     short loc_1800F6355
0x1800f62de  mov     edx, [rdi]; uBytes
0x1800f62e0  mov     ecx, 40h ; '@'; uFlags
0x1800f62e5  call    cs:__imp_LocalAlloc
0x1800f62eb  mov     rbx, rax
0x1800f62ee  test    rax, rax
0x1800f62f1  jnz     short loc_1800F6306
0x1800f62f3  call    cs:__imp_GetLastError
0x1800f62f9  lea     r9, aLocalallocFail_0; "LocalAlloc failed with %d"
0x1800f6300  lea     r8d, [rbx+3Dh]
0x1800f6304  jmp     short loc_1800F62C7
0x1800f6306  mov     r9d, [rdi]; TokenInformationLength
0x1800f6309  mov     r8, rbx; TokenInformation
0x1800f630c  mov     edx, 1; TokenInformationClass
0x1800f6311  mov     [rsp+38h+ReturnLength], rdi; ReturnLength
0x1800f6316  mov     rcx, rsi; TokenHandle
0x1800f6319  call    cs:__imp_GetTokenInformation
0x1800f631f  test    eax, eax
0x1800f6321  jnz     short loc_1800F6355
0x1800f6323  call    cs:__imp_GetLastError
0x1800f6329  mov     r8d, 47h ; 'G'; unsigned int
0x1800f632f  lea     r9, aGettokeninform_1; "GetTokenInformation failed with %d"
0x1800f6336  lea     rdx, aOnecoreuapDsEx_20; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f633d  mov     dword ptr [rsp+38h+ReturnLength], eax
0x1800f6341  lea     ecx, [r8-45h]; unsigned __int8
0x1800f6345  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800f634a  mov     rcx, rbx; hMem
0x1800f634d  call    cs:__imp_LocalFree
0x1800f6353  xor     ebx, ebx
0x1800f6355  mov     rsi, [rsp+38h+arg_8]
0x1800f635a  mov     rax, rbx
0x1800f635d  mov     rbx, [rsp+38h+arg_0]
0x1800f6362  add     rsp, 30h
0x1800f6366  pop     rdi
0x1800f6367  retn
```
