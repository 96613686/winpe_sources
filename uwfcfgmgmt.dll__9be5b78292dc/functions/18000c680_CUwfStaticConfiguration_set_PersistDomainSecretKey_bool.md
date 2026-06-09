# CUwfStaticConfiguration::set_PersistDomainSecretKey(bool)

- ea: `0x18000c680`
- end: `0x18000c956`
- name: `?set_PersistDomainSecretKey@CUwfStaticConfiguration@@QEAAJ_N@Z`
- size: `726`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a080`

## callees

- `0x180001384`
- `0x180002692`
- `0x18000a150`
- `0x18000c680`
- `0x18000cd30`
- `0x180011a30`
- `0x180011b90`
- `0x180011c40`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000c7a6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000c92b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000c7a6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000c92b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c6f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c779`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c6f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c779`

## string_xrefs

- `0x18000c7c1`: `HKLM\SECURITY\Policy\Secrets\$MACHINE.ACC`
- `0x18000c7db`: `HKLM\SECURITY\Policy\Secrets\$MACHINE.ACC`
- `0x18000c81f`: `HKLM\SECURITY\Policy\Secrets\$MACHINE.ACC`
- `0x18000c6d6`: `RegistryExceptionsUWFSpecific`
- `0x18000c758`: `RegistryExceptionsUWFSpecific`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::set_PersistDomainSecretKey(
        CUwfStaticConfiguration *this,
        unsigned __int8 a2)
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
    if ( (int)MultiSzFind((wchar_t *)L"HKLM\\SECURITY\\Policy\\Secrets\\$MACHINE.ACC") < 0 )
    {
      v13 = MultiSzReAlloc(v8, L"HKLM\\SECURITY\\Policy\\Secrets\\$MACHINE.ACC");
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
  v14 = MultiSzFind((wchar_t *)L"HKLM\\SECURITY\\Policy\\Secrets\\$MACHINE.ACC");
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
                  L"DomainSecretKeyPersisted",
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
0x18000c680  mov     [rsp+arg_8], rbx
0x18000c685  push    rbp
0x18000c686  push    rsi
0x18000c687  push    rdi
0x18000c688  push    r12
0x18000c68a  push    r13
0x18000c68c  push    r14
0x18000c68e  push    r15
0x18000c690  sub     rsp, 40h
0x18000c694  xor     ebp, ebp
0x18000c696  movzx   r12d, dl
0x18000c69a  mov     r14, rcx
0x18000c69d  cmp     [rcx+9], bpl
0x18000c6a1  jz      short loc_18000C6AD
0x18000c6a3  mov     ebx, 80070005h
0x18000c6a8  jmp     loc_18000C935
0x18000c6ad  lea     rax, [rsp+78h+arg_0]
0x18000c6b5  mov     [rsp+78h+arg_10], ebp
0x18000c6bc  mov     [rsp+78h+pcbData], rax; pcbData
0x18000c6c1  lea     r13, [rcx+10h]
0x18000c6c5  mov     rcx, [r13+0]; hkey
0x18000c6c9  lea     rax, [rsp+78h+arg_10]
0x18000c6d1  mov     [rsp+78h+pvData], rbp; pvData
0x18000c6d6  lea     r8, aRegistryexcept; "RegistryExceptionsUWFSpecific"
0x18000c6dd  mov     r9d, 20h ; ' '; dwFlags
0x18000c6e3  mov     [rsp+78h+pdwType], rax; pdwType
0x18000c6e8  xor     edx, edx; lpSubKey
0x18000c6ea  mov     [rsp+78h+arg_0], ebp
0x18000c6f1  mov     rsi, rbp
0x18000c6f4  call    cs:__imp_RegGetValueW
0x18000c6fa  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000c6fe  mov     ebx, 8007000Eh
0x18000c703  mov     edi, eax
0x18000c705  test    eax, eax
0x18000c707  jz      short loc_18000C71D
0x18000c709  jle     loc_18000C7A3
0x18000c70f  movzx   edi, ax
0x18000c712  or      edi, 80070000h
0x18000c718  jmp     loc_18000C7A3
0x18000c71d  mov     ecx, [rsp+78h+arg_0]
0x18000c724  mov     eax, 2
0x18000c729  shr     rcx, 1
0x18000c72c  mul     rcx
0x18000c72f  cmovb   rax, r15
0x18000c733  mov     rcx, rax; unsigned __int64
0x18000c736  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c73b  mov     rbp, rax
0x18000c73e  test    rax, rax
0x18000c741  jnz     short loc_18000C747
0x18000c743  mov     edi, ebx
0x18000c745  jmp     short loc_18000C7A3
0x18000c747  mov     rcx, [r13+0]; hkey
0x18000c74b  lea     rax, [rsp+78h+arg_0]
0x18000c753  mov     [rsp+78h+pcbData], rax; pcbData
0x18000c758  lea     r8, aRegistryexcept; "RegistryExceptionsUWFSpecific"
0x18000c75f  lea     rax, [rsp+78h+arg_10]
0x18000c767  mov     [rsp+78h+pvData], rbp; pvData
0x18000c76c  mov     r9d, 20h ; ' '; dwFlags
0x18000c772  mov     [rsp+78h+pdwType], rax; pdwType
0x18000c777  xor     edx, edx; lpSubKey
0x18000c779  call    cs:__imp_RegGetValueW
0x18000c77f  mov     edi, eax
0x18000c781  test    eax, eax
0x18000c783  jnz     short loc_18000C709
0x18000c785  mov     edx, [rsp+78h+arg_0]
0x18000c78c  mov     rcx, rbp; Src
0x18000c78f  shr     edx, 1
0x18000c791  call    MultiSzAlloc
0x18000c796  mov     rsi, rax
0x18000c799  mov     edi, ebx
0x18000c79b  xor     eax, eax
0x18000c79d  test    rsi, rsi
0x18000c7a0  cmovnz  edi, eax
0x18000c7a3  mov     rcx, rbp
0x18000c7a6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000c7ac  xor     ebp, ebp
0x18000c7ae  test    edi, edi
0x18000c7b0  js      loc_18000C921
0x18000c7b6  lea     edi, [rbp+1]
0x18000c7b9  test    r12b, r12b
0x18000c7bc  jz      short loc_18000C7FB
0x18000c7be  xor     r9d, r9d
0x18000c7c1  lea     rcx, aHklmSecurityPo; "HKLM\\SECURITY\\Policy\\Secrets\\$MACHI"...
0x18000c7c8  xor     r8d, r8d
0x18000c7cb  mov     rdx, rsi
0x18000c7ce  call    MultiSzFind
0x18000c7d3  test    eax, eax
0x18000c7d5  jns     loc_18000C8EB
0x18000c7db  lea     rdx, aHklmSecurityPo; "HKLM\\SECURITY\\Policy\\Secrets\\$MACHI"...
0x18000c7e2  mov     rcx, rsi
0x18000c7e5  call    MultiSzReAlloc
0x18000c7ea  test    rax, rax
0x18000c7ed  jz      loc_18000C923
0x18000c7f3  mov     rsi, rax
0x18000c7f6  jmp     loc_18000C8EB
0x18000c7fb  mov     [rsp+78h+arg_0], ebp
0x18000c802  test    rsi, rsi
0x18000c805  jnz     short loc_18000C811
0x18000c807  mov     ebx, 80004003h
0x18000c80c  jmp     loc_18000C935
0x18000c811  lea     r9, [rsp+78h+arg_0]
0x18000c819  xor     r8d, r8d
0x18000c81c  mov     rdx, rsi
0x18000c81f  lea     rcx, aHklmSecurityPo; "HKLM\\SECURITY\\Policy\\Secrets\\$MACHI"...
0x18000c826  call    MultiSzFind
0x18000c82b  mov     ebx, eax
0x18000c82d  test    eax, eax
0x18000c82f  js      loc_18000C8E4
0x18000c835  mov     r9, [rsi+10h]
0x18000c839  mov     edx, [rsp+78h+arg_0]
0x18000c840  mov     rcx, [r9+rdx*8]; void *
0x18000c844  inc     r15
0x18000c847  cmp     [rcx+r15*2], bp
0x18000c84c  jnz     short loc_18000C844
0x18000c84e  mov     eax, [rsi+18h]
0x18000c851  inc     r15d
0x18000c854  sub     eax, edi
0x18000c856  cmp     edx, eax
0x18000c858  jnz     short loc_18000C863
0x18000c85a  mov     [rcx], bp
0x18000c85d  lea     rcx, [rsi+8]
0x18000c861  jmp     short loc_18000C8DC
0x18000c863  mov     r8, rcx
0x18000c866  lea     rbx, [rsi+8]
0x18000c86a  sub     r8, [r9]
0x18000c86d  mov     eax, [rbx]
0x18000c86f  sar     r8, 1
0x18000c872  sub     eax, r8d
0x18000c875  sub     eax, r15d
0x18000c878  mov     r8d, eax
0x18000c87b  lea     eax, [rdx+1]
0x18000c87e  add     r8, r8; Size
0x18000c881  mov     rdx, [r9+rax*8]; Src
0x18000c885  call    memmove_0
0x18000c88a  mov     rcx, [rsi+10h]
0x18000c88e  mov     r9d, edi
0x18000c891  mov     rax, [rsi]
0x18000c894  mov     edx, ebp
0x18000c896  mov     [rcx], rax
0x18000c899  cmp     [rbx], ebp
0x18000c89b  jbe     short loc_18000C8D9
0x18000c89d  mov     eax, [rsi+18h]
0x18000c8a0  mov     rcx, rbx
0x18000c8a3  sub     eax, edi
0x18000c8a5  cmp     r9d, eax
0x18000c8a8  jnb     short loc_18000C8DC
0x18000c8aa  mov     r10, [rsi]
0x18000c8ad  lea     r8d, [rdx+1]
0x18000c8b1  mov     ecx, edx
0x18000c8b3  cmp     bp, [r10+rcx*2]
0x18000c8b8  jnz     short loc_18000C8CC
0x18000c8ba  mov     rax, [rsi+10h]
0x18000c8be  lea     rdx, [r10+r8*2]
0x18000c8c2  mov     ecx, r9d
0x18000c8c5  add     r9d, edi
0x18000c8c8  mov     [rax+rcx*8], rdx
0x18000c8cc  mov     edx, r8d
0x18000c8cf  mov     rcx, rbx
0x18000c8d2  cmp     edx, [rsi+8]
0x18000c8d5  jb      short loc_18000C89D
0x18000c8d7  jmp     short loc_18000C8DC
0x18000c8d9  mov     rcx, rbx
0x18000c8dc  dec     dword ptr [rsi+18h]
0x18000c8df  sub     [rcx], r15d
0x18000c8e2  jmp     short loc_18000C8EB
0x18000c8e4  cmp     eax, 80070490h
0x18000c8e9  jnz     short loc_18000C928
0x18000c8eb  mov     rdx, rsi; struct _MULTISZ *
0x18000c8ee  mov     rcx, r14; this
0x18000c8f1  call    ?set_RegKeyExclusionsUWFSpecific@CUwfStaticConfiguration@@QEAAJPEAU_MULTISZ@@@Z; CUwfStaticConfiguration::set_RegKeyExclusionsUWFSpecific(_MULTISZ *)
0x18000c8f6  mov     ebx, eax
0x18000c8f8  test    eax, eax
0x18000c8fa  js      short loc_18000C923
0x18000c8fc  mov     rcx, [r14+20h]; this
0x18000c900  lea     r8, aDomainsecretke; "DomainSecretKeyPersisted"
0x18000c907  mov     r9d, r12d; unsigned int
0x18000c90a  mov     byte ptr [rsp+78h+pdwType], dil; bool
0x18000c90f  mov     rdx, r13; struct CUwfRegKey *
0x18000c912  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000c917  mov     ebx, eax
0x18000c919  test    eax, eax
0x18000c91b  js      short loc_18000C923
0x18000c91d  mov     ebx, ebp
0x18000c91f  jmp     short loc_18000C923
0x18000c921  mov     ebx, edi
0x18000c923  test    rsi, rsi
0x18000c926  jz      short loc_18000C931
0x18000c928  mov     rcx, rsi
0x18000c92b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000c931  test    ebx, ebx
0x18000c933  jns     short loc_18000C93C
0x18000c935  mov     rax, [r14+20h]
0x18000c939  mov     [rax+10h], ebx
0x18000c93c  mov     eax, ebx
0x18000c93e  mov     rbx, [rsp+78h+arg_8]
0x18000c946  add     rsp, 40h
0x18000c94a  pop     r15
0x18000c94c  pop     r14
0x18000c94e  pop     r13
0x18000c950  pop     r12
0x18000c952  pop     rdi
0x18000c953  pop     rsi
0x18000c954  pop     rbp
0x18000c955  retn
```
