# VmpApplyHotplugProtection(VM_VOLUME_EXTENSION *)

- ea: `0x140010014`
- end: `0x140010467`
- name: `?VmpApplyHotplugProtection@@YAJPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `1107`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400046a4`

## callees

- `0x140005050`
- `0x140005540`
- `0x140010014`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140010147`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140010147`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400103ff`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400103ff`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14001019c`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14001041e`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14001019c`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14001041e`
- `ntoskrnl!RtlLengthSid` at `0x140010212`
- `ntoskrnl!RtlLengthSid` at `0x140010223`
- `ntoskrnl!RtlLengthSid` at `0x140010243`
- `ntoskrnl!RtlLengthSid` at `0x140010262`
- `ntoskrnl!RtlLengthSid` at `0x140010281`
- `ntoskrnl!RtlLengthSid` at `0x140010212`
- `ntoskrnl!RtlLengthSid` at `0x140010223`
- `ntoskrnl!RtlLengthSid` at `0x140010243`
- `ntoskrnl!RtlLengthSid` at `0x140010262`
- `ntoskrnl!RtlLengthSid` at `0x140010281`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400102f8`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001032b`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001035e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140010391`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400103c4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400102f8`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001032b`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001035e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140010391`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400103c4`
- `ntoskrnl!RtlGetVersion` at `0x1400101cd`
- `ntoskrnl!RtlGetVersion` at `0x1400101cd`
- `ntoskrnl!RtlCreateAcl` at `0x1400102c5`
- `ntoskrnl!RtlCreateAcl` at `0x1400102c5`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400103e0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400103e0`
- `ntoskrnl!SeExports` at `0x1400101fa`
- `ntoskrnl!SeExports` at `0x140010232`
- `ntoskrnl!SeExports` at `0x140010251`
- `ntoskrnl!SeExports` at `0x140010270`
- `ntoskrnl!SeExports` at `0x1400102db`
- `ntoskrnl!SeExports` at `0x14001030e`
- `ntoskrnl!SeExports` at `0x140010341`
- `ntoskrnl!SeExports` at `0x140010374`
- `ntoskrnl!SeExports` at `0x1400103a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010431`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010431`
- `ntoskrnl!ExAllocatePool2` at `0x14001029f`
- `ntoskrnl!ExAllocatePool2` at `0x14001029f`

## string_xrefs

- `0x1400100cb`: `HotplugSecurityDescriptor`
- `0x14001012d`: `HotplugSecureOpen`
- `0x1400100f8`: `\Registry\Machine\System\CurrentControlSet\Control\Storage`

## pseudocode

```c
__int64 __fastcall VmpApplyHotplugProtection(struct VM_VOLUME_EXTENSION *a1)
{
  __int64 v1; // rsi
  NTSTATUS RegistryValues; // eax
  NTSTATUS Version; // ebx
  struct _ACL *v4; // r8
  NTSTATUS v5; // eax
  struct _ACL *v6; // rcx
  PSID SeAliasAdminsSid; // rbx
  ULONG v8; // edi
  ULONG v9; // ebx
  struct _ACL *Pool2; // rax
  struct _ACL *v11; // rdi
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+34h] [rbp-CCh] BYREF
  struct _ACL *v15; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h]
  _BYTE VersionInformation[284]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v19[28]; // [rsp+190h] [rbp+90h] BYREF

  v1 = *(_QWORD *)a1;
  v14 = 0;
  memset(&v19[1], 0, 0xD8u);
  v15 = 0;
  v13 = -1;
  v17 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  memset(VersionInformation, 0, sizeof(VersionInformation));
  LODWORD(v19[4]) = 50331648;
  LODWORD(v19[11]) = 0x4000000;
  v19[0] = &VmpQueryHotplugProtectionQueryRoutine;
  LODWORD(v19[18]) = 0x4000000;
  LODWORD(v19[8]) = 288;
  v19[2] = L"HotplugSecurityDescriptor";
  LODWORD(v19[15]) = 288;
  v19[3] = &v15;
  LODWORD(v19[1]) = 256;
  v19[9] = L"Deny_Execute";
  v19[10] = &v14;
  v19[16] = L"HotplugSecureOpen";
  v19[17] = &v13;
  RegistryValues = RtlQueryRegistryValuesEx(
                     0,
                     L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Storage",
                     v19,
                     0,
                     0);
  Version = 0;
  if ( RegistryValues != -1073741772 )
    Version = RegistryValues;
  if ( Version >= 0 )
  {
    if ( v14 == 1 )
      *(_DWORD *)(v1 + 48) |= 0x800000u;
    v4 = v15;
    if ( v15 )
    {
      if ( v13 )
      {
        *(_DWORD *)(v1 + 52) |= 0x100u;
        v4 = v15;
      }
      v5 = ObSetSecurityObjectByPointer(v1, 12, v4);
      v6 = v15;
      Version = v5;
LABEL_26:
      ExFreePoolWithTag(v6, 0);
      return (unsigned int)Version;
    }
    if ( v13 == 1 )
      *(_DWORD *)(v1 + 52) |= 0x100u;
    *(_DWORD *)VersionInformation = 284;
    Version = RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation);
    if ( Version >= 0 && (unsigned __int8)(VersionInformation[282] - 2) > 1u )
    {
      SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
      v8 = RtlLengthSid(SeExports->SeRestrictedSid);
      LODWORD(SeAliasAdminsSid) = v8 + RtlLengthSid(SeAliasAdminsSid);
      LODWORD(SeAliasAdminsSid) = RtlLengthSid(SeExports->SeLocalSystemSid) + (_DWORD)SeAliasAdminsSid;
      LODWORD(SeAliasAdminsSid) = RtlLengthSid(SeExports->SeInteractiveSid) + (_DWORD)SeAliasAdminsSid;
      v9 = RtlLengthSid(SeExports->SeWorldSid) + 68 + (_DWORD)SeAliasAdminsSid;
      Pool2 = (struct _ACL *)ExAllocatePool2(258, v9, 538987862);
      v11 = Pool2;
      if ( Pool2 )
      {
        Version = RtlCreateAcl(Pool2, v9, 2u);
        if ( Version >= 0 )
        {
          Version = RtlAddAccessAllowedAce(v11, 2u, 0x20000000u, SeExports->SeWorldSid);
          if ( Version >= 0 )
          {
            Version = RtlAddAccessAllowedAce(v11, 2u, 0x10000000u, SeExports->SeLocalSystemSid);
            if ( Version >= 0 )
            {
              Version = RtlAddAccessAllowedAce(v11, 2u, 0x10000000u, SeExports->SeAliasAdminsSid);
              if ( Version >= 0 )
              {
                Version = RtlAddAccessAllowedAce(v11, 2u, 0x20000000u, SeExports->SeRestrictedSid);
                if ( Version >= 0 )
                {
                  Version = RtlAddAccessAllowedAce(v11, 2u, 0xC0010000, SeExports->SeInteractiveSid);
                  if ( Version >= 0 )
                  {
                    Version = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                    if ( Version >= 0 )
                    {
                      Version = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0);
                      if ( Version >= 0 )
                        Version = ObSetSecurityObjectByPointer(v1, 4, SecurityDescriptor);
                    }
                  }
                }
              }
            }
          }
        }
        v6 = v11;
        goto LABEL_26;
      }
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)Version;
}

