# RegistryKeyEnumerator::MoveNext(void)

- ea: `0x140007d00`
- end: `0x140007d9f`
- name: `?MoveNext@RegistryKeyEnumerator@@QEAAKXZ`
- size: `159`
- prototype: `unsigned int __fastcall(RegistryKeyEnumerator *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000a6a0`
- `0x14000adf0`
- `0x14001e458`
- `0x14002e0cc`

## callees

- `0x140007d00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007d82`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007d82`

## pseudocode

```c
__int64 __fastcall RegistryKeyEnumerator::MoveNext(RegistryKeyEnumerator *this)
{
  int v1; // eax
  unsigned int v3; // edx
  const WCHAR *v4; // rcx
  __int64 v5; // rax
  HKEY v7; // rcx
  DWORD cchName; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 8);
  v3 = 259;
  if ( v1 )
  {
    while ( v3 )
    {
      v7 = *(HKEY *)this;
      *((_DWORD *)this + 8) = v1 - 1;
      cchName = 256;
      v3 = RegEnumKeyExW(v7, v1 - 1, (LPWSTR)this + 20, &cchName, 0, 0, 0, 0);
      v1 = *((_DWORD *)this + 8);
      if ( !v1 )
        goto LABEL_2;
    }
  }
  else
  {
LABEL_2:
    if ( v3 )
    {
      v5 = 0;
      v4 = &ValueName;
      goto LABEL_5;
    }
  }
  v4 = (const WCHAR *)((char *)this + 40);
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
LABEL_5:
  *((_QWORD *)this + 2) = v4;
  *((_QWORD *)this + 3) = v5;
  return v3;
}

```

## disassembly

```asm
0x140007d00  mov     [rsp+arg_8], rbx
0x140007d05  push    rdi
0x140007d06  sub     rsp, 40h
0x140007d0a  mov     eax, [rcx+20h]
0x140007d0d  xor     edi, edi
0x140007d0f  mov     rbx, rcx
0x140007d12  mov     edx, 103h
0x140007d17  test    eax, eax
0x140007d19  jnz     short loc_140007D50
0x140007d1b  test    edx, edx
0x140007d1d  jnz     short loc_140007D93
0x140007d1f  lea     rcx, [rbx+28h]
0x140007d23  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140007d2a  nop     word ptr [rax+rax+00h]
0x140007d30  inc     rax
0x140007d33  cmp     [rcx+rax*2], di
0x140007d37  jnz     short loc_140007D30
0x140007d39  mov     [rbx+10h], rcx
0x140007d3d  mov     [rbx+18h], rax
0x140007d41  mov     eax, edx
0x140007d43  mov     rbx, [rsp+48h+arg_8]
0x140007d48  add     rsp, 40h
0x140007d4c  pop     rdi
0x140007d4d  retn
0x140007d50  test    edx, edx
0x140007d52  jz      short loc_140007D1F
0x140007d54  mov     rcx, [rbx]; hKey
0x140007d57  lea     edx, [rax-1]; dwIndex
0x140007d5a  mov     [rsp+48h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x140007d5f  lea     r8, [rbx+28h]; lpName
0x140007d63  mov     [rsp+48h+lpcchClass], rdi; lpcchClass
0x140007d68  lea     r9, [rsp+48h+cchName]; lpcchName
0x140007d6d  mov     [rsp+48h+lpClass], rdi; lpClass
0x140007d72  mov     [rsp+48h+lpReserved], rdi; lpReserved
0x140007d77  mov     [rbx+20h], edx
0x140007d7a  mov     [rsp+48h+cchName], 100h
0x140007d82  call    cs:__imp_RegEnumKeyExW
0x140007d88  mov     edx, eax
0x140007d8a  mov     eax, [rbx+20h]
0x140007d8d  test    eax, eax
0x140007d8f  jnz     short loc_140007D50
0x140007d91  jmp     short loc_140007D1B
0x140007d93  mov     rax, rdi
0x140007d96  lea     rcx, ValueName
0x140007d9d  jmp     short loc_140007D39
```
