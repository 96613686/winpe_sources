# SsGetDefaultSdFromRegistry

- ea: `0x1800259f0`
- end: `0x180025aa8`
- name: `SsGetDefaultSdFromRegistry`
- size: `184`
- prototype: `char __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000aa8c`
- `0x1800275a0`

## callees

- `0x18001e80c`
- `0x1800259f0`

## import_xrefs

- `ntdll!RtlQueryRegistryValuesEx` at `0x180025a7c`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180025a7c`

## string_xrefs

- `0x180025a3d`: `LanmanServer\DefaultSecurity`

## pseudocode

```c
char __fastcall SsGetDefaultSdFromRegistry(__int64 a1, _QWORD *a2)
{
  void *v5; // [rsp+30h] [rbp-69h] BYREF
  int v6; // [rsp+38h] [rbp-61h]
  __int64 v7; // [rsp+40h] [rbp-59h]
  __int64 v8; // [rsp+48h] [rbp-51h]
  int v9; // [rsp+50h] [rbp-49h]
  __int64 v10; // [rsp+68h] [rbp-31h]
  int v11; // [rsp+70h] [rbp-29h]
  __int64 v12; // [rsp+78h] [rbp-21h]
  _BYTE v13[72]; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v14; // [rsp+E8h] [rbp+4Fh]

  memset_0(v13, 0, 0x50u);
  *a2 = 0;
  v5 = &GetSdFromRegistry;
  v6 = 4;
  v7 = a1;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  if ( (int)RtlQueryRegistryValuesEx(2147483649LL, L"LanmanServer\\DefaultSecurity", &v5, v13, 0) < 0 )
    return 0;
  *a2 = v14;
  return 1;
}

```

## disassembly

```asm
0x1800259f0  mov     [rsp-8+arg_0], rbx
0x1800259f5  mov     [rsp-8+arg_8], rdi
0x1800259fa  push    rbp
0x1800259fb  lea     rbp, [rsp-57h]
0x180025a00  sub     rsp, 0F0h
0x180025a07  mov     rdi, rdx
0x180025a0a  mov     rbx, rcx
0x180025a0d  xor     edx, edx; Val
0x180025a0f  lea     rcx, [rbp+57h+var_50]; void *
0x180025a13  lea     r8d, [rdx+50h]; Size
0x180025a17  call    memset_0
0x180025a1c  lea     rax, GetSdFromRegistry
0x180025a23  mov     qword ptr [rdi], 0
0x180025a2a  lea     r9, [rbp+57h+var_50]
0x180025a2e  mov     [rbp+57h+var_C0], rax
0x180025a32  lea     r8, [rbp+57h+var_C0]
0x180025a36  mov     [rbp+57h+var_B8], 4
0x180025a3d  lea     rdx, aLanmanserverDe; "LanmanServer\\DefaultSecurity"
0x180025a44  mov     [rbp+57h+var_B0], rbx
0x180025a48  mov     ecx, 80000001h
0x180025a4d  mov     [rbp+57h+var_A8], 0
0x180025a55  mov     [rbp+57h+var_A0], 0
0x180025a5c  mov     [rbp+57h+var_88], 0
0x180025a64  mov     [rbp+57h+var_80], 0
0x180025a6b  mov     [rbp+57h+var_78], 0
0x180025a73  mov     [rsp+0F0h+var_D0], 0
0x180025a7c  call    cs:__imp_RtlQueryRegistryValuesEx
0x180025a82  test    eax, eax
0x180025a84  js      short loc_180025A91
0x180025a86  mov     rax, [rbp+57h+var_8]
0x180025a8a  mov     [rdi], rax
0x180025a8d  mov     al, 1
0x180025a8f  jmp     short loc_180025A93
0x180025a91  xor     al, al
0x180025a93  lea     r11, [rsp+0F0h+var_s0]
0x180025a9b  mov     rbx, [r11+10h]
0x180025a9f  mov     rdi, [r11+18h]
0x180025aa3  mov     rsp, r11
0x180025aa6  pop     rbp
0x180025aa7  retn
```
