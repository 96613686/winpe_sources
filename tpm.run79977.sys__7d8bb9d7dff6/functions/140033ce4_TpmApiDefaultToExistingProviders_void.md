# TpmApiDefaultToExistingProviders(void)

- ea: `0x140033ce4`
- end: `0x140033d6e`
- name: `?TpmApiDefaultToExistingProviders@@YAEXZ`
- size: `138`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140033d74`

## callees

- `0x140033ce4`
- `0x140033f68`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140033d0b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033d23`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033d0b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033d23`

## string_xrefs

- `0x140033cf8`: `\Registry\Machine\System\CurrentControlSet\Control\BitLocker`

## pseudocode

```c
bool TpmApiDefaultToExistingProviders(void)
{
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING v2; // [rsp+40h] [rbp-18h] BYREF
  int v3; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v4; // [rsp+68h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&v2, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\BitLocker");
  RtlInitUnicodeString(&DestinationString, L"DefaultToExistingProviders");
  v4 = 4;
  return (int)TpmApiRegistryGetValue(&v2, &DestinationString, 4, &v3, &v4) < 0 || v3 != 0;
}

```

## disassembly

```asm
0x140033ce4  mov     rax, rsp
0x140033ce7  sub     rsp, 58h
0x140033ceb  xorps   xmm0, xmm0
0x140033cee  mov     dword ptr [rax+8], 0
0x140033cf5  xorps   xmm1, xmm1
0x140033cf8  lea     rdx, aRegistryMachin_21; "\\Registry\\Machine\\System\\CurrentCon"...
0x140033cff  lea     rcx, [rax-18h]; DestinationString
0x140033d03  movups  xmmword ptr [rax-18h], xmm0
0x140033d07  movups  xmmword ptr [rax-28h], xmm1
0x140033d0b  call    cs:__imp_RtlInitUnicodeString
0x140033d12  nop     dword ptr [rax+rax+00h]
0x140033d17  lea     rdx, aDefaulttoexist; "DefaultToExistingProviders"
0x140033d1e  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140033d23  call    cs:__imp_RtlInitUnicodeString
0x140033d2a  nop     dword ptr [rax+rax+00h]
0x140033d2f  mov     r8d, 4; unsigned int
0x140033d35  lea     rax, [rsp+58h+arg_8]
0x140033d3a  lea     r9, [rsp+58h+arg_0]; void *
0x140033d3f  mov     [rsp+58h+arg_8], r8d
0x140033d44  lea     rdx, [rsp+58h+DestinationString]; struct _UNICODE_STRING *
0x140033d49  mov     [rsp+58h+var_38], rax; unsigned int *
0x140033d4e  lea     rcx, [rsp+58h+var_18]; struct _UNICODE_STRING *
0x140033d53  call    ?TpmApiRegistryGetValue@@YAJPEAU_UNICODE_STRING@@0KPEAXPEAK@Z; TpmApiRegistryGetValue(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *,ulong *)
0x140033d58  test    eax, eax
0x140033d5a  jns     short loc_140033D60
0x140033d5c  mov     al, 1
0x140033d5e  jmp     short loc_140033D68
0x140033d60  cmp     [rsp+58h+arg_0], 0
0x140033d65  setnz   al
0x140033d68  add     rsp, 58h
0x140033d6c  retn
```
