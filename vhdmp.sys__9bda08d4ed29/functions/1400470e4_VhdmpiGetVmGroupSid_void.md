# VhdmpiGetVmGroupSid(void * *)

- ea: `0x1400470e4`
- end: `0x1400471d1`
- name: `?VhdmpiGetVmGroupSid@@YAJPEAPEAX@Z`
- size: `237`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400cc9a0`

## callees

- `0x1400470e4`
- `0x14005dbb0`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x140047119`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140047119`
- `ntoskrnl!RtlInitializeSid` at `0x140047158`
- `ntoskrnl!RtlInitializeSid` at `0x140047158`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004716f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140047189`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004716f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140047189`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400471a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400471a5`
- `ntoskrnl!ExAllocatePool2` at `0x140047132`
- `ntoskrnl!ExAllocatePool2` at `0x140047132`

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
0x1400470e4  mov     [rsp+arg_8], rbx
0x1400470e9  mov     [rsp+arg_10], rsi
0x1400470ee  push    rdi
0x1400470ef  sub     rsp, 30h
0x1400470f3  mov     rax, cs:__security_cookie
0x1400470fa  xor     rax, rsp
0x1400470fd  mov     [rsp+38h+var_10], rax
0x140047102  mov     rsi, rcx
0x140047105  mov     dword ptr [rsp+38h+IdentifierAuthority.Value], 0
0x14004710d  mov     ecx, 2; SubAuthorityCount
0x140047112  mov     word ptr [rsp+38h+IdentifierAuthority.Value+4], 500h
0x140047119  call    cs:__imp_RtlLengthRequiredSid
0x140047120  nop     dword ptr [rax+rax+00h]
0x140047125  mov     edx, eax
0x140047127  mov     ecx, 100h
0x14004712c  mov     r8d, 61444856h
0x140047132  call    cs:__imp_ExAllocatePool2
0x140047139  nop     dword ptr [rax+rax+00h]
0x14004713e  mov     rdi, rax
0x140047141  test    rax, rax
0x140047144  jnz     short loc_14004714D
0x140047146  mov     ebx, 0C000009Ah
0x14004714b  jmp     short loc_1400471B1
0x14004714d  mov     r8b, 2; SubAuthorityCount
0x140047150  lea     rdx, [rsp+38h+IdentifierAuthority]; IdentifierAuthority
0x140047155  mov     rcx, rdi; Sid
0x140047158  call    cs:__imp_RtlInitializeSid
0x14004715f  nop     dword ptr [rax+rax+00h]
0x140047164  mov     ebx, eax
0x140047166  mov     rcx, rdi; P
0x140047169  test    eax, eax
0x14004716b  js      short loc_1400471A0
0x14004716d  xor     edx, edx; SubAuthority
0x14004716f  call    cs:__imp_RtlSubAuthoritySid
0x140047176  nop     dword ptr [rax+rax+00h]
0x14004717b  mov     edx, 1; SubAuthority
0x140047180  mov     rcx, rdi; Sid
0x140047183  mov     dword ptr [rax], 53h ; 'S'
0x140047189  call    cs:__imp_RtlSubAuthoritySid
0x140047190  nop     dword ptr [rax+rax+00h]
0x140047195  mov     dword ptr [rax], 0
0x14004719b  mov     [rsi], rdi
0x14004719e  jmp     short loc_1400471B1
0x1400471a0  mov     edx, 61444856h; Tag
0x1400471a5  call    cs:__imp_ExFreePoolWithTag
0x1400471ac  nop     dword ptr [rax+rax+00h]
0x1400471b1  mov     eax, ebx
0x1400471b3  mov     rcx, [rsp+38h+var_10]
0x1400471b8  xor     rcx, rsp; StackCookie
0x1400471bb  call    __security_check_cookie
0x1400471c0  mov     rbx, [rsp+38h+arg_8]
0x1400471c5  mov     rsi, [rsp+38h+arg_10]
0x1400471ca  add     rsp, 30h
0x1400471ce  pop     rdi
0x1400471cf  retn
```
