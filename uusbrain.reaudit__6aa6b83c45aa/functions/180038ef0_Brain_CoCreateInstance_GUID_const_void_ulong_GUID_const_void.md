# Brain::CoCreateInstance(_GUID const &,void *,ulong,_GUID const &,void * *)

- ea: `0x180038ef0`
- end: `0x180038fd1`
- name: `?CoCreateInstance@Brain@@UEBAJAEBU_GUID@@PEAXK0PEAPEAX@Z`
- size: `225`
- prototype: `int(Brain *__hidden this, const struct _GUID *, void *, unsigned int, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180028728`
- `0x1800361a8`
- `0x180038ef0`
- `0x180042bfc`
- `0x180047a30`
- `0x180047ab0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038f95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038f95`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Brain::CoCreateInstance(
        Brain *this,
        const struct _GUID *a2,
        IUnknown *a3,
        DWORD a4,
        const struct _GUID *riid,
        void **ppv)
{
  void (__fastcall ***v10)(_QWORD, __int64); // rbx
  unsigned int Instance; // edi
  const char *v12; // r9
  __int64 result; // rax
  wil *v14; // rcx
  void *v15; // [rsp+30h] [rbp-98h]
  _BYTE v16[32]; // [rsp+48h] [rbp-80h] BYREF
  _BYTE v17[96]; // [rsp+68h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  try
  {
    v15 = operator new(0x98u);
    memset(v15, 0, 0x98u);
    std::wstring::wstring(v16, (char *)this + 224);
    std::wstring::wstring(v17, (char *)this + 136);
    v10 = (void (__fastcall ***)(_QWORD, __int64))SmartActivationContext::SmartActivationContext(
                                                    (__int64)v15,
                                                    (__int64)v17,
                                                    (__int64)v16);
    Instance = CoCreateInstance(a2, a3, a4, riid, ppv);
    if ( v10 )
      (**v10)(v10, 1);
    result = Instance;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x137,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\Brain.cpp",
      v12);
    return (unsigned int)wil::ResultFromCaughtException(v14);
  }
  return result;
}

```

## disassembly

```asm
0x180038ef0  push    rbx
0x180038ef2  push    rsi
0x180038ef3  push    rdi
0x180038ef4  push    r12
0x180038ef6  push    r13
0x180038ef8  push    r14
0x180038efa  push    r15
0x180038efc  sub     rsp, 90h
0x180038f03  mov     r15d, r9d
0x180038f06  mov     r14, r8
0x180038f09  mov     rsi, rdx
0x180038f0c  mov     rdi, rcx
0x180038f0f  mov     r12, [rsp+0C8h+riid]
0x180038f17  mov     r13, [rsp+0C8h+arg_28]
0x180038f1f  mov     ecx, 98h; Size
0x180038f24  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038f29  mov     rbx, rax
0x180038f2c  mov     [rsp+0C8h+var_98], rax
0x180038f31  xor     edx, edx; Val
0x180038f33  mov     r8d, 98h; Size
0x180038f39  mov     rcx, rax; void *
0x180038f3c  call    memset
0x180038f41  lea     rax, [rsp+0C8h+var_80]
0x180038f46  mov     [rsp+0C8h+var_90], rax
0x180038f4b  lea     rdx, [rdi+0E0h]
0x180038f52  lea     rcx, [rsp+0C8h+var_80]
0x180038f57  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038f5c  nop
0x180038f5d  lea     rdx, [rdi+88h]
0x180038f64  lea     rcx, [rsp+0C8h+var_60]
0x180038f69  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038f6e  nop
0x180038f6f  lea     r8, [rsp+0C8h+var_80]
0x180038f74  lea     rdx, [rsp+0C8h+var_60]
0x180038f79  mov     rcx, rbx
0x180038f7c  call    ??0SmartActivationContext@@QEAA@Vpath@filesystem@std@@0@Z; SmartActivationContext::SmartActivationContext(std::filesystem::path,std::filesystem::path)
0x180038f81  mov     rbx, rax
0x180038f84  mov     [rsp+0C8h+ppv], r13; ppv
0x180038f89  mov     r9, r12; riid
0x180038f8c  mov     r8d, r15d; dwClsContext
0x180038f8f  mov     rdx, r14; pUnkOuter
0x180038f92  mov     rcx, rsi; rclsid
0x180038f95  call    cs:__imp_CoCreateInstance
0x180038f9b  mov     edi, eax
0x180038f9d  test    rbx, rbx
0x180038fa0  jz      short loc_180038FB5
0x180038fa2  mov     rcx, [rbx]
0x180038fa5  mov     rax, [rcx]
0x180038fa8  mov     edx, 1
0x180038fad  mov     rcx, rbx
0x180038fb0  call    _guard_dispatch_icall
0x180038fb5  mov     eax, edi
0x180038fb7  jmp     short loc_180038FBD
0x180038fb9  mov     eax, dword ptr [rsp+0C8h+var_98]
0x180038fbd  add     rsp, 90h
0x180038fc4  pop     r15
0x180038fc6  pop     r14
0x180038fc8  pop     r13
0x180038fca  pop     r12
0x180038fcc  pop     rdi
0x180038fcd  pop     rsi
0x180038fce  pop     rbx
0x180038fcf  retn
```
