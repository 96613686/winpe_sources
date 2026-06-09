# IASConditionsCollection::Add(_ATTRIBUTEID,ushort *,IIASItem * *)

- ea: `0x1800360c0`
- end: `0x1800364a0`
- name: `?Add@IASConditionsCollection@@UEAAJW4_ATTRIBUTEID@@PEAGPEAPEAUIIASItem@@@Z`
- size: `992`
- prototype: `__int64 __fastcall(IASConditionsCollection *__hidden this, enum _ATTRIBUTEID, unsigned __int16 *, struct IIASItem **)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180024cac`
- `0x1800255e0`
- `0x18002844c`
- `0x180029ef4`
- `0x18002cca4`
- `0x18002cd00`
- `0x18002f08c`
- `0x18002f240`
- `0x1800360c0`
- `0x180036694`
- `0x180036eec`
- `0x180042a80`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1800361b4`
- `ole32!StringFromGUID2` at `0x1800361b4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800361c6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800362c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800361c6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800362c8`
- `OLEAUT32!__imp_SysFreeString` at `0x180036454`
- `OLEAUT32!__imp_SysFreeString` at `0x18003645f`
- `OLEAUT32!__imp_SysFreeString` at `0x180036454`
- `OLEAUT32!__imp_SysFreeString` at `0x18003645f`
- `OLEAUT32!__imp_VariantInit` at `0x180036119`
- `OLEAUT32!__imp_VariantInit` at `0x180036119`
- `RPCRT4!UuidCreate` at `0x1800361a0`
- `RPCRT4!UuidCreate` at `0x1800361a0`

## string_xrefs

- `0x1800363e9`: `IASSDOCreateItem failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASConditionsCollection::Add(
        IASConditionsCollection *this,
        enum _ATTRIBUTEID a2,
        unsigned __int16 *a3,
        struct IIASItem **a4)
{
  unsigned __int16 *v8; // r14
  enum _ATTRIBUTEID v9; // edx
  unsigned __int16 *v10; // r8
  int ConditionPrefix; // ebx
  int v12; // edx
  struct ISdo *v14; // [rsp+30h] [rbp-99h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-91h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-89h] BYREF
  struct tagVARIANT v17; // [rsp+60h] [rbp-69h] BYREF
  UUID Uuid; // [rsp+80h] [rbp-49h] BYREF
  OLECHAR sz[40]; // [rsp+90h] [rbp-39h] BYREF

  if ( a3 && a4 )
  {
    v8 = 0;
    v14 = 0;
    psz = 0;
    VariantInit(&pvarg);
    ConditionPrefix = IASConditionsCollection::ValidateCondition(this, v9, v10);
    if ( ConditionPrefix >= 0 )
    {
      Uuid = 0;
      UuidCreate(&Uuid);
      if ( !StringFromGUID2(&Uuid, sz, 40) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("StringFromGUID2 failed");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids, "NPSSDO");
        }
        goto LABEL_39;
      }
      v8 = SysAllocString(sz);
      ConditionPrefix = AddToSdoCollection(*((struct ISdoCollection **)this + 3), v8, &v14);
      if ( ConditionPrefix < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("AddToSdoCollection(%S) failed with 0x%x");
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids,
            (unsigned int)"NPSSDO",
            (__int64)v8,
            ConditionPrefix);
        }
        goto LABEL_39;
      }
      ConditionPrefix = GetConditionPrefix(*((struct ISdoDictionaryOld **)this + 6), a2, a3, &psz);
      if ( ConditionPrefix >= 0 )
      {
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(psz);
        v17 = pvarg;
        ConditionPrefix = PutSdoProperty(v14, 0x400u, &v17);
        if ( ConditionPrefix >= 0 )
        {
          ConditionPrefix = ((__int64 (__fastcall *)(struct ISdo *))v14->lpVtbl->Apply)(v14);
          if ( ConditionPrefix >= 0 )
          {
            ConditionPrefix = IASSDOCreateItem(
                                *((_DWORD *)this + 4),
                                v14,
                                *((struct ISdo **)this + 4),
                                *((struct ISdoMachine **)this + 5),
                                *((struct ISdoDictionaryOld **)this + 6),
                                (__int64)a4);
            if ( ConditionPrefix >= 0
              || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
            {
              goto LABEL_39;
            }
            WppDbgPrint("IASSDOCreateItem failed with 0x%x");
            v12 = 26;
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
            {
              goto LABEL_39;
            }
            WppDbgPrint("pSdo->Apply failed with 0x%x");
            v12 = 25;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          {
            goto LABEL_39;
          }
          WppDbgPrint("PutSdoProperty(PROPERTY_CONDITION_TEXT) failed with 0x%x");
          v12 = 24;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_39;
        }
        WppDbgPrint("GetConditionPrefix failed with 0x%x");
        v12 = 23;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        goto LABEL_39;
      }
      WppDbgPrint("ValidateCondition returned 0x%x");
      v12 = 20;
    }
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      (unsigned int)WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids,
      (unsigned int)"NPSSDO",
      ConditionPrefix);
