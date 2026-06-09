# WlanQueryCreateAllUserProfileRestricted

- ea: `0x18002eac0`
- end: `0x18002edfb`
- name: `WlanQueryCreateAllUserProfileRestricted`
- size: `827`
- prototype: `__int64 __fastcall(int *, PWLAN_OPCODE_VALUE_TYPE pValueType)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005330`
- `0x180005610`
- `0x180005d50`
- `0x1800063a0`
- `0x1800063e0`
- `0x180006934`
- `0x18000bb70`
- `0x18001a5bc`
- `0x18002e78c`
- `0x18002eac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ecf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ecf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ed6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ed6d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002ece8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002ece8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002ec1c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002ec1c`

## pseudocode

```c
__int64 __fastcall WlanQueryCreateAllUserProfileRestricted(int *a1, PWLAN_OPCODE_VALUE_TYPE pValueType)
{
  void *v2; // rdi
  void *v3; // rsi
  union DOT11_OUI_HEADER *v6; // rcx
  DWORD SecuritySettings; // ebx
  DWORD LastError; // eax
  PVOID Memory; // rax
  DWORD v10; // eax
  DWORD v11; // eax
  void *phClientHandle; // [rsp+30h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-18h] BYREF
  LPWSTR pstrCurrentSDDL; // [rsp+40h] [rbp-10h] BYREF
  size_t Size; // [rsp+80h] [rbp+30h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+90h] [rbp+40h] BYREF
  DWORD pdwGrantedAccess; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  LODWORD(Size) = 0;
  phClientHandle = 0;
  v3 = 0;
  pdwNegotiatedVersion = 0;
  pdwGrantedAccess = 0;
  pstrCurrentSDDL = 0;
  SecurityDescriptor = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a1 && !pValueType )
  {
    if ( v6 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control && *((_BYTE *)v6 + 105) && (*((_BYTE *)v6 + 108) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)v6 + 12), 24, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    SecuritySettings = 87;
    goto LABEL_41;
  }
  SecuritySettings = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( SecuritySettings )
  {
    v2 = phClientHandle;
    goto LABEL_40;
  }
  if ( pdwNegotiatedVersion != 2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        25,
        WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids,
        pdwNegotiatedVersion);
      v6 = WPP_GLOBAL_Control;
    }
    v2 = phClientHandle;
    SecuritySettings = 1638;
    goto LABEL_41;
  }
  v2 = phClientHandle;
  SecuritySettings = WlanGetSecuritySettings(
                       phClientHandle,
                       wlan_secure_add_new_all_user_profiles,
                       pValueType,
                       &pstrCurrentSDDL,
                       &pdwGrantedAccess);
  if ( SecuritySettings )
  {
LABEL_40:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(pstrCurrentSDDL, 1u, &SecurityDescriptor, 0) )
    goto LABEL_26;
  LastError = GetLastError();
  SecuritySettings = LastError;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 26, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids, LastError);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !SecuritySettings )
  {
LABEL_26:
    LODWORD(Size) = 68;
    Memory = WlanAllocateMemory(0x44u);
    v3 = Memory;
    if ( Memory )
    {
      memset_0(Memory, 0, (unsigned int)Size);
      if ( CreateWellKnownSid(WinBuiltinUsersSid, 0, v3, (DWORD *)&Size) )
        goto LABEL_38;
      v10 = GetLastError();
      SecuritySettings = v10;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 28, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids, v10);
        v6 = WPP_GLOBAL_Control;
      }
      if ( !SecuritySettings )
      {
LABEL_38:
        v11 = ValidateSidRights(v3, SecurityDescriptor, a1);
        v6 = WPP_GLOBAL_Control;
        SecuritySettings = v11;
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      SecuritySettings = 14;
    }
  }
LABEL_41:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    FreeWLMem(v3);
    v6 = WPP_GLOBAL_Control;
  }
  if ( pstrCurrentSDDL )
  {
    FreeWLMem(pstrCurrentSDDL);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v2 )
  {
    WlanCloseHandle(v2, 0);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v6 + 105) >= 4u
    && (*((_BYTE *)v6 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v6 + 12), 29, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids, SecuritySettings);
  }
  return SecuritySettings;
}

```

