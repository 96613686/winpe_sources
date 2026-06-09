# LookupSids(ulong,void * *,_SID_INFO * *)

- ea: `0x180010ce4`
- end: `0x1800110a2`
- name: `?LookupSids@@YAJKPEAPEAXPEAPEAU_SID_INFO@@@Z`
- size: `958`
- prototype: `__int64 __fastcall(ULONG Count, PSID *Sids, struct _SID_INFO **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000ed10`
- `0x180011e80`

## callees

- `0x18000b290`
- `0x180010ce4`
- `0x180012ee8`
- `0x180012f18`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010ec2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010ec2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011013`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010eda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010eda`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180010d34`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180010d34`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x180010d62`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x180010d62`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180011048`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180011048`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180011034`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001103e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180011034`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001103e`

## pseudocode

```c
__int64 __fastcall LookupSids(ULONG Count, PSID *Sids, LPVOID *a3)
{
  __int64 v3; // rsi
  LPVOID *v4; // r15
  NTSTATUS v6; // ebx
  NTSTATUS v7; // eax
  int v8; // ebx
  unsigned int v9; // edi
  ULONG v10; // r8d
  unsigned int v11; // edi
  unsigned int Length; // edx
  unsigned int v13; // eax
  unsigned int v14; // edx
  __int64 v15; // rcx
  unsigned int v16; // edi
  unsigned int v17; // ecx
  unsigned int v18; // eax
  _QWORD *v19; // r14
  char *v20; // rax
  _DWORD *v21; // r11
  ULONG v22; // edi
  unsigned __int16 *i; // r12
  __int64 v24; // r13
  struct _UNICODE_STRING *v25; // rcx
  unsigned int v26; // edi
  _QWORD *v27; // r15
  __int64 v28; // r14
  SID_NAME_USE Use; // ecx
  __int64 v30; // rdx
  SID_NAME_USE v31; // ecx
  __int64 v32; // rax
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+30h] [rbp-50h] BYREF
  PVOID PolicyHandle; // [rsp+38h] [rbp-48h] BYREF
  _QWORD *v36; // [rsp+40h] [rbp-40h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  PLSA_TRANSLATED_NAME Names; // [rsp+D8h] [rbp+58h] BYREF

  v3 = Count;
  *a3 = 0;
  v4 = a3;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v6 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle);
  if ( v6 >= 0 )
  {
    ReferencedDomains = 0;
    Names = 0;
    v7 = LsaLookupSids(PolicyHandle, v3, Sids, &ReferencedDomains, &Names);
    if ( v7 < 0 )
    {
      if ( v7 == -1073741427 )
      {
        v8 = -805305971;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43);
      }
      else if ( v7 == -1073741709 )
      {
        *v4 = 0;
        v8 = 0;
      }
      else
      {
        v8 = v7 | 0x10000000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            44,
            WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
            (unsigned int)v8);
      }
      goto LABEL_51;
    }
    v9 = 24 * v3;
    v8 = 0;
    if ( ReferencedDomains->Entries )
    {
      v10 = 0;
      do
      {
        if ( v8 < 0 )
          break;
        v11 = v9 + 2;
        if ( v11 < 2 )
        {
          v9 = -1;
          v8 = -2147024362;
        }
        else
        {
          Length = ReferencedDomains->Domains[v10].Name.Length;
          v13 = Length + v11;
          v9 = -1;
          if ( v13 >= Length )
            v9 = v13;
          v8 = v13 < Length ? 0x80070216 : 0;
        }
        ++v10;
      }
      while ( v10 < ReferencedDomains->Entries );
    }
    v14 = 0;
    if ( (_DWORD)v3 )
    {
      while ( v8 >= 0 )
      {
        v15 = v14;
        if ( (unsigned int)(Names[v15].Use - 7) > 1 )
        {
          v16 = v9 + 2;
          if ( v16 < 2 )
          {
            v9 = -1;
            v8 = -2147024362;
          }
          else
          {
            v17 = Names[v15].Name.Length;
            v18 = v17 + v16;
            v9 = -1;
            if ( v18 >= v17 )
              v9 = v18;
            v8 = v18 < v17 ? 0x80070216 : 0;
          }
        }
        if ( ++v14 >= (unsigned int)v3 )
          goto LABEL_30;
      }
    }
    else
    {
LABEL_30:
      if ( v8 >= 0 )
      {
        v36 = LocalAlloc(0, 8LL * ReferencedDomains->Entries);
        v19 = v36;
        if ( v36 )
        {
          v20 = (char *)CoTaskMemAlloc(v9);
          v21 = v20;
          if ( v20 )
          {
            v22 = 0;
            for ( i = (unsigned __int16 *)&v20[24 * v3];
                  v22 < ReferencedDomains->Entries;
                  i = (unsigned __int16 *)((char *)i + ReferencedDomains->Domains[v24].Name.Length + 2) )
            {
              v19[v22] = i;
              v24 = v22;
              v25 = (struct _UNICODE_STRING *)&ReferencedDomains->Domains[v22];
              v8 = CopyUstrToPstr(v25, i, (unsigned int)v25->Length + 2);
              if ( v8 < 0 )
                break;
              ++v22;
            }
            v26 = 0;
            if ( (_DWORD)v3 )
            {
              v27 = v19;
              do
              {
                v28 = v26;
                Use = Names[v28].Use;
                if ( (unsigned int)(Use - 7) <= 1 )
                {
                  v32 = 3LL * v26;
                  v21[2 * v32] = Use;
                  *(_QWORD *)&v21[2 * v32 + 4] = 0;
                  *(_QWORD *)&v21[2 * v32 + 2] = 0;
                }
                else
                {
                  v8 = CopyUstrToPstr(
                         (struct _UNICODE_STRING *const)&Names[v28].Name,
                         i,
                         (unsigned int)Names[v28].Name.Length + 2);
                  if ( v8 < 0 )
                    break;
                  v30 = 3LL * v26;
                  v31 = Names[v28].Use;
                  *(_QWORD *)&v21[2 * v30 + 4] = i;
                  v21[2 * v30] = v31;
                  *(_QWORD *)&v21[2 * v30 + 2] = v27[Names[v28].DomainIndex];
                  i = (unsigned __int16 *)((char *)i + Names[v28].Name.Length + 2);
                }
                ++v26;
              }
              while ( v26 < (unsigned int)v3 );
              v4 = a3;
              v19 = v36;
            }
            *v4 = v21;
          }
          else
          {
            v8 = -2147024882;
          }
          LocalFree(v19);
          if ( v8 >= 0 )
            goto LABEL_50;
        }
        else
        {
          v8 = -2147024882;
        }
      }
    }
    CoTaskMemFree(*v4);
    *v4 = 0;
