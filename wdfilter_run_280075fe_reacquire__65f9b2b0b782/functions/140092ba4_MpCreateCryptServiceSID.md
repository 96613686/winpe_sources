# MpCreateCryptServiceSID

- ea: `0x140092ba4`
- end: `0x140092d8e`
- name: `MpCreateCryptServiceSID`
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
- `0x140092ba4`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x140092c68`
- `ntoskrnl!RtlInitializeSid` at `0x140092c68`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092cd5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092cef`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092d09`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092d23`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092d3d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092d57`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092cd5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092cef`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092d09`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092d23`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092d3d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092d57`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140092be0`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140092be0`

## pseudocode

```c
__int64 __fastcall MpCreateCryptServiceSID(_QWORD *a1)
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
      *RtlSubAuthoritySid(v4, 1u) = 242729624;
      *RtlSubAuthoritySid(v4, 2u) = 280608522;
      *RtlSubAuthoritySid(v4, 3u) = -2075914409;
      *RtlSubAuthoritySid(v4, 4u) = -1107558236;
      v5 = 0;
      *RtlSubAuthoritySid(v4, 5u) = -2069023837;
      *a1 = v4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
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
        31,
        WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
        KeGetCurrentThread(),
        -1073741670);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140092ba4  mov     [rsp+arg_8], rbx
0x140092ba9  mov     [rsp+arg_10], rsi
0x140092bae  push    rdi
0x140092baf  sub     rsp, 40h
0x140092bb3  mov     rax, cs:__security_cookie
0x140092bba  xor     rax, rsp
0x140092bbd  mov     [rsp+48h+var_10], rax
0x140092bc2  mov     rsi, rcx
0x140092bc5  mov     qword ptr [rcx], 0
0x140092bcc  mov     ecx, 6; SubAuthorityCount
0x140092bd1  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], 0
0x140092bd9  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x140092be0  call    cs:__imp_RtlLengthRequiredSid
0x140092be7  nop     dword ptr [rax+rax+00h]
0x140092bec  mov     edx, eax
0x140092bee  mov     ecx, 1
0x140092bf3  mov     r8d, 6473504Dh
0x140092bf9  call    MpAllocatePoolWithTag
0x140092bfe  mov     rdi, rax
0x140092c01  test    rax, rax
0x140092c04  jnz     short loc_140092C5D
0x140092c06  mov     ebx, 0C000009Ah
0x140092c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140092c12  lea     rax, WPP_GLOBAL_Control
0x140092c19  cmp     rcx, rax
0x140092c1c  jz      loc_140092D6E
0x140092c22  mov     eax, [rcx+2Ch]
0x140092c25  test    al, 1
0x140092c27  jz      loc_140092D6E
0x140092c2d  mov     r9, gs:188h
0x140092c36  lea     edx, [rdi+1Fh]
0x140092c39  mov     rcx, cs:WPP_GLOBAL_Control
0x140092c40  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140092c47  mov     [rsp+48h+var_28], 0C000009Ah
0x140092c4f  mov     rcx, [rcx+18h]
0x140092c53  call    WPP_SF_qD
0x140092c58  jmp     loc_140092D6E
0x140092c5d  mov     r8b, 6; SubAuthorityCount
0x140092c60  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x140092c65  mov     rcx, rdi; Sid
0x140092c68  call    cs:__imp_RtlInitializeSid
0x140092c6f  nop     dword ptr [rax+rax+00h]
0x140092c74  mov     ebx, eax
0x140092c76  test    eax, eax
0x140092c78  jns     short loc_140092CCD
0x140092c7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140092c81  lea     rax, WPP_GLOBAL_Control
0x140092c88  cmp     rcx, rax
0x140092c8b  jz      short loc_140092CC0
0x140092c8d  mov     eax, [rcx+2Ch]
0x140092c90  test    al, 1
0x140092c92  jz      short loc_140092CC0
0x140092c94  lfence
0x140092c97  mov     r9, gs:188h
0x140092ca0  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140092ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x140092cae  mov     edx, 20h ; ' '
0x140092cb3  mov     [rsp+48h+var_28], ebx
0x140092cb7  mov     rcx, [rcx+18h]
0x140092cbb  call    WPP_SF_qD
0x140092cc0  mov     rcx, rdi
0x140092cc3  call    MpFreeServiceSID
0x140092cc8  jmp     loc_140092D6E
0x140092ccd  lfence
0x140092cd0  xor     edx, edx; SubAuthority
0x140092cd2  mov     rcx, rdi; Sid
0x140092cd5  call    cs:__imp_RtlSubAuthoritySid
0x140092cdc  nop     dword ptr [rax+rax+00h]
0x140092ce1  mov     edx, 1; SubAuthority
0x140092ce6  mov     rcx, rdi; Sid
0x140092ce9  mov     dword ptr [rax], 50h ; 'P'
0x140092cef  call    cs:__imp_RtlSubAuthoritySid
0x140092cf6  nop     dword ptr [rax+rax+00h]
0x140092cfb  mov     edx, 2; SubAuthority
0x140092d00  mov     rcx, rdi; Sid
0x140092d03  mov     dword ptr [rax], 0E77C298h
0x140092d09  call    cs:__imp_RtlSubAuthoritySid
0x140092d10  nop     dword ptr [rax+rax+00h]
0x140092d15  mov     edx, 3; SubAuthority
0x140092d1a  mov     rcx, rdi; Sid
0x140092d1d  mov     dword ptr [rax], 10B9BF0Ah
0x140092d23  call    cs:__imp_RtlSubAuthoritySid
0x140092d2a  nop     dword ptr [rax+rax+00h]
0x140092d2f  mov     edx, 4; SubAuthority
0x140092d34  mov     rcx, rdi; Sid
0x140092d37  mov     dword ptr [rax], 84440F57h
0x140092d3d  call    cs:__imp_RtlSubAuthoritySid
0x140092d44  nop     dword ptr [rax+rax+00h]
0x140092d49  mov     edx, 5; SubAuthority
0x140092d4e  mov     rcx, rdi; Sid
0x140092d51  mov     dword ptr [rax], 0BDFC00A4h
0x140092d57  call    cs:__imp_RtlSubAuthoritySid
0x140092d5e  nop     dword ptr [rax+rax+00h]
0x140092d63  xor     ebx, ebx
0x140092d65  mov     dword ptr [rax], 84AD33A3h
0x140092d6b  mov     [rsi], rdi
0x140092d6e  mov     eax, ebx
0x140092d70  mov     rcx, [rsp+48h+var_10]
0x140092d75  xor     rcx, rsp; StackCookie
0x140092d78  call    __security_check_cookie
0x140092d7d  mov     rbx, [rsp+48h+arg_8]
0x140092d82  mov     rsi, [rsp+48h+arg_10]
0x140092d87  add     rsp, 40h
0x140092d8b  pop     rdi
0x140092d8c  retn
```
