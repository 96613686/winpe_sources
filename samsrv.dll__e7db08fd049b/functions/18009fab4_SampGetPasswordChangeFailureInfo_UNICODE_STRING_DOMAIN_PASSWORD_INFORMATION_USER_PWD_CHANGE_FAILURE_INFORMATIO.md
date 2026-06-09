# SampGetPasswordChangeFailureInfo(_UNICODE_STRING *,_DOMAIN_PASSWORD_INFORMATION * *,_USER_PWD_CHANGE_FAILURE_INFORMATION * *)

- ea: `0x18009fab4`
- end: `0x18009fd01`
- name: `?SampGetPasswordChangeFailureInfo@@YAJPEAU_UNICODE_STRING@@PEAPEAU_DOMAIN_PASSWORD_INFORMATION@@PEAPEAU_USER_PWD_CHANGE_FAILURE_INFORMATION@@@Z`
- size: `589`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _DOMAIN_PASSWORD_INFORMATION **, struct _USER_PWD_CHANGE_FAILURE_INFORMATION **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009b894`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x180059a74`
- `0x18009fab4`
- `0x1800b2c04`
- `0x1800b2e34`
- `0x1800b34b8`
- `0x1800b37b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009fc5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009fc5b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18009fcaf`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18009fcaf`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18009fb8c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18009fb8c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18009fca0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18009fca0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18009fb38`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18009fb38`

## pseudocode

```c
__int64 __fastcall SampGetPasswordChangeFailureInfo(
        struct _LSA_UNICODE_STRING *a1,
        struct _DOMAIN_PASSWORD_INFORMATION **a2,
        struct _USER_PWD_CHANGE_FAILURE_INFORMATION **a3)
{
  void *v5; // rdi
  NTSTATUS v6; // eax
  int InformationDomain; // ebx
  NTSTATUS v8; // eax
  __int64 v9; // rsi
  struct _USER_PWD_CHANGE_FAILURE_INFORMATION *v10; // rax
  PVOID PolicyHandle; // [rsp+30h] [rbp-79h] BYREF
  PVOID Buffer; // [rsp+38h] [rbp-71h] BYREF
  void *v14; // [rsp+40h] [rbp-69h] BYREF
  void *v15; // [rsp+48h] [rbp-61h]
  __int128 v16; // [rsp+50h] [rbp-59h] BYREF
  __int128 v17; // [rsp+60h] [rbp-49h]
  __int128 v18; // [rsp+70h] [rbp-39h]
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-29h] BYREF
  __int64 v20; // [rsp+B0h] [rbp+7h] BYREF
  int v21; // [rsp+B8h] [rbp+Fh]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a3 = 0;
  v14 = 0;
  v20 = 0;
  v21 = 0;
  v15 = 0;
  PolicyHandle = 0;
  Buffer = 0;
  v16 = 0;
  v5 = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v17 = 0;
  v18 = 0;
  v6 = LsaOpenPolicy(a1, &ObjectAttributes, 1u, &PolicyHandle);
  InformationDomain = v6;
  if ( v6 >= 0 )
  {
    v8 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
    InformationDomain = v8;
    if ( v8 >= 0 )
    {
      LODWORD(v16) = 48;
      *((_QWORD *)&v18 + 1) = &v20;
      *((_QWORD *)&v16 + 1) = 0;
      DWORD2(v17) = 0;
      *(_QWORD *)&v17 = 0;
      *(_QWORD *)&v18 = 0;
      v20 = 0x10000000CLL;
      LOWORD(v21) = 0;
      InformationDomain = SamConnect(a1, &v14, 32, &v16);
      if ( InformationDomain >= 0 )
      {
        InformationDomain = SamOpenDomain(v14);
        if ( InformationDomain >= 0 )
        {
          v5 = v15;
          InformationDomain = SamQueryInformationDomain(v15);
          if ( InformationDomain >= 0 )
          {
            v9 = 24;
            v10 = (struct _USER_PWD_CHANGE_FAILURE_INFORMATION *)LocalAlloc(0x40u, 0x18u);
            *a3 = v10;
            if ( v10 )
            {
              do
              {
                *(_BYTE *)v10 = 0;
                v10 = (struct _USER_PWD_CHANGE_FAILURE_INFORMATION *)((char *)v10 + 1);
                --v9;
              }
              while ( v9 );
            }
            else
            {
              InformationDomain = -1073741801;
            }
          }
        }
      }
    }
    else
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x100) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_ZD(
          WPP_GLOBAL_Control[3].Buffer,
          340,
          (unsigned int)WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
          (_DWORD)a1,
          v8);
      }
      Buffer = 0;
    }
  }
  else
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x100) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_ZD(
        WPP_GLOBAL_Control[3].Buffer,
        339,
        (unsigned int)WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
        (_DWORD)a1,
        v6);
    }
    PolicyHandle = 0;
  }
  if ( v14 )
    SamCloseHandle(v14);
  if ( v5 )
    SamCloseHandle(v5);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      341,
      WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
      (unsigned int)InformationDomain,
      InformationDomain);
  return (unsigned int)InformationDomain;
}

