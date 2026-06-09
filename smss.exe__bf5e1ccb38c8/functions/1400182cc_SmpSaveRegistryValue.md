# SmpSaveRegistryValue

- ea: `0x1400182cc`
- end: `0x140018347`
- name: `SmpSaveRegistryValue`
- size: `123`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140013340`
- `0x140013470`
- `0x1400134e0`
- `0x140013540`
- `0x140013570`
- `0x1400135c0`
- `0x1400137b0`
- `0x140013950`

## callees

- `0x140007e50`
- `0x1400182cc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1400182f7`
- `ntdll!RtlInitUnicodeString` at `0x14001830a`
- `ntdll!RtlInitUnicodeString` at `0x1400182f7`
- `ntdll!RtlInitUnicodeString` at `0x14001830a`

## pseudocode

```c
__int64 __fastcall SmpSaveRegistryValue(
        struct _UNICODE_STRING **a1,
        const WCHAR *a2,
        const WCHAR *a3,
        char a4,
        struct _UNICODE_STRING **a5)
{
  struct _UNICODE_STRING *p_DestinationString; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  UNICODE_STRING v11; // [rsp+40h] [rbp-18h] BYREF

  v11 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&v11, a2);
  if ( a3 )
  {
    RtlInitUnicodeString(&DestinationString, a3);
    p_DestinationString = &DestinationString;
  }
  else
  {
    p_DestinationString = 0;
  }
  return SmpSaveRegistryValue_U(a1, &v11, p_DestinationString, a4, a5);
}

```

## disassembly

```asm
0x1400182cc  mov     rax, rsp
0x1400182cf  mov     [rax+8], rbx
0x1400182d3  mov     [rax+10h], rsi
0x1400182d7  push    rdi
0x1400182d8  sub     rsp, 50h
0x1400182dc  mov     rsi, rcx
0x1400182df  xorps   xmm0, xmm0
0x1400182e2  xorps   xmm1, xmm1
0x1400182e5  lea     rcx, [rax-18h]; DestinationString
0x1400182e9  movups  xmmword ptr [rax-18h], xmm0
0x1400182ed  mov     edi, r9d
0x1400182f0  mov     rbx, r8
0x1400182f3  movups  xmmword ptr [rax-28h], xmm1
0x1400182f7  call    cs:__imp_RtlInitUnicodeString
0x1400182fd  test    rbx, rbx
0x140018300  jz      short loc_140018317
0x140018302  mov     rdx, rbx; SourceString
0x140018305  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14001830a  call    cs:__imp_RtlInitUnicodeString
0x140018310  lea     r8, [rsp+58h+DestinationString]
0x140018315  jmp     short loc_14001831A
0x140018317  xor     r8d, r8d
0x14001831a  mov     rax, [rsp+58h+arg_20]
0x140018322  lea     rdx, [rsp+58h+var_18]
0x140018327  mov     r9d, edi
0x14001832a  mov     [rsp+58h+var_38], rax
0x14001832f  mov     rcx, rsi
0x140018332  call    SmpSaveRegistryValue_U
0x140018337  mov     rbx, [rsp+58h+arg_0]
0x14001833c  mov     rsi, [rsp+58h+arg_8]
0x140018341  add     rsp, 50h
0x140018345  pop     rdi
0x140018346  retn
```
