# CustomizedContactPropMapping_PoomToUdm(PoomOperationContext *,ulong,Udm::Vector<_SQLCEPROPVAL> const &,Udm::Vector<_SQLCEPROPVAL> const &,UdmObjectId const &,UdmPropertyValue *)

- ea: `0x180018560`
- end: `0x180018a01`
- name: `?CustomizedContactPropMapping_PoomToUdm@@YAJPEAVPoomOperationContext@@KAEBV?$Vector@U_SQLCEPROPVAL@@@Udm@@1AEBUUdmObjectId@@PEAUUdmPropertyValue@@@Z`
- size: `1185`
- prototype: `__int64 __fastcall(int, int, int, int, struct UdmObjectId *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180008f0c`
- `0x180018560`
- `0x180019110`
- `0x18002596c`
- `0x180027220`
- `0x18004aff0`
- `0x1800977ac`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `PIMSTORE!PimBinaryBodyToString` at `0x180018761`
- `PIMSTORE!PimBinaryBodyToString` at `0x180018761`
- `PIMSTORE!GetContactDisplayAndSortPropertiesFromRegistry` at `0x180018980`
- `PIMSTORE!GetContactDisplayAndSortPropertiesFromRegistry` at `0x180018980`
- `UserDataTypeHelperUtil!UsOidToContactUdmId` at `0x1800187f3`
- `UserDataTypeHelperUtil!UsOidToContactUdmId` at `0x1800187f3`
- `UserDataTypeHelperUtil!DupString` at `0x180018777`
- `UserDataTypeHelperUtil!DupString` at `0x1800189c0`
- `UserDataTypeHelperUtil!DupString` at `0x180018777`
- `UserDataTypeHelperUtil!DupString` at `0x1800189c0`

## string_xrefs

- `0x1800186b7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactprop.cpp`
- `0x1800186d0`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactprop.cpp`
- `0x180018939`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactprop.cpp`
- `0x1800189de`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactprop.cpp`

## pseudocode

```c
__int64 __fastcall CustomizedContactPropMapping_PoomToUdm(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        struct UdmObjectId *a5,
        __int64 a6)
{
  unsigned __int64 v7; // rcx
  __int64 v9; // r10
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r9
  __int64 v12; // r8
  int v13; // ebx
  __int64 result; // rax
  __int64 v15; // xmm2_8
  __int64 v16; // r9
  unsigned __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // esi
  int v21; // eax
  unsigned int v22; // ebx
  __int64 v23; // r10
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // r11
  unsigned __int64 i; // r8
  const struct _SQLCEPROPVAL *v29; // r9
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // r9
  __int64 v33; // r10
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // r10
  unsigned __int64 v38; // rdx
  unsigned __int64 v39; // r8
  __int64 v40; // r9
  struct UdmPropertyValue *v41; // rdx
  const struct _USPROPVAL *PropByUnistorePropId; // rdx
  struct UdmPropertyValue *v43; // rdx
  _BYTE Block[24]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v45[2]; // [rsp+48h] [rbp-28h] BYREF
  int v46; // [rsp+50h] [rbp-20h]
  __int64 v47; // [rsp+58h] [rbp-18h] BYREF
  int v48; // [rsp+60h] [rbp-10h]

  *(_DWORD *)&Block[4] = a2;
  v7 = 0;
  *(_DWORD *)Block = 256;
  *(_OWORD *)&Block[8] = 0;
  switch ( a2 )
  {
    case 0x14140007u:
      v16 = *(_QWORD *)(a3 + 8);
      v17 = *(_QWORD *)a3;
      while ( v7 < v17 )
      {
        v18 = v16 + 24 * v7;
        if ( *(_DWORD *)v18 == 806617107 )
        {
          if ( (*(_WORD *)(v18 + 6) & 0x300) != 0 )
            goto LABEL_11;
          v19 = *(_QWORD *)(a1 + 48);
          v20 = *(_DWORD *)(v18 + 8);
          *(_QWORD *)v45 = 0;
          v46 = 0;
          v47 = 0;
          v48 = 0;
          v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 80LL))(v19, &v47);
          v22 = v21;
          if ( v21 < 0 )
          {
            Log_HREvent(
              (unsigned int)v21,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactprop.cpp",
              33);
            Log_HREvent(
              v22,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactprop.cpp",
              1186);
            if ( *(unsigned __int16 *)&Block[4] == 5 && *(_QWORD *)&Block[8] )
              operator delete(*(void **)&Block[8]);
            return v22;
          }
          *(_DWORD *)Block &= ~0x100u;
          v45[0] = v47;
          v45[1] = 458754;
          v46 = v20;
          v30 = UsOidToContactUdmId(&v47, v45);
          *(_QWORD *)&Block[8] = *(_QWORD *)v30;
          v31 = *(_DWORD *)(v30 + 8);
LABEL_37:
          *(_DWORD *)&Block[16] = v31;
          goto LABEL_11;
        }
        ++v7;
      }
      goto LABEL_11;
    case 0x140F0006u:
