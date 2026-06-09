# CSGetAccountRights

- ea: `0x180011ca4`
- end: `0x180011e77`
- name: `CSGetAccountRights`
- size: `467`
- prototype: `__int64 __fastcall(PSID AccountSid)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800063b0`
- `0x18000ed10`
- `0x18001645c`

## callees

- `0x18000b290`
- `0x180011ca4`
- `0x180013490`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180011da3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180011da3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011dc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011dc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d51`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180011cfb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180011cfb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180011e25`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180011e25`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaEnumerateAccountRights` at `0x180011d23`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaEnumerateAccountRights` at `0x180011d23`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180011dda`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180011dda`

## pseudocode

```c
__int64 __fastcall CSGetAccountRights(PSID AccountSid, _DWORD *a2)
{
  NTSTATUS v4; // ebx
  __int64 v5; // r8
  int v6; // ebx
  NTSTATUS v7; // eax
  __int64 v8; // r8
  ULONG i; // r14d
  struct _UNICODE_STRING *v10; // rbx
  unsigned int v11; // esi
  unsigned __int16 *v12; // rax
  WCHAR *v13; // r15
  unsigned int j; // esi
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  ULONG CountOfRights; // [rsp+A0h] [rbp+40h] BYREF
  PLSA_UNICODE_STRING UserRights; // [rsp+B0h] [rbp+50h] BYREF
  PVOID PolicyHandle; // [rsp+B8h] [rbp+58h] BYREF

  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( AccountSid && a2 )
  {
    *a2 = 0;
    v4 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle);
    if ( v4 < 0 )
    {
      v6 = v4 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF__sid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, v5, AccountSid, v6);
    }
    else
    {
      v6 = 0;
      UserRights = 0;
      CountOfRights = 0;
      v7 = LsaEnumerateAccountRights(PolicyHandle, AccountSid, &UserRights, &CountOfRights);
      if ( v7 < 0 )
      {
        if ( v7 == -1073741772 )
        {
          *a2 = 0;
        }
        else
        {
          v6 = v7 | 0x10000000;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF__sid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, v8, AccountSid, v6);
        }
      }
      else
      {
        for ( i = 0; i < CountOfRights; ++i )
        {
          v10 = (struct _UNICODE_STRING *)&UserRights[i];
          v11 = v10->Length + 2;
          v12 = (unsigned __int16 *)CoTaskMemAlloc(v11);
          v13 = v12;
          if ( !v12 )
          {
            v6 = -2147024882;
            break;
          }
          v6 = CopyUstrToPstr(v10, v12, v11);
          if ( v6 >= 0 )
          {
            for ( j = 0; j < 0xA; ++j )
            {
              if ( CompareStringW(0x7Fu, 1u, v13, -1, (&off_180018840)[2 * (int)j], -1) == 2 )
              {
                *a2 |= *((_DWORD *)&off_180018840 + 4 * (int)j + 2);
                break;
              }
            }
          }
          CoTaskMemFree(v13);
        }
        LsaFreeMemory(UserRights);
      }
      LsaClose(PolicyHandle);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180011ca4  push    rbp
