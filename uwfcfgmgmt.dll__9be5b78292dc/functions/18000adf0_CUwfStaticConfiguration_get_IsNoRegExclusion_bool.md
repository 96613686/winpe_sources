# CUwfStaticConfiguration::get_IsNoRegExclusion(bool *)

- ea: `0x18000adf0`
- end: `0x18000ae42`
- name: `?get_IsNoRegExclusion@CUwfStaticConfiguration@@QEAAJPEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x18000adf0`
- `0x18000e170`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ae2f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ae2f`

## string_xrefs

- `0x18000ae06`: `RegistryExceptionsUserDefined`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::get_IsNoRegExclusion(CUwfStaticConfiguration *this, bool *a2)
{
  int v3; // ebx
  struct _MULTISZ *v4; // rcx
  struct _MULTISZ *v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  v3 = CUwfRegKey::QueryMultiSzValue(
         (CUwfStaticConfiguration *)((char *)this + 16),
         L"RegistryExceptionsUserDefined",
         &v6);
  v4 = v6;
  if ( v3 >= 0 )
    *a2 = *((_DWORD *)v6 + 6) == 0;
  operator delete[](v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000adf0  mov     [rsp+arg_0], rbx
0x18000adf5  push    rdi
0x18000adf6  sub     rsp, 20h
0x18000adfa  mov     rdi, rdx
0x18000adfd  mov     [rsp+28h+arg_10], 0
0x18000ae06  lea     rdx, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x18000ae0d  add     rcx, 10h; this
0x18000ae11  lea     r8, [rsp+28h+arg_10]; struct _MULTISZ **
0x18000ae16  call    ?QueryMultiSzValue@CUwfRegKey@@QEAAJPEBGPEAPEAU_MULTISZ@@@Z; CUwfRegKey::QueryMultiSzValue(ushort const *,_MULTISZ * *)
0x18000ae1b  mov     ebx, eax
0x18000ae1d  mov     rcx, [rsp+28h+arg_10]
0x18000ae22  test    eax, eax
0x18000ae24  js      short loc_18000AE2F
0x18000ae26  cmp     dword ptr [rcx+18h], 0
0x18000ae2a  setz    dl
0x18000ae2d  mov     [rdi], dl
0x18000ae2f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ae35  mov     eax, ebx
0x18000ae37  mov     rbx, [rsp+28h+arg_0]
0x18000ae3c  add     rsp, 20h
0x18000ae40  pop     rdi
0x18000ae41  retn
```
