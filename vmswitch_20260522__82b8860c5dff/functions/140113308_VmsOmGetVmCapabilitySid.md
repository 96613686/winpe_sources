# VmsOmGetVmCapabilitySid

- ea: `0x140113308`
- end: `0x1401134ae`
- name: `VmsOmGetVmCapabilitySid`
- size: `422`
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
- `0x140113308`
- `0x1401bbc40`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x14011341f`
- `ntoskrnl!RtlInitializeSid` at `0x14011341f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140113438`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140113438`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1401133bc`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1401133bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011345e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011345e`
- `ntoskrnl!ExAllocatePool2` at `0x1401133d7`
- `ntoskrnl!ExAllocatePool2` at `0x1401133d7`

## string_xrefs

- `0x14011338d`: `VmCapabilitySid`

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
0x140113308  push    rbp
0x14011330a  push    rbx
0x14011330b  push    rsi
0x14011330c  push    rdi
0x14011330d  push    r12
0x14011330f  push    r14
0x140113311  lea     rbp, [rsp-2Fh]
0x140113316  sub     rsp, 88h
0x14011331d  mov     rax, cs:__security_cookie
0x140113324  xor     rax, rsp
0x140113327  mov     [rbp+57h+var_40], rax
0x14011332b  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], 0
0x140113332  mov     r14, rcx
0x140113335  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 0F00h
0x14011333b  lea     r12, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x140113342  mov     [rbp+57h+var_70], 3
0x140113349  mov     [rbp+57h+var_6C], 400h
0x140113350  mov     [rbp+57h+var_68], 873BADC0h
0x140113357  mov     [rbp+57h+var_64], 0DDCEA5EDh
0x14011335e  mov     [rbp+57h+var_60], 0E6C5A5Dh
0x140113365  mov     [rbp+57h+var_5C], 0A599D60h
0x14011336c  mov     [rbp+57h+var_58], 58DD02C8h
0x140113373  mov     [rbp+57h+var_54], 63CBB71h
0x14011337a  mov     [rbp+57h+var_50], 0ADCE083Ch
0x140113381  mov     [rbp+57h+var_4C], 601C32A0h
0x140113388  test    rcx, rcx
0x14011338b  jnz     short loc_1401133B7
0x14011338d  lea     rax, aVmcapabilitysi; "VmCapabilitySid"
0x140113394  lea     r9d, [rcx+12h]
0x140113398  mov     [rsp+0B0h+var_88], rax
0x14011339d  lea     r8d, [rcx+13h]
0x1401133a1  mov     [rsp+0B0h+var_90], r12
0x1401133a6  mov     rcx, cs:VmsIfrLog
0x1401133ad  call    WPP_RECORDER_SF_s
0x1401133b2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmCapabilitySid")
0x1401133b7  mov     ecx, 0Ah; SubAuthorityCount
0x1401133bc  call    cs:__imp_RtlLengthRequiredSid
0x1401133c3  nop     dword ptr [rax+rax+00h]
0x1401133c8  mov     edx, eax
0x1401133ca  mov     ecx, 100h
0x1401133cf  mov     r8d, 624F7356h
0x1401133d5  mov     ebx, eax
0x1401133d7  call    cs:__imp_ExAllocatePool2
0x1401133de  nop     dword ptr [rax+rax+00h]
0x1401133e3  mov     rsi, rax
0x1401133e6  test    rax, rax
0x1401133e9  jnz     short loc_140113415
0x1401133eb  mov     edi, 0C000009Ah
0x1401133f0  mov     rcx, cs:VmsIfrLog
0x1401133f7  lea     r9d, [rax+13h]
0x1401133fb  mov     [rsp+0B0h+var_80], edi
0x1401133ff  lea     r8d, [rax+14h]
0x140113403  mov     dword ptr [rsp+0B0h+var_88], ebx
0x140113407  mov     dl, 2
0x140113409  mov     [rsp+0B0h+var_90], r12
0x14011340e  call    WPP_RECORDER_SF_ld
0x140113413  jmp     short loc_14011346A
0x140113415  mov     r8b, 0Ah; SubAuthorityCount
0x140113418  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x14011341c  mov     rcx, rsi; Sid
0x14011341f  call    cs:__imp_RtlInitializeSid
0x140113426  nop     dword ptr [rax+rax+00h]
0x14011342b  mov     edi, eax
0x14011342d  test    eax, eax
0x14011342f  js      short loc_140113456
0x140113431  xor     ebx, ebx
0x140113433  mov     edx, ebx; SubAuthority
0x140113435  mov     rcx, rsi; Sid
0x140113438  call    cs:__imp_RtlSubAuthoritySid
0x14011343f  nop     dword ptr [rax+rax+00h]
0x140113444  mov     edx, [rbp+rbx*4+57h+var_70]
0x140113448  inc     ebx
0x14011344a  mov     [rax], edx
0x14011344c  cmp     ebx, 0Ah
0x14011344f  jl      short loc_140113433
0x140113451  mov     [r14], rsi
0x140113454  jmp     short loc_14011348F
0x140113456  mov     edx, 624F7356h; Tag
0x14011345b  mov     rcx, rsi; P
0x14011345e  call    cs:__imp_ExFreePoolWithTag
0x140113465  nop     dword ptr [rax+rax+00h]
0x14011346a  mov     rcx, cs:VmsIfrLog
0x140113471  mov     r8d, 14h
0x140113477  mov     [rsp+0B0h+var_80], edi
0x14011347b  mov     r9d, r8d
0x14011347e  mov     [rsp+0B0h+var_88], r14
0x140113483  mov     dl, 2
0x140113485  mov     [rsp+0B0h+var_90], r12
0x14011348a  call    WPP_RECORDER_SF_id
0x14011348f  mov     eax, edi
0x140113491  mov     rcx, [rbp+57h+var_40]
0x140113495  xor     rcx, rsp; StackCookie
0x140113498  call    __security_check_cookie
0x14011349d  add     rsp, 88h
0x1401134a4  pop     r14
0x1401134a6  pop     r12
0x1401134a8  pop     rdi
0x1401134a9  pop     rsi
0x1401134aa  pop     rbx
0x1401134ab  pop     rbp
0x1401134ac  retn
```
