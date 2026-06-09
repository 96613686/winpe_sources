# CWbemNamespace::MUILocaleUpdateNSInstance(CWbemInstance *)

- ea: `0x1800733a4`
- end: `0x18007372d`
- name: `?MUILocaleUpdateNSInstance@CWbemNamespace@@IEAAJPEAVCWbemInstance@@@Z`
- size: `905`
- prototype: `__int64 __fastcall(CWbemNamespace *__hidden this, struct CWbemInstance *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180049d34`

## callees

- `0x18000b104`
- `0x18000b140`
- `0x1800733a4`
- `0x18008d4a8`
- `0x1800ce4d2`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?ms_XXX_Locale_To_LCID@CMUILocale@@SAJPEBGPEAK@Z` at `0x180073486`
- `wbemcomn!?ms_XXX_Locale_To_LCID@CMUILocale@@SAJPEBGPEAK@Z` at `0x180073486`
- `wbemcomn!?CheckLangNeutral@CMUILocale@@SAJPEBGPEA_N@Z` at `0x1800734f9`
- `wbemcomn!?CheckLangNeutral@CMUILocale@@SAJPEBGPEA_N@Z` at `0x1800734f9`
- `wbemcomn!?LocaleName_To_LCID@CMUILocale@@SAJPEBGPEA_NPEAK@Z` at `0x180073561`
- `wbemcomn!?LocaleName_To_LCID@CMUILocale@@SAJPEBGPEA_NPEAK@Z` at `0x180073561`
- `wbemcomn!?LCID_To_ms_XXX_Format@CMUILocale@@SAJKPEAG_K@Z` at `0x1800735c3`
- `wbemcomn!?LCID_To_ms_XXX_Format@CMUILocale@@SAJKPEAG_K@Z` at `0x1800735c3`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x18007345a`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x18007345a`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180073428`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180073428`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18007346d`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18007346d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800736b1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180073706`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800736b1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180073706`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x1800734df`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x1800734df`
- `wbemcomn!GetMemLogObject` at `0x180073492`
- `wbemcomn!GetMemLogObject` at `0x180073505`
- `wbemcomn!GetMemLogObject` at `0x18007356d`
- `wbemcomn!GetMemLogObject` at `0x1800735cf`
- `wbemcomn!GetMemLogObject` at `0x180073655`
- `wbemcomn!GetMemLogObject` at `0x1800736bb`
- `wbemcomn!GetMemLogObject` at `0x180073492`
- `wbemcomn!GetMemLogObject` at `0x180073505`
- `wbemcomn!GetMemLogObject` at `0x18007356d`
- `wbemcomn!GetMemLogObject` at `0x1800735cf`
- `wbemcomn!GetMemLogObject` at `0x180073655`
- `wbemcomn!GetMemLogObject` at `0x1800736bb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007349d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073510`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073578`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800735da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073660`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800736cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007349d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073510`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073578`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800735da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073660`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800736cb`
- `OLEAUT32!__imp_VariantInit` at `0x180073613`
- `OLEAUT32!__imp_VariantInit` at `0x180073613`
- `OLEAUT32!__imp_VariantClear` at `0x180073698`
- `OLEAUT32!__imp_VariantClear` at `0x1800736a5`
- `OLEAUT32!__imp_VariantClear` at `0x180073698`
- `OLEAUT32!__imp_VariantClear` at `0x1800736a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemNamespace::MUILocaleUpdateNSInstance(CWbemNamespace *this, struct CWbemInstance *a2)
{
  const unsigned __int16 *LPWSTR; // rdi
  int v4; // ebx
  CMemoryLog *v5; // rax
  CClientCnt *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  CMemoryLog *v9; // rax
  CMemoryLog *v10; // rax
  CMemoryLog *v11; // rax
  CMemoryLog *v12; // rax
  CMemoryLog *MemLogObject; // rax
  bool v15; // [rsp+30h] [rbp-D0h] BYREF
  bool v16; // [rsp+31h] [rbp-CFh] BYREF
  unsigned int v17; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v18[32]; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR psz; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v21[526]; // [rsp+72h] [rbp-8Eh] BYREF

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
  }
  psz = 0;
  memset_0(v21, 0, 0x206u);
  CVar::CVar((CVar *)v18);
  if ( (*(int (__fastcall **)(struct CWbemInstance *, const wchar_t *, _BYTE *))(*(_QWORD *)a2 + 776LL))(
         a2,
         L"Name",
         v18) < 0
    || CVar::IsNull((CVar *)v18) )
  {
    MemLogObject = GetMemLogObject();
    v4 = -2147217394;
    CMemoryLog::Write(MemLogObject, -2147217394);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v7 = 133;
    v8 = 2147749902LL;
    goto LABEL_45;
  }
  LPWSTR = CVar::GetLPWSTR((CVar *)v18);
  v17 = 0;
  v4 = CMUILocale::ms_XXX_Locale_To_LCID(LPWSTR, &v17);
  if ( v4 < 0 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, v4);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v7 = 134;
    goto LABEL_12;
  }
  if ( v17 || (unsigned __int8)CWbemInstallObject::IsOffline() )
    goto LABEL_40;
  v15 = 0;
  v4 = CMUILocale::CheckLangNeutral(LPWSTR, &v15);
  if ( v4 < 0 )
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, v4);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v7 = 135;
    goto LABEL_12;
  }
  if ( !v15 )
  {
    v16 = 0;
    v4 = CMUILocale::LocaleName_To_LCID(LPWSTR, &v16, &v17);
    if ( v4 < 0 )
    {
      v10 = GetMemLogObject();
      CMemoryLog::Write(v10, v4);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v7 = 136;
      goto LABEL_12;
    }
    if ( v17 )
    {
      v4 = CMUILocale::LCID_To_ms_XXX_Format(v17, &psz, 0x104u);
      if ( v4 < 0 )
      {
        v11 = GetMemLogObject();
        CMemoryLog::Write(v11, v4);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_46;
        }
        v7 = 137;
LABEL_12:
        v8 = (unsigned int)v4;
LABEL_45:
        WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v8);
        goto LABEL_46;
      }
      VariantInit(&pvarg);
      CVARIANT::SetStr(&pvarg, &psz);
      v4 = (*(__int64 (__fastcall **)(struct CWbemInstance *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)a2 + 40LL))(
             a2,
             L"Name",
             0,
             &pvarg,
             0);
      if ( v4 < 0 )
      {
        v12 = GetMemLogObject();
        CMemoryLog::Write(v12, v4);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            138,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)v4);
        }
        VariantClear(&pvarg);
        goto LABEL_46;
      }
      VariantClear(&pvarg);
    }
LABEL_40:
    CVar::~CVar((CVar *)v18);
    return 0;
  }
  v4 = 0;
LABEL_46:
  CVar::~CVar((CVar *)v18);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800733a4  push    rbp
0x1800733a6  push    rbx
0x1800733a7  push    rsi
0x1800733a8  push    rdi
0x1800733a9  push    r12
0x1800733ab  push    r13
0x1800733ad  lea     rbp, [rsp-198h]
0x1800733b5  sub     rsp, 298h
0x1800733bc  mov     rax, cs:__security_cookie
0x1800733c3  xor     rax, rsp
0x1800733c6  mov     [rbp+1C0h+var_40], rax
0x1800733cd  mov     rsi, rdx
0x1800733d0  lea     r13, WPP_GLOBAL_Control
0x1800733d7  lea     r12, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800733de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800733e5  cmp     rcx, r13
0x1800733e8  jz      short loc_18007340A
0x1800733ea  test    byte ptr [rcx+1Ch], 1
0x1800733ee  jz      short loc_18007340A
0x1800733f0  cmp     byte ptr [rcx+19h], 5
0x1800733f4  jb      short loc_18007340A
0x1800733f6  mov     edx, 84h
0x1800733fb  mov     r9, rsi
0x1800733fe  mov     r8, r12
0x180073401  mov     rcx, [rcx+10h]
0x180073405  call    WPP_SF_q
0x18007340a  xor     eax, eax
0x18007340c  mov     [rsp+2C0h+psz], ax
0x180073411  xor     edx, edx; Val
0x180073413  mov     r8d, 206h; Size
0x180073419  lea     rcx, [rsp+2C0h+var_24E]; void *
0x18007341e  call    memset_0
0x180073423  lea     rcx, [rsp+2C0h+var_288]
0x180073428  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18007342e  nop
0x18007342f  mov     rax, [rsi]
0x180073432  lea     r8, [rsp+2C0h+var_288]
0x180073437  lea     rdx, aName; "Name"
0x18007343e  mov     rcx, rsi
0x180073441  mov     rax, [rax+308h]
0x180073448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007344d  test    eax, eax
0x18007344f  js      loc_1800736BB
0x180073455  lea     rcx, [rsp+2C0h+var_288]
0x18007345a  call    cs:__imp_?IsNull@CVar@@QEAAHXZ; CVar::IsNull(void)
0x180073460  test    eax, eax
0x180073462  jnz     loc_1800736BB
0x180073468  lea     rcx, [rsp+2C0h+var_288]
0x18007346d  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x180073473  mov     rdi, rax
0x180073476  mov     [rsp+2C0h+var_28C], 0
0x18007347e  lea     rdx, [rsp+2C0h+var_28C]
0x180073483  mov     rcx, rax
0x180073486  call    cs:__imp_?ms_XXX_Locale_To_LCID@CMUILocale@@SAJPEBGPEAK@Z; CMUILocale::ms_XXX_Locale_To_LCID(ushort const *,ulong *)
0x18007348c  mov     ebx, eax
0x18007348e  test    eax, eax
0x180073490  jns     short loc_1800734D4
0x180073492  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180073498  mov     edx, ebx
0x18007349a  mov     rcx, rax
0x18007349d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800734a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800734aa  cmp     rcx, r13
0x1800734ad  jz      loc_180073701
0x1800734b3  test    byte ptr [rcx+1Ch], 1
0x1800734b7  jz      loc_180073701
0x1800734bd  cmp     byte ptr [rcx+19h], 2
0x1800734c1  jb      loc_180073701
0x1800734c7  mov     edx, 86h
0x1800734cc  mov     r9d, ebx
0x1800734cf  jmp     loc_1800736F4
0x1800734d4  cmp     [rsp+2C0h+var_28C], 0
0x1800734d9  jnz     loc_1800736AC
0x1800734df  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x1800734e5  test    al, al
0x1800734e7  jnz     loc_1800736AC
0x1800734ed  mov     [rsp+2C0h+var_290], al
0x1800734f1  lea     rdx, [rsp+2C0h+var_290]
0x1800734f6  mov     rcx, rdi
0x1800734f9  call    cs:__imp_?CheckLangNeutral@CMUILocale@@SAJPEBGPEA_N@Z; CMUILocale::CheckLangNeutral(ushort const *,bool *)
0x1800734ff  mov     ebx, eax
0x180073501  test    eax, eax
0x180073503  jns     short loc_180073541
0x180073505  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007350b  mov     edx, ebx
0x18007350d  mov     rcx, rax
0x180073510  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180073516  mov     rcx, cs:WPP_GLOBAL_Control
0x18007351d  cmp     rcx, r13
0x180073520  jz      loc_180073701
0x180073526  test    byte ptr [rcx+1Ch], 1
0x18007352a  jz      loc_180073701
0x180073530  cmp     byte ptr [rcx+19h], 2
0x180073534  jb      loc_180073701
0x18007353a  mov     edx, 87h
0x18007353f  jmp     short loc_1800734CC
0x180073541  cmp     [rsp+2C0h+var_290], 0
0x180073546  jz      short loc_18007354F
0x180073548  xor     ebx, ebx
0x18007354a  jmp     loc_180073701
0x18007354f  mov     [rsp+2C0h+var_28F], 0
0x180073554  lea     r8, [rsp+2C0h+var_28C]
0x180073559  lea     rdx, [rsp+2C0h+var_28F]
0x18007355e  mov     rcx, rdi
0x180073561  call    cs:__imp_?LocaleName_To_LCID@CMUILocale@@SAJPEBGPEA_NPEAK@Z; CMUILocale::LocaleName_To_LCID(ushort const *,bool *,ulong *)
0x180073567  mov     ebx, eax
0x180073569  test    eax, eax
0x18007356b  jns     short loc_1800735AC
0x18007356d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180073573  mov     edx, ebx
0x180073575  mov     rcx, rax
0x180073578  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007357e  mov     rcx, cs:WPP_GLOBAL_Control
0x180073585  cmp     rcx, r13
0x180073588  jz      loc_180073701
0x18007358e  test    byte ptr [rcx+1Ch], 1
0x180073592  jz      loc_180073701
0x180073598  cmp     byte ptr [rcx+19h], 2
0x18007359c  jb      loc_180073701
0x1800735a2  mov     edx, 88h
0x1800735a7  jmp     loc_1800734CC
0x1800735ac  mov     ecx, [rsp+2C0h+var_28C]
0x1800735b0  test    ecx, ecx
0x1800735b2  jz      loc_1800736AC
0x1800735b8  mov     r8d, 104h
0x1800735be  lea     rdx, [rsp+2C0h+psz]
0x1800735c3  call    cs:__imp_?LCID_To_ms_XXX_Format@CMUILocale@@SAJKPEAG_K@Z; CMUILocale::LCID_To_ms_XXX_Format(ulong,ushort *,unsigned __int64)
0x1800735c9  mov     ebx, eax
0x1800735cb  test    eax, eax
0x1800735cd  jns     short loc_18007360E
0x1800735cf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800735d5  mov     edx, ebx
0x1800735d7  mov     rcx, rax
0x1800735da  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800735e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800735e7  cmp     rcx, r13
0x1800735ea  jz      loc_180073701
0x1800735f0  test    byte ptr [rcx+1Ch], 1
0x1800735f4  jz      loc_180073701
0x1800735fa  cmp     byte ptr [rcx+19h], 2
0x1800735fe  jb      loc_180073701
0x180073604  mov     edx, 89h
0x180073609  jmp     loc_1800734CC
0x18007360e  lea     rcx, [rsp+2C0h+pvarg]; pvarg
0x180073613  call    cs:__imp_VariantInit
0x180073619  lea     rdx, [rsp+2C0h+psz]; psz
0x18007361e  lea     rcx, [rsp+2C0h+pvarg]; pvarg
0x180073623  call    ?SetStr@CVARIANT@@QEAAXPEAG@Z; CVARIANT::SetStr(ushort *)
0x180073628  nop
0x180073629  mov     rax, [rsi]
0x18007362c  mov     [rsp+2C0h+var_2A0], 0
0x180073634  lea     r9, [rsp+2C0h+pvarg]
0x180073639  xor     r8d, r8d
0x18007363c  lea     rdx, aName; "Name"
0x180073643  mov     rcx, rsi
0x180073646  mov     rax, [rax+28h]
0x18007364a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007364f  mov     ebx, eax
0x180073651  test    eax, eax
0x180073653  jns     short loc_1800736A0
0x180073655  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007365b  mov     edx, ebx
0x18007365d  mov     rcx, rax
0x180073660  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180073666  mov     rcx, cs:WPP_GLOBAL_Control
0x18007366d  cmp     rcx, r13
0x180073670  jz      short loc_180073693
0x180073672  test    byte ptr [rcx+1Ch], 1
0x180073676  jz      short loc_180073693
0x180073678  cmp     byte ptr [rcx+19h], 2
0x18007367c  jb      short loc_180073693
0x18007367e  mov     edx, 8Ah
0x180073683  mov     r9d, ebx
0x180073686  mov     r8, r12
0x180073689  mov     rcx, [rcx+10h]
0x18007368d  call    WPP_SF_d
0x180073692  nop
0x180073693  lea     rcx, [rsp+2C0h+pvarg]; pvarg
0x180073698  call    cs:__imp_VariantClear
0x18007369e  jmp     short loc_180073701
0x1800736a0  lea     rcx, [rsp+2C0h+pvarg]; pvarg
0x1800736a5  call    cs:__imp_VariantClear
0x1800736ab  nop
0x1800736ac  lea     rcx, [rsp+2C0h+var_288]
0x1800736b1  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800736b7  xor     eax, eax
0x1800736b9  jmp     short loc_18007370E
0x1800736bb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800736c1  mov     ebx, 8004100Eh
0x1800736c6  mov     edx, ebx
0x1800736c8  mov     rcx, rax
0x1800736cb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800736d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800736d8  cmp     rcx, r13
0x1800736db  jz      short loc_180073701
0x1800736dd  test    byte ptr [rcx+1Ch], 1
0x1800736e1  jz      short loc_180073701
0x1800736e3  cmp     byte ptr [rcx+19h], 2
0x1800736e7  jb      short loc_180073701
0x1800736e9  mov     edx, 85h
0x1800736ee  mov     r9d, 8004100Eh
0x1800736f4  mov     r8, r12
0x1800736f7  mov     rcx, [rcx+10h]
0x1800736fb  call    WPP_SF_d
0x180073700  nop
0x180073701  lea     rcx, [rsp+2C0h+var_288]
0x180073706  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18007370c  mov     eax, ebx
0x18007370e  mov     rcx, [rbp+1C0h+var_40]
0x180073715  xor     rcx, rsp; StackCookie
0x180073718  call    __security_check_cookie
0x18007371d  add     rsp, 298h
0x180073724  pop     r13
0x180073726  pop     r12
0x180073728  pop     rdi
0x180073729  pop     rsi
0x18007372a  pop     rbx
0x18007372b  pop     rbp
0x18007372c  retn
```
