# SampAddAliasToAccountMembership(_SAMP_OBJECT *,void *)

- ea: `0x180034204`
- end: `0x18003451a`
- name: `?SampAddAliasToAccountMembership@@YAJPEAU_SAMP_OBJECT@@PEAX@Z`
- size: `790`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034520`

## callees

- `0x1800213d0`
- `0x180027e24`
- `0x180034204`
- `0x1800aeafc`

## import_xrefs

- `ntdll!RtlAddActionToRXact` at `0x180034445`
- `ntdll!RtlAddActionToRXact` at `0x180034484`
- `ntdll!RtlAddActionToRXact` at `0x1800344c4`
- `ntdll!RtlAddActionToRXact` at `0x180034445`
- `ntdll!RtlAddActionToRXact` at `0x180034484`
- `ntdll!RtlAddActionToRXact` at `0x1800344c4`
- `ntdll!NtClose` at `0x1800342e4`
- `ntdll!NtClose` at `0x180034406`
- `ntdll!NtClose` at `0x1800342e4`
- `ntdll!NtClose` at `0x180034406`
- `ntdll!RtlpNtQueryValueKey` at `0x1800342d8`
- `ntdll!RtlpNtQueryValueKey` at `0x180034357`
- `ntdll!RtlpNtQueryValueKey` at `0x1800343aa`
- `ntdll!RtlpNtQueryValueKey` at `0x1800342d8`
- `ntdll!RtlpNtQueryValueKey` at `0x180034357`
- `ntdll!RtlpNtQueryValueKey` at `0x1800343aa`
- `ntdll!RtlpNtOpenKey` at `0x1800342b5`
- `ntdll!RtlpNtOpenKey` at `0x180034324`
- `ntdll!RtlpNtOpenKey` at `0x1800342b5`
- `ntdll!RtlpNtOpenKey` at `0x180034324`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034383`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034383`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800343d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800343f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034498`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800343d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800343f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034498`

## pseudocode

```c
__int64 __fastcall SampAddAliasToAccountMembership(struct _SAMP_OBJECT *a1, void *a2)
{
  int v2; // eax
  bool v3; // zf
  NTSTATUS v4; // ebx
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  int *v7; // rax
  int *v8; // rdi
  ULONG v9; // edx
  ULONG i; // ecx
  char v11; // si
  ULONG v12; // r9d
  int v14; // [rsp+30h] [rbp-29h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING KeyName; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING v17; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  ULONG DataLength; // [rsp+C0h] [rbp+67h] BYREF
  ULONG v20; // [rsp+D0h] [rbp+77h] BYREF
  ULONG Type; // [rsp+D8h] [rbp+7Fh] BYREF

  v2 = *((_DWORD *)a1 + 62);
  v3 = (*((_BYTE *)a1 + 192) & 2) == 0;
  KeyHandle = 0;
  v20 = 0;
  v4 = 0;
  DataLength = 0;
  KeyName = 0;
  Type = 0;
  v17 = 0;
  v14 = v2;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( v3 )
  {
    v4 = SampBuildAliasMembersKeyName(a2, &KeyName, &v17);
    if ( v4 >= 0 )
    {
      ObjectAttributes.RootDirectory = SampKey;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &KeyName;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v5 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
      v4 = v5;
      if ( v5 < 0 )
      {
        if ( v5 != -1073741772 )
          goto LABEL_29;
        Type = 0;
        v4 = RtlAddActionToRXact(SampRXactContext, 2u, &KeyName, 0, 0, 0);
        if ( v4 < 0 )
          goto LABEL_29;
      }
      else
      {
        v4 = RtlpNtQueryValueKey(KeyHandle, &Type, 0, 0, 0);
        NtClose(KeyHandle);
        if ( v4 < 0 )
          goto LABEL_29;
        ObjectAttributes.RootDirectory = SampKey;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &v17;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v6 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
        v4 = v6;
        if ( v6 != -1073741772 )
        {
          if ( v6 >= 0 )
          {
            DataLength = 0;
            v4 = RtlpNtQueryValueKey(KeyHandle, &v20, 0, &DataLength, 0);
            if ( (int)(v4 + 0x80000000) < 0 || v4 == -2147483643 )
            {
              DataLength += 4;
              v7 = (int *)LocalAlloc(0x40u, DataLength);
              v8 = v7;
              if ( !v7 )
              {
                v4 = -1073741670;
LABEL_20:
                v11 = 0;
                NtClose(KeyHandle);
                if ( v4 < 0 )
                {
LABEL_27:
                  if ( v11 )
                    v4 = RtlAddActionToRXact(SampRXactContext, 2u, &KeyName, Type + 1, 0, 0);
                  goto LABEL_29;
                }
                v12 = v20;
LABEL_25:
                DataLength = 4 * v12;
                v4 = RtlAddActionToRXact(SampRXactContext, 2u, &v17, v12, v8, 4 * v12);
                if ( v8 != &v14 )
                  LocalFree(v8);
                goto LABEL_27;
              }
              v4 = RtlpNtQueryValueKey(KeyHandle, 0, v7, &DataLength, 0);
              if ( v4 >= 0 )
              {
                v9 = v20;
                for ( i = 0; i < v20; ++i )
                {
                  if ( v8[i] == v14 )
                  {
                    LocalFree(v8);
                    v4 = -1073741485;
                    goto LABEL_19;
                  }
                }
                ++v20;
                v8[v9] = v14;
                goto LABEL_20;
              }
              LocalFree(v8);
            }
LABEL_19:
            v8 = 0;
            goto LABEL_20;
          }
LABEL_29:
          SampFreeUnicodeString(&KeyName);
          SampFreeUnicodeString(&v17);
          goto LABEL_30;
        }
      }
      v11 = 1;
      v8 = &v14;
      v12 = 1;
      v20 = 1;
      goto LABEL_25;
    }
  }
LABEL_30:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 48, &WPP_799c13f926ef3db95a69a5604490dfde_Traceguids, (unsigned int)v4, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180034204  push    rbp
0x180034206  push    rbx
0x180034207  push    rsi
0x180034208  push    rdi
0x180034209  push    r14
0x18003420b  lea     rbp, [rsp-37h]
0x180034210  sub     rsp, 90h
0x180034217  mov     eax, [rcx+0F8h]
0x18003421d  xor     r14d, r14d
0x180034220  test    byte ptr [rcx+0C0h], 2
0x180034227  xorps   xmm0, xmm0
0x18003422a  xorps   xmm1, xmm1
0x18003422d  mov     [rbp+57h+KeyHandle], r14
0x180034231  mov     r9, rdx
0x180034234  mov     [rbp+57h+arg_10], r14d
0x180034238  mov     ebx, r14d
0x18003423b  mov     [rbp+57h+DataLength], r14d
0x18003423f  movups  xmmword ptr [rbp+57h+KeyName.Length], xmm0
0x180034243  mov     [rbp+57h+Type], r14d
0x180034247  movups  xmmword ptr [rbp+57h+var_60.Length], xmm1
0x18003424b  mov     [rbp+57h+var_80], eax
0x18003424e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180034252  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180034256  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003425a  jnz     loc_1800344DE
0x180034260  lea     r8, [rbp+57h+var_60]; struct _UNICODE_STRING *
0x180034264  mov     rcx, r9; Sid
0x180034267  lea     rdx, [rbp+57h+KeyName]; struct _UNICODE_STRING *
0x18003426b  call    SampBuildAliasMembersKeyName
0x180034270  mov     ebx, eax
0x180034272  test    eax, eax
0x180034274  js      loc_1800344DE
0x18003427a  mov     rax, cs:SampKey
0x180034281  lea     edi, [r14+40h]
0x180034285  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180034289  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003428d  lea     rax, [rbp+57h+KeyName]
0x180034291  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180034298  xorps   xmm0, xmm0
0x18003429b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003429f  mov     esi, 20019h
0x1800342a4  mov     [rbp+57h+ObjectAttributes.Attributes], edi
0x1800342a7  xor     r9d, r9d; Unused
0x1800342aa  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800342ae  mov     edx, esi; DesiredAccess
0x1800342b0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800342b5  call    cs:__imp_RtlpNtOpenKey
0x1800342bb  mov     ebx, eax
0x1800342bd  test    eax, eax
0x1800342bf  js      loc_18003441A
0x1800342c5  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800342c9  lea     rdx, [rbp+57h+Type]; Type
0x1800342cd  xor     r9d, r9d; DataLength
0x1800342d0  mov     qword ptr [rsp+0B0h+Unused], r14; Unused
0x1800342d5  xor     r8d, r8d; Data
0x1800342d8  call    cs:__imp_RtlpNtQueryValueKey
0x1800342de  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800342e2  mov     ebx, eax
0x1800342e4  call    cs:__imp_NtClose
0x1800342ea  test    ebx, ebx
0x1800342ec  js      loc_1800344CC
0x1800342f2  mov     rax, cs:SampKey
0x1800342f9  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800342fd  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180034301  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180034305  lea     rax, [rbp+57h+var_60]
0x180034309  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180034310  xorps   xmm0, xmm0
0x180034313  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180034317  xor     r9d, r9d; Unused
0x18003431a  mov     [rbp+57h+ObjectAttributes.Attributes], edi
0x18003431d  mov     edx, esi; DesiredAccess
0x18003431f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180034324  call    cs:__imp_RtlpNtOpenKey
0x18003432a  mov     ebx, eax
0x18003432c  cmp     eax, 0C0000034h
0x180034331  jz      loc_180034451
0x180034337  test    eax, eax
0x180034339  js      loc_1800344CC
0x18003433f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180034343  lea     r9, [rbp+57h+DataLength]; DataLength
0x180034347  xor     r8d, r8d; Data
0x18003434a  mov     [rbp+57h+DataLength], r14d
0x18003434e  lea     rdx, [rbp+57h+arg_10]; Type
0x180034352  mov     qword ptr [rsp+0B0h+Unused], r14; Unused
0x180034357  call    cs:__imp_RtlpNtQueryValueKey
0x18003435d  mov     ecx, 80000000h
0x180034362  mov     ebx, eax
0x180034364  add     eax, ecx
0x180034366  test    ecx, eax
0x180034368  jnz     short loc_180034376
0x18003436a  cmp     ebx, 80000005h
0x180034370  jnz     loc_1800343FC
0x180034376  mov     eax, [rbp+57h+DataLength]
0x180034379  mov     ecx, edi; uFlags
0x18003437b  add     eax, 4
0x18003437e  mov     edx, eax; uBytes
0x180034380  mov     [rbp+57h+DataLength], eax
0x180034383  call    cs:__imp_LocalAlloc
0x180034389  mov     rdi, rax
0x18003438c  test    rax, rax
0x18003438f  jnz     short loc_180034398
0x180034391  mov     ebx, 0C000009Ah
0x180034396  jmp     short loc_1800343FF
0x180034398  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18003439c  lea     r9, [rbp+57h+DataLength]; DataLength
0x1800343a0  mov     r8, rdi; Data
0x1800343a3  mov     qword ptr [rsp+0B0h+Unused], r14; Unused
0x1800343a8  xor     edx, edx; Type
0x1800343aa  call    cs:__imp_RtlpNtQueryValueKey
0x1800343b0  mov     ebx, eax
0x1800343b2  test    eax, eax
0x1800343b4  js      short loc_1800343F3
0x1800343b6  mov     edx, [rbp+57h+arg_10]
0x1800343b9  mov     ecx, r14d
0x1800343bc  mov     r8d, [rbp+57h+var_80]
0x1800343c0  mov     esi, 1
0x1800343c5  cmp     ecx, edx
0x1800343c7  jnb     short loc_1800343E5
0x1800343c9  mov     eax, ecx
0x1800343cb  cmp     [rdi+rax*4], r8d
0x1800343cf  jz      short loc_1800343D5
0x1800343d1  add     ecx, esi
0x1800343d3  jmp     short loc_1800343C5
0x1800343d5  mov     rcx, rdi; hMem
0x1800343d8  call    cs:__imp_LocalFree
0x1800343de  mov     ebx, 0C0000153h
0x1800343e3  jmp     short loc_1800343FC
0x1800343e5  add     edx, esi
0x1800343e7  mov     [rbp+57h+arg_10], edx
0x1800343ea  lea     eax, [rdx-1]
0x1800343ed  mov     [rdi+rax*4], r8d
0x1800343f1  jmp     short loc_1800343FF
0x1800343f3  mov     rcx, rdi; hMem
0x1800343f6  call    cs:__imp_LocalFree
0x1800343fc  mov     rdi, r14
0x1800343ff  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180034403  mov     sil, r14b
0x180034406  call    cs:__imp_NtClose
0x18003440c  test    ebx, ebx
0x18003440e  js      loc_18003449E
0x180034414  mov     r9d, [rbp+57h+arg_10]
0x180034418  jmp     short loc_180034460
0x18003441a  cmp     eax, 0C0000034h
0x18003441f  jnz     loc_1800344CC
0x180034425  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; Context
0x18003442c  lea     r8, [rbp+57h+KeyName]; KeyName
0x180034430  xor     r9d, r9d; ValueType
0x180034433  mov     [rsp+0B0h+ValueDataSize], r14d; ValueDataSize
0x180034438  mov     [rbp+57h+Type], r14d
0x18003443c  mov     qword ptr [rsp+0B0h+Unused], r14; ValueData
0x180034441  lea     edx, [r9+2]; ActionType
0x180034445  call    cs:__imp_RtlAddActionToRXact
0x18003444b  mov     ebx, eax
0x18003444d  test    eax, eax
0x18003444f  js      short loc_1800344CC
0x180034451  mov     esi, 1
0x180034456  lea     rdi, [rbp+57h+var_80]
0x18003445a  mov     r9d, esi; ValueType
0x18003445d  mov     [rbp+57h+arg_10], esi
0x180034460  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; Context
0x180034467  lea     eax, ds:0[r9*4]
0x18003446f  mov     [rsp+0B0h+ValueDataSize], eax; ValueDataSize
0x180034473  lea     r8, [rbp+57h+var_60]; KeyName
0x180034477  mov     edx, 2; ActionType
0x18003447c  mov     qword ptr [rsp+0B0h+Unused], rdi; ValueData
0x180034481  mov     [rbp+57h+DataLength], eax
0x180034484  call    cs:__imp_RtlAddActionToRXact
0x18003448a  mov     ebx, eax
0x18003448c  lea     rax, [rbp+57h+var_80]
0x180034490  cmp     rdi, rax
0x180034493  jz      short loc_18003449E
0x180034495  mov     rcx, rdi; hMem
0x180034498  call    cs:__imp_LocalFree
0x18003449e  test    sil, sil
0x1800344a1  jz      short loc_1800344CC
0x1800344a3  mov     r9d, [rbp+57h+Type]
0x1800344a7  lea     r8, [rbp+57h+KeyName]; KeyName
0x1800344ab  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; Context
0x1800344b2  inc     r9d; ValueType
0x1800344b5  mov     [rsp+0B0h+ValueDataSize], r14d; ValueDataSize
0x1800344ba  mov     edx, 2; ActionType
0x1800344bf  mov     qword ptr [rsp+0B0h+Unused], r14; ValueData
0x1800344c4  call    cs:__imp_RtlAddActionToRXact
0x1800344ca  mov     ebx, eax
0x1800344cc  lea     rcx, [rbp+57h+KeyName]
0x1800344d0  call    SampFreeUnicodeString
0x1800344d5  lea     rcx, [rbp+57h+var_60]
0x1800344d9  call    SampFreeUnicodeString
0x1800344de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800344e5  test    dword ptr [rcx+44h], 20000h
0x1800344ec  jz      short loc_18003450A
0x1800344ee  mov     rcx, [rcx+38h]
0x1800344f2  lea     r8, WPP_799c13f926ef3db95a69a5604490dfde_Traceguids
0x1800344f9  mov     edx, 30h ; '0'
0x1800344fe  mov     [rsp+0B0h+Unused], ebx
0x180034502  mov     r9d, ebx
0x180034505  call    WPP_SF_Dd
0x18003450a  mov     eax, ebx
0x18003450c  add     rsp, 90h
0x180034513  pop     r14
0x180034515  pop     rdi
0x180034516  pop     rsi
0x180034517  pop     rbx
0x180034518  pop     rbp
0x180034519  retn
```
