# WldpQueryPolicySettingEnabled2(ushort const *,int *)

- ea: `0x180015cb0`
- end: `0x1800162f4`
- name: `?WldpQueryPolicySettingEnabled2@@YAJPEBGPEAH@Z`
- size: `1604`
- prototype: `__int64 __fastcall(PCWSTR SourceString, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c210`

## callees

- `0x180015cb0`
- `0x18002333c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180015ced`
- `ntdll!RtlInitUnicodeString` at `0x180015ced`
- `ntdll!RtlEqualUnicodeString` at `0x180015d16`
- `ntdll!RtlEqualUnicodeString` at `0x180015d32`
- `ntdll!RtlEqualUnicodeString` at `0x180015d4e`
- `ntdll!RtlEqualUnicodeString` at `0x180015d6a`
- `ntdll!RtlEqualUnicodeString` at `0x180015d86`
- `ntdll!RtlEqualUnicodeString` at `0x180015d16`
- `ntdll!RtlEqualUnicodeString` at `0x180015d32`
- `ntdll!RtlEqualUnicodeString` at `0x180015d4e`
- `ntdll!RtlEqualUnicodeString` at `0x180015d6a`
- `ntdll!RtlEqualUnicodeString` at `0x180015d86`
- `ntdll!RtlIsApiSetImplemented` at `0x180015f4f`
- `ntdll!RtlIsApiSetImplemented` at `0x180015f4f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180015d94`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180015d94`
- `ntdll!ZwFilterBootOption` at `0x180015dc2`
- `ntdll!ZwFilterBootOption` at `0x180015e0a`
- `ntdll!ZwFilterBootOption` at `0x180015e4a`
- `ntdll!ZwFilterBootOption` at `0x180015e8a`
- `ntdll!ZwFilterBootOption` at `0x180015eca`
- `ntdll!ZwFilterBootOption` at `0x180015f0a`
- `ntdll!ZwFilterBootOption` at `0x180016094`
- `ntdll!ZwFilterBootOption` at `0x1800160dc`
- `ntdll!ZwFilterBootOption` at `0x18001611c`
- `ntdll!ZwFilterBootOption` at `0x18001615c`
- `ntdll!ZwFilterBootOption` at `0x18001619c`
- `ntdll!ZwFilterBootOption` at `0x1800161dc`
- `ntdll!ZwFilterBootOption` at `0x180015dc2`
- `ntdll!ZwFilterBootOption` at `0x180015e0a`
- `ntdll!ZwFilterBootOption` at `0x180015e4a`
- `ntdll!ZwFilterBootOption` at `0x180015e8a`
- `ntdll!ZwFilterBootOption` at `0x180015eca`
- `ntdll!ZwFilterBootOption` at `0x180015f0a`
- `ntdll!ZwFilterBootOption` at `0x180016094`
- `ntdll!ZwFilterBootOption` at `0x1800160dc`
- `ntdll!ZwFilterBootOption` at `0x18001611c`
- `ntdll!ZwFilterBootOption` at `0x18001615c`
- `ntdll!ZwFilterBootOption` at `0x18001619c`
- `ntdll!ZwFilterBootOption` at `0x1800161dc`
- `ntdll!NtQuerySecurityPolicy` at `0x180015fde`
- `ntdll!NtQuerySecurityPolicy` at `0x180016048`
- `ntdll!NtQuerySecurityPolicy` at `0x180015fde`
- `ntdll!NtQuerySecurityPolicy` at `0x180016048`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x180015f97`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x180015f97`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x180016067`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x180016067`

## string_xrefs

- `0x180015f48`: `SchemaExt-Composable-Vail`

## pseudocode

```c
int __fastcall WldpQueryPolicySettingEnabled2(PCWSTR SourceString, int *a2)
{
  int Win32SubsystemHost; // edi
  int v4; // eax
  int v5; // edi
  int v6; // esi
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // esi
  int v17; // edi
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
  int v25; // [rsp+80h] [rbp+18h] BYREF
  int v26; // [rsp+90h] [rbp+28h] BYREF
  int v27; // [rsp+98h] [rbp+30h] BYREF

  if ( !SourceString || !a2 )
    return -805306355;
  *a2 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  if ( (unsigned __int8)IsQueryWin32SubsystemHostPresent() )
    Win32SubsystemHost = QueryWin32SubsystemHost();
  else
    Win32SubsystemHost = 0;
  if ( RtlEqualUnicodeString(&DestinationString, &stru_180043080, 1u)
    && (!(unsigned int)RtlIsApiSetImplemented("SchemaExt-Composable-Vail") || (unsigned int)(Win32SubsystemHost - 1) > 1) )
  {
    v25 = 0;
    GetPersistedRegistryValueW(
      L"CIVAILSettings",
      L"SYSTEM\\CurrentControlSet\\Control\\CI\\VAILSettings\\",
      L"GuestWindowsMode",
      16,
      0,
      &v25,
      4,
      0);
    v13 = v25;
LABEL_28:
    *a2 = v13;
    goto LABEL_29;
  }
  if ( RtlEqualUnicodeString(&DestinationString, &stru_180043050, 1u)
    || RtlEqualUnicodeString(&DestinationString, &stru_180043060, 1u) )
  {
    v26 = 0;
    LOBYTE(v25) = 0;
    v27 = 1;
    v14 = NtQuerySecurityPolicy(&qword_1800430F0, &qword_1800430D0, &qword_1800430E0, &v26, &v25, &v27);
    if ( v14 < 0 )
    {
      if ( v14 != -1073741275 )
        return v14 | 0x10000000;
      *a2 = 0;
LABEL_30:
      v26 = 0;
      LOBYTE(v25) = 0;
      v27 = 1;
      v14 = NtQuerySecurityPolicy(&qword_1800430B0, L":<", &DestinationString, &v26, &v25, &v27);
      if ( v14 >= 0 )
      {
        if ( v26 )
          v23 = 0;
        else
          v23 = (unsigned __int8)v25;
        *a2 = v23;
        return 0;
      }
      if ( v14 == -1073741275 )
      {
        *a2 = 0;
        return 0;
      }
      return v14 | 0x10000000;
    }
    v13 = (unsigned __int8)v25;
    if ( v26 )
      v13 = 0;
    goto LABEL_28;
  }
  if ( RtlEqualUnicodeString(&DestinationString, &stru_180043090, 1u) )
  {
    LOBYTE(v25) = 1;
    v15 = ZwFilterBootOption(1, 270532611, 637534368, &v25, 1) | 0x10000000;
    if ( v15 == 0x10000000 || (v16 = 1, v17 = 0, v15 == -1874657274) )
    {
      v17 = 1;
      v16 = v15;
    }
    LOBYTE(v25) = 1;
    v18 = ZwFilterBootOption(1, 270532611, 369098768, &v25, 1) | 0x10000000;
    if ( v18 == 0x10000000 || v18 == -1874657274 )
    {
      v17 = 1;
      v16 = v18;
    }
    LOBYTE(v25) = 1;
    v19 = ZwFilterBootOption(1, 270532611, 369098825, &v25, 1) | 0x10000000;
    if ( v19 == 0x10000000 || v19 == -1874657274 )
    {
      v17 = 1;
      v16 = v19;
    }
    LOBYTE(v25) = 1;
    v20 = ZwFilterBootOption(1, 270532611, 637534450, &v25, 1) | 0x10000000;
    if ( v20 == 0x10000000 || v20 == -1874657274 )
    {
      v17 = 1;
      v16 = v20;
    }
    LOBYTE(v25) = 1;
    v21 = ZwFilterBootOption(1, 270532610, 369098768, &v25, 1) | 0x10000000;
    if ( v21 == 0x10000000 || v21 == -1874657274 )
    {
      v17 = 1;
      v16 = v21;
    }
    LOBYTE(v25) = 1;
    v22 = ZwFilterBootOption(1, 270532610, 369098825, &v25, 1) | 0x10000000;
    if ( v22 == 0x10000000 || v22 == -1874657274 )
    {
      v17 = 1;
      v16 = v22;
    }
    if ( v16 < 0 )
    {
      *a2 = 0;
      return v16;
    }
    *a2 = v17;
  }
  else if ( RtlEqualUnicodeString(&DestinationString, &stru_1800430A0, 1u) )
  {
    if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
    {
      *a2 = 1;
      return 0;
    }
    LOBYTE(v25) = 1;
    v4 = ZwFilterBootOption(1, 270532611, 637534368, &v25, 1) | 0x10000000;
    if ( v4 == 0x10000000 || (v5 = 1, v6 = 0, v4 == -1874657274) )
    {
      v6 = 1;
      v5 = v4;
    }
    LOBYTE(v25) = 1;
    v7 = ZwFilterBootOption(1, 270532611, 369098768, &v25, 1) | 0x10000000;
    if ( v7 == 0x10000000 || v7 == -1874657274 )
    {
      v6 = 1;
      v5 = v7;
    }
    LOBYTE(v25) = 1;
    v8 = ZwFilterBootOption(1, 270532611, 369098825, &v25, 1) | 0x10000000;
    if ( v8 == 0x10000000 || v8 == -1874657274 )
    {
      v6 = 1;
      v5 = v8;
    }
    LOBYTE(v25) = 1;
    v9 = ZwFilterBootOption(1, 270532611, 637534450, &v25, 1) | 0x10000000;
    if ( v9 == 0x10000000 || v9 == -1874657274 )
    {
      v6 = 1;
      v5 = v9;
    }
    LOBYTE(v25) = 1;
    v10 = ZwFilterBootOption(1, 270532610, 369098768, &v25, 1) | 0x10000000;
    if ( v10 == 0x10000000 || v10 == -1874657274 )
    {
      v6 = 1;
      v5 = v10;
    }
    LOBYTE(v25) = 1;
    v11 = ZwFilterBootOption(1, 270532610, 369098825, &v25, 1) | 0x10000000;
    if ( v11 == 0x10000000 || v11 == -1874657274 )
    {
      v6 = 1;
      v5 = v11;
    }
    if ( v5 < 0 )
    {
      *a2 = 0;
      return v5;
    }
    *a2 = v6;
  }
LABEL_29:
  if ( !*a2 )
    goto LABEL_30;
  return 0;
}

