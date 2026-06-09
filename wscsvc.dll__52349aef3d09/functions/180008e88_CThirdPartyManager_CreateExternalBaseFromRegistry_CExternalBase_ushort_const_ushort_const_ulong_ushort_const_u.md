# CThirdPartyManager::CreateExternalBaseFromRegistry(CExternalBase * *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,CList<ushort *,ushort *> *)

- ea: `0x180008e88`
- end: `0x18000935d`
- name: `?CreateExternalBaseFromRegistry@CThirdPartyManager@@IEAAJPEAPEAVCExternalBase@@PEBG1K11PEAV?$CList@PEAGPEAG@@@Z`
- size: `1237`
- prototype: `__int64 __fastcall(__int64, CExternalBase **, __int64, const unsigned __int16 *, int, wchar_t *String1, unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180016d50`

## callees

- `0x180005710`
- `0x180008910`
- `0x180008cc0`
- `0x180008e48`
- `0x180008e88`
- `0x180009390`
- `0x180009f40`
- `0x180016120`
- `0x180018774`
- `0x1800191c0`
- `0x18001b7f0`
- `0x18001fa14`
- `0x180028810`
- `0x180029158`
- `0x1800319bc`
- `0x180032c38`
- `0x180039614`
- `0x18003ea24`
- `0x180042010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180008f96`
- `msvcrt!_wcsicmp` at `0x180008f96`

## pseudocode

