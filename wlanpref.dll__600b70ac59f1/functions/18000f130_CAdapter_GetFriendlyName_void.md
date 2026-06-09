# CAdapter::GetFriendlyName(void)

- ea: `0x18000f130`
- end: `0x18000f214`
- name: `?GetFriendlyName@CAdapter@@QEBA?AVCString@WTL@@XZ`
- size: `228`
- prototype: `struct WTL::CString __high(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f630`
- `0x1800105cc`

## callees

- `0x1800036fc`
- `0x18000cee0`
- `0x18000f130`
- `0x18002d80e`
- `0x18002d840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f1a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f1a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f1ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f1ee`
- `NCI!NciGetConnectionName` at `0x18000f18c`
- `NCI!NciGetConnectionName` at `0x18000f1d0`
- `NCI!NciGetConnectionName` at `0x18000f18c`
- `NCI!NciGetConnectionName` at `0x18000f1d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
WTL::CString *__fastcall CAdapter::GetFriendlyName(__int64 a1, WTL::CString *a2)
{
  void *v3; // rax
  unsigned __int16 *v4; // rbx
  unsigned __int16 *v5; // rcx
  SIZE_T cb[3]; // [rsp+20h] [rbp-30h] BYREF
  __int128 v8; // [rsp+38h] [rbp-18h] BYREF

  cb[1] = (SIZE_T)a2;
  cb[0] = 0x100000000LL;
  v8 = *(_OWORD *)(a1 + 8);
  WTL::CString::CString(a2, (const struct WTL::CString *)(a1 + 24));
  if ( !(unsigned int)NciGetConnectionName(&v8, 0, 0, cb) )
  {
    if ( LODWORD(cb[0]) <= 0x7FFFFFFFuLL
      && (v3 = CoTaskMemAlloc(LODWORD(cb[0])), v4 = (unsigned __int16 *)v3, (cb[2] = (SIZE_T)v3) != 0) )
    {
      memset_0(v3, 0, LODWORD(cb[0]));
      if ( !(unsigned int)NciGetConnectionName(&v8, v4, LODWORD(cb[0]), 0) )
        WTL::CString::operator=(a2, v4);
      v5 = v4;
    }
    else
    {
      v5 = 0;
    }
    CoTaskMemFree(v5);
  }
  return a2;
}

```

## disassembly

```asm
0x18000f130  mov     [rsp-8+arg_10], rbx
0x18000f135  mov     [rsp-8+arg_18], rdi
0x18000f13a  push    rbp
0x18000f13b  mov     rbp, rsp
0x18000f13e  sub     rsp, 50h
0x18000f142  mov     rax, cs:__security_cookie
0x18000f149  xor     rax, rsp
0x18000f14c  mov     [rbp+var_8], rax
0x18000f150  mov     rdi, rdx
0x18000f153  mov     [rbp+var_28], rdx
0x18000f157  mov     ebx, 1
0x18000f15c  mov     dword ptr [rbp+cb+4], ebx
0x18000f15f  mov     dword ptr [rbp+cb], 0
0x18000f166  movups  xmm0, xmmword ptr [rcx+8]
0x18000f16a  movdqu  [rbp+var_18], xmm0
0x18000f16f  lea     rdx, [rcx+18h]; struct WTL::CString *
0x18000f173  mov     rcx, rdi; this
0x18000f176  call    ??0CString@WTL@@QEAA@AEBV01@@Z; WTL::CString::CString(WTL::CString const &)
0x18000f17b  nop
0x18000f17c  mov     dword ptr [rbp+cb+4], ebx
0x18000f17f  lea     r9, [rbp+cb]
0x18000f183  xor     r8d, r8d
0x18000f186  xor     edx, edx
0x18000f188  lea     rcx, [rbp+var_18]
0x18000f18c  call    cs:__imp_NciGetConnectionName
0x18000f192  test    eax, eax
0x18000f194  jnz     short loc_18000F1F5
0x18000f196  mov     ecx, dword ptr [rbp+cb]; cb
0x18000f199  cmp     rcx, 7FFFFFFFh
0x18000f1a0  ja      short loc_18000F1EC
0x18000f1a2  call    cs:__imp_CoTaskMemAlloc
0x18000f1a8  mov     rbx, rax
0x18000f1ab  mov     [rbp+var_20], rax
0x18000f1af  test    rax, rax
0x18000f1b2  jz      short loc_18000F1EC
0x18000f1b4  mov     r8d, dword ptr [rbp+cb]; Size
0x18000f1b8  xor     edx, edx; Val
0x18000f1ba  mov     rcx, rax; void *
0x18000f1bd  call    memset_0
0x18000f1c2  xor     r9d, r9d
0x18000f1c5  mov     r8d, dword ptr [rbp+cb]
0x18000f1c9  mov     rdx, rbx
0x18000f1cc  lea     rcx, [rbp+var_18]
0x18000f1d0  call    cs:__imp_NciGetConnectionName
0x18000f1d6  test    eax, eax
0x18000f1d8  jz      short loc_18000F1DF
0x18000f1da  mov     rcx, rbx
0x18000f1dd  jmp     short loc_18000F1EE
0x18000f1df  mov     rdx, rbx; unsigned __int16 *
0x18000f1e2  mov     rcx, rdi; this
0x18000f1e5  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x18000f1ea  jmp     short loc_18000F1DA
0x18000f1ec  xor     ecx, ecx; pv
0x18000f1ee  call    cs:__imp_CoTaskMemFree
0x18000f1f4  nop
0x18000f1f5  mov     rax, rdi
0x18000f1f8  mov     rcx, [rbp+var_8]
0x18000f1fc  xor     rcx, rsp; StackCookie
0x18000f1ff  call    __security_check_cookie
0x18000f204  mov     rbx, [rsp+50h+arg_10]
0x18000f209  mov     rdi, [rsp+50h+arg_18]
0x18000f20e  add     rsp, 50h
0x18000f212  pop     rbp
0x18000f213  retn
```
