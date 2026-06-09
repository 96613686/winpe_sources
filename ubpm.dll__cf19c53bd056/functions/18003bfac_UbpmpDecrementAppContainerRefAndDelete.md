# UbpmpDecrementAppContainerRefAndDelete

- ea: `0x18003bfac`
- end: `0x18003c084`
- name: `UbpmpDecrementAppContainerRefAndDelete`
- size: `216`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800057b0`
- `0x180021060`

## callees

- `0x180032e38`
- `0x18003bfac`
- `0x18003c08c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003bfdf`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003bfdf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003c068`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003c068`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003c030`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003c030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c078`

## pseudocode

```c
int __fastcall UbpmpDecrementAppContainerRefAndDelete(__int64 a1, void *a2)
{
  PVOID *v3; // rax
  DWORD LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // rdx
  HANDLE Token; // [rsp+50h] [rbp+18h] BYREF

  Token = 0;
  if ( DuplicateTokenEx(a2, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &Token) )
  {
    if ( SetThreadToken(0, Token) )
    {
      UbpmpDeleteAppContainerImpersonated(a1, v6);
      LODWORD(v3) = RevertToSelf();
    }
    else
    {
      v3 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        v5 = 88;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v3 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      v5 = 87;
LABEL_5:
      LODWORD(v3) = WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v5,
                      WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                      LastError);
    }
  }
  if ( Token )
    LODWORD(v3) = CloseHandle(Token);
  return (int)v3;
}

```

## disassembly

```asm
0x18003bfac  mov     r11, rsp
0x18003bfaf  push    rbx
0x18003bfb0  sub     rsp, 30h
0x18003bfb4  mov     rbx, rcx
0x18003bfb7  mov     qword ptr [r11+18h], 0
0x18003bfbf  lea     rcx, [r11+18h]
0x18003bfc3  mov     rax, rdx
0x18003bfc6  mov     [r11-10h], rcx
0x18003bfca  mov     r9d, 2; ImpersonationLevel
0x18003bfd0  mov     rcx, rax; hExistingToken
0x18003bfd3  mov     [r11-18h], r9d
0x18003bfd7  xor     r8d, r8d; lpTokenAttributes
0x18003bfda  mov     edx, 2000000h; dwDesiredAccess
0x18003bfdf  call    cs:__imp_DuplicateTokenEx
0x18003bfe5  test    eax, eax
0x18003bfe7  jnz     short loc_18003C029
0x18003bfe9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bff0  lea     rax, WPP_GLOBAL_Control
0x18003bff7  cmp     rcx, rax
0x18003bffa  jz      short loc_18003C06E
0x18003bffc  test    byte ptr [rcx+1Ch], 1
0x18003c000  jz      short loc_18003C06E
0x18003c002  call    cs:__imp_GetLastError
0x18003c008  mov     edx, 57h ; 'W'
0x18003c00d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c014  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18003c01b  mov     r9d, eax
0x18003c01e  mov     rcx, [rcx+10h]
0x18003c022  call    WPP_SF_d
0x18003c027  jmp     short loc_18003C06E
0x18003c029  mov     rdx, [rsp+38h+Token]; Token
0x18003c02e  xor     ecx, ecx; Thread
0x18003c030  call    cs:__imp_SetThreadToken
0x18003c036  test    eax, eax
0x18003c038  jnz     short loc_18003C060
0x18003c03a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c041  lea     rax, WPP_GLOBAL_Control
0x18003c048  cmp     rcx, rax
0x18003c04b  jz      short loc_18003C06E
0x18003c04d  test    byte ptr [rcx+1Ch], 1
0x18003c051  jz      short loc_18003C06E
0x18003c053  call    cs:__imp_GetLastError
0x18003c059  mov     edx, 58h ; 'X'
0x18003c05e  jmp     short loc_18003C00D
0x18003c060  mov     rcx, rbx
0x18003c063  call    UbpmpDeleteAppContainerImpersonated
0x18003c068  call    cs:__imp_RevertToSelf
0x18003c06e  mov     rcx, [rsp+38h+Token]; hObject
0x18003c073  test    rcx, rcx
0x18003c076  jz      short loc_18003C07E
0x18003c078  call    cs:__imp_CloseHandle
0x18003c07e  add     rsp, 30h
0x18003c082  pop     rbx
0x18003c083  retn
```
