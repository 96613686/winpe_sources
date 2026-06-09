# UbpmUtilsRemoveProcessPrivileges(void *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 *)

- ea: `0x180028cf8`
- end: `0x180028e28`
- name: `?UbpmUtilsRemoveProcessPrivileges@@YAKPEAX_K11PEA_K@Z`
- size: `304`
- prototype: `unsigned int __usercall@<eax>(HANDLE TokenHandle@<rcx>, unsigned __int64@<rdx>, unsigned __int64@<r8>, unsigned __int64@<r9>, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019480`

## callees

- `0x180019d90`
- `0x180028cf8`
- `0x180028e30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180028dce`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180028dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e1b`

## pseudocode

```c
__int64 __fastcall UbpmUtilsRemoveProcessPrivileges(
        HANDLE TokenHandle,
        __int64 a2,
        unsigned __int64 *a3,
        __int64 a4,
        unsigned __int64 *a5)
{
  unsigned __int64 *v5; // r14
  DWORD ProcessPrivileges; // eax
  PTOKEN_PRIVILEGES v11; // rbx
  DWORD LastError; // edi
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r11
  DWORD LowPart; // ecx
  __int64 v18; // rdx
  __int64 v19; // rcx
  PTOKEN_PRIVILEGES NewState; // [rsp+68h] [rbp+10h] BYREF

  v5 = a5;
  NewState = 0;
  *a5 = 0;
  ProcessPrivileges = UbpmUtilsGetProcessPrivileges(TokenHandle, &NewState, a3);
  v11 = NewState;
  LastError = ProcessPrivileges;
  if ( !ProcessPrivileges )
  {
    v14 = 0;
    v15 = 0;
    v16 = a2;
    if ( NewState->PrivilegeCount )
    {
      do
      {
        LowPart = v11->Privileges[v15].Luid.LowPart;
        v18 = 1LL << LowPart;
        if ( v16 && (v18 & a2) == 0 || (v18 & (unsigned __int64)a3) != 0 )
        {
          if ( LowPart != 23 || v11->Privileges[v15].Luid.HighPart )
          {
            v19 = v14;
            v14 = (unsigned int)(v14 + 1);
            v11->Privileges[v19].Attributes = 4;
            v11->Privileges[v19].Luid = v11->Privileges[v15].Luid;
          }
          else
          {
            *v5 |= v18;
          }
        }
        else
        {
          *v5 |= v18;
          a2 &= ~v18;
          a4 &= ~v18;
        }
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (unsigned int)v15 < v11->PrivilegeCount );
    }
    if ( a2 || a4 )
    {
      LastError = 87;
    }
    else if ( (_DWORD)v14 && (v11->PrivilegeCount = v14, !AdjustTokenPrivileges(TokenHandle, 0, v11, 0, 0, 0)) )
    {
      LastError = GetLastError();
    }
    else
    {
      LastError = 0;
    }
  }
  UBPM_MIDL_user_free(v11);
  return LastError;
}

