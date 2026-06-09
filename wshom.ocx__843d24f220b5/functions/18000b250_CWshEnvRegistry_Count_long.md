# CWshEnvRegistry::Count(long *)

- ea: `0x18000b250`
- end: `0x18000b2ef`
- name: `?Count@CWshEnvRegistry@@UEAAJPEAJ@Z`
- size: `159`
- prototype: `__int64 __fastcall(CWshEnvRegistry *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000b250`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyA` at `0x18000b2cb`
- `ADVAPI32!RegQueryInfoKeyA` at `0x18000b2cb`

## pseudocode

```c
LSTATUS __fastcall CWshEnvRegistry::Count(CWshEnvRegistry *this, DWORD *a2)
{
  LSTATUS result; // eax
  HKEY v4; // rcx
  DWORD cValues; // [rsp+78h] [rbp+10h] BYREF

  if ( !a2 )
    return -2147467261;
  *a2 = 0;
  v4 = (HKEY)*((_QWORD *)this + 9);
  cValues = 0;
  result = RegQueryInfoKeyA(v4, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    *a2 = cValues;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b250  push    rbx
0x18000b252  sub     rsp, 60h
0x18000b256  mov     rbx, rdx
0x18000b259  test    rdx, rdx
0x18000b25c  jnz     short loc_18000B268
0x18000b25e  mov     eax, 80004003h
0x18000b263  jmp     loc_18000B2E9
0x18000b268  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000b271  lea     rax, [rsp+68h+cValues]
0x18000b276  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18000b27f  xor     r9d, r9d; lpReserved
0x18000b282  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18000b28b  xor     r8d, r8d; lpcchClass
0x18000b28e  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18000b297  mov     [rsp+68h+lpcValues], rax; lpcValues
0x18000b29c  mov     dword ptr [rdx], 0
0x18000b2a2  xor     edx, edx; lpClass
0x18000b2a4  mov     rcx, [rcx+48h]; hKey
0x18000b2a8  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18000b2b1  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18000b2ba  mov     [rsp+68h+lpcSubKeys], 0; lpcSubKeys
0x18000b2c3  mov     [rsp+68h+cValues], 0
0x18000b2cb  call    cs:__imp_RegQueryInfoKeyA
0x18000b2d1  test    eax, eax
0x18000b2d3  jz      short loc_18000B2E1
0x18000b2d5  jle     short loc_18000B2E9
0x18000b2d7  movzx   eax, ax
0x18000b2da  or      eax, 80070000h
0x18000b2df  jmp     short loc_18000B2E9
0x18000b2e1  mov     eax, [rsp+68h+cValues]
0x18000b2e5  mov     [rbx], eax
0x18000b2e7  xor     eax, eax
0x18000b2e9  add     rsp, 60h
0x18000b2ed  pop     rbx
0x18000b2ee  retn
```