LABEL_39:
    SysFreeString(v8);
    SysFreeString(psz);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
    return (unsigned int)ConditionPrefix;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800360c0  push    rbp
0x1800360c2  push    rbx
0x1800360c3  push    rsi
0x1800360c4  push    rdi
0x1800360c5  push    r12
0x1800360c7  push    r14
0x1800360c9  push    r15
0x1800360cb  lea     rbp, [rsp-27h]
0x1800360d0  sub     rsp, 0F0h
0x1800360d7  mov     rax, cs:__security_cookie
0x1800360de  xor     rax, rsp
0x1800360e1  mov     [rbp+57h+var_40], rax
0x1800360e5  mov     r15, r9
0x1800360e8  mov     rdi, r8
0x1800360eb  mov     r12d, edx
0x1800360ee  mov     rsi, rcx
0x1800360f1  test    r8, r8
0x1800360f4  jz      loc_18003647D
0x1800360fa  test    r9, r9
0x1800360fd  jz      loc_18003647D
0x180036103  xor     r14d, r14d
0x180036106  mov     [rsp+120h+var_F0], 0
0x18003610f  lea     rcx, [rsp+120h+pvarg]; pvarg
0x180036114  mov     [rsp+120h+psz], r14
0x180036119  call    cs:__imp_VariantInit
0x18003611f  mov     rcx, rsi; this
0x180036122  call    ?ValidateCondition@IASConditionsCollection@@QEAAJW4_ATTRIBUTEID@@PEAG@Z; IASConditionsCollection::ValidateCondition(_ATTRIBUTEID,ushort *)
0x180036127  mov     ebx, eax
0x180036129  test    eax, eax
0x18003612b  jns     short loc_180036195
0x18003612d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036134  lea     rax, WPP_GLOBAL_Control
0x18003613b  cmp     rcx, rax
0x18003613e  jz      loc_180036451
0x180036144  cmp     byte ptr [rcx+19h], 2
0x180036148  jb      loc_180036451
0x18003614e  mov     edi, 400h
0x180036153  test    [rcx+1Ch], edi
0x180036156  jz      loc_180036451
0x18003615c  mov     edx, ebx
0x18003615e  lea     rcx, aValidatecondit; "ValidateCondition returned 0x%x"
0x180036165  call    WppDbgPrint
0x18003616a  lea     edx, [r14+14h]
0x18003616e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036175  lea     r9, aNpssdo; "NPSSDO"
0x18003617c  lea     r8, WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids
0x180036183  mov     dword ptr [rsp+120h+var_100], ebx
0x180036187  mov     rcx, [rcx+10h]
0x18003618b  call    WPP_SF_sd
0x180036190  jmp     loc_180036451
0x180036195  xorps   xmm0, xmm0
0x180036198  lea     rcx, [rbp+57h+Uuid]; Uuid
0x18003619c  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800361a0  call    cs:__imp_UuidCreate
0x1800361a6  mov     r8d, 28h ; '('; cchMax
0x1800361ac  lea     rdx, [rbp+57h+sz]; lpsz
0x1800361b0  lea     rcx, [rbp+57h+Uuid]; rguid
0x1800361b4  call    cs:__imp_StringFromGUID2
0x1800361ba  test    eax, eax
0x1800361bc  jz      loc_1800363FF
0x1800361c2  lea     rcx, [rbp+57h+sz]; psz
0x1800361c6  call    cs:__imp_SysAllocString
0x1800361cc  mov     rcx, [rsi+18h]; struct ISdoCollection *
0x1800361d0  lea     r8, [rsp+120h+var_F0]; struct ISdo **
0x1800361d5  mov     rdx, rax; unsigned __int16 *
0x1800361d8  mov     r14, rax
0x1800361db  call    ?AddToSdoCollection@@YAJPEAUISdoCollection@@PEAGPEAPEAUISdo@@@Z; AddToSdoCollection(ISdoCollection *,ushort *,ISdo * *)
0x1800361e0  mov     ebx, eax
0x1800361e2  test    eax, eax
0x1800361e4  jns     short loc_180036258
0x1800361e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800361ed  lea     rax, WPP_GLOBAL_Control
0x1800361f4  cmp     rcx, rax
0x1800361f7  jz      loc_180036451
0x1800361fd  cmp     byte ptr [rcx+19h], 2
0x180036201  jb      loc_180036451
0x180036207  mov     edi, 400h
0x18003620c  test    [rcx+1Ch], edi
0x18003620f  jz      loc_180036451
0x180036215  mov     r8d, ebx
0x180036218  lea     rcx, aAddtosdocollec_0; "AddToSdoCollection(%S) failed with 0x%x"
0x18003621f  mov     rdx, r14
0x180036222  call    WppDbgPrint
0x180036227  mov     rcx, cs:WPP_GLOBAL_Control
0x18003622e  lea     r9, aNpssdo; "NPSSDO"
0x180036235  mov     edx, 16h
0x18003623a  mov     dword ptr [rsp+120h+var_F8], ebx
0x18003623e  lea     r8, WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids
0x180036245  mov     [rsp+120h+var_100], r14
0x18003624a  mov     rcx, [rcx+10h]
0x18003624e  call    WPP_SF_sSd
0x180036253  jmp     loc_180036451
0x180036258  mov     rcx, [rsi+30h]; struct ISdoDictionaryOld *
0x18003625c  lea     r9, [rsp+120h+psz]; unsigned __int16 **
0x180036261  mov     r8, rdi; unsigned __int16 *
0x180036264  mov     edx, r12d; enum _ATTRIBUTEID
0x180036267  call    ?GetConditionPrefix@@YAJPEAUISdoDictionaryOld@@W4_ATTRIBUTEID@@QEAGPEAPEAG@Z; GetConditionPrefix(ISdoDictionaryOld *,_ATTRIBUTEID,ushort * const,ushort * *)
0x18003626c  mov     ebx, eax
0x18003626e  test    eax, eax
0x180036270  jns     short loc_1800362B9
0x180036272  mov     rcx, cs:WPP_GLOBAL_Control
0x180036279  lea     rax, WPP_GLOBAL_Control
0x180036280  cmp     rcx, rax
0x180036283  jz      loc_180036451
0x180036289  cmp     byte ptr [rcx+19h], 2
0x18003628d  jb      loc_180036451
0x180036293  mov     edi, 400h
0x180036298  test    [rcx+1Ch], edi
0x18003629b  jz      loc_180036451
0x1800362a1  mov     edx, ebx
0x1800362a3  lea     rcx, aGetconditionpr; "GetConditionPrefix failed with 0x%x"
0x1800362aa  call    WppDbgPrint
0x1800362af  mov     edx, 17h
0x1800362b4  jmp     loc_18003616E
0x1800362b9  mov     rcx, [rsp+120h+psz]; psz
0x1800362be  mov     eax, 8
0x1800362c3  mov     word ptr [rsp+120h+pvarg], ax
0x1800362c8  call    cs:__imp_SysAllocString
0x1800362ce  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800362d3  lea     r8, [rbp+57h+var_C0]; struct tagVARIANT
0x1800362d7  mov     rcx, [rsp+120h+var_F0]; struct ISdo *
0x1800362dc  mov     edi, 400h
0x1800362e1  mov     qword ptr [rsp+120h+pvarg+8], rax
0x1800362e6  mov     edx, edi; unsigned int
0x1800362e8  movups  xmm0, xmmword ptr [rsp+120h+pvarg]
0x1800362ed  movsd   qword ptr [rbp+57h+var_C0+10h], xmm1
0x1800362f2  movaps  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800362f6  call    ?PutSdoProperty@@YAJPEAUISdo@@KUtagVARIANT@@@Z; PutSdoProperty(ISdo *,ulong,tagVARIANT)
0x1800362fb  mov     ebx, eax
0x1800362fd  test    eax, eax
0x1800362ff  jns     short loc_180036343
0x180036301  mov     rcx, cs:WPP_GLOBAL_Control
0x180036308  lea     rax, WPP_GLOBAL_Control
0x18003630f  cmp     rcx, rax
0x180036312  jz      loc_180036451
0x180036318  cmp     byte ptr [rcx+19h], 2
0x18003631c  jb      loc_180036451
0x180036322  test    [rcx+1Ch], edi
0x180036325  jz      loc_180036451
0x18003632b  mov     edx, ebx
0x18003632d  lea     rcx, aPutsdoproperty; "PutSdoProperty(PROPERTY_CONDITION_TEXT)"...
0x180036334  call    WppDbgPrint
0x180036339  mov     edx, 18h
0x18003633e  jmp     loc_18003616E
0x180036343  mov     rcx, [rsp+120h+var_F0]
0x180036348  mov     rax, [rcx]
0x18003634b  mov     rax, [rax+58h]
0x18003634f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036354  mov     ebx, eax
0x180036356  test    eax, eax
0x180036358  jns     short loc_18003639C
0x18003635a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036361  lea     rax, WPP_GLOBAL_Control
0x180036368  cmp     rcx, rax
0x18003636b  jz      loc_180036451
0x180036371  cmp     byte ptr [rcx+19h], 2
0x180036375  jb      loc_180036451
0x18003637b  test    [rcx+1Ch], edi
0x18003637e  jz      loc_180036451
0x180036384  mov     edx, ebx
0x180036386  lea     rcx, aPsdoApplyFaile; "pSdo->Apply failed with 0x%x"
0x18003638d  call    WppDbgPrint
0x180036392  mov     edx, 19h
0x180036397  jmp     loc_18003616E
0x18003639c  mov     rax, [rsi+30h]
0x1800363a0  mov     r9, [rsi+28h]
0x1800363a4  mov     r8, [rsi+20h]
0x1800363a8  mov     rdx, [rsp+120h+var_F0]
0x1800363ad  mov     ecx, [rsi+10h]
0x1800363b0  mov     [rsp+120h+var_F8], r15
0x1800363b5  mov     [rsp+120h+var_100], rax
0x1800363ba  call    ?IASSDOCreateItem@@YAJW4_ITEMTYPE@@PEAUISdo@@1PEAUISdoMachine@@PEAUISdoDictionaryOld@@PEAPEAUIIASItem@@@Z; IASSDOCreateItem(_ITEMTYPE,ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *,IIASItem * *)
0x1800363bf  mov     ebx, eax
0x1800363c1  test    eax, eax
0x1800363c3  jns     loc_180036451
0x1800363c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800363d0  lea     rax, WPP_GLOBAL_Control
0x1800363d7  cmp     rcx, rax
0x1800363da  jz      short loc_180036451
0x1800363dc  cmp     byte ptr [rcx+19h], 2
0x1800363e0  jb      short loc_180036451
0x1800363e2  test    [rcx+1Ch], edi
0x1800363e5  jz      short loc_180036451
0x1800363e7  mov     edx, ebx
0x1800363e9  lea     rcx, aIassdocreateit_1; "IASSDOCreateItem failed with 0x%x"
0x1800363f0  call    WppDbgPrint
0x1800363f5  mov     edx, 1Ah
0x1800363fa  jmp     loc_18003616E
0x1800363ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180036406  lea     rax, WPP_GLOBAL_Control
0x18003640d  cmp     rcx, rax
0x180036410  jz      short loc_180036451
0x180036412  cmp     byte ptr [rcx+19h], 2
0x180036416  jb      short loc_180036451
0x180036418  mov     edi, 400h
0x18003641d  test    [rcx+1Ch], edi
0x180036420  jz      short loc_180036451
0x180036422  lea     rcx, aStringfromguid; "StringFromGUID2 failed"
0x180036429  call    WppDbgPrint
0x18003642e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036435  lea     r9, aNpssdo; "NPSSDO"
0x18003643c  mov     edx, 15h
0x180036441  lea     r8, WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids
0x180036448  mov     rcx, [rcx+10h]
0x18003644c  call    WPP_SF_s
0x180036451  mov     rcx, r14; bstrString
0x180036454  call    cs:__imp_SysFreeString
0x18003645a  mov     rcx, [rsp+120h+psz]; bstrString
0x18003645f  call    cs:__imp_SysFreeString
0x180036465  lea     rcx, [rsp+120h+pvarg]; this
0x18003646a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003646f  lea     rcx, [rsp+120h+var_F0]
0x180036474  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180036479  mov     eax, ebx
0x18003647b  jmp     short loc_180036482
0x18003647d  mov     eax, 80004003h
0x180036482  mov     rcx, [rbp+57h+var_40]
0x180036486  xor     rcx, rsp; StackCookie
0x180036489  call    __security_check_cookie
0x18003648e  add     rsp, 0F0h
0x180036495  pop     r15
0x180036497  pop     r14
0x180036499  pop     r12
0x18003649b  pop     rdi
0x18003649c  pop     rsi
0x18003649d  pop     rbx
0x18003649e  pop     rbp
0x18003649f  retn
```