```

## disassembly

```asm
0x180028cf8  mov     rax, rsp
0x180028cfb  mov     [rax+8], rbx
0x180028cff  mov     [rax+18h], rbp
0x180028d03  push    rsi
0x180028d04  push    rdi
0x180028d05  push    r12
0x180028d07  push    r14
0x180028d09  push    r15
0x180028d0b  sub     rsp, 30h
0x180028d0f  mov     r14, [rsp+58h+arg_20]
0x180028d17  mov     rsi, rdx
0x180028d1a  lea     rdx, [rax+10h]; struct _TOKEN_PRIVILEGES **
0x180028d1e  mov     qword ptr [rax+10h], 0
0x180028d26  mov     rbp, r9
0x180028d29  mov     r12, r8
0x180028d2c  mov     r15, rcx
0x180028d2f  mov     qword ptr [r14], 0
0x180028d36  call    ?UbpmUtilsGetProcessPrivileges@@YAKPEAXPEAPEAU_TOKEN_PRIVILEGES@@PEA_K@Z; UbpmUtilsGetProcessPrivileges(void *,_TOKEN_PRIVILEGES * *,unsigned __int64 *)
0x180028d3b  mov     rbx, [rsp+58h+NewState]
0x180028d40  mov     edi, eax
0x180028d42  test    eax, eax
0x180028d44  jz      short loc_180028D67
0x180028d46  mov     rcx, rbx
0x180028d49  call    UBPM_MIDL_user_free
0x180028d4e  mov     rbx, [rsp+58h+arg_0]
0x180028d53  mov     eax, edi
0x180028d55  mov     rbp, [rsp+58h+arg_10]
0x180028d5a  add     rsp, 30h
0x180028d5e  pop     r15
0x180028d60  pop     r14
0x180028d62  pop     r12
0x180028d64  pop     rdi
0x180028d65  pop     rsi
0x180028d66  retn
0x180028d67  xor     r8d, r8d
0x180028d6a  xor     r9d, r9d
0x180028d6d  mov     r11, rsi
0x180028d70  cmp     [rbx], r8d
0x180028d73  jbe     short loc_180028DA7
0x180028d75  lea     r10, [r9+r9*2]
0x180028d79  mov     edx, 1
0x180028d7e  mov     ecx, [rbx+r10*4+4]
0x180028d83  shl     rdx, cl
0x180028d86  test    r11, r11
0x180028d89  jnz     short loc_180028DDF
0x180028d8b  test    r12, rdx
0x180028d8e  jnz     short loc_180028DE4
0x180028d90  or      [r14], rdx
0x180028d93  mov     rax, rdx
0x180028d96  not     rax
0x180028d99  and     rsi, rax
0x180028d9c  and     rbp, rax
0x180028d9f  inc     r9d
0x180028da2  cmp     r9d, [rbx]
0x180028da5  jb      short loc_180028D75
0x180028da7  test    rsi, rsi
0x180028daa  jnz     short loc_180028E04
0x180028dac  test    rbp, rbp
0x180028daf  jnz     short loc_180028E04
0x180028db1  test    r8d, r8d
0x180028db4  jz      short loc_180028DD8
0x180028db6  mov     [rbx], r8d
0x180028db9  xor     r9d, r9d; BufferLength
0x180028dbc  mov     r8, rbx; NewState
0x180028dbf  mov     [rsp+58h+ReturnLength], rbp; ReturnLength
0x180028dc4  xor     edx, edx; DisableAllPrivileges
0x180028dc6  mov     [rsp+58h+PreviousState], rbp; PreviousState
0x180028dcb  mov     rcx, r15; TokenHandle
0x180028dce  call    cs:__imp_AdjustTokenPrivileges
0x180028dd4  test    eax, eax
0x180028dd6  jz      short loc_180028E1B
0x180028dd8  xor     edi, edi
0x180028dda  jmp     loc_180028D46
0x180028ddf  test    rsi, rdx
0x180028de2  jnz     short loc_180028D8B
0x180028de4  cmp     ecx, 17h
0x180028de7  jz      short loc_180028E0E
0x180028de9  lea     rcx, [r8+r8*2]
0x180028ded  inc     r8d
0x180028df0  mov     dword ptr [rbx+rcx*4+0Ch], 4
0x180028df8  mov     rax, [rbx+r10*4+4]
0x180028dfd  mov     [rbx+rcx*4+4], rax
0x180028e02  jmp     short loc_180028D9F
0x180028e04  mov     edi, 57h ; 'W'
0x180028e09  jmp     loc_180028D46
0x180028e0e  cmp     dword ptr [rbx+r10*4+8], 0
0x180028e14  jnz     short loc_180028DE9
0x180028e16  or      [r14], rdx
0x180028e19  jmp     short loc_180028D9F
0x180028e1b  call    cs:__imp_GetLastError
0x180028e21  mov     edi, eax
0x180028e23  jmp     loc_180028D46
```
