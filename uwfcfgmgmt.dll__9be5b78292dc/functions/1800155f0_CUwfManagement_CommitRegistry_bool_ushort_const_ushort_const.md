# CUwfManagement::CommitRegistry(bool,ushort const *,ushort const *)

- ea: `0x1800155f0`
- end: `0x180015863`
- name: `?CommitRegistry@CUwfManagement@@QEAAJ_NPEBG1@Z`
- size: `627`
- prototype: `__int64 __fastcall(CUwfManagement *this, char, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800181a0`

## callees

- `0x180001384`
- `0x18000e170`
- `0x180011a30`
- `0x180011b90`
- `0x180011c40`
- `0x180012c70`
- `0x180013100`
- `0x180013130`
- `0x180013310`
- `0x1800139f0`
- `0x1800155f0`
- `0x180016c94`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180015719`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001583a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015843`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015719`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001583a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015843`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015674`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800156f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015674`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800156f0`

## string_xrefs

- `0x18001562e`: `RegistryExceptionsUserDefined`
- `0x180015660`: `RegistryExceptionsUWFSpecific`
- `0x1800156d3`: `RegistryExceptionsUWFSpecific`

## pseudocode

```c
__int64 __fastcall CUwfManagement::CommitRegistry(
        CUwfManagement *this,
        char a2,
        const unsigned __int16 *a3,
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
  __int64 v14; // rdx
  struct _MULTISZ *v15; // rdi
  __int64 v16; // rsi
  __int64 v17; // rax
  __int64 v18; // r15
  __int64 v19; // rax
  char v20; // r15
  int v21; // eax
  int v22; // eax
  CUwfRegDevice *v23; // rcx
  int v24; // eax
  DWORD pcbData; // [rsp+40h] [rbp-10h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-Ch] BYREF
  struct _MULTISZ *v28; // [rsp+48h] [rbp-8h] BYREF
  bool v29; // [rsp+90h] [rbp+40h] BYREF
  char v30; // [rsp+98h] [rbp+48h]
  unsigned __int16 *v31; // [rsp+A8h] [rbp+58h]

  v31 = a4;
  v30 = a2;
  v4 = (HKEY *)((char *)this + 136);
  v28 = 0;
  v29 = 0;
  v7 = 0;
  v8 = CUwfRegKey::QueryMultiSzValue((CUwfManagement *)((char *)this + 136), L"RegistryExceptionsUserDefined", &v28);
  if ( v8 < 0 )
    goto LABEL_33;
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
LABEL_33:
    v15 = v28;
    goto LABEL_34;
  }
  v15 = v28;
  v16 = 0;
  if ( *(_DWORD *)(v7 + 24) )
  {
    while ( 1 )
    {
      v17 = *(_QWORD *)(v7 + 16);
      v18 = *(_QWORD *)(v17 + 8 * v16);
      if ( !v18 )
        break;
      if ( (int)MultiSzFind(*(wchar_t **)(v17 + 8 * v16)) >= 0 )
      {
        v8 = -2147024713;
        goto LABEL_34;
      }
      v19 = MultiSzReAlloc(v15, v18);
      if ( !v19 )
        goto LABEL_34;
      v15 = (struct _MULTISZ *)v19;
      v16 = (unsigned int)(v16 + 1);
      if ( (unsigned int)v16 >= *(_DWORD *)(v7 + 24) )
        goto LABEL_17;
    }
    v8 = -2147467261;
  }
  else
  {
LABEL_17:
    v20 = v30;
    LOBYTE(v14) = v30;
    v21 = ValidateRegistryKeyValueToBeCommitted(0, v14, a3, v31, *((_DWORD *)v15 + 6), *((_QWORD *)v15 + 2));
    if ( v21 )
    {
      if ( v21 == 4 )
      {
        v8 = 0;
      }
      else
      {
        v8 = -2147024809;
        if ( v21 == 1 )
          v8 = -2147024894;
      }
    }
    else
    {
      v8 = CUwfManagement::get_IsRegistryChangeAlwaysPersisted(this, &v29);
      if ( v8 >= 0 && !v29 )
      {
        v22 = CDevice::Initialize((CUwfManagement *)((char *)this + 48), L"\\\\.\\UwfregControl");
        *((_DWORD *)this + 18) = v22;
        v8 = v22;
        if ( v22 >= 0 )
        {
          *((_BYTE *)this + 10) = 1;
          v23 = (CUwfManagement *)((char *)this + 48);
          if ( v20 )
            v24 = CUwfRegDevice::CommitRegistryValue(v23, a3, v31);
          else
            v24 = CUwfRegDevice::CommitRegistryKey(v23, a3);
          v8 = v24;
        }
      }
    }
  }
