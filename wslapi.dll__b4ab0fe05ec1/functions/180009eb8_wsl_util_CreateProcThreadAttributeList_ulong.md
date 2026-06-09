# wsl::util::CreateProcThreadAttributeList(ulong)

- ea: `0x180009eb8`
- end: `0x180009f8b`
- name: `?CreateProcThreadAttributeList@util@wsl@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6AXPEAU1@@Z$1?DeleteProcThreadAttributeList@util@wsl@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `211`
- prototype: `struct _PROC_THREAD_ATTRIBUTE_LIST **__fastcall(struct _PROC_THREAD_ATTRIBUTE_LIST **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a054`

## callees

- `0x180001dc0`
- `0x180009058`
- `0x180009eb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f06`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180009ef7`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180009f50`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180009ef7`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180009f50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009f30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009f30`

## pseudocode

```c
struct _PROC_THREAD_ATTRIBUTE_LIST **__fastcall wsl::util::CreateProcThreadAttributeList(
        struct _PROC_THREAD_ATTRIBUTE_LIST **a1)
{
  const char *v2; // r9
  struct _PROC_THREAD_ATTRIBUTE_LIST *v3; // rax
  const char *v4; // r9
  SIZE_T cb; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  cb = 0;
  if ( !InitializeProcThreadAttributeList(0, 1u, 0, &cb) && GetLastError() != 122 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x46,
      (int)"onecore\\vm\\wsl\\lxss\\wslutil\\wslutil.cpp",
      v2);
  *a1 = 0;
  v3 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)CoTaskMemAlloc(cb);
  *a1 = v3;
  if ( !InitializeProcThreadAttributeList(v3, 1u, 0, &cb) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x4A,
      (int)"onecore\\vm\\wsl\\lxss\\wslutil\\wslutil.cpp",
      v4);
  return a1;
}

```

## disassembly

```asm
0x180009eb8  mov     r11, rsp
0x180009ebb  mov     [r11+10h], rbx
0x180009ebf  push    rdi
0x180009ec0  sub     rsp, 40h
0x180009ec4  mov     rax, cs:__security_cookie
0x180009ecb  xor     rax, rsp
0x180009ece  mov     [rsp+48h+var_10], rax
0x180009ed3  mov     rbx, rcx
0x180009ed6  mov     [r11-20h], rcx
0x180009eda  mov     [rsp+48h+var_28], 0
0x180009ee2  mov     qword ptr [r11-18h], 0
0x180009eea  lea     r9, [r11-18h]; lpSize
0x180009eee  xor     r8d, r8d; dwFlags
0x180009ef1  lea     edx, [r8+1]; dwAttributeCount
0x180009ef5  xor     ecx, ecx; lpAttributeList
0x180009ef7  call    cs:__imp_InitializeProcThreadAttributeList
0x180009efd  test    eax, eax
0x180009eff  jnz     short loc_180009F26
0x180009f01  mov     rdi, [rsp+48h]
0x180009f06  call    cs:__imp_GetLastError
0x180009f0c  cmp     eax, 7Ah ; 'z'
0x180009f0f  jz      short loc_180009F26
0x180009f11  lea     r8, aOnecoreVmWslLx_0; "onecore\\vm\\wsl\\lxss\\wslutil\\wsluti"...
0x180009f18  mov     edx, 46h ; 'F'; void *
0x180009f1d  mov     rcx, rdi; this
0x180009f20  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180009f26  xor     eax, eax
0x180009f28  mov     [rbx], rax
0x180009f2b  mov     rcx, [rsp+48h+cb]; cb
0x180009f30  call    cs:__imp_CoTaskMemAlloc
0x180009f36  mov     [rbx], rax
0x180009f39  mov     [rsp+48h+var_28], 1
0x180009f41  lea     r9, [rsp+48h+cb]; lpSize
0x180009f46  xor     r8d, r8d; dwFlags
0x180009f49  lea     edx, [r8+1]; dwAttributeCount
0x180009f4d  mov     rcx, rax; lpAttributeList
0x180009f50  call    cs:__imp_InitializeProcThreadAttributeList
0x180009f56  test    eax, eax
0x180009f58  jnz     short loc_180009F6F
0x180009f5a  mov     rcx, [rsp+48h]; this
0x180009f5f  lea     r8, aOnecoreVmWslLx_0; "onecore\\vm\\wsl\\lxss\\wslutil\\wsluti"...
0x180009f66  lea     edx, [rax+4Ah]; void *
0x180009f69  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180009f6f  mov     rax, rbx
0x180009f72  mov     rcx, [rsp+48h+var_10]
0x180009f77  xor     rcx, rsp; StackCookie
0x180009f7a  call    __security_check_cookie
0x180009f7f  mov     rbx, [rsp+48h+arg_8]
0x180009f84  add     rsp, 40h
0x180009f88  pop     rdi
0x180009f89  retn
```