LABEL_10:
      v13 = CombineDataPropsToPoomProp(a2, (unsigned __int64 *)a3, (__int64)Block);
      if ( v13 >= 0 )
        goto LABEL_11;
      v32 = 1278;
      goto LABEL_72;
    case 0x14130001u:
      v9 = *(_QWORD *)(a3 + 8);
      v10 = 0;
      v11 = *(_QWORD *)a3;
      while ( v10 < v11 )
      {
        v12 = v9 + 24 * v10;
        if ( *(_DWORD *)v12 == 16908307 )
        {
          if ( (*(_WORD *)(v12 + 6) & 0x300) != 0 )
            goto LABEL_11;
          *(_DWORD *)Block = 0;
          if ( *(_DWORD *)(v12 + 8) != 1 )
            goto LABEL_48;
          goto LABEL_9;
        }
        ++v10;
      }
      goto LABEL_11;
  }
  if ( a2 <= 0x14100006 )
  {
    if ( a2 != 336592902 )
    {
      if ( a2 == 336199685 )
      {
        v23 = *(_QWORD *)(a3 + 8);
        v24 = 0;
        v25 = *(_QWORD *)a3;
        while ( v24 < v25 )
        {
          v26 = v23 + 24 * v24;
          if ( *(_DWORD *)v26 == 1966180 )
          {
            if ( (*(_WORD *)(v26 + 6) & 0x300) != 0 )
              goto LABEL_11;
            *(_QWORD *)v45 = 0;
            if ( (int)PimBinaryBodyToString(v26 + 8, v45) < 0 )
              goto LABEL_11;
            v13 = DupString(&Block[8], *(_QWORD *)v45);
            if ( v13 >= 0 )
            {
              *(_DWORD *)Block &= ~0x100u;
              goto LABEL_11;
            }
            v32 = 1262;
            goto LABEL_72;
          }
          ++v24;
        }
        goto LABEL_11;
      }
      if ( a2 != 336265222 && a2 != 336330758 && a2 != 336396294 && a2 != 336461830 )
        goto LABEL_63;
    }
    goto LABEL_10;
  }
  switch ( a2 )
  {
    case 0x14150005u:
      v27 = *(_QWORD *)(a3 + 8);
      for ( i = 0; i < *(_QWORD *)a3; ++i )
      {
        v29 = (const struct _SQLCEPROPVAL *)(v27 + 24 * i);
        if ( *(_DWORD *)v29 == 17432641 )
          goto LABEL_40;
      }
      v29 = 0;
LABEL_40:
      v13 = PoomRemoteIdToUdmRemoteId(v29, a5, (struct UdmPropertyValue *)Block);
      if ( v13 >= 0 )
        goto LABEL_11;
      v32 = 1250;
      goto LABEL_72;
    case 0x16020001u:
      v33 = *(_QWORD *)(a3 + 8);
      v34 = 0;
      v35 = *(_QWORD *)a3;
      while ( v34 < v35 )
      {
        v36 = v33 + 24 * v34;
        if ( *(_DWORD *)v36 == 29556747 )
        {
          if ( (*(_WORD *)(v36 + 6) & 0x300) == 0 )
          {
            *(_DWORD *)Block = 0;
            if ( *(_DWORD *)(v36 + 8) )
LABEL_48:
              *(_DWORD *)&Block[8] = 0;
            else
LABEL_9:
              *(_DWORD *)&Block[8] = 1;
          }
          goto LABEL_11;
        }
        ++v34;
      }
      goto LABEL_11;
    case 0x16070007u:
      v37 = *(_QWORD *)(a3 + 8);
      v38 = 0;
      v39 = *(_QWORD *)a3;
      while ( v38 < v39 )
      {
        v40 = v37 + 24 * v38;
        if ( *(_DWORD *)v40 == 1124073491 )
        {
          if ( (*(_WORD *)(v40 + 6) & 0x300) != 0 )
            goto LABEL_11;
          *(_DWORD *)Block = 0;
          *(_QWORD *)&Block[8] = 0x2900000000LL;
          v31 = *(_DWORD *)(v40 + 8);
          goto LABEL_37;
        }
        ++v38;
      }
      goto LABEL_11;
    case 0x14110006u:
      goto LABEL_10;
  }
  if ( a2 != 343015429 )
  {
LABEL_63:
    Log_HREvent(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactprop.cpp",
      1284);
    Udm::FreeUdmPropVal((Udm *)Block, v41);
    return 2147942487LL;
  }
  v45[0] = 0;
  GetContactDisplayAndSortPropertiesFromRegistry(0, v45);
  PropByUnistorePropId = FindPropByUnistorePropId(*(_QWORD *)a3, *(const struct _USPROPVAL **)(a3 + 8), v45[0]);
  if ( !PropByUnistorePropId
    || (*((_WORD *)PropByUnistorePropId + 3) & 0x300) != 0
    || (*(_DWORD *)Block &= ~0x100u, v13 = DupString(&Block[8], *((_QWORD *)PropByUnistorePropId + 1)), v13 >= 0) )
  {
LABEL_11:
    result = 0;
    v15 = *(_QWORD *)&Block[16];
    *(_OWORD *)a6 = *(_OWORD *)Block;
    *(_QWORD *)(a6 + 16) = v15;
    return result;
  }
  v32 = 1214;
