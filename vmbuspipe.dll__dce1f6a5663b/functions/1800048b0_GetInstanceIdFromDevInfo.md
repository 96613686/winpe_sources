# GetInstanceIdFromDevInfo

- ea: `0x1800048b0`
- end: `0x1800049f5`
- name: `GetInstanceIdFromDevInfo`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180006718`

## callees

- `0x180001b44`
- `0x180001f64`
- `0x1800024e0`
- `0x180002504`
- `0x1800028e0`
- `0x1800048b0`
- `0x1800049fc`
- `0x180005d94`

## import_xrefs

- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1800048ec`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180004975`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1800048ec`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180004975`

## string_xrefs

- `0x1800048ff`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x18000494b`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x180004984`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x1800049b9`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`

## pseudocode

```c
int __fastcall GetInstanceIdFromDevInfo(__int64 a1, __int64 a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  DevObjGetDeviceInstanceId(a1, a2, 0, 0);
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x29D,
           (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
           v2);
}

```

## disassembly

```asm
0x1800048b0  mov     [rsp+arg_18], rbx
0x1800048b5  push    rbp
0x1800048b6  push    rsi
0x1800048b7  push    rdi
0x1800048b8  sub     rsp, 40h
0x1800048bc  mov     rax, cs:__security_cookie
0x1800048c3  xor     rax, rsp
0x1800048c6  mov     [rsp+58h+var_20], rax
0x1800048cb  mov     rbp, r8
0x1800048ce  mov     [rsp+58h+var_28], 0
0x1800048d6  lea     rax, [rsp+58h+var_28]
0x1800048db  xor     r8d, r8d
0x1800048de  xor     r9d, r9d
0x1800048e1  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x1800048e6  mov     rsi, rdx
0x1800048e9  mov     rbx, rcx
0x1800048ec  call    cs:__imp_DevObjGetDeviceInstanceId
0x1800048f2  mov     eax, [rsp+58h+var_28]
0x1800048f6  test    eax, eax
0x1800048f8  jnz     short loc_180004915
0x1800048fa  mov     rcx, [rsp+58h]; this
0x1800048ff  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180004906  mov     edx, 29Dh; void *
0x18000490b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180004910  jmp     loc_1800049DB
0x180004915  lea     ecx, [rax+1]
0x180004918  mov     eax, 2
0x18000491d  mul     rcx
0x180004920  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180004927  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000492e  cmovb   rax, rcx
0x180004932  mov     rcx, rax; unsigned __int64
0x180004935  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000493a  mov     rdi, rax
0x18000493d  test    rax, rax
0x180004940  jnz     short loc_18000495E
0x180004942  mov     rcx, [rsp+58h]; this
0x180004947  lea     r9d, [rax+8]; char *
0x18000494b  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180004952  mov     edx, 2A3h; void *
0x180004957  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000495c  jmp     short loc_1800049DB
0x18000495e  mov     r9d, [rsp+58h+var_28]
0x180004963  mov     r8, rdi
0x180004966  mov     rdx, rsi
0x180004969  mov     qword ptr [rsp+58h+var_38], 0; int
0x180004972  mov     rcx, rbx
0x180004975  call    cs:__imp_DevObjGetDeviceInstanceId
0x18000497b  test    eax, eax
0x18000497d  jnz     short loc_180004999
0x18000497f  mov     rcx, [rsp+58h]; this
0x180004984  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x18000498b  mov     edx, 2AAh; void *
0x180004990  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180004995  mov     ebx, eax
0x180004997  jmp     short loc_1800049D1
0x180004999  mov     ecx, [rsp+58h+var_28]
0x18000499d  xor     eax, eax
0x18000499f  mov     rdx, rbp; lpiid
0x1800049a2  mov     [rdi+rcx*2], ax
0x1800049a6  mov     rcx, rdi; String2
0x1800049a9  call    GetInstanceIdFromDevName
0x1800049ae  mov     ebx, eax
0x1800049b0  test    eax, eax
0x1800049b2  jns     short loc_1800049CF
0x1800049b4  mov     rcx, [rsp+58h]; this
0x1800049b9  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x1800049c0  mov     r9d, eax; char *
0x1800049c3  mov     edx, 2AEh; void *
0x1800049c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049cd  jmp     short loc_1800049D1
0x1800049cf  xor     ebx, ebx
0x1800049d1  mov     rcx, rdi; void *
0x1800049d4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800049d9  mov     eax, ebx
0x1800049db  mov     rcx, [rsp+58h+var_20]
0x1800049e0  xor     rcx, rsp; StackCookie
0x1800049e3  call    __security_check_cookie
0x1800049e8  mov     rbx, [rsp+58h+arg_18]
0x1800049ed  add     rsp, 40h
0x1800049f1  pop     rdi
0x1800049f2  pop     rsi
0x1800049f3  pop     rbp
0x1800049f4  retn
```
