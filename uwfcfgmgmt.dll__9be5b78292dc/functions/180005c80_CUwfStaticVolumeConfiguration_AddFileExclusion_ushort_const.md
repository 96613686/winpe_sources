# CUwfStaticVolumeConfiguration::AddFileExclusion(ushort const *)

- ea: `0x180005c80`
- end: `0x180005ef8`
- name: `?AddFileExclusion@CUwfStaticVolumeConfiguration@@QEAAJPEBG@Z`
- size: `632`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180017d50`

## callees

- `0x180001384`
- `0x180005c80`
- `0x1800079a0`
- `0x18000d370`
- `0x18000e320`
- `0x18000e4d0`
- `0x18000f52c`
- `0x1800105a8`
- `0x180011a30`
- `0x180011b90`
- `0x180011c40`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180005e13`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005eba`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005ec3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005ecd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005e13`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005eba`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005ec3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005ecd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005d55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005ddb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005d55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005ddb`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::AddFileExclusion(
        CUwfStaticVolumeConfiguration *this,
        unsigned __int16 *a2)
{
  struct _MULTISZ *v2; // rsi
  unsigned __int16 *v3; // r12
  int v6; // ebx
  HKEY *v7; // r15
  const unsigned __int16 *v8; // rdx
  HKEY v9; // rcx
  LSTATUS ValueW; // eax
  signed int v11; // edi
  void *v12; // rcx
  LSTATUS v13; // eax
  __int64 v14; // rax
  unsigned __int16 *v16; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *pcbData; // [rsp+90h] [rbp+40h] BYREF
  DWORD pdwType; // [rsp+A0h] [rbp+50h] BYREF
  void *Src; // [rsp+A8h] [rbp+58h]

  v2 = 0;
  v3 = 0;
  pcbData = 0;
  v16 = 0;
  if ( *((_BYTE *)this + 9) )
  {
    v6 = -2147024891;
    goto LABEL_32;
  }
  if ( !a2 )
  {
    v6 = -2147467261;
    goto LABEL_32;
  }
  if ( !IsValidPathName(a2) )
    goto LABEL_6;
  v7 = (HKEY *)((char *)this + 16);
  v6 = CUwfRegKey::QuerySzValue((CUwfStaticVolumeConfiguration *)((char *)this + 16), L"VolumeName", &pcbData);
  if ( v6 < 0 )
  {
    v3 = pcbData;
    goto LABEL_32;
  }
  CUwfRegKey::QuerySzValue((CUwfStaticVolumeConfiguration *)((char *)this + 16), L"DriveLetter", &v16);
  v3 = pcbData;
  if ( !FilePathCanBeExcluded(pcbData, v8, a2) )
  {
LABEL_6:
    v6 = -2147024809;
    goto LABEL_32;
  }
  v9 = *v7;
  pdwType = 0;
  LODWORD(pcbData) = 0;
  ValueW = RegGetValueW(v9, 0, L"FileExceptionsUserDefined", 0x20u, &pdwType, 0, (LPDWORD)&pcbData);
  v11 = ValueW;
  v6 = -2147024882;
  if ( ValueW )
  {
    v12 = 0;
    if ( ValueW > 0 )
      v11 = (unsigned __int16)ValueW | 0x80070000;
  }
  else
  {
    Src = operator new[](saturated_mul((unsigned __int64)(unsigned int)pcbData >> 1, 2u));
    if ( Src )
    {
      v13 = RegGetValueW(*v7, 0, L"FileExceptionsUserDefined", 0x20u, &pdwType, Src, (LPDWORD)&pcbData);
      v11 = v13;
      if ( v13 )
      {
        if ( v13 > 0 )
          v11 = (unsigned __int16)v13 | 0x80070000;
      }
      else
      {
        v2 = (struct _MULTISZ *)MultiSzAlloc(Src);
        v11 = -2147024882;
        if ( v2 )
          v11 = 0;
      }
      v12 = Src;
    }
    else
    {
      v11 = -2147024882;
      v12 = 0;
    }
  }
  operator delete[](v12);
  if ( v11 == -2147024893 )
  {
    v2 = (struct _MULTISZ *)MultiSzAlloc(&dword_18001FAA4);
    if ( !v2 )
      goto LABEL_32;
  }
  else if ( v11 < 0 )
  {
    v6 = v11;
    goto LABEL_32;
  }
  if ( (int)MultiSzFind(a2) >= 0 )
  {
    v6 = 0;
  }
  else
  {
    v14 = MultiSzReAlloc(v2, a2);
    if ( v14 )
    {
      v2 = (struct _MULTISZ *)v14;
      v6 = CUwfConfiguration::FixupUpdatedSettings(*((CUwfConfiguration **)this + 3));
      if ( v6 >= 0 )
      {
        v6 = CUwfRegKey::SetMultiSzValue(
               (CUwfStaticVolumeConfiguration *)((char *)this + 16),
               L"FileExceptionsUserDefined",
               v2);
        if ( v6 >= 0 )
          v6 = CUwfRegKey::AddDWORDValue(
                 (CUwfStaticVolumeConfiguration *)((char *)this + 16),
                 L"NumFileExceptionsUserDefined",
                 1u);
      }
    }
  }
LABEL_32:
  operator delete[](v2);
  operator delete[](v3);
  operator delete[](v16);
  if ( v6 < 0 )
    *(_DWORD *)(*((_QWORD *)this + 3) + 16LL) = v6;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005c80  mov     [rsp-38h+arg_8], rbx
0x180005c85  push    rbp
0x180005c86  push    rsi
0x180005c87  push    rdi
0x180005c88  push    r12
0x180005c8a  push    r13
0x180005c8c  push    r14
0x180005c8e  push    r15
0x180005c90  mov     rbp, rsp
0x180005c93  sub     rsp, 50h
0x180005c97  xor     esi, esi
0x180005c99  xor     r12d, r12d
0x180005c9c  mov     r14, rdx
0x180005c9f  mov     r13, rcx
0x180005ca2  mov     [rbp+arg_0], r12
0x180005ca6  mov     [rbp+var_10], rsi
0x180005caa  cmp     [rcx+9], sil
0x180005cae  jz      short loc_180005CBA
0x180005cb0  mov     ebx, 80070005h
0x180005cb5  jmp     loc_180005EB7
0x180005cba  test    r14, r14
0x180005cbd  jnz     short loc_180005CC9
0x180005cbf  mov     ebx, 80004003h
0x180005cc4  jmp     loc_180005EB7
0x180005cc9  mov     rcx, r14; unsigned __int16 *
0x180005ccc  call    ?IsValidPathName@@YA_NPEBG@Z; IsValidPathName(ushort const *)
0x180005cd1  test    al, al
0x180005cd3  jnz     short loc_180005CDF
0x180005cd5  mov     ebx, 80070057h
0x180005cda  jmp     loc_180005EB7
0x180005cdf  lea     r15, [r13+10h]
0x180005ce3  mov     rcx, r15; this
0x180005ce6  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x180005cea  lea     rdx, aVolumename; "VolumeName"
0x180005cf1  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x180005cf6  mov     ebx, eax
0x180005cf8  test    eax, eax
0x180005cfa  js      loc_180005EB3
0x180005d00  lea     r8, [rbp+var_10]; unsigned __int16 **
0x180005d04  mov     rcx, r15; this
0x180005d07  lea     rdx, aDriveletter; "DriveLetter"
0x180005d0e  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x180005d13  mov     r12, [rbp+arg_0]
0x180005d17  mov     r8, r14; unsigned __int16 *
0x180005d1a  mov     rcx, r12; unsigned __int16 *
0x180005d1d  call    ?FilePathCanBeExcluded@@YA_NPEBG00@Z; FilePathCanBeExcluded(ushort const *,ushort const *,ushort const *)
0x180005d22  test    al, al
0x180005d24  jz      short loc_180005CD5
0x180005d26  mov     rcx, [r15]; hkey
0x180005d29  lea     rax, [rbp+arg_0]
0x180005d2d  mov     [rsp+50h+pcbData], rax; pcbData
0x180005d32  lea     r8, Value; "FileExceptionsUserDefined"
0x180005d39  lea     rax, [rbp+arg_10]
0x180005d3d  mov     [rsp+50h+pvData], rsi; pvData
0x180005d42  mov     r9d, 20h ; ' '; dwFlags
0x180005d48  mov     [rsp+50h+pdwType], rax; pdwType
0x180005d4d  xor     edx, edx; lpSubKey
0x180005d4f  mov     [rbp+arg_10], esi
0x180005d52  mov     dword ptr [rbp+arg_0], esi
0x180005d55  call    cs:__imp_RegGetValueW
0x180005d5b  mov     edi, eax
0x180005d5d  mov     ebx, 8007000Eh
0x180005d62  test    eax, eax
0x180005d64  jz      short loc_180005D7E
0x180005d66  xor     ecx, ecx
0x180005d68  test    eax, eax
0x180005d6a  jle     loc_180005E13
0x180005d70  movzx   edi, ax
0x180005d73  or      edi, 80070000h
0x180005d79  jmp     loc_180005E13
0x180005d7e  mov     ecx, dword ptr [rbp+arg_0]
0x180005d81  mov     eax, 2
0x180005d86  shr     rcx, 1
0x180005d89  mul     rcx
0x180005d8c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005d93  cmovb   rax, rcx
0x180005d97  mov     rcx, rax; unsigned __int64
0x180005d9a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005d9f  mov     [rbp+Src], rax
0x180005da3  mov     rdi, rax
0x180005da6  test    rax, rax
0x180005da9  jnz     short loc_180005DB2
0x180005dab  mov     edi, ebx
0x180005dad  mov     rcx, rax
0x180005db0  jmp     short loc_180005E13
0x180005db2  mov     rcx, [r15]; hkey
0x180005db5  lea     rax, [rbp+arg_0]
0x180005db9  mov     [rsp+50h+pcbData], rax; pcbData
0x180005dbe  lea     r8, Value; "FileExceptionsUserDefined"
0x180005dc5  lea     rax, [rbp+arg_10]
0x180005dc9  mov     [rsp+50h+pvData], rdi; pvData
0x180005dce  mov     r9d, 20h ; ' '; dwFlags
0x180005dd4  mov     [rsp+50h+pdwType], rax; pdwType
0x180005dd9  xor     edx, edx; lpSubKey
0x180005ddb  call    cs:__imp_RegGetValueW
0x180005de1  mov     edi, eax
0x180005de3  test    eax, eax
0x180005de5  jz      short loc_180005DF4
0x180005de7  jle     short loc_180005E0F
0x180005de9  movzx   edi, ax
0x180005dec  or      edi, 80070000h
0x180005df2  jmp     short loc_180005E0F
0x180005df4  mov     edx, dword ptr [rbp+arg_0]
0x180005df7  mov     rcx, [rbp+Src]; Src
0x180005dfb  shr     edx, 1
0x180005dfd  call    MultiSzAlloc
0x180005e02  mov     rsi, rax
0x180005e05  mov     edi, ebx
0x180005e07  xor     eax, eax
0x180005e09  test    rsi, rsi
0x180005e0c  cmovnz  edi, eax
0x180005e0f  mov     rcx, [rbp+Src]
0x180005e13  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005e19  cmp     edi, 80070003h
0x180005e1f  jnz     short loc_180005E3C
0x180005e21  mov     edx, 2
0x180005e26  lea     rcx, dword_18001FAA4; Src
0x180005e2d  call    MultiSzAlloc
0x180005e32  mov     rsi, rax
0x180005e35  test    rax, rax
0x180005e38  jnz     short loc_180005E40
0x180005e3a  jmp     short loc_180005EB7
0x180005e3c  test    edi, edi
0x180005e3e  js      short loc_180005EAF
0x180005e40  xor     r9d, r9d
0x180005e43  xor     r8d, r8d
0x180005e46  mov     rdx, rsi
0x180005e49  mov     rcx, r14; String2
0x180005e4c  call    MultiSzFind
0x180005e51  test    eax, eax
0x180005e53  jns     short loc_180005EAB
0x180005e55  mov     rdx, r14
0x180005e58  mov     rcx, rsi
0x180005e5b  call    MultiSzReAlloc
0x180005e60  mov     rdi, rax
0x180005e63  test    rax, rax
0x180005e66  jz      short loc_180005EB7
0x180005e68  mov     rsi, rax
0x180005e6b  mov     rcx, [r13+18h]; this
0x180005e6f  call    ?FixupUpdatedSettings@CUwfConfiguration@@QEAAJXZ; CUwfConfiguration::FixupUpdatedSettings(void)
0x180005e74  mov     ebx, eax
0x180005e76  test    eax, eax
0x180005e78  js      short loc_180005EB7
0x180005e7a  mov     r8, rsi; struct _MULTISZ *
0x180005e7d  lea     rdx, Value; "FileExceptionsUserDefined"
0x180005e84  mov     rcx, r15; this
0x180005e87  call    ?SetMultiSzValue@CUwfRegKey@@QEAAJPEBGQEAU_MULTISZ@@@Z; CUwfRegKey::SetMultiSzValue(ushort const *,_MULTISZ * const)
0x180005e8c  mov     ebx, eax
0x180005e8e  test    eax, eax
0x180005e90  js      short loc_180005EB7
0x180005e92  mov     r8d, 1; unsigned int
0x180005e98  lea     rdx, aNumfileexcepti; "NumFileExceptionsUserDefined"
0x180005e9f  mov     rcx, r15; this
0x180005ea2  call    ?AddDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::AddDWORDValue(ushort const *,ulong)
0x180005ea7  mov     ebx, eax
0x180005ea9  jmp     short loc_180005EB7
0x180005eab  xor     ebx, ebx
0x180005ead  jmp     short loc_180005EB7
0x180005eaf  mov     ebx, edi
0x180005eb1  jmp     short loc_180005EB7
0x180005eb3  mov     r12, [rbp+arg_0]
0x180005eb7  mov     rcx, rsi
0x180005eba  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005ec0  mov     rcx, r12
0x180005ec3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005ec9  mov     rcx, [rbp+var_10]
0x180005ecd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005ed3  test    ebx, ebx
0x180005ed5  jns     short loc_180005EDE
0x180005ed7  mov     rax, [r13+18h]
0x180005edb  mov     [rax+10h], ebx
0x180005ede  mov     eax, ebx
0x180005ee0  mov     rbx, [rsp+50h+arg_8]
0x180005ee8  add     rsp, 50h
0x180005eec  pop     r15
0x180005eee  pop     r14
0x180005ef0  pop     r13
0x180005ef2  pop     r12
0x180005ef4  pop     rdi
0x180005ef5  pop     rsi
0x180005ef6  pop     rbp
0x180005ef7  retn
```