LABEL_72:
  Log_HREvent(
    (unsigned int)v13,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactprop.cpp",
    v32);
  Udm::FreeUdmPropVal((Udm *)Block, v43);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180018560  mov     [rsp-18h+arg_18], rbx
0x180018565  push    rbp
0x180018566  push    rsi
0x180018567  push    rdi
0x180018568  mov     rbp, rsp
0x18001856b  sub     rsp, 70h
0x18001856f  mov     rax, cs:__security_cookie
0x180018576  xor     rax, rsp
0x180018579  mov     [rbp+var_8], rax
0x18001857d  mov     rdi, [rbp+arg_28]
0x180018581  mov     eax, edx
0x180018583  mov     rdx, [rbp+arg_20]; struct UdmObjectId *
0x180018587  xorps   xmm0, xmm0
0x18001858a  movups  xmmword ptr [rbp+Block], xmm0
0x18001858e  mov     r10, rcx
0x180018591  mov     dword ptr [rbp+Block+4], eax
0x180018594  xor     ecx, ecx
0x180018596  mov     dword ptr [rbp+Block], 100h
0x18001859d  mov     [rbp+var_30], rcx
0x1800185a1  mov     rbx, r8
0x1800185a4  movups  xmmword ptr [rbp+Block+8], xmm0
0x1800185a8  cmp     eax, 14140007h
0x1800185ad  jz      loc_180018653
0x1800185b3  cmp     eax, 140F0006h
0x1800185b8  jz      short loc_18001860C
0x1800185ba  cmp     eax, 14130001h
0x1800185bf  jnz     loc_180018700
0x1800185c5  mov     r10, [r8+8]
0x1800185c9  mov     edx, ecx
0x1800185cb  mov     r9, [r8]
0x1800185ce  cmp     rdx, r9
0x1800185d1  jnb     short loc_180018624
0x1800185d3  lea     rax, [rdx+rdx*2]
0x1800185d7  cmp     dword ptr [r10+rax*8], 1020013h
0x1800185df  lea     r8, [r10+rax*8]
0x1800185e3  jnz     loc_18001879B
0x1800185e9  mov     eax, 300h
0x1800185ee  test    [r8+6], ax
0x1800185f3  jnz     short loc_180018624
0x1800185f5  mov     dword ptr [rbp+Block], ecx
0x1800185f8  cmp     dword ptr [r8+8], 1
0x1800185fd  jnz     loc_180018882
0x180018603  mov     dword ptr [rbp+Block+8], 1
0x18001860a  jmp     short loc_180018624
0x18001860c  lea     r8, [rbp+Block]
0x180018610  mov     rdx, rbx
0x180018613  mov     ecx, eax
0x180018615  call    ?CombineDataPropsToPoomProp@@YAJKAEBV?$Vector@U_SQLCEPROPVAL@@@Udm@@PEAUUdmPropertyValue@@@Z; CombineDataPropsToPoomProp(ulong,Udm::Vector<_SQLCEPROPVAL> const &,UdmPropertyValue *)
0x18001861a  mov     ebx, eax
0x18001861c  test    eax, eax
0x18001861e  js      loc_1800189D8
0x180018624  movups  xmm1, xmmword ptr [rbp+Block]
0x180018628  xor     eax, eax
0x18001862a  movsd   xmm2, [rbp+var_30]
0x18001862f  movups  xmmword ptr [rdi], xmm1
0x180018632  movsd   qword ptr [rdi+10h], xmm2
0x180018637  mov     rcx, [rbp+var_8]
0x18001863b  xor     rcx, rsp; StackCookie
0x18001863e  call    __security_check_cookie
0x180018643  mov     rbx, [rsp+70h+arg_18]
0x18001864b  add     rsp, 70h
0x18001864f  pop     rdi
0x180018650  pop     rsi
0x180018651  pop     rbp
0x180018652  retn
0x180018653  mov     r9, [r8+8]
0x180018657  mov     r8, [r8]
0x18001865a  cmp     rcx, r8
0x18001865d  jnb     short loc_180018624
0x18001865f  lea     rax, [rcx+rcx*2]
0x180018663  cmp     dword ptr [r9+rax*8], 30140013h
0x18001866b  lea     rdx, [r9+rax*8]
0x18001866f  jnz     loc_180018793
0x180018675  mov     eax, 300h
0x18001867a  test    [rdx+6], ax
0x18001867e  jnz     short loc_180018624
0x180018680  mov     rcx, [r10+30h]
0x180018684  xor     eax, eax
0x180018686  mov     esi, [rdx+8]
0x180018689  lea     rdx, [rbp+var_18]
0x18001868d  mov     qword ptr [rbp+var_28], rax
0x180018691  mov     [rbp+var_20], eax
0x180018694  mov     [rbp+var_18], rax
0x180018698  mov     [rbp+var_10], eax
0x18001869b  mov     rax, [rcx]
0x18001869e  mov     rax, [rax+50h]
0x1800186a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186a7  mov     ebx, eax
0x1800186a9  test    eax, eax
0x1800186ab  jns     loc_1800187D4
0x1800186b1  mov     r9d, 21h ; '!'
0x1800186b7  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800186be  mov     edx, 1
0x1800186c3  mov     ecx, eax
0x1800186c5  call    Log_HREvent
0x1800186ca  mov     r9d, 4A2h
0x1800186d0  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800186d7  mov     edx, 1
0x1800186dc  mov     ecx, ebx
0x1800186de  call    Log_HREvent
0x1800186e3  movzx   eax, word ptr [rbp+Block+4]
0x1800186e7  cmp     eax, 5
0x1800186ea  jz      loc_18001888F
0x1800186f0  cmp     eax, 6
0x1800186f3  jz      loc_1800188A6
0x1800186f9  mov     eax, ebx
0x1800186fb  jmp     loc_180018637
0x180018700  cmp     eax, 14100006h
0x180018705  ja      loc_1800187A3
0x18001870b  jz      loc_18001860C
0x180018711  cmp     eax, 140A0005h
0x180018716  jnz     loc_180018907
0x18001871c  mov     r10, [r8+8]
0x180018720  mov     rdx, rcx
0x180018723  mov     r9, [r8]
0x180018726  cmp     rdx, r9
0x180018729  jnb     loc_180018624
0x18001872f  lea     rax, [rdx+rdx*2]
0x180018733  cmp     dword ptr [r10+rax*8], 1E0064h
0x18001873b  lea     r8, [r10+rax*8]
0x18001873f  jnz     loc_18001880D
0x180018745  mov     eax, 300h
0x18001874a  test    [r8+6], ax
0x18001874f  jnz     loc_180018624
0x180018755  mov     qword ptr [rbp+var_28], rcx
0x180018759  lea     rdx, [rbp+var_28]
0x18001875d  lea     rcx, [r8+8]
0x180018761  call    cs:__imp_PimBinaryBodyToString
0x180018767  test    eax, eax
0x180018769  js      loc_180018624
0x18001876f  mov     rdx, qword ptr [rbp+var_28]
0x180018773  lea     rcx, [rbp+Block+8]
0x180018777  call    cs:__imp_DupString
0x18001877d  mov     ebx, eax
0x18001877f  test    eax, eax
0x180018781  js      loc_18001895F
0x180018787  and     dword ptr [rbp+Block], 0FFFFFEFFh
0x18001878e  jmp     loc_180018624
0x180018793  inc     rcx
0x180018796  jmp     loc_18001865A
0x18001879b  inc     rdx
0x18001879e  jmp     loc_1800185CE
0x1800187a3  cmp     eax, 14150005h
0x1800187a8  jnz     loc_180018839
0x1800187ae  mov     r11, [r8+8]
0x1800187b2  mov     r8, rcx
0x1800187b5  mov     r10, [rbx]
0x1800187b8  cmp     r8, r10
0x1800187bb  jnb     short loc_180018815
0x1800187bd  lea     rax, [r8+r8*2]
0x1800187c1  cmp     dword ptr [r11+rax*8], 10A0041h
0x1800187c9  lea     r9, [r11+rax*8]
0x1800187cd  jz      short loc_180018818
0x1800187cf  inc     r8
0x1800187d2  jmp     short loc_1800187B8
0x1800187d4  mov     eax, dword ptr [rbp+var_18]
0x1800187d7  lea     rdx, [rbp+var_28]
0x1800187db  and     dword ptr [rbp+Block], 0FFFFFEFFh
0x1800187e2  lea     rcx, [rbp+var_18]
0x1800187e6  mov     [rbp+var_28], eax
0x1800187e9  mov     [rbp+var_28+4], 70002h
0x1800187f0  mov     [rbp+var_20], esi
0x1800187f3  call    cs:__imp_UsOidToContactUdmId
0x1800187f9  movsd   xmm0, qword ptr [rax]
0x1800187fd  movsd   [rbp+Block+8], xmm0
0x180018802  mov     eax, [rax+8]
0x180018805  mov     dword ptr [rbp+var_30], eax
0x180018808  jmp     loc_180018624
0x18001880d  inc     rdx
0x180018810  jmp     loc_180018726
0x180018815  mov     r9, rcx
0x180018818  lea     r8, [rbp+Block]; struct UdmPropertyValue *
0x18001881c  mov     rcx, r9; struct _SQLCEPROPVAL *
0x18001881f  call    ?PoomRemoteIdToUdmRemoteId@@YAJPEBU_SQLCEPROPVAL@@AEBUUdmObjectId@@PEAUUdmPropertyValue@@@Z; PoomRemoteIdToUdmRemoteId(_SQLCEPROPVAL const *,UdmObjectId const &,UdmPropertyValue *)
0x180018824  mov     ebx, eax
0x180018826  test    eax, eax
0x180018828  jns     loc_180018624
0x18001882e  mov     r9d, 4E2h
0x180018834  jmp     loc_1800189DE
0x180018839  cmp     eax, 16020001h
0x18001883e  jnz     short loc_1800188AC
0x180018840  mov     r10, [r8+8]
0x180018844  mov     rdx, rcx
0x180018847  mov     r8, [r8]
0x18001884a  cmp     rdx, r8
0x18001884d  jnb     loc_180018624
0x180018853  lea     rax, [rdx+rdx*2]
0x180018857  cmp     dword ptr [r10+rax*8], 1C3000Bh
0x18001885f  lea     r9, [r10+rax*8]
0x180018863  jnz     short loc_18001888A
0x180018865  mov     eax, 300h
0x18001886a  test    [r9+6], ax
0x18001886f  jnz     loc_180018624
0x180018875  mov     dword ptr [rbp+Block], ecx
0x180018878  cmp     [r9+8], ecx
0x18001887c  jz      loc_180018603
0x180018882  mov     dword ptr [rbp+Block+8], ecx
0x180018885  jmp     loc_180018624
0x18001888a  inc     rdx
0x18001888d  jmp     short loc_18001884A
0x18001888f  mov     rcx, [rbp+Block+8]; Block
0x180018893  test    rcx, rcx
0x180018896  jz      loc_1800186F9
0x18001889c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800188a1  jmp     loc_1800186F9
0x1800188a6  mov     rcx, [rbp+var_30]
0x1800188aa  jmp     short loc_180018893
0x1800188ac  cmp     eax, 16070007h
0x1800188b1  jnz     loc_180018967
0x1800188b7  mov     r10, [r8+8]
0x1800188bb  mov     rdx, rcx
0x1800188be  mov     r8, [r8]
0x1800188c1  cmp     rdx, r8
0x1800188c4  jnb     loc_180018624
0x1800188ca  lea     rax, [rdx+rdx*2]
0x1800188ce  cmp     dword ptr [r10+rax*8], 43000013h
0x1800188d6  lea     r9, [r10+rax*8]
0x1800188da  jnz     short loc_180018902
0x1800188dc  mov     eax, 300h
0x1800188e1  test    [r9+6], ax
0x1800188e6  jnz     loc_180018624
0x1800188ec  mov     dword ptr [rbp+Block], ecx
0x1800188ef  mov     dword ptr [rbp+Block+8], ecx
0x1800188f2  mov     dword ptr [rbp+Block+0Ch], 29h ; ')'
0x1800188f9  mov     eax, [r9+8]
0x1800188fd  jmp     loc_180018805
0x180018902  inc     rdx
0x180018905  jmp     short loc_1800188C1
0x180018907  cmp     eax, 140B0006h
0x18001890c  jz      loc_18001860C
0x180018912  cmp     eax, 140C0006h
0x180018917  jz      loc_18001860C
0x18001891d  cmp     eax, 140D0006h
0x180018922  jz      loc_18001860C
0x180018928  cmp     eax, 140E0006h
0x18001892d  jz      loc_18001860C
0x180018933  mov     r9d, 504h
0x180018939  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018940  xor     edx, edx
0x180018942  mov     ecx, 80070057h
0x180018947  call    Log_HREvent
0x18001894c  lea     rcx, [rbp+Block]; this
0x180018950  call    ?FreeUdmPropVal@Udm@@YAXPEAUUdmPropertyValue@@@Z; Udm::FreeUdmPropVal(UdmPropertyValue *)
0x180018955  mov     eax, 80070057h
0x18001895a  jmp     loc_180018637
0x18001895f  mov     r9d, 4EEh
0x180018965  jmp     short loc_1800189DE
0x180018967  cmp     eax, 14110006h
0x18001896c  jz      loc_18001860C
0x180018972  cmp     eax, 14720005h
0x180018977  jnz     short loc_180018933
0x180018979  lea     rdx, [rbp+var_28]
0x18001897d  mov     [rbp+var_28], ecx
0x180018980  call    cs:__imp_GetContactDisplayAndSortPropertiesFromRegistry
0x180018986  mov     rdx, [rbx+8]; struct _USPROPVAL *
0x18001898a  mov     rcx, [rbx]; unsigned __int64
0x18001898d  mov     r8d, [rbp+var_28]; unsigned int
0x180018991  call    ?FindPropByUnistorePropId@@YAPEBU_USPROPVAL@@_KPEBU1@K@Z; FindPropByUnistorePropId(unsigned __int64,_USPROPVAL const *,ulong)
0x180018996  mov     rdx, rax
0x180018999  test    rax, rax
0x18001899c  jz      loc_180018624
0x1800189a2  mov     eax, 300h
0x1800189a7  test    [rdx+6], ax
0x1800189ab  jnz     loc_180018624
0x1800189b1  and     dword ptr [rbp+Block], 0FFFFFEFFh
0x1800189b8  lea     rcx, [rbp+Block+8]
0x1800189bc  mov     rdx, [rdx+8]
0x1800189c0  call    cs:__imp_DupString
0x1800189c6  mov     ebx, eax
0x1800189c8  test    eax, eax
0x1800189ca  jns     loc_180018624
0x1800189d0  mov     r9d, 4BEh
0x1800189d6  jmp     short loc_1800189DE
0x1800189d8  mov     r9d, 4FEh
0x1800189de  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800189e5  mov     edx, 1
0x1800189ea  mov     ecx, ebx
0x1800189ec  call    Log_HREvent
0x1800189f1  lea     rcx, [rbp+Block]; this
0x1800189f5  call    ?FreeUdmPropVal@Udm@@YAXPEAUUdmPropertyValue@@@Z; Udm::FreeUdmPropVal(UdmPropertyValue *)
0x1800189fa  mov     eax, ebx
0x1800189fc  jmp     loc_180018637
```
