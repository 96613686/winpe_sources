# SampGetPasswordPolicyInfo(_UNICODE_STRING *,_DOMAIN_PASSWORD_INFORMATION * *)

- ea: `0x18000a5a0`
- end: `0x18000a837`
- name: `?SampGetPasswordPolicyInfo@@YAJPEAU_UNICODE_STRING@@PEAPEAU_DOMAIN_PASSWORD_INFORMATION@@@Z`
- size: `663`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _DOMAIN_PASSWORD_INFORMATION **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013b70`

## callees

- `0x180001010`
- `0x1800011f0`
- `0x180001800`
- `0x180002a80`
- `0x180004dd0`
- `0x180006620`
- `0x18000807c`
- `0x18000a5a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a7a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a7a9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000a80c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000a80c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000a7fd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000a7fd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000a677`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000a677`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000a626`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000a626`

## pseudocode

```c
__int64 __fastcall SampGetPasswordPolicyInfo(struct _LSA_UNICODE_STRING *a1, struct _DOMAIN_PASSWORD_INFORMATION **a2)
{
  void *v4; // rdi
  NTSTATUS InformationDomain; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  struct _DOMAIN_PASSWORD_INFORMATION *v10; // rax
  struct _DOMAIN_PASSWORD_INFORMATION *v11; // rcx
  _OWORD *v12; // rax
  void *v14; // [rsp+20h] [rbp-69h] BYREF
  _OWORD *v15; // [rsp+28h] [rbp-61h]
  void *v16; // [rsp+30h] [rbp-59h] BYREF
  PVOID Buffer; // [rsp+38h] [rbp-51h] BYREF
  PVOID PolicyHandle; // [rsp+40h] [rbp-49h] BYREF
  __int128 v19; // [rsp+48h] [rbp-41h] BYREF
  __int128 v20; // [rsp+58h] [rbp-31h]
  __int128 v21; // [rsp+68h] [rbp-21h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF
  __int64 v23; // [rsp+A8h] [rbp+1Fh] BYREF
  int v24; // [rsp+B0h] [rbp+27h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a2 = 0;
  v16 = 0;
  v23 = 0;
  v24 = 0;
  v14 = 0;
  PolicyHandle = 0;
  v19 = 0;
  v4 = 0;
  Buffer = 0;
  v20 = 0;
  v15 = 0;
  v21 = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  InformationDomain = LsaOpenPolicy(a1, &ObjectAttributes, 1u, &PolicyHandle);
  v6 = InformationDomain;
  if ( InformationDomain >= 0 )
  {
    InformationDomain = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
    v6 = InformationDomain;
    if ( InformationDomain >= 0 )
    {
      LODWORD(v19) = 48;
      *((_QWORD *)&v21 + 1) = &v23;
      *((_QWORD *)&v19 + 1) = 0;
      DWORD2(v20) = 0;
      *(_QWORD *)&v20 = 0;
      *(_QWORD *)&v21 = 0;
      v23 = 0x10000000CLL;
      LOWORD(v24) = 0;
      InformationDomain = SamConnect(a1, &v16, 32, &v19);
      v6 = InformationDomain;
      if ( InformationDomain >= 0 )
      {
        v9 = SamOpenDomain(v16, 1, *((PSID *)Buffer + 2), (__int64 *)&v14);
        v6 = v9;
        if ( v9 >= 0 )
        {
          v4 = v14;
          InformationDomain = SamQueryInformationDomain(v14);
          v6 = InformationDomain;
          if ( InformationDomain >= 0 )
          {
            v10 = (struct _DOMAIN_PASSWORD_INFORMATION *)LocalAlloc(0x40u, 0x18u);
            *a2 = v10;
            v11 = v10;
            if ( v10 )
            {
              v12 = v15;
              *(_OWORD *)&v11->MinPasswordLength = *v15;
              v11->MinPasswordAge.QuadPart = *((_QWORD *)v12 + 2);
            }
            else
            {
              v6 = -1073741801;
            }
          }
          else
          {
            v7 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v8 = 422;
              goto LABEL_5;
            }
          }
        }
        else
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              421,
              &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
              (unsigned int)v9);
          v4 = v14;
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 420;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 419;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 418;
LABEL_5:
      WPP_SF_D(v7[2], v8, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, (unsigned int)InformationDomain);
    }
  }
  SamFreeMemory(v15);
  if ( v4 )
    SamCloseHandle(v4);
  if ( v16 )
    SamCloseHandle(v16);
  LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v6;
}

```

## disassembly

