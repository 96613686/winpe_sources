# DavFsSetTheDavCallBackContext

- ea: `0x1800113c8`
- end: `0x18001145a`
- name: `DavFsSetTheDavCallBackContext`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000ce10`

## callees

- `0x18000b89c`
- `0x1800113c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001140a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001140a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800113e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800113e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800113f9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800113f9`

## pseudocode

```c
__int64 __fastcall DavFsSetTheDavCallBackContext(__int64 a1)
{
  void **v1; // rdi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax

  v1 = (void **)(a1 + 72);
  *(_QWORD *)(a1 + 72) = -1;
  LastError = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 0, v1) )
  {
    *v1 = (void *)-1LL;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        131,
        WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
        *(unsigned int *)(a1 + 48),
        LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800113c8  mov     [rsp+arg_0], rbx
0x1800113cd  mov     [rsp+arg_8], rsi
0x1800113d2  push    rdi
0x1800113d3  sub     rsp, 30h
0x1800113d7  lea     rdi, [rcx+48h]
0x1800113db  mov     rsi, rcx
0x1800113de  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800113e5  xor     ebx, ebx
0x1800113e7  call    cs:__imp_GetCurrentThread
0x1800113ed  mov     r9, rdi; TokenHandle
0x1800113f0  lea     edx, [rbx+0Eh]; DesiredAccess
0x1800113f3  mov     rcx, rax; ThreadHandle
0x1800113f6  xor     r8d, r8d; OpenAsSelf
0x1800113f9  call    cs:__imp_OpenThreadToken
0x1800113ff  test    eax, eax
0x180011401  jnz     short loc_180011448
0x180011403  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18001140a  call    cs:__imp_GetLastError
0x180011410  mov     ebx, eax
0x180011412  mov     rcx, cs:WPP_GLOBAL_Control
0x180011419  lea     rax, WPP_GLOBAL_Control
0x180011420  cmp     rcx, rax
0x180011423  jz      short loc_180011448
0x180011425  test    byte ptr [rcx+1Ch], 1
0x180011429  jz      short loc_180011448
0x18001142b  mov     r9d, [rsi+30h]
0x18001142f  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180011436  mov     rcx, [rcx+10h]
0x18001143a  mov     edx, 83h
0x18001143f  mov     [rsp+38h+var_18], ebx
0x180011443  call    WPP_SF_Dd
0x180011448  mov     rsi, [rsp+38h+arg_8]
0x18001144d  mov     eax, ebx
0x18001144f  mov     rbx, [rsp+38h+arg_0]
0x180011454  add     rsp, 30h
0x180011458  pop     rdi
0x180011459  retn
```
