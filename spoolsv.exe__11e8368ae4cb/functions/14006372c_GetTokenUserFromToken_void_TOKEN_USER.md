# GetTokenUserFromToken(void *,_TOKEN_USER * *)

- ea: `0x14006372c`
- end: `0x14006382a`
- name: `?GetTokenUserFromToken@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z`
- size: `254`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, struct _TOKEN_USER **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140064810`

## callees

- `0x1400041c0`
- `0x1400140cc`
- `0x14006372c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006379f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140063822`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006379f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140063822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140063782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400637ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140063782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400637ea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140063778`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400637d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140063778`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400637d0`

## string_xrefs

- `0x140063805`: `GetTokenUserFromToken`

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
0x14006372c  push    rbx
0x14006372e  push    rbp
0x14006372f  push    rsi
0x140063730  push    rdi
0x140063731  sub     rsp, 38h
0x140063735  mov     rbp, rcx
0x140063738  mov     [rsp+58h+TokenInformationLength], 0
0x140063740  mov     ecx, 58h ; 'X'; dwBytes
0x140063745  mov     rsi, rdx
0x140063748  call    DllAllocSplMem
0x14006374d  mov     rdi, rax
0x140063750  test    rax, rax
0x140063753  jnz     short loc_14006375F
0x140063755  mov     ebx, 8
0x14006375a  jmp     loc_1400637FB
0x14006375f  xor     ebx, ebx
0x140063761  lea     rax, [rsp+58h+TokenInformationLength]
0x140063766  mov     r8, rdi; TokenInformation
0x140063769  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x14006376e  mov     rcx, rbp; TokenHandle
0x140063771  lea     r9d, [rbx+58h]; TokenInformationLength
0x140063775  lea     edx, [rbx+1]; TokenInformationClass
0x140063778  call    cs:__imp_GetTokenInformation
0x14006377e  test    eax, eax
0x140063780  jnz     short loc_1400637DC
0x140063782  call    cs:__imp_GetLastError
0x140063788  mov     ebx, eax
0x14006378a  test    eax, eax
0x14006378c  jz      short loc_1400637F6
0x14006378e  cmp     eax, 7Ah ; 'z'
0x140063791  jnz     short loc_1400637FB
0x140063793  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006379a  mov     r8, rdi; lpMem
0x14006379d  xor     edx, edx; dwFlags
0x14006379f  call    cs:__imp_HeapFree
0x1400637a5  mov     ebx, [rsp+58h+TokenInformationLength]
0x1400637a9  mov     ecx, ebx; dwBytes
0x1400637ab  call    DllAllocSplMem
0x1400637b0  mov     rdi, rax
0x1400637b3  test    rax, rax
0x1400637b6  jz      short loc_140063755
0x1400637b8  lea     rax, [rsp+58h+TokenInformationLength]
0x1400637bd  mov     r9d, ebx; TokenInformationLength
0x1400637c0  mov     r8, rdi; TokenInformation
0x1400637c3  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1400637c8  mov     edx, 1; TokenInformationClass
0x1400637cd  mov     rcx, rbp; TokenHandle
0x1400637d0  call    cs:__imp_GetTokenInformation
0x1400637d6  test    eax, eax
0x1400637d8  jz      short loc_1400637EA
0x1400637da  xor     ebx, ebx
0x1400637dc  mov     [rsi], rdi
0x1400637df  mov     eax, ebx
0x1400637e1  add     rsp, 38h
0x1400637e5  pop     rdi
0x1400637e6  pop     rsi
0x1400637e7  pop     rbp
0x1400637e8  pop     rbx
0x1400637e9  retn
0x1400637ea  call    cs:__imp_GetLastError
0x1400637f0  mov     ebx, eax
0x1400637f2  test    eax, eax
0x1400637f4  jnz     short loc_1400637FB
0x1400637f6  mov     ebx, 5
0x1400637fb  mov     r8d, ebx
0x1400637fe  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140063805  lea     rcx, aGettokenuserfr; "GetTokenUserFromToken"
0x14006380c  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140063811  test    rdi, rdi
0x140063814  jz      short loc_1400637DF
0x140063816  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006381d  mov     r8, rdi; lpMem
0x140063820  xor     edx, edx; dwFlags
0x140063822  call    cs:__imp_HeapFree
0x140063828  jmp     short loc_1400637DF
```
