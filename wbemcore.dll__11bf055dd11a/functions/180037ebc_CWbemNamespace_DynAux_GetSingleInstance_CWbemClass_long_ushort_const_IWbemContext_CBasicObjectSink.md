# CWbemNamespace::DynAux_GetSingleInstance(CWbemClass *,long,ushort const *,IWbemContext *,CBasicObjectSink *)

- ea: `0x180037ebc`
- end: `0x180038478`
- name: `?DynAux_GetSingleInstance@CWbemNamespace@@QEAAJPEAVCWbemClass@@JPEBGPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z`
- size: `1468`
- prototype: `int(CWbemNamespace *__hidden this, struct CWbemClass *, int, const unsigned __int16 *, struct IWbemContext *, struct CBasicObjectSink *)`
- caller_count: `3`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032340`
- `0x180036444`
- `0x180037bf8`

## callees

- `0x18000b140`
- `0x18000b17c`
- `0x18001307c`
- `0x180037ebc`
- `0x180039c50`
- `0x180039d40`
- `0x180039f68`
- `0x18003be20`
- `0x18003c000`
- `0x18003cfe0`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x180037fd2`
- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x180037fd2`
- `wbemcomn!??BCVar@@QEAAPEAGXZ` at `0x180038023`
- `wbemcomn!??BCVar@@QEAAPEAGXZ` at `0x180038023`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x180037fe6`
- `wbemcomn!??4WString@@QEAAAEAV0@PEBG@Z` at `0x180037fa9`
- `wbemcomn!??4WString@@QEAAAEAV0@PEBG@Z` at `0x180037fa9`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180037f4d`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180037f4d`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x180037f85`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x180037f85`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180037f98`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180037f98`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180038187`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180038205`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800382ec`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180038438`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180038187`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180038205`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800382ec`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180038438`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800380b0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800380b0`
- `wbemcomn!GetMemLogObject` at `0x1800381da`
- `wbemcomn!GetMemLogObject` at `0x180038295`
- `wbemcomn!GetMemLogObject` at `0x1800382ab`
- `wbemcomn!GetMemLogObject` at `0x180038337`
- `wbemcomn!GetMemLogObject` at `0x180038393`
- `wbemcomn!GetMemLogObject` at `0x1800383ca`
- `wbemcomn!GetMemLogObject` at `0x1800381da`
- `wbemcomn!GetMemLogObject` at `0x180038295`
- `wbemcomn!GetMemLogObject` at `0x1800382ab`
- `wbemcomn!GetMemLogObject` at `0x180038337`
- `wbemcomn!GetMemLogObject` at `0x180038393`
- `wbemcomn!GetMemLogObject` at `0x1800383ca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800381e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800382a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800382bb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038342`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003839e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800383da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800381e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800382a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800382bb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038342`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003839e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800383da`
- `FastProx!?IsDynamic@CWbemClass@@QEAAHXZ` at `0x180037f3b`
- `FastProx!?IsDynamic@CWbemClass@@QEAAHXZ` at `0x180037f3b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800380f5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800380f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180038151`
- `OLEAUT32!__imp_SysFreeString` at `0x180038151`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CWbemNamespace::DynAux_GetSingleInstance(
        CWbemNamespace *this,
        struct CWbemClass *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        struct IWbemContext *a5,
        struct CBasicObjectSink *a6)
{
  unsigned __int16 *LPWSTR; // rax
  struct CBasicObjectSink *v10; // r13
  int First_ms_XXX_Locale; // ebx
  unsigned __int16 *v12; // r14
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int128 *, _QWORD, struct IWbemContext *, _QWORD, _QWORD, unsigned __int16 *, _QWORD, __int64, GUID *, unsigned __int16 **); // rbx
  __int64 v15; // rax
  unsigned __int16 *v16; // rbx
  CDecoratingSink *v17; // rax
  CDecoratingSink *v18; // rdi
  OLECHAR *v19; // r14
  int v20; // esi
  unsigned int v22; // edi
  struct CBasicObjectSink *v23; // rbx
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned int v27; // ebx
  struct CBasicObjectSink *v28; // rcx
  CMemoryLog *v29; // rax
  CClientCnt *v30; // rcx
  __int64 v31; // rdx
  CMemoryLog *v32; // rax
  CMemoryLog *v33; // rax
  unsigned __int16 *v34; // [rsp+70h] [rbp-71h] BYREF
  unsigned __int16 *v35; // [rsp+78h] [rbp-69h] BYREF
  _BYTE v36[8]; // [rsp+80h] [rbp-61h] BYREF
  struct CBasicObjectSink *v37; // [rsp+88h] [rbp-59h]
  CDecoratingSink *v38; // [rsp+90h] [rbp-51h]
  _BYTE v39[32]; // [rsp+98h] [rbp-49h] BYREF
  __int128 v40; // [rsp+B8h] [rbp-29h] BYREF
  char v41; // [rsp+C8h] [rbp-19h]
  _DWORD (*v42)(void *); // [rsp+D0h] [rbp-11h]
  unsigned __int16 *v43; // [rsp+D8h] [rbp-9h]

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 350, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a4);
  }
  COperationError::COperationError((COperationError *)v36, a6, L"GetObject", a4, 0);
  if ( !v36[0] )
  {
    MemLogObject = GetMemLogObject();
    v27 = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 351, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    v28 = v37;
    if ( !v37 )
      return v27;
    goto LABEL_44;
  }
  if ( CWbemClass::IsDynamic(a2) )
  {
    CVar::CVar((CVar *)v39);
    if ( (*(int (__fastcall **)(struct CWbemClass *, const wchar_t *, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)a2 + 976LL))(
           a2,
           L"Provider",
           v39,
           0,
           0) >= 0
      && CVar::GetType((CVar *)v39) == 8 )
    {
      LPWSTR = CVar::GetLPWSTR((CVar *)v39);
      v10 = v37;
      WString::operator=((char *)v37 + 64, LPWSTR);
      v35 = 0;
      if ( *((_QWORD *)this + 31) )
      {
        v34 = 0;
        First_ms_XXX_Locale = CMUILocaleList::GetFirst_ms_XXX_Locale((CWbemNamespace *)((char *)this + 176), &v34);
        if ( First_ms_XXX_Locale < 0 )
        {
          v29 = GetMemLogObject();
          CMemoryLog::Write(v29, First_ms_XXX_Locale);
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_42;
          }
          v31 = 352;
          goto LABEL_54;
        }
        v12 = v34;
        v41 = 0;
        v42 = CMUILocale::_Free;
        v43 = v34;
        v13 = *((_QWORD *)this + 31);
        v14 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, struct IWbemContext *, _QWORD, _QWORD, unsigned __int16 *, _QWORD, __int64, GUID *, unsigned __int16 **))(*(_QWORD *)v13 + 40LL);
        v15 = CVar::operator unsigned short *(v39);
        v40 = 0;
        First_ms_XXX_Locale = v14(v13, &v40, 0, a5, 0, *((_QWORD *)this + 14), v34, 0, v15, &IID_IWbemServices, &v35);
        ((void (__fastcall *)(unsigned __int16 *))CMUILocale::_Free)(v12);
        if ( First_ms_XXX_Locale >= 0 )
        {
          v16 = v35;
          v34 = v35;
          v17 = (CDecoratingSink *)CWin32DefaultArena::WbemMemAlloc(0x38u);
          v38 = v17;
          if ( v17 )
            v18 = CDecoratingSink::CDecoratingSink(v17, v10, this);
          else
            v18 = 0;
          if ( v18 )
          {
            (*(void (__fastcall **)(CDecoratingSink *))(*(_QWORD *)v18 + 8LL))(v18);
            v38 = v18;
            v19 = SysAllocString(a4);
            *(_QWORD *)&v40 = v19;
            v20 = (*(__int64 (__fastcall **)(unsigned __int16 *, OLECHAR *, _QWORD, struct IWbemContext *, CDecoratingSink *))(*(_QWORD *)v35 + 56LL))(
                    v35,
                    v19,
                    a3,
                    a5,
                    v18);
            if ( v20 < 0 )
            {
              v25 = GetMemLogObject();
              CMemoryLog::Write(v25, v20);
            }
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                355,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                (unsigned int)v20);
            }
            if ( v19 )
              SysFreeString(v19);
            (*(void (__fastcall **)(CDecoratingSink *))(*(_QWORD *)v18 + 16LL))(v18);
            v38 = 0;
            if ( v16 )
              (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v16 + 16LL))(v16);
            v34 = 0;
            CVar::~CVar((CVar *)v39);
            if ( v10 )
              CObjectSink::Release(v10);
            return (unsigned int)v20;
          }
          v33 = GetMemLogObject();
          CMemoryLog::Write(v33, -2147217402);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              354,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              2147749894LL);
          }
          v27 = CBasicObjectSink::Return(a6, -2147217402, 0);
          CReleaseMe::release((CReleaseMe *)&v34);
          CVar::~CVar((CVar *)v39);
          COperationError::~COperationError((COperationError *)v36);
          return v27;
        }
      }
      else
      {
        First_ms_XXX_Locale = -2147217398;
      }
      v32 = GetMemLogObject();
      CMemoryLog::Write(v32, First_ms_XXX_Locale);
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_42;
      }
      v31 = 353;
LABEL_54:
      WPP_SF_d(
        *((_QWORD *)v30 + 2),
        v31,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)First_ms_XXX_Locale);
LABEL_42:
      v27 = CBasicObjectSink::Return(a6, First_ms_XXX_Locale, 0);
      CVar::~CVar((CVar *)v39);
      if ( !v10 )
        return v27;
      v28 = v10;
LABEL_44:
      CObjectSink::Release(v28);
      return v27;
    }
    v22 = -2147217390;
    v23 = v37;
    if ( v37 )
      COperationErrorSink::SetStatus(v37, 0, -2147217390, 0, 0);
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, -2147217390);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids, 2147749906LL);
    }
    CVar::~CVar((CVar *)v39);
  }
  else
  {
    v22 = -2147217406;
    v23 = v37;
    if ( v37 )
      COperationErrorSink::SetStatus(v37, 0, -2147217406, 0, 0);
  }
  if ( v23 )
    CObjectSink::Release(v23);
  return v22;
}

```