```

## disassembly

```asm
0x18009fab4  push    rbp
0x18009fab6  push    rbx
0x18009fab7  push    rsi
0x18009fab8  push    rdi
0x18009fab9  push    r12
0x18009fabb  push    r14
0x18009fabd  push    r15
0x18009fabf  lea     rbp, [rsp-27h]
0x18009fac4  sub     rsp, 0D0h
0x18009facb  mov     rax, cs:__security_cookie
0x18009fad2  xor     rax, rsp
0x18009fad5  mov     [rbp+57h+var_40], rax
0x18009fad9  xor     r12d, r12d
0x18009fadc  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18009fae4  xorps   xmm0, xmm0
0x18009fae7  mov     [r8], r12
0x18009faea  xor     eax, eax
0x18009faec  mov     [rbp+57h+var_C0], r12
0x18009faf0  mov     r14, r8
0x18009faf3  mov     [rbp+57h+var_50], rax
0x18009faf7  mov     r15, rdx
0x18009fafa  mov     [rbp+57h+var_48], eax
0x18009fafd  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18009fb01  mov     [rbp+57h+var_B8], r12
0x18009fb05  lea     r8d, [rax+1]; DesiredAccess
0x18009fb09  mov     [rbp+57h+PolicyHandle], r12
0x18009fb0d  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18009fb11  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r12
0x18009fb15  mov     rsi, rcx
0x18009fb18  mov     [rbp+57h+Buffer], r12
0x18009fb1c  movups  [rbp+57h+var_B0], xmm0
0x18009fb20  mov     edi, r12d
0x18009fb23  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18009fb27  movups  [rbp+57h+var_A0], xmm0
0x18009fb2b  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x18009fb2f  movups  [rbp+57h+var_90], xmm0
0x18009fb33  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009fb38  call    cs:__imp_LsaOpenPolicy
0x18009fb3e  mov     ebx, eax
0x18009fb40  test    eax, eax
0x18009fb42  jns     short loc_18009FB7F
0x18009fb44  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fb4b  test    dword ptr [rcx+44h], 100h
0x18009fb52  jz      short loc_18009FB76
0x18009fb54  cmp     byte ptr [rcx+41h], 2
0x18009fb58  jb      short loc_18009FB76
0x18009fb5a  mov     rcx, [rcx+38h]
0x18009fb5e  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x18009fb65  mov     edx, 153h
0x18009fb6a  mov     [rsp+100h+var_E0], eax
0x18009fb6e  mov     r9, rsi
0x18009fb71  call    WPP_SF_ZD
0x18009fb76  mov     [rbp+57h+PolicyHandle], r12
0x18009fb7a  jmp     loc_18009FC7C
0x18009fb7f  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18009fb83  lea     r8, [rbp+57h+Buffer]; Buffer
0x18009fb87  mov     edx, 5; InformationClass
0x18009fb8c  call    cs:__imp_LsaQueryInformationPolicy
0x18009fb92  mov     ebx, eax
0x18009fb94  test    eax, eax
0x18009fb96  jns     short loc_18009FBD3
0x18009fb98  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fb9f  test    dword ptr [rcx+44h], 100h
0x18009fba6  jz      short loc_18009FBCA
0x18009fba8  cmp     byte ptr [rcx+41h], 2
0x18009fbac  jb      short loc_18009FBCA
0x18009fbae  mov     rcx, [rcx+38h]
0x18009fbb2  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x18009fbb9  mov     edx, 154h
0x18009fbbe  mov     [rsp+100h+var_E0], eax
0x18009fbc2  mov     r9, rsi
0x18009fbc5  call    WPP_SF_ZD
0x18009fbca  mov     [rbp+57h+Buffer], r12
0x18009fbce  jmp     loc_18009FC7C
0x18009fbd3  lea     rax, [rbp+57h+var_50]
0x18009fbd7  mov     dword ptr [rbp+57h+var_B0], 30h ; '0'
0x18009fbde  lea     r9, [rbp+57h+var_B0]
0x18009fbe2  mov     qword ptr [rbp+57h+var_90+8], rax
0x18009fbe6  mov     r8d, 20h ; ' '
0x18009fbec  mov     qword ptr [rbp+57h+var_B0+8], r12
0x18009fbf0  lea     rdx, [rbp+57h+var_C0]
0x18009fbf4  mov     dword ptr [rbp+57h+var_A0+8], r12d
0x18009fbf8  mov     rcx, rsi
0x18009fbfb  mov     qword ptr [rbp+57h+var_A0], r12
0x18009fbff  mov     qword ptr [rbp+57h+var_90], r12
0x18009fc03  mov     dword ptr [rbp+57h+var_50], 0Ch
0x18009fc0a  mov     dword ptr [rbp+57h+var_50+4], 1
0x18009fc11  mov     word ptr [rbp+57h+var_48], r12w
0x18009fc16  call    SamConnect
0x18009fc1b  mov     ebx, eax
0x18009fc1d  test    eax, eax
0x18009fc1f  js      short loc_18009FC7C
0x18009fc21  mov     r8, [rbp+57h+Buffer]
0x18009fc25  lea     r9, [rbp+57h+var_B8]
0x18009fc29  mov     rcx, [rbp+57h+var_C0]; void *
0x18009fc2d  mov     r8, [r8+10h]
0x18009fc31  call    SamOpenDomain
0x18009fc36  mov     ebx, eax
0x18009fc38  test    eax, eax
0x18009fc3a  js      short loc_18009FC7C
0x18009fc3c  mov     rdi, [rbp+57h+var_B8]
0x18009fc40  mov     r8, r15
0x18009fc43  mov     rcx, rdi; void *
0x18009fc46  call    SamQueryInformationDomain
0x18009fc4b  mov     ebx, eax
0x18009fc4d  test    eax, eax
0x18009fc4f  js      short loc_18009FC7C
0x18009fc51  mov     esi, 18h
0x18009fc56  mov     edx, esi; uBytes
0x18009fc58  lea     ecx, [rsi+28h]; uFlags
0x18009fc5b  call    cs:__imp_LocalAlloc
0x18009fc61  mov     [r14], rax
0x18009fc64  test    rax, rax
0x18009fc67  jnz     short loc_18009FC70
0x18009fc69  mov     ebx, 0C0000017h
0x18009fc6e  jmp     short loc_18009FC7C
0x18009fc70  mov     [rax], r12b
0x18009fc73  inc     rax
0x18009fc76  sub     rsi, 1
0x18009fc7a  jnz     short loc_18009FC70
0x18009fc7c  mov     rcx, [rbp+57h+var_C0]; void *
0x18009fc80  test    rcx, rcx
0x18009fc83  jz      short loc_18009FC8A
0x18009fc85  call    SamCloseHandle
0x18009fc8a  test    rdi, rdi
0x18009fc8d  jz      short loc_18009FC97
0x18009fc8f  mov     rcx, rdi; void *
0x18009fc92  call    SamCloseHandle
0x18009fc97  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18009fc9b  test    rcx, rcx
0x18009fc9e  jz      short loc_18009FCA6
0x18009fca0  call    cs:__imp_LsaClose
0x18009fca6  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18009fcaa  test    rcx, rcx
0x18009fcad  jz      short loc_18009FCB5
0x18009fcaf  call    cs:__imp_LsaFreeMemory
0x18009fcb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fcbc  test    dword ptr [rcx+44h], 20000h
0x18009fcc3  jz      short loc_18009FCE1
0x18009fcc5  mov     rcx, [rcx+38h]
0x18009fcc9  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x18009fcd0  mov     edx, 155h
0x18009fcd5  mov     [rsp+100h+var_E0], ebx
0x18009fcd9  mov     r9d, ebx
0x18009fcdc  call    WPP_SF_Dd
0x18009fce1  mov     eax, ebx
0x18009fce3  mov     rcx, [rbp+57h+var_40]
0x18009fce7  xor     rcx, rsp; StackCookie
0x18009fcea  call    __security_check_cookie
0x18009fcef  add     rsp, 0D0h
0x18009fcf6  pop     r15
0x18009fcf8  pop     r14
0x18009fcfa  pop     r12
0x18009fcfc  pop     rdi
0x18009fcfd  pop     rsi
0x18009fcfe  pop     rbx
0x18009fcff  pop     rbp
0x18009fd00  retn
```
