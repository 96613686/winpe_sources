# SampRemoveAliasFromAccountMembership(_SAMP_OBJECT *,void *)

- ea: `0x180034fa4`
- end: `0x1800351b2`
- name: `?SampRemoveAliasFromAccountMembership@@YAJPEAU_SAMP_OBJECT@@PEAX@Z`
- size: `526`
- prototype: `int(struct _SAMP_OBJECT *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800351b8`
- `0x18003526c`

## callees

- `0x1800213d0`
- `0x180027e24`
- `0x180034758`
- `0x180034fa4`
- `0x1800aeafc`

## import_xrefs

- `ntdll!RtlAddActionToRXact` at `0x180035138`
- `ntdll!RtlAddActionToRXact` at `0x180035138`
- `ntdll!NtClose` at `0x180035157`
- `ntdll!NtClose` at `0x180035157`
- `ntdll!RtlpNtQueryValueKey` at `0x18003508b`
- `ntdll!RtlpNtQueryValueKey` at `0x1800350df`
- `ntdll!RtlpNtQueryValueKey` at `0x18003508b`
- `ntdll!RtlpNtQueryValueKey` at `0x1800350df`
- `ntdll!RtlpNtOpenKey` at `0x180035046`
- `ntdll!RtlpNtOpenKey` at `0x180035046`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800350b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800350b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003514d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003514d`

## pseudocode

```c
__int64 __fastcall SampRemoveAliasFromAccountMembership(struct _SAMP_OBJECT *a1, void *a2)
{
  NTSTATUS v2; // ebx
  bool v3; // zf
  int v5; // r14d
  NTSTATUS v6; // eax
  NTSTATUS v7; // eax
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  __int64 i; // rcx
  __int64 v11; // rax
  NTSTATUS v12; // eax
  struct _UNICODE_STRING KeyName; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING v15; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG DataLength; // [rsp+B0h] [rbp+30h] BYREF
  ULONG Type; // [rsp+C0h] [rbp+40h] BYREF
  HANDLE KeyHandle; // [rsp+C8h] [rbp+48h] BYREF

  v2 = 0;
  v3 = (*((_BYTE *)a1 + 192) & 2) == 0;
  KeyHandle = 0;
  v15 = 0;
  Type = 0;
  KeyName = 0;
  DataLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( v3 )
  {
    v5 = *((_DWORD *)a1 + 62);
    v2 = SampBuildAliasMembersKeyName(a2, &v15, &KeyName);
    if ( v2 >= 0 )
    {
      ObjectAttributes.RootDirectory = SampKey;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &KeyName;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v6 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
      v2 = v6;
      if ( v6 == -1073741772 || v6 == -1073741766 )
      {
        v2 = -1073741486;
      }
      else if ( v6 >= 0 )
      {
        DataLength = 0;
        v7 = RtlpNtQueryValueKey(KeyHandle, &Type, 0, &DataLength, 0);
        v2 = v7;
        if ( v7 < 0 )
        {
          if ( v7 == -2147483643 )
          {
            v8 = LocalAlloc(0x40u, DataLength);
            v9 = v8;
            if ( v8 )
            {
              v2 = RtlpNtQueryValueKey(KeyHandle, 0, v8, &DataLength, 0);
              if ( v2 >= 0 )
              {
                v2 = -1073741486;
                for ( i = 0; (unsigned int)i < Type; i = (unsigned int)(i + 1) )
                {
                  if ( v9[i] == v5 )
                  {
                    DataLength -= 4;
                    v11 = Type - 1;
                    Type = v11;
                    if ( (_DWORD)v11 )
                    {
                      v9[(unsigned int)i] = v9[v11];
                      v12 = RtlAddActionToRXact(SampRXactContext, 2u, &KeyName, Type, v9, DataLength);
                    }
                    else
                    {
                      v12 = SampDeleteAliasMembershipKeysForAccount(a2);
                    }
                    v2 = v12;
                    break;
                  }
                }
              }
              LocalFree(v9);
            }
            else
            {
              v2 = -1073741670;
            }
          }
        }
        else
        {
          v2 = -1073741486;
        }
        NtClose(KeyHandle);
      }
      SampFreeUnicodeString(&v15);
      SampFreeUnicodeString(&KeyName);
    }
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 49, &WPP_799c13f926ef3db95a69a5604490dfde_Traceguids, (unsigned int)v2, v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180034fa4  push    rbp
0x180034fa6  push    rbx
0x180034fa7  push    rsi
0x180034fa8  push    rdi
0x180034fa9  push    r14
0x180034fab  mov     rbp, rsp
0x180034fae  sub     rsp, 80h
0x180034fb5  xor     ebx, ebx
0x180034fb7  xorps   xmm0, xmm0
0x180034fba  test    byte ptr [rcx+0C0h], 2
0x180034fc1  xorps   xmm1, xmm1
0x180034fc4  mov     rsi, rdx
0x180034fc7  mov     [rbp+KeyHandle], rbx
0x180034fcb  movups  xmmword ptr [rbp+var_40.Length], xmm0
0x180034fcf  mov     [rbp+Type], ebx
0x180034fd2  movups  xmmword ptr [rbp+KeyName.Length], xmm1
0x180034fd6  mov     [rbp+DataLength], ebx
0x180034fd9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180034fdd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180034fe1  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180034fe5  jnz     loc_180035176
0x180034feb  mov     r14d, [rcx+0F8h]
0x180034ff2  lea     r8, [rbp+KeyName]; struct _UNICODE_STRING *
0x180034ff6  mov     rcx, rsi; Sid
0x180034ff9  lea     rdx, [rbp+var_40]; struct _UNICODE_STRING *
0x180034ffd  call    SampBuildAliasMembersKeyName
0x180035002  mov     ebx, eax
0x180035004  test    eax, eax
0x180035006  js      loc_180035176
0x18003500c  mov     rax, cs:SampKey
0x180035013  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180035017  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x18003501b  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18003501f  lea     rax, [rbp+KeyName]
0x180035023  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18003502a  xorps   xmm0, xmm0
0x18003502d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180035031  mov     edi, 40h ; '@'
0x180035036  xor     r9d, r9d; Unused
0x180035039  mov     edx, 20019h; DesiredAccess
0x18003503e  mov     [rbp+ObjectAttributes.Attributes], edi
0x180035041  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180035046  call    cs:__imp_RtlpNtOpenKey
0x18003504c  mov     ebx, eax
0x18003504e  cmp     eax, 0C0000034h
0x180035053  jz      loc_18003515F
0x180035059  cmp     eax, 0C000003Ah
0x18003505e  jz      loc_18003515F
0x180035064  test    eax, eax
0x180035066  js      loc_180035164
0x18003506c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180035070  lea     r9, [rbp+DataLength]; DataLength
0x180035074  xor     r8d, r8d; Data
0x180035077  mov     [rbp+DataLength], 0
0x18003507e  lea     rdx, [rbp+Type]; Type
0x180035082  mov     qword ptr [rsp+80h+Unused], 0; Unused
0x18003508b  call    cs:__imp_RtlpNtQueryValueKey
0x180035091  mov     ebx, eax
0x180035093  test    eax, eax
0x180035095  js      short loc_1800350A1
0x180035097  mov     ebx, 0C0000152h
0x18003509c  jmp     loc_180035153
0x1800350a1  cmp     eax, 80000005h
0x1800350a6  jnz     loc_180035153
0x1800350ac  mov     edx, [rbp+DataLength]; uBytes
0x1800350af  mov     ecx, edi; uFlags
0x1800350b1  call    cs:__imp_LocalAlloc
0x1800350b7  mov     rdi, rax
0x1800350ba  test    rax, rax
0x1800350bd  jnz     short loc_1800350C9
0x1800350bf  mov     ebx, 0C000009Ah
0x1800350c4  jmp     loc_180035153
0x1800350c9  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800350cd  lea     r9, [rbp+DataLength]; DataLength
0x1800350d1  mov     r8, rdi; Data
0x1800350d4  mov     qword ptr [rsp+80h+Unused], 0; Unused
0x1800350dd  xor     edx, edx; Type
0x1800350df  call    cs:__imp_RtlpNtQueryValueKey
0x1800350e5  mov     ebx, eax
0x1800350e7  test    eax, eax
0x1800350e9  js      short loc_18003514A
0x1800350eb  mov     eax, [rbp+Type]
0x1800350ee  mov     ebx, 0C0000152h
0x1800350f3  xor     ecx, ecx
0x1800350f5  cmp     ecx, eax
0x1800350f7  jnb     short loc_18003514A
0x1800350f9  mov     edx, ecx
0x1800350fb  cmp     [rdi+rcx*4], r14d
0x1800350ff  jz      short loc_180035105
0x180035101  inc     ecx
0x180035103  jmp     short loc_1800350F5
0x180035105  add     [rbp+DataLength], 0FFFFFFFCh
0x180035109  dec     eax
0x18003510b  mov     [rbp+Type], eax
0x18003510e  test    eax, eax
0x180035110  jz      short loc_180035140
0x180035112  mov     ecx, [rdi+rax*4]
0x180035115  lea     r8, [rbp+KeyName]; KeyName
0x180035119  mov     [rdi+rdx*4], ecx
0x18003511c  mov     edx, 2; ActionType
0x180035121  mov     eax, [rbp+DataLength]
0x180035124  mov     r9d, [rbp+Type]; ValueType
0x180035128  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; Context
0x18003512f  mov     [rsp+80h+ValueDataSize], eax; ValueDataSize
0x180035133  mov     qword ptr [rsp+80h+Unused], rdi; ValueData
0x180035138  call    cs:__imp_RtlAddActionToRXact
0x18003513e  jmp     short loc_180035148
0x180035140  mov     rcx, rsi; void *
0x180035143  call    ?SampDeleteAliasMembershipKeysForAccount@@YAJPEAX@Z; SampDeleteAliasMembershipKeysForAccount(void *)
0x180035148  mov     ebx, eax
0x18003514a  mov     rcx, rdi; hMem
0x18003514d  call    cs:__imp_LocalFree
0x180035153  mov     rcx, [rbp+KeyHandle]; Handle
0x180035157  call    cs:__imp_NtClose
0x18003515d  jmp     short loc_180035164
0x18003515f  mov     ebx, 0C0000152h
0x180035164  lea     rcx, [rbp+var_40]
0x180035168  call    SampFreeUnicodeString
0x18003516d  lea     rcx, [rbp+KeyName]
0x180035171  call    SampFreeUnicodeString
0x180035176  mov     rcx, cs:WPP_GLOBAL_Control
0x18003517d  test    dword ptr [rcx+44h], 20000h
0x180035184  jz      short loc_1800351A2
0x180035186  mov     rcx, [rcx+38h]
0x18003518a  lea     r8, WPP_799c13f926ef3db95a69a5604490dfde_Traceguids
0x180035191  mov     edx, 31h ; '1'
0x180035196  mov     [rsp+80h+Unused], ebx
0x18003519a  mov     r9d, ebx
0x18003519d  call    WPP_SF_Dd
0x1800351a2  mov     eax, ebx
0x1800351a4  add     rsp, 80h
0x1800351ab  pop     r14
0x1800351ad  pop     rdi
0x1800351ae  pop     rsi
0x1800351af  pop     rbx
0x1800351b0  pop     rbp
0x1800351b1  retn
```
