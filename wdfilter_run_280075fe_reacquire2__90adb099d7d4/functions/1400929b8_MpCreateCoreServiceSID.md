# MpCreateCoreServiceSID

- ea: `0x1400929b8`
- end: `0x140092ba2`
- name: `MpCreateCoreServiceSID`
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
- `0x1400929b8`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x140092a7c`
- `ntoskrnl!RtlInitializeSid` at `0x140092a7c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092ae9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092b03`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092b1d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092b37`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092b51`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092b6b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092ae9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092b03`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092b1d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092b37`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092b51`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092b6b`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400929f4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400929f4`

## pseudocode

```c
__int64 __fastcall MpCreateCoreServiceSID(_QWORD *a1)
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
      *RtlSubAuthoritySid(v4, 1u) = 30551196;
      *RtlSubAuthoritySid(v4, 2u) = 2029750602;
      *RtlSubAuthoritySid(v4, 3u) = -614613349;
      *RtlSubAuthoritySid(v4, 4u) = -1958107533;
      v5 = 0;
      *RtlSubAuthoritySid(v4, 5u) = 523537544;
      *a1 = v4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          30,
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
        29,
        WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
        KeGetCurrentThread(),
        -1073741670);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400929b8  mov     [rsp+arg_8], rbx
0x1400929bd  mov     [rsp+arg_10], rsi
0x1400929c2  push    rdi
0x1400929c3  sub     rsp, 40h
0x1400929c7  mov     rax, cs:__security_cookie
0x1400929ce  xor     rax, rsp
0x1400929d1  mov     [rsp+48h+var_10], rax
0x1400929d6  mov     rsi, rcx
0x1400929d9  mov     qword ptr [rcx], 0
0x1400929e0  mov     ecx, 6; SubAuthorityCount
0x1400929e5  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], 0
0x1400929ed  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x1400929f4  call    cs:__imp_RtlLengthRequiredSid
0x1400929fb  nop     dword ptr [rax+rax+00h]
0x140092a00  mov     edx, eax
0x140092a02  mov     ecx, 1
0x140092a07  mov     r8d, 6473504Dh
0x140092a0d  call    MpAllocatePoolWithTag
0x140092a12  mov     rdi, rax
0x140092a15  test    rax, rax
0x140092a18  jnz     short loc_140092A71
0x140092a1a  mov     ebx, 0C000009Ah
0x140092a1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140092a26  lea     rax, WPP_GLOBAL_Control
0x140092a2d  cmp     rcx, rax
0x140092a30  jz      loc_140092B82
0x140092a36  mov     eax, [rcx+2Ch]
0x140092a39  test    al, 1
0x140092a3b  jz      loc_140092B82
0x140092a41  mov     r9, gs:188h
0x140092a4a  lea     edx, [rdi+1Dh]
0x140092a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140092a54  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140092a5b  mov     [rsp+48h+var_28], 0C000009Ah
0x140092a63  mov     rcx, [rcx+18h]
0x140092a67  call    WPP_SF_qD
0x140092a6c  jmp     loc_140092B82
0x140092a71  mov     r8b, 6; SubAuthorityCount
0x140092a74  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x140092a79  mov     rcx, rdi; Sid
0x140092a7c  call    cs:__imp_RtlInitializeSid
0x140092a83  nop     dword ptr [rax+rax+00h]
0x140092a88  mov     ebx, eax
0x140092a8a  test    eax, eax
0x140092a8c  jns     short loc_140092AE1
0x140092a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140092a95  lea     rax, WPP_GLOBAL_Control
0x140092a9c  cmp     rcx, rax
0x140092a9f  jz      short loc_140092AD4
0x140092aa1  mov     eax, [rcx+2Ch]
0x140092aa4  test    al, 1
0x140092aa6  jz      short loc_140092AD4
0x140092aa8  lfence
0x140092aab  mov     r9, gs:188h
0x140092ab4  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140092abb  mov     rcx, cs:WPP_GLOBAL_Control
0x140092ac2  mov     edx, 1Eh
0x140092ac7  mov     [rsp+48h+var_28], ebx
0x140092acb  mov     rcx, [rcx+18h]
0x140092acf  call    WPP_SF_qD
0x140092ad4  mov     rcx, rdi
0x140092ad7  call    MpFreeServiceSID
0x140092adc  jmp     loc_140092B82
0x140092ae1  lfence
0x140092ae4  xor     edx, edx; SubAuthority
0x140092ae6  mov     rcx, rdi; Sid
0x140092ae9  call    cs:__imp_RtlSubAuthoritySid
0x140092af0  nop     dword ptr [rax+rax+00h]
0x140092af5  mov     edx, 1; SubAuthority
0x140092afa  mov     rcx, rdi; Sid
0x140092afd  mov     dword ptr [rax], 50h ; 'P'
0x140092b03  call    cs:__imp_RtlSubAuthoritySid
0x140092b0a  nop     dword ptr [rax+rax+00h]
0x140092b0f  mov     edx, 2; SubAuthority
0x140092b14  mov     rcx, rdi; Sid
0x140092b17  mov     dword ptr [rax], 1D22C9Ch
0x140092b1d  call    cs:__imp_RtlSubAuthoritySid
0x140092b24  nop     dword ptr [rax+rax+00h]
0x140092b29  mov     edx, 3; SubAuthority
0x140092b2e  mov     rcx, rdi; Sid
0x140092b31  mov     dword ptr [rax], 78FB894Ah
0x140092b37  call    cs:__imp_RtlSubAuthoritySid
0x140092b3e  nop     dword ptr [rax+rax+00h]
0x140092b43  mov     edx, 4; SubAuthority
0x140092b48  mov     rcx, rdi; Sid
0x140092b4b  mov     dword ptr [rax], 0DB5DBE9Bh
0x140092b51  call    cs:__imp_RtlSubAuthoritySid
0x140092b58  nop     dword ptr [rax+rax+00h]
0x140092b5d  mov     edx, 5; SubAuthority
0x140092b62  mov     rcx, rdi; Sid
0x140092b65  mov     dword ptr [rax], 8B49A673h
0x140092b6b  call    cs:__imp_RtlSubAuthoritySid
0x140092b72  nop     dword ptr [rax+rax+00h]
0x140092b77  xor     ebx, ebx
0x140092b79  mov     dword ptr [rax], 1F348C88h
0x140092b7f  mov     [rsi], rdi
0x140092b82  mov     eax, ebx
0x140092b84  mov     rcx, [rsp+48h+var_10]
0x140092b89  xor     rcx, rsp; StackCookie
0x140092b8c  call    __security_check_cookie
0x140092b91  mov     rbx, [rsp+48h+arg_8]
0x140092b96  mov     rsi, [rsp+48h+arg_10]
0x140092b9b  add     rsp, 40h
0x140092b9f  pop     rdi
0x140092ba0  retn
```
