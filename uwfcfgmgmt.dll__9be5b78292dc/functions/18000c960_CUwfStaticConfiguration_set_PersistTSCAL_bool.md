# CUwfStaticConfiguration::set_PersistTSCAL(bool)

- ea: `0x18000c960`
- end: `0x18000cc36`
- name: `?set_PersistTSCAL@CUwfStaticConfiguration@@QEAAJ_N@Z`
- size: `726`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a110`

## callees

- `0x180001384`
- `0x180002692`
- `0x18000a150`
- `0x18000c960`
- `0x18000cd30`
- `0x180011a30`
- `0x180011b90`
- `0x180011c40`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ca86`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000cc0b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ca86`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000cc0b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c9d4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ca59`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c9d4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ca59`

## string_xrefs

- `0x18000c9b6`: `RegistryExceptionsUWFSpecific`
- `0x18000ca38`: `RegistryExceptionsUWFSpecific`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::set_PersistTSCAL(CUwfStaticConfiguration *this, unsigned __int8 a2)
{
  void *pvData; // rbp
  unsigned int v3; // r12d
  int updated; // ebx
  HKEY *v6; // r13
  HKEY v7; // rcx
  __int64 v8; // rsi
  LSTATUS ValueW; // eax
  __int64 v10; // r15
  signed int v11; // edi
  bool v12; // cc
  __int64 v13; // rax
  int v14; // eax
  _QWORD *v15; // r9
  _WORD *v16; // rcx
  int v17; // r15d
  _DWORD *v18; // rcx
  unsigned int v19; // r9d
  unsigned int v20; // edx
  __int64 v21; // r8
  __int64 v22; // rcx
  DWORD pcbData; // [rsp+80h] [rbp+8h] BYREF
  DWORD pdwType; // [rsp+90h] [rbp+18h] BYREF

  pvData = 0;
  v3 = a2;
  if ( *((_BYTE *)this + 9) )
  {
    updated = -2147024891;
LABEL_39:
    *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = updated;
    return (unsigned int)updated;
  }
  pdwType = 0;
  v6 = (HKEY *)((char *)this + 16);
  v7 = (HKEY)*((_QWORD *)this + 2);
  pcbData = 0;
  v8 = 0;
  ValueW = RegGetValueW(v7, 0, L"RegistryExceptionsUWFSpecific", 0x20u, &pdwType, 0, &pcbData);
  v10 = -1;
  updated = -2147024882;
  v11 = ValueW;
  v12 = ValueW <= 0;
  if ( ValueW )
    goto LABEL_4;
  pvData = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
  if ( !pvData )
  {
    v11 = -2147024882;
    goto LABEL_11;
  }
  ValueW = RegGetValueW(*v6, 0, L"RegistryExceptionsUWFSpecific", 0x20u, &pdwType, pvData, &pcbData);
  v11 = ValueW;
  v12 = ValueW <= 0;
  if ( ValueW )
  {
LABEL_4:
    if ( !v12 )
      v11 = (unsigned __int16)ValueW | 0x80070000;
  }
  else
  {
    v8 = MultiSzAlloc(pvData);
    v11 = -2147024882;
    if ( v8 )
      v11 = 0;
  }
LABEL_11:
  operator delete[](pvData);
  if ( v11 < 0 )
  {
    updated = v11;
    goto LABEL_36;
  }
  if ( (_BYTE)v3 )
  {
    if ( (int)MultiSzFind((wchar_t *)L"HKLM\\Software\\Microsoft\\MSLicensing") < 0 )
    {
      v13 = MultiSzReAlloc(v8, L"HKLM\\Software\\Microsoft\\MSLicensing");
      if ( !v13 )
        goto LABEL_36;
      v8 = v13;
    }
    goto LABEL_32;
  }
  pcbData = 0;
  if ( !v8 )
  {
    updated = -2147467261;
    goto LABEL_39;
  }
  v14 = MultiSzFind((wchar_t *)L"HKLM\\Software\\Microsoft\\MSLicensing");
  updated = v14;
  if ( v14 >= 0 )
  {
    v15 = *(_QWORD **)(v8 + 16);
    v16 = (_WORD *)v15[pcbData];
    do
      ++v10;
    while ( v16[v10] );
    v17 = v10 + 1;
    if ( pcbData == *(_DWORD *)(v8 + 24) - 1 )
    {
      *v16 = 0;
      v18 = (_DWORD *)(v8 + 8);
    }
    else
    {
      memmove_0(
        v16,
        (const void *)v15[pcbData + 1],
        2LL * (*(_DWORD *)(v8 + 8) - (unsigned int)(((__int64)v16 - *v15) >> 1) - v17));
      v19 = 1;
      v20 = 0;
      **(_QWORD **)(v8 + 16) = *(_QWORD *)v8;
      if ( *(_DWORD *)(v8 + 8) )
      {
        do
        {
          v18 = (_DWORD *)(v8 + 8);
          if ( v19 >= *(_DWORD *)(v8 + 24) - 1 )
            break;
          v21 = v20 + 1;
          if ( !*(_WORD *)(*(_QWORD *)v8 + 2LL * v20) )
          {
            v22 = v19++;
            *(_QWORD *)(*(_QWORD *)(v8 + 16) + 8 * v22) = *(_QWORD *)v8 + 2 * v21;
          }
          ++v20;
          v18 = (_DWORD *)(v8 + 8);
        }
        while ( (unsigned int)v21 < *(_DWORD *)(v8 + 8) );
      }
      else
      {
        v18 = (_DWORD *)(v8 + 8);
      }
    }
    --*(_DWORD *)(v8 + 24);
    *v18 -= v17;
    goto LABEL_32;
  }
  if ( v14 == -2147023728 )
  {
LABEL_32:
    updated = CUwfStaticConfiguration::set_RegKeyExclusionsUWFSpecific(this, (struct _MULTISZ *)v8);
    if ( updated >= 0 )
    {
      updated = CUwfConfiguration::UpdateDWORDValue(
                  *((CUwfConfiguration **)this + 4),
                  (struct CUwfRegKey *)v6,
                  L"TSCALPersisted",
                  v3,
                  1);
      if ( updated >= 0 )
        updated = 0;
    }
LABEL_36:
    if ( !v8 )
      goto LABEL_38;
  }
  operator delete[]((void *)v8);
LABEL_38:
  if ( updated < 0 )
    goto LABEL_39;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000c960  mov     [rsp+arg_8], rbx
0x18000c965  push    rbp
0x18000c966  push    rsi
0x18000c967  push    rdi
0x18000c968  push    r12
0x18000c96a  push    r13
0x18000c96c  push    r14
0x18000c96e  push    r15
0x18000c970  sub     rsp, 40h
0x18000c974  xor     ebp, ebp
0x18000c976  movzx   r12d, dl
0x18000c97a  mov     r14, rcx
0x18000c97d  cmp     [rcx+9], bpl
0x18000c981  jz      short loc_18000C98D
0x18000c983  mov     ebx, 80070005h
0x18000c988  jmp     loc_18000CC15
0x18000c98d  lea     rax, [rsp+78h+arg_0]
0x18000c995  mov     [rsp+78h+arg_10], ebp
0x18000c99c  mov     [rsp+78h+pcbData], rax; pcbData
0x18000c9a1  lea     r13, [rcx+10h]
0x18000c9a5  mov     rcx, [r13+0]; hkey
0x18000c9a9  lea     rax, [rsp+78h+arg_10]
0x18000c9b1  mov     [rsp+78h+pvData], rbp; pvData
0x18000c9b6  lea     r8, aRegistryexcept; "RegistryExceptionsUWFSpecific"
0x18000c9bd  mov     r9d, 20h ; ' '; dwFlags
0x18000c9c3  mov     [rsp+78h+pdwType], rax; pdwType
0x18000c9c8  xor     edx, edx; lpSubKey
0x18000c9ca  mov     [rsp+78h+arg_0], ebp
0x18000c9d1  mov     rsi, rbp
0x18000c9d4  call    cs:__imp_RegGetValueW
0x18000c9da  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000c9de  mov     ebx, 8007000Eh
0x18000c9e3  mov     edi, eax
0x18000c9e5  test    eax, eax
0x18000c9e7  jz      short loc_18000C9FD
0x18000c9e9  jle     loc_18000CA83
0x18000c9ef  movzx   edi, ax
0x18000c9f2  or      edi, 80070000h
0x18000c9f8  jmp     loc_18000CA83
0x18000c9fd  mov     ecx, [rsp+78h+arg_0]
0x18000ca04  mov     eax, 2
0x18000ca09  shr     rcx, 1
0x18000ca0c  mul     rcx
0x18000ca0f  cmovb   rax, r15
0x18000ca13  mov     rcx, rax; unsigned __int64
0x18000ca16  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ca1b  mov     rbp, rax
0x18000ca1e  test    rax, rax
0x18000ca21  jnz     short loc_18000CA27
0x18000ca23  mov     edi, ebx
0x18000ca25  jmp     short loc_18000CA83
0x18000ca27  mov     rcx, [r13+0]; hkey
0x18000ca2b  lea     rax, [rsp+78h+arg_0]
0x18000ca33  mov     [rsp+78h+pcbData], rax; pcbData
0x18000ca38  lea     r8, aRegistryexcept; "RegistryExceptionsUWFSpecific"
0x18000ca3f  lea     rax, [rsp+78h+arg_10]
0x18000ca47  mov     [rsp+78h+pvData], rbp; pvData
0x18000ca4c  mov     r9d, 20h ; ' '; dwFlags
0x18000ca52  mov     [rsp+78h+pdwType], rax; pdwType
0x18000ca57  xor     edx, edx; lpSubKey
0x18000ca59  call    cs:__imp_RegGetValueW
0x18000ca5f  mov     edi, eax
0x18000ca61  test    eax, eax
0x18000ca63  jnz     short loc_18000C9E9
0x18000ca65  mov     edx, [rsp+78h+arg_0]
0x18000ca6c  mov     rcx, rbp; Src
0x18000ca6f  shr     edx, 1
0x18000ca71  call    MultiSzAlloc
0x18000ca76  mov     rsi, rax
0x18000ca79  mov     edi, ebx
0x18000ca7b  xor     eax, eax
0x18000ca7d  test    rsi, rsi
0x18000ca80  cmovnz  edi, eax
0x18000ca83  mov     rcx, rbp
0x18000ca86  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ca8c  xor     ebp, ebp
0x18000ca8e  test    edi, edi
0x18000ca90  js      loc_18000CC01
0x18000ca96  lea     edi, [rbp+1]
0x18000ca99  test    r12b, r12b
0x18000ca9c  jz      short loc_18000CADB
0x18000ca9e  xor     r9d, r9d
0x18000caa1  lea     rcx, aHklmSoftwareMi; "HKLM\\Software\\Microsoft\\MSLicensing"
0x18000caa8  xor     r8d, r8d
0x18000caab  mov     rdx, rsi
0x18000caae  call    MultiSzFind
0x18000cab3  test    eax, eax
0x18000cab5  jns     loc_18000CBCB
0x18000cabb  lea     rdx, aHklmSoftwareMi; "HKLM\\Software\\Microsoft\\MSLicensing"
0x18000cac2  mov     rcx, rsi
0x18000cac5  call    MultiSzReAlloc
0x18000caca  test    rax, rax
0x18000cacd  jz      loc_18000CC03
0x18000cad3  mov     rsi, rax
0x18000cad6  jmp     loc_18000CBCB
0x18000cadb  mov     [rsp+78h+arg_0], ebp
0x18000cae2  test    rsi, rsi
0x18000cae5  jnz     short loc_18000CAF1
0x18000cae7  mov     ebx, 80004003h
0x18000caec  jmp     loc_18000CC15
0x18000caf1  lea     r9, [rsp+78h+arg_0]
0x18000caf9  xor     r8d, r8d
0x18000cafc  mov     rdx, rsi
0x18000caff  lea     rcx, aHklmSoftwareMi; "HKLM\\Software\\Microsoft\\MSLicensing"
0x18000cb06  call    MultiSzFind
0x18000cb0b  mov     ebx, eax
0x18000cb0d  test    eax, eax
0x18000cb0f  js      loc_18000CBC4
0x18000cb15  mov     r9, [rsi+10h]
0x18000cb19  mov     edx, [rsp+78h+arg_0]
0x18000cb20  mov     rcx, [r9+rdx*8]; void *
0x18000cb24  inc     r15
0x18000cb27  cmp     [rcx+r15*2], bp
0x18000cb2c  jnz     short loc_18000CB24
0x18000cb2e  mov     eax, [rsi+18h]
0x18000cb31  inc     r15d
0x18000cb34  sub     eax, edi
0x18000cb36  cmp     edx, eax
0x18000cb38  jnz     short loc_18000CB43
0x18000cb3a  mov     [rcx], bp
0x18000cb3d  lea     rcx, [rsi+8]
0x18000cb41  jmp     short loc_18000CBBC
0x18000cb43  mov     r8, rcx
0x18000cb46  lea     rbx, [rsi+8]
0x18000cb4a  sub     r8, [r9]
0x18000cb4d  mov     eax, [rbx]
0x18000cb4f  sar     r8, 1
0x18000cb52  sub     eax, r8d
0x18000cb55  sub     eax, r15d
0x18000cb58  mov     r8d, eax
0x18000cb5b  lea     eax, [rdx+1]
0x18000cb5e  add     r8, r8; Size
0x18000cb61  mov     rdx, [r9+rax*8]; Src
0x18000cb65  call    memmove_0
0x18000cb6a  mov     rcx, [rsi+10h]
0x18000cb6e  mov     r9d, edi
0x18000cb71  mov     rax, [rsi]
0x18000cb74  mov     edx, ebp
0x18000cb76  mov     [rcx], rax
0x18000cb79  cmp     [rbx], ebp
0x18000cb7b  jbe     short loc_18000CBB9
0x18000cb7d  mov     eax, [rsi+18h]
0x18000cb80  mov     rcx, rbx
0x18000cb83  sub     eax, edi
0x18000cb85  cmp     r9d, eax
0x18000cb88  jnb     short loc_18000CBBC
0x18000cb8a  mov     r10, [rsi]
0x18000cb8d  lea     r8d, [rdx+1]
0x18000cb91  mov     ecx, edx
0x18000cb93  cmp     bp, [r10+rcx*2]
0x18000cb98  jnz     short loc_18000CBAC
0x18000cb9a  mov     rax, [rsi+10h]
0x18000cb9e  lea     rdx, [r10+r8*2]
0x18000cba2  mov     ecx, r9d
0x18000cba5  add     r9d, edi
0x18000cba8  mov     [rax+rcx*8], rdx
0x18000cbac  mov     edx, r8d
0x18000cbaf  mov     rcx, rbx
0x18000cbb2  cmp     edx, [rsi+8]
0x18000cbb5  jb      short loc_18000CB7D
0x18000cbb7  jmp     short loc_18000CBBC
0x18000cbb9  mov     rcx, rbx
0x18000cbbc  dec     dword ptr [rsi+18h]
0x18000cbbf  sub     [rcx], r15d
0x18000cbc2  jmp     short loc_18000CBCB
0x18000cbc4  cmp     eax, 80070490h
0x18000cbc9  jnz     short loc_18000CC08
0x18000cbcb  mov     rdx, rsi; struct _MULTISZ *
0x18000cbce  mov     rcx, r14; this
0x18000cbd1  call    ?set_RegKeyExclusionsUWFSpecific@CUwfStaticConfiguration@@QEAAJPEAU_MULTISZ@@@Z; CUwfStaticConfiguration::set_RegKeyExclusionsUWFSpecific(_MULTISZ *)
0x18000cbd6  mov     ebx, eax
0x18000cbd8  test    eax, eax
0x18000cbda  js      short loc_18000CC03
0x18000cbdc  mov     rcx, [r14+20h]; this
0x18000cbe0  lea     r8, aTscalpersisted; "TSCALPersisted"
0x18000cbe7  mov     r9d, r12d; unsigned int
0x18000cbea  mov     byte ptr [rsp+78h+pdwType], dil; bool
0x18000cbef  mov     rdx, r13; struct CUwfRegKey *
0x18000cbf2  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000cbf7  mov     ebx, eax
0x18000cbf9  test    eax, eax
0x18000cbfb  js      short loc_18000CC03
0x18000cbfd  mov     ebx, ebp
0x18000cbff  jmp     short loc_18000CC03
0x18000cc01  mov     ebx, edi
0x18000cc03  test    rsi, rsi
0x18000cc06  jz      short loc_18000CC11
0x18000cc08  mov     rcx, rsi
0x18000cc0b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000cc11  test    ebx, ebx
0x18000cc13  jns     short loc_18000CC1C
0x18000cc15  mov     rax, [r14+20h]
0x18000cc19  mov     [rax+10h], ebx
0x18000cc1c  mov     eax, ebx
0x18000cc1e  mov     rbx, [rsp+78h+arg_8]
0x18000cc26  add     rsp, 40h
0x18000cc2a  pop     r15
0x18000cc2c  pop     r14
0x18000cc2e  pop     r13
0x18000cc30  pop     r12
0x18000cc32  pop     rdi
0x18000cc33  pop     rsi
0x18000cc34  pop     rbp
0x18000cc35  retn
```