```

## disassembly

```asm
0x140010014  mov     [rsp-8+arg_8], rbx
0x140010019  mov     [rsp-8+arg_10], rsi
0x14001001e  push    rbp
0x14001001f  push    rdi
0x140010020  push    r15
0x140010022  lea     rbp, [rsp-180h]
0x14001002a  sub     rsp, 280h
0x140010031  mov     rax, cs:__security_cookie
0x140010038  xor     rax, rsp
0x14001003b  mov     [rbp+190h+var_20], rax
0x140010042  mov     rsi, [rcx]
0x140010045  xor     edx, edx; Val
0x140010047  lea     rcx, [rbp+190h+var_F8]; void *
0x14001004e  mov     [rsp+290h+var_25C], 0
0x140010056  mov     r8d, 0D8h; Size
0x14001005c  call    memset
0x140010061  xorps   xmm0, xmm0
0x140010064  mov     [rsp+290h+var_258], 0
0x14001006d  xor     eax, eax
0x14001006f  mov     [rsp+290h+var_260], 0FFFFFFFFh
0x140010077  mov     r15d, 11Ch
0x14001007d  mov     [rsp+290h+var_230], rax
0x140010082  mov     r8d, r15d; Size
0x140010085  lea     rcx, [rsp+290h+VersionInformation]; void *
0x14001008a  xor     edx, edx; Val
0x14001008c  movups  [rsp+290h+SecurityDescriptor], xmm0
0x140010091  movups  [rsp+290h+var_240], xmm0
0x140010096  call    memset
0x14001009b  mov     ecx, 4000000h
0x1400100a0  mov     [rbp+190h+var_E0], 3000000h
0x1400100aa  lea     rax, VmpQueryHotplugProtectionQueryRoutine
0x1400100b1  mov     [rbp+190h+var_A8], ecx
0x1400100b7  mov     [rbp+190h+var_100], rax
0x1400100be  lea     edi, [r15-1Ch]
0x1400100c2  lea     edx, [rdi+20h]
0x1400100c5  mov     [rbp+190h+var_70], ecx
0x1400100cb  lea     rax, aHotplugsecurit; "HotplugSecurityDescriptor"
0x1400100d2  mov     [rbp+190h+var_C0], edx
0x1400100d8  mov     [rbp+190h+var_F0], rax
0x1400100df  lea     r8, [rbp+190h+var_100]
0x1400100e6  lea     rax, [rsp+290h+var_258]
0x1400100eb  mov     [rbp+190h+var_88], edx
0x1400100f1  mov     [rbp+190h+var_E8], rax
0x1400100f8  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400100ff  lea     rax, aDenyExecute; "Deny_Execute"
0x140010106  mov     [rbp+190h+var_F8], edi
0x14001010c  mov     [rbp+190h+var_B8], rax
0x140010113  xor     r9d, r9d
0x140010116  lea     rax, [rsp+290h+var_25C]
0x14001011b  mov     [rsp+290h+var_270], 0
0x140010124  mov     [rbp+190h+var_B0], rax
0x14001012b  xor     ecx, ecx
0x14001012d  lea     rax, aHotplugsecureo; "HotplugSecureOpen"
0x140010134  mov     [rbp+190h+var_80], rax
0x14001013b  lea     rax, [rsp+290h+var_260]
0x140010140  mov     [rbp+190h+var_78], rax
0x140010147  call    cs:__imp_RtlQueryRegistryValuesEx
0x14001014e  nop     dword ptr [rax+rax+00h]
0x140010153  xor     ebx, ebx
0x140010155  cmp     eax, 0C0000034h
0x14001015a  cmovnz  ebx, eax
0x14001015d  test    ebx, ebx
0x14001015f  js      loc_14001043D
0x140010165  cmp     [rsp+290h+var_25C], 1
0x14001016a  jnz     short loc_140010176
0x14001016c  mov     eax, [rsi+30h]
0x14001016f  bts     eax, 17h
0x140010173  mov     [rsi+30h], eax
0x140010176  mov     r8, [rsp+290h+var_258]
0x14001017b  test    r8, r8
0x14001017e  jz      short loc_1400101B4
0x140010180  cmp     [rsp+290h+var_260], 0
0x140010185  jz      short loc_140010194
0x140010187  mov     eax, [rsi+34h]
0x14001018a  or      eax, edi
0x14001018c  mov     [rsi+34h], eax
0x14001018f  mov     r8, [rsp+290h+var_258]
0x140010194  mov     edx, 0Ch
0x140010199  mov     rcx, rsi
0x14001019c  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400101a3  nop     dword ptr [rax+rax+00h]
0x1400101a8  mov     rcx, [rsp+290h+var_258]
0x1400101ad  mov     ebx, eax
0x1400101af  jmp     loc_14001042F
0x1400101b4  cmp     [rsp+290h+var_260], 1
0x1400101b9  jnz     short loc_1400101C3
0x1400101bb  mov     eax, [rsi+34h]
0x1400101be  or      eax, edi
0x1400101c0  mov     [rsi+34h], eax
0x1400101c3  lea     rcx, [rsp+290h+VersionInformation]; lpVersionInformation
0x1400101c8  mov     [rsp+290h+VersionInformation.dwOSVersionInfoSize], r15d
0x1400101cd  call    cs:__imp_RtlGetVersion
0x1400101d4  nop     dword ptr [rax+rax+00h]
0x1400101d9  mov     ebx, eax
0x1400101db  test    eax, eax
0x1400101dd  js      loc_14001043D
0x1400101e3  mov     al, [rbp+190h+var_106]
0x1400101e9  mov     r15d, 2
0x1400101ef  sub     al, r15b
0x1400101f2  cmp     al, 1
0x1400101f4  jbe     loc_14001043D
0x1400101fa  mov     rdx, cs:__imp_SeExports
0x140010201  mov     rax, [rdx]
0x140010204  mov     rcx, [rax+158h]; Sid
0x14001020b  mov     rbx, [rax+110h]
0x140010212  call    cs:__imp_RtlLengthSid
0x140010219  nop     dword ptr [rax+rax+00h]
0x14001021e  mov     rcx, rbx; Sid
0x140010221  mov     edi, eax
0x140010223  call    cs:__imp_RtlLengthSid
0x14001022a  nop     dword ptr [rax+rax+00h]
0x14001022f  lea     ebx, [rdi+rax]
0x140010232  mov     rax, cs:__imp_SeExports
0x140010239  mov     rcx, [rax]
0x14001023c  mov     rcx, [rcx+108h]; Sid
0x140010243  call    cs:__imp_RtlLengthSid
0x14001024a  nop     dword ptr [rax+rax+00h]
0x14001024f  add     ebx, eax
0x140010251  mov     rax, cs:__imp_SeExports
0x140010258  mov     rcx, [rax]
0x14001025b  mov     rcx, [rcx+100h]; Sid
0x140010262  call    cs:__imp_RtlLengthSid
0x140010269  nop     dword ptr [rax+rax+00h]
0x14001026e  add     ebx, eax
0x140010270  mov     rax, cs:__imp_SeExports
0x140010277  mov     rcx, [rax]
0x14001027a  mov     rcx, [rcx+0C0h]; Sid
0x140010281  call    cs:__imp_RtlLengthSid
0x140010288  nop     dword ptr [rax+rax+00h]
0x14001028d  mov     ecx, 102h
0x140010292  mov     r8d, 20204D56h
0x140010298  add     eax, 44h ; 'D'
0x14001029b  add     ebx, eax
0x14001029d  mov     edx, ebx
0x14001029f  call    cs:__imp_ExAllocatePool2
0x1400102a6  nop     dword ptr [rax+rax+00h]
0x1400102ab  mov     rdi, rax
0x1400102ae  test    rax, rax
0x1400102b1  jnz     short loc_1400102BD
0x1400102b3  mov     ebx, 0C000009Ah
0x1400102b8  jmp     loc_14001043D
0x1400102bd  mov     r8d, r15d; AclRevision
0x1400102c0  mov     edx, ebx; AclLength
0x1400102c2  mov     rcx, rdi; Acl
0x1400102c5  call    cs:__imp_RtlCreateAcl
0x1400102cc  nop     dword ptr [rax+rax+00h]
0x1400102d1  mov     ebx, eax
0x1400102d3  test    eax, eax
0x1400102d5  js      loc_14001042C
0x1400102db  mov     rax, cs:__imp_SeExports
0x1400102e2  mov     r8d, 20000000h; AccessMask
0x1400102e8  mov     edx, r15d; AceRevision
0x1400102eb  mov     rcx, rdi; Acl
0x1400102ee  mov     r9, [rax]
0x1400102f1  mov     r9, [r9+0C0h]; Sid
0x1400102f8  call    cs:__imp_RtlAddAccessAllowedAce
0x1400102ff  nop     dword ptr [rax+rax+00h]
0x140010304  mov     ebx, eax
0x140010306  test    eax, eax
0x140010308  js      loc_14001042C
0x14001030e  mov     rax, cs:__imp_SeExports
0x140010315  mov     r8d, 10000000h; AccessMask
0x14001031b  mov     edx, r15d; AceRevision
0x14001031e  mov     rcx, rdi; Acl
0x140010321  mov     r9, [rax]
0x140010324  mov     r9, [r9+108h]; Sid
0x14001032b  call    cs:__imp_RtlAddAccessAllowedAce
0x140010332  nop     dword ptr [rax+rax+00h]
0x140010337  mov     ebx, eax
0x140010339  test    eax, eax
0x14001033b  js      loc_14001042C
0x140010341  mov     rax, cs:__imp_SeExports
0x140010348  mov     r8d, 10000000h; AccessMask
0x14001034e  mov     edx, r15d; AceRevision
0x140010351  mov     rcx, rdi; Acl
0x140010354  mov     r9, [rax]
0x140010357  mov     r9, [r9+110h]; Sid
0x14001035e  call    cs:__imp_RtlAddAccessAllowedAce
0x140010365  nop     dword ptr [rax+rax+00h]
0x14001036a  mov     ebx, eax
0x14001036c  test    eax, eax
0x14001036e  js      loc_14001042C
0x140010374  mov     rax, cs:__imp_SeExports
0x14001037b  mov     r8d, 20000000h; AccessMask
0x140010381  mov     edx, r15d; AceRevision
0x140010384  mov     rcx, rdi; Acl
0x140010387  mov     r9, [rax]
0x14001038a  mov     r9, [r9+158h]; Sid
0x140010391  call    cs:__imp_RtlAddAccessAllowedAce
0x140010398  nop     dword ptr [rax+rax+00h]
0x14001039d  mov     ebx, eax
0x14001039f  test    eax, eax
0x1400103a1  js      loc_14001042C
0x1400103a7  mov     rax, cs:__imp_SeExports
0x1400103ae  mov     r8d, 0C0010000h; AccessMask
0x1400103b4  mov     edx, r15d; AceRevision
0x1400103b7  mov     rcx, rdi; Acl
0x1400103ba  mov     r9, [rax]
0x1400103bd  mov     r9, [r9+100h]; Sid
0x1400103c4  call    cs:__imp_RtlAddAccessAllowedAce
0x1400103cb  nop     dword ptr [rax+rax+00h]
0x1400103d0  mov     ebx, eax
0x1400103d2  test    eax, eax
0x1400103d4  js      short loc_14001042C
0x1400103d6  mov     edx, 1; Revision
0x1400103db  lea     rcx, [rsp+290h+SecurityDescriptor]; SecurityDescriptor
0x1400103e0  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400103e7  nop     dword ptr [rax+rax+00h]
0x1400103ec  mov     ebx, eax
0x1400103ee  test    eax, eax
0x1400103f0  js      short loc_14001042C
0x1400103f2  xor     r9d, r9d; DaclDefaulted
0x1400103f5  lea     rcx, [rsp+290h+SecurityDescriptor]; SecurityDescriptor
0x1400103fa  mov     r8, rdi; Dacl
0x1400103fd  mov     dl, 1; DaclPresent
0x1400103ff  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140010406  nop     dword ptr [rax+rax+00h]
0x14001040b  mov     ebx, eax
0x14001040d  test    eax, eax
0x14001040f  js      short loc_14001042C
0x140010411  lea     r8, [rsp+290h+SecurityDescriptor]
0x140010416  mov     edx, 4
0x14001041b  mov     rcx, rsi
0x14001041e  call    cs:__imp_ObSetSecurityObjectByPointer
0x140010425  nop     dword ptr [rax+rax+00h]
0x14001042a  mov     ebx, eax
0x14001042c  mov     rcx, rdi; P
0x14001042f  xor     edx, edx; Tag
0x140010431  call    cs:__imp_ExFreePoolWithTag
0x140010438  nop     dword ptr [rax+rax+00h]
0x14001043d  mov     eax, ebx
0x14001043f  mov     rcx, [rbp+190h+var_20]
0x140010446  xor     rcx, rsp; StackCookie
0x140010449  call    __security_check_cookie
0x14001044e  lea     r11, [rsp+290h+var_10]
0x140010456  mov     rbx, [r11+28h]
0x14001045a  mov     rsi, [r11+30h]
0x14001045e  mov     rsp, r11
0x140010461  pop     r15
0x140010463  pop     rdi
0x140010464  pop     rbp
0x140010465  retn
```