```c
__int64 __fastcall CThirdPartyManager::CreateExternalBaseFromRegistry(
        __int64 a1,
        CExternalBase **a2,
        __int64 a3,
        const unsigned __int16 *a4,
        int a5,
        wchar_t *String1,
        unsigned __int16 *a7,
        __int64 a8)
{
  wchar_t *v11; // rsi
  unsigned __int16 *v12; // r14
  CExternalBase *v13; // rbx
  unsigned __int16 *v14; // rax
  __int64 v15; // r9
  int v16; // edx
  int v17; // r8d
  __int64 v18; // rdi
  struct CExternalBase *HeadPosition; // rax
  const wchar_t *Next; // rax
  int v21; // edi
  struct CExternalBase *v22; // rsi
  unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  int v25; // ecx
  int v26; // r8d
  int v27; // eax
  CThirdPartyManager *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  int v31; // eax
  unsigned int v32; // r14d
  int v33; // edi
  unsigned int v34; // ecx
  int ProductNotification; // eax
  __int64 v36; // r8
  int v37; // eax
  char updated; // al
  unsigned int ProductState; // eax
  CExternalBase *v40; // rax
  struct CExternalBase *v42; // [rsp+30h] [rbp-10h] BYREF
  struct CExternalBase *v43; // [rsp+38h] [rbp-8h] BYREF
  struct CExternalBase *v45; // [rsp+90h] [rbp+50h] BYREF

  if ( !a3 )
    return 2147942487LL;
  if ( !a4 )
    return 2147942487LL;
  v11 = String1;
  if ( !String1 )
    return 2147942487LL;
  v12 = a7;
  if ( !a7 )
    return 2147942487LL;
  v13 = 0;
  v45 = 0;
  v42 = 0;
  if ( (*(int (__fastcall **)(__int64, struct CExternalBase **))(*(_QWORD *)a1 + 8LL))(a1, &v42) >= 0 )
  {
    v14 = (unsigned __int16 *)*((_QWORD *)v42 + 1);
    v15 = a3 - (_QWORD)v14;
    do
    {
      v16 = *(unsigned __int16 *)((char *)v14 + v15);
      v17 = *v14 - v16;
      if ( v17 )
        break;
      ++v14;
    }
    while ( v16 );
    if ( v17 )
    {
      if ( v42 )
        (**(void (__fastcall ***)(struct CExternalBase *, __int64))v42)(v42, 1);
    }
    else
    {
      v43 = v42;
      std::unique_ptr<CExternalBase>::operator=((__int64 (__fastcall ****)(_QWORD, __int64))&v45, &v43);
      CommonUtil::CAutoUniquePtr<CExternalBase,void>::~CAutoUniquePtr<CExternalBase,void>((__int64 (__fastcall ****)(_QWORD, __int64))&v43);
      v13 = v45;
    }
    v42 = 0;
    if ( v13 )
      goto LABEL_38;
  }
  v18 = a8;
  if ( a8 && *(int *)(a8 + 48) > 0 )
  {
    HeadPosition = (struct CExternalBase *)CList<unsigned short *,unsigned short *>::GetHeadPosition(a8);
    v43 = HeadPosition;
    while ( HeadPosition )
    {
      Next = (const wchar_t *)CList<unsigned short *,unsigned short *>::GetNext(v18, &v43);
      if ( !_wcsicmp(v11, Next) )
      {
        *(_DWORD *)(a1 + 84) = 1;
        EvtLog_LogInformational(0x4000000Du);
        v21 = -2147024894;
        goto LABEL_55;
      }
      HeadPosition = v43;
    }
  }
  v43 = 0;
  v21 = CSecurityVerificationManager::CreateExternalBaseFromPESettings(
          *(CSecurityVerificationManager **)(a1 + 64),
          v11,
          &v43);
  v22 = v43;
  if ( v43 )
  {
    CommonUtil::CAutoUniquePtr<CExternalBase,void>::~CAutoUniquePtr<CExternalBase,void>((__int64 (__fastcall ****)(_QWORD, __int64))&v45);
    v13 = v22;
    v45 = v22;
  }
  if ( v21 >= 0 )
  {
    v23 = (unsigned __int16 *)*((_QWORD *)v13 + 1);
    v24 = a3 - (_QWORD)v23;
    do
    {
      v25 = *(unsigned __int16 *)((char *)v23 + v24);
      v26 = *v23 - v25;
      if ( v26 )
        break;
      ++v23;
    }
    while ( v25 );
    if ( v26 )
      v21 = -2147024883;
    if ( v21 < 0 )
      goto LABEL_55;
    v27 = CExternalBase::SetDisplayName(v13, a4);
    v21 = v27;
    if ( v27 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v29 = 35;
        v30 = (unsigned int)v27;
LABEL_54:
        WPP_SF_d(*((_QWORD *)v28 + 2), v29, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids, v30);
        goto LABEL_55;
      }
      goto LABEL_55;
    }
    v31 = CExternalBase::SetPath(v13, v12);
    if ( v31 < 0
      && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        WPP_945edad5fd7435d1f807bc12083ac763_Traceguids,
        (unsigned int)v31);
    }
LABEL_38:
    v32 = a5 | 0x40000;
    v33 = a5 & 0xB0000 | 0x40000;
    v34 = v33 | *((_DWORD *)v13 + 20) & 0xFFF0FFFF;
    *((_DWORD *)v13 + 20) = v34;
    *((_DWORD *)v13 + 20) = v32 & 0x10 | v34 & 0xFFFFFF0F;
    ProductNotification = ExtractProductNotification(v32);
    *((_DWORD *)v13 + 20) &= 0xFF0FFFFF;
    *((_DWORD *)v13 + 20) |= ProductNotification;
    if ( *(_DWORD *)(a1 + 80) && (unsigned int)ExtractProductState(v32) == 4096 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids, a3);
      }
      CExternalBase::SetProductState(v13, 0, v36);
      v37 = (*(__int64 (__fastcall **)(CExternalBase *))(*(_QWORD *)v13 + 24LL))(v13);
      updated = CExternalBase::UpdatePersistentStoreRegistry((__int64)v13, v37, 4);
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          (unsigned int)WPP_945edad5fd7435d1f807bc12083ac763_Traceguids,
          a3,
          updated);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids, a3);
      }
      ProductState = ExtractProductState(v32);
      CExternalBase::SetProductStateEx(v13, ProductState);
    }
    v40 = v13;
    v13 = 0;
    *a2 = v40;
    v21 = 0;
    goto LABEL_55;
  }
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v29 = 34;
    v30 = (unsigned int)v21;
    goto LABEL_54;
  }
LABEL_55:
  if ( v13 )
    (**(void (__fastcall ***)(CExternalBase *, __int64))v13)(v13, 1);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180008e88  mov     [rsp-38h+arg_0], rbx
0x180008e8d  mov     [rsp-38h+arg_8], rdx
0x180008e92  push    rbp
0x180008e93  push    rsi
0x180008e94  push    rdi
0x180008e95  push    r12
0x180008e97  push    r13
0x180008e99  push    r14
0x180008e9b  push    r15
0x180008e9d  mov     rbp, rsp
0x180008ea0  sub     rsp, 40h
0x180008ea4  mov     r15, r9
0x180008ea7  mov     r12, r8
0x180008eaa  mov     r13, rcx
0x180008ead  test    r8, r8
0x180008eb0  jz      loc_180009340
0x180008eb6  test    r9, r9
0x180008eb9  jz      loc_180009340
0x180008ebf  mov     rsi, [rbp+String1]
0x180008ec3  test    rsi, rsi
0x180008ec6  jz      loc_180009340
0x180008ecc  mov     r14, [rbp+arg_30]
0x180008ed0  test    r14, r14
0x180008ed3  jz      loc_180009340
0x180008ed9  xor     ebx, ebx
0x180008edb  mov     [rbp+arg_10], rbx
0x180008edf  mov     [rbp+var_10], rbx
0x180008ee3  mov     rax, [rcx]
0x180008ee6  lea     rdx, [rbp+var_10]
0x180008eea  mov     rax, [rax+8]
0x180008eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef3  test    eax, eax
0x180008ef5  js      short loc_180008F64
0x180008ef7  mov     rcx, [rbp+var_10]
0x180008efb  mov     rax, [rcx+8]
0x180008eff  mov     r9, r12
0x180008f02  sub     r9, rax
0x180008f05  movzx   r8d, word ptr [rax]
0x180008f09  movzx   edx, word ptr [rax+r9]
0x180008f0e  sub     r8d, edx
0x180008f11  jnz     short loc_180008F1B
0x180008f13  add     rax, 2
0x180008f17  test    edx, edx
0x180008f19  jnz     short loc_180008F05
0x180008f1b  test    r8d, r8d
0x180008f1e  jnz     short loc_180008F40
0x180008f20  mov     [rbp+var_8], rcx
0x180008f24  lea     rdx, [rbp+var_8]
0x180008f28  lea     rcx, [rbp+arg_10]
0x180008f2c  call    ??4?$unique_ptr@VCExternalBase@@U?$default_delete@VCExternalBase@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CExternalBase>::operator=(std::unique_ptr<CExternalBase> &&)
0x180008f31  lea     rcx, [rbp+var_8]
0x180008f35  call    ??1?$CAutoUniquePtr@VCExternalBase@@X@CommonUtil@@QEAA@XZ; CommonUtil::CAutoUniquePtr<CExternalBase,void>::~CAutoUniquePtr<CExternalBase,void>(void)
0x180008f3a  mov     rbx, [rbp+arg_10]
0x180008f3e  jmp     short loc_180008F55
0x180008f40  test    rcx, rcx
0x180008f43  jz      short loc_180008F55
0x180008f45  mov     rax, [rcx]
0x180008f48  mov     edx, 1
0x180008f4d  mov     rax, [rax]
0x180008f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f55  xor     eax, eax
0x180008f57  mov     [rbp+var_10], rax
0x180008f5b  test    rbx, rbx
0x180008f5e  jnz     loc_1800090AF
0x180008f64  mov     rdi, [rbp+arg_38]
0x180008f68  test    rdi, rdi
0x180008f6b  jz      short loc_180008FC2
0x180008f6d  cmp     dword ptr [rdi+30h], 0
0x180008f71  jle     short loc_180008FC2
0x180008f73  mov     rcx, rdi
0x180008f76  call    ?GetHeadPosition@?$CList@PEAGPEAG@@QEBAPEAU_CListElement@@XZ; CList<ushort *,ushort *>::GetHeadPosition(void)
0x180008f7b  mov     [rbp+var_8], rax
0x180008f7f  test    rax, rax
0x180008f82  jz      short loc_180008FC2
0x180008f84  lea     rdx, [rbp+var_8]
0x180008f88  mov     rcx, rdi
0x180008f8b  call    ?GetNext@?$CList@PEAGPEAG@@QEAAPEAGAEAPEAU_CListElement@@@Z; CList<ushort *,ushort *>::GetNext(_CListElement * &)
0x180008f90  mov     rdx, rax; String2
0x180008f93  mov     rcx, rsi; String1
0x180008f96  call    cs:__imp__wcsicmp
0x180008f9c  test    eax, eax
0x180008f9e  jz      short loc_180008FA6
0x180008fa0  mov     rax, [rbp+var_8]
0x180008fa4  jmp     short loc_180008F7F
0x180008fa6  mov     dword ptr [r13+54h], 1
0x180008fae  mov     ecx, 4000000Dh; dwEventID
0x180008fb3  call    ?EvtLog_LogInformational@@YAXK@Z; EvtLog_LogInformational(ulong)
0x180008fb8  mov     edi, 80070002h
0x180008fbd  jmp     loc_180009324
0x180008fc2  mov     [rbp+var_8], 0
0x180008fca  lea     r8, [rbp+var_8]; struct CExternalBase **
0x180008fce  mov     rdx, rsi; unsigned __int16 *
0x180008fd1  mov     rcx, [r13+40h]; this
0x180008fd5  call    ?CreateExternalBaseFromPESettings@CSecurityVerificationManager@@QEAAJPEAGPEAPEAVCExternalBase@@@Z; CSecurityVerificationManager::CreateExternalBaseFromPESettings(ushort *,CExternalBase * *)
0x180008fda  mov     edi, eax
0x180008fdc  mov     rsi, [rbp+var_8]
0x180008fe0  test    rsi, rsi
0x180008fe3  jz      short loc_180008FF5
0x180008fe5  lea     rcx, [rbp+arg_10]
0x180008fe9  call    ??1?$CAutoUniquePtr@VCExternalBase@@X@CommonUtil@@QEAA@XZ; CommonUtil::CAutoUniquePtr<CExternalBase,void>::~CAutoUniquePtr<CExternalBase,void>(void)
0x180008fee  mov     rbx, rsi
0x180008ff1  mov     [rbp+arg_10], rbx
0x180008ff5  test    edi, edi
0x180008ff7  js      loc_1800092F2
0x180008ffd  mov     rax, [rbx+8]
0x180009001  mov     rdx, r12
0x180009004  sub     rdx, rax
0x180009007  movzx   r8d, word ptr [rax]
0x18000900b  movzx   ecx, word ptr [rax+rdx]
0x18000900f  sub     r8d, ecx
0x180009012  jnz     short loc_18000901C
0x180009014  add     rax, 2
0x180009018  test    ecx, ecx
0x18000901a  jnz     short loc_180009007
0x18000901c  mov     eax, 8007000Dh
0x180009021  test    r8d, r8d
0x180009024  cmovnz  edi, eax
0x180009027  test    edi, edi
0x180009029  js      loc_180009324
0x18000902f  mov     rdx, r15; unsigned __int16 *
0x180009032  mov     rcx, rbx; this
0x180009035  call    ?SetDisplayName@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetDisplayName(ushort const *)
0x18000903a  mov     edi, eax
0x18000903c  test    eax, eax
0x18000903e  jns     short loc_18000906E
0x180009040  mov     rcx, cs:WPP_GLOBAL_Control
0x180009047  lea     rsi, WPP_GLOBAL_Control
0x18000904e  cmp     rcx, rsi
0x180009051  jz      loc_180009324
0x180009057  test    byte ptr [rcx+1Ch], 1
0x18000905b  jz      loc_180009324
0x180009061  mov     edx, 23h ; '#'
0x180009066  mov     r9d, eax
0x180009069  jmp     loc_180009313
0x18000906e  mov     rdx, r14; unsigned __int16 *
0x180009071  mov     rcx, rbx; this
0x180009074  call    ?SetPath@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetPath(ushort const *)
0x180009079  test    eax, eax
0x18000907b  jns     short loc_1800090AF
0x18000907d  mov     r10, cs:WPP_GLOBAL_Control
0x180009084  lea     rdx, WPP_GLOBAL_Control
0x18000908b  cmp     r10, rdx
0x18000908e  jz      short loc_1800090BD
0x180009090  test    byte ptr [r10+1Ch], 1
0x180009095  jz      short loc_1800090BD
0x180009097  mov     edx, 24h ; '$'
0x18000909c  mov     r9d, eax
0x18000909f  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x1800090a6  mov     rcx, [r10+10h]
0x1800090aa  call    WPP_SF_d
0x1800090af  lea     rdx, WPP_GLOBAL_Control
0x1800090b6  mov     r10, cs:WPP_GLOBAL_Control
0x1800090bd  mov     r14d, [rbp+arg_20]
0x1800090c1  bts     r14d, 12h
0x1800090c6  mov     edi, r14d
0x1800090c9  mov     r15d, 0F0000h
0x1800090cf  and     edi, r15d
0x1800090d2  mov     esi, edi
0x1800090d4  and     esi, r15d
0x1800090d7  cmp     esi, edi
0x1800090d9  jz      short loc_18000910D
0x1800090db  cmp     r10, rdx
0x1800090de  jz      short loc_18000910B
0x1800090e0  test    byte ptr [r10+1Ch], 1
0x1800090e5  jz      short loc_18000910B
0x1800090e7  mov     edx, 0Dh
0x1800090ec  mov     [rsp+40h+var_20], r15d
0x1800090f1  mov     r9d, edi
0x1800090f4  mov     rcx, [r10+10h]
0x1800090f8  call    WPP_SF_DD
0x1800090fd  mov     r10, cs:WPP_GLOBAL_Control
0x180009104  lea     rdx, WPP_GLOBAL_Control
0x18000910b  mov     edi, esi
0x18000910d  mov     ecx, [rbx+50h]
0x180009110  mov     r9d, ecx
0x180009113  and     r9d, r15d
0x180009116  mov     eax, r9d
0x180009119  and     eax, r15d
0x18000911c  cmp     eax, r9d
0x18000911f  jz      short loc_18000914A
0x180009121  cmp     r10, rdx
0x180009124  jz      short loc_18000914A
0x180009126  test    byte ptr [r10+1Ch], 1
0x18000912b  jz      short loc_18000914A
0x18000912d  mov     edx, 0Dh
0x180009132  mov     [rsp+40h+var_20], r15d
0x180009137  mov     rcx, [r10+10h]
0x18000913b  call    WPP_SF_DD
0x180009140  mov     ecx, [rbx+50h]
0x180009143  lea     rdx, WPP_GLOBAL_Control
0x18000914a  and     ecx, 0FFF0FFFFh
0x180009150  or      ecx, edi
0x180009152  mov     [rbx+50h], ecx
0x180009155  mov     edi, r14d
0x180009158  and     edi, 10h
0x18000915b  mov     esi, edi
0x18000915d  mov     r15d, 0F0h
0x180009163  and     esi, r15d
0x180009166  mov     r8, cs:WPP_GLOBAL_Control
0x18000916d  cmp     esi, edi
0x18000916f  jz      short loc_1800091A6
0x180009171  cmp     r8, rdx
0x180009174  jz      short loc_1800091A4
0x180009176  test    byte ptr [r8+1Ch], 1
0x18000917b  jz      short loc_1800091A4
0x18000917d  mov     edx, 0Ah
0x180009182  mov     [rsp+40h+var_20], r15d
0x180009187  mov     r9d, edi
0x18000918a  mov     rcx, [r8+10h]
0x18000918e  call    WPP_SF_DD
0x180009193  mov     ecx, [rbx+50h]
0x180009196  mov     r8, cs:WPP_GLOBAL_Control
0x18000919d  lea     rdx, WPP_GLOBAL_Control
0x1800091a4  mov     edi, esi
0x1800091a6  mov     r9d, ecx
0x1800091a9  and     r9d, 10h
0x1800091ad  mov     eax, r9d
0x1800091b0  and     eax, r15d
0x1800091b3  cmp     eax, r9d
0x1800091b6  jz      short loc_1800091DA
0x1800091b8  cmp     r8, rdx
0x1800091bb  jz      short loc_1800091DA
0x1800091bd  test    byte ptr [r8+1Ch], 1
0x1800091c2  jz      short loc_1800091DA
0x1800091c4  mov     edx, 0Ah
0x1800091c9  mov     [rsp+40h+var_20], r15d
0x1800091ce  mov     rcx, [r8+10h]
0x1800091d2  call    WPP_SF_DD
0x1800091d7  mov     ecx, [rbx+50h]
0x1800091da  and     ecx, 0FFFFFF0Fh
0x1800091e0  or      ecx, edi
0x1800091e2  mov     [rbx+50h], ecx
0x1800091e5  mov     ecx, r14d
0x1800091e8  call    ?ExtractProductNotification@@YA?AW4ProductNotification@@K@Z; ExtractProductNotification(ulong)
0x1800091ed  and     dword ptr [rbx+50h], 0FF0FFFFFh
0x1800091f4  or      [rbx+50h], eax
0x1800091f7  cmp     dword ptr [r13+50h], 0
0x1800091fc  jz      loc_18000929F
0x180009202  mov     ecx, r14d
0x180009205  call    ?ExtractProductState@@YA?AW4ProductState@@K@Z; ExtractProductState(ulong)
0x18000920a  cmp     eax, 1000h
0x18000920f  jnz     loc_18000929F
0x180009215  mov     rcx, cs:WPP_GLOBAL_Control
0x18000921c  lea     rsi, WPP_GLOBAL_Control
0x180009223  cmp     rcx, rsi
0x180009226  jz      short loc_180009246
0x180009228  test    byte ptr [rcx+1Ch], 4
0x18000922c  jz      short loc_180009246
0x18000922e  mov     edx, 26h ; '&'
0x180009233  mov     r9, r12
0x180009236  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x18000923d  mov     rcx, [rcx+10h]
0x180009241  call    WPP_SF_S
0x180009246  xor     edx, edx
0x180009248  mov     rcx, rbx
0x18000924b  call    ?SetProductState@CExternalBase@@QEAAHW4ProductState@@@Z; CExternalBase::SetProductState(ProductState)
0x180009250  mov     rax, [rbx]
0x180009253  mov     rcx, rbx
0x180009256  mov     rax, [rax+18h]
0x18000925a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000925f  mov     r8d, 4
0x180009265  mov     edx, eax
0x180009267  mov     rcx, rbx
0x18000926a  call    ?UpdatePersistentStoreRegistry@CExternalBase@@QEAAJW4_SECURITY_PRODUCT_TYPE@@W4_DATASTORE_BITMASK@@@Z; CExternalBase::UpdatePersistentStoreRegistry(_SECURITY_PRODUCT_TYPE,_DATASTORE_BITMASK)
0x18000926f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009276  cmp     rcx, rsi
0x180009279  jz      short loc_1800092E2
0x18000927b  test    byte ptr [rcx+1Ch], 4
0x18000927f  jz      short loc_1800092E2
0x180009281  mov     edx, 27h ; '''
0x180009286  mov     [rsp+40h+var_20], eax
0x18000928a  mov     r9, r12
0x18000928d  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180009294  mov     rcx, [rcx+10h]
0x180009298  call    WPP_SF_SD
0x18000929d  jmp     short loc_1800092E2
0x18000929f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092a6  lea     rsi, WPP_GLOBAL_Control
0x1800092ad  cmp     rcx, rsi
0x1800092b0  jz      short loc_1800092D0
0x1800092b2  test    byte ptr [rcx+1Ch], 4
0x1800092b6  jz      short loc_1800092D0
0x1800092b8  mov     edx, 25h ; '%'
0x1800092bd  mov     r9, r12
0x1800092c0  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x1800092c7  mov     rcx, [rcx+10h]
0x1800092cb  call    WPP_SF_S
0x1800092d0  mov     ecx, r14d
0x1800092d3  call    ?ExtractProductState@@YA?AW4ProductState@@K@Z; ExtractProductState(ulong)
0x1800092d8  mov     edx, eax
0x1800092da  mov     rcx, rbx
0x1800092dd  call    ?SetProductStateEx@CExternalBase@@QEAAHW4ProductState@@@Z; CExternalBase::SetProductStateEx(ProductState)
0x1800092e2  mov     rax, rbx
0x1800092e5  xor     ebx, ebx
0x1800092e7  mov     rcx, [rbp+arg_8]
0x1800092eb  mov     [rcx], rax
0x1800092ee  xor     edi, edi
0x1800092f0  jmp     short loc_180009324
0x1800092f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092f9  lea     rsi, WPP_GLOBAL_Control
  ... truncated ...
```
