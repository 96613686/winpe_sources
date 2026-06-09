# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180081ef8`
- end: `0x180081f4a`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `82`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180081f50`
- `0x180082158`

## callees

- `0x180081674`
- `0x180081ef8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081f24`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081f24`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY a2, const unsigned __int16 *a3, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = 0;
  v5 = RegOpenKeyExW(HKEY_CURRENT_USER, a3, 0, a4, &v7);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = v7;
  }
  return v5;
}

```

## disassembly

```asm
0x180081ef8  mov     rax, rsp
0x180081efb  mov     [rax+10h], rdx
0x180081eff  push    rbx
0x180081f00  sub     rsp, 30h
0x180081f04  mov     rbx, rcx
0x180081f07  mov     qword ptr [rax+10h], 0
0x180081f0f  lea     rcx, [rax+10h]
0x180081f13  mov     rdx, r8; lpSubKey
0x180081f16  mov     [rax-18h], rcx
0x180081f1a  xor     r8d, r8d; ulOptions
0x180081f1d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180081f24  call    cs:__imp_RegOpenKeyExW
0x180081f2a  mov     edx, eax
0x180081f2c  test    eax, eax
0x180081f2e  jnz     short loc_180081F42
0x180081f30  mov     rcx, rbx; this
0x180081f33  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180081f38  mov     edx, eax
0x180081f3a  mov     rax, [rsp+38h+arg_8]
0x180081f3f  mov     [rbx], rax
0x180081f42  mov     eax, edx
0x180081f44  add     rsp, 30h
0x180081f48  pop     rbx
0x180081f49  retn
```
