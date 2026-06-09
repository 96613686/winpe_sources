# GetKindFlags(IShellItem2 *)

- ea: `0x1800469d4`
- end: `0x180046b48`
- name: `?GetKindFlags@@YA?AW4KIND_FLAGS@@PEAUIShellItem2@@@Z`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180046d70`

## callees

- `0x180003624`
- `0x18000a220`
- `0x180035830`
- `0x1800469d4`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046ae9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046ae9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046aa4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046b11`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046aa4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046b11`
- `PROPSYS!PropVariantChangeType` at `0x180046a98`
- `PROPSYS!PropVariantChangeType` at `0x180046a98`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetKindFlags(int a1)
{
  unsigned int v1; // edi
  __int128 v2; // xmm1
  __int64 v3; // xmm2_8
  HRESULT v4; // ebx
  unsigned int i; // ebx
  unsigned int j; // esi
  __int64 v7; // r15
  __int64 v9; // [rsp+30h] [rbp-40h] BYREF
  PROPVARIANT ppropvarDest[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v11; // [rsp+48h] [rbp-28h]
  PROPVARIANT propvarSrc[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v13; // [rsp+60h] [rbp-10h]

  v1 = 0;
  v9 = 0;
  if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(
              (unsigned int)&v9,
              a1,
              8,
              (unsigned int)&PKEY_Kind,
              1) >= 0 )
  {
    LOWORD(ppropvarDest[0]) = 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v9 + 40LL))(
           v9,
           &PKEY_Kind,
           ppropvarDest) >= 0 )
    {
      if ( LOWORD(ppropvarDest[0]) )
      {
        if ( LOWORD(ppropvarDest[0]) == 4127 )
          goto LABEL_6;
        v2 = *(_OWORD *)ppropvarDest;
        v3 = v11;
        *(_OWORD *)ppropvarDest = 0;
        v11 = 0;
        *(_OWORD *)propvarSrc = v2;
        v13 = v3;
        v4 = PropVariantChangeType(ppropvarDest, propvarSrc, 0, 0x101Fu);
        PropVariantClear(propvarSrc);
        if ( v4 >= 0 )
        {
LABEL_6:
          v1 = 0;
          for ( i = 0; i < LODWORD(ppropvarDest[1]); ++i )
          {
            for ( j = 0; j < 7; ++j )
            {
              v7 = 16LL * (int)j;
              if ( CompareStringOrdinal(
                     *(LPCWCH *)(v11 + 8LL * i),
                     -1,
                     *(LPCWCH *)((char *)&g_rgCanonicalKindToKindFlag + v7),
                     -1,
                     1) == 2 )
                v1 |= *(_DWORD *)((char *)&g_rgCanonicalKindToKindFlag + v7 + 8);
            }
          }
        }
      }
    }
    PropVariantClear(ppropvarDest);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  return v1;
}

```

## disassembly

