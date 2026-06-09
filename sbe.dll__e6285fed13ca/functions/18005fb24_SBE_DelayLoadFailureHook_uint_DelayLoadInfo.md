# SBE_DelayLoadFailureHook(uint,DelayLoadInfo *)

- ea: `0x18005fb24`
- end: `0x18005fb8c`
- name: `?SBE_DelayLoadFailureHook@@YAP6A_JXZIPEAUDelayLoadInfo@@@Z`
- size: `104`
- prototype: `__int64 (*__fastcall(unsigned int, struct DelayLoadInfo *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b2fc0`

## callees

- `0x18005fb24`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x18005fb50`
- `KERNEL32!CompareStringA` at `0x18005fb7e`
- `KERNEL32!CompareStringA` at `0x18005fb50`
- `KERNEL32!CompareStringA` at `0x18005fb7e`

## string_xrefs

- `0x18005fb2e`: `wmvcore.dll`
- `0x18005fb5f`: `sbeio.dll`

## pseudocode

```c
__int64 (*__fastcall SBE_DelayLoadFailureHook(__int64 a1, struct DelayLoadInfo *a2))(void)
{
  if ( CompareStringA(0x7Fu, 1u, a2->szDll, -1, "wmvcore.dll", -1) != 2 )
    CompareStringA(0x7Fu, 1u, a2->szDll, -1, "sbeio.dll", -1);
  return 0;
}

```

## disassembly

```asm
0x18005fb24  push    rbx
0x18005fb26  sub     rsp, 30h
0x18005fb2a  mov     r8, [rdx+18h]; lpString1
0x18005fb2e  lea     rax, aWmvcoreDll_0; "wmvcore.dll"
0x18005fb35  or      r9d, 0FFFFFFFFh; cchCount1
0x18005fb39  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005fb41  mov     rbx, rdx
0x18005fb44  mov     [rsp+38h+lpString2], rax; lpString2
0x18005fb49  lea     edx, [r9+2]; dwCmpFlags
0x18005fb4d  lea     ecx, [rdx+7Eh]; Locale
0x18005fb50  call    cs:__imp_CompareStringA
0x18005fb56  cmp     eax, 2
0x18005fb59  jz      short loc_18005FB84
0x18005fb5b  mov     r8, [rbx+18h]; lpString1
0x18005fb5f  lea     rax, aSbeioDll_0; "sbeio.dll"
0x18005fb66  or      r9d, 0FFFFFFFFh; cchCount1
0x18005fb6a  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005fb72  mov     [rsp+38h+lpString2], rax; lpString2
0x18005fb77  lea     edx, [r9+2]; dwCmpFlags
0x18005fb7b  lea     ecx, [rdx+7Eh]; Locale
0x18005fb7e  call    cs:__imp_CompareStringA
0x18005fb84  xor     eax, eax
0x18005fb86  add     rsp, 30h
0x18005fb8a  pop     rbx
0x18005fb8b  retn
```
