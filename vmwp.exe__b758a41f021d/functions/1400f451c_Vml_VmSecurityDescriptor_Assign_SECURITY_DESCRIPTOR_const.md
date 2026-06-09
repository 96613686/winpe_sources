# Vml::VmSecurityDescriptor::Assign(_SECURITY_DESCRIPTOR const *)

- ea: `0x1400f451c`
- end: `0x1400f467c`
- name: `?Assign@VmSecurityDescriptor@Vml@@QEAAXPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `352`
- prototype: `void(Vml::VmSecurityDescriptor *__hidden this, const struct _SECURITY_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400f44b0`
- `0x14029d138`

## callees

- `0x140083990`
- `0x1400ba144`
- `0x1400f451c`
- `0x14011ea40`
- `0x140121a35`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400f4581`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400f4581`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400f461f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400f461f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1400f45c9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1400f45c9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1400f4543`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1400f4543`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1400f4655`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1400f4655`

## string_xrefs

- `0x1400f4563`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400f459f`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400f45de`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400f466a`: `onecore\vm\common\vml\VmSecurity.h`

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
0x1400f451c  mov     [rsp+arg_10], rbx
0x1400f4521  mov     [rsp+arg_18], rsi
0x1400f4526  push    rdi
0x1400f4527  sub     rsp, 50h
0x1400f452b  mov     rax, cs:__security_cookie
0x1400f4532  xor     rax, rsp
0x1400f4535  mov     [rsp+58h+var_18], rax
0x1400f453a  mov     rdi, rdx
0x1400f453d  mov     rsi, rcx
0x1400f4540  mov     rcx, rdx; pSecurityDescriptor
0x1400f4543  call    cs:__imp_GetSecurityDescriptorLength
0x1400f454a  nop     dword ptr [rax+rax+00h]
0x1400f454f  mov     dword ptr [rsp+58h+Size], eax
0x1400f4553  cmp     eax, 28h ; '('
0x1400f4556  jnb     short loc_1400F4575
0x1400f4558  mov     rcx, [rsp+58h]; this
0x1400f455d  mov     r9d, 57h ; 'W'; char *
0x1400f4563  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400f456a  mov     edx, 191Dh; void *
0x1400f456f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400f4575  xorps   xmm0, xmm0
0x1400f4578  movups  [rsp+58h+var_38], xmm0
0x1400f457d  mov     edx, eax; uBytes
0x1400f457f  xor     ecx, ecx; uFlags
0x1400f4581  call    cs:__imp_LocalAlloc
0x1400f4588  nop     dword ptr [rax+rax+00h]
0x1400f458d  mov     rbx, rax
0x1400f4590  mov     qword ptr [rsp+58h+var_38], rax
0x1400f4595  test    rax, rax
0x1400f4598  jnz     short loc_1400F45B1
0x1400f459a  mov     rcx, [rsp+58h]; this
0x1400f459f  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400f45a6  mov     edx, 1927h; void *
0x1400f45ab  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400f45b1  xor     eax, eax
0x1400f45b3  mov     word ptr [rsp+58h+Size+4], ax
0x1400f45b8  mov     [rsp+58h+dwRevision], eax
0x1400f45bc  lea     r8, [rsp+58h+dwRevision]; lpdwRevision
0x1400f45c1  lea     rdx, [rsp+58h+Size+4]; pControl
0x1400f45c6  mov     rcx, rdi; pSecurityDescriptor
0x1400f45c9  call    cs:__imp_GetSecurityDescriptorControl
0x1400f45d0  nop     dword ptr [rax+rax+00h]
0x1400f45d5  mov     rcx, [rsp+58h]; this
0x1400f45da  test    eax, eax
0x1400f45dc  jnz     short loc_1400F45F0
0x1400f45de  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400f45e5  mov     edx, 1933h; void *
0x1400f45ea  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400f45f0  movzx   ecx, word ptr [rsp+58h+Size+4]
0x1400f45f5  mov     eax, 8000h
0x1400f45fa  and     cx, ax
0x1400f45fd  xor     eax, eax
0x1400f45ff  cmp     ax, cx
0x1400f4602  jz      short loc_1400F464A
0x1400f4604  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x1400f4609  mov     rdx, rdi; Src
0x1400f460c  mov     rcx, rbx; void *
0x1400f460f  call    memcpy_0
0x1400f4614  mov     rcx, [rsi]; hMem
0x1400f4617  mov     [rsi], rbx
0x1400f461a  test    rcx, rcx
0x1400f461d  jz      short loc_1400F462C
0x1400f461f  call    cs:__imp_LocalFree
0x1400f4626  nop     dword ptr [rax+rax+00h]
0x1400f462b  nop
0x1400f462c  mov     rcx, [rsp+58h+var_18]
0x1400f4631  xor     rcx, rsp; StackCookie
0x1400f4634  call    __security_check_cookie
0x1400f4639  mov     rbx, [rsp+58h+arg_10]
0x1400f463e  mov     rsi, [rsp+58h+arg_18]
0x1400f4643  add     rsp, 50h
0x1400f4647  pop     rdi
0x1400f4648  retn
0x1400f464a  lea     r8, [rsp+58h+Size]; lpdwBufferLength
0x1400f464f  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x1400f4652  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x1400f4655  call    cs:__imp_MakeSelfRelativeSD
0x1400f465c  nop     dword ptr [rax+rax+00h]
0x1400f4661  mov     rcx, [rsp+58h]; this
0x1400f4666  test    eax, eax
0x1400f4668  jnz     short loc_1400F4614
0x1400f466a  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400f4671  mov     edx, 193Eh; void *
0x1400f4676  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