## disassembly

```asm
0x180037ebc  mov     rax, rsp
0x180037ebf  mov     [rax+20h], r9
0x180037ec3  mov     [rax+18h], r8d
0x180037ec7  mov     [rax+8], rcx
0x180037ecb  push    rbp
0x180037ecc  push    rbx
0x180037ecd  push    rsi
0x180037ece  push    rdi
0x180037ecf  push    r13
0x180037ed1  push    r14
0x180037ed3  push    r15
0x180037ed5  lea     rbp, [rax-4Fh]
0x180037ed9  sub     rsp, 0F0h
0x180037ee0  movaps  xmmword ptr [rax-48h], xmm6
0x180037ee4  mov     rsi, r9
0x180037ee7  mov     rbx, rdx
0x180037eea  mov     rdi, rcx
0x180037eed  xor     r15d, r15d
0x180037ef0  mov     [rbp+47h+var_C0], r15d
0x180037ef4  lea     r14, WPP_GLOBAL_Control
0x180037efb  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f02  cmp     rcx, r14
0x180037f05  jz      short loc_180037F11
0x180037f07  test    byte ptr [rcx+1Ch], 1
0x180037f0b  jnz     loc_18003824A
0x180037f11  mov     dword ptr [rsp+120h+var_100], r15d; int
0x180037f16  mov     r9, rsi; unsigned __int16 *
0x180037f19  lea     r8, aGetobject; "GetObject"
0x180037f20  mov     rdx, [rbp+47h+arg_28]; struct CBasicObjectSink *
0x180037f24  lea     rcx, [rbp+47h+var_A8]; this
0x180037f28  call    ??0COperationError@@QEAA@PEAVCBasicObjectSink@@PEBG1H@Z; COperationError::COperationError(CBasicObjectSink *,ushort const *,ushort const *,int)
0x180037f2d  nop
0x180037f2e  cmp     [rbp+47h+var_A8], r15b
0x180037f32  jz      loc_1800382AB
0x180037f38  mov     rcx, rbx
0x180037f3b  call    cs:__imp_?IsDynamic@CWbemClass@@QEAAHXZ; CWbemClass::IsDynamic(void)
0x180037f41  test    eax, eax
0x180037f43  jz      loc_180038225
0x180037f49  lea     rcx, [rbp+47h+var_90]
0x180037f4d  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180037f53  nop
0x180037f54  mov     rax, [rbx]
0x180037f57  mov     [rsp+120h+var_100], r15
0x180037f5c  xor     r9d, r9d
0x180037f5f  lea     r8, [rbp+47h+var_90]
0x180037f63  lea     rdx, aProvider_0; "Provider"
0x180037f6a  mov     rcx, rbx
0x180037f6d  mov     rax, [rax+3D0h]
0x180037f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f79  test    eax, eax
0x180037f7b  js      loc_1800381B7
0x180037f81  lea     rcx, [rbp+47h+var_90]
0x180037f85  call    cs:__imp_?GetType@CVar@@QEAAHXZ; CVar::GetType(void)
0x180037f8b  cmp     eax, 8
0x180037f8e  jnz     loc_1800381B7
0x180037f94  lea     rcx, [rbp+47h+var_90]
0x180037f98  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x180037f9e  mov     r13, [rbp+47h+var_A0]
0x180037fa2  lea     rcx, [r13+40h]
0x180037fa6  mov     rdx, rax
0x180037fa9  call    cs:__imp_??4WString@@QEAAAEAV0@PEBG@Z; WString::operator=(ushort const *)
0x180037faf  mov     [rbp+47h+var_B0], r15
0x180037fb3  cmp     [rdi+0F8h], r15
0x180037fba  jz      loc_180038330
0x180037fc0  xorps   xmm6, xmm6
0x180037fc3  mov     [rbp+47h+var_B8], r15
0x180037fc7  lea     rcx, [rdi+0B0h]
0x180037fce  lea     rdx, [rbp+47h+var_B8]
0x180037fd2  call    cs:__imp_?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z; CMUILocaleList::GetFirst_ms_XXX_Locale(ushort * *)
0x180037fd8  mov     ebx, eax
0x180037fda  test    eax, eax
0x180037fdc  js      loc_180038337
0x180037fe2  mov     r14, [rbp+47h+var_B8]
0x180037fe6  mov     r15, cs:__imp_?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180037fed  mov     [rbp+47h+var_60], 0
0x180037ff1  mov     [rbp+47h+var_58], r15
0x180037ff5  mov     [rbp+47h+var_50], r14
0x180037ff9  mov     [rbp+47h+var_C0], 2
0x180038000  mov     esi, 2
0x180038005  and     esi, 0FFFFFFFDh
0x180038008  mov     [rbp+47h+var_C0], esi
0x18003800b  or      esi, 1
0x18003800e  mov     [rbp+47h+var_C0], esi
0x180038011  mov     rdi, [rdi+0F8h]
0x180038018  mov     rax, [rdi]
0x18003801b  mov     rbx, [rax+28h]
0x18003801f  lea     rcx, [rbp+47h+var_90]
0x180038023  call    cs:__imp_??BCVar@@QEAAPEAGXZ; CVar::operator ushort *(void)
0x180038029  mov     rdx, [rbp+47h+var_B8]
0x18003802d  movdqa  [rbp+47h+var_70], xmm6
0x180038032  lea     rcx, [rbp+47h+var_B0]
0x180038036  mov     [rsp+50h], rcx
0x18003803b  lea     rcx, IID_IWbemServices
0x180038042  mov     [rsp+120h+var_D8], rcx
0x180038047  mov     [rsp+120h+var_E0], rax
0x18003804c  mov     [rsp+120h+var_E8], 0
0x180038055  mov     [rsp+120h+var_F0], rdx
0x18003805a  mov     rax, [rbp+47h+arg_0]
0x18003805e  mov     rdx, [rax+70h]
0x180038062  mov     [rsp+120h+var_F8], rdx
0x180038067  mov     [rsp+120h+var_100], 0
0x180038070  mov     r9, [rbp+47h+arg_20]
0x180038074  xor     r8d, r8d
0x180038077  lea     rdx, [rbp+47h+var_70]
0x18003807b  mov     rcx, rdi
0x18003807e  mov     rax, rbx
0x180038081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038086  mov     ebx, eax
0x180038088  and     esi, 0FFFFFFFEh
0x18003808b  mov     [rbp+47h+var_C0], esi
0x18003808e  mov     rcx, r14
0x180038091  mov     rax, r15
0x180038094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038099  xor     r15d, r15d
0x18003809c  test    ebx, ebx
0x18003809e  js      loc_18003838C
0x1800380a4  mov     rbx, [rbp+47h+var_B0]
0x1800380a8  mov     [rbp+47h+var_B8], rbx
0x1800380ac  lea     ecx, [r15+38h]
0x1800380b0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800380b6  mov     [rbp+47h+var_98], rax
0x1800380ba  test    rax, rax
0x1800380bd  jz      loc_18003821D
0x1800380c3  mov     r8, [rbp+47h+arg_0]; struct CWbemNamespace *
0x1800380c7  mov     rdx, r13; struct CBasicObjectSink *
0x1800380ca  mov     rcx, rax; this
0x1800380cd  call    ??0CDecoratingSink@@QEAA@PEAVCBasicObjectSink@@PEAVCWbemNamespace@@@Z; CDecoratingSink::CDecoratingSink(CBasicObjectSink *,CWbemNamespace *)
0x1800380d2  mov     rdi, rax
0x1800380d5  test    rdi, rdi
0x1800380d8  jz      loc_1800383CA
0x1800380de  mov     rax, [rdi]
0x1800380e1  mov     rcx, rdi
0x1800380e4  mov     rax, [rax+8]
0x1800380e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380ed  mov     [rbp+47h+var_98], rdi
0x1800380f1  mov     rcx, [rbp+47h+psz]; psz
0x1800380f5  call    cs:__imp_SysAllocString
0x1800380fb  mov     r14, rax
0x1800380fe  mov     qword ptr [rbp+47h+var_70], rax
0x180038102  mov     rcx, [rbp+47h+var_B0]
0x180038106  mov     rdx, [rcx]
0x180038109  mov     rax, [rdx+38h]
0x18003810d  mov     [rsp+120h+var_100], rdi
0x180038112  mov     r9, [rbp+47h+arg_20]
0x180038116  mov     r8d, [rbp+47h+arg_10]
0x18003811a  mov     rdx, r14
0x18003811d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038122  mov     esi, eax
0x180038124  test    eax, eax
0x180038126  js      loc_180038295
0x18003812c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038133  lea     rax, WPP_GLOBAL_Control
0x18003813a  cmp     rcx, rax
0x18003813d  jz      short loc_180038149
0x18003813f  test    byte ptr [rcx+1Ch], 1
0x180038143  jnz     loc_18003826E
0x180038149  test    r14, r14
0x18003814c  jz      short loc_180038158
0x18003814e  mov     rcx, r14; bstrString
0x180038151  call    cs:__imp_SysFreeString
0x180038157  nop
0x180038158  mov     rax, [rdi]
0x18003815b  mov     rcx, rdi
0x18003815e  mov     rax, [rax+10h]
0x180038162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038167  mov     [rbp+47h+var_98], r15
0x18003816b  test    rbx, rbx
0x18003816e  jz      short loc_18003817F
0x180038170  mov     rax, [rbx]
0x180038173  mov     rcx, rbx
0x180038176  mov     rax, [rax+10h]
0x18003817a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003817f  mov     [rbp+47h+var_B8], r15
0x180038183  lea     rcx, [rbp+47h+var_90]
0x180038187  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18003818d  nop
0x18003818e  test    r13, r13
0x180038191  jz      short loc_18003819B
0x180038193  mov     rcx, r13; this
0x180038196  call    ?Release@CObjectSink@@UEAAKXZ; CObjectSink::Release(void)
0x18003819b  mov     eax, esi
0x18003819d  movaps  xmm6, [rsp+120h+var_48+8]
0x1800381a5  add     rsp, 0F0h
0x1800381ac  pop     r15
0x1800381ae  pop     r14
0x1800381b0  pop     r13
0x1800381b2  pop     rdi
0x1800381b3  pop     rsi
0x1800381b4  pop     rbx
0x1800381b5  pop     rbp
0x1800381b6  retn
0x1800381b7  mov     edi, 80041012h
0x1800381bc  mov     rbx, [rbp+47h+var_A0]
0x1800381c0  test    rbx, rbx
0x1800381c3  jz      short loc_1800381DA
0x1800381c5  mov     [rsp+120h+var_100], r15; struct IWbemClassObject *
0x1800381ca  xor     r9d, r9d; unsigned __int16 *
0x1800381cd  mov     r8d, edi; int
0x1800381d0  xor     edx, edx; int
0x1800381d2  mov     rcx, rbx; this
0x1800381d5  call    ?SetStatus@COperationErrorSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; COperationErrorSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x1800381da  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800381e0  mov     edx, edi
0x1800381e2  mov     rcx, rax
0x1800381e5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800381eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800381f2  cmp     rcx, r14
0x1800381f5  jz      short loc_180038201
0x1800381f7  test    byte ptr [rcx+1Ch], 1
0x1800381fb  jnz     loc_18003844D
0x180038201  lea     rcx, [rbp+47h+var_90]
0x180038205  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18003820b  nop
0x18003820c  test    rbx, rbx
0x18003820f  jz      short loc_180038219
0x180038211  mov     rcx, rbx; this
0x180038214  call    ?Release@CObjectSink@@UEAAKXZ; CObjectSink::Release(void)
0x180038219  mov     eax, edi
0x18003821b  jmp     short loc_18003819D
0x18003821d  mov     rdi, r15
0x180038220  jmp     loc_1800380D5
0x180038225  mov     edi, 80041002h
0x18003822a  mov     rbx, [rbp+47h+var_A0]
0x18003822e  test    rbx, rbx
0x180038231  jz      short loc_18003820C
0x180038233  mov     [rsp+120h+var_100], r15; struct IWbemClassObject *
0x180038238  xor     r9d, r9d; unsigned __int16 *
0x18003823b  mov     r8d, edi; int
0x18003823e  xor     edx, edx; int
0x180038240  mov     rcx, rbx; this
0x180038243  call    ?SetStatus@COperationErrorSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; COperationErrorSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x180038248  jmp     short loc_18003820C
0x18003824a  cmp     byte ptr [rcx+19h], 5
0x18003824e  jb      loc_180037F11
0x180038254  mov     edx, 15Eh
0x180038259  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180038260  mov     rcx, [rcx+10h]
0x180038264  call    WPP_SF_S
0x180038269  jmp     loc_180037F11
0x18003826e  cmp     byte ptr [rcx+19h], 2
0x180038272  jb      loc_180038149
0x180038278  mov     edx, 163h
0x18003827d  mov     r9d, esi
0x180038280  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180038287  mov     rcx, [rcx+10h]
0x18003828b  call    WPP_SF_d
0x180038290  jmp     loc_180038149
0x180038295  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003829b  mov     edx, esi
0x18003829d  mov     rcx, rax
0x1800382a0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800382a6  jmp     loc_18003812C
0x1800382ab  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800382b1  mov     ebx, 80041006h
0x1800382b6  mov     edx, ebx
0x1800382b8  mov     rcx, rax
0x1800382bb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800382c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382c8  cmp     rcx, r14
0x1800382cb  jnz     short loc_180038307
0x1800382cd  mov     rcx, [rbp+47h+var_A0]
0x1800382d1  test    rcx, rcx
0x1800382d4  jz      short loc_180038300
0x1800382d6  jmp     short loc_1800382FB
0x1800382d8  xor     r8d, r8d; struct IWbemClassObject *
0x1800382db  mov     edx, ebx; int
0x1800382dd  mov     rcx, [rbp+47h+arg_28]; this
0x1800382e1  call    ?Return@CBasicObjectSink@@QEAAJJPEAUIWbemClassObject@@@Z; CBasicObjectSink::Return(long,IWbemClassObject *)
0x1800382e6  mov     ebx, eax
0x1800382e8  lea     rcx, [rbp+47h+var_90]
0x1800382ec  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800382f2  nop
0x1800382f3  test    r13, r13
0x1800382f6  jz      short loc_180038300
0x1800382f8  mov     rcx, r13; this
0x1800382fb  call    ?Release@CObjectSink@@UEAAKXZ; CObjectSink::Release(void)
0x180038300  mov     eax, ebx
0x180038302  jmp     loc_18003819D
0x180038307  test    byte ptr [rcx+1Ch], 1
0x18003830b  jz      short loc_1800382CD
0x18003830d  cmp     byte ptr [rcx+19h], 2
0x180038311  jb      short loc_1800382CD
0x180038313  mov     edx, 15Fh
0x180038318  mov     r9d, 80041006h
0x18003831e  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180038325  mov     rcx, [rcx+10h]
0x180038329  call    WPP_SF_d
0x18003832e  jmp     short loc_1800382CD
0x180038330  mov     ebx, 8004100Ah
0x180038335  jmp     short loc_180038393
0x180038337  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003833d  mov     edx, ebx
0x18003833f  mov     rcx, rax
0x180038342  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038348  mov     rcx, cs:WPP_GLOBAL_Control
0x18003834f  cmp     rcx, r14
0x180038352  jz      short loc_1800382D8
0x180038354  test    byte ptr [rcx+1Ch], 1
0x180038358  jz      loc_1800382D8
0x18003835e  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
