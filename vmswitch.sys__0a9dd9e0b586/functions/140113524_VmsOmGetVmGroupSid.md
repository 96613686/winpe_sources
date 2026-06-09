# VmsOmGetVmGroupSid

- ea: `0x140113524`
- end: `0x140113699`
- name: `VmsOmGetVmGroupSid`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401136a0`

## callees

- `0x140027a64`
- `0x14002e0f0`
- `0x140046f1c`
- `0x14008497c`
- `0x140113524`
- `0x1401bbcb0`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x1401135f5`
- `ntoskrnl!RtlInitializeSid` at `0x1401135f5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14011360c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140113626`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14011360c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140113626`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140113591`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140113591`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113642`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113642`
- `ntoskrnl!ExAllocatePool2` at `0x1401135ac`
- `ntoskrnl!ExAllocatePool2` at `0x1401135ac`

## string_xrefs

- `0x140113564`: `VmGroupSid`

## pseudocode

```c
__int64 __fastcall VmsOmGetVmGroupSid(_QWORD *a1, int a2)
{
  ULONG v3; // eax
  char v4; // bp
  void *Pool2; // rax
  int v6; // edx
  void *v7; // rdi
  NTSTATUS v8; // ebx
  int v9; // edx
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+40h] [rbp-28h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  if ( !a1 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      15,
      (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
      (__int64)"VmGroupSid");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v3 = RtlLengthRequiredSid(2u);
  v4 = v3;
  Pool2 = (void *)ExAllocatePool2(256, v3, 1649374038);
  v7 = Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741670;
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_ld(VmsIfrLog, v6, 20, 16, (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids, v4, 154);
LABEL_8:
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_id(VmsIfrLog, v9, 20, 17, (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids, (char)a1, v8);
    return (unsigned int)v8;
  }
  v8 = RtlInitializeSid(Pool2, &IdentifierAuthority, 2u);
  if ( v8 < 0 )
  {
    ExFreePoolWithTag(v7, 0x624F7356u);
    goto LABEL_8;
  }
  *RtlSubAuthoritySid(v7, 0) = 83;
  *RtlSubAuthoritySid(v7, 1u) = 0;
  *a1 = v7;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140113524  mov     r11, rsp
0x140113527  mov     [r11+10h], rbx
0x14011352b  mov     [r11+18h], rbp
0x14011352f  push    rsi
0x140113530  push    rdi
0x140113531  push    r15
0x140113533  sub     rsp, 50h
0x140113537  mov     rax, cs:__security_cookie
0x14011353e  xor     rax, rsp
0x140113541  mov     [rsp+68h+var_20], rax
0x140113546  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], 0
0x14011354e  mov     rsi, rcx
0x140113551  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 500h
0x140113558  lea     r15, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x14011355f  test    rcx, rcx
0x140113562  jnz     short loc_14011358C
0x140113564  lea     rax, aVmgroupsid; "VmGroupSid"
0x14011356b  lea     r9d, [rcx+0Fh]
0x14011356f  mov     [r11-40h], rax
0x140113573  lea     r8d, [rcx+13h]
0x140113577  mov     [r11-48h], r15
0x14011357b  mov     rcx, cs:VmsIfrLog
0x140113582  call    WPP_RECORDER_SF_s
0x140113587  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmGroupSid")
0x14011358c  mov     ecx, 2; SubAuthorityCount
0x140113591  call    cs:__imp_RtlLengthRequiredSid
0x140113598  nop     dword ptr [rax+rax+00h]
0x14011359d  mov     edx, eax
0x14011359f  mov     ecx, 100h
0x1401135a4  mov     r8d, 624F7356h
0x1401135aa  mov     ebp, eax
0x1401135ac  call    cs:__imp_ExAllocatePool2
0x1401135b3  nop     dword ptr [rax+rax+00h]
0x1401135b8  mov     rdi, rax
0x1401135bb  test    rax, rax
0x1401135be  jnz     short loc_1401135EA
0x1401135c0  mov     ebx, 0C000009Ah
0x1401135c5  mov     rcx, cs:VmsIfrLog
0x1401135cc  lea     r9d, [rax+10h]
0x1401135d0  mov     [rsp+68h+var_38], ebx
0x1401135d4  lea     r8d, [rax+14h]
0x1401135d8  mov     dword ptr [rsp+68h+var_40], ebp
0x1401135dc  mov     dl, 2
0x1401135de  mov     [rsp+68h+var_48], r15
0x1401135e3  call    WPP_RECORDER_SF_ld
0x1401135e8  jmp     short loc_14011364E
0x1401135ea  mov     r8b, 2; SubAuthorityCount
0x1401135ed  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x1401135f2  mov     rcx, rdi; Sid
0x1401135f5  call    cs:__imp_RtlInitializeSid
0x1401135fc  nop     dword ptr [rax+rax+00h]
0x140113601  mov     ebx, eax
0x140113603  mov     rcx, rdi; P
0x140113606  test    eax, eax
0x140113608  js      short loc_14011363D
0x14011360a  xor     edx, edx; SubAuthority
0x14011360c  call    cs:__imp_RtlSubAuthoritySid
0x140113613  nop     dword ptr [rax+rax+00h]
0x140113618  mov     edx, 1; SubAuthority
0x14011361d  mov     rcx, rdi; Sid
0x140113620  mov     dword ptr [rax], 53h ; 'S'
0x140113626  call    cs:__imp_RtlSubAuthoritySid
0x14011362d  nop     dword ptr [rax+rax+00h]
0x140113632  mov     dword ptr [rax], 0
0x140113638  mov     [rsi], rdi
0x14011363b  jmp     short loc_140113674
0x14011363d  mov     edx, 624F7356h; Tag
0x140113642  call    cs:__imp_ExFreePoolWithTag
0x140113649  nop     dword ptr [rax+rax+00h]
0x14011364e  mov     rcx, cs:VmsIfrLog
0x140113655  mov     r9d, 11h
0x14011365b  mov     [rsp+68h+var_38], ebx
0x14011365f  mov     dl, 2
0x140113661  mov     [rsp+68h+var_40], rsi
0x140113666  mov     [rsp+68h+var_48], r15
0x14011366b  lea     r8d, [r9+3]
0x14011366f  call    WPP_RECORDER_SF_id
0x140113674  mov     eax, ebx
0x140113676  mov     rcx, [rsp+68h+var_20]
0x14011367b  xor     rcx, rsp; StackCookie
0x14011367e  call    __security_check_cookie
0x140113683  lea     r11, [rsp+68h+var_18]
0x140113688  mov     rbx, [r11+28h]
0x14011368c  mov     rbp, [r11+30h]
0x140113690  mov     rsp, r11
0x140113693  pop     r15
0x140113695  pop     rdi
0x140113696  pop     rsi
0x140113697  retn
```