## disassembly

```asm
0x18002eac0  mov     [rsp-28h+arg_8], rbx
0x18002eac5  push    rbp
0x18002eac6  push    rsi
0x18002eac7  push    rdi
0x18002eac8  push    r14
0x18002eaca  push    r15
0x18002eacc  mov     rbp, rsp
0x18002eacf  sub     rsp, 50h
0x18002ead3  xor     edi, edi
0x18002ead5  mov     dword ptr [rbp+Size], 0
0x18002eadc  mov     [rbp+phClientHandle], rdi
0x18002eae0  xor     esi, esi
0x18002eae2  mov     [rbp+pdwNegotiatedVersion], edi
0x18002eae5  mov     r14, rdx
0x18002eae8  mov     [rbp+arg_18], edi
0x18002eaeb  mov     r15, rcx
0x18002eaee  mov     [rbp+pstrCurrentSDDL], rdi
0x18002eaf2  mov     [rbp+SecurityDescriptor], rdi
0x18002eaf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eafd  lea     rax, WPP_GLOBAL_Control
0x18002eb04  cmp     rcx, rax
0x18002eb07  jz      short loc_18002EB36
0x18002eb09  cmp     byte ptr [rcx+69h], 4
0x18002eb0d  jb      short loc_18002EB36
0x18002eb0f  test    byte ptr [rcx+6Ch], 2
0x18002eb13  jz      short loc_18002EB36
0x18002eb15  mov     rcx, [rcx+60h]
0x18002eb19  lea     edx, [rdi+17h]
0x18002eb1c  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002eb23  call    WPP_SF_
0x18002eb28  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb2f  lea     rax, WPP_GLOBAL_Control
0x18002eb36  test    r15, r15
0x18002eb39  jnz     short loc_18002EB76
0x18002eb3b  test    r14, r14
0x18002eb3e  jnz     short loc_18002EB76
0x18002eb40  cmp     rcx, rax
0x18002eb43  jz      short loc_18002EB6C
0x18002eb45  cmp     byte ptr [rcx+69h], 1
0x18002eb49  jb      short loc_18002EB6C
0x18002eb4b  test    byte ptr [rcx+6Ch], 2
0x18002eb4f  jz      short loc_18002EB6C
0x18002eb51  mov     rcx, [rcx+60h]
0x18002eb55  lea     edx, [r15+18h]
0x18002eb59  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002eb60  call    WPP_SF_
0x18002eb65  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb6c  mov     ebx, 57h ; 'W'
0x18002eb71  jmp     loc_18002ED5A
0x18002eb76  xor     edx, edx; pReserved
0x18002eb78  lea     r9, [rbp+phClientHandle]; phClientHandle
0x18002eb7c  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18002eb80  lea     ecx, [rdx+2]; dwClientVersion
0x18002eb83  call    WlanOpenHandle
0x18002eb88  mov     ebx, eax
0x18002eb8a  test    eax, eax
0x18002eb8c  jnz     loc_18002ED4F
0x18002eb92  mov     r9d, [rbp+pdwNegotiatedVersion]
0x18002eb96  cmp     r9d, 2
0x18002eb9a  jz      short loc_18002EBE3
0x18002eb9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eba3  lea     r14, WPP_GLOBAL_Control
0x18002ebaa  cmp     rcx, r14
0x18002ebad  jz      short loc_18002EBD5
0x18002ebaf  cmp     byte ptr [rcx+69h], 1
0x18002ebb3  jb      short loc_18002EBD5
0x18002ebb5  test    byte ptr [rcx+6Ch], 2
0x18002ebb9  jz      short loc_18002EBD5
0x18002ebbb  mov     rcx, [rcx+60h]
0x18002ebbf  lea     edx, [rax+19h]
0x18002ebc2  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002ebc9  call    WPP_SF_d
0x18002ebce  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebd5  mov     rdi, [rbp+phClientHandle]
0x18002ebd9  mov     ebx, 666h
0x18002ebde  jmp     loc_18002ED61
0x18002ebe3  mov     rdi, [rbp+phClientHandle]
0x18002ebe7  lea     rax, [rbp+arg_18]
0x18002ebeb  mov     rcx, rdi; hClientHandle
0x18002ebee  mov     [rsp+50h+pdwGrantedAccess], rax; pdwGrantedAccess
0x18002ebf3  lea     r9, [rbp+pstrCurrentSDDL]; pstrCurrentSDDL
0x18002ebf7  mov     r8, r14; pValueType
0x18002ebfa  mov     edx, 9; SecurableObject
0x18002ebff  call    WlanGetSecuritySettings
0x18002ec04  mov     ebx, eax
0x18002ec06  test    eax, eax
0x18002ec08  jnz     loc_18002ED53
0x18002ec0e  mov     rcx, [rbp+pstrCurrentSDDL]; StringSecurityDescriptor
0x18002ec12  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002ec16  xor     r9d, r9d; SecurityDescriptorSize
0x18002ec19  lea     edx, [rax+1]; StringSDRevision
0x18002ec1c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002ec22  test    eax, eax
0x18002ec24  jnz     short loc_18002EC76
0x18002ec26  call    cs:__imp_GetLastError
0x18002ec2c  mov     ebx, eax
0x18002ec2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec35  lea     r14, WPP_GLOBAL_Control
0x18002ec3c  cmp     rcx, r14
0x18002ec3f  jz      short loc_18002EC6C
0x18002ec41  cmp     byte ptr [rcx+69h], 1
0x18002ec45  jb      short loc_18002EC6C
0x18002ec47  test    byte ptr [rcx+6Ch], 2
0x18002ec4b  jz      short loc_18002EC6C
0x18002ec4d  mov     rcx, [rcx+60h]
0x18002ec51  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002ec58  mov     edx, 1Ah
0x18002ec5d  mov     r9d, eax
0x18002ec60  call    WPP_SF_d
0x18002ec65  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec6c  test    ebx, ebx
0x18002ec6e  jnz     loc_18002ED61
0x18002ec74  jmp     short loc_18002EC7D
0x18002ec76  lea     r14, WPP_GLOBAL_Control
0x18002ec7d  mov     ecx, 44h ; 'D'; dwMemorySize
0x18002ec82  mov     dword ptr [rbp+Size], ecx
0x18002ec85  call    WlanAllocateMemory
0x18002ec8a  mov     rsi, rax
0x18002ec8d  test    rax, rax
0x18002ec90  jnz     short loc_18002ECCE
0x18002ec92  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec99  cmp     rcx, r14
0x18002ec9c  jz      short loc_18002ECC4
0x18002ec9e  cmp     byte ptr [rcx+69h], 1
0x18002eca2  jb      short loc_18002ECC4
0x18002eca4  test    byte ptr [rcx+6Ch], 2
0x18002eca8  jz      short loc_18002ECC4
0x18002ecaa  mov     rcx, [rcx+60h]
0x18002ecae  lea     edx, [rax+1Bh]
0x18002ecb1  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002ecb8  call    WPP_SF_
0x18002ecbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecc4  mov     ebx, 0Eh
0x18002ecc9  jmp     loc_18002ED61
0x18002ecce  mov     r8d, dword ptr [rbp+Size]; Size
0x18002ecd2  xor     edx, edx; Val
0x18002ecd4  mov     rcx, rsi; void *
0x18002ecd7  call    memset_0
0x18002ecdc  xor     edx, edx; DomainSid
0x18002ecde  lea     r9, [rbp+Size]; cbSid
0x18002ece2  mov     r8, rsi; pSid
0x18002ece5  lea     ecx, [rdx+1Bh]; WellKnownSidType
0x18002ece8  call    cs:__imp_CreateWellKnownSid
0x18002ecee  test    eax, eax
0x18002ecf0  jnz     short loc_18002ED35
0x18002ecf2  call    cs:__imp_GetLastError
0x18002ecf8  mov     ebx, eax
0x18002ecfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed01  cmp     rcx, r14
0x18002ed04  jz      short loc_18002ED31
0x18002ed06  cmp     byte ptr [rcx+69h], 1
0x18002ed0a  jb      short loc_18002ED31
0x18002ed0c  test    byte ptr [rcx+6Ch], 2
0x18002ed10  jz      short loc_18002ED31
0x18002ed12  mov     rcx, [rcx+60h]
0x18002ed16  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002ed1d  mov     edx, 1Ch
0x18002ed22  mov     r9d, eax
0x18002ed25  call    WPP_SF_d
0x18002ed2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed31  test    ebx, ebx
0x18002ed33  jnz     short loc_18002ED61
0x18002ed35  mov     rdx, [rbp+SecurityDescriptor]; void *
0x18002ed39  mov     r8, r15; int *
0x18002ed3c  mov     rcx, rsi; void *
0x18002ed3f  call    ?ValidateSidRights@@YAKPEAX0PEAH@Z; ValidateSidRights(void *,void *,int *)
0x18002ed44  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed4b  mov     ebx, eax
0x18002ed4d  jmp     short loc_18002ED61
0x18002ed4f  mov     rdi, [rbp+phClientHandle]
0x18002ed53  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed5a  lea     r14, WPP_GLOBAL_Control
0x18002ed61  mov     rax, [rbp+SecurityDescriptor]
0x18002ed65  test    rax, rax
0x18002ed68  jz      short loc_18002ED7A
0x18002ed6a  mov     rcx, rax; hMem
0x18002ed6d  call    cs:__imp_LocalFree
0x18002ed73  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed7a  test    rsi, rsi
0x18002ed7d  jz      short loc_18002ED8E
0x18002ed7f  mov     rcx, rsi
0x18002ed82  call    FreeWLMem
0x18002ed87  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed8e  mov     rax, [rbp+pstrCurrentSDDL]
0x18002ed92  test    rax, rax
0x18002ed95  jz      short loc_18002EDA6
0x18002ed97  mov     rcx, rax
0x18002ed9a  call    FreeWLMem
0x18002ed9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eda6  test    rdi, rdi
0x18002eda9  jz      short loc_18002EDBC
0x18002edab  xor     edx, edx; pReserved
0x18002edad  mov     rcx, rdi; hClientHandle
0x18002edb0  call    WlanCloseHandle
0x18002edb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002edbc  cmp     rcx, r14
0x18002edbf  jz      short loc_18002EDE5
0x18002edc1  cmp     byte ptr [rcx+69h], 4
0x18002edc5  jb      short loc_18002EDE5
0x18002edc7  test    byte ptr [rcx+6Ch], 2
0x18002edcb  jz      short loc_18002EDE5
0x18002edcd  mov     rcx, [rcx+60h]
0x18002edd1  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002edd8  mov     edx, 1Dh
0x18002eddd  mov     r9d, ebx
0x18002ede0  call    WPP_SF_d
0x18002ede5  mov     eax, ebx
0x18002ede7  mov     rbx, [rsp+50h+arg_8]
0x18002edef  add     rsp, 50h
0x18002edf3  pop     r15
0x18002edf5  pop     r14
0x18002edf7  pop     rdi
0x18002edf8  pop     rsi
0x18002edf9  pop     rbp
0x18002edfa  retn
```
