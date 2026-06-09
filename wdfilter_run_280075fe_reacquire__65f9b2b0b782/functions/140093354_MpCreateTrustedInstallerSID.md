# MpCreateTrustedInstallerSID

- ea: `0x140093354`
- end: `0x14009353e`
- name: `MpCreateTrustedInstallerSID`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x1400907b8`

## callees

- `0x1400026c0`
- `0x1400051bc`
- `0x1400118d0`
- `0x140080070`
- `0x140093354`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x140093418`
- `ntoskrnl!RtlInitializeSid` at `0x140093418`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140093485`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14009349f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400934b9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400934d3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400934ed`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140093507`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140093485`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14009349f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400934b9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400934d3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400934ed`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140093507`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140093390`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140093390`

## pseudocode

```c
__int64 __fastcall MpCreateTrustedInstallerSID(_QWORD *a1)
{
  ULONG v2; // eax
  void *PoolWithTag; // rax
  void *v4; // rdi
  NTSTATUS v5; // ebx
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+30h] [rbp-18h] BYREF

  *a1 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v2 = RtlLengthRequiredSid(6u);
  PoolWithTag = (void *)MpAllocatePoolWithTag(1, v2, 1685278797);
  v4 = PoolWithTag;
  if ( PoolWithTag )
  {
    v5 = RtlInitializeSid(PoolWithTag, &IdentifierAuthority, 6u);
    if ( v5 >= 0 )
    {
      _mm_lfence();
      *RtlSubAuthoritySid(v4, 0) = 80;
      *RtlSubAuthoritySid(v4, 1u) = 956008885;
      *RtlSubAuthoritySid(v4, 2u) = -876444647;
      *RtlSubAuthoritySid(v4, 3u) = 1831038044;
      *RtlSubAuthoritySid(v4, 4u) = 1853292631;
      v5 = 0;
      *RtlSubAuthoritySid(v4, 5u) = -2023488832;
      *a1 = v4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          28,
          WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
          KeGetCurrentThread(),
          v5);
      }
      MpFreeServiceSID(v4);
    }
  }
  else
  {
    v5 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
        KeGetCurrentThread(),
        -1073741670);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140093354  mov     [rsp+arg_8], rbx
0x140093359  mov     [rsp+arg_10], rsi
0x14009335e  push    rdi
0x14009335f  sub     rsp, 40h
0x140093363  mov     rax, cs:__security_cookie
0x14009336a  xor     rax, rsp
0x14009336d  mov     [rsp+48h+var_10], rax
0x140093372  mov     rsi, rcx
0x140093375  mov     qword ptr [rcx], 0
0x14009337c  mov     ecx, 6; SubAuthorityCount
0x140093381  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], 0
0x140093389  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x140093390  call    cs:__imp_RtlLengthRequiredSid
0x140093397  nop     dword ptr [rax+rax+00h]
0x14009339c  mov     edx, eax
0x14009339e  mov     ecx, 1
0x1400933a3  mov     r8d, 6473504Dh
0x1400933a9  call    MpAllocatePoolWithTag
0x1400933ae  mov     rdi, rax
0x1400933b1  test    rax, rax
0x1400933b4  jnz     short loc_14009340D
0x1400933b6  mov     ebx, 0C000009Ah
0x1400933bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400933c2  lea     rax, WPP_GLOBAL_Control
0x1400933c9  cmp     rcx, rax
0x1400933cc  jz      loc_14009351E
0x1400933d2  mov     eax, [rcx+2Ch]
0x1400933d5  test    al, 1
0x1400933d7  jz      loc_14009351E
0x1400933dd  mov     r9, gs:188h
0x1400933e6  lea     edx, [rdi+1Bh]
0x1400933e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400933f0  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x1400933f7  mov     [rsp+48h+var_28], 0C000009Ah
0x1400933ff  mov     rcx, [rcx+18h]
0x140093403  call    WPP_SF_qD
0x140093408  jmp     loc_14009351E
0x14009340d  mov     r8b, 6; SubAuthorityCount
0x140093410  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x140093415  mov     rcx, rdi; Sid
0x140093418  call    cs:__imp_RtlInitializeSid
0x14009341f  nop     dword ptr [rax+rax+00h]
0x140093424  mov     ebx, eax
0x140093426  test    eax, eax
0x140093428  jns     short loc_14009347D
0x14009342a  mov     rcx, cs:WPP_GLOBAL_Control
0x140093431  lea     rax, WPP_GLOBAL_Control
0x140093438  cmp     rcx, rax
0x14009343b  jz      short loc_140093470
0x14009343d  mov     eax, [rcx+2Ch]
0x140093440  test    al, 1
0x140093442  jz      short loc_140093470
0x140093444  lfence
0x140093447  mov     r9, gs:188h
0x140093450  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140093457  mov     rcx, cs:WPP_GLOBAL_Control
0x14009345e  mov     edx, 1Ch
0x140093463  mov     [rsp+48h+var_28], ebx
0x140093467  mov     rcx, [rcx+18h]
0x14009346b  call    WPP_SF_qD
0x140093470  mov     rcx, rdi
0x140093473  call    MpFreeServiceSID
0x140093478  jmp     loc_14009351E
0x14009347d  lfence
0x140093480  xor     edx, edx; SubAuthority
0x140093482  mov     rcx, rdi; Sid
0x140093485  call    cs:__imp_RtlSubAuthoritySid
0x14009348c  nop     dword ptr [rax+rax+00h]
0x140093491  mov     edx, 1; SubAuthority
0x140093496  mov     rcx, rdi; Sid
0x140093499  mov     dword ptr [rax], 50h ; 'P'
0x14009349f  call    cs:__imp_RtlSubAuthoritySid
0x1400934a6  nop     dword ptr [rax+rax+00h]
0x1400934ab  mov     edx, 2; SubAuthority
0x1400934b0  mov     rcx, rdi; Sid
0x1400934b3  mov     dword ptr [rax], 38FB89B5h
0x1400934b9  call    cs:__imp_RtlSubAuthoritySid
0x1400934c0  nop     dword ptr [rax+rax+00h]
0x1400934c5  mov     edx, 3; SubAuthority
0x1400934ca  mov     rcx, rdi; Sid
0x1400934cd  mov     dword ptr [rax], 0CBC28419h
0x1400934d3  call    cs:__imp_RtlSubAuthoritySid
0x1400934da  nop     dword ptr [rax+rax+00h]
0x1400934df  mov     edx, 4; SubAuthority
0x1400934e4  mov     rcx, rdi; Sid
0x1400934e7  mov     dword ptr [rax], 6D236C5Ch
0x1400934ed  call    cs:__imp_RtlSubAuthoritySid
0x1400934f4  nop     dword ptr [rax+rax+00h]
0x1400934f9  mov     edx, 5; SubAuthority
0x1400934fe  mov     rcx, rdi; Sid
0x140093501  mov     dword ptr [rax], 6E770057h
0x140093507  call    cs:__imp_RtlSubAuthoritySid
0x14009350e  nop     dword ptr [rax+rax+00h]
0x140093513  xor     ebx, ebx
0x140093515  mov     dword ptr [rax], 876402C0h
0x14009351b  mov     [rsi], rdi
0x14009351e  mov     eax, ebx
0x140093520  mov     rcx, [rsp+48h+var_10]
0x140093525  xor     rcx, rsp; StackCookie
0x140093528  call    __security_check_cookie
0x14009352d  mov     rbx, [rsp+48h+arg_8]
0x140093532  mov     rsi, [rsp+48h+arg_10]
0x140093537  add     rsp, 40h
0x14009353b  pop     rdi
0x14009353c  retn
```
