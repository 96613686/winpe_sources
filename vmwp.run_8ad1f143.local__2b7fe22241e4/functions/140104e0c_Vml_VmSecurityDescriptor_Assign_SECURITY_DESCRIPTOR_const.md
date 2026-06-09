# Vml::VmSecurityDescriptor::Assign(_SECURITY_DESCRIPTOR const *)

- ea: `0x140104e0c`
- end: `0x140104f6c`
- name: `?Assign@VmSecurityDescriptor@Vml@@QEAAXPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `352`
- prototype: `void(Vml::VmSecurityDescriptor *__hidden this, const struct _SECURITY_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140104da0`
- `0x140294728`

## callees

- `0x14005b648`
- `0x14009d7cc`
- `0x140104e0c`
- `0x140132960`
- `0x140135955`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140104f0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140104f0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140104e71`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140104e71`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x140104eb9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x140104eb9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140104e33`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140104e33`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140104f45`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140104f45`

## string_xrefs

- `0x140104e53`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140104e8f`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140104ece`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140104f5a`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Vml::VmSecurityDescriptor::Assign(void **this, struct _SECURITY_DESCRIPTOR *a2)
{
  DWORD SecurityDescriptorLength; // eax
  HLOCAL v5; // rbx
  const char *v6; // r9
  const char *v7; // r9
  void *v8; // rcx
  const char *v9; // r9
  unsigned int v10; // [rsp+20h] [rbp-38h]
  DWORD Size; // [rsp+30h] [rbp-28h] BYREF
  __int16 Size_4; // [rsp+34h] [rbp-24h] BYREF
  DWORD dwRevision; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  SecurityDescriptorLength = GetSecurityDescriptorLength(a2);
  Size = SecurityDescriptorLength;
  if ( SecurityDescriptorLength < 0x28 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x191D,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      (const char *)0x57,
      v10);
  v5 = LocalAlloc(0, SecurityDescriptorLength);
  if ( !v5 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1927,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v6);
  Size_4 = 0;
  dwRevision = 0;
  if ( !GetSecurityDescriptorControl(a2, (PSECURITY_DESCRIPTOR_CONTROL)&Size_4, &dwRevision) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1933,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v7);
  if ( Size_4 >= 0 )
  {
    if ( !MakeSelfRelativeSD(a2, v5, &Size) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x193E,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v9);
  }
  else
  {
    memcpy_0(v5, a2, Size);
  }
  v8 = *this;
  *this = v5;
  if ( v8 )
    LocalFree(v8);
}

```

## disassembly

```asm
0x140104e0c  mov     [rsp+arg_10], rbx
0x140104e11  mov     [rsp+arg_18], rsi
0x140104e16  push    rdi
0x140104e17  sub     rsp, 50h
0x140104e1b  mov     rax, cs:__security_cookie
0x140104e22  xor     rax, rsp
0x140104e25  mov     [rsp+58h+var_18], rax
0x140104e2a  mov     rdi, rdx
0x140104e2d  mov     rsi, rcx
0x140104e30  mov     rcx, rdx; pSecurityDescriptor
0x140104e33  call    cs:__imp_GetSecurityDescriptorLength
0x140104e3a  nop     dword ptr [rax+rax+00h]
0x140104e3f  mov     dword ptr [rsp+58h+Size], eax
0x140104e43  cmp     eax, 28h ; '('
0x140104e46  jnb     short loc_140104E65
0x140104e48  mov     rcx, [rsp+58h]; this
0x140104e4d  mov     r9d, 57h ; 'W'; char *
0x140104e53  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140104e5a  mov     edx, 191Dh; void *
0x140104e5f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140104e65  xorps   xmm0, xmm0
0x140104e68  movups  [rsp+58h+var_38], xmm0
0x140104e6d  mov     edx, eax; uBytes
0x140104e6f  xor     ecx, ecx; uFlags
0x140104e71  call    cs:__imp_LocalAlloc
0x140104e78  nop     dword ptr [rax+rax+00h]
0x140104e7d  mov     rbx, rax
0x140104e80  mov     qword ptr [rsp+58h+var_38], rax
0x140104e85  test    rax, rax
0x140104e88  jnz     short loc_140104EA1
0x140104e8a  mov     rcx, [rsp+58h]; this
0x140104e8f  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140104e96  mov     edx, 1927h; void *
0x140104e9b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140104ea1  xor     eax, eax
0x140104ea3  mov     word ptr [rsp+58h+Size+4], ax
0x140104ea8  mov     [rsp+58h+dwRevision], eax
0x140104eac  lea     r8, [rsp+58h+dwRevision]; lpdwRevision
0x140104eb1  lea     rdx, [rsp+58h+Size+4]; pControl
0x140104eb6  mov     rcx, rdi; pSecurityDescriptor
0x140104eb9  call    cs:__imp_GetSecurityDescriptorControl
0x140104ec0  nop     dword ptr [rax+rax+00h]
0x140104ec5  mov     rcx, [rsp+58h]; this
0x140104eca  test    eax, eax
0x140104ecc  jnz     short loc_140104EE0
0x140104ece  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140104ed5  mov     edx, 1933h; void *
0x140104eda  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140104ee0  movzx   ecx, word ptr [rsp+58h+Size+4]
0x140104ee5  mov     eax, 8000h
0x140104eea  and     cx, ax
0x140104eed  xor     eax, eax
0x140104eef  cmp     ax, cx
0x140104ef2  jz      short loc_140104F3A
0x140104ef4  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x140104ef9  mov     rdx, rdi; Src
0x140104efc  mov     rcx, rbx; void *
0x140104eff  call    memcpy_0
0x140104f04  mov     rcx, [rsi]; hMem
0x140104f07  mov     [rsi], rbx
0x140104f0a  test    rcx, rcx
0x140104f0d  jz      short loc_140104F1C
0x140104f0f  call    cs:__imp_LocalFree
0x140104f16  nop     dword ptr [rax+rax+00h]
0x140104f1b  nop
0x140104f1c  mov     rcx, [rsp+58h+var_18]
0x140104f21  xor     rcx, rsp; StackCookie
0x140104f24  call    __security_check_cookie
0x140104f29  mov     rbx, [rsp+58h+arg_10]
0x140104f2e  mov     rsi, [rsp+58h+arg_18]
0x140104f33  add     rsp, 50h
0x140104f37  pop     rdi
0x140104f38  retn
0x140104f3a  lea     r8, [rsp+58h+Size]; lpdwBufferLength
0x140104f3f  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x140104f42  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x140104f45  call    cs:__imp_MakeSelfRelativeSD
0x140104f4c  nop     dword ptr [rax+rax+00h]
0x140104f51  mov     rcx, [rsp+58h]; this
0x140104f56  test    eax, eax
0x140104f58  jnz     short loc_140104F04
0x140104f5a  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140104f61  mov     edx, 193Eh; void *
0x140104f66  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
