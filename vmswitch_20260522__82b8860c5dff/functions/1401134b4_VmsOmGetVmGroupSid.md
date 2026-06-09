# VmsOmGetVmGroupSid

- ea: `0x1401134b4`
- end: `0x140113629`
- name: `VmsOmGetVmGroupSid`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140113630`

## callees

- `0x140027a64`
- `0x14002e0f0`
- `0x140046f1c`
- `0x14008497c`
- `0x1401134b4`
- `0x1401bbc40`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x140113585`
- `ntoskrnl!RtlInitializeSid` at `0x140113585`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14011359c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401135b6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14011359c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401135b6`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140113521`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140113521`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401135d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401135d2`
- `ntoskrnl!ExAllocatePool2` at `0x14011353c`
- `ntoskrnl!ExAllocatePool2` at `0x14011353c`

## string_xrefs

- `0x1401134f4`: `VmGroupSid`

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
0x1401134b4  mov     r11, rsp
0x1401134b7  mov     [r11+10h], rbx
0x1401134bb  mov     [r11+18h], rbp
0x1401134bf  push    rsi
0x1401134c0  push    rdi
0x1401134c1  push    r15
0x1401134c3  sub     rsp, 50h
0x1401134c7  mov     rax, cs:__security_cookie
0x1401134ce  xor     rax, rsp
0x1401134d1  mov     [rsp+68h+var_20], rax
0x1401134d6  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], 0
0x1401134de  mov     rsi, rcx
0x1401134e1  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 500h
0x1401134e8  lea     r15, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x1401134ef  test    rcx, rcx
0x1401134f2  jnz     short loc_14011351C
0x1401134f4  lea     rax, aVmgroupsid; "VmGroupSid"
0x1401134fb  lea     r9d, [rcx+0Fh]
0x1401134ff  mov     [r11-40h], rax
0x140113503  lea     r8d, [rcx+13h]
0x140113507  mov     [r11-48h], r15
0x14011350b  mov     rcx, cs:VmsIfrLog
0x140113512  call    WPP_RECORDER_SF_s
0x140113517  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmGroupSid")
0x14011351c  mov     ecx, 2; SubAuthorityCount
0x140113521  call    cs:__imp_RtlLengthRequiredSid
0x140113528  nop     dword ptr [rax+rax+00h]
0x14011352d  mov     edx, eax
0x14011352f  mov     ecx, 100h
0x140113534  mov     r8d, 624F7356h
0x14011353a  mov     ebp, eax
0x14011353c  call    cs:__imp_ExAllocatePool2
0x140113543  nop     dword ptr [rax+rax+00h]
0x140113548  mov     rdi, rax
0x14011354b  test    rax, rax
0x14011354e  jnz     short loc_14011357A
0x140113550  mov     ebx, 0C000009Ah
0x140113555  mov     rcx, cs:VmsIfrLog
0x14011355c  lea     r9d, [rax+10h]
0x140113560  mov     [rsp+68h+var_38], ebx
0x140113564  lea     r8d, [rax+14h]
0x140113568  mov     dword ptr [rsp+68h+var_40], ebp
0x14011356c  mov     dl, 2
0x14011356e  mov     [rsp+68h+var_48], r15
0x140113573  call    WPP_RECORDER_SF_ld
0x140113578  jmp     short loc_1401135DE
0x14011357a  mov     r8b, 2; SubAuthorityCount
0x14011357d  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x140113582  mov     rcx, rdi; Sid
0x140113585  call    cs:__imp_RtlInitializeSid
0x14011358c  nop     dword ptr [rax+rax+00h]
0x140113591  mov     ebx, eax
0x140113593  mov     rcx, rdi; P
0x140113596  test    eax, eax
0x140113598  js      short loc_1401135CD
0x14011359a  xor     edx, edx; SubAuthority
0x14011359c  call    cs:__imp_RtlSubAuthoritySid
0x1401135a3  nop     dword ptr [rax+rax+00h]
0x1401135a8  mov     edx, 1; SubAuthority
0x1401135ad  mov     rcx, rdi; Sid
0x1401135b0  mov     dword ptr [rax], 53h ; 'S'
0x1401135b6  call    cs:__imp_RtlSubAuthoritySid
0x1401135bd  nop     dword ptr [rax+rax+00h]
0x1401135c2  mov     dword ptr [rax], 0
0x1401135c8  mov     [rsi], rdi
0x1401135cb  jmp     short loc_140113604
0x1401135cd  mov     edx, 624F7356h; Tag
0x1401135d2  call    cs:__imp_ExFreePoolWithTag
0x1401135d9  nop     dword ptr [rax+rax+00h]
0x1401135de  mov     rcx, cs:VmsIfrLog
0x1401135e5  mov     r9d, 11h
0x1401135eb  mov     [rsp+68h+var_38], ebx
0x1401135ef  mov     dl, 2
0x1401135f1  mov     [rsp+68h+var_40], rsi
0x1401135f6  mov     [rsp+68h+var_48], r15
0x1401135fb  lea     r8d, [r9+3]
0x1401135ff  call    WPP_RECORDER_SF_id
0x140113604  mov     eax, ebx
0x140113606  mov     rcx, [rsp+68h+var_20]
0x14011360b  xor     rcx, rsp; StackCookie
0x14011360e  call    __security_check_cookie
0x140113613  lea     r11, [rsp+68h+var_18]
0x140113618  mov     rbx, [r11+28h]
0x14011361c  mov     rbp, [r11+30h]
0x140113620  mov     rsp, r11
0x140113623  pop     r15
0x140113625  pop     rdi
0x140113626  pop     rsi
0x140113627  retn
```
