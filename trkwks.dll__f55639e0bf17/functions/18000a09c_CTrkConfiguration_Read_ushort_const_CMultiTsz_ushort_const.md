# CTrkConfiguration::Read(ushort const *,CMultiTsz *,ushort const *)

- ea: `0x18000a09c`
- end: `0x18000a126`
- name: `?Read@CTrkConfiguration@@IEBAXPEBGPEAVCMultiTsz@@0@Z`
- size: `138`
- prototype: `void __fastcall(CTrkConfiguration *this, const unsigned __int16 *, struct CMultiTsz *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800020a4`
- `0x180003b8c`

## callees

- `0x180009640`
- `0x18000a09c`
- `0x180010fca`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a0e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a0e4`

## pseudocode

```c
void __fastcall CTrkConfiguration::Read(
        CTrkConfiguration *this,
        const unsigned __int16 *a2,
        struct CMultiTsz *a3,
        const unsigned __int16 *a4)
{
  bool v4; // zf
  size_t *v6; // r8
  size_t v7; // [rsp+20h] [rbp-18h]
  DWORD v8; // [rsp+40h] [rbp+8h] BYREF
  const unsigned __int16 *v9; // [rsp+58h] [rbp+20h] BYREF

  v9 = a4;
  v4 = *((_QWORD *)this + 1) == 0;
  v8 = 260;
  LODWORD(v9) = 0;
  if ( v4
    || (*((_DWORD *)a3 + 130) = 0, RegQueryValueExW(*((HKEY *)this + 1), a2, 0, (LPDWORD)&v9, (LPBYTE)a3, &v8))
    || (_DWORD)v9 != 1 && (_DWORD)v9 != 7 )
  {
    memset_0(a3, 0, 0x208u);
    StringCopyWorkerW((STRSAFE_LPWSTR)a3, 0x104u, v6, &word_180015AD0, v7);
  }
}

```

## disassembly

```asm
0x18000a09c  mov     r11, rsp
0x18000a09f  mov     [r11+20h], r9
0x18000a0a3  push    rbx
0x18000a0a4  sub     rsp, 30h
0x18000a0a8  cmp     qword ptr [rcx+8], 0
0x18000a0ad  mov     rbx, r8
0x18000a0b0  mov     [rsp+38h+arg_0], 104h
0x18000a0b8  mov     dword ptr [rsp+38h+arg_18], 0
0x18000a0c0  jz      short loc_18000A0FC
0x18000a0c2  mov     dword ptr [r8+208h], 0
0x18000a0cd  lea     rax, [r11+8]
0x18000a0d1  mov     rcx, [rcx+8]; hKey
0x18000a0d5  lea     r9, [r11+20h]; lpType
0x18000a0d9  mov     [r11-10h], rax
0x18000a0dd  xor     r8d, r8d; lpReserved
0x18000a0e0  mov     [r11-18h], rbx
0x18000a0e4  call    cs:__imp_RegQueryValueExW
0x18000a0ea  test    eax, eax
0x18000a0ec  jnz     short loc_18000A0FC
0x18000a0ee  cmp     dword ptr [rsp+38h+arg_18], 1
0x18000a0f3  jz      short loc_18000A120
0x18000a0f5  cmp     dword ptr [rsp+38h+arg_18], 7
0x18000a0fa  jz      short loc_18000A120
0x18000a0fc  xor     edx, edx; Val
0x18000a0fe  mov     r8d, 208h; Size
0x18000a104  mov     rcx, rbx; void *
0x18000a107  call    memset_0
0x18000a10c  lea     r9, word_180015AD0; pszSrc
0x18000a113  mov     edx, 104h; cchDest
0x18000a118  mov     rcx, rbx; pszDest
0x18000a11b  call    StringCopyWorkerW
0x18000a120  add     rsp, 30h
0x18000a124  pop     rbx
0x18000a125  retn
```
