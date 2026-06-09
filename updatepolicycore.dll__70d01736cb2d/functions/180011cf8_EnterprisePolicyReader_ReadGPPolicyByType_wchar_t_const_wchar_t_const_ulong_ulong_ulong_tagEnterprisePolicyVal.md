# EnterprisePolicyReader::ReadGPPolicyByType(wchar_t const *,wchar_t const *,ulong,ulong,ulong,tagEnterprisePolicyValue_V1 *,wchar_t const *,ulong)

- ea: `0x180011cf8`
- end: `0x180011d89`
- name: `?ReadGPPolicyByType@EnterprisePolicyReader@@CAJPEB_W0KKKPEAUtagEnterprisePolicyValue_V1@@0K@Z`
- size: `145`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, __int64, __int64, unsigned int, struct tagEnterprisePolicyValue_V1 *, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800118d4`
- `0x180011b2c`

## callees

- `0x18000aac0`
- `0x180011cf8`
- `0x18001f880`
- `0x18001f950`

## string_xrefs

- `0x180011d15`: `C:\__w\1\s\src\Client\policy\src\Enterprise\PolicyReader.cpp`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::ReadGPPolicyByType(
        const wchar_t *a1,
        const wchar_t *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        struct tagEnterprisePolicyValue_V1 *a6,
        const wchar_t *a7,
        unsigned int a8)
{
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a8 == 3 )
    return PolicyHelpers::ReadPolicyRegistry(a7, a1, a3, a4, a5, 1, a6);
  if ( a8 == 8 )
    return PolicyHelpers::ReadPolicyRegistry(a7, a1, a2, 1, a6);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x347,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Enterprise\\PolicyReader.cpp",
    (const char *)0x80070057LL,
    v9);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180011cf8  sub     rsp, 48h
0x180011cfc  cmp     [rsp+48h+arg_38], 3
0x180011d04  jz      short loc_180011D5A
0x180011d06  cmp     [rsp+48h+arg_38], 8
0x180011d0e  jz      short loc_180011D33
0x180011d10  mov     rcx, [rsp+48h]; this
0x180011d15  lea     r8, aCW1SSrcClientP_4; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180011d1c  mov     r9d, 80070057h; char *
0x180011d22  mov     edx, 347h; void *
0x180011d27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d2c  mov     eax, 80070057h
0x180011d31  jmp     short loc_180011D84
0x180011d33  mov     rax, [rsp+48h+arg_28]
0x180011d38  mov     r8, rdx
0x180011d3b  mov     rdx, rcx
0x180011d3e  mov     qword ptr [rsp+48h+arg_20], rax
0x180011d43  mov     rcx, [rsp+48h+arg_30]
0x180011d4b  mov     r9d, 1
0x180011d51  add     rsp, 48h
0x180011d55  jmp     ?ReadPolicyRegistry@PolicyHelpers@@SAJPEB_W00W4tagPolicyStore@@PEAUtagEnterprisePolicyValue_V1@@@Z; PolicyHelpers::ReadPolicyRegistry(wchar_t const *,wchar_t const *,wchar_t const *,tagPolicyStore,tagEnterprisePolicyValue_V1 *)
0x180011d5a  mov     rax, [rsp+48h+arg_28]
0x180011d5f  mov     rdx, rcx
0x180011d62  mov     rcx, [rsp+48h+arg_30]
0x180011d6a  mov     [rsp+48h+var_18], rax
0x180011d6f  mov     eax, [rsp+48h+arg_20]
0x180011d73  mov     [rsp+48h+var_20], 1
0x180011d7b  mov     [rsp+48h+var_28], eax
0x180011d7f  call    ?ReadPolicyRegistry@PolicyHelpers@@SAJPEB_W0KKKW4tagPolicyStore@@PEAUtagEnterprisePolicyValue_V1@@@Z; PolicyHelpers::ReadPolicyRegistry(wchar_t const *,wchar_t const *,ulong,ulong,ulong,tagPolicyStore,tagEnterprisePolicyValue_V1 *)
0x180011d84  add     rsp, 48h
0x180011d88  retn
```
