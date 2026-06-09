# VmpApplyServiceProtection(VM_VOLUME_EXTENSION *)

- ea: `0x140010470`
- end: `0x140010726`
- name: `?VmpApplyServiceProtection@@YAJPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400046a4`

## callees

- `0x140010470`

## import_xrefs

- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x1400106b9`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x1400106b9`
- `ntoskrnl!RtlAddProcessTrustLabelAce` at `0x14001065b`
- `ntoskrnl!RtlAddProcessTrustLabelAce` at `0x14001065b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001069a`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001069a`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400106d8`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400106d8`
- `ntoskrnl!RtlLengthSid` at `0x1400104aa`
- `ntoskrnl!RtlLengthSid` at `0x1400104bb`
- `ntoskrnl!RtlLengthSid` at `0x1400104db`
- `ntoskrnl!RtlLengthSid` at `0x1400105dd`
- `ntoskrnl!RtlLengthSid` at `0x1400104aa`
- `ntoskrnl!RtlLengthSid` at `0x1400104bb`
- `ntoskrnl!RtlLengthSid` at `0x1400104db`
- `ntoskrnl!RtlLengthSid` at `0x1400105dd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140010558`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140010587`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400105b6`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140010558`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140010587`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400105b6`
- `ntoskrnl!RtlCreateAcl` at `0x140010524`
- `ntoskrnl!RtlCreateAcl` at `0x14001061f`
- `ntoskrnl!RtlCreateAcl` at `0x140010524`
- `ntoskrnl!RtlCreateAcl` at `0x14001061f`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001067b`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001067b`
- `ntoskrnl!SeExports` at `0x14001047b`
- `ntoskrnl!SeExports` at `0x1400104ca`
- `ntoskrnl!SeExports` at `0x14001053a`
- `ntoskrnl!SeExports` at `0x14001056e`
- `ntoskrnl!SeExports` at `0x14001059d`
- `ntoskrnl!SeExports` at `0x1400105cc`
- `ntoskrnl!SeExports` at `0x140010635`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400106fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001070c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400106fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001070c`
- `ntoskrnl!ExAllocatePool2` at `0x1400104f9`
- `ntoskrnl!ExAllocatePool2` at `0x1400105f9`
- `ntoskrnl!ExAllocatePool2` at `0x1400104f9`
- `ntoskrnl!ExAllocatePool2` at `0x1400105f9`

## pseudocode

```c
__int64 __fastcall VmpApplyServiceProtection(struct VM_VOLUME_EXTENSION *a1)
{
  PSID SeAliasAdminsSid; // rbx
  ULONG v3; // edi
  ULONG v4; // ebx
  struct _ACL *Pool2; // rax
  struct _ACL *v6; // rdi
  NTSTATUS Acl; // ebx
  ULONG v8; // ebx
  struct _ACL *v9; // rax
  struct _ACL *v10; // rsi
  __int128 SecurityDescriptor; // [rsp+30h] [rbp-58h] BYREF
  __int128 v13; // [rsp+40h] [rbp-48h]
  __int64 v14; // [rsp+50h] [rbp-38h]

  SecurityDescriptor = 0;
  v13 = 0;
  v14 = 0;
  SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
  v3 = RtlLengthSid(SeExports->SeUserModeDriversSid);
  LODWORD(SeAliasAdminsSid) = v3 + RtlLengthSid(SeAliasAdminsSid);
  v4 = RtlLengthSid(SeExports->SeLocalSystemSid) + 32 + (_DWORD)SeAliasAdminsSid;
  Pool2 = (struct _ACL *)ExAllocatePool2(258, v4, 538987862);
  v6 = Pool2;
  if ( Pool2 )
  {
    Acl = RtlCreateAcl(Pool2, v4, 2u);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(v6, 2u, 0x80000000, SeExports->SeLocalSystemSid);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v6, 2u, 0x80000000, SeExports->SeUserModeDriversSid);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v6, 2u, 0x80000000, SeExports->SeAliasAdminsSid);
          if ( Acl >= 0 )
          {
            v8 = RtlLengthSid(SeExports->SeProcTrustWinTcbSid) + 16;
            v9 = (struct _ACL *)ExAllocatePool2(258, v8, 538987862);
            v10 = v9;
            if ( v9 )
            {
              Acl = RtlCreateAcl(v9, v8, 2u);
              if ( Acl >= 0 )
              {
                Acl = RtlAddProcessTrustLabelAce(
                        v10,
                        2,
                        0,
                        SeExports->SeProcTrustWinTcbSid,
                        20,
                        1179785,
                        SecurityDescriptor,
                        *((_QWORD *)&SecurityDescriptor + 1),
                        v13,
                        *((_QWORD *)&v13 + 1),
                        v14);
                if ( Acl >= 0 )
                {
                  Acl = RtlCreateSecurityDescriptor(&SecurityDescriptor, 1u);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetDaclSecurityDescriptor(&SecurityDescriptor, 1u, v6, 0);
                    if ( Acl >= 0 )
                    {
                      Acl = RtlSetSaclSecurityDescriptor(&SecurityDescriptor, 1u, v10, 0);
                      if ( Acl >= 0 )
                      {
                        Acl = ObSetSecurityObjectByPointer(*(_QWORD *)a1, 132, &SecurityDescriptor);
                        *(_DWORD *)(*(_QWORD *)a1 + 52LL) |= 0x100u;
                      }
                    }
                  }
                }
              }
              ExFreePoolWithTag(v10, 0);
            }
            else
            {
              Acl = -1073741670;
            }
          }
        }
      }
    }
    ExFreePoolWithTag(v6, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x140010470  push    rbx
0x140010472  push    rbp
0x140010473  push    rsi
0x140010474  push    rdi
0x140010475  push    r14
0x140010477  sub     rsp, 60h
0x14001047b  mov     rdx, cs:__imp_SeExports
0x140010482  xorps   xmm0, xmm0
0x140010485  movups  [rsp+88h+SecurityDescriptor], xmm0
0x14001048a  xor     eax, eax
0x14001048c  mov     r14, rcx
0x14001048f  movups  [rsp+88h+var_48], xmm0
0x140010494  mov     [rsp+88h+var_38], rax
0x140010499  mov     rax, [rdx]
0x14001049c  mov     rcx, [rax+210h]; Sid
0x1400104a3  mov     rbx, [rax+110h]
0x1400104aa  call    cs:__imp_RtlLengthSid
0x1400104b1  nop     dword ptr [rax+rax+00h]
0x1400104b6  mov     rcx, rbx; Sid
0x1400104b9  mov     edi, eax
0x1400104bb  call    cs:__imp_RtlLengthSid
0x1400104c2  nop     dword ptr [rax+rax+00h]
0x1400104c7  lea     ebx, [rdi+rax]
0x1400104ca  mov     rax, cs:__imp_SeExports
0x1400104d1  mov     rcx, [rax]
0x1400104d4  mov     rcx, [rcx+108h]; Sid
0x1400104db  call    cs:__imp_RtlLengthSid
0x1400104e2  nop     dword ptr [rax+rax+00h]
0x1400104e7  mov     ecx, 102h
0x1400104ec  mov     r8d, 20204D56h
0x1400104f2  add     eax, 20h ; ' '
0x1400104f5  add     ebx, eax
0x1400104f7  mov     edx, ebx
0x1400104f9  call    cs:__imp_ExAllocatePool2
0x140010500  nop     dword ptr [rax+rax+00h]
0x140010505  mov     rdi, rax
0x140010508  test    rax, rax
0x14001050b  jnz     short loc_140010517
0x14001050d  mov     ebx, 0C000009Ah
0x140010512  jmp     loc_140010718
0x140010517  mov     ebp, 2
0x14001051c  mov     edx, ebx; AclLength
0x14001051e  mov     r8d, ebp; AclRevision
0x140010521  mov     rcx, rdi; Acl
0x140010524  call    cs:__imp_RtlCreateAcl
0x14001052b  nop     dword ptr [rax+rax+00h]
0x140010530  mov     ebx, eax
0x140010532  test    eax, eax
0x140010534  js      loc_140010707
0x14001053a  mov     rax, cs:__imp_SeExports
0x140010541  mov     esi, 80000000h
0x140010546  mov     r8d, esi; AccessMask
0x140010549  mov     edx, ebp; AceRevision
0x14001054b  mov     rcx, rdi; Acl
0x14001054e  mov     r9, [rax]
0x140010551  mov     r9, [r9+108h]; Sid
0x140010558  call    cs:__imp_RtlAddAccessAllowedAce
0x14001055f  nop     dword ptr [rax+rax+00h]
0x140010564  mov     ebx, eax
0x140010566  test    eax, eax
0x140010568  js      loc_140010707
0x14001056e  mov     rax, cs:__imp_SeExports
0x140010575  mov     r8d, esi; AccessMask
0x140010578  mov     edx, ebp; AceRevision
0x14001057a  mov     rcx, rdi; Acl
0x14001057d  mov     r9, [rax]
0x140010580  mov     r9, [r9+210h]; Sid
0x140010587  call    cs:__imp_RtlAddAccessAllowedAce
0x14001058e  nop     dword ptr [rax+rax+00h]
0x140010593  mov     ebx, eax
0x140010595  test    eax, eax
0x140010597  js      loc_140010707
0x14001059d  mov     rax, cs:__imp_SeExports
0x1400105a4  mov     r8d, esi; AccessMask
0x1400105a7  mov     edx, ebp; AceRevision
0x1400105a9  mov     rcx, rdi; Acl
0x1400105ac  mov     r9, [rax]
0x1400105af  mov     r9, [r9+110h]; Sid
0x1400105b6  call    cs:__imp_RtlAddAccessAllowedAce
0x1400105bd  nop     dword ptr [rax+rax+00h]
0x1400105c2  mov     ebx, eax
0x1400105c4  test    eax, eax
0x1400105c6  js      loc_140010707
0x1400105cc  mov     rax, cs:__imp_SeExports
0x1400105d3  mov     rcx, [rax]
0x1400105d6  mov     rcx, [rcx+218h]; Sid
0x1400105dd  call    cs:__imp_RtlLengthSid
0x1400105e4  nop     dword ptr [rax+rax+00h]
0x1400105e9  mov     ecx, 102h
0x1400105ee  mov     r8d, 20204D56h
0x1400105f4  lea     ebx, [rax+10h]
0x1400105f7  mov     edx, ebx
0x1400105f9  call    cs:__imp_ExAllocatePool2
0x140010600  nop     dword ptr [rax+rax+00h]
0x140010605  mov     rsi, rax
0x140010608  test    rax, rax
0x14001060b  jnz     short loc_140010617
0x14001060d  mov     ebx, 0C000009Ah
0x140010612  jmp     loc_140010707
0x140010617  mov     r8d, ebp; AclRevision
0x14001061a  mov     edx, ebx; AclLength
0x14001061c  mov     rcx, rsi; Acl
0x14001061f  call    cs:__imp_RtlCreateAcl
0x140010626  nop     dword ptr [rax+rax+00h]
0x14001062b  mov     ebx, eax
0x14001062d  test    eax, eax
0x14001062f  js      loc_1400106F6
0x140010635  mov     rax, cs:__imp_SeExports
0x14001063c  xor     r8d, r8d
0x14001063f  mov     [rsp+88h+var_60], 120089h
0x140010647  mov     edx, ebp
0x140010649  mov     rcx, rsi
0x14001064c  mov     [rsp+88h+var_68], 14h
0x140010651  mov     r9, [rax]
0x140010654  mov     r9, [r9+218h]
0x14001065b  call    cs:__imp_RtlAddProcessTrustLabelAce
0x140010662  nop     dword ptr [rax+rax+00h]
0x140010667  mov     ebx, eax
0x140010669  test    eax, eax
0x14001066b  js      loc_1400106F6
0x140010671  mov     edx, 1; Revision
0x140010676  lea     rcx, [rsp+88h+SecurityDescriptor]; SecurityDescriptor
0x14001067b  call    cs:__imp_RtlCreateSecurityDescriptor
0x140010682  nop     dword ptr [rax+rax+00h]
0x140010687  mov     ebx, eax
0x140010689  test    eax, eax
0x14001068b  js      short loc_1400106F6
0x14001068d  xor     r9d, r9d; DaclDefaulted
0x140010690  lea     rcx, [rsp+88h+SecurityDescriptor]; SecurityDescriptor
0x140010695  mov     r8, rdi; Dacl
0x140010698  mov     dl, 1; DaclPresent
0x14001069a  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400106a1  nop     dword ptr [rax+rax+00h]
0x1400106a6  mov     ebx, eax
0x1400106a8  test    eax, eax
0x1400106aa  js      short loc_1400106F6
0x1400106ac  xor     r9d, r9d; SaclDefaulted
0x1400106af  lea     rcx, [rsp+88h+SecurityDescriptor]; SecurityDescriptor
0x1400106b4  mov     r8, rsi; Sacl
0x1400106b7  mov     dl, 1; SaclPresent
0x1400106b9  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x1400106c0  nop     dword ptr [rax+rax+00h]
0x1400106c5  mov     ebx, eax
0x1400106c7  test    eax, eax
0x1400106c9  js      short loc_1400106F6
0x1400106cb  mov     rcx, [r14]
0x1400106ce  lea     r8, [rsp+88h+SecurityDescriptor]
0x1400106d3  mov     edx, 84h
0x1400106d8  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400106df  nop     dword ptr [rax+rax+00h]
0x1400106e4  mov     ebx, eax
0x1400106e6  mov     rax, [r14]
0x1400106e9  mov     ecx, [rax+34h]
0x1400106ec  mov     rax, [r14]
0x1400106ef  bts     ecx, 8
0x1400106f3  mov     [rax+34h], ecx
0x1400106f6  xor     edx, edx; Tag
0x1400106f8  mov     rcx, rsi; P
0x1400106fb  call    cs:__imp_ExFreePoolWithTag
0x140010702  nop     dword ptr [rax+rax+00h]
0x140010707  xor     edx, edx; Tag
0x140010709  mov     rcx, rdi; P
0x14001070c  call    cs:__imp_ExFreePoolWithTag
0x140010713  nop     dword ptr [rax+rax+00h]
0x140010718  mov     eax, ebx
0x14001071a  add     rsp, 60h
0x14001071e  pop     r14
0x140010720  pop     rdi
0x140010721  pop     rsi
0x140010722  pop     rbp
0x140010723  pop     rbx
0x140010724  retn
```
