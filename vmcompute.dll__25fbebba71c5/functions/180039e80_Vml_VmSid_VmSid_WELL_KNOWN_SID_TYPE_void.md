# Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)

- ea: `0x180039e80`
- end: `0x180039ff4`
- name: `??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z`
- size: `372`
- prototype: `_QWORD(Vml::VmSid *__hidden this, enum WELL_KNOWN_SID_TYPE, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003a324`

## callees

- `0x180002f50`
- `0x18000d0ec`
- `0x180039e80`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039f64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039f64`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180039f07`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180039f07`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180039f4d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180039f4d`
- `KERNELBASE!LocalAlloc` at `0x180039f29`
- `KERNELBASE!LocalAlloc` at `0x180039f29`

## string_xrefs

- `0x180039fd0`: `onecore\vm\common\vml\VmSecurity.h`
- `0x180039fe2`: `onecore\vm\common\vml\VmSecurity.h`

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
  DWORD cbSid[4]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE pSid[80]; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

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
  if ( !CreateWellKnownSid(a2, 0, pSid, cbSid) )
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
0x180039e80  mov     [rsp+arg_10], rbx
0x180039e85  mov     [rsp+arg_18], rbp
0x180039e8a  push    rsi
0x180039e8b  push    rdi
0x180039e8c  push    r15
0x180039e8e  sub     rsp, 0A0h
0x180039e95  mov     rax, cs:__security_cookie
0x180039e9c  xor     rax, rsp
0x180039e9f  mov     [rsp+0B8h+var_28], rax
0x180039ea7  mov     r10d, edx
0x180039eaa  mov     rsi, rcx
0x180039ead  mov     [rsp+0B8h+var_98], rcx
0x180039eb2  mov     qword ptr [rcx], 0
0x180039eb9  mov     r15d, 7
0x180039ebf  mov     [rcx+8], r15d
0x180039ec3  lea     rbx, [rcx+10h]
0x180039ec7  xorps   xmm0, xmm0
0x180039eca  movups  xmmword ptr [rbx], xmm0
0x180039ecd  mov     qword ptr [rbx+10h], 0
0x180039ed5  mov     [rbx+18h], r15
0x180039ed9  xor     eax, eax
0x180039edb  mov     [rbx], ax
0x180039ede  lea     rdi, [rcx+30h]
0x180039ee2  movups  xmmword ptr [rdi], xmm0
0x180039ee5  mov     [rdi+10h], rax
0x180039ee9  mov     [rdi+18h], r15
0x180039eed  mov     [rdi], ax
0x180039ef0  mov     [rsp+0B8h+cbSid], 44h ; 'D'
0x180039ef8  lea     r9, [rsp+0B8h+cbSid]; cbSid
0x180039efd  lea     r8, [rsp+0B8h+pSid]; pSid
0x180039f02  xor     edx, edx; DomainSid
0x180039f04  mov     ecx, r10d; WellKnownSidType
0x180039f07  call    cs:__imp_CreateWellKnownSid
0x180039f0e  nop     dword ptr [rax+rax+00h]
0x180039f13  mov     rcx, [rsp+0B8h]; this
0x180039f1b  test    eax, eax
0x180039f1d  jz      loc_180039FE2
0x180039f23  mov     edx, [rsp+0B8h+cbSid]; uBytes
0x180039f27  xor     ecx, ecx; uFlags
0x180039f29  call    cs:__imp_LocalAlloc
0x180039f30  nop     dword ptr [rax+rax+00h]
0x180039f35  mov     rbp, rax
0x180039f38  test    rax, rax
0x180039f3b  jz      loc_180039FC8
0x180039f41  lea     r8, [rsp+0B8h+pSid]; pSourceSid
0x180039f46  mov     rdx, rax; pDestinationSid
0x180039f49  mov     ecx, [rsp+0B8h+cbSid]; nDestinationSidLength
0x180039f4d  call    cs:__imp_CopySid
0x180039f54  nop     dword ptr [rax+rax+00h]
0x180039f59  mov     rcx, [rsi]; hMem
0x180039f5c  mov     [rsi], rbp
0x180039f5f  test    rcx, rcx
0x180039f62  jz      short loc_180039F70
0x180039f64  call    cs:__imp_LocalFree
0x180039f6b  nop     dword ptr [rax+rax+00h]
0x180039f70  mov     [rsi+8], r15d
0x180039f74  mov     qword ptr [rdi+10h], 0
0x180039f7c  cmp     [rdi+18h], r15
0x180039f80  jbe     short loc_180039F85
0x180039f82  mov     rdi, [rdi]
0x180039f85  xor     eax, eax
0x180039f87  mov     [rdi], ax
0x180039f8a  mov     [rbx+10h], rax
0x180039f8e  cmp     [rbx+18h], r15
0x180039f92  jbe     short loc_180039F97
0x180039f94  mov     rbx, [rbx]
0x180039f97  xor     ecx, ecx
0x180039f99  mov     [rbx], cx
0x180039f9c  mov     rax, rsi
0x180039f9f  mov     rcx, [rsp+0B8h+var_28]
0x180039fa7  xor     rcx, rsp; StackCookie
0x180039faa  call    __security_check_cookie
0x180039faf  lea     r11, [rsp+0B8h+var_18]
0x180039fb7  mov     rbx, [r11+30h]
0x180039fbb  mov     rbp, [r11+38h]
0x180039fbf  mov     rsp, r11
0x180039fc2  pop     r15
0x180039fc4  pop     rdi
0x180039fc5  pop     rsi
0x180039fc6  retn
0x180039fc8  mov     rcx, [rsp+0B8h]; this
0x180039fd0  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180039fd7  mov     edx, 146Fh; void *
0x180039fdc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180039fe2  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180039fe9  mov     edx, 1469h; void *
0x180039fee  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
