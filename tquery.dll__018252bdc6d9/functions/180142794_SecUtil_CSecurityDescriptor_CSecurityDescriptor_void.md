# SecUtil::CSecurityDescriptor::CSecurityDescriptor(void)

- ea: `0x180142794`
- end: `0x18014287b`
- name: `??0CSecurityDescriptor@SecUtil@@QEAA@XZ`
- size: `231`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180064688`
- `0x18010bb54`
- `0x18014164c`
- `0x180142978`
- `0x180142bac`
- `0x1801ffbe8`

## callees

- `0x180142794`
- `0x180142884`
- `0x180147154`
- `0x1801895b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1801427d7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180142817`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1801427d7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180142817`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180142840`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180142840`

## string_xrefs

- `0x1801427e6`: `onecoreuap\base\appmodel\Search\common\include\secutil_common.hxx`
- `0x180142826`: `onecoreuap\base\appmodel\Search\common\include\secutil_common.hxx`
- `0x18014284f`: `onecoreuap\base\appmodel\Search\common\include\secutil_common.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall SecUtil::CSecurityDescriptor::CSecurityDescriptor(_QWORD *pSecurityDescriptor)
{
  struct _ACL *v2; // rax
  const char *v3; // r9
  struct _ACL *v4; // rax
  const char *v5; // r9
  int v6; // edx
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  pSecurityDescriptor[5] = 0;
  pSecurityDescriptor[6] = 0;
  pSecurityDescriptor[7] = 0;
  v2 = (struct _ACL *)operator new[](8u);
  pSecurityDescriptor[7] = v2;
  if ( !InitializeAcl(v2, 8u, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\secutil_common.hxx",
      v3);
  pSecurityDescriptor[8] = 0;
  v4 = (struct _ACL *)operator new[](8u);
  pSecurityDescriptor[8] = v4;
  if ( !InitializeAcl(v4, 8u, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\secutil_common.hxx",
      v5);
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x18D,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\secutil_common.hxx",
      v7);
  SecUtil::CSecurityDescriptor::SetDacl((SecUtil::CSecurityDescriptor *)pSecurityDescriptor, v6, 0, (int)v7);
  return pSecurityDescriptor;
}

```

## disassembly

```asm
0x180142794  mov     [rsp+arg_8], rbx
0x180142799  mov     [rsp+arg_0], rcx
0x18014279e  push    rsi
0x18014279f  sub     rsp, 20h
0x1801427a3  mov     rbx, rcx
0x1801427a6  mov     qword ptr [rcx+28h], 0
0x1801427ae  mov     qword ptr [rcx+30h], 0
0x1801427b6  mov     qword ptr [rcx+38h], 0
0x1801427be  mov     esi, 8
0x1801427c3  mov     ecx, esi; unsigned __int64
0x1801427c5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1801427ca  mov     [rbx+38h], rax
0x1801427ce  lea     r8d, [rsi-6]; dwAclRevision
0x1801427d2  mov     edx, esi; nAclLength
0x1801427d4  mov     rcx, rax; pAcl
0x1801427d7  call    cs:__imp_InitializeAcl
0x1801427dd  test    eax, eax
0x1801427df  jnz     short loc_1801427F8
0x1801427e1  mov     rcx, [rsp+28h]; this
0x1801427e6  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801427ed  mov     edx, 16Ah; void *
0x1801427f2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801427f8  mov     qword ptr [rbx+40h], 0
0x180142800  mov     rcx, rsi; unsigned __int64
0x180142803  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180142808  mov     [rbx+40h], rax
0x18014280c  mov     r8d, 2; dwAclRevision
0x180142812  mov     edx, esi; nAclLength
0x180142814  mov     rcx, rax; pAcl
0x180142817  call    cs:__imp_InitializeAcl
0x18014281d  test    eax, eax
0x18014281f  jnz     short loc_180142838
0x180142821  mov     rcx, [rsp+28h]; this
0x180142826  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18014282d  mov     edx, 16Ah; void *
0x180142832  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180142838  mov     edx, 1; dwRevision
0x18014283d  mov     rcx, rbx; pSecurityDescriptor
0x180142840  call    cs:__imp_InitializeSecurityDescriptor
0x180142846  test    eax, eax
0x180142848  jnz     short loc_180142861
0x18014284a  mov     rcx, [rsp+28h]; this
0x18014284f  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180142856  mov     edx, 18Dh; void *
0x18014285b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180142861  xor     r8d, r8d; struct _ACL *
0x180142864  mov     rcx, rbx; this
0x180142867  call    ?SetDacl@CSecurityDescriptor@SecUtil@@QEAAXHPEAU_ACL@@H@Z; SecUtil::CSecurityDescriptor::SetDacl(int,_ACL *,int)
0x18014286c  nop
0x18014286d  mov     rax, rbx
0x180142870  mov     rbx, [rsp+28h+arg_8]
0x180142875  add     rsp, 20h
0x180142879  pop     rsi
0x18014287a  retn
```
