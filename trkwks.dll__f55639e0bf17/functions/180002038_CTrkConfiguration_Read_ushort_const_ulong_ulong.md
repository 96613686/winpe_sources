# CTrkConfiguration::Read(ushort const *,ulong *,ulong)

- ea: `0x180002038`
- end: `0x18000209b`
- name: `?Read@CTrkConfiguration@@IEBAXPEBGPEAKK@Z`
- size: `99`
- prototype: `void __fastcall(CTrkConfiguration *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180001e28`
- `0x1800020a4`

## callees

- `0x180002038`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000207e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000207e`

## pseudocode

```c
void __fastcall CTrkConfiguration::Read(
        CTrkConfiguration *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int a4)
{
  HKEY v5; // rcx
  unsigned int v6; // [rsp+40h] [rbp+8h] BYREF
  DWORD v7; // [rsp+50h] [rbp+18h] BYREF
  DWORD v8; // [rsp+58h] [rbp+20h] BYREF

  *a3 = a4;
  v5 = (HKEY)*((_QWORD *)this + 1);
  if ( v5 )
  {
    v8 = 0;
    v6 = 0;
    v7 = 4;
    if ( !RegQueryValueExW(v5, a2, 0, &v8, (LPBYTE)&v6, &v7) && v8 == 4 )
      *a3 = v6;
  }
}

```

## disassembly

```asm
0x180002038  mov     r11, rsp
0x18000203b  push    rbx
0x18000203c  sub     rsp, 30h
0x180002040  mov     [r8], r9d
0x180002043  mov     rbx, r8
0x180002046  mov     rcx, [rcx+8]; hKey
0x18000204a  test    rcx, rcx
0x18000204d  jz      short loc_180002095
0x18000204f  lea     rax, [r11+18h]
0x180002053  mov     [rsp+38h+arg_18], 0
0x18000205b  mov     [r11-10h], rax
0x18000205f  lea     r9, [r11+20h]; lpType
0x180002063  lea     rax, [r11+8]
0x180002067  mov     [rsp+38h+arg_0], 0
0x18000206f  xor     r8d, r8d; lpReserved
0x180002072  mov     [r11-18h], rax
0x180002076  mov     [rsp+38h+arg_10], 4
0x18000207e  call    cs:__imp_RegQueryValueExW
0x180002084  test    eax, eax
0x180002086  jnz     short loc_180002095
0x180002088  cmp     [rsp+38h+arg_18], 4
0x18000208d  jnz     short loc_180002095
0x18000208f  mov     eax, [rsp+38h+arg_0]
0x180002093  mov     [rbx], eax
0x180002095  add     rsp, 30h
0x180002099  pop     rbx
0x18000209a  retn
```
