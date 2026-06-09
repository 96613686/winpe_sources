# CUwfManagement::CommitRegistryDeletion(bool,ushort const *,ushort const *)

- ea: `0x180015870`
- end: `0x180015ae3`
- name: `?CommitRegistryDeletion@CUwfManagement@@QEAAJ_NPEBG1@Z`
- size: `627`
- prototype: `__int64 __fastcall(CUwfManagement *this, char, wchar_t *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180018240`

## callees

- `0x180001384`
- `0x18000e170`
- `0x180011a30`
- `0x180011b90`
- `0x180011c40`
- `0x180012c70`
- `0x180013100`
- `0x180013220`
- `0x180013460`
- `0x1800139f0`
- `0x180015870`
- `0x180016c94`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180015999`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015aba`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015ac3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015999`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015aba`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015ac3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800158f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015970`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800158f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015970`

## string_xrefs

- `0x1800158ae`: `RegistryExceptionsUserDefined`
- `0x1800158e0`: `RegistryExceptionsUWFSpecific`
- `0x180015953`: `RegistryExceptionsUWFSpecific`

## pseudocode

```c
__int64 __fastcall CUwfManagement::CommitRegistryDeletion(
        CUwfManagement *this,
        char a2,
        wchar_t *a3,
        unsigned __int16 *a4)
{
  HKEY *v4; // r15
  __int64 v7; // r13
  int v8; // ebx
  HKEY v9; // rcx
  LSTATUS ValueW; // eax
  signed int v11; // edi
  void *pvData; // rsi
  bool v13; // cc
  struct _MULTISZ *v14; // rdi
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // r15
  __int64 v18; // rax
  char v19; // r15
  int v20; // eax
  int v21; // eax
  CUwfRegDevice *v22; // rcx
  int v23; // eax
  DWORD pcbData; // [rsp+40h] [rbp-10h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-Ch] BYREF
  struct _MULTISZ *v27; // [rsp+48h] [rbp-8h] BYREF
  bool v28; // [rsp+90h] [rbp+40h] BYREF
  char v29; // [rsp+98h] [rbp+48h]
  unsigned __int16 *v30; // [rsp+A8h] [rbp+58h]

  v30 = a4;
  v29 = a2;
  v4 = (HKEY *)((char *)this + 136);
  v27 = 0;
  v28 = 0;
  v7 = 0;
  v8 = CUwfRegKey::QueryMultiSzValue((CUwfManagement *)((char *)this + 136), L"RegistryExceptionsUserDefined", &v27);
  if ( v8 < 0 )
    goto LABEL_32;
  v9 = *v4;
  pdwType = 0;
  pcbData = 0;
  ValueW = RegGetValueW(v9, 0, L"RegistryExceptionsUWFSpecific", 0x20u, &pdwType, 0, &pcbData);
  v11 = ValueW;
  v8 = -2147024882;
  if ( ValueW )
  {
    pvData = 0;
    v13 = ValueW <= 0;
LABEL_4:
    if ( !v13 )
      v11 = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_11;
  }
  pvData = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
  if ( !pvData )
  {
    v11 = -2147024882;
    goto LABEL_11;
  }
  ValueW = RegGetValueW(*v4, 0, L"RegistryExceptionsUWFSpecific", 0x20u, &pdwType, pvData, &pcbData);
  v11 = ValueW;
  v13 = ValueW <= 0;
  if ( ValueW )
    goto LABEL_4;
  v7 = MultiSzAlloc(pvData);
  v11 = -2147024882;
  if ( v7 )
    v11 = 0;
LABEL_11:
  operator delete[](pvData);
  if ( v11 < 0 )
  {
    v8 = v11;
LABEL_32:
    v14 = v27;
    goto LABEL_33;
  }
  v14 = v27;
  v15 = 0;
  if ( *(_DWORD *)(v7 + 24) )
  {
    while ( 1 )
    {
      v16 = *(_QWORD *)(v7 + 16);
      v17 = *(_QWORD *)(v16 + 8 * v15);
      if ( !v17 )
        break;
      if ( (int)MultiSzFind(*(wchar_t **)(v16 + 8 * v15)) >= 0 )
      {
        v8 = -2147024713;
        goto LABEL_33;
      }
      v18 = MultiSzReAlloc(v14, v17);
      if ( !v18 )
        goto LABEL_33;
      v14 = (struct _MULTISZ *)v18;
      v15 = (unsigned int)(v15 + 1);
      if ( (unsigned int)v15 >= *(_DWORD *)(v7 + 24) )
        goto LABEL_17;
    }
    v8 = -2147467261;
  }
  else
  {
LABEL_17:
    v19 = v29;
    v20 = ValidateRegistryKeyValueToBeCommitted(1, v29, a3, v30, *((_DWORD *)v14 + 6), *((unsigned __int16 ***)v14 + 2));
    if ( v20 )
    {
      v8 = -2147483634;
      if ( v20 != 4 )
        v8 = -2147024809;
    }
    else
    {
      v8 = CUwfManagement::get_IsRegistryChangeAlwaysPersisted(this, &v28);
      if ( v8 >= 0 )
      {
        if ( v28 )
        {
          v8 = -2147483634;
        }
        else
        {
          v21 = CDevice::Initialize((CUwfManagement *)((char *)this + 48), L"\\\\.\\UwfregControl");
          *((_DWORD *)this + 18) = v21;
          v8 = v21;
          if ( v21 >= 0 )
          {
            *((_BYTE *)this + 10) = 1;
            v22 = (CUwfManagement *)((char *)this + 48);
            if ( v19 )
              v23 = CUwfRegDevice::CommitRegistryValueDeletion(v22, a3, v30);
            else
              v23 = CUwfRegDevice::CommitRegistryKeyDeletion(v22, a3);
            v8 = v23;
          }
        }
      }
    }
  }
LABEL_33:
  if ( *((_BYTE *)this + 10) )
  {
    CDevice::Close((CUwfManagement *)((char *)this + 48));
    *((_BYTE *)this + 10) = 0;
  }
  operator delete[]((void *)v7);
  operator delete[](v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015870  mov     [rsp-38h+arg_10], rbx
0x180015875  mov     [rsp-38h+arg_18], r9
0x18001587a  mov     [rsp-38h+arg_8], dl
0x18001587e  push    rbp
0x18001587f  push    rsi
0x180015880  push    rdi
0x180015881  push    r12
0x180015883  push    r13
0x180015885  push    r14
0x180015887  push    r15
0x180015889  mov     rbp, rsp
0x18001588c  sub     rsp, 50h
0x180015890  xor     edi, edi
0x180015892  lea     r15, [rcx+88h]
0x180015899  mov     r12, r8
0x18001589c  mov     [rbp+var_8], rdi
0x1800158a0  mov     r14, rcx
0x1800158a3  mov     [rbp+arg_0], dil
0x1800158a7  mov     rcx, r15; this
0x1800158aa  lea     r8, [rbp+var_8]; struct _MULTISZ **
0x1800158ae  lea     rdx, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x1800158b5  mov     r13d, edi
0x1800158b8  call    ?QueryMultiSzValue@CUwfRegKey@@QEAAJPEBGPEAPEAU_MULTISZ@@@Z; CUwfRegKey::QueryMultiSzValue(ushort const *,_MULTISZ * *)
0x1800158bd  mov     ebx, eax
0x1800158bf  test    eax, eax
0x1800158c1  js      loc_180015A9E
0x1800158c7  mov     rcx, [r15]; hkey
0x1800158ca  lea     rax, [rbp+var_10]
0x1800158ce  mov     [rsp+50h+pcbData], rax; pcbData
0x1800158d3  lea     r9d, [rdi+20h]; dwFlags
0x1800158d7  lea     rax, [rbp+var_C]
0x1800158db  mov     [rsp+50h+pvData], rdi; pvData
0x1800158e0  lea     r8, aRegistryexcept; "RegistryExceptionsUWFSpecific"
0x1800158e7  mov     [rsp+50h+pdwType], rax; pdwType
0x1800158ec  xor     edx, edx; lpSubKey
0x1800158ee  mov     [rbp+var_C], edi
0x1800158f1  mov     [rbp+var_10], edi
0x1800158f4  call    cs:__imp_RegGetValueW
0x1800158fa  mov     edi, eax
0x1800158fc  mov     ebx, 8007000Eh
0x180015901  test    eax, eax
0x180015903  jz      short loc_18001591A
0x180015905  xor     esi, esi
0x180015907  test    eax, eax
0x180015909  jle     loc_180015996
0x18001590f  movzx   edi, ax
0x180015912  or      edi, 80070000h
0x180015918  jmp     short loc_180015996
0x18001591a  mov     ecx, [rbp+var_10]
0x18001591d  mov     eax, 2
0x180015922  shr     rcx, 1
0x180015925  mul     rcx
0x180015928  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001592f  cmovb   rax, rcx
0x180015933  mov     rcx, rax; unsigned __int64
0x180015936  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001593b  mov     rsi, rax
0x18001593e  test    rax, rax
0x180015941  jnz     short loc_180015947
0x180015943  mov     edi, ebx
0x180015945  jmp     short loc_180015996
0x180015947  mov     rcx, [r15]; hkey
0x18001594a  lea     rax, [rbp+var_10]
0x18001594e  mov     [rsp+50h+pcbData], rax; pcbData
0x180015953  lea     r8, aRegistryexcept; "RegistryExceptionsUWFSpecific"
0x18001595a  lea     rax, [rbp+var_C]
0x18001595e  mov     [rsp+50h+pvData], rsi; pvData
0x180015963  mov     r9d, 20h ; ' '; dwFlags
0x180015969  mov     [rsp+50h+pdwType], rax; pdwType
0x18001596e  xor     edx, edx; lpSubKey
0x180015970  call    cs:__imp_RegGetValueW
0x180015976  mov     edi, eax
0x180015978  test    eax, eax
0x18001597a  jnz     short loc_180015909
0x18001597c  mov     edx, [rbp+var_10]
0x18001597f  mov     rcx, rsi; Src
0x180015982  shr     edx, 1
0x180015984  call    MultiSzAlloc
0x180015989  mov     r13, rax
0x18001598c  mov     edi, ebx
0x18001598e  xor     eax, eax
0x180015990  test    r13, r13
0x180015993  cmovnz  edi, eax
0x180015996  mov     rcx, rsi
0x180015999  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001599f  test    edi, edi
0x1800159a1  js      loc_180015A9C
0x1800159a7  mov     rdi, [rbp+var_8]
0x1800159ab  xor     esi, esi
0x1800159ad  cmp     [r13+18h], esi
0x1800159b1  jbe     short loc_1800159F4
0x1800159b3  mov     rax, [r13+10h]
0x1800159b7  mov     r15, [rax+rsi*8]
0x1800159bb  test    r15, r15
0x1800159be  jz      short loc_180015A36
0x1800159c0  xor     r9d, r9d
0x1800159c3  xor     r8d, r8d
0x1800159c6  mov     rdx, rdi
0x1800159c9  mov     rcx, r15; String2
0x1800159cc  call    MultiSzFind
0x1800159d1  test    eax, eax
0x1800159d3  jns     short loc_180015A2F
0x1800159d5  mov     rdx, r15
0x1800159d8  mov     rcx, rdi
0x1800159db  call    MultiSzReAlloc
0x1800159e0  test    rax, rax
0x1800159e3  jz      loc_180015AA2
0x1800159e9  mov     rdi, rax
0x1800159ec  inc     esi
0x1800159ee  cmp     esi, [r13+18h]
0x1800159f2  jb      short loc_1800159B3
0x1800159f4  mov     rax, [rdi+10h]
0x1800159f8  mov     r8, r12
0x1800159fb  mov     r15b, [rbp+arg_8]
0x1800159ff  mov     cl, 1
0x180015a01  mov     r9, [rbp+arg_18]
0x180015a05  mov     dl, r15b
0x180015a08  mov     [rsp+50h+pvData], rax
0x180015a0d  mov     eax, [rdi+18h]
0x180015a10  mov     dword ptr [rsp+50h+pdwType], eax
0x180015a14  call    ?ValidateRegistryKeyValueToBeCommitted@@YA?AW4REG_COMMIT_VALIDATE_RESULT@@_N0PEBG1KPEAPEAG@Z; ValidateRegistryKeyValueToBeCommitted(bool,bool,ushort const *,ushort const *,ulong,ushort * *)
0x180015a19  test    eax, eax
0x180015a1b  jz      short loc_180015A3D
0x180015a1d  cmp     eax, 4
0x180015a20  mov     ebx, 8000000Eh
0x180015a25  mov     ecx, 80070057h
0x180015a2a  cmovnz  ebx, ecx
0x180015a2d  jmp     short loc_180015AA2
0x180015a2f  mov     ebx, 800700B7h
0x180015a34  jmp     short loc_180015AA2
0x180015a36  mov     ebx, 80004003h
0x180015a3b  jmp     short loc_180015AA2
0x180015a3d  lea     rdx, [rbp+arg_0]; bool *
0x180015a41  mov     rcx, r14; this
0x180015a44  call    ?get_IsRegistryChangeAlwaysPersisted@CUwfManagement@@AEAAJPEA_N@Z; CUwfManagement::get_IsRegistryChangeAlwaysPersisted(bool *)
0x180015a49  mov     ebx, eax
0x180015a4b  test    eax, eax
0x180015a4d  js      short loc_180015AA2
0x180015a4f  cmp     [rbp+arg_0], 0
0x180015a53  jz      short loc_180015A5C
0x180015a55  mov     ebx, 8000000Eh
0x180015a5a  jmp     short loc_180015AA2
0x180015a5c  lea     rsi, [r14+30h]
0x180015a60  mov     rcx, rsi; this
0x180015a63  lea     rdx, FileName; "\\\\.\\UwfregControl"
0x180015a6a  call    ?Initialize@CDevice@@QEAAJPEBG@Z; CDevice::Initialize(ushort const *)
0x180015a6f  mov     [rsi+18h], eax
0x180015a72  mov     ebx, eax
0x180015a74  test    eax, eax
0x180015a76  js      short loc_180015AA2
0x180015a78  mov     byte ptr [r14+0Ah], 1
0x180015a7d  mov     rdx, r12; unsigned __int16 *
0x180015a80  mov     rcx, rsi; this
0x180015a83  test    r15b, r15b
0x180015a86  jz      short loc_180015A95
0x180015a88  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x180015a8c  call    ?CommitRegistryValueDeletion@CUwfRegDevice@@QEAAJPEBG0@Z; CUwfRegDevice::CommitRegistryValueDeletion(ushort const *,ushort const *)
0x180015a91  mov     ebx, eax
0x180015a93  jmp     short loc_180015AA2
0x180015a95  call    ?CommitRegistryKeyDeletion@CUwfRegDevice@@QEAAJPEBG@Z; CUwfRegDevice::CommitRegistryKeyDeletion(ushort const *)
0x180015a9a  jmp     short loc_180015A91
0x180015a9c  mov     ebx, edi
0x180015a9e  mov     rdi, [rbp+var_8]
0x180015aa2  cmp     byte ptr [r14+0Ah], 0
0x180015aa7  jz      short loc_180015AB7
0x180015aa9  lea     rcx, [r14+30h]; this
0x180015aad  call    ?Close@CDevice@@QEAAXXZ; CDevice::Close(void)
0x180015ab2  mov     byte ptr [r14+0Ah], 0
0x180015ab7  mov     rcx, r13
0x180015aba  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015ac0  mov     rcx, rdi
0x180015ac3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015ac9  mov     eax, ebx
0x180015acb  mov     rbx, [rsp+50h+arg_10]
0x180015ad3  add     rsp, 50h
0x180015ad7  pop     r15
0x180015ad9  pop     r14
0x180015adb  pop     r13
0x180015add  pop     r12
0x180015adf  pop     rdi
0x180015ae0  pop     rsi
0x180015ae1  pop     rbp
0x180015ae2  retn
```
