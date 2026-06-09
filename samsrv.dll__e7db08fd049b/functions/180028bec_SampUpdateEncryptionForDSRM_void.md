# SampUpdateEncryptionForDSRM(void)

- ea: `0x180028bec`
- end: `0x1800290e3`
- name: `?SampUpdateEncryptionForDSRM@@YAJXZ`
- size: `1271`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180094c94`

## callees

- `0x1800022a0`
- `0x180003d40`
- `0x1800066f0`
- `0x180006800`
- `0x180007080`
- `0x18000e7f0`
- `0x180011810`
- `0x1800270e0`
- `0x180027c30`
- `0x180027e24`
- `0x180027e70`
- `0x180028bec`
- `0x1800290f0`
- `0x18002cd80`
- `0x180065b60`
- `0x18006a96c`
- `0x18009fd08`

## import_xrefs

- `ntdll!RtlpNtOpenKey` at `0x180028dcc`
- `ntdll!RtlpNtOpenKey` at `0x180028dcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028eff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ffa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029007`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002908f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028eff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ffa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029007`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002908f`

## pseudocode

```c
__int64 SampUpdateEncryptionForDSRM(void)
{
  _QWORD *v0; // r14
  _DWORD *v1; // rdi
  __int64 v2; // rcx
  NTSTATUS UserAccountSettings; // ebx
  bool v4; // r15
  __int64 v5; // rsi
  int v6; // eax
  unsigned int v7; // r13d
  __int64 Context; // rax
  int v9; // ecx
  int PrivateUserData; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  NTSTATUS v13; // eax
  _BYTE *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  NTSTATUS v18; // eax
  _BYTE *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  NTSTATUS v23; // eax
  _BYTE *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  NTSTATUS v28; // eax
  _BYTE *v29; // rcx
  __int64 v30; // rax
  HLOCAL hMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v34; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v35; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v36; // [rsp+80h] [rbp-80h] BYREF
  ULONG v37; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v38; // [rsp+8Ch] [rbp-74h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  struct _DOMAIN_PASSWORD_INFORMATION v40[2]; // [rsp+C0h] [rbp-40h] BYREF

  v37 = 0;
  v0 = 0;
  v36 = 0;
  v1 = 0;
  v34 = 0;
  v2 = *((_QWORD *)SampDefinedDomains + 170);
  v38 = 0;
  v35 = 0;
  UserAccountSettings = SampAcquireWriteLock(v2);
  if ( UserAccountSettings >= 0 )
  {
    v4 = 0;
    SampSetTransactionWithinDomain(0);
    SampSetTransactionDomain(1);
LABEL_3:
    v5 = 0;
    if ( !v4 )
    {
      v33 = 0;
      *(_OWORD *)hMem = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      v6 = SampEnumerateAccountNamesRegistry(4u, &v37, 0, &v36, 0xFFFFu, 0, &v34, 1);
      v0 = v36;
      UserAccountSettings = v6;
      if ( v6 < 0 )
      {
        v5 = 0;
      }
      else
      {
        v7 = 0;
        v4 = v6 != 261;
        while ( 1 )
        {
          if ( v7 >= v34 )
          {
            SamIFree_SAMPR_ENUMERATION_BUFFER(v0);
            v0 = 0;
            v36 = 0;
            goto LABEL_3;
          }
          memset(v40, 0, sizeof(v40));
          Context = SampCreateContextEx(4u, 1, 1, 0, 1, 1, 0, 0, 1u);
          v5 = Context;
          if ( !Context )
            break;
          v9 = *(_DWORD *)(Context + 192);
          *(_QWORD *)(Context + 176) = 0;
          *(_DWORD *)(Context + 200) = 1;
          *(_DWORD *)(Context + 192) = v9 & 0xFFFFFFFC | 1;
          *(_DWORD *)(Context + 148) = 985087;
          *(_DWORD *)(Context + 248) = *(_DWORD *)(v0[1] + 24LL * v7);
          UserAccountSettings = SampBuildAccountSubKeyName(4, Context + 160, *(unsigned int *)(v0[1] + 24LL * v7));
          if ( UserAccountSettings < 0 )
            goto LABEL_38;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)(v5 + 160);
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = SampKey;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          UserAccountSettings = RtlpNtOpenKey((HANDLE)(v5 + 152), 0x2001Fu, &ObjectAttributes, 0);
          if ( UserAccountSettings < 0 )
          {
            *(_QWORD *)(v5 + 152) = -1;
            goto LABEL_38;
          }
          UserAccountSettings = SampGetUserAccountSettings((struct _SAMP_OBJECT *)v5, v40);
          if ( UserAccountSettings < 0 )
            goto LABEL_38;
          PrivateUserData = SampGetPrivateUserData((struct _SAMP_OBJECT *)v5, v40, &v38, &v35);
          v1 = v35;
          UserAccountSettings = PrivateUserData;
          if ( PrivateUserData < 0 )
            goto LABEL_38;
          LODWORD(v33) = *((_DWORD *)v35 + 1);
          *((_QWORD *)&v33 + 1) = (char *)v35 + 12;
          UserAccountSettings = SampEncryptDSRMPassword(hMem, v11, v12, &v33);
          if ( UserAccountSettings < 0 )
            goto LABEL_38;
          v13 = SampSetUnicodeStringAttribute((struct _SAMP_OBJECT *)v5, 0xDu);
          v14 = hMem[1];
          UserAccountSettings = v13;
          v15 = LOWORD(hMem[0]);
          if ( LOWORD(hMem[0]) )
          {
            do
            {
              *v14++ = 0;
              --v15;
            }
            while ( v15 );
            v14 = hMem[1];
          }
          LocalFree(v14);
          if ( UserAccountSettings < 0 )
            goto LABEL_38;
          LODWORD(v33) = v1[7];
          *((_QWORD *)&v33 + 1) = v1 + 9;
          UserAccountSettings = SampEncryptDSRMPassword(hMem, v16, v17, &v33);
          if ( UserAccountSettings < 0 )
            goto LABEL_38;
          v18 = SampSetUnicodeStringAttribute((struct _SAMP_OBJECT *)v5, 0xEu);
          v19 = hMem[1];
          UserAccountSettings = v18;
          v20 = LOWORD(hMem[0]);
          if ( LOWORD(hMem[0]) )
          {
            do
            {
              *v19++ = 0;
              --v20;
            }
            while ( v20 );
            v19 = hMem[1];
          }
          LocalFree(v19);
          if ( UserAccountSettings < 0 )
            goto LABEL_38;
          LODWORD(v33) = v1[15];
          *((_QWORD *)&v33 + 1) = v1 + 17;
          UserAccountSettings = SampEncryptDSRMPassword(hMem, v21, v22, &v33);
          if ( UserAccountSettings < 0 )
            goto LABEL_38;
          v23 = SampSetUnicodeStringAttribute((struct _SAMP_OBJECT *)v5, 0xFu);
          v24 = hMem[1];
          UserAccountSettings = v23;
          v25 = LOWORD(hMem[0]);
          if ( LOWORD(hMem[0]) )
          {
            do
            {
              *v24++ = 0;
              --v25;
            }
            while ( v25 );
            v24 = hMem[1];
          }
          LocalFree(v24);
          if ( UserAccountSettings < 0 )
            goto LABEL_38;
          LODWORD(v33) = v1[13];
          *((_QWORD *)&v33 + 1) = (char *)v1 + *((unsigned __int16 *)v1 + 30) + 68;
          UserAccountSettings = SampEncryptDSRMPassword(hMem, v26, v27, &v33);
          if ( UserAccountSettings < 0 )
            goto LABEL_38;
          v28 = SampSetUnicodeStringAttribute((struct _SAMP_OBJECT *)v5, 0x10u);
          v29 = hMem[1];
          UserAccountSettings = v28;
          v30 = LOWORD(hMem[0]);
          if ( LOWORD(hMem[0]) )
          {
            do
            {
              *v29++ = 0;
              --v30;
            }
            while ( v30 );
            v29 = hMem[1];
          }
          LocalFree(v29);
          if ( UserAccountSettings < 0 )
            goto LABEL_38;
          LocalFree(v1);
          v35 = 0;
          v1 = 0;
          UserAccountSettings = SampStoreObjectAttributes((struct _SAMP_OBJECT *)v5);
          SampDeleteContext((PVOID **)v5);
          v5 = 0;
          if ( UserAccountSettings < 0 )
            goto LABEL_38;
          ++v7;
        }
        UserAccountSettings = -1073741670;
      }
    }
LABEL_38:
    SampReleaseWriteLock(UserAccountSettings >= 0);
    if ( v5 )
      SampDeleteContext((PVOID **)v5);
    if ( v0 )
      SamIFree_SAMPR_ENUMERATION_BUFFER(v0);
    if ( v1 )
      LocalFree(v1);
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      31,
      WPP_8db69bd9a17034f9cf99ab18ffdabd47_Traceguids,
      (unsigned int)UserAccountSettings,
      UserAccountSettings);
  return (unsigned int)UserAccountSettings;
}