```

## disassembly

```asm
0x180015cb0  push    rbp
0x180015cb2  push    rbx
0x180015cb3  mov     rbp, rsp
0x180015cb6  sub     rsp, 68h
0x180015cba  mov     rbx, rdx
0x180015cbd  test    rcx, rcx
0x180015cc0  jz      loc_180015F3C
0x180015cc6  test    rdx, rdx
0x180015cc9  jz      loc_180015F3C
0x180015ccf  mov     [rsp+68h+var_18], r14
0x180015cd4  xorps   xmm0, xmm0
0x180015cd7  xor     r14d, r14d
0x180015cda  mov     [rsp+68h+var_10], rdi
0x180015cdf  mov     [rdx], r14d
0x180015ce2  mov     rdx, rcx; SourceString
0x180015ce5  lea     rcx, [rbp+DestinationString]; DestinationString
0x180015ce9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180015ced  call    cs:__imp_RtlInitUnicodeString
0x180015cf3  call    IsQueryWin32SubsystemHostPresent
0x180015cf8  test    al, al
0x180015cfa  jnz     loc_180016067
0x180015d00  mov     edi, r14d
0x180015d03  mov     r8b, 1; CaseInsensitive
0x180015d06  mov     [rsp+68h+var_8], rsi
0x180015d0b  lea     rdx, stru_180043080; String2
0x180015d12  lea     rcx, [rbp+DestinationString]; String1
0x180015d16  call    cs:__imp_RtlEqualUnicodeString
0x180015d1c  test    al, al
0x180015d1e  jnz     loc_180015F48
0x180015d24  mov     r8b, 1; CaseInsensitive
0x180015d27  lea     rdx, stru_180043050; String2
0x180015d2e  lea     rcx, [rbp+DestinationString]; String1
0x180015d32  call    cs:__imp_RtlEqualUnicodeString
0x180015d38  test    al, al
0x180015d3a  jnz     loc_18001600E
0x180015d40  mov     r8b, 1; CaseInsensitive
0x180015d43  lea     rdx, stru_180043060; String2
0x180015d4a  lea     rcx, [rbp+DestinationString]; String1
0x180015d4e  call    cs:__imp_RtlEqualUnicodeString
0x180015d54  test    al, al
0x180015d56  jnz     loc_18001600E
0x180015d5c  mov     r8b, 1; CaseInsensitive
0x180015d5f  lea     rdx, stru_180043090; String2
0x180015d66  lea     rcx, [rbp+DestinationString]; String1
0x180015d6a  call    cs:__imp_RtlEqualUnicodeString
0x180015d70  test    al, al
0x180015d72  jnz     loc_180016074
0x180015d78  mov     r8b, 1; CaseInsensitive
0x180015d7b  lea     rdx, stru_1800430A0; String2
0x180015d82  lea     rcx, [rbp+DestinationString]; String1
0x180015d86  call    cs:__imp_RtlEqualUnicodeString
0x180015d8c  test    al, al
0x180015d8e  jz      loc_180015FA2
0x180015d94  call    cs:__imp_RtlIsStateSeparationEnabled
0x180015d9a  test    al, al
0x180015d9c  jz      loc_18001627B
0x180015da2  lea     r9, [rbp+arg_0]
0x180015da6  mov     byte ptr [rbp+arg_0], 1
0x180015daa  mov     edx, 10200003h
0x180015daf  mov     dword ptr [rsp+68h+var_48], 1
0x180015db7  mov     ecx, 1
0x180015dbc  mov     r8d, 260000A0h
0x180015dc2  call    cs:__imp_ZwFilterBootOption
0x180015dc8  bts     eax, 1Ch
0x180015dcc  cmp     eax, 10000000h
0x180015dd1  jz      loc_180016286
0x180015dd7  mov     edi, 1
0x180015ddc  mov     esi, r14d
0x180015ddf  cmp     eax, 90430006h
0x180015de4  jz      loc_180016286
0x180015dea  lea     r9, [rbp+arg_0]
0x180015dee  mov     byte ptr [rbp+arg_0], 1
0x180015df2  mov     edx, 10200003h
0x180015df7  mov     dword ptr [rsp+68h+var_48], 1
0x180015dff  mov     ecx, 1
0x180015e04  mov     r8d, 16000010h
0x180015e0a  call    cs:__imp_ZwFilterBootOption
0x180015e10  bts     eax, 1Ch
0x180015e14  cmp     eax, 10000000h
0x180015e19  jz      loc_180016292
0x180015e1f  cmp     eax, 90430006h
0x180015e24  jz      loc_180016292
0x180015e2a  lea     r9, [rbp+arg_0]
0x180015e2e  mov     byte ptr [rbp+arg_0], 1
0x180015e32  mov     edx, 10200003h
0x180015e37  mov     dword ptr [rsp+68h+var_48], 1
0x180015e3f  mov     ecx, 1
0x180015e44  mov     r8d, 16000049h
0x180015e4a  call    cs:__imp_ZwFilterBootOption
0x180015e50  bts     eax, 1Ch
0x180015e54  cmp     eax, 10000000h
0x180015e59  jz      loc_18001629E
0x180015e5f  cmp     eax, 90430006h
0x180015e64  jz      loc_18001629E
0x180015e6a  lea     r9, [rbp+arg_0]
0x180015e6e  mov     byte ptr [rbp+arg_0], 1
0x180015e72  mov     edx, 10200003h
0x180015e77  mov     dword ptr [rsp+68h+var_48], 1
0x180015e7f  mov     ecx, 1
0x180015e84  mov     r8d, 260000F2h
0x180015e8a  call    cs:__imp_ZwFilterBootOption
0x180015e90  bts     eax, 1Ch
0x180015e94  cmp     eax, 10000000h
0x180015e99  jz      loc_1800162AA
0x180015e9f  cmp     eax, 90430006h
0x180015ea4  jz      loc_1800162AA
0x180015eaa  lea     r9, [rbp+arg_0]
0x180015eae  mov     byte ptr [rbp+arg_0], 1
0x180015eb2  mov     edx, 10200002h
0x180015eb7  mov     dword ptr [rsp+68h+var_48], 1
0x180015ebf  mov     ecx, 1
0x180015ec4  mov     r8d, 16000010h
0x180015eca  call    cs:__imp_ZwFilterBootOption
0x180015ed0  bts     eax, 1Ch
0x180015ed4  cmp     eax, 10000000h
0x180015ed9  jz      loc_1800162B6
0x180015edf  cmp     eax, 90430006h
0x180015ee4  jz      loc_1800162B6
0x180015eea  lea     r9, [rbp+arg_0]
0x180015eee  mov     byte ptr [rbp+arg_0], 1
0x180015ef2  mov     edx, 10200002h
0x180015ef7  mov     dword ptr [rsp+68h+var_48], 1
0x180015eff  mov     ecx, 1
0x180015f04  mov     r8d, 16000049h
0x180015f0a  call    cs:__imp_ZwFilterBootOption
0x180015f10  bts     eax, 1Ch
0x180015f14  cmp     eax, 10000000h
0x180015f19  jz      loc_1800162C2
0x180015f1f  cmp     eax, 90430006h
0x180015f24  jz      loc_1800162C2
0x180015f2a  test    edi, edi
0x180015f2c  jns     loc_1800162CE
0x180015f32  mov     [rbx], r14d
0x180015f35  mov     eax, edi
0x180015f37  jmp     loc_180015FF8
0x180015f3c  mov     eax, 0D000000Dh
0x180015f41  add     rsp, 68h
0x180015f45  pop     rbx
0x180015f46  pop     rbp
0x180015f47  retn
0x180015f48  lea     rcx, aSchemaextCompo; "SchemaExt-Composable-Vail"
0x180015f4f  call    cs:__imp_RtlIsApiSetImplemented
0x180015f55  test    eax, eax
0x180015f57  jnz     loc_18001621B
0x180015f5d  mov     [rsp+68h+var_30], r14
0x180015f62  lea     rax, [rbp+arg_0]
0x180015f66  mov     [rsp+68h+var_38], 4
0x180015f6e  lea     r8, aGuestwindowsmo; "GuestWindowsMode"
0x180015f75  mov     [rsp+68h+var_40], rax
0x180015f7a  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\CI"...
0x180015f81  mov     r9d, 10h
0x180015f87  mov     [rsp+68h+var_48], r14
0x180015f8c  lea     rcx, aCivailsettings; "CIVAILSettings"
0x180015f93  mov     [rbp+arg_0], r14d
0x180015f97  call    cs:__imp_GetPersistedRegistryValueW
0x180015f9d  mov     eax, [rbp+arg_0]
0x180015fa0  mov     [rbx], eax
0x180015fa2  cmp     [rbx], r14d
0x180015fa5  jnz     short loc_180015FF6
0x180015fa7  lea     rax, [rbp+arg_18]
0x180015fab  mov     [rbp+arg_10], r14d
0x180015faf  mov     [rsp+68h+var_40], rax
0x180015fb4  lea     r9, [rbp+arg_10]
0x180015fb8  lea     rax, [rbp+arg_0]
0x180015fbc  mov     byte ptr [rbp+arg_0], r14b
0x180015fc0  lea     r8, [rbp+DestinationString]
0x180015fc4  mov     [rsp+68h+var_48], rax
0x180015fc9  lea     rdx, asc_1800430C0; ":<"
0x180015fd0  mov     [rbp+arg_18], 1
0x180015fd7  lea     rcx, qword_1800430B0
0x180015fde  call    cs:__imp_NtQuerySecurityPolicy
0x180015fe4  test    eax, eax
0x180015fe6  jns     loc_1800161FF
0x180015fec  cmp     eax, 0C0000225h
0x180015ff1  jnz     short loc_180016061
0x180015ff3  mov     [rbx], r14d
0x180015ff6  xor     eax, eax
0x180015ff8  mov     rsi, [rsp+68h+var_8]
0x180015ffd  mov     rdi, [rsp+68h+var_10]
0x180016002  mov     r14, [rsp+68h+var_18]
0x180016007  add     rsp, 68h
0x18001600b  pop     rbx
0x18001600c  pop     rbp
0x18001600d  retn
0x18001600e  lea     rax, [rbp+arg_18]
0x180016012  mov     [rbp+arg_10], r14d
0x180016016  mov     [rsp+68h+var_40], rax
0x18001601b  lea     r9, [rbp+arg_10]
0x18001601f  lea     rax, [rbp+arg_0]
0x180016023  mov     byte ptr [rbp+arg_0], r14b
0x180016027  lea     r8, qword_1800430E0
0x18001602e  mov     [rsp+68h+var_48], rax
0x180016033  lea     rdx, qword_1800430D0
0x18001603a  mov     [rbp+arg_18], 1
0x180016041  lea     rcx, qword_1800430F0
0x180016048  call    cs:__imp_NtQuerySecurityPolicy
0x18001604e  test    eax, eax
0x180016050  jns     loc_1800162D5
0x180016056  cmp     eax, 0C0000225h
0x18001605b  jz      loc_180016213
0x180016061  bts     eax, 1Ch
0x180016065  jmp     short loc_180015FF8
0x180016067  call    cs:__imp_QueryWin32SubsystemHost
0x18001606d  mov     edi, eax
0x18001606f  jmp     loc_180015D03
0x180016074  lea     r9, [rbp+arg_0]
0x180016078  mov     byte ptr [rbp+arg_0], 1
0x18001607c  mov     edx, 10200003h
0x180016081  mov     dword ptr [rsp+68h+var_48], 1
0x180016089  mov     ecx, 1
0x18001608e  mov     r8d, 260000A0h
0x180016094  call    cs:__imp_ZwFilterBootOption
0x18001609a  bts     eax, 1Ch
0x18001609e  cmp     eax, 10000000h
0x1800160a3  jz      loc_18001622C
0x1800160a9  mov     esi, 1
0x1800160ae  mov     edi, r14d
0x1800160b1  cmp     eax, 90430006h
0x1800160b6  jz      loc_18001622C
0x1800160bc  lea     r9, [rbp+arg_0]
0x1800160c0  mov     byte ptr [rbp+arg_0], 1
0x1800160c4  mov     edx, 10200003h
0x1800160c9  mov     dword ptr [rsp+68h+var_48], 1
0x1800160d1  mov     ecx, 1
0x1800160d6  mov     r8d, 16000010h
0x1800160dc  call    cs:__imp_ZwFilterBootOption
0x1800160e2  bts     eax, 1Ch
0x1800160e6  cmp     eax, 10000000h
0x1800160eb  jz      loc_180016238
0x1800160f1  cmp     eax, 90430006h
0x1800160f6  jz      loc_180016238
0x1800160fc  lea     r9, [rbp+arg_0]
0x180016100  mov     byte ptr [rbp+arg_0], 1
0x180016104  mov     edx, 10200003h
0x180016109  mov     dword ptr [rsp+68h+var_48], 1
0x180016111  mov     ecx, 1
0x180016116  mov     r8d, 16000049h
0x18001611c  call    cs:__imp_ZwFilterBootOption
0x180016122  bts     eax, 1Ch
0x180016126  cmp     eax, 10000000h
0x18001612b  jz      loc_180016244
0x180016131  cmp     eax, 90430006h
0x180016136  jz      loc_180016244
0x18001613c  lea     r9, [rbp+arg_0]
0x180016140  mov     byte ptr [rbp+arg_0], 1
0x180016144  mov     edx, 10200003h
0x180016149  mov     dword ptr [rsp+68h+var_48], 1
0x180016151  mov     ecx, 1
0x180016156  mov     r8d, 260000F2h
0x18001615c  call    cs:__imp_ZwFilterBootOption
0x180016162  bts     eax, 1Ch
0x180016166  cmp     eax, 10000000h
0x18001616b  jz      loc_180016250
0x180016171  cmp     eax, 90430006h
0x180016176  jz      loc_180016250
0x18001617c  lea     r9, [rbp+arg_0]
0x180016180  mov     byte ptr [rbp+arg_0], 1
0x180016184  mov     edx, 10200002h
0x180016189  mov     dword ptr [rsp+68h+var_48], 1
0x180016191  mov     ecx, 1
0x180016196  mov     r8d, 16000010h
0x18001619c  call    cs:__imp_ZwFilterBootOption
0x1800161a2  bts     eax, 1Ch
0x1800161a6  cmp     eax, 10000000h
0x1800161ab  jz      loc_18001625C
0x1800161b1  cmp     eax, 90430006h
0x1800161b6  jz      loc_18001625C
0x1800161bc  lea     r9, [rbp+arg_0]
0x1800161c0  mov     byte ptr [rbp+arg_0], 1
0x1800161c4  mov     edx, 10200002h
0x1800161c9  mov     dword ptr [rsp+68h+var_48], 1
0x1800161d1  mov     ecx, 1
0x1800161d6  mov     r8d, 16000049h
0x1800161dc  call    cs:__imp_ZwFilterBootOption
0x1800161e2  bts     eax, 1Ch
0x1800161e6  cmp     eax, 10000000h
0x1800161eb  jz      short loc_180016268
0x1800161ed  cmp     eax, 90430006h
0x1800161f2  jz      short loc_180016268
0x1800161f4  test    esi, esi
0x1800161f6  js      short loc_180016271
0x1800161f8  mov     [rbx], edi
0x1800161fa  jmp     loc_180015FA2
0x1800161ff  cmp     [rbp+arg_10], r14d
0x180016203  jz      loc_1800162EB
0x180016209  mov     eax, r14d
0x18001620c  mov     [rbx], eax
0x18001620e  jmp     loc_180015FF6
0x180016213  mov     [rbx], r14d
0x180016216  jmp     loc_180015FA7
0x18001621b  lea     eax, [rdi-1]
0x18001621e  cmp     eax, 1
0x180016221  jbe     loc_180015D24
0x180016227  jmp     loc_180015F5D
0x18001622c  mov     edi, 1
0x180016231  mov     esi, eax
0x180016233  jmp     loc_1800160BC
0x180016238  mov     edi, 1
0x18001623d  mov     esi, eax
0x18001623f  jmp     loc_1800160FC
  ... truncated ...
```
