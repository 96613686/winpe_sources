# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x18002d69c`
- end: `0x18002d752`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `182`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, void *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a0e8`

## callees

- `0x18000b3c0`
- `0x18002d69c`
- `0x18002d758`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d748`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d748`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d700`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d700`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::IsProcessAppContainer(CallerIdentity *this, bool *a2, void **a3)
{
  signed int v4; // eax
  signed int Error; // ebx
  char *v6; // rcx
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  v4 = ARI::ProcessToken::SysAppId::OpenTokenForProcess(this, &TokenHandle, a3);
  Error = v4;
  if ( v4 > 0 )
    Error = (unsigned __int16)v4 | 0x80070000;
  if ( Error >= 0 )
  {
    ReturnLength = 0;
    TokenInformation = 0;
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      Error = 0;
LABEL_6:
      *a2 = TokenInformation != 0;
      goto LABEL_7;
    }
    Error = ResultFromKnownLastError();
    if ( Error >= 0 )
      goto LABEL_6;
  }
LABEL_7:
  v6 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002d69c  mov     [rsp+arg_0], rbx
0x18002d6a1  push    rdi
0x18002d6a2  sub     rsp, 30h
0x18002d6a6  mov     rdi, rdx
0x18002d6a9  mov     byte ptr [rdx], 0
0x18002d6ac  mov     [rsp+38h+TokenHandle], 0
0x18002d6b5  lea     rdx, [rsp+38h+TokenHandle]; TokenHandle
0x18002d6ba  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x18002d6bf  mov     ebx, eax
0x18002d6c1  test    eax, eax
0x18002d6c3  jle     short loc_18002D6CE
0x18002d6c5  movzx   ebx, ax
0x18002d6c8  or      ebx, 80070000h
0x18002d6ce  test    ebx, ebx
0x18002d6d0  js      short loc_18002D716
0x18002d6d2  mov     [rsp+38h+arg_10], 0
0x18002d6da  mov     [rsp+38h+TokenInformation], 0
0x18002d6e2  lea     rax, [rsp+38h+arg_10]
0x18002d6e7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002d6ec  mov     r9d, 4; TokenInformationLength
0x18002d6f2  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18002d6f7  lea     edx, [r9+19h]; TokenInformationClass
0x18002d6fb  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18002d700  call    cs:__imp_GetTokenInformation
0x18002d706  test    eax, eax
0x18002d708  jz      short loc_18002D73B
0x18002d70a  xor     ebx, ebx
0x18002d70c  cmp     [rsp+38h+TokenInformation], 0
0x18002d711  setnz   al
0x18002d714  mov     [rdi], al
0x18002d716  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18002d71b  mov     [rsp+38h+TokenHandle], 0
0x18002d724  lea     rdx, [rcx-1]
0x18002d728  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002d72c  jbe     short loc_18002D748
0x18002d72e  mov     eax, ebx
0x18002d730  mov     rbx, [rsp+38h+arg_0]
0x18002d735  add     rsp, 30h
0x18002d739  pop     rdi
0x18002d73a  retn
0x18002d73b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002d740  mov     ebx, eax
0x18002d742  test    eax, eax
0x18002d744  jns     short loc_18002D70C
0x18002d746  jmp     short loc_18002D716
0x18002d748  call    cs:__imp_CloseHandle
0x18002d74e  nop
0x18002d74f  jmp     short loc_18002D72E
```