```

## disassembly

```asm
0x180028bec  push    rbp
0x180028bee  push    rbx
0x180028bef  push    rsi
0x180028bf0  push    rdi
0x180028bf1  push    r12
0x180028bf3  push    r13
0x180028bf5  push    r14
0x180028bf7  push    r15
0x180028bf9  lea     rbp, [rsp-8]
0x180028bfe  sub     rsp, 108h
0x180028c05  mov     rax, cs:__security_cookie
0x180028c0c  xor     rax, rsp
0x180028c0f  mov     [rbp+40h+var_50], rax
0x180028c13  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180028c1a  xor     r12d, r12d
0x180028c1d  mov     [rbp+40h+var_B8], r12d
0x180028c21  mov     r14d, r12d
0x180028c24  mov     [rbp+40h+var_C0], r12
0x180028c28  mov     edi, r12d
0x180028c2b  mov     [rsp+140h+var_D0], r12d
0x180028c30  mov     rcx, [rcx+550h]
0x180028c37  mov     [rbp+40h+var_B4], r12d
0x180028c3b  mov     [rsp+140h+var_C8], r12
0x180028c40  call    SampAcquireWriteLock
0x180028c45  mov     ebx, eax
0x180028c47  test    eax, eax
0x180028c49  js      loc_180029095
0x180028c4f  xor     ecx, ecx
0x180028c51  mov     r15b, r12b
0x180028c54  call    SampSetTransactionWithinDomain
0x180028c59  lea     ecx, [r12+1]
0x180028c5e  call    SampSetTransactionDomain
0x180028c63  mov     rsi, r12
0x180028c66  test    r15b, r15b
0x180028c69  jnz     loc_180029060
0x180028c6f  xorps   xmm0, xmm0
0x180028c72  lea     rax, [rsp+140h+var_D0]
0x180028c77  mov     esi, 1
0x180028c7c  lea     r9, [rbp+40h+var_C0]
0x180028c80  mov     [rsp+140h+var_108], sil
0x180028c85  lea     rdx, [rbp+40h+var_B8]
0x180028c89  mov     [rsp+140h+var_110], rax
0x180028c8e  xorps   xmm1, xmm1
0x180028c91  mov     [rsp+140h+var_118], r12d
0x180028c96  xor     r8d, r8d
0x180028c99  lea     ecx, [rsi+3]
0x180028c9c  mov     [rsp+140h+var_120], 0FFFFh
0x180028ca4  movups  [rsp+140h+var_E0], xmm0
0x180028ca9  movups  xmmword ptr [rsp+140h+hMem], xmm1
0x180028cae  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x180028cb2  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x180028cb6  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x180028cba  call    ?SampEnumerateAccountNamesRegistry@@YAJW4_SAMP_OBJECT_TYPE@@PEAKKPEAPEAU_SAMPR_ENUMERATION_BUFFER@@KK1E@Z; SampEnumerateAccountNamesRegistry(_SAMP_OBJECT_TYPE,ulong *,ulong,_SAMPR_ENUMERATION_BUFFER * *,ulong,ulong,ulong *,uchar)
0x180028cbf  mov     r14, [rbp+40h+var_C0]
0x180028cc3  mov     ebx, eax
0x180028cc5  test    eax, eax
0x180028cc7  js      loc_18002905D
0x180028ccd  cmp     eax, 105h
0x180028cd2  movzx   r15d, r15b
0x180028cd6  mov     r13d, r12d
0x180028cd9  cmovnz  r15d, esi
0x180028cdd  cmp     r13d, [rsp+140h+var_D0]
0x180028ce2  jnb     loc_180029038
0x180028ce8  mov     ebx, 1
0x180028ced  xorps   xmm0, xmm0
0x180028cf0  mov     [rsp+140h+var_100], ebx
0x180028cf4  xor     r9d, r9d
0x180028cf7  mov     [rsp+140h+var_108], r12b
0x180028cfc  mov     r8b, bl
0x180028cff  mov     byte ptr [rsp+140h+var_110], r12b
0x180028d04  mov     dl, bl
0x180028d06  mov     byte ptr [rsp+140h+var_118], bl
0x180028d0a  lea     ecx, [rbx+3]
0x180028d0d  mov     byte ptr [rsp+140h+var_120], bl
0x180028d11  movups  xmmword ptr [rbp+40h+var_80.MinPasswordLength], xmm0
0x180028d15  movups  xmmword ptr [rbp+40h+var_80.MinPasswordAge], xmm0
0x180028d19  movups  [rbp+40h+var_60], xmm0
0x180028d1d  call    SampCreateContextEx
0x180028d22  mov     rsi, rax
0x180028d25  test    rax, rax
0x180028d28  jz      loc_180029056
0x180028d2e  mov     ecx, [rax+0C0h]
0x180028d34  xor     r9d, r9d
0x180028d37  mov     [rax+0B0h], r12
0x180028d3e  and     ecx, 0FFFFFFFDh
0x180028d41  or      ecx, ebx
0x180028d43  mov     [rax+0C8h], ebx
0x180028d49  mov     [rax+0C0h], ecx
0x180028d4f  lea     r12, [rsi+0A0h]
0x180028d56  mov     dword ptr [rax+94h], 0F07FFh
0x180028d60  mov     rax, [r14+8]
0x180028d64  mov     ecx, r13d
0x180028d67  lea     rdx, [rcx+rcx*2]
0x180028d6b  mov     ecx, [rax+rdx*8]
0x180028d6e  mov     [rsi+0F8h], ecx
0x180028d74  lea     ecx, [rbx+3]
0x180028d77  mov     r8, [r14+8]
0x180028d7b  mov     r8d, [r8+rdx*8]
0x180028d7f  mov     rdx, r12
0x180028d82  call    ?SampBuildAccountSubKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@K1@Z; SampBuildAccountSubKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,ulong,_UNICODE_STRING *)
0x180028d87  mov     ebx, eax
0x180028d89  test    eax, eax
0x180028d8b  js      loc_180029060
0x180028d91  mov     rax, cs:SampKey
0x180028d98  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x180028d9c  mov     [rbp+40h+ObjectAttributes.ObjectName], r12
0x180028da0  xorps   xmm0, xmm0
0x180028da3  lea     r12, [rsi+98h]
0x180028daa  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x180028db1  mov     rcx, r12; KeyHandle
0x180028db4  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x180028db8  xor     r9d, r9d; Unused
0x180028dbb  mov     [rbp+40h+ObjectAttributes.Attributes], 40h ; '@'
0x180028dc2  mov     edx, 2001Fh; DesiredAccess
0x180028dc7  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x180028dcc  call    cs:__imp_RtlpNtOpenKey
0x180028dd2  mov     ebx, eax
0x180028dd4  test    eax, eax
0x180028dd6  js      loc_18002904C
0x180028ddc  lea     rdx, [rbp+40h+var_80]
0x180028de0  mov     rcx, rsi
0x180028de3  call    SampGetUserAccountSettings
0x180028de8  xor     r12d, r12d
0x180028deb  mov     ebx, eax
0x180028ded  test    eax, eax
0x180028def  js      loc_180029060
0x180028df5  lea     r9, [rsp+140h+var_C8]; void **
0x180028dfa  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180028dfd  lea     r8, [rbp+40h+var_B4]; unsigned int *
0x180028e01  lea     rdx, [rbp+40h+var_80]; struct _DOMAIN_PASSWORD_INFORMATION *
0x180028e05  call    ?SampGetPrivateUserData@@YAJPEAU_SAMP_OBJECT@@PEAU_DOMAIN_PASSWORD_INFORMATION@@PEAKPEAPEAX@Z; SampGetPrivateUserData(_SAMP_OBJECT *,_DOMAIN_PASSWORD_INFORMATION *,ulong *,void * *)
0x180028e0a  mov     rdi, [rsp+140h+var_C8]
0x180028e0f  mov     ebx, eax
0x180028e11  test    eax, eax
0x180028e13  js      loc_180029060
0x180028e19  movzx   eax, word ptr [rdi+4]
0x180028e1d  lea     r9, [rsp+140h+var_E0]
0x180028e22  mov     word ptr [rsp+140h+var_E0], ax
0x180028e27  lea     rcx, [rsp+140h+hMem]
0x180028e2c  movzx   eax, word ptr [rdi+6]
0x180028e30  mov     word ptr [rsp+140h+var_E0+2], ax
0x180028e35  lea     rax, [rdi+0Ch]
0x180028e39  mov     qword ptr [rsp+140h+var_E0+8], rax
0x180028e3e  call    ?SampEncryptDSRMPassword@@YAJPEAU_UNICODE_STRING@@GW4_SAMP_ENCRYPTED_DATA_TYPE@@0K@Z; SampEncryptDSRMPassword(_UNICODE_STRING *,ushort,_SAMP_ENCRYPTED_DATA_TYPE,_UNICODE_STRING *,ulong)
0x180028e43  mov     ebx, eax
0x180028e45  test    eax, eax
0x180028e47  js      loc_180029060
0x180028e4d  lea     r8, [rsp+140h+hMem]
0x180028e52  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180028e55  lea     edx, [r12+0Dh]; unsigned int
0x180028e5a  call    SampSetUnicodeStringAttribute
0x180028e5f  mov     rcx, [rsp+140h+hMem+8]
0x180028e64  mov     ebx, eax
0x180028e66  movzx   eax, word ptr [rsp+140h+hMem]
0x180028e6b  test    rax, rax
0x180028e6e  jz      short loc_180028E85
0x180028e70  lea     edx, [r12+1]
0x180028e75  mov     [rcx], r12b
0x180028e78  add     rcx, rdx
0x180028e7b  sub     rax, rdx
0x180028e7e  jnz     short loc_180028E75
0x180028e80  mov     rcx, [rsp+140h+hMem+8]; hMem
0x180028e85  call    cs:__imp_LocalFree
0x180028e8b  test    ebx, ebx
0x180028e8d  js      loc_180029060
0x180028e93  movzx   eax, word ptr [rdi+1Ch]
0x180028e97  lea     r9, [rsp+140h+var_E0]
0x180028e9c  mov     word ptr [rsp+140h+var_E0], ax
0x180028ea1  lea     rcx, [rsp+140h+hMem]
0x180028ea6  movzx   eax, word ptr [rdi+1Eh]
0x180028eaa  mov     word ptr [rsp+140h+var_E0+2], ax
0x180028eaf  lea     rax, [rdi+24h]
0x180028eb3  mov     qword ptr [rsp+140h+var_E0+8], rax
0x180028eb8  call    ?SampEncryptDSRMPassword@@YAJPEAU_UNICODE_STRING@@GW4_SAMP_ENCRYPTED_DATA_TYPE@@0K@Z; SampEncryptDSRMPassword(_UNICODE_STRING *,ushort,_SAMP_ENCRYPTED_DATA_TYPE,_UNICODE_STRING *,ulong)
0x180028ebd  mov     ebx, eax
0x180028ebf  test    eax, eax
0x180028ec1  js      loc_180029060
0x180028ec7  lea     r8, [rsp+140h+hMem]
0x180028ecc  mov     edx, 0Eh; unsigned int
0x180028ed1  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180028ed4  call    SampSetUnicodeStringAttribute
0x180028ed9  mov     rcx, [rsp+140h+hMem+8]
0x180028ede  mov     ebx, eax
0x180028ee0  movzx   eax, word ptr [rsp+140h+hMem]
0x180028ee5  test    rax, rax
0x180028ee8  jz      short loc_180028EFF
0x180028eea  mov     edx, 1
0x180028eef  mov     [rcx], r12b
0x180028ef2  add     rcx, rdx
0x180028ef5  sub     rax, rdx
0x180028ef8  jnz     short loc_180028EEF
0x180028efa  mov     rcx, [rsp+140h+hMem+8]; hMem
0x180028eff  call    cs:__imp_LocalFree
0x180028f05  test    ebx, ebx
0x180028f07  js      loc_180029060
0x180028f0d  movzx   eax, word ptr [rdi+3Ch]
0x180028f11  lea     r9, [rsp+140h+var_E0]
0x180028f16  mov     word ptr [rsp+140h+var_E0], ax
0x180028f1b  lea     rcx, [rsp+140h+hMem]
0x180028f20  movzx   eax, word ptr [rdi+3Eh]
0x180028f24  mov     word ptr [rsp+140h+var_E0+2], ax
0x180028f29  lea     rax, [rdi+44h]
0x180028f2d  mov     qword ptr [rsp+140h+var_E0+8], rax
0x180028f32  call    ?SampEncryptDSRMPassword@@YAJPEAU_UNICODE_STRING@@GW4_SAMP_ENCRYPTED_DATA_TYPE@@0K@Z; SampEncryptDSRMPassword(_UNICODE_STRING *,ushort,_SAMP_ENCRYPTED_DATA_TYPE,_UNICODE_STRING *,ulong)
0x180028f37  mov     ebx, eax
0x180028f39  test    eax, eax
0x180028f3b  js      loc_180029060
0x180028f41  lea     r8, [rsp+140h+hMem]
0x180028f46  mov     edx, 0Fh; unsigned int
0x180028f4b  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180028f4e  call    SampSetUnicodeStringAttribute
0x180028f53  mov     rcx, [rsp+140h+hMem+8]
0x180028f58  mov     ebx, eax
0x180028f5a  movzx   eax, word ptr [rsp+140h+hMem]
0x180028f5f  test    rax, rax
0x180028f62  jz      short loc_180028F79
0x180028f64  mov     edx, 1
0x180028f69  mov     [rcx], r12b
0x180028f6c  add     rcx, rdx
0x180028f6f  sub     rax, rdx
0x180028f72  jnz     short loc_180028F69
0x180028f74  mov     rcx, [rsp+140h+hMem+8]; hMem
0x180028f79  call    cs:__imp_LocalFree
0x180028f7f  test    ebx, ebx
0x180028f81  js      loc_180029060
0x180028f87  movzx   eax, word ptr [rdi+34h]
0x180028f8b  lea     r9, [rsp+140h+var_E0]
0x180028f90  mov     word ptr [rsp+140h+var_E0], ax
0x180028f95  movzx   eax, word ptr [rdi+36h]
0x180028f99  mov     word ptr [rsp+140h+var_E0+2], ax
0x180028f9e  movzx   ecx, word ptr [rdi+3Ch]
0x180028fa2  add     rcx, 44h ; 'D'
0x180028fa6  add     rcx, rdi
0x180028fa9  mov     qword ptr [rsp+140h+var_E0+8], rcx
0x180028fae  lea     rcx, [rsp+140h+hMem]
0x180028fb3  call    ?SampEncryptDSRMPassword@@YAJPEAU_UNICODE_STRING@@GW4_SAMP_ENCRYPTED_DATA_TYPE@@0K@Z; SampEncryptDSRMPassword(_UNICODE_STRING *,ushort,_SAMP_ENCRYPTED_DATA_TYPE,_UNICODE_STRING *,ulong)
0x180028fb8  mov     ebx, eax
0x180028fba  test    eax, eax
0x180028fbc  js      loc_180029060
0x180028fc2  lea     r8, [rsp+140h+hMem]
0x180028fc7  mov     edx, 10h; unsigned int
0x180028fcc  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180028fcf  call    SampSetUnicodeStringAttribute
0x180028fd4  mov     rcx, [rsp+140h+hMem+8]
0x180028fd9  mov     ebx, eax
0x180028fdb  movzx   eax, word ptr [rsp+140h+hMem]
0x180028fe0  test    rax, rax
0x180028fe3  jz      short loc_180028FFA
0x180028fe5  mov     edx, 1
0x180028fea  mov     [rcx], r12b
0x180028fed  add     rcx, rdx
0x180028ff0  sub     rax, rdx
0x180028ff3  jnz     short loc_180028FEA
0x180028ff5  mov     rcx, [rsp+140h+hMem+8]; hMem
0x180028ffa  call    cs:__imp_LocalFree
0x180029000  test    ebx, ebx
0x180029002  js      short loc_180029060
0x180029004  mov     rcx, rdi; hMem
0x180029007  call    cs:__imp_LocalFree
0x18002900d  xor     edx, edx
0x18002900f  mov     [rsp+140h+var_C8], r12
0x180029014  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180029017  mov     rdi, r12
0x18002901a  call    SampStoreObjectAttributes
0x18002901f  mov     rcx, rsi; HandleId
0x180029022  mov     ebx, eax
0x180029024  call    SampDeleteContext
0x180029029  mov     rsi, r12
0x18002902c  test    ebx, ebx
0x18002902e  js      short loc_180029060
0x180029030  inc     r13d
0x180029033  jmp     loc_180028CDD
0x180029038  mov     rcx, r14; hMem
0x18002903b  call    SamIFree_SAMPR_ENUMERATION_BUFFER
0x180029040  mov     r14, r12
0x180029043  mov     [rbp+40h+var_C0], r12
0x180029047  jmp     loc_180028C63
0x18002904c  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180029054  jmp     short loc_180029060
0x180029056  mov     ebx, 0C000009Ah
0x18002905b  jmp     short loc_180029060
0x18002905d  mov     rsi, r12
0x180029060  mov     ecx, ebx
0x180029062  shr     ecx, 1Fh
0x180029065  xor     cl, 1
0x180029068  call    SampReleaseWriteLock
0x18002906d  test    rsi, rsi
0x180029070  jz      short loc_18002907A
0x180029072  mov     rcx, rsi; HandleId
0x180029075  call    SampDeleteContext
0x18002907a  test    r14, r14
0x18002907d  jz      short loc_180029087
0x18002907f  mov     rcx, r14; hMem
0x180029082  call    SamIFree_SAMPR_ENUMERATION_BUFFER
0x180029087  test    rdi, rdi
0x18002908a  jz      short loc_180029095
0x18002908c  mov     rcx, rdi; hMem
0x18002908f  call    cs:__imp_LocalFree
0x180029095  mov     rcx, cs:WPP_GLOBAL_Control
0x18002909c  test    dword ptr [rcx+44h], 20000h
  ... truncated ...
```
