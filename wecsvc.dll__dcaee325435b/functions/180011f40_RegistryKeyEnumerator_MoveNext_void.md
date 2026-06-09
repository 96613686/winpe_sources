# RegistryKeyEnumerator::MoveNext(void)

- ea: `0x180011f40`
- end: `0x180011fd0`
- name: `?MoveNext@RegistryKeyEnumerator@@QEAAKXZ`
- size: `144`
- prototype: `LSTATUS __fastcall(RegistryKeyEnumerator *this)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d15c`
- `0x1800155e8`
- `0x180015f78`
- `0x180016380`
- `0x180016450`
- `0x18001764c`
- `0x18001ab58`
- `0x18001b998`
- `0x1800225fa`

## callees

- `0x180010800`
- `0x180011f40`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180011fa7`
- `ADVAPI32!RegEnumKeyExW` at `0x180011fa7`

## pseudocode

```c
LSTATUS __fastcall RegistryKeyEnumerator::MoveNext(RegistryKeyEnumerator *this)
{
  WCHAR **v1; // rdi
  WCHAR *v3; // rdi
  DWORD v4; // edx
  HKEY v5; // rcx
  LSTATUS result; // eax
  DWORD cchName; // [rsp+50h] [rbp+8h] BYREF

  v1 = (WCHAR **)((char *)this + 16);
  if ( (__int64)(*((_QWORD *)this + 4) - *((_QWORD *)this + 2)) >> 1 < (unsigned __int64)*((unsigned int *)this + 13) )
    std::vector<unsigned short>::_Reallocate((char *)this + 16);
  v3 = *v1;
  v4 = *((_DWORD *)this + 2);
  v5 = *(HKEY *)this;
  cchName = *((_DWORD *)this + 13);
  result = RegEnumKeyExW(v5, v4, v3, &cchName, 0, 0, 0, 0);
  if ( result == 259 )
    return 259;
  if ( !result )
  {
    ++*((_DWORD *)this + 2);
    *((_QWORD *)this + 5) = v3;
  }
  return result;
}

```

## disassembly

```asm
0x180011f40  mov     [rsp+arg_8], rbx
0x180011f45  push    rdi
0x180011f46  sub     rsp, 40h
0x180011f4a  mov     edx, [rcx+34h]
0x180011f4d  lea     rdi, [rcx+10h]
0x180011f51  mov     rax, [rdi+10h]
0x180011f55  mov     rbx, rcx
0x180011f58  sub     rax, [rdi]
0x180011f5b  sar     rax, 1
0x180011f5e  cmp     rax, rdx
0x180011f61  jnb     short loc_180011F6B
0x180011f63  mov     rcx, rdi
0x180011f66  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x180011f6b  mov     rdi, [rdi]
0x180011f6e  lea     r9, [rsp+48h+cchName]; lpcchName
0x180011f73  mov     eax, [rbx+34h]
0x180011f76  mov     r8, rdi; lpName
0x180011f79  mov     edx, [rbx+8]; dwIndex
0x180011f7c  mov     rcx, [rbx]; hKey
0x180011f7f  mov     [rsp+48h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180011f88  mov     [rsp+48h+lpcchClass], 0; lpcchClass
0x180011f91  mov     [rsp+48h+lpClass], 0; lpClass
0x180011f9a  mov     [rsp+48h+lpReserved], 0; lpReserved
0x180011fa3  mov     [rsp+48h+cchName], eax
0x180011fa7  call    cs:__imp_RegEnumKeyExW
0x180011fad  mov     ecx, 103h
0x180011fb2  cmp     eax, ecx
0x180011fb4  jnz     short loc_180011FBA
0x180011fb6  mov     eax, ecx
0x180011fb8  jmp     short loc_180011FC5
0x180011fba  test    eax, eax
0x180011fbc  jnz     short loc_180011FC5
0x180011fbe  inc     dword ptr [rbx+8]
0x180011fc1  mov     [rbx+28h], rdi
0x180011fc5  mov     rbx, [rsp+48h+arg_8]
0x180011fca  add     rsp, 40h
0x180011fce  pop     rdi
0x180011fcf  retn
```
