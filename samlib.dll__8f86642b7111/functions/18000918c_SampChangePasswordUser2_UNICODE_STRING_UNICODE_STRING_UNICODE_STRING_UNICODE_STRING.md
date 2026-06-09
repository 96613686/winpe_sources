# SampChangePasswordUser2(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x18000918c`
- end: `0x1800094e1`
- name: `?SampChangePasswordUser2@@YAJPEAU_UNICODE_STRING@@000@Z`
- size: `853`
- prototype: `__int64 __fastcall(PLSA_UNICODE_STRING SystemName, struct _UNICODE_STRING *, PCUNICODE_STRING SourceString, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000d020`

## callees

- `0x180001010`
- `0x180001800`
- `0x180002a80`
- `0x180002e90`
- `0x1800038b0`
- `0x180004dd0`
- `0x180006620`
- `0x18000807c`
- `0x18000918c`
- `0x18000ccb0`
- `0x180014734`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000948e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000948e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000949d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000949d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800092b3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800092b3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180009262`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180009262`

## pseudocode

```c
__int64 __fastcall SampChangePasswordUser2(
        PLSA_UNICODE_STRING SystemName,
        struct _UNICODE_STRING *a2,
        PCUNICODE_STRING SourceString,
        struct _UNICODE_STRING *a4)
{
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  void *v13; // rsi
  int v14; // eax
  int v15; // eax
  void *v16; // rdi
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  void *v20; // [rsp+30h] [rbp-69h] BYREF
  PVOID PolicyHandle; // [rsp+38h] [rbp-61h] BYREF
  PVOID Buffer; // [rsp+40h] [rbp-59h] BYREF
  unsigned int *v23; // [rsp+48h] [rbp-51h] BYREF
  void *v24; // [rsp+50h] [rbp-49h] BYREF
  void *v25; // [rsp+58h] [rbp-41h] BYREF
  enum _SID_NAME_USE *v26; // [rsp+60h] [rbp-39h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-31h] BYREF
  __int64 v28; // [rsp+98h] [rbp-1h] BYREF
  int v29; // [rsp+A0h] [rbp+7h]

  v20 = 0;
  v28 = 0;
  v29 = 0;
  v24 = 0;
  v25 = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Buffer = 0;
  v23 = 0;
  v26 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_ZZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 288, (_DWORD)SourceString, (_DWORD)SystemName, (__int64)a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.SecurityQualityOfService = &v28;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  ObjectAttributes.SecurityDescriptor = 0;
  v28 = 0x20000000CLL;
  LOWORD(v29) = 1;
  v8 = LsaOpenPolicy(SystemName, &ObjectAttributes, 1u, &PolicyHandle);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 289;
LABEL_8:
      WPP_SF_D(v10[2], v11, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, (unsigned int)v8);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  v8 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v8 = SamConnect(SystemName, &v20, 32, &ObjectAttributes);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 291;
        goto LABEL_8;
      }
      goto LABEL_40;
    }
    v12 = SamOpenDomain(v20, 0x20000000, *((PSID *)Buffer + 2), (__int64 *)&v24);
    v13 = v24;
    v9 = v12;
    if ( v12 < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          292,
          &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
          (unsigned int)v12);
LABEL_38:
      if ( v13 )
        SamCloseHandle(v13);
      goto LABEL_40;
    }
    v14 = SamLookupNamesInDomain(v24, 1u, a2, &v23, &v26);
    v9 = v14;
    if ( v14 < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          293,
          &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
          (unsigned int)v14);
      if ( v9 == -1073741709 )
        v9 = -1073741724;
      goto LABEL_38;
    }
    v15 = SamOpenUser(v13, 64, *v23, (__int64 *)&v25);
    v16 = v25;
    v9 = v15;
    if ( v15 >= 0 )
    {
      v15 = SamChangePasswordUser(v25, SourceString, a4);
      v9 = v15;
      if ( v15 < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = 295;
          goto LABEL_35;
        }
      }
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = 294;
LABEL_35:
        WPP_SF_D(v17[2], v18, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, (unsigned int)v15);
      }
    }
    if ( v16 )
      SamCloseHandle(v16);
    goto LABEL_38;
  }
  v10 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 290;
    goto LABEL_8;
  }
LABEL_40:
  if ( v20 )
    SamCloseHandle(v20);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( v23 )
    SamFreeMemory();
  if ( v26 )
    SamFreeMemory();
  return v9;
}

```

## disassembly

