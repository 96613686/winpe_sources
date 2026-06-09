# CProperty::AggregateSourceIfEqual(CPropertyValue const &)

- ea: `0x180055c44`
- end: `0x180055eaf`
- name: `?AggregateSourceIfEqual@CProperty@@AEAA_NAEBVCPropertyValue@@@Z`
- size: `619`
- prototype: `bool __fastcall(CProperty *__hidden this, const struct CPropertyValue *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x180056030`
- `0x1800561ec`
- `0x180056388`

## callees

- `0x180001350`
- `0x180002978`
- `0x18000a320`
- `0x18000af40`
- `0x18002f284`
- `0x180054c3c`
- `0x180055b70`
- `0x180055c44`
- `0x180057450`
- `0x18006febc`
- `0x1800700b8`
- `0x18007424c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!wcschr` at `0x180055d73`
- `msvcrt!wcschr` at `0x180055d73`
- `msvcrt!_wcsicmp` at `0x180055df2`
- `msvcrt!_wcsicmp` at `0x180055df2`
- `ole32!CoTaskMemFree` at `0x180055db9`
- `ole32!CoTaskMemFree` at `0x180055db9`

## string_xrefs

- `0x180055c80`: `base\fs\fsrm\service\pipeline\property.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall CProperty::AggregateSourceIfEqual(CProperty *this, const struct CPropertyValue *a2)
{
  char v4; // r15
  const unsigned __int16 *v5; // rbx
  __int64 v6; // rax
  void *v7; // rbx
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  wchar_t *v10; // rax
  wchar_t *v11; // r14
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 IsMultiValueEqual; // r14
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v17; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h]
  _QWORD v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v21[3]; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+88h] [rbp-78h]
  int v23; // [rsp+8Ch] [rbp-74h]
  int v24; // [rsp+90h] [rbp-70h]
  _BYTE v25[96]; // [rsp+98h] [rbp-68h] BYREF
  int v26; // [rsp+F8h] [rbp-8h]
  _QWORD v27[22]; // [rsp+100h] [rbp+0h] BYREF

  v20[0] = v21;
  v21[0] = L"base\\fs\\fsrm\\service\\pipeline\\property.cpp";
  v21[1] = L"CProperty::AggregateSourceIfEqual";
  v21[2] = L"PROPRTYC";
  v22 = 1033;
  v23 = 22;
  v24 = 255;
  v26 = 0x1000000;
  v4 = 1;
  memset_0(v25, 0, sizeof(v25));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v27, (const struct CSrmDebugInfo *)v21, 0);
  if ( *((_QWORD *)a2 + 3) < 8u )
    v5 = (const unsigned __int16 *)a2;
  else
    v5 = *(const unsigned __int16 **)a2;
  v6 = *((_QWORD *)this + 16);
  if ( v6 && (*(_DWORD *)(v6 + 64) == 2 || *(_DWORD *)(v6 + 64) == 5) )
  {
    std::set<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>>::set<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>>(v18);
    pv = 0;
    CSrmAutoPWSZ::CopyFrom(&pv, v5);
    v7 = pv;
    v17 = pv;
    v8 = (const wchar_t *)pv;
    while ( 1 )
    {
      v10 = wcschr(v8, 0x7Cu);
      v11 = v10;
      if ( !v10 )
        break;
      *v10 = 0;
      v9 = std::_Tree_val<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::_Buynode<unsigned short * &>(
             v18,
             &v17);
      std::_Tree<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::_Linsert(
        v18,
        v20,
        v9);
      v8 = v11 + 1;
      v17 = v11 + 1;
    }
    v12 = std::_Tree_val<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::_Buynode<unsigned short * &>(
            v18,
            &v17);
    std::_Tree<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::_Linsert(
      v18,
      v20,
      v12);
    IsMultiValueEqual = (unsigned __int8)CProperty::IsMultiValueEqual(v13, v18, (char *)this + 328);
    CoTaskMemFree(v7);
    pv = 0;
    std::_Tree<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::clear(v18);
    operator delete(Block);
  }
  else
  {
    LOBYTE(IsMultiValueEqual) = _wcsicmp(*((const wchar_t **)this + 34), v5) == 0;
  }
  if ( (_BYTE)IsMultiValueEqual )
  {
    CProperty::AggregateSource(this, a2);
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v27,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"TRUE");
    v27[0] = &CSrmFunctionTracer::`vftable';
  }
  else
  {
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v27,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"FALSE");
    v27[0] = &CSrmFunctionTracer::`vftable';
    v4 = 0;
  }
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v27);
  return v4;
}

```