LABEL_34:
  if ( *((_BYTE *)this + 10) )
  {
    CDevice::Close((CUwfManagement *)((char *)this + 48));
    *((_BYTE *)this + 10) = 0;
  }
  operator delete[]((void *)v7);
  operator delete[](v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800155f0  mov     [rsp-38h+arg_10], rbx
0x1800155f5  mov     [rsp-38h+arg_18], r9
0x1800155fa  mov     [rsp-38h+arg_8], dl
0x1800155fe  push    rbp
0x1800155ff  push    rsi
0x180015600  push    rdi
0x180015601  push    r12
0x180015603  push    r13
0x180015605  push    r14
0x180015607  push    r15
0x180015609  mov     rbp, rsp
0x18001560c  sub     rsp, 50h
0x180015610  xor     edi, edi
0x180015612  lea     r15, [rcx+88h]
0x180015619  mov     r12, r8
0x18001561c  mov     [rbp+var_8], rdi
0x180015620  mov     r14, rcx
0x180015623  mov     [rbp+arg_0], dil
0x180015627  mov     rcx, r15; this
0x18001562a  lea     r8, [rbp+var_8]; struct _MULTISZ **
0x18001562e  lea     rdx, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x180015635  mov     r13d, edi
0x180015638  call    ?QueryMultiSzValue@CUwfRegKey@@QEAAJPEBGPEAPEAU_MULTISZ@@@Z; CUwfRegKey::QueryMultiSzValue(ushort const *,_MULTISZ * *)
0x18001563d  mov     ebx, eax
0x18001563f  test    eax, eax
0x180015641  js      loc_18001581E
0x180015647  mov     rcx, [r15]; hkey
0x18001564a  lea     rax, [rbp+var_10]
0x18001564e  mov     [rsp+50h+pcbData], rax; pcbData
0x180015653  lea     r9d, [rdi+20h]; dwFlags
0x180015657  lea     rax, [rbp+var_C]
0x18001565b  mov     [rsp+50h+pvData], rdi; pvData
0x180015660  lea     r8, aRegistryexcept; "RegistryExceptionsUWFSpecific"
0x180015667  mov     [rsp+50h+pdwType], rax; pdwType
0x18001566c  xor     edx, edx; lpSubKey
0x18001566e  mov     [rbp+var_C], edi
0x180015671  mov     [rbp+var_10], edi
0x180015674  call    cs:__imp_RegGetValueW
0x18001567a  mov     edi, eax
0x18001567c  mov     ebx, 8007000Eh
0x180015681  test    eax, eax
0x180015683  jz      short loc_18001569A
0x180015685  xor     esi, esi
0x180015687  test    eax, eax
0x180015689  jle     loc_180015716
0x18001568f  movzx   edi, ax
0x180015692  or      edi, 80070000h
0x180015698  jmp     short loc_180015716
0x18001569a  mov     ecx, [rbp+var_10]
0x18001569d  mov     eax, 2
0x1800156a2  shr     rcx, 1
0x1800156a5  mul     rcx
0x1800156a8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800156af  cmovb   rax, rcx
0x1800156b3  mov     rcx, rax; unsigned __int64
0x1800156b6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800156bb  mov     rsi, rax
0x1800156be  test    rax, rax
0x1800156c1  jnz     short loc_1800156C7
0x1800156c3  mov     edi, ebx
0x1800156c5  jmp     short loc_180015716
0x1800156c7  mov     rcx, [r15]; hkey
0x1800156ca  lea     rax, [rbp+var_10]
0x1800156ce  mov     [rsp+50h+pcbData], rax; pcbData
0x1800156d3  lea     r8, aRegistryexcept; "RegistryExceptionsUWFSpecific"
0x1800156da  lea     rax, [rbp+var_C]
0x1800156de  mov     [rsp+50h+pvData], rsi; pvData
0x1800156e3  mov     r9d, 20h ; ' '; dwFlags
0x1800156e9  mov     [rsp+50h+pdwType], rax; pdwType
0x1800156ee  xor     edx, edx; lpSubKey
0x1800156f0  call    cs:__imp_RegGetValueW
0x1800156f6  mov     edi, eax
0x1800156f8  test    eax, eax
0x1800156fa  jnz     short loc_180015689
0x1800156fc  mov     edx, [rbp+var_10]
0x1800156ff  mov     rcx, rsi; Src
0x180015702  shr     edx, 1
0x180015704  call    MultiSzAlloc
0x180015709  mov     r13, rax
0x18001570c  mov     edi, ebx
0x18001570e  xor     eax, eax
0x180015710  test    r13, r13
0x180015713  cmovnz  edi, eax
0x180015716  mov     rcx, rsi
0x180015719  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001571f  test    edi, edi
0x180015721  js      loc_18001581C
0x180015727  mov     rdi, [rbp+var_8]
0x18001572b  xor     esi, esi
0x18001572d  cmp     [r13+18h], esi
0x180015731  jbe     short loc_180015774
0x180015733  mov     rax, [r13+10h]
0x180015737  mov     r15, [rax+rsi*8]
0x18001573b  test    r15, r15
0x18001573e  jz      short loc_1800157AD
0x180015740  xor     r9d, r9d
0x180015743  xor     r8d, r8d
0x180015746  mov     rdx, rdi
0x180015749  mov     rcx, r15; String2
0x18001574c  call    MultiSzFind
0x180015751  test    eax, eax
0x180015753  jns     short loc_1800157A6
0x180015755  mov     rdx, r15
0x180015758  mov     rcx, rdi
0x18001575b  call    MultiSzReAlloc
0x180015760  test    rax, rax
0x180015763  jz      loc_180015822
0x180015769  mov     rdi, rax
0x18001576c  inc     esi
0x18001576e  cmp     esi, [r13+18h]
0x180015772  jb      short loc_180015733
0x180015774  mov     rax, [rdi+10h]
0x180015778  mov     r8, r12
0x18001577b  mov     r15b, [rbp+arg_8]
0x18001577f  xor     ecx, ecx
0x180015781  mov     r9, [rbp+arg_18]
0x180015785  mov     dl, r15b
0x180015788  mov     [rsp+50h+pvData], rax
0x18001578d  mov     eax, [rdi+18h]
0x180015790  mov     dword ptr [rsp+50h+pdwType], eax
0x180015794  call    ?ValidateRegistryKeyValueToBeCommitted@@YA?AW4REG_COMMIT_VALIDATE_RESULT@@_N0PEBG1KPEAPEAG@Z; ValidateRegistryKeyValueToBeCommitted(bool,bool,ushort const *,ushort const *,ulong,ushort * *)
0x180015799  test    eax, eax
0x18001579b  jz      short loc_1800157C4
0x18001579d  cmp     eax, 4
0x1800157a0  jnz     short loc_1800157B4
0x1800157a2  xor     ebx, ebx
0x1800157a4  jmp     short loc_180015822
0x1800157a6  mov     ebx, 800700B7h
0x1800157ab  jmp     short loc_180015822
0x1800157ad  mov     ebx, 80004003h
0x1800157b2  jmp     short loc_180015822
0x1800157b4  mov     ebx, 80070057h
0x1800157b9  cmp     eax, 1
0x1800157bc  lea     ecx, [rbx-55h]
0x1800157bf  cmovz   ebx, ecx
0x1800157c2  jmp     short loc_180015822
0x1800157c4  lea     rdx, [rbp+arg_0]; bool *
0x1800157c8  mov     rcx, r14; this
0x1800157cb  call    ?get_IsRegistryChangeAlwaysPersisted@CUwfManagement@@AEAAJPEA_N@Z; CUwfManagement::get_IsRegistryChangeAlwaysPersisted(bool *)
0x1800157d0  mov     ebx, eax
0x1800157d2  test    eax, eax
0x1800157d4  js      short loc_180015822
0x1800157d6  cmp     [rbp+arg_0], 0
0x1800157da  jnz     short loc_180015822
0x1800157dc  lea     rsi, [r14+30h]
0x1800157e0  mov     rcx, rsi; this
0x1800157e3  lea     rdx, FileName; "\\\\.\\UwfregControl"
0x1800157ea  call    ?Initialize@CDevice@@QEAAJPEBG@Z; CDevice::Initialize(ushort const *)
0x1800157ef  mov     [rsi+18h], eax
0x1800157f2  mov     ebx, eax
0x1800157f4  test    eax, eax
0x1800157f6  js      short loc_180015822
0x1800157f8  mov     byte ptr [r14+0Ah], 1
0x1800157fd  mov     rdx, r12; unsigned __int16 *
0x180015800  mov     rcx, rsi; this
0x180015803  test    r15b, r15b
0x180015806  jz      short loc_180015815
0x180015808  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x18001580c  call    ?CommitRegistryValue@CUwfRegDevice@@QEAAJPEBG0@Z; CUwfRegDevice::CommitRegistryValue(ushort const *,ushort const *)
0x180015811  mov     ebx, eax
0x180015813  jmp     short loc_180015822
0x180015815  call    ?CommitRegistryKey@CUwfRegDevice@@QEAAJPEBG@Z; CUwfRegDevice::CommitRegistryKey(ushort const *)
0x18001581a  jmp     short loc_180015811
0x18001581c  mov     ebx, edi
0x18001581e  mov     rdi, [rbp+var_8]
0x180015822  cmp     byte ptr [r14+0Ah], 0
0x180015827  jz      short loc_180015837
0x180015829  lea     rcx, [r14+30h]; this
0x18001582d  call    ?Close@CDevice@@QEAAXXZ; CDevice::Close(void)
0x180015832  mov     byte ptr [r14+0Ah], 0
0x180015837  mov     rcx, r13
0x18001583a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015840  mov     rcx, rdi
0x180015843  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015849  mov     eax, ebx
0x18001584b  mov     rbx, [rsp+50h+arg_10]
0x180015853  add     rsp, 50h
0x180015857  pop     r15
0x180015859  pop     r14
0x18001585b  pop     r13
0x18001585d  pop     r12
0x18001585f  pop     rdi
0x180015860  pop     rsi
0x180015861  pop     rbp
0x180015862  retn
```
