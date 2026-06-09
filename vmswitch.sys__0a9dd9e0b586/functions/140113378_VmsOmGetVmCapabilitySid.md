# VmsOmGetVmCapabilitySid

- ea: `0x140113378`
- end: `0x14011351e`
- name: `VmsOmGetVmCapabilitySid`
- size: `422`
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
- `0x140113378`
- `0x1401bbcb0`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x14011348f`
- `ntoskrnl!RtlInitializeSid` at `0x14011348f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401134a8`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401134a8`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14011342c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14011342c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401134ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401134ce`
- `ntoskrnl!ExAllocatePool2` at `0x140113447`
- `ntoskrnl!ExAllocatePool2` at `0x140113447`

## string_xrefs

- `0x1401133fd`: `VmCapabilitySid`

## pseudocode

```c
__int64 __fastcall VmsOmGetVmCapabilitySid(_QWORD *a1, int a2)
{
  ULONG v3; // eax
  char v4; // bl
  void *Pool2; // rax
  int v6; // edx
  void *v7; // rsi
  NTSTATUS v8; // edi
  int v9; // edx
  __int64 v10; // rbx
  PULONG v11; // rax
  ULONG v12; // edx
  _DWORD v14[10]; // [rsp+40h] [rbp-19h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp+Fh] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  v14[0] = 3;
  v14[1] = 1024;
  v14[2] = -2026132032;
  v14[3] = -573659667;
  v14[4] = 241982045;
  v14[5] = 173645152;
  v14[6] = 1490879176;
  v14[7] = 104643441;
  v14[8] = -1379006404;
  v14[9] = 1612460704;
  if ( !a1 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      18,
      (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
      (__int64)"VmCapabilitySid");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v3 = RtlLengthRequiredSid(0xAu);
  v4 = v3;
  Pool2 = (void *)ExAllocatePool2(256, v3, 1649374038);
  v7 = Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741670;
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_ld(VmsIfrLog, v6, 20, 19, (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids, v4, 154);
LABEL_10:
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_id(VmsIfrLog, v9, 20, 20, (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids, (char)a1, v8);
    return (unsigned int)v8;
  }
  v8 = RtlInitializeSid(Pool2, &IdentifierAuthority, 0xAu);
  if ( v8 < 0 )
  {
    ExFreePoolWithTag(v7, 0x624F7356u);
    goto LABEL_10;
  }
  v10 = 0;
  do
  {
    v11 = RtlSubAuthoritySid(v7, v10);
    v12 = v14[v10];
    v10 = (unsigned int)(v10 + 1);
    *v11 = v12;
  }
  while ( (int)v10 < 10 );
  *a1 = v7;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140113378  push    rbp
0x14011337a  push    rbx
0x14011337b  push    rsi
0x14011337c  push    rdi
0x14011337d  push    r12
0x14011337f  push    r14
0x140113381  lea     rbp, [rsp-2Fh]
0x140113386  sub     rsp, 88h
0x14011338d  mov     rax, cs:__security_cookie
0x140113394  xor     rax, rsp
0x140113397  mov     [rbp+57h+var_40], rax
0x14011339b  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], 0
0x1401133a2  mov     r14, rcx
0x1401133a5  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 0F00h
0x1401133ab  lea     r12, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x1401133b2  mov     [rbp+57h+var_70], 3
0x1401133b9  mov     [rbp+57h+var_6C], 400h
0x1401133c0  mov     [rbp+57h+var_68], 873BADC0h
0x1401133c7  mov     [rbp+57h+var_64], 0DDCEA5EDh
0x1401133ce  mov     [rbp+57h+var_60], 0E6C5A5Dh
0x1401133d5  mov     [rbp+57h+var_5C], 0A599D60h
0x1401133dc  mov     [rbp+57h+var_58], 58DD02C8h
0x1401133e3  mov     [rbp+57h+var_54], 63CBB71h
0x1401133ea  mov     [rbp+57h+var_50], 0ADCE083Ch
0x1401133f1  mov     [rbp+57h+var_4C], 601C32A0h
0x1401133f8  test    rcx, rcx
0x1401133fb  jnz     short loc_140113427
0x1401133fd  lea     rax, aVmcapabilitysi; "VmCapabilitySid"
0x140113404  lea     r9d, [rcx+12h]
0x140113408  mov     [rsp+0B0h+var_88], rax
0x14011340d  lea     r8d, [rcx+13h]
0x140113411  mov     [rsp+0B0h+var_90], r12
0x140113416  mov     rcx, cs:VmsIfrLog
0x14011341d  call    WPP_RECORDER_SF_s
0x140113422  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmCapabilitySid")
0x140113427  mov     ecx, 0Ah; SubAuthorityCount
0x14011342c  call    cs:__imp_RtlLengthRequiredSid
0x140113433  nop     dword ptr [rax+rax+00h]
0x140113438  mov     edx, eax
0x14011343a  mov     ecx, 100h
0x14011343f  mov     r8d, 624F7356h
0x140113445  mov     ebx, eax
0x140113447  call    cs:__imp_ExAllocatePool2
0x14011344e  nop     dword ptr [rax+rax+00h]
0x140113453  mov     rsi, rax
0x140113456  test    rax, rax
0x140113459  jnz     short loc_140113485
0x14011345b  mov     edi, 0C000009Ah
0x140113460  mov     rcx, cs:VmsIfrLog
0x140113467  lea     r9d, [rax+13h]
0x14011346b  mov     [rsp+0B0h+var_80], edi
0x14011346f  lea     r8d, [rax+14h]
0x140113473  mov     dword ptr [rsp+0B0h+var_88], ebx
0x140113477  mov     dl, 2
0x140113479  mov     [rsp+0B0h+var_90], r12
0x14011347e  call    WPP_RECORDER_SF_ld
0x140113483  jmp     short loc_1401134DA
0x140113485  mov     r8b, 0Ah; SubAuthorityCount
0x140113488  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x14011348c  mov     rcx, rsi; Sid
0x14011348f  call    cs:__imp_RtlInitializeSid
0x140113496  nop     dword ptr [rax+rax+00h]
0x14011349b  mov     edi, eax
0x14011349d  test    eax, eax
0x14011349f  js      short loc_1401134C6
0x1401134a1  xor     ebx, ebx
0x1401134a3  mov     edx, ebx; SubAuthority
0x1401134a5  mov     rcx, rsi; Sid
0x1401134a8  call    cs:__imp_RtlSubAuthoritySid
0x1401134af  nop     dword ptr [rax+rax+00h]
0x1401134b4  mov     edx, [rbp+rbx*4+57h+var_70]
0x1401134b8  inc     ebx
0x1401134ba  mov     [rax], edx
0x1401134bc  cmp     ebx, 0Ah
0x1401134bf  jl      short loc_1401134A3
0x1401134c1  mov     [r14], rsi
0x1401134c4  jmp     short loc_1401134FF
0x1401134c6  mov     edx, 624F7356h; Tag
0x1401134cb  mov     rcx, rsi; P
0x1401134ce  call    cs:__imp_ExFreePoolWithTag
0x1401134d5  nop     dword ptr [rax+rax+00h]
0x1401134da  mov     rcx, cs:VmsIfrLog
0x1401134e1  mov     r8d, 14h
0x1401134e7  mov     [rsp+0B0h+var_80], edi
0x1401134eb  mov     r9d, r8d
0x1401134ee  mov     [rsp+0B0h+var_88], r14
0x1401134f3  mov     dl, 2
0x1401134f5  mov     [rsp+0B0h+var_90], r12
0x1401134fa  call    WPP_RECORDER_SF_id
0x1401134ff  mov     eax, edi
0x140113501  mov     rcx, [rbp+57h+var_40]
0x140113505  xor     rcx, rsp; StackCookie
0x140113508  call    __security_check_cookie
0x14011350d  add     rsp, 88h
0x140113514  pop     r14
0x140113516  pop     r12
0x140113518  pop     rdi
0x140113519  pop     rsi
0x14011351a  pop     rbx
0x14011351b  pop     rbp
0x14011351c  retn
```