```asm
0x1800469d4  mov     [rsp-28h+arg_8], rbx
0x1800469d9  mov     [rsp-28h+arg_10], rsi
0x1800469de  push    rbp
0x1800469df  push    rdi
0x1800469e0  push    r12
0x1800469e2  push    r14
0x1800469e4  push    r15
0x1800469e6  mov     rbp, rsp
0x1800469e9  sub     rsp, 70h
0x1800469ed  mov     rax, cs:__security_cookie
0x1800469f4  xor     rax, rsp
0x1800469f7  mov     [rbp+var_8], rax
0x1800469fb  xor     r12d, r12d
0x1800469fe  mov     edi, r12d
0x180046a01  mov     [rbp+var_40], r12
0x180046a05  mov     [rsp+70h+bIgnoreCase], 1
0x180046a0d  lea     r9, PKEY_Kind
0x180046a14  lea     r8d, [r12+8]
0x180046a19  mov     rdx, rcx
0x180046a1c  lea     rcx, [rbp+var_40]
0x180046a20  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x180046a25  test    eax, eax
0x180046a27  js      loc_180046B18
0x180046a2d  mov     word ptr [rbp+ppropvarDest], r12w
0x180046a32  mov     rcx, [rbp+var_40]
0x180046a36  mov     rax, [rcx]
0x180046a39  lea     r8, [rbp+ppropvarDest]
0x180046a3d  lea     rdx, PKEY_Kind
0x180046a44  mov     rax, [rax+28h]
0x180046a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a4d  test    eax, eax
0x180046a4f  js      loc_180046B0D
0x180046a55  movzx   eax, word ptr [rbp+ppropvarDest]
0x180046a59  test    ax, ax
0x180046a5c  jz      loc_180046B0D
0x180046a62  mov     r9d, 101Fh; vt
0x180046a68  cmp     ax, r9w
0x180046a6c  jz      short loc_180046AAE
0x180046a6e  movups  xmm1, xmmword ptr [rbp+ppropvarDest]
0x180046a72  movsd   xmm2, [rbp+var_28]
0x180046a77  xorps   xmm0, xmm0
0x180046a7a  xor     eax, eax
0x180046a7c  movups  xmmword ptr [rbp+ppropvarDest], xmm0
0x180046a80  mov     [rbp+var_28], rax
0x180046a84  movups  xmmword ptr [rbp+propvarSrc], xmm1
0x180046a88  movsd   [rbp+var_10], xmm2
0x180046a8d  xor     r8d, r8d; flags
0x180046a90  lea     rdx, [rbp+propvarSrc]; propvarSrc
0x180046a94  lea     rcx, [rbp+ppropvarDest]; ppropvarDest
0x180046a98  call    cs:__imp_PropVariantChangeType
0x180046a9e  mov     ebx, eax
0x180046aa0  lea     rcx, [rbp+propvarSrc]; pvar
0x180046aa4  call    cs:__imp_PropVariantClear
0x180046aaa  test    ebx, ebx
0x180046aac  js      short loc_180046B0D
0x180046aae  mov     edi, r12d
0x180046ab1  mov     ebx, r12d
0x180046ab4  cmp     dword ptr [rbp+ppropvarDest+8], r12d
0x180046ab8  jbe     short loc_180046B0D
0x180046aba  mov     esi, r12d
0x180046abd  mov     r14d, ebx
0x180046ac0  lea     r12, ?g_rgCanonicalKindToKindFlag@@3QBUKIND_MAP@@B; KIND_MAP const near * const g_rgCanonicalKindToKindFlag
0x180046ac7  movsxd  r15, esi
0x180046aca  shl     r15, 4
0x180046ace  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x180046ad6  or      r9d, 0FFFFFFFFh; cchCount2
0x180046ada  mov     r8, [r15+r12]; lpString2
0x180046ade  or      edx, r9d; cchCount1
0x180046ae1  mov     rcx, [rbp+var_28]
0x180046ae5  mov     rcx, [rcx+r14*8]; lpString1
0x180046ae9  call    cs:__imp_CompareStringOrdinal
0x180046aef  cmp     eax, 2
0x180046af2  jnz     short loc_180046AF9
0x180046af4  or      edi, [r15+r12+8]
0x180046af9  inc     esi
0x180046afb  cmp     esi, 7
0x180046afe  jb      short loc_180046AC7
0x180046b00  inc     ebx
0x180046b02  cmp     ebx, dword ptr [rbp+ppropvarDest+8]
0x180046b05  mov     r12d, 0
0x180046b0b  jb      short loc_180046ABA
0x180046b0d  lea     rcx, [rbp+ppropvarDest]; pvar
0x180046b11  call    cs:__imp_PropVariantClear
0x180046b17  nop
0x180046b18  lea     rcx, [rbp+var_40]
0x180046b1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046b21  mov     eax, edi
0x180046b23  mov     rcx, [rbp+var_8]
0x180046b27  xor     rcx, rsp; StackCookie
0x180046b2a  call    __security_check_cookie
0x180046b2f  lea     r11, [rsp+70h+var_s0]
0x180046b34  mov     rbx, [r11+38h]
0x180046b38  mov     rsi, [r11+40h]
0x180046b3c  mov     rsp, r11
0x180046b3f  pop     r15
0x180046b41  pop     r14
0x180046b43  pop     r12
0x180046b45  pop     rdi
0x180046b46  pop     rbp
0x180046b47  retn
```
