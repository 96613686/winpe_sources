# CUwfStaticVolumeConfiguration::RemoveFileExclusion(ushort const *)

- ea: `0x180008da0`
- end: `0x180008f4d`
- name: `?RemoveFileExclusion@CUwfStaticVolumeConfiguration@@QEAAJPEBG@Z`
- size: `429`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180019690`

## callees

- `0x180001384`
- `0x1800079a0`
- `0x180008da0`
- `0x18000d370`
- `0x18000e4d0`
- `0x180011a30`
- `0x180011d20`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180008ec4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008f29`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008ec4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008f29`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008e14`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008e97`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008e14`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008e97`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::RemoveFileExclusion(
        CUwfStaticVolumeConfiguration *this,
        const unsigned __int16 *a2)
{
  struct _MULTISZ *v2; // rsi
  int v5; // ebx
  HKEY *v6; // r15
  HKEY v7; // rcx
  LSTATUS ValueW; // eax
  void *pvData; // rbp
  bool v10; // cc
  int v11; // eax
  DWORD pcbData; // [rsp+78h] [rbp+10h] BYREF
  DWORD pdwType; // [rsp+80h] [rbp+18h] BYREF

  v2 = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    goto LABEL_21;
  }
  if ( *((_BYTE *)this + 9) )
  {
    v5 = -2147024891;
    goto LABEL_21;
  }
  pdwType = 0;
  v6 = (HKEY *)((char *)this + 16);
  v7 = (HKEY)*((_QWORD *)this + 2);
  pcbData = 0;
  ValueW = RegGetValueW(v7, 0, L"FileExceptionsUserDefined", 0x20u, &pdwType, 0, &pcbData);
  v5 = ValueW;
  if ( ValueW )
  {
    pvData = 0;
    v10 = ValueW <= 0;
LABEL_7:
    if ( !v10 )
      v5 = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_14;
  }
  pvData = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
  if ( pvData )
  {
    ValueW = RegGetValueW(*v6, 0, L"FileExceptionsUserDefined", 0x20u, &pdwType, pvData, &pcbData);
    v5 = ValueW;
    v10 = ValueW <= 0;
    if ( !ValueW )
    {
      v2 = (struct _MULTISZ *)MultiSzAlloc(pvData);
      v5 = -2147024882;
      if ( v2 )
        v5 = 0;
      goto LABEL_14;
    }
    goto LABEL_7;
  }
  v5 = -2147024882;
LABEL_14:
  operator delete[](pvData);
  if ( v5 >= 0 )
  {
    v11 = MultiSzRemove(a2, v2);
    v5 = v11;
    if ( v11 == -2147023728 )
    {
      v5 = 0;
    }
    else if ( v11 >= 0 )
    {
      v5 = CUwfConfiguration::FixupUpdatedSettings(*((CUwfConfiguration **)this + 3));
      if ( v5 >= 0 )
      {
        v5 = CUwfRegKey::SetMultiSzValue((CUwfRegKey *)v6, L"FileExceptionsUserDefined", v2);
        if ( v5 >= 0 )
          v5 = CUwfRegKey::AddDWORDValue((CUwfRegKey *)v6, L"NumFileExceptionsUserDefined", 0xFFFFFFFF);
      }
    }
  }
LABEL_21:
  operator delete[](v2);
  if ( v5 < 0 )
    *(_DWORD *)(*((_QWORD *)this + 3) + 16LL) = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008da0  mov     [rsp+arg_0], rbx
0x180008da5  push    rbp
0x180008da6  push    rsi
0x180008da7  push    rdi
0x180008da8  push    r14
0x180008daa  push    r15
0x180008dac  sub     rsp, 40h
0x180008db0  xor     esi, esi
0x180008db2  mov     r14, rdx
0x180008db5  mov     rdi, rcx
0x180008db8  test    rdx, rdx
0x180008dbb  jnz     short loc_180008DC7
0x180008dbd  mov     ebx, 80004003h
0x180008dc2  jmp     loc_180008F26
0x180008dc7  cmp     [rcx+9], sil
0x180008dcb  jz      short loc_180008DD7
0x180008dcd  mov     ebx, 80070005h
0x180008dd2  jmp     loc_180008F26
0x180008dd7  lea     rax, [rsp+68h+arg_8]
0x180008ddc  mov     [rsp+68h+arg_10], esi
0x180008de3  mov     [rsp+68h+pcbData], rax; pcbData
0x180008de8  lea     r15, [rcx+10h]
0x180008dec  mov     rcx, [r15]; hkey
0x180008def  lea     rax, [rsp+68h+arg_10]
0x180008df7  mov     [rsp+68h+pvData], rsi; pvData
0x180008dfc  lea     r8, Value; "FileExceptionsUserDefined"
0x180008e03  mov     r9d, 20h ; ' '; dwFlags
0x180008e09  mov     [rsp+68h+pdwType], rax; pdwType
0x180008e0e  xor     edx, edx; lpSubKey
0x180008e10  mov     [rsp+68h+arg_8], esi
0x180008e14  call    cs:__imp_RegGetValueW
0x180008e1a  mov     ebx, eax
0x180008e1c  test    eax, eax
0x180008e1e  jz      short loc_180008E38
0x180008e20  xor     ebp, ebp
0x180008e22  test    eax, eax
0x180008e24  jle     loc_180008EC1
0x180008e2a  movzx   ebx, ax
0x180008e2d  or      ebx, 80070000h
0x180008e33  jmp     loc_180008EC1
0x180008e38  mov     ecx, [rsp+68h+arg_8]
0x180008e3c  mov     eax, 2
0x180008e41  shr     rcx, 1
0x180008e44  mul     rcx
0x180008e47  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180008e4e  cmovb   rax, rcx
0x180008e52  mov     rcx, rax; unsigned __int64
0x180008e55  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008e5a  mov     rbp, rax
0x180008e5d  test    rax, rax
0x180008e60  jnz     short loc_180008E69
0x180008e62  mov     ebx, 8007000Eh
0x180008e67  jmp     short loc_180008EC1
0x180008e69  mov     rcx, [r15]; hkey
0x180008e6c  lea     rax, [rsp+68h+arg_8]
0x180008e71  mov     [rsp+68h+pcbData], rax; pcbData
0x180008e76  lea     r8, Value; "FileExceptionsUserDefined"
0x180008e7d  lea     rax, [rsp+68h+arg_10]
0x180008e85  mov     [rsp+68h+pvData], rbp; pvData
0x180008e8a  mov     r9d, 20h ; ' '; dwFlags
0x180008e90  mov     [rsp+68h+pdwType], rax; pdwType
0x180008e95  xor     edx, edx; lpSubKey
0x180008e97  call    cs:__imp_RegGetValueW
0x180008e9d  mov     ebx, eax
0x180008e9f  test    eax, eax
0x180008ea1  jnz     short loc_180008E24
0x180008ea3  mov     edx, [rsp+68h+arg_8]
0x180008ea7  mov     rcx, rbp; Src
0x180008eaa  shr     edx, 1
0x180008eac  call    MultiSzAlloc
0x180008eb1  mov     rsi, rax
0x180008eb4  mov     ebx, 8007000Eh
0x180008eb9  xor     eax, eax
0x180008ebb  test    rsi, rsi
0x180008ebe  cmovnz  ebx, eax
0x180008ec1  mov     rcx, rbp
0x180008ec4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008eca  test    ebx, ebx
0x180008ecc  js      short loc_180008F26
0x180008ece  mov     rdx, rsi
0x180008ed1  mov     rcx, r14
0x180008ed4  call    MultiSzRemove
0x180008ed9  mov     ebx, eax
0x180008edb  cmp     eax, 80070490h
0x180008ee0  jnz     short loc_180008EE6
0x180008ee2  xor     ebx, ebx
0x180008ee4  jmp     short loc_180008F26
0x180008ee6  test    eax, eax
0x180008ee8  js      short loc_180008F26
0x180008eea  mov     rcx, [rdi+18h]; this
0x180008eee  call    ?FixupUpdatedSettings@CUwfConfiguration@@QEAAJXZ; CUwfConfiguration::FixupUpdatedSettings(void)
0x180008ef3  mov     ebx, eax
0x180008ef5  test    eax, eax
0x180008ef7  js      short loc_180008F26
0x180008ef9  mov     r8, rsi; struct _MULTISZ *
0x180008efc  lea     rdx, Value; "FileExceptionsUserDefined"
0x180008f03  mov     rcx, r15; this
0x180008f06  call    ?SetMultiSzValue@CUwfRegKey@@QEAAJPEBGQEAU_MULTISZ@@@Z; CUwfRegKey::SetMultiSzValue(ushort const *,_MULTISZ * const)
0x180008f0b  mov     ebx, eax
0x180008f0d  test    eax, eax
0x180008f0f  js      short loc_180008F26
0x180008f11  or      r8d, 0FFFFFFFFh; unsigned int
0x180008f15  lea     rdx, aNumfileexcepti; "NumFileExceptionsUserDefined"
0x180008f1c  mov     rcx, r15; this
0x180008f1f  call    ?AddDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::AddDWORDValue(ushort const *,ulong)
0x180008f24  mov     ebx, eax
0x180008f26  mov     rcx, rsi
0x180008f29  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008f2f  test    ebx, ebx
0x180008f31  jns     short loc_180008F3A
0x180008f33  mov     rax, [rdi+18h]
0x180008f37  mov     [rax+10h], ebx
0x180008f3a  mov     eax, ebx
0x180008f3c  mov     rbx, [rsp+68h+arg_0]
0x180008f41  add     rsp, 40h
0x180008f45  pop     r15
0x180008f47  pop     r14
0x180008f49  pop     rdi
0x180008f4a  pop     rsi
0x180008f4b  pop     rbp
0x180008f4c  retn
```
