# UbpmpDecrementAppContainerRefAndDelete

- ea: `0x18003e8b0`
- end: `0x18003e9b5`
- name: `UbpmpDecrementAppContainerRefAndDelete`
- size: `261`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800060d0`
- `0x18001da20`

## callees

- `0x1800351ec`
- `0x18003e8b0`
- `0x18003e9bc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003e8e3`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003e8e3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003e98c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003e98c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003e948`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003e948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e971`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e9a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e9a2`

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
0x18003e8b0  mov     r11, rsp
0x18003e8b3  push    rbx
0x18003e8b4  sub     rsp, 30h
0x18003e8b8  mov     rbx, rcx
0x18003e8bb  mov     qword ptr [r11+18h], 0
0x18003e8c3  lea     rcx, [r11+18h]
0x18003e8c7  mov     rax, rdx
0x18003e8ca  mov     [r11-10h], rcx
0x18003e8ce  mov     r9d, 2; ImpersonationLevel
0x18003e8d4  mov     rcx, rax; hExistingToken
0x18003e8d7  mov     [r11-18h], r9d
0x18003e8db  xor     r8d, r8d; lpTokenAttributes
0x18003e8de  mov     edx, 2000000h; dwDesiredAccess
0x18003e8e3  call    cs:__imp_DuplicateTokenEx
0x18003e8ea  nop     dword ptr [rax+rax+00h]
0x18003e8ef  test    eax, eax
0x18003e8f1  jnz     short loc_18003E941
0x18003e8f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e8fa  lea     rax, WPP_GLOBAL_Control
0x18003e901  cmp     rcx, rax
0x18003e904  jz      loc_18003E998
0x18003e90a  test    byte ptr [rcx+1Ch], 1
0x18003e90e  jz      loc_18003E998
0x18003e914  call    cs:__imp_GetLastError
0x18003e91b  nop     dword ptr [rax+rax+00h]
0x18003e920  mov     edx, 57h ; 'W'
0x18003e925  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e92c  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18003e933  mov     r9d, eax
0x18003e936  mov     rcx, [rcx+10h]
0x18003e93a  call    WPP_SF_d
0x18003e93f  jmp     short loc_18003E998
0x18003e941  mov     rdx, [rsp+38h+Token]; Token
0x18003e946  xor     ecx, ecx; Thread
0x18003e948  call    cs:__imp_SetThreadToken
0x18003e94f  nop     dword ptr [rax+rax+00h]
0x18003e954  test    eax, eax
0x18003e956  jnz     short loc_18003E984
0x18003e958  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e95f  lea     rax, WPP_GLOBAL_Control
0x18003e966  cmp     rcx, rax
0x18003e969  jz      short loc_18003E998
0x18003e96b  test    byte ptr [rcx+1Ch], 1
0x18003e96f  jz      short loc_18003E998
0x18003e971  call    cs:__imp_GetLastError
0x18003e978  nop     dword ptr [rax+rax+00h]
0x18003e97d  mov     edx, 58h ; 'X'
0x18003e982  jmp     short loc_18003E925
0x18003e984  mov     rcx, rbx
0x18003e987  call    UbpmpDeleteAppContainerImpersonated
0x18003e98c  call    cs:__imp_RevertToSelf
0x18003e993  nop     dword ptr [rax+rax+00h]
0x18003e998  mov     rcx, [rsp+38h+Token]; hObject
0x18003e99d  test    rcx, rcx
0x18003e9a0  jz      short loc_18003E9AE
0x18003e9a2  call    cs:__imp_CloseHandle
0x18003e9a9  nop     dword ptr [rax+rax+00h]
0x18003e9ae  add     rsp, 30h
0x18003e9b2  pop     rbx
0x18003e9b3  retn
```
