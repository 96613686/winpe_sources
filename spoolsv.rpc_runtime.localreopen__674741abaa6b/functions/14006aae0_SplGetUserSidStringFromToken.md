# SplGetUserSidStringFromToken

- ea: `0x14006aae0`
- end: `0x14006abdb`
- name: `SplGetUserSidStringFromToken`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000fd70`
- `0x1400633d0`

## callees

- `0x140015378`
- `0x1400166d0`
- `0x140069884`
- `0x14006aae0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006ab67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006ab67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ab30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ab30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14006ab4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14006ab4f`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14006ab20`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14006ab20`

## string_xrefs

- `0x14006ab81`: `SplGetUserSidStringFromToken`

## pseudocode

```c
__int64 __fastcall SplGetUserSidStringFromToken(void *a1, unsigned __int16 *a2, unsigned int a3, unsigned int *a4)
{
  unsigned __int64 v5; // rsi
  DWORD TokenUserFromToken; // eax
  void *v8; // rdi
  DWORD LastError; // ebx
  unsigned __int16 *v10; // rcx
  __int64 v12; // rax
  unsigned int v13; // eax
  LPWSTR StringSid; // [rsp+20h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-40h] BYREF

  v5 = a3;
  lpMem = 0;
  StringSid = 0;
  TokenUserFromToken = GetTokenUserFromToken(a1, (struct _TOKEN_USER **)&lpMem);
  v8 = lpMem;
  LastError = TokenUserFromToken;
  if ( TokenUserFromToken )
    goto LABEL_5;
  if ( !ConvertSidToStringSidW(*(PSID *)lpMem, &StringSid) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 8;
    goto LABEL_5;
  }
  v10 = StringSid;
  v12 = -1;
  do
    ++v12;
  while ( StringSid[v12] );
  v13 = 2 * v12 + 2;
  *a4 = v13;
  if ( v13 <= (unsigned int)v5 )
  {
    StringCbCopyW(a2, v5, v10);
LABEL_5:
    v10 = StringSid;
    goto LABEL_6;
  }
  LastError = 122;
LABEL_6:
  if ( v10 )
    LocalFree(v10);
  HeapFree(g_hSpoolssHeap, 0, v8);
  if ( LastError )
    PrvSpoolssTelemetry::WriteDbgTraceError("SplGetUserSidStringFromToken", L"Failed.  Error %d.", LastError);
  return LastError;
}

```

## disassembly

```asm
0x14006aae0  push    rbx
0x14006aae2  push    rbp
0x14006aae3  push    rsi
0x14006aae4  push    rdi
0x14006aae5  push    r14
0x14006aae7  push    r15
0x14006aae9  sub     rsp, 38h
0x14006aaed  mov     rbp, rdx
0x14006aaf0  mov     esi, r8d
0x14006aaf3  xor     r15d, r15d
0x14006aaf6  lea     rdx, [rsp+68h+lpMem]; struct _TOKEN_USER **
0x14006aafb  mov     [rsp+68h+lpMem], r15
0x14006ab00  mov     r14, r9
0x14006ab03  mov     [rsp+68h+StringSid], r15
0x14006ab08  call    ?GetTokenUserFromToken@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenUserFromToken(void *,_TOKEN_USER * *)
0x14006ab0d  mov     rdi, [rsp+68h+lpMem]
0x14006ab12  mov     ebx, eax
0x14006ab14  test    eax, eax
0x14006ab16  jnz     short loc_14006AB45
0x14006ab18  mov     rcx, [rdi]; Sid
0x14006ab1b  lea     rdx, [rsp+68h+StringSid]; StringSid
0x14006ab20  call    cs:__imp_ConvertSidToStringSidW
0x14006ab27  nop     dword ptr [rax+rax+00h]
0x14006ab2c  test    eax, eax
0x14006ab2e  jnz     short loc_14006AB9D
0x14006ab30  call    cs:__imp_GetLastError
0x14006ab37  nop     dword ptr [rax+rax+00h]
0x14006ab3c  mov     ebx, eax
0x14006ab3e  test    eax, eax
0x14006ab40  jnz     short loc_14006AB45
0x14006ab42  lea     ebx, [rax+8]
0x14006ab45  mov     rcx, [rsp+68h+StringSid]; hMem
0x14006ab4a  test    rcx, rcx
0x14006ab4d  jz      short loc_14006AB5B
0x14006ab4f  call    cs:__imp_LocalFree
0x14006ab56  nop     dword ptr [rax+rax+00h]
0x14006ab5b  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006ab62  mov     r8, rdi; lpMem
0x14006ab65  xor     edx, edx; dwFlags
0x14006ab67  call    cs:__imp_HeapFree
0x14006ab6e  nop     dword ptr [rax+rax+00h]
0x14006ab73  test    ebx, ebx
0x14006ab75  jz      short loc_14006AB8D
0x14006ab77  mov     r8d, ebx
0x14006ab7a  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x14006ab81  lea     rcx, aSplgetusersids; "SplGetUserSidStringFromToken"
0x14006ab88  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006ab8d  mov     eax, ebx
0x14006ab8f  add     rsp, 38h
0x14006ab93  pop     r15
0x14006ab95  pop     r14
0x14006ab97  pop     rdi
0x14006ab98  pop     rsi
0x14006ab99  pop     rbp
0x14006ab9a  pop     rbx
0x14006ab9b  retn
0x14006ab9d  mov     rcx, [rsp+68h+StringSid]
0x14006aba2  or      rax, 0FFFFFFFFFFFFFFFFh
0x14006aba6  inc     rax
0x14006aba9  cmp     [rcx+rax*2], r15w
0x14006abae  jnz     short loc_14006ABA6
0x14006abb0  lea     eax, ds:2[rax*2]
0x14006abb7  mov     [r14], eax
0x14006abba  cmp     eax, esi
0x14006abbc  ja      short loc_14006ABD1
0x14006abbe  mov     r8, rcx; unsigned __int16 *
0x14006abc1  mov     rdx, rsi; unsigned __int64
0x14006abc4  mov     rcx, rbp; unsigned __int16 *
0x14006abc7  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14006abcc  jmp     loc_14006AB45
0x14006abd1  mov     ebx, 7Ah ; 'z'
0x14006abd6  jmp     loc_14006AB4A
```
