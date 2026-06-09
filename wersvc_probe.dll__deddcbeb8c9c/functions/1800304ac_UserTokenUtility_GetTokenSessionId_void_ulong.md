# UserTokenUtility::GetTokenSessionId(void *,ulong *)

- ea: `0x1800304ac`
- end: `0x180030589`
- name: `?GetTokenSessionId@UserTokenUtility@@SAJPEAXPEAK@Z`
- size: `221`
- prototype: `__int64 __fastcall(void *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180027460`
- `0x180030590`

## callees

- `0x180011ef8`
- `0x1800304ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304fa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800304f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800304f0`

## pseudocode

```c
__int64 __fastcall UserTokenUtility::GetTokenSessionId(void *a1, unsigned int *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  DWORD ReturnLength; // [rsp+40h] [rbp+8h] BYREF
  unsigned int TokenInformation; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = 0;
  ReturnLength = 0;
  if ( !a1 || !a2 )
    return (unsigned int)-2147024809;
  if ( GetTokenInformation(a1, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
  {
    v7 = ReturnLength;
    if ( ReturnLength == 4 )
    {
      *a2 = TokenInformation;
      return 0;
    }
    v4 = -2147467259;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 11;
      goto LABEL_9;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 10;
      v7 = v4;
LABEL_9:
      WPP_SF_d(v5[2], v6, &WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids, v7);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800304ac  push    rbx
0x1800304ae  sub     rsp, 30h
0x1800304b2  mov     [rsp+38h+TokenInformation], 0
0x1800304ba  mov     rbx, rdx
0x1800304bd  mov     [rsp+38h+arg_0], 0
0x1800304c5  test    rcx, rcx
0x1800304c8  jz      loc_18003057C
0x1800304ce  test    rdx, rdx
0x1800304d1  jz      loc_18003057C
0x1800304d7  mov     r9d, 4; TokenInformationLength
0x1800304dd  lea     rax, [rsp+38h+arg_0]
0x1800304e2  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800304e7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800304ec  lea     edx, [r9+8]; TokenInformationClass
0x1800304f0  call    cs:__imp_GetTokenInformation
0x1800304f6  test    eax, eax
0x1800304f8  jnz     short loc_180030542
0x1800304fa  call    cs:__imp_GetLastError
0x180030500  mov     ebx, eax
0x180030502  test    eax, eax
0x180030504  jle     short loc_18003050F
0x180030506  movzx   ebx, ax
0x180030509  or      ebx, 80070000h
0x18003050f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030516  lea     rax, WPP_GLOBAL_Control
0x18003051d  cmp     rcx, rax
0x180030520  jz      short loc_180030581
0x180030522  test    byte ptr [rcx+1Ch], 1
0x180030526  jz      short loc_180030581
0x180030528  mov     edx, 0Ah
0x18003052d  mov     r9d, ebx
0x180030530  mov     rcx, [rcx+10h]
0x180030534  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x18003053b  call    WPP_SF_d
0x180030540  jmp     short loc_180030581
0x180030542  mov     r9d, [rsp+38h+arg_0]
0x180030547  cmp     r9d, 4
0x18003054b  jz      short loc_180030572
0x18003054d  mov     ebx, 80004005h
0x180030552  mov     rcx, cs:WPP_GLOBAL_Control
0x180030559  lea     rax, WPP_GLOBAL_Control
0x180030560  cmp     rcx, rax
0x180030563  jz      short loc_180030581
0x180030565  test    byte ptr [rcx+1Ch], 1
0x180030569  jz      short loc_180030581
0x18003056b  mov     edx, 0Bh
0x180030570  jmp     short loc_180030530
0x180030572  mov     eax, [rsp+38h+TokenInformation]
0x180030576  mov     [rbx], eax
0x180030578  xor     ebx, ebx
0x18003057a  jmp     short loc_180030581
0x18003057c  mov     ebx, 80070057h
0x180030581  mov     eax, ebx
0x180030583  add     rsp, 30h
0x180030587  pop     rbx
0x180030588  retn
```
