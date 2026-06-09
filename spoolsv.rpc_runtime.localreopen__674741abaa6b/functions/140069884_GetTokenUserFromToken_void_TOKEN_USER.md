# GetTokenUserFromToken(void *,_TOKEN_USER * *)

- ea: `0x140069884`
- end: `0x1400699a7`
- name: `?GetTokenUserFromToken@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z`
- size: `291`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, struct _TOKEN_USER **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14006aae0`

## callees

- `0x140004790`
- `0x140015378`
- `0x140069884`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140069903`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140069999`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140069903`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140069999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400698e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006995b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400698e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006995b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400698d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14006993a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400698d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14006993a`

## string_xrefs

- `0x14006997c`: `GetTokenUserFromToken`

## pseudocode

```c
__int64 __fastcall GetTokenUserFromToken(HANDLE TokenHandle, struct _TOKEN_USER **a2)
{
  struct _TOKEN_USER *v4; // rdi
  DWORD v5; // ebx
  DWORD LastError; // eax
  DWORD v7; // ebx
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  v4 = (struct _TOKEN_USER *)DllAllocSplMem(0x58u);
  if ( !v4 )
    goto LABEL_2;
  v5 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, v4, 0x58u, &TokenInformationLength) )
  {
LABEL_9:
    *a2 = v4;
    return v5;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( !LastError )
    goto LABEL_12;
  if ( LastError == 122 )
  {
    HeapFree(g_hSpoolssHeap, 0, v4);
    v7 = TokenInformationLength;
    v4 = (struct _TOKEN_USER *)DllAllocSplMem(TokenInformationLength);
    if ( !v4 )
    {
LABEL_2:
      v5 = 8;
      goto LABEL_13;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v4, v7, &TokenInformationLength) )
    {
      v5 = 0;
      goto LABEL_9;
    }
    v5 = GetLastError();
    if ( !v5 )
LABEL_12:
      v5 = 5;
  }
LABEL_13:
  PrvSpoolssTelemetry::WriteDbgTraceError("GetTokenUserFromToken", L"Failed.  Error %d.", v5);
  if ( v4 )
    HeapFree(g_hSpoolssHeap, 0, v4);
  return v5;
}

```

## disassembly

```asm
0x140069884  push    rbx
0x140069886  push    rbp
0x140069887  push    rsi
0x140069888  push    rdi
0x140069889  sub     rsp, 38h
0x14006988d  mov     rbp, rcx
0x140069890  mov     [rsp+58h+TokenInformationLength], 0
0x140069898  mov     ecx, 58h ; 'X'; dwBytes
0x14006989d  mov     rsi, rdx
0x1400698a0  call    DllAllocSplMem
0x1400698a5  mov     rdi, rax
0x1400698a8  test    rax, rax
0x1400698ab  jnz     short loc_1400698B7
0x1400698ad  mov     ebx, 8
0x1400698b2  jmp     loc_140069972
0x1400698b7  xor     ebx, ebx
0x1400698b9  lea     rax, [rsp+58h+TokenInformationLength]
0x1400698be  mov     r8, rdi; TokenInformation
0x1400698c1  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1400698c6  mov     rcx, rbp; TokenHandle
0x1400698c9  lea     r9d, [rbx+58h]; TokenInformationLength
0x1400698cd  lea     edx, [rbx+1]; TokenInformationClass
0x1400698d0  call    cs:__imp_GetTokenInformation
0x1400698d7  nop     dword ptr [rax+rax+00h]
0x1400698dc  test    eax, eax
0x1400698de  jnz     short loc_14006994C
0x1400698e0  call    cs:__imp_GetLastError
0x1400698e7  nop     dword ptr [rax+rax+00h]
0x1400698ec  mov     ebx, eax
0x1400698ee  test    eax, eax
0x1400698f0  jz      short loc_14006996D
0x1400698f2  cmp     eax, 7Ah ; 'z'
0x1400698f5  jnz     short loc_140069972
0x1400698f7  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x1400698fe  mov     r8, rdi; lpMem
0x140069901  xor     edx, edx; dwFlags
0x140069903  call    cs:__imp_HeapFree
0x14006990a  nop     dword ptr [rax+rax+00h]
0x14006990f  mov     ebx, [rsp+58h+TokenInformationLength]
0x140069913  mov     ecx, ebx; dwBytes
0x140069915  call    DllAllocSplMem
0x14006991a  mov     rdi, rax
0x14006991d  test    rax, rax
0x140069920  jz      short loc_1400698AD
0x140069922  lea     rax, [rsp+58h+TokenInformationLength]
0x140069927  mov     r9d, ebx; TokenInformationLength
0x14006992a  mov     r8, rdi; TokenInformation
0x14006992d  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x140069932  mov     edx, 1; TokenInformationClass
0x140069937  mov     rcx, rbp; TokenHandle
0x14006993a  call    cs:__imp_GetTokenInformation
0x140069941  nop     dword ptr [rax+rax+00h]
0x140069946  test    eax, eax
0x140069948  jz      short loc_14006995B
0x14006994a  xor     ebx, ebx
0x14006994c  mov     [rsi], rdi
0x14006994f  mov     eax, ebx
0x140069951  add     rsp, 38h
0x140069955  pop     rdi
0x140069956  pop     rsi
0x140069957  pop     rbp
0x140069958  pop     rbx
0x140069959  retn
0x14006995b  call    cs:__imp_GetLastError
0x140069962  nop     dword ptr [rax+rax+00h]
0x140069967  mov     ebx, eax
0x140069969  test    eax, eax
0x14006996b  jnz     short loc_140069972
0x14006996d  mov     ebx, 5
0x140069972  mov     r8d, ebx
0x140069975  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x14006997c  lea     rcx, aGettokenuserfr; "GetTokenUserFromToken"
0x140069983  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140069988  test    rdi, rdi
0x14006998b  jz      short loc_14006994F
0x14006998d  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140069994  mov     r8, rdi; lpMem
0x140069997  xor     edx, edx; dwFlags
0x140069999  call    cs:__imp_HeapFree
0x1400699a0  nop     dword ptr [rax+rax+00h]
0x1400699a5  jmp     short loc_14006994F
```
