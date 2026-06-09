# SampDeleteAliasMembershipKeysForAccount(void *)

- ea: `0x180034758`
- end: `0x1800348ed`
- name: `?SampDeleteAliasMembershipKeysForAccount@@YAJPEAX@Z`
- size: `405`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034b6c`
- `0x180034fa4`

## callees

- `0x1800213d0`
- `0x180027e24`
- `0x180034758`
- `0x1800aeafc`

## import_xrefs

- `ntdll!RtlAddActionToRXact` at `0x1800347cb`
- `ntdll!RtlAddActionToRXact` at `0x180034872`
- `ntdll!RtlAddActionToRXact` at `0x180034883`
- `ntdll!RtlAddActionToRXact` at `0x1800347cb`
- `ntdll!RtlAddActionToRXact` at `0x180034872`
- `ntdll!RtlAddActionToRXact` at `0x180034883`
- `ntdll!NtClose` at `0x180034896`
- `ntdll!NtClose` at `0x180034896`
- `ntdll!RtlpNtQueryValueKey` at `0x180034837`
- `ntdll!RtlpNtQueryValueKey` at `0x180034837`
- `ntdll!RtlpNtOpenKey` at `0x180034814`
- `ntdll!RtlpNtOpenKey` at `0x180034814`

## pseudocode

```c
__int64 __fastcall SampDeleteAliasMembershipKeysForAccount(void *a1)
{
  NTSTATUS v1; // ebx
  bool v2; // zf
  ULONG v3; // r9d
  struct _UNICODE_STRING v5; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING KeyName; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG Type; // [rsp+98h] [rbp+18h] BYREF
  HANDLE KeyHandle; // [rsp+A8h] [rbp+28h] BYREF

  KeyHandle = 0;
  Type = 0;
  v5 = 0;
  KeyName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v1 = SampBuildAliasMembersKeyName(a1, &v5, &KeyName);
  if ( v1 >= 0 )
  {
    v1 = RtlAddActionToRXact(SampRXactContext, 1u, &KeyName, 0, 0, 0);
    if ( v1 >= 0 )
    {
      ObjectAttributes.RootDirectory = SampKey;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &v5;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v1 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
      if ( v1 >= 0 )
      {
        v1 = RtlpNtQueryValueKey(KeyHandle, &Type, 0, 0, 0);
        if ( v1 >= 0 )
        {
          v2 = Type == 1;
          v3 = --Type;
          if ( v2 )
          {
            v1 = RtlAddActionToRXact(SampRXactContext, 1u, &v5, 0, 0, 0);
            if ( v1 >= 0 )
              v1 = 0;
          }
          else
          {
            v1 = RtlAddActionToRXact(SampRXactContext, 2u, &v5, v3, 0, 0);
          }
        }
        NtClose(KeyHandle);
      }
    }
    SampFreeUnicodeString(&v5);
    SampFreeUnicodeString(&KeyName);
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 54, &WPP_799c13f926ef3db95a69a5604490dfde_Traceguids, (unsigned int)v1, v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180034758  mov     [rsp-8+arg_0], rbx
0x18003475d  push    rbp
0x18003475e  mov     rbp, rsp
0x180034761  sub     rsp, 80h
0x180034768  xorps   xmm0, xmm0
0x18003476b  mov     [rbp+KeyHandle], 0
0x180034773  xorps   xmm1, xmm1
0x180034776  mov     [rbp+Type], 0
0x18003477d  lea     r8, [rbp+KeyName]; struct _UNICODE_STRING *
0x180034781  lea     rdx, [rbp+var_50]; struct _UNICODE_STRING *
0x180034785  movups  xmmword ptr [rbp+var_50.Length], xmm0
0x180034789  movups  xmmword ptr [rbp+KeyName.Length], xmm1
0x18003478d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180034791  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180034795  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180034799  call    SampBuildAliasMembersKeyName
0x18003479e  mov     ebx, eax
0x1800347a0  test    eax, eax
0x1800347a2  js      loc_1800348AE
0x1800347a8  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; Context
0x1800347af  lea     r8, [rbp+KeyName]; KeyName
0x1800347b3  xor     r9d, r9d; ValueType
0x1800347b6  mov     [rsp+80h+ValueDataSize], 0; ValueDataSize
0x1800347be  mov     [rsp+80h+ValueData], 0; ValueData
0x1800347c7  lea     edx, [r9+1]; ActionType
0x1800347cb  call    cs:__imp_RtlAddActionToRXact
0x1800347d1  mov     ebx, eax
0x1800347d3  test    eax, eax
0x1800347d5  js      loc_18003489C
0x1800347db  mov     rax, cs:SampKey
0x1800347e2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800347e6  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1800347ea  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800347ee  lea     rax, [rbp+var_50]
0x1800347f2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800347f9  xorps   xmm0, xmm0
0x1800347fc  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180034800  xor     r9d, r9d; Unused
0x180034803  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18003480a  mov     edx, 20019h; DesiredAccess
0x18003480f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180034814  call    cs:__imp_RtlpNtOpenKey
0x18003481a  mov     ebx, eax
0x18003481c  test    eax, eax
0x18003481e  js      short loc_18003489C
0x180034820  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180034824  lea     rdx, [rbp+Type]; Type
0x180034828  xor     r9d, r9d; DataLength
0x18003482b  mov     [rsp+80h+ValueData], 0; Unused
0x180034834  xor     r8d, r8d; Data
0x180034837  call    cs:__imp_RtlpNtQueryValueKey
0x18003483d  mov     ebx, eax
0x18003483f  test    eax, eax
0x180034841  js      short loc_180034892
0x180034843  mov     r9d, [rbp+Type]
0x180034847  lea     r8, [rbp+var_50]; KeyName
0x18003484b  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; Context
0x180034852  add     r9d, 0FFFFFFFFh; ValueType
0x180034856  mov     [rsp+80h+ValueDataSize], 0; ValueDataSize
0x18003485e  mov     [rbp+Type], r9d
0x180034862  mov     [rsp+80h+ValueData], 0; ValueData
0x18003486b  jz      short loc_18003487C
0x18003486d  mov     edx, 2; ActionType
0x180034872  call    cs:__imp_RtlAddActionToRXact
0x180034878  mov     ebx, eax
0x18003487a  jmp     short loc_180034892
0x18003487c  xor     r9d, r9d; ValueType
0x18003487f  lea     edx, [r9+1]; ActionType
0x180034883  call    cs:__imp_RtlAddActionToRXact
0x180034889  mov     ebx, eax
0x18003488b  xor     eax, eax
0x18003488d  test    ebx, ebx
0x18003488f  cmovns  ebx, eax
0x180034892  mov     rcx, [rbp+KeyHandle]; Handle
0x180034896  call    cs:__imp_NtClose
0x18003489c  lea     rcx, [rbp+var_50]
0x1800348a0  call    SampFreeUnicodeString
0x1800348a5  lea     rcx, [rbp+KeyName]
0x1800348a9  call    SampFreeUnicodeString
0x1800348ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800348b5  test    dword ptr [rcx+44h], 20000h
0x1800348bc  jz      short loc_1800348DA
0x1800348be  mov     rcx, [rcx+38h]
0x1800348c2  lea     r8, WPP_799c13f926ef3db95a69a5604490dfde_Traceguids
0x1800348c9  mov     edx, 36h ; '6'
0x1800348ce  mov     dword ptr [rsp+80h+ValueData], ebx
0x1800348d2  mov     r9d, ebx
0x1800348d5  call    WPP_SF_Dd
0x1800348da  mov     eax, ebx
0x1800348dc  mov     rbx, [rsp+80h+arg_0]
0x1800348e4  add     rsp, 80h
0x1800348eb  pop     rbp
0x1800348ec  retn
```
