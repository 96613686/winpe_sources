# ValidateSecurityQOS(_RPC_SECURITY_QOS *,int,ushort *)

- ea: `0x1800079b4`
- end: `0x180007ad9`
- name: `?ValidateSecurityQOS@@YAJPEAU_RPC_SECURITY_QOS@@HPEAG@Z`
- size: `293`
- prototype: `__int64 __fastcall(struct _RPC_SECURITY_QOS *, int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007820`
- `0x180008190`

## callees

- `0x1800079b4`
- `0x1800a0078`
- `0x1800a0ebc`

## import_xrefs

- `ntdll!RtlValidSecurityDescriptor` at `0x180007a77`
- `ntdll!RtlValidSecurityDescriptor` at `0x180007a77`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180007a42`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180007a42`

## pseudocode

```c
__int64 __fastcall ValidateSecurityQOS(struct _RPC_SECURITY_QOS *a1, int a2, unsigned __int16 *a3)
{
  unsigned int Version; // ecx
  unsigned int v6; // eax
  __int64 v7; // rsi
  void *v8; // rcx
  __int64 result; // rax
  void *v10; // rcx
  void *v11; // rcx

  Version = a1->Version;
  if ( Version - 1 > 4 || a1->IdentityTracking > 1 || a1->ImpersonationType > 4 || (a1->Capabilities & 0xFFFFFFC2) != 0 )
    return 87;
  v6 = a1->Capabilities & 1;
  if ( (a1->Capabilities & 0x10) != 0 )
  {
    if ( !v6 || a2 )
      return 87;
  }
  else if ( !v6 )
  {
    goto LABEL_12;
  }
  if ( a3 && *a3 )
  {
LABEL_12:
    if ( Version <= 1 )
      return 0;
    goto LABEL_13;
  }
  if ( Version < 3 || !*(_QWORD *)&a1[2].Version )
    return 87;
LABEL_13:
  v7 = *(_QWORD *)&a1[1].IdentityTracking;
  if ( a1[1].Version != 1 )
  {
    if ( a1[1].Version || v7 )
      return 87;
    goto LABEL_16;
  }
  if ( !v7 )
    return 87;
  result = ValidateHttpCredentialsCommon(*(struct _RPC_HTTP_TRANSPORT_CREDENTIALS_W **)&a1[1].IdentityTracking);
  if ( !(_DWORD)result )
  {
    if ( !*(_QWORD *)v7 || (result = ValidateAuthIdentity(*(void **)v7), !(_DWORD)result) )
    {
      if ( (*(_BYTE *)(v7 + 12) & 2) == 0
        || (v11 = *(void **)(v7 + 40)) == 0
        || (result = ValidateAuthIdentity(v11), !(_DWORD)result) )
      {
LABEL_16:
        if ( a1->Version < 3 || (v8 = *(void **)&a1[2].Version) == 0 || !a2 && IsValidSid(v8) )
        {
          if ( a1->Version < 5 )
            return 0;
          v10 = *(void **)&a1[3].Version;
          if ( !v10 || RtlValidSecurityDescriptor(v10) )
            return 0;
        }
        return 87;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800079b4  push    rbx
0x1800079b6  push    rbp
0x1800079b7  push    rsi
0x1800079b8  push    rdi
0x1800079b9  sub     rsp, 28h
0x1800079bd  mov     rdi, rcx
0x1800079c0  mov     ebp, edx
0x1800079c2  mov     ecx, [rcx]
0x1800079c4  lea     eax, [rcx-1]
0x1800079c7  cmp     eax, 4
0x1800079ca  ja      loc_180007A67
0x1800079d0  cmp     dword ptr [rdi+8], 1
0x1800079d4  ja      loc_180007A67
0x1800079da  cmp     dword ptr [rdi+0Ch], 4
0x1800079de  ja      loc_180007A67
0x1800079e4  test    dword ptr [rdi+4], 0FFFFFFC2h
0x1800079eb  jnz     short loc_180007A67
0x1800079ed  mov     eax, [rdi+4]
0x1800079f0  xor     ebx, ebx
0x1800079f2  and     eax, 1
0x1800079f5  test    byte ptr [rdi+4], 10h
0x1800079f9  jnz     short loc_180007A63
0x1800079fb  test    eax, eax
0x1800079fd  jz      short loc_180007A17
0x1800079ff  test    r8, r8
0x180007a02  jnz     short loc_180007A11
0x180007a04  cmp     ecx, 3
0x180007a07  jb      short loc_180007A67
0x180007a09  cmp     [rdi+20h], rbx
0x180007a0d  jz      short loc_180007A67
0x180007a0f  jmp     short loc_180007A1C
0x180007a11  cmp     [r8], bx
0x180007a15  jz      short loc_180007A04
0x180007a17  cmp     ecx, 1
0x180007a1a  jbe     short loc_180007A57
0x180007a1c  cmp     dword ptr [rdi+10h], 1
0x180007a20  mov     rsi, [rdi+18h]
0x180007a24  jz      short loc_180007A92
0x180007a26  cmp     [rdi+10h], ebx
0x180007a29  jnz     short loc_180007A67
0x180007a2b  test    rsi, rsi
0x180007a2e  jnz     short loc_180007A67
0x180007a30  cmp     dword ptr [rdi], 3
0x180007a33  jb      short loc_180007A52
0x180007a35  mov     rcx, [rdi+20h]; pSid
0x180007a39  test    rcx, rcx
0x180007a3c  jz      short loc_180007A52
0x180007a3e  test    ebp, ebp
0x180007a40  jnz     short loc_180007A67
0x180007a42  call    cs:__imp_IsValidSid
0x180007a49  nop     dword ptr [rax+rax+00h]
0x180007a4e  test    eax, eax
0x180007a50  jz      short loc_180007A67
0x180007a52  cmp     dword ptr [rdi], 5
0x180007a55  jnb     short loc_180007A6E
0x180007a57  xor     eax, eax
0x180007a59  add     rsp, 28h
0x180007a5d  pop     rdi
0x180007a5e  pop     rsi
0x180007a5f  pop     rbp
0x180007a60  pop     rbx
0x180007a61  retn
0x180007a63  test    eax, eax
0x180007a65  jnz     short loc_180007A89
0x180007a67  mov     eax, 57h ; 'W'
0x180007a6c  jmp     short loc_180007A59
0x180007a6e  mov     rcx, [rdi+30h]; SecurityDescriptor
0x180007a72  test    rcx, rcx
0x180007a75  jz      short loc_180007A57
0x180007a77  call    cs:__imp_RtlValidSecurityDescriptor
0x180007a7e  nop     dword ptr [rax+rax+00h]
0x180007a83  test    al, al
0x180007a85  jz      short loc_180007A67
0x180007a87  jmp     short loc_180007A57
0x180007a89  test    ebp, ebp
0x180007a8b  jnz     short loc_180007A67
0x180007a8d  jmp     loc_1800079FF
0x180007a92  test    rsi, rsi
0x180007a95  jz      short loc_180007A67
0x180007a97  mov     rcx, rsi; struct _RPC_HTTP_TRANSPORT_CREDENTIALS_W *
0x180007a9a  call    ?ValidateHttpCredentialsCommon@@YAJPEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_W@@@Z; ValidateHttpCredentialsCommon(_RPC_HTTP_TRANSPORT_CREDENTIALS_W *)
0x180007a9f  test    eax, eax
0x180007aa1  jnz     short loc_180007A59
0x180007aa3  cmp     [rsi], rbx
0x180007aa6  jz      short loc_180007AB4
0x180007aa8  mov     rcx, [rsi]; void *
0x180007aab  call    ?ValidateAuthIdentity@@YAJPEAX@Z; ValidateAuthIdentity(void *)
0x180007ab0  test    eax, eax
0x180007ab2  jnz     short loc_180007A59
0x180007ab4  test    byte ptr [rsi+0Ch], 2
0x180007ab8  jz      loc_180007A30
0x180007abe  mov     rcx, [rsi+28h]; void *
0x180007ac2  test    rcx, rcx
0x180007ac5  jz      loc_180007A30
0x180007acb  call    ?ValidateAuthIdentity@@YAJPEAX@Z; ValidateAuthIdentity(void *)
0x180007ad0  test    eax, eax
0x180007ad2  jnz     short loc_180007A59
0x180007ad4  jmp     loc_180007A30
```
