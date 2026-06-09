# Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)

- ea: `0x1400dfa90`
- end: `0x1400dfbda`
- name: `??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z`
- size: `330`
- prototype: `_QWORD(Vml::VmSid *__hidden this, enum WELL_KNOWN_SID_TYPE, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400e22d4`

## callees

- `0x140005360`
- `0x14000ddac`
- `0x1400dfa90`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1400dfb14`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1400dfb14`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400dfb4a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400dfb4a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400dfb30`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400dfb30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400dfb5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400dfb5b`

## string_xrefs

- `0x1400dfbb6`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400dfbc8`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Vml::VmSid *__fastcall Vml::VmSid::VmSid(Vml::VmSid *this, enum WELL_KNOWN_SID_TYPE a2, void *a3)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rdi
  const char *v6; // r9
  HLOCAL v7; // rax
  const char *v8; // r9
  HLOCAL v9; // rbp
  void *v10; // rcx
  DWORD cbSid[4]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE pSid[80]; // [rsp+40h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 7;
  v4 = (_QWORD *)((char *)this + 16);
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 7;
  *((_WORD *)this + 8) = 0;
  v5 = (_QWORD *)((char *)this + 48);
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 7;
  *((_WORD *)this + 24) = 0;
  cbSid[0] = 68;
  if ( !CreateWellKnownSid(a2, a3, pSid, cbSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1469,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v6);
  v7 = LocalAlloc(0, cbSid[0]);
  v9 = v7;
  if ( !v7 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x146F,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v8);
  CopySid(cbSid[0], v7, pSid);
  v10 = *(void **)this;
  *(_QWORD *)this = v9;
  if ( v10 )
    LocalFree(v10);
  *((_DWORD *)this + 2) = 7;
  v5[2] = 0;
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  *(_WORD *)v5 = 0;
  v4[2] = 0;
  if ( v4[3] > 7u )
    v4 = (_QWORD *)*v4;
  *(_WORD *)v4 = 0;
  return this;
}

```

## disassembly

```asm
0x1400dfa90  push    rbx
0x1400dfa92  push    rbp
0x1400dfa93  push    rsi
0x1400dfa94  push    rdi
0x1400dfa95  push    r15
0x1400dfa97  sub     rsp, 0A0h
0x1400dfa9e  mov     rax, cs:__security_cookie
0x1400dfaa5  xor     rax, rsp
0x1400dfaa8  mov     [rsp+0C8h+var_38], rax
0x1400dfab0  mov     r11, r8
0x1400dfab3  mov     r10d, edx
0x1400dfab6  mov     rsi, rcx
0x1400dfab9  mov     [rsp+0C8h+var_A8], rcx
0x1400dfabe  mov     qword ptr [rcx], 0
0x1400dfac5  mov     r15d, 7
0x1400dfacb  mov     [rcx+8], r15d
0x1400dfacf  lea     rbx, [rcx+10h]
0x1400dfad3  xorps   xmm0, xmm0
0x1400dfad6  movups  xmmword ptr [rbx], xmm0
0x1400dfad9  mov     qword ptr [rbx+10h], 0
0x1400dfae1  mov     [rbx+18h], r15
0x1400dfae5  xor     eax, eax
0x1400dfae7  mov     [rbx], ax
0x1400dfaea  lea     rdi, [rcx+30h]
0x1400dfaee  movups  xmmword ptr [rdi], xmm0
0x1400dfaf1  mov     [rdi+10h], rax
0x1400dfaf5  mov     [rdi+18h], r15
0x1400dfaf9  mov     [rdi], ax
0x1400dfafc  mov     [rsp+0C8h+cbSid], 44h ; 'D'
0x1400dfb04  lea     r9, [rsp+0C8h+cbSid]; cbSid
0x1400dfb09  lea     r8, [rsp+0C8h+pSid]; pSid
0x1400dfb0e  mov     rdx, r11; DomainSid
0x1400dfb11  mov     ecx, r10d; WellKnownSidType
0x1400dfb14  call    cs:__imp_CreateWellKnownSid
0x1400dfb1a  mov     rcx, [rsp+0C8h]; this
0x1400dfb22  test    eax, eax
0x1400dfb24  jz      loc_1400DFBC8
0x1400dfb2a  mov     edx, [rsp+0C8h+cbSid]; uBytes
0x1400dfb2e  xor     ecx, ecx; uFlags
0x1400dfb30  call    cs:__imp_LocalAlloc
0x1400dfb36  mov     rbp, rax
0x1400dfb39  test    rax, rax
0x1400dfb3c  jz      short loc_1400DFBAE
0x1400dfb3e  lea     r8, [rsp+0C8h+pSid]; pSourceSid
0x1400dfb43  mov     rdx, rax; pDestinationSid
0x1400dfb46  mov     ecx, [rsp+0C8h+cbSid]; nDestinationSidLength
0x1400dfb4a  call    cs:__imp_CopySid
0x1400dfb50  mov     rcx, [rsi]; hMem
0x1400dfb53  mov     [rsi], rbp
0x1400dfb56  test    rcx, rcx
0x1400dfb59  jz      short loc_1400DFB61
0x1400dfb5b  call    cs:__imp_LocalFree
0x1400dfb61  mov     [rsi+8], r15d
0x1400dfb65  mov     qword ptr [rdi+10h], 0
0x1400dfb6d  cmp     [rdi+18h], r15
0x1400dfb71  jbe     short loc_1400DFB76
0x1400dfb73  mov     rdi, [rdi]
0x1400dfb76  xor     eax, eax
0x1400dfb78  mov     [rdi], ax
0x1400dfb7b  mov     [rbx+10h], rax
0x1400dfb7f  cmp     [rbx+18h], r15
0x1400dfb83  jbe     short loc_1400DFB88
0x1400dfb85  mov     rbx, [rbx]
0x1400dfb88  xor     ecx, ecx
0x1400dfb8a  mov     [rbx], cx
0x1400dfb8d  mov     rax, rsi
0x1400dfb90  mov     rcx, [rsp+0C8h+var_38]
0x1400dfb98  xor     rcx, rsp; StackCookie
0x1400dfb9b  call    __security_check_cookie
0x1400dfba0  add     rsp, 0A0h
0x1400dfba7  pop     r15
0x1400dfba9  pop     rdi
0x1400dfbaa  pop     rsi
0x1400dfbab  pop     rbp
0x1400dfbac  pop     rbx
0x1400dfbad  retn
0x1400dfbae  mov     rcx, [rsp+0C8h]; this
0x1400dfbb6  lea     r8, aOnecoreVmCommo_12; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400dfbbd  mov     edx, 146Fh; void *
0x1400dfbc2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400dfbc8  lea     r8, aOnecoreVmCommo_12; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400dfbcf  mov     edx, 1469h; void *
0x1400dfbd4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
