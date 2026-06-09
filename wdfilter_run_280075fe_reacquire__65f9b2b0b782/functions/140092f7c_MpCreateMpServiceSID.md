# MpCreateMpServiceSID

- ea: `0x140092f7c`
- end: `0x140093166`
- name: `MpCreateMpServiceSID`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400907b8`

## callees

- `0x1400026c0`
- `0x1400051bc`
- `0x1400118d0`
- `0x140080070`
- `0x140092f7c`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x140093040`
- `ntoskrnl!RtlInitializeSid` at `0x140093040`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400930ad`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400930c7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400930e1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400930fb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140093115`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14009312f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400930ad`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400930c7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400930e1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400930fb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140093115`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14009312f`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140092fb8`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140092fb8`

## pseudocode

```c
__int64 __fastcall MpCreateMpServiceSID(_QWORD *a1)
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
      *RtlSubAuthoritySid(v4, 1u) = 1913148863;
      *RtlSubAuthoritySid(v4, 2u) = -802627525;
      *RtlSubAuthoritySid(v4, 3u) = -129271415;
      *RtlSubAuthoritySid(v4, 4u) = 2087618961;
      v5 = 0;
      *RtlSubAuthoritySid(v4, 5u) = -185850560;
      *a1 = v4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
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
        21,
        WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
        KeGetCurrentThread(),
        -1073741670);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140092f7c  mov     [rsp+arg_8], rbx
0x140092f81  mov     [rsp+arg_10], rsi
0x140092f86  push    rdi
0x140092f87  sub     rsp, 40h
0x140092f8b  mov     rax, cs:__security_cookie
0x140092f92  xor     rax, rsp
0x140092f95  mov     [rsp+48h+var_10], rax
0x140092f9a  mov     rsi, rcx
0x140092f9d  mov     qword ptr [rcx], 0
0x140092fa4  mov     ecx, 6; SubAuthorityCount
0x140092fa9  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], 0
0x140092fb1  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x140092fb8  call    cs:__imp_RtlLengthRequiredSid
0x140092fbf  nop     dword ptr [rax+rax+00h]
0x140092fc4  mov     edx, eax
0x140092fc6  mov     ecx, 1
0x140092fcb  mov     r8d, 6473504Dh
0x140092fd1  call    MpAllocatePoolWithTag
0x140092fd6  mov     rdi, rax
0x140092fd9  test    rax, rax
0x140092fdc  jnz     short loc_140093035
0x140092fde  mov     ebx, 0C000009Ah
0x140092fe3  mov     rcx, cs:WPP_GLOBAL_Control
0x140092fea  lea     rax, WPP_GLOBAL_Control
0x140092ff1  cmp     rcx, rax
0x140092ff4  jz      loc_140093146
0x140092ffa  mov     eax, [rcx+2Ch]
0x140092ffd  test    al, 1
0x140092fff  jz      loc_140093146
0x140093005  mov     r9, gs:188h
0x14009300e  lea     edx, [rdi+15h]
0x140093011  mov     rcx, cs:WPP_GLOBAL_Control
0x140093018  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x14009301f  mov     [rsp+48h+var_28], 0C000009Ah
0x140093027  mov     rcx, [rcx+18h]
0x14009302b  call    WPP_SF_qD
0x140093030  jmp     loc_140093146
0x140093035  mov     r8b, 6; SubAuthorityCount
0x140093038  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x14009303d  mov     rcx, rdi; Sid
0x140093040  call    cs:__imp_RtlInitializeSid
0x140093047  nop     dword ptr [rax+rax+00h]
0x14009304c  mov     ebx, eax
0x14009304e  test    eax, eax
0x140093050  jns     short loc_1400930A5
0x140093052  mov     rcx, cs:WPP_GLOBAL_Control
0x140093059  lea     rax, WPP_GLOBAL_Control
0x140093060  cmp     rcx, rax
0x140093063  jz      short loc_140093098
0x140093065  mov     eax, [rcx+2Ch]
0x140093068  test    al, 1
0x14009306a  jz      short loc_140093098
0x14009306c  lfence
0x14009306f  mov     r9, gs:188h
0x140093078  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x14009307f  mov     rcx, cs:WPP_GLOBAL_Control
0x140093086  mov     edx, 16h
0x14009308b  mov     [rsp+48h+var_28], ebx
0x14009308f  mov     rcx, [rcx+18h]
0x140093093  call    WPP_SF_qD
0x140093098  mov     rcx, rdi
0x14009309b  call    MpFreeServiceSID
0x1400930a0  jmp     loc_140093146
0x1400930a5  lfence
0x1400930a8  xor     edx, edx; SubAuthority
0x1400930aa  mov     rcx, rdi; Sid
0x1400930ad  call    cs:__imp_RtlSubAuthoritySid
0x1400930b4  nop     dword ptr [rax+rax+00h]
0x1400930b9  mov     edx, 1; SubAuthority
0x1400930be  mov     rcx, rdi; Sid
0x1400930c1  mov     dword ptr [rax], 50h ; 'P'
0x1400930c7  call    cs:__imp_RtlSubAuthoritySid
0x1400930ce  nop     dword ptr [rax+rax+00h]
0x1400930d3  mov     edx, 2; SubAuthority
0x1400930d8  mov     rcx, rdi; Sid
0x1400930db  mov     dword ptr [rax], 720855BFh
0x1400930e1  call    cs:__imp_RtlSubAuthoritySid
0x1400930e8  nop     dword ptr [rax+rax+00h]
0x1400930ed  mov     edx, 3; SubAuthority
0x1400930f2  mov     rcx, rdi; Sid
0x1400930f5  mov     dword ptr [rax], 0D028E03Bh
0x1400930fb  call    cs:__imp_RtlSubAuthoritySid
0x140093102  nop     dword ptr [rax+rax+00h]
0x140093107  mov     edx, 4; SubAuthority
0x14009310c  mov     rcx, rdi; Sid
0x14009310f  mov     dword ptr [rax], 0F84B7989h
0x140093115  call    cs:__imp_RtlSubAuthoritySid
0x14009311c  nop     dword ptr [rax+rax+00h]
0x140093121  mov     edx, 5; SubAuthority
0x140093126  mov     rcx, rdi; Sid
0x140093129  mov     dword ptr [rax], 7C6E8991h
0x14009312f  call    cs:__imp_RtlSubAuthoritySid
0x140093136  nop     dword ptr [rax+rax+00h]
0x14009313b  xor     ebx, ebx
0x14009313d  mov     dword ptr [rax], 0F4EC2540h
0x140093143  mov     [rsi], rdi
0x140093146  mov     eax, ebx
0x140093148  mov     rcx, [rsp+48h+var_10]
0x14009314d  xor     rcx, rsp; StackCookie
0x140093150  call    __security_check_cookie
0x140093155  mov     rbx, [rsp+48h+arg_8]
0x14009315a  mov     rsi, [rsp+48h+arg_10]
0x14009315f  add     rsp, 40h
0x140093163  pop     rdi
0x140093164  retn
```
