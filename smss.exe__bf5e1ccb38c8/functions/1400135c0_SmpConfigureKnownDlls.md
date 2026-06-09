# SmpConfigureKnownDlls

- ea: `0x1400135c0`
- end: `0x140013623`
- name: `SmpConfigureKnownDlls`
- size: `99`
- prototype: `__int64 __usercall@<rax>(wchar_t *Str1@<rcx>, int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1400135c0`
- `0x1400182cc`

## import_xrefs

- `ntdll!_wcsicmp` at `0x1400135d7`
- `ntdll!_wcsicmp` at `0x1400135eb`
- `ntdll!_wcsicmp` at `0x1400135d7`
- `ntdll!_wcsicmp` at `0x1400135eb`

## string_xrefs

- `0x1400135ca`: `DllDirectory`
- `0x1400135e1`: `DllDirectory32`

## pseudocode

```c
__int64 __fastcall SmpConfigureKnownDlls(wchar_t *Str1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  if ( _wcsicmp(Str1, L"DllDirectory") && _wcsicmp(Str1, L"DllDirectory32") )
    return SmpSaveRegistryValue(a6, Str1, a3, 1, 0);
  else
    return 0;
}

```

## disassembly

```asm
0x1400135c0  mov     [rsp+arg_0], rbx
0x1400135c5  push    rdi
0x1400135c6  sub     rsp, 30h
0x1400135ca  lea     rdx, aDlldirectory; "DllDirectory"
0x1400135d1  mov     rdi, r8
0x1400135d4  mov     rbx, rcx
0x1400135d7  call    cs:__imp__wcsicmp
0x1400135dd  test    eax, eax
0x1400135df  jz      short loc_140013616
0x1400135e1  lea     rdx, aDlldirectory32; "DllDirectory32"
0x1400135e8  mov     rcx, rbx; Str1
0x1400135eb  call    cs:__imp__wcsicmp
0x1400135f1  test    eax, eax
0x1400135f3  jz      short loc_140013616
0x1400135f5  mov     rcx, [rsp+38h+arg_28]
0x1400135fa  mov     r9d, 1
0x140013600  mov     r8, rdi
0x140013603  mov     [rsp+38h+var_18], 0
0x14001360c  mov     rdx, rbx
0x14001360f  call    SmpSaveRegistryValue
0x140013614  jmp     short loc_140013618
0x140013616  xor     eax, eax
0x140013618  mov     rbx, [rsp+38h+arg_0]
0x14001361d  add     rsp, 30h
0x140013621  pop     rdi
0x140013622  retn
```
