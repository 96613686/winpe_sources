# Vml::VmSid::VmSid(ushort const *)

- ea: `0x180049c60`
- end: `0x180049d5a`
- name: `??0VmSid@Vml@@QEAA@PEBG@Z`
- size: `250`
- prototype: `__int64 __fastcall(Vml::VmSid *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004a43c`
- `0x18004a688`
- `0x18004aa68`
- `0x18004ba9c`

## callees

- `0x180002f50`
- `0x18000d0ec`
- `0x180049c60`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049cf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049cf0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180049cd0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180049cd0`

## string_xrefs

- `0x180049d48`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Vml::VmSid *__fastcall Vml::VmSid::VmSid(Vml::VmSid *this, const unsigned __int16 *a2)
{
  _QWORD *v3; // rbx
  _QWORD *v4; // rdi
  const char *v5; // r9
  void *v6; // rcx
  PSID Sid; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 7;
  v3 = (_QWORD *)((char *)this + 16);
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 7;
  *((_WORD *)this + 8) = 0;
  v4 = (_QWORD *)((char *)this + 48);
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 7;
  *((_WORD *)this + 24) = 0;
  Sid = 0;
  if ( !ConvertStringSidToSidW(
          L"S-1-15-3-1024-2268835264-3721307629-241982045-173645152-1490879176-104643441-2915960892-1612460704",
          &Sid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x156D,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v5);
  v6 = *(void **)this;
  *(_QWORD *)this = Sid;
  if ( v6 )
    LocalFree(v6);
  *((_DWORD *)this + 2) = 7;
  v4[2] = 0;
  if ( v4[3] > 7u )
    v4 = (_QWORD *)*v4;
  *(_WORD *)v4 = 0;
  v3[2] = 0;
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  *(_WORD *)v3 = 0;
  return this;
}

```

## disassembly

```asm
0x180049c60  push    rbx
0x180049c62  push    rsi
0x180049c63  push    rdi
0x180049c64  push    r14
0x180049c66  sub     rsp, 48h
0x180049c6a  mov     rax, cs:__security_cookie
0x180049c71  xor     rax, rsp
0x180049c74  mov     [rsp+68h+var_30], rax
0x180049c79  mov     rsi, rcx
0x180049c7c  mov     [rsp+68h+var_48], rcx
0x180049c81  mov     qword ptr [rcx], 0
0x180049c88  mov     r14d, 7
0x180049c8e  mov     [rcx+8], r14d
0x180049c92  lea     rbx, [rcx+10h]
0x180049c96  xorps   xmm0, xmm0
0x180049c99  movups  xmmword ptr [rbx], xmm0
0x180049c9c  mov     qword ptr [rbx+10h], 0
0x180049ca4  mov     [rbx+18h], r14
0x180049ca8  xor     eax, eax
0x180049caa  mov     [rbx], ax
0x180049cad  lea     rdi, [rcx+30h]
0x180049cb1  movups  xmmword ptr [rdi], xmm0
0x180049cb4  mov     [rdi+10h], rax
0x180049cb8  mov     [rdi+18h], r14
0x180049cbc  mov     [rdi], ax
0x180049cbf  mov     [rsp+68h+Sid], rax
0x180049cc4  lea     rdx, [rsp+68h+Sid]; Sid
0x180049cc9  lea     rcx, StringSid; "S-1-15-3-1024-2268835264-3721307629-241"...
0x180049cd0  call    cs:__imp_ConvertStringSidToSidW
0x180049cd7  nop     dword ptr [rax+rax+00h]
0x180049cdc  test    eax, eax
0x180049cde  jz      short loc_180049D43
0x180049ce0  mov     rcx, [rsi]; hMem
0x180049ce3  mov     rax, [rsp+68h+Sid]
0x180049ce8  mov     [rsi], rax
0x180049ceb  test    rcx, rcx
0x180049cee  jz      short loc_180049CFC
0x180049cf0  call    cs:__imp_LocalFree
0x180049cf7  nop     dword ptr [rax+rax+00h]
0x180049cfc  mov     [rsi+8], r14d
0x180049d00  mov     qword ptr [rdi+10h], 0
0x180049d08  cmp     [rdi+18h], r14
0x180049d0c  jbe     short loc_180049D11
0x180049d0e  mov     rdi, [rdi]
0x180049d11  xor     eax, eax
0x180049d13  mov     [rdi], ax
0x180049d16  mov     [rbx+10h], rax
0x180049d1a  cmp     [rbx+18h], r14
0x180049d1e  jbe     short loc_180049D23
0x180049d20  mov     rbx, [rbx]
0x180049d23  xor     ecx, ecx
0x180049d25  mov     [rbx], cx
0x180049d28  mov     rax, rsi
0x180049d2b  mov     rcx, [rsp+68h+var_30]
0x180049d30  xor     rcx, rsp; StackCookie
0x180049d33  call    __security_check_cookie
0x180049d38  add     rsp, 48h
0x180049d3c  pop     r14
0x180049d3e  pop     rdi
0x180049d3f  pop     rsi
0x180049d40  pop     rbx
0x180049d41  retn
0x180049d43  mov     rcx, [rsp+68h]; this
0x180049d48  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180049d4f  mov     edx, 156Dh; void *
0x180049d54  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