## disassembly

```asm
0x180055c44  mov     [rsp-8+arg_10], rbx
0x180055c49  push    rbp
0x180055c4a  push    rsi
0x180055c4b  push    rdi
0x180055c4c  push    r14
0x180055c4e  push    r15
0x180055c50  lea     rbp, [rsp-0C0h]
0x180055c58  sub     rsp, 1C0h
0x180055c5f  mov     rax, cs:__security_cookie
0x180055c66  xor     rax, rsp
0x180055c69  mov     [rbp+0E0h+var_30], rax
0x180055c70  mov     rdi, rdx
0x180055c73  mov     rsi, rcx
0x180055c76  lea     rax, [rsp+1E0h+var_170]
0x180055c7b  mov     [rsp+1E0h+var_180], rax
0x180055c80  lea     rax, aBaseFsFsrmServ_31; "base\\fs\\fsrm\\service\\pipeline\\prop"...
0x180055c87  mov     [rsp+1E0h+var_170], rax
0x180055c8c  lea     rax, aCpropertyAggre; "CProperty::AggregateSourceIfEqual"
0x180055c93  mov     [rsp+1E0h+var_168], rax
0x180055c98  lea     rax, aProprtyc; "PROPRTYC"
0x180055c9f  mov     [rbp+0E0h+var_160], rax
0x180055ca3  mov     [rbp+0E0h+var_158], 409h
0x180055caa  mov     [rbp+0E0h+var_154], 16h
0x180055cb1  mov     [rbp+0E0h+var_150], 0FFh
0x180055cb8  mov     [rbp+0E0h+var_E8], 1000000h
0x180055cbf  mov     r15b, 1
0x180055cc2  xor     edx, edx; Val
0x180055cc4  lea     r8d, [rdx+60h]; Size
0x180055cc8  lea     rcx, [rbp+0E0h+var_148]; void *
0x180055ccc  call    memset_0
0x180055cd1  nop
0x180055cd2  xor     r8d, r8d
0x180055cd5  lea     rdx, [rsp+1E0h+var_170]
0x180055cda  lea     rcx, [rbp+0E0h+var_E0]
0x180055cde  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180055ce3  nop
0x180055ce4  cmp     qword ptr [rdi+18h], 8
0x180055ce9  jb      short loc_180055CF0
0x180055ceb  mov     rbx, [rdi]
0x180055cee  jmp     short loc_180055CF3
0x180055cf0  mov     rbx, rdi
0x180055cf3  mov     rax, [rsi+80h]
0x180055cfa  test    rax, rax
0x180055cfd  jz      loc_180055DE8
0x180055d03  cmp     dword ptr [rax+40h], 2
0x180055d07  jz      short loc_180055D13
0x180055d09  cmp     dword ptr [rax+40h], 5
0x180055d0d  jnz     loc_180055DE8
0x180055d13  lea     rcx, [rsp+1E0h+var_1A0]
0x180055d18  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>>::set<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>>(void)
0x180055d1d  nop
0x180055d1e  mov     [rsp+1E0h+pv], 0
0x180055d27  mov     rdx, rbx; unsigned __int16 *
0x180055d2a  lea     rcx, [rsp+1E0h+pv]; this
0x180055d2f  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180055d34  mov     rbx, [rsp+1E0h+pv]
0x180055d39  mov     [rsp+1E0h+var_1A8], rbx
0x180055d3e  mov     rcx, rbx
0x180055d41  jmp     short loc_180055D6E
0x180055d43  xor     ecx, ecx
0x180055d45  mov     [r14], cx
0x180055d49  lea     rcx, [rsp+1E0h+var_1A0]
0x180055d4e  call    ??$_Buynode@AEAPEAG@?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@1@AEAPEAG@Z; std::_Tree_val<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::_Buynode<ushort * &>(ushort * &)
0x180055d53  mov     r8, rax
0x180055d56  lea     rdx, [rsp+1E0h+var_180]
0x180055d5b  lea     rcx, [rsp+1E0h+var_1A0]
0x180055d60  call    ?_Linsert@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@std@@_N@2@PEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@2@_N@Z; std::_Tree<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::_Linsert(std::_Tree_nod<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::_Node *,bool)
0x180055d65  lea     rcx, [r14+2]; Str
0x180055d69  mov     [rsp+1E0h+var_1A8], rcx
0x180055d6e  mov     edx, 7Ch ; '|'; Ch
0x180055d73  call    cs:__imp_wcschr
0x180055d79  test    rax, rax
0x180055d7c  mov     r14, rax
0x180055d7f  lea     rdx, [rsp+1E0h+var_1A8]
0x180055d84  jnz     short loc_180055D43
0x180055d86  lea     rcx, [rsp+1E0h+var_1A0]
0x180055d8b  call    ??$_Buynode@AEAPEAG@?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@1@AEAPEAG@Z; std::_Tree_val<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::_Buynode<ushort * &>(ushort * &)
0x180055d90  mov     r8, rax
0x180055d93  lea     rdx, [rsp+1E0h+var_180]
0x180055d98  lea     rcx, [rsp+1E0h+var_1A0]
0x180055d9d  call    ?_Linsert@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@std@@_N@2@PEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@2@_N@Z; std::_Tree<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::_Linsert(std::_Tree_nod<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::_Node *,bool)
0x180055da2  lea     r8, [rsi+148h]
0x180055da9  lea     rdx, [rsp+1E0h+var_1A0]
0x180055dae  call    ?IsMultiValueEqual@CProperty@@AEAA_NAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z; CProperty::IsMultiValueEqual(std::set<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>> const &,std::set<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>> const &)
0x180055db3  mov     r14b, al
0x180055db6  mov     rcx, rbx; pv
0x180055db9  call    cs:__imp_CoTaskMemFree
0x180055dbf  mov     [rsp+1E0h+pv], 0
0x180055dc8  mov     [rsp+1E0h+pv], 0
0x180055dd1  lea     rcx, [rsp+1E0h+var_1A0]
0x180055dd6  call    ?clear@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<std::wstring,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::wstring>,0>>::clear(void)
0x180055ddb  nop
0x180055ddc  mov     rcx, [rsp+1E0h+Block]; Block
0x180055de1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180055de6  jmp     short loc_180055DFE
0x180055de8  mov     rdx, rbx; String2
0x180055deb  mov     rcx, [rsi+110h]; String1
0x180055df2  call    cs:__imp__wcsicmp
0x180055df8  test    eax, eax
0x180055dfa  setz    r14b
0x180055dfe  test    r14b, r14b
0x180055e01  jz      short loc_180055E45
0x180055e03  mov     rdx, rdi; struct CPropertyValue *
0x180055e06  mov     rcx, rsi; this
0x180055e09  call    ?AggregateSource@CProperty@@AEAAXAEBVCPropertyValue@@@Z; CProperty::AggregateSource(CPropertyValue const &)
0x180055e0e  lea     rax, aTrue_0; "TRUE"
0x180055e15  mov     [rsp+1E0h+var_1C0], rax
0x180055e1a  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180055e21  mov     r8d, 0AAh; unsigned int
0x180055e27  lea     rdx, aReturn; "RETURN"
0x180055e2e  lea     rcx, [rbp+0E0h+var_E0]; this
0x180055e32  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180055e37  nop
0x180055e38  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180055e3f  mov     [rbp+0E0h+var_E0], rax
0x180055e43  jmp     short loc_180055E7D
0x180055e45  lea     rax, aFalse; "FALSE"
0x180055e4c  mov     [rsp+1E0h+var_1C0], rax
0x180055e51  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180055e58  mov     r8d, 0AAh; unsigned int
0x180055e5e  lea     rdx, aReturn; "RETURN"
0x180055e65  lea     rcx, [rbp+0E0h+var_E0]; this
0x180055e69  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180055e6e  nop
0x180055e6f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180055e76  mov     [rbp+0E0h+var_E0], rax
0x180055e7a  xor     r15d, r15d
0x180055e7d  lea     rcx, [rbp+0E0h+var_E0]; this
0x180055e81  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180055e86  mov     al, r15b
0x180055e89  mov     rcx, [rbp+0E0h+var_30]
0x180055e90  xor     rcx, rsp; StackCookie
0x180055e93  call    __security_check_cookie
0x180055e98  mov     rbx, [rsp+1E0h+arg_10]
0x180055ea0  add     rsp, 1C0h
0x180055ea7  pop     r15
0x180055ea9  pop     r14
0x180055eab  pop     rdi
0x180055eac  pop     rsi
0x180055ead  pop     rbp
0x180055eae  retn
```
