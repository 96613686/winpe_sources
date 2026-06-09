# VhdmpiGetVmGroupSid(void * *)

- ea: `0x140046cf4`
- end: `0x140046de1`
- name: `?VhdmpiGetVmGroupSid@@YAJPEAPEAX@Z`
- size: `237`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400cc9b0`

## callees

- `0x140046cf4`
- `0x14005d7c0`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x140046d29`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140046d29`
- `ntoskrnl!RtlInitializeSid` at `0x140046d68`
- `ntoskrnl!RtlInitializeSid` at `0x140046d68`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140046d7f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140046d99`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140046d7f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140046d99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046db5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046db5`
- `ntoskrnl!ExAllocatePool2` at `0x140046d42`
- `ntoskrnl!ExAllocatePool2` at `0x140046d42`

## pseudocode

```c
__int64 __fastcall VhdmpiGetVmGroupSid(void **a1)
{
  ULONG v2; // eax
  void *Pool2; // rax
  void *v4; // rdi
  NTSTATUS v5; // ebx
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-18h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v2 = RtlLengthRequiredSid(2u);
  Pool2 = (void *)ExAllocatePool2(256, v2, 1631864918);
  v4 = Pool2;
  if ( Pool2 )
  {
    v5 = RtlInitializeSid(Pool2, &IdentifierAuthority, 2u);
    if ( v5 < 0 )
    {
      ExFreePoolWithTag(v4, 0x61444856u);
    }
    else
    {
      *RtlSubAuthoritySid(v4, 0) = 83;
      *RtlSubAuthoritySid(v4, 1u) = 0;
      *a1 = v4;
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140046cf4  mov     [rsp+arg_8], rbx
0x140046cf9  mov     [rsp+arg_10], rsi
0x140046cfe  push    rdi
0x140046cff  sub     rsp, 30h
0x140046d03  mov     rax, cs:__security_cookie
0x140046d0a  xor     rax, rsp
0x140046d0d  mov     [rsp+38h+var_10], rax
0x140046d12  mov     rsi, rcx
0x140046d15  mov     dword ptr [rsp+38h+IdentifierAuthority.Value], 0
0x140046d1d  mov     ecx, 2; SubAuthorityCount
0x140046d22  mov     word ptr [rsp+38h+IdentifierAuthority.Value+4], 500h
0x140046d29  call    cs:__imp_RtlLengthRequiredSid
0x140046d30  nop     dword ptr [rax+rax+00h]
0x140046d35  mov     edx, eax
0x140046d37  mov     ecx, 100h
0x140046d3c  mov     r8d, 61444856h
0x140046d42  call    cs:__imp_ExAllocatePool2
0x140046d49  nop     dword ptr [rax+rax+00h]
0x140046d4e  mov     rdi, rax
0x140046d51  test    rax, rax
0x140046d54  jnz     short loc_140046D5D
0x140046d56  mov     ebx, 0C000009Ah
0x140046d5b  jmp     short loc_140046DC1
0x140046d5d  mov     r8b, 2; SubAuthorityCount
0x140046d60  lea     rdx, [rsp+38h+IdentifierAuthority]; IdentifierAuthority
0x140046d65  mov     rcx, rdi; Sid
0x140046d68  call    cs:__imp_RtlInitializeSid
0x140046d6f  nop     dword ptr [rax+rax+00h]
0x140046d74  mov     ebx, eax
0x140046d76  mov     rcx, rdi; P
0x140046d79  test    eax, eax
0x140046d7b  js      short loc_140046DB0
0x140046d7d  xor     edx, edx; SubAuthority
0x140046d7f  call    cs:__imp_RtlSubAuthoritySid
0x140046d86  nop     dword ptr [rax+rax+00h]
0x140046d8b  mov     edx, 1; SubAuthority
0x140046d90  mov     rcx, rdi; Sid
0x140046d93  mov     dword ptr [rax], 53h ; 'S'
0x140046d99  call    cs:__imp_RtlSubAuthoritySid
0x140046da0  nop     dword ptr [rax+rax+00h]
0x140046da5  mov     dword ptr [rax], 0
0x140046dab  mov     [rsi], rdi
0x140046dae  jmp     short loc_140046DC1
0x140046db0  mov     edx, 61444856h; Tag
0x140046db5  call    cs:__imp_ExFreePoolWithTag
0x140046dbc  nop     dword ptr [rax+rax+00h]
0x140046dc1  mov     eax, ebx
0x140046dc3  mov     rcx, [rsp+38h+var_10]
0x140046dc8  xor     rcx, rsp; StackCookie
0x140046dcb  call    __security_check_cookie
0x140046dd0  mov     rbx, [rsp+38h+arg_8]
0x140046dd5  mov     rsi, [rsp+38h+arg_10]
0x140046dda  add     rsp, 30h
0x140046dde  pop     rdi
0x140046ddf  retn
```
