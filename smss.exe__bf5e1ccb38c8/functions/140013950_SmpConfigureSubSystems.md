# SmpConfigureSubSystems

- ea: `0x140013950`
- end: `0x140013a13`
- name: `SmpConfigureSubSystems`
- size: `195`
- prototype: `__int64 __usercall@<rax>(wchar_t *Str1@<rcx>, int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x140013950`
- `0x1400182cc`

## import_xrefs

- `ntdll!_wcsicmp` at `0x140013978`
- `ntdll!_wcsicmp` at `0x1400139c4`
- `ntdll!_wcsicmp` at `0x1400139d8`
- `ntdll!_wcsicmp` at `0x140013978`
- `ntdll!_wcsicmp` at `0x1400139c4`
- `ntdll!_wcsicmp` at `0x1400139d8`

## pseudocode

```c
__int64 __fastcall SmpConfigureSubSystems(wchar_t *Str1, int a2, const WCHAR *a3, int a4, int a5, __int64 a6)
{
  int v6; // edi

  v6 = 0;
  if ( a2 != 7 )
  {
    if ( _wcsicmp(Str1, L"Kmode") )
    {
      if ( _wcsicmp(Str1, L"Required") && _wcsicmp(Str1, L"Optional") )
        return (unsigned int)SmpSaveRegistryValue((struct _UNICODE_STRING **)(a6 + 8), Str1, a3, 1, 0);
    }
    else if ( (unsigned int)(a2 - 1) <= 1 )
    {
      v6 = SmpSaveRegistryValue((struct _UNICODE_STRING **)(a6 + 24), a3, 0, 1, 0);
      if ( v6 >= 0 )
      {
        ++*(_DWORD *)a6;
        *(_DWORD *)(a6 + 4) += a4 + 2;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140013950  push    rbx
0x140013952  push    rbp
0x140013953  push    rsi
0x140013954  push    rdi
0x140013955  push    r14
0x140013957  sub     rsp, 30h
0x14001395b  xor     edi, edi
0x14001395d  mov     ebp, r9d
0x140013960  mov     r14, r8
0x140013963  mov     esi, edx
0x140013965  mov     rbx, rcx
0x140013968  cmp     edx, 7
0x14001396b  jz      loc_140013A06
0x140013971  lea     rdx, aKmode; "Kmode"
0x140013978  call    cs:__imp__wcsicmp
0x14001397e  test    eax, eax
0x140013980  jnz     short loc_1400139BA
0x140013982  lea     eax, [rsi-1]
0x140013985  cmp     eax, 1
0x140013988  ja      short loc_140013A06
0x14001398a  mov     rbx, [rsp+58h+arg_28]
0x140013992  lea     r9d, [rdi+1]
0x140013996  xor     r8d, r8d
0x140013999  mov     [rsp+58h+var_38], rdi
0x14001399e  mov     rdx, r14
0x1400139a1  lea     rcx, [rbx+18h]
0x1400139a5  call    SmpSaveRegistryValue
0x1400139aa  mov     edi, eax
0x1400139ac  test    eax, eax
0x1400139ae  js      short loc_140013A06
0x1400139b0  inc     dword ptr [rbx]
0x1400139b2  lea     ecx, [rbp+2]
0x1400139b5  add     [rbx+4], ecx
0x1400139b8  jmp     short loc_140013A06
0x1400139ba  lea     rdx, aRequired; "Required"
0x1400139c1  mov     rcx, rbx; Str1
0x1400139c4  call    cs:__imp__wcsicmp
0x1400139ca  test    eax, eax
0x1400139cc  jz      short loc_140013A06
0x1400139ce  lea     rdx, aOptional; "Optional"
0x1400139d5  mov     rcx, rbx; Str1
0x1400139d8  call    cs:__imp__wcsicmp
0x1400139de  test    eax, eax
0x1400139e0  jz      short loc_140013A06
0x1400139e2  mov     rcx, [rsp+58h+arg_28]
0x1400139ea  mov     r9d, 1
0x1400139f0  add     rcx, 8
0x1400139f4  mov     [rsp+58h+var_38], rdi
0x1400139f9  mov     r8, r14
0x1400139fc  mov     rdx, rbx
0x1400139ff  call    SmpSaveRegistryValue
0x140013a04  mov     edi, eax
0x140013a06  mov     eax, edi
0x140013a08  add     rsp, 30h
0x140013a0c  pop     r14
0x140013a0e  pop     rdi
0x140013a0f  pop     rsi
0x140013a10  pop     rbp
0x140013a11  pop     rbx
0x140013a12  retn
```