```asm
0x18000a5a0  mov     [rsp-8+arg_10], rbx
0x18000a5a5  push    rbp
0x18000a5a6  push    rsi
0x18000a5a7  push    rdi
0x18000a5a8  push    r14
0x18000a5aa  push    r15
0x18000a5ac  lea     rbp, [rsp-37h]
0x18000a5b1  sub     rsp, 0C0h
0x18000a5b8  mov     rax, cs:__security_cookie
0x18000a5bf  xor     rax, rsp
0x18000a5c2  mov     [rbp+57h+var_28], rax
0x18000a5c6  xor     r15d, r15d
0x18000a5c9  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000a5d1  xorps   xmm0, xmm0
0x18000a5d4  mov     [rdx], r15
0x18000a5d7  xor     eax, eax
0x18000a5d9  mov     [rbp+57h+var_B0], r15
0x18000a5dd  mov     rsi, rdx
0x18000a5e0  mov     [rbp+57h+var_38], rax
0x18000a5e4  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000a5e8  mov     [rbp+57h+var_30], eax
0x18000a5eb  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000a5ef  mov     [rbp+57h+var_C0], r15
0x18000a5f3  lea     r8d, [rax+1]; DesiredAccess
0x18000a5f7  mov     [rbp+57h+PolicyHandle], r15
0x18000a5fb  mov     r14, rcx
0x18000a5fe  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r15
0x18000a602  movups  [rbp+57h+var_98], xmm0
0x18000a606  mov     edi, r15d
0x18000a609  mov     [rbp+57h+Buffer], r15
0x18000a60d  movups  [rbp+57h+var_88], xmm0
0x18000a611  mov     [rbp+57h+var_B8], r15
0x18000a615  movups  [rbp+57h+var_78], xmm0
0x18000a619  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x18000a61d  mov     [rbp+57h+ObjectAttributes.ObjectName], r15
0x18000a621  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a626  call    cs:__imp_LsaOpenPolicy
0x18000a62c  mov     ebx, eax
0x18000a62e  test    eax, eax
0x18000a630  jns     short loc_18000A66A
0x18000a632  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a639  test    byte ptr [rcx+1Ch], 2
0x18000a63d  jz      loc_18000A7D5
0x18000a643  cmp     byte ptr [rcx+19h], 2
0x18000a647  jb      loc_18000A7D5
0x18000a64d  mov     edx, 1A2h
0x18000a652  mov     rcx, [rcx+10h]
0x18000a656  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000a65d  mov     r9d, eax
0x18000a660  call    WPP_SF_D
0x18000a665  jmp     loc_18000A7D5
0x18000a66a  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000a66e  lea     r8, [rbp+57h+Buffer]; Buffer
0x18000a672  mov     edx, 5; InformationClass
0x18000a677  call    cs:__imp_LsaQueryInformationPolicy
0x18000a67d  mov     ebx, eax
0x18000a67f  test    eax, eax
0x18000a681  jns     short loc_18000A6A5
0x18000a683  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a68a  test    byte ptr [rcx+1Ch], 2
0x18000a68e  jz      loc_18000A7D5
0x18000a694  cmp     byte ptr [rcx+19h], 2
0x18000a698  jb      loc_18000A7D5
0x18000a69e  mov     edx, 1A3h
0x18000a6a3  jmp     short loc_18000A652
0x18000a6a5  lea     rax, [rbp+57h+var_38]
0x18000a6a9  mov     dword ptr [rbp+57h+var_98], 30h ; '0'
0x18000a6b0  lea     r9, [rbp+57h+var_98]
0x18000a6b4  mov     qword ptr [rbp+57h+var_78+8], rax
0x18000a6b8  mov     r8d, 20h ; ' '
0x18000a6be  mov     qword ptr [rbp+57h+var_98+8], r15
0x18000a6c2  lea     rdx, [rbp+57h+var_B0]
0x18000a6c6  mov     dword ptr [rbp+57h+var_88+8], r15d
0x18000a6ca  mov     rcx, r14
0x18000a6cd  mov     qword ptr [rbp+57h+var_88], r15
0x18000a6d1  mov     qword ptr [rbp+57h+var_78], r15
0x18000a6d5  mov     dword ptr [rbp+57h+var_38], 0Ch
0x18000a6dc  mov     dword ptr [rbp+57h+var_38+4], 1
0x18000a6e3  mov     word ptr [rbp+57h+var_30], r15w
0x18000a6e8  call    SamConnect
0x18000a6ed  mov     ebx, eax
0x18000a6ef  test    eax, eax
0x18000a6f1  jns     short loc_18000A718
0x18000a6f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6fa  test    byte ptr [rcx+1Ch], 2
0x18000a6fe  jz      loc_18000A7D5
0x18000a704  cmp     byte ptr [rcx+19h], 2
0x18000a708  jb      loc_18000A7D5
0x18000a70e  mov     edx, 1A4h
0x18000a713  jmp     loc_18000A652
0x18000a718  mov     r8, [rbp+57h+Buffer]
0x18000a71c  lea     r9, [rbp+57h+var_C0]
0x18000a720  mov     rcx, [rbp+57h+var_B0]; void *
0x18000a724  mov     edx, 1; char
0x18000a729  mov     r8, [r8+10h]; pSid
0x18000a72d  call    SamOpenDomain
0x18000a732  mov     ebx, eax
0x18000a734  test    eax, eax
0x18000a736  jns     short loc_18000A769
0x18000a738  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a73f  test    byte ptr [rcx+1Ch], 2
0x18000a743  jz      short loc_18000A763
0x18000a745  cmp     byte ptr [rcx+19h], 2
0x18000a749  jb      short loc_18000A763
0x18000a74b  mov     rcx, [rcx+10h]
0x18000a74f  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000a756  mov     edx, 1A5h
0x18000a75b  mov     r9d, eax
0x18000a75e  call    WPP_SF_D
0x18000a763  mov     rdi, [rbp+57h+var_C0]
0x18000a767  jmp     short loc_18000A7D5
0x18000a769  mov     rdi, [rbp+57h+var_C0]
0x18000a76d  lea     r8, [rbp+57h+var_B8]
0x18000a771  mov     rcx, rdi; void *
0x18000a774  mov     edx, 1
0x18000a779  call    SamQueryInformationDomain
0x18000a77e  mov     ebx, eax
0x18000a780  test    eax, eax
0x18000a782  jns     short loc_18000A7A1
0x18000a784  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a78b  test    byte ptr [rcx+1Ch], 2
0x18000a78f  jz      short loc_18000A7D5
0x18000a791  cmp     byte ptr [rcx+19h], 2
0x18000a795  jb      short loc_18000A7D5
0x18000a797  mov     edx, 1A6h
0x18000a79c  jmp     loc_18000A652
0x18000a7a1  mov     edx, 18h; uBytes
0x18000a7a6  lea     ecx, [rdx+28h]; uFlags
0x18000a7a9  call    cs:__imp_LocalAlloc
0x18000a7af  mov     [rsi], rax
0x18000a7b2  mov     rcx, rax
0x18000a7b5  test    rax, rax
0x18000a7b8  jnz     short loc_18000A7C1
0x18000a7ba  mov     ebx, 0C0000017h
0x18000a7bf  jmp     short loc_18000A7D5
0x18000a7c1  mov     rax, [rbp+57h+var_B8]
0x18000a7c5  movups  xmm0, xmmword ptr [rax]
0x18000a7c8  movups  xmmword ptr [rcx], xmm0
0x18000a7cb  movsd   xmm1, qword ptr [rax+10h]
0x18000a7d0  movsd   qword ptr [rcx+10h], xmm1
0x18000a7d5  mov     rcx, [rbp+57h+var_B8]
0x18000a7d9  call    SamFreeMemory
0x18000a7de  test    rdi, rdi
0x18000a7e1  jz      short loc_18000A7EB
0x18000a7e3  mov     rcx, rdi; void *
0x18000a7e6  call    SamCloseHandle
0x18000a7eb  mov     rcx, [rbp+57h+var_B0]; void *
0x18000a7ef  test    rcx, rcx
0x18000a7f2  jz      short loc_18000A7F9
0x18000a7f4  call    SamCloseHandle
0x18000a7f9  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18000a7fd  call    cs:__imp_LsaFreeMemory
0x18000a803  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18000a807  test    rcx, rcx
0x18000a80a  jz      short loc_18000A812
0x18000a80c  call    cs:__imp_LsaClose
0x18000a812  mov     eax, ebx
0x18000a814  mov     rcx, [rbp+57h+var_28]
0x18000a818  xor     rcx, rsp; StackCookie
0x18000a81b  call    __security_check_cookie
0x18000a820  mov     rbx, [rsp+0E0h+arg_10]
0x18000a828  add     rsp, 0C0h
0x18000a82f  pop     r15
0x18000a831  pop     r14
0x18000a833  pop     rdi
0x18000a834  pop     rsi
0x18000a835  pop     rbp
0x18000a836  retn
```