0x180011ca6  push    rbx
0x180011ca7  push    rsi
0x180011ca8  push    rdi
0x180011ca9  push    r12
0x180011cab  push    r14
0x180011cad  push    r15
0x180011caf  mov     rbp, rsp
0x180011cb2  sub     rsp, 60h
0x180011cb6  mov     [rbp+PolicyHandle], 0
0x180011cbe  xorps   xmm0, xmm0
0x180011cc1  mov     rdi, rdx
0x180011cc4  mov     rsi, rcx
0x180011cc7  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180011ccb  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180011ccf  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180011cd3  test    rcx, rcx
0x180011cd6  jz      loc_180011E61
0x180011cdc  test    rdx, rdx
0x180011cdf  jz      loc_180011E61
0x180011ce5  mov     dword ptr [rdx], 0
0x180011ceb  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180011cef  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180011cf3  mov     r8d, 800h; DesiredAccess
0x180011cf9  xor     ecx, ecx; SystemName
0x180011cfb  call    cs:__imp_LsaOpenPolicy
0x180011d01  mov     ebx, eax
0x180011d03  test    eax, eax
0x180011d05  js      loc_180011E2D
0x180011d0b  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180011d0f  lea     r9, [rbp+CountOfRights]; CountOfRights
0x180011d13  xor     ebx, ebx
0x180011d15  lea     r8, [rbp+UserRights]; UserRights
0x180011d19  mov     rdx, rsi; AccountSid
0x180011d1c  mov     [rbp+UserRights], rbx
0x180011d20  mov     [rbp+CountOfRights], ebx
0x180011d23  call    cs:__imp_LsaEnumerateAccountRights
0x180011d29  test    eax, eax
0x180011d2b  js      loc_180011DE2
0x180011d31  xor     r14d, r14d
0x180011d34  cmp     r14d, [rbp+CountOfRights]
0x180011d38  jnb     loc_180011DD6
0x180011d3e  mov     ebx, r14d
0x180011d41  shl     rbx, 4
0x180011d45  add     rbx, [rbp+UserRights]
0x180011d49  movzx   esi, word ptr [rbx]
0x180011d4c  add     esi, 2
0x180011d4f  mov     ecx, esi; cb
0x180011d51  call    cs:__imp_CoTaskMemAlloc
0x180011d57  mov     r15, rax
0x180011d5a  test    rax, rax
0x180011d5d  jz      short loc_180011DD1
0x180011d5f  mov     r8d, esi; unsigned int
0x180011d62  mov     rdx, rax; unsigned __int16 *
0x180011d65  mov     rcx, rbx; struct _UNICODE_STRING *
0x180011d68  call    ?CopyUstrToPstr@@YAJQEAU_UNICODE_STRING@@PEAGK@Z; CopyUstrToPstr(_UNICODE_STRING * const,ushort *,ulong)
0x180011d6d  mov     ebx, eax
0x180011d6f  test    eax, eax
0x180011d71  js      short loc_180011DC0
0x180011d73  xor     esi, esi
0x180011d75  cmp     esi, 0Ah
0x180011d78  jnb     short loc_180011DC0
0x180011d7a  or      ecx, 0FFFFFFFFh
0x180011d7d  movsxd  r12, esi
0x180011d80  mov     [rsp+60h+cchCount2], ecx; cchCount2
0x180011d84  lea     rax, off_180018840; "SeInteractiveLogonRight"
0x180011d8b  mov     r9d, ecx; cchCount1
0x180011d8e  add     r12, r12
0x180011d91  mov     r8, r15; lpString1
0x180011d94  lea     edx, [rcx+2]; dwCmpFlags
0x180011d97  lea     ecx, [rdx+7Eh]; Locale
0x180011d9a  mov     rax, [rax+r12*8]
0x180011d9e  mov     [rsp+60h+lpString2], rax; lpString2
0x180011da3  call    cs:__imp_CompareStringW
0x180011da9  cmp     eax, 2
0x180011dac  jz      short loc_180011DB2
0x180011dae  inc     esi
0x180011db0  jmp     short loc_180011D75
0x180011db2  lea     rax, off_180018840; "SeInteractiveLogonRight"
0x180011db9  mov     eax, [rax+r12*8+8]
0x180011dbe  or      [rdi], eax
0x180011dc0  mov     rcx, r15; pv
0x180011dc3  call    cs:__imp_CoTaskMemFree
0x180011dc9  inc     r14d
0x180011dcc  jmp     loc_180011D34
0x180011dd1  mov     ebx, 8007000Eh
0x180011dd6  mov     rcx, [rbp+UserRights]; Buffer
0x180011dda  call    cs:__imp_LsaFreeMemory
0x180011de0  jmp     short loc_180011E21
0x180011de2  cmp     eax, 0C0000034h
0x180011de7  jnz     short loc_180011DED
0x180011de9  mov     [rdi], ebx
0x180011deb  jmp     short loc_180011E21
0x180011ded  mov     ebx, eax
0x180011def  bts     ebx, 1Ch
0x180011df3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011dfa  lea     rax, WPP_GLOBAL_Control
0x180011e01  cmp     rcx, rax
0x180011e04  jz      short loc_180011E21
0x180011e06  test    byte ptr [rcx+1Ch], 2
0x180011e0a  jz      short loc_180011E21
0x180011e0c  mov     rcx, [rcx+10h]
0x180011e10  mov     edx, 2Eh ; '.'
0x180011e15  mov     r9, rsi
0x180011e18  mov     dword ptr [rsp+60h+lpString2], ebx
0x180011e1c  call    WPP_SF__sid_D
0x180011e21  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180011e25  call    cs:__imp_LsaClose
0x180011e2b  jmp     short loc_180011E66
0x180011e2d  bts     ebx, 1Ch
0x180011e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e38  lea     rax, WPP_GLOBAL_Control
0x180011e3f  cmp     rcx, rax
0x180011e42  jz      short loc_180011E66
0x180011e44  test    byte ptr [rcx+1Ch], 2
0x180011e48  jz      short loc_180011E66
0x180011e4a  mov     rcx, [rcx+10h]
0x180011e4e  mov     edx, 2Fh ; '/'
0x180011e53  mov     r9, rsi
0x180011e56  mov     dword ptr [rsp+60h+lpString2], ebx
0x180011e5a  call    WPP_SF__sid_D
0x180011e5f  jmp     short loc_180011E66
0x180011e61  mov     ebx, 80004003h
0x180011e66  mov     eax, ebx
0x180011e68  add     rsp, 60h
0x180011e6c  pop     r15
0x180011e6e  pop     r14
0x180011e70  pop     r12
0x180011e72  pop     rdi
0x180011e73  pop     rsi
0x180011e74  pop     rbx
0x180011e75  pop     rbp
0x180011e76  retn
```