```asm
0x18000918c  push    rbp
0x18000918e  push    rbx
0x18000918f  push    rsi
0x180009190  push    rdi
0x180009191  push    r12
0x180009193  push    r13
0x180009195  push    r14
0x180009197  push    r15
0x180009199  lea     rbp, [rsp-1Fh]
0x18000919e  sub     rsp, 0B8h
0x1800091a5  mov     rax, cs:__security_cookie
0x1800091ac  xor     rax, rsp
0x1800091af  mov     [rbp+57h+var_48], rax
0x1800091b3  xor     r13d, r13d
0x1800091b6  xorps   xmm0, xmm0
0x1800091b9  xor     eax, eax
0x1800091bb  mov     [rbp+57h+var_C0], r13
0x1800091bf  mov     [rbp+57h+var_58], rax
0x1800091c3  mov     r12, r9
0x1800091c6  mov     [rbp+57h+var_50], eax
0x1800091c9  mov     r15, r8
0x1800091cc  mov     r14, rdx
0x1800091cf  mov     [rbp+57h+var_A0], r13
0x1800091d3  mov     rdi, rcx
0x1800091d6  mov     [rbp+57h+var_98], r13
0x1800091da  mov     [rbp+57h+PolicyHandle], r13
0x1800091de  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800091e2  mov     [rbp+57h+Buffer], r13
0x1800091e6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800091ea  mov     [rbp+57h+var_A8], r13
0x1800091ee  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800091f2  mov     [rbp+57h+var_90], r13
0x1800091f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091fd  lea     esi, [rax+2]
0x180009200  test    [rcx+1Ch], sil
0x180009204  jz      short loc_180009222
0x180009206  cmp     byte ptr [rcx+19h], 4
0x18000920a  jb      short loc_180009222
0x18000920c  mov     rcx, [rcx+10h]
0x180009210  mov     edx, 120h
0x180009215  mov     r9, rdi
0x180009218  mov     [rsp+0F0h+var_D0], r14
0x18000921d  call    WPP_SF_ZZ
0x180009222  lea     rax, [rbp+57h+var_58]
0x180009226  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000922d  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x180009231  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x180009235  mov     r8d, 1; DesiredAccess
0x18000923b  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x18000923f  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180009243  mov     [rbp+57h+ObjectAttributes.Attributes], r13d
0x180009247  mov     rcx, rdi; SystemName
0x18000924a  mov     [rbp+57h+ObjectAttributes.ObjectName], r13
0x18000924e  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r13
0x180009252  mov     dword ptr [rbp+57h+var_58], 0Ch
0x180009259  mov     dword ptr [rbp+57h+var_58+4], esi
0x18000925c  mov     word ptr [rbp+57h+var_50], 1
0x180009262  call    cs:__imp_LsaOpenPolicy
0x180009268  mov     ebx, eax
0x18000926a  test    eax, eax
0x18000926c  jns     short loc_1800092A6
0x18000926e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009275  test    [rcx+1Ch], sil
0x180009279  jz      loc_180009477
0x18000927f  cmp     [rcx+19h], sil
0x180009283  jb      loc_180009477
0x180009289  mov     edx, 121h
0x18000928e  mov     rcx, [rcx+10h]
0x180009292  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180009299  mov     r9d, eax
0x18000929c  call    WPP_SF_D
0x1800092a1  jmp     loc_180009477
0x1800092a6  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800092aa  lea     r8, [rbp+57h+Buffer]; Buffer
0x1800092ae  mov     edx, 5; InformationClass
0x1800092b3  call    cs:__imp_LsaQueryInformationPolicy
0x1800092b9  mov     ebx, eax
0x1800092bb  test    eax, eax
0x1800092bd  jns     short loc_1800092E1
0x1800092bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092c6  test    [rcx+1Ch], sil
0x1800092ca  jz      loc_180009477
0x1800092d0  cmp     [rcx+19h], sil
0x1800092d4  jb      loc_180009477
0x1800092da  mov     edx, 122h
0x1800092df  jmp     short loc_18000928E
0x1800092e1  lea     r9, [rbp+57h+ObjectAttributes]
0x1800092e5  mov     r8d, 20h ; ' '
0x1800092eb  lea     rdx, [rbp+57h+var_C0]
0x1800092ef  mov     rcx, rdi
0x1800092f2  call    SamConnect
0x1800092f7  mov     ebx, eax
0x1800092f9  test    eax, eax
0x1800092fb  jns     short loc_180009322
0x1800092fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180009304  test    [rcx+1Ch], sil
0x180009308  jz      loc_180009477
0x18000930e  cmp     [rcx+19h], sil
0x180009312  jb      loc_180009477
0x180009318  mov     edx, 123h
0x18000931d  jmp     loc_18000928E
0x180009322  mov     r8, [rbp+57h+Buffer]
0x180009326  lea     r9, [rbp+57h+var_A0]
0x18000932a  mov     rcx, [rbp+57h+var_C0]; void *
0x18000932e  mov     edx, 20000000h; char
0x180009333  mov     r8, [r8+10h]; pSid
0x180009337  call    SamOpenDomain
0x18000933c  mov     rsi, [rbp+57h+var_A0]
0x180009340  mov     ebx, eax
0x180009342  test    eax, eax
0x180009344  jns     short loc_18000937E
0x180009346  mov     rcx, cs:WPP_GLOBAL_Control
0x18000934d  test    byte ptr [rcx+1Ch], 2
0x180009351  jz      loc_18000946A
0x180009357  cmp     byte ptr [rcx+19h], 2
0x18000935b  jb      loc_18000946A
0x180009361  mov     rcx, [rcx+10h]
0x180009365  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000936c  mov     edx, 124h
0x180009371  mov     r9d, eax
0x180009374  call    WPP_SF_D
0x180009379  jmp     loc_18000946A
0x18000937e  lea     rax, [rbp+57h+var_90]
0x180009382  mov     r8, r14; struct _UNICODE_STRING *
0x180009385  lea     r9, [rbp+57h+var_A8]; unsigned int **
0x180009389  mov     [rsp+0F0h+var_D0], rax; enum _SID_NAME_USE **
0x18000938e  mov     edx, 1; unsigned int
0x180009393  mov     rcx, rsi; void *
0x180009396  call    SamLookupNamesInDomain
0x18000939b  mov     ebx, eax
0x18000939d  test    eax, eax
0x18000939f  jns     short loc_1800093E2
0x1800093a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093a8  test    byte ptr [rcx+1Ch], 2
0x1800093ac  jz      short loc_1800093CC
0x1800093ae  cmp     byte ptr [rcx+19h], 2
0x1800093b2  jb      short loc_1800093CC
0x1800093b4  mov     rcx, [rcx+10h]
0x1800093b8  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800093bf  mov     edx, 125h
0x1800093c4  mov     r9d, eax
0x1800093c7  call    WPP_SF_D
0x1800093cc  cmp     ebx, 0C0000073h
0x1800093d2  jnz     loc_18000946A
0x1800093d8  mov     ebx, 0C0000064h
0x1800093dd  jmp     loc_18000946A
0x1800093e2  mov     r8, [rbp+57h+var_A8]
0x1800093e6  lea     r9, [rbp+57h+var_98]
0x1800093ea  mov     edx, 40h ; '@'
0x1800093ef  mov     rcx, rsi; void *
0x1800093f2  mov     r8d, [r8]
0x1800093f5  call    SamOpenUser
0x1800093fa  mov     rdi, [rbp+57h+var_98]
0x1800093fe  mov     ebx, eax
0x180009400  test    eax, eax
0x180009402  jns     short loc_18000941E
0x180009404  mov     rcx, cs:WPP_GLOBAL_Control
0x18000940b  test    byte ptr [rcx+1Ch], 2
0x18000940f  jz      short loc_18000945D
0x180009411  cmp     byte ptr [rcx+19h], 2
0x180009415  jb      short loc_18000945D
0x180009417  mov     edx, 126h
0x18000941c  jmp     short loc_18000944A
0x18000941e  mov     r8, r12; struct _UNICODE_STRING *
0x180009421  mov     rdx, r15; SourceString
0x180009424  mov     rcx, rdi; void *
0x180009427  call    SamChangePasswordUser
0x18000942c  mov     ebx, eax
0x18000942e  test    eax, eax
0x180009430  jns     short loc_18000945D
0x180009432  mov     rcx, cs:WPP_GLOBAL_Control
0x180009439  test    byte ptr [rcx+1Ch], 2
0x18000943d  jz      short loc_18000945D
0x18000943f  cmp     byte ptr [rcx+19h], 2
0x180009443  jb      short loc_18000945D
0x180009445  mov     edx, 127h
0x18000944a  mov     rcx, [rcx+10h]
0x18000944e  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180009455  mov     r9d, eax
0x180009458  call    WPP_SF_D
0x18000945d  test    rdi, rdi
0x180009460  jz      short loc_18000946A
0x180009462  mov     rcx, rdi; void *
0x180009465  call    SamCloseHandle
0x18000946a  test    rsi, rsi
0x18000946d  jz      short loc_180009477
0x18000946f  mov     rcx, rsi; void *
0x180009472  call    SamCloseHandle
0x180009477  mov     rcx, [rbp+57h+var_C0]; void *
0x18000947b  test    rcx, rcx
0x18000947e  jz      short loc_180009485
0x180009480  call    SamCloseHandle
0x180009485  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x180009489  test    rcx, rcx
0x18000948c  jz      short loc_180009494
0x18000948e  call    cs:__imp_LsaClose
0x180009494  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180009498  test    rcx, rcx
0x18000949b  jz      short loc_1800094A3
0x18000949d  call    cs:__imp_LsaFreeMemory
0x1800094a3  mov     rcx, [rbp+57h+var_A8]
0x1800094a7  test    rcx, rcx
0x1800094aa  jz      short loc_1800094B1
0x1800094ac  call    SamFreeMemory
0x1800094b1  mov     rcx, [rbp+57h+var_90]
0x1800094b5  test    rcx, rcx
0x1800094b8  jz      short loc_1800094BF
0x1800094ba  call    SamFreeMemory
0x1800094bf  mov     eax, ebx
0x1800094c1  mov     rcx, [rbp+57h+var_48]
0x1800094c5  xor     rcx, rsp; StackCookie
0x1800094c8  call    __security_check_cookie
0x1800094cd  add     rsp, 0B8h
0x1800094d4  pop     r15
0x1800094d6  pop     r14
0x1800094d8  pop     r13
0x1800094da  pop     r12
0x1800094dc  pop     rdi
0x1800094dd  pop     rsi
0x1800094de  pop     rbx
0x1800094df  pop     rbp
0x1800094e0  retn
```