LABEL_50:
    LsaFreeMemory(ReferencedDomains);
    LsaFreeMemory(Names);
LABEL_51:
    LsaClose(PolicyHandle);
    return (unsigned int)v8;
  }
  v8 = v6 | 0x10000000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010ce4  mov     [rsp-38h+arg_0], rbx
0x180010ce9  mov     [rsp-38h+arg_10], r8
0x180010cee  push    rbp
0x180010cef  push    rsi
0x180010cf0  push    rdi
0x180010cf1  push    r12
0x180010cf3  push    r13
0x180010cf5  push    r14
0x180010cf7  push    r15
0x180010cf9  mov     rbp, rsp
0x180010cfc  sub     rsp, 80h
0x180010d03  xorps   xmm0, xmm0
0x180010d06  mov     esi, ecx
0x180010d08  xor     r13d, r13d
0x180010d0b  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180010d0f  mov     [r8], r13
0x180010d12  mov     r15, r8
0x180010d15  mov     rdi, rdx
0x180010d18  mov     [rbp+PolicyHandle], r13
0x180010d1c  mov     r8d, 800h; DesiredAccess
0x180010d22  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180010d26  xor     ecx, ecx; SystemName
0x180010d28  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180010d2c  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180010d30  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180010d34  call    cs:__imp_LsaOpenPolicy
0x180010d3a  mov     ebx, eax
0x180010d3c  test    eax, eax
0x180010d3e  js      loc_180011050
0x180010d44  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180010d48  lea     rax, [rbp+arg_18]
0x180010d4c  lea     r9, [rbp+ReferencedDomains]; ReferencedDomains
0x180010d50  mov     [rsp+80h+Names], rax; Names
0x180010d55  mov     r8, rdi; Sids
0x180010d58  mov     [rbp+ReferencedDomains], r13
0x180010d5c  mov     edx, esi; Count
0x180010d5e  mov     [rbp+arg_18], r13
0x180010d62  call    cs:__imp_LsaLookupSids
0x180010d68  mov     ebx, eax
0x180010d6a  test    eax, eax
0x180010d6c  jns     loc_180010E06
0x180010d72  cmp     eax, 0C000018Dh
0x180010d77  jnz     short loc_180010DB1
0x180010d79  mov     ebx, 0D000018Dh
0x180010d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d85  lea     rax, WPP_GLOBAL_Control
0x180010d8c  cmp     rcx, rax
0x180010d8f  jz      loc_180011044
0x180010d95  test    byte ptr [rcx+1Ch], 4
0x180010d99  jz      loc_180011044
0x180010d9f  mov     rcx, [rcx+10h]
0x180010da3  lea     edx, [r13+2Bh]
0x180010da7  call    WPP_SF_
0x180010dac  jmp     loc_180011044
0x180010db1  cmp     ebx, 0C0000073h
0x180010db7  jnz     short loc_180010DC4
0x180010db9  mov     [r15], r13
0x180010dbc  mov     ebx, r13d
0x180010dbf  jmp     loc_180011044
0x180010dc4  bts     ebx, 1Ch
0x180010dc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180010dcf  lea     rax, WPP_GLOBAL_Control
0x180010dd6  cmp     rcx, rax
0x180010dd9  jz      loc_180011044
0x180010ddf  test    byte ptr [rcx+1Ch], 2
0x180010de3  jz      loc_180011044
0x180010de9  mov     rcx, [rcx+10h]
0x180010ded  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180010df4  mov     edx, 2Ch ; ','
0x180010df9  mov     r9d, ebx
0x180010dfc  call    WPP_SF_d
0x180010e01  jmp     loc_180011044
0x180010e06  mov     r9, [rbp+ReferencedDomains]
0x180010e0a  lea     edi, [rsi+rsi*2]
0x180010e0d  shl     edi, 3
0x180010e10  or      r10d, 0FFFFFFFFh
0x180010e14  mov     ebx, r13d
0x180010e17  mov     r11d, 80070216h
0x180010e1d  cmp     [r9], r13d
0x180010e20  jbe     short loc_180010E60
0x180010e22  mov     r8d, r13d
0x180010e25  test    ebx, ebx
0x180010e27  js      short loc_180010E60
0x180010e29  add     edi, 2
0x180010e2c  cmp     edi, 2
0x180010e2f  jb      short loc_180010E52
0x180010e31  mov     eax, r8d
0x180010e34  lea     rcx, [rax+rax*2]
0x180010e38  mov     rax, [r9+8]
0x180010e3c  movzx   edx, word ptr [rax+rcx*8]
0x180010e40  lea     eax, [rdx+rdi]
0x180010e43  mov     edi, r10d
0x180010e46  cmp     eax, edx
0x180010e48  cmovnb  edi, eax
0x180010e4b  sbb     ebx, ebx
0x180010e4d  and     ebx, r11d
0x180010e50  jmp     short loc_180010E58
0x180010e52  mov     edi, r10d
0x180010e55  mov     ebx, r11d
0x180010e58  inc     r8d
0x180010e5b  cmp     r8d, [r9]
0x180010e5e  jb      short loc_180010E25
0x180010e60  mov     edx, r13d
0x180010e63  test    esi, esi
0x180010e65  jz      short loc_180010EB1
0x180010e67  mov     r8, [rbp+arg_18]
0x180010e6b  test    ebx, ebx
0x180010e6d  js      loc_180011024
0x180010e73  mov     ecx, edx
0x180010e75  shl     rcx, 5
0x180010e79  mov     eax, [rcx+r8]
0x180010e7d  sub     eax, 7
0x180010e80  cmp     eax, 1
0x180010e83  jbe     short loc_180010EAB
0x180010e85  add     edi, 2
0x180010e88  cmp     edi, 2
0x180010e8b  jb      short loc_180010EA5
0x180010e8d  movzx   ecx, word ptr [rcx+r8+8]
0x180010e93  lea     eax, [rcx+rdi]
0x180010e96  mov     edi, r10d
0x180010e99  cmp     eax, ecx
0x180010e9b  cmovnb  edi, eax
0x180010e9e  sbb     ebx, ebx
0x180010ea0  and     ebx, r11d
0x180010ea3  jmp     short loc_180010EAB
0x180010ea5  mov     edi, r10d
0x180010ea8  mov     ebx, r11d
0x180010eab  inc     edx
0x180010ead  cmp     edx, esi
0x180010eaf  jb      short loc_180010E6B
0x180010eb1  test    ebx, ebx
0x180010eb3  js      loc_180011024
0x180010eb9  mov     edx, [r9]
0x180010ebc  xor     ecx, ecx; uFlags
0x180010ebe  shl     rdx, 3; uBytes
0x180010ec2  call    cs:__imp_LocalAlloc
0x180010ec8  mov     [rbp+var_40], rax
0x180010ecc  mov     r14, rax
0x180010ecf  test    rax, rax
0x180010ed2  jz      loc_18001101F
0x180010ed8  mov     ecx, edi; cb
0x180010eda  call    cs:__imp_CoTaskMemAlloc
0x180010ee0  mov     r11, rax
0x180010ee3  test    rax, rax
0x180010ee6  jz      loc_18001100B
0x180010eec  lea     rcx, [rsi+rsi*2]
0x180010ef0  mov     edi, r13d
0x180010ef3  lea     r12, [rax+rcx*8]
0x180010ef7  mov     rax, [rbp+ReferencedDomains]
0x180010efb  cmp     [rax], r13d
0x180010efe  jbe     short loc_180010F4A
0x180010f00  mov     eax, edi
0x180010f02  mov     rdx, r12; unsigned __int16 *
0x180010f05  mov     [r14+rax*8], r12
0x180010f09  lea     r13, [rax+rax*2]
0x180010f0d  mov     rax, [rbp+ReferencedDomains]
0x180010f11  mov     rcx, [rax+8]
0x180010f15  lea     rcx, [rcx+r13*8]; struct _UNICODE_STRING *
0x180010f19  movzx   r8d, word ptr [rcx]
0x180010f1d  add     r8d, 2; unsigned int
0x180010f21  call    ?CopyUstrToPstr@@YAJQEAU_UNICODE_STRING@@PEAGK@Z; CopyUstrToPstr(_UNICODE_STRING * const,ushort *,ulong)
0x180010f26  mov     ebx, eax
0x180010f28  test    eax, eax
0x180010f2a  js      short loc_180010F47
0x180010f2c  mov     r8, [rbp+ReferencedDomains]
0x180010f30  add     r12, 2
0x180010f34  inc     edi
0x180010f36  mov     rcx, [r8+8]
0x180010f3a  movzx   edx, word ptr [rcx+r13*8]
0x180010f3f  add     r12, rdx
0x180010f42  cmp     edi, [r8]
0x180010f45  jb      short loc_180010F00
0x180010f47  xor     r13d, r13d
0x180010f4a  mov     edi, r13d
0x180010f4d  test    esi, esi
0x180010f4f  jz      loc_180011006
0x180010f55  mov     r15, r14
0x180010f58  mov     rdx, [rbp+arg_18]
0x180010f5c  mov     r14d, edi
0x180010f5f  shl     r14, 5
0x180010f63  mov     r13d, edi
0x180010f66  mov     ecx, [r14+rdx]
0x180010f6a  lea     eax, [rcx-7]
0x180010f6d  cmp     eax, 1
0x180010f70  jbe     short loc_180010FD0
0x180010f72  lea     rcx, [rdx+8]
0x180010f76  mov     rdx, r12; unsigned __int16 *
0x180010f79  add     rcx, r14; struct _UNICODE_STRING *
0x180010f7c  movzx   r8d, word ptr [rcx]
0x180010f80  add     r8d, 2; unsigned int
0x180010f84  call    ?CopyUstrToPstr@@YAJQEAU_UNICODE_STRING@@PEAGK@Z; CopyUstrToPstr(_UNICODE_STRING * const,ushort *,ulong)
0x180010f89  mov     ebx, eax
0x180010f8b  test    eax, eax
0x180010f8d  js      short loc_180010FFB
0x180010f8f  mov     rax, [rbp+arg_18]
0x180010f93  lea     rdx, ds:0[r13*2]
0x180010f9b  add     rdx, r13
0x180010f9e  mov     ecx, [r14+rax]
0x180010fa2  mov     [r11+rdx*8+10h], r12
0x180010fa7  add     r12, 2
0x180010fab  mov     [r11+rdx*8], ecx
0x180010faf  mov     rax, [rbp+arg_18]
0x180010fb3  movsxd  rcx, dword ptr [r14+rax+18h]
0x180010fb8  mov     rax, [r15+rcx*8]
0x180010fbc  mov     [r11+rdx*8+8], rax
0x180010fc1  mov     rax, [rbp+arg_18]
0x180010fc5  movzx   ecx, word ptr [r14+rax+8]
0x180010fcb  add     r12, rcx
0x180010fce  jmp     short loc_180010FF1
0x180010fd0  lea     rax, ds:0[r13*2]
0x180010fd8  add     rax, r13
0x180010fdb  mov     [r11+rax*8], ecx
0x180010fdf  mov     qword ptr [r11+rax*8+10h], 0
0x180010fe8  mov     qword ptr [r11+rax*8+8], 0
0x180010ff1  inc     edi
0x180010ff3  cmp     edi, esi
0x180010ff5  jb      loc_180010F58
0x180010ffb  mov     r15, [rbp+arg_10]
0x180010fff  xor     r13d, r13d
0x180011002  mov     r14, [rbp+var_40]
0x180011006  mov     [r15], r11
0x180011009  jmp     short loc_180011010
0x18001100b  mov     ebx, 8007000Eh
0x180011010  mov     rcx, r14; hMem
0x180011013  call    cs:__imp_LocalFree
0x180011019  test    ebx, ebx
0x18001101b  jns     short loc_180011030
0x18001101d  jmp     short loc_180011024
0x18001101f  mov     ebx, 8007000Eh
0x180011024  mov     rcx, [r15]; pv
0x180011027  call    cs:__imp_CoTaskMemFree
0x18001102d  mov     [r15], r13
0x180011030  mov     rcx, [rbp+ReferencedDomains]; Buffer
0x180011034  call    cs:__imp_LsaFreeMemory
0x18001103a  mov     rcx, [rbp+arg_18]; Buffer
0x18001103e  call    cs:__imp_LsaFreeMemory
0x180011044  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180011048  call    cs:__imp_LsaClose
0x18001104e  jmp     short loc_180011085
0x180011050  bts     ebx, 1Ch
0x180011054  mov     rcx, cs:WPP_GLOBAL_Control
0x18001105b  lea     rax, WPP_GLOBAL_Control
0x180011062  cmp     rcx, rax
0x180011065  jz      short loc_180011085
0x180011067  test    byte ptr [rcx+1Ch], 2
0x18001106b  jz      short loc_180011085
0x18001106d  mov     rcx, [rcx+10h]
0x180011071  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180011078  mov     edx, 2Dh ; '-'
0x18001107d  mov     r9d, ebx
0x180011080  call    WPP_SF_d
0x180011085  mov     eax, ebx
0x180011087  mov     rbx, [rsp+80h+arg_0]
0x18001108f  add     rsp, 80h
0x180011096  pop     r15
0x180011098  pop     r14
0x18001109a  pop     r13
0x18001109c  pop     r12
0x18001109e  pop     rdi
0x18001109f  pop     rsi
0x1800110a0  pop     rbp
0x1800110a1  retn
```
