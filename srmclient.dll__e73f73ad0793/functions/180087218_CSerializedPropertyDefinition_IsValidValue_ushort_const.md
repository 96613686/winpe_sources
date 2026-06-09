# CSerializedPropertyDefinition::IsValidValue(ushort const *)

- ea: `0x180087218`
- end: `0x1800878c5`
- name: `?IsValidValue@CSerializedPropertyDefinition@@QEBA_NPEBG@Z`
- size: `1709`
- prototype: `bool(CSerializedPropertyDefinition *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180048d1c`

## callees

- `0x180001350`
- `0x18000af40`
- `0x18000eef4`
- `0x18001a184`
- `0x18006febc`
- `0x1800700b8`
- `0x18007424c`
- `0x180087218`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!wcschr` at `0x1800876a1`
- `msvcrt!wcschr` at `0x1800876a1`
- `msvcrt!wcstol` at `0x18008755d`
- `msvcrt!wcstol` at `0x18008755d`
- `msvcrt!_wcstoui64` at `0x1800873a5`
- `msvcrt!_wcstoui64` at `0x1800873a5`
- `msvcrt!iswdigit` at `0x1800874f9`
- `msvcrt!iswdigit` at `0x1800874f9`
- `msvcrt!_errno` at `0x1800873b1`
- `msvcrt!_errno` at `0x18008756f`
- `msvcrt!_errno` at `0x1800873b1`
- `msvcrt!_errno` at `0x18008756f`
- `ole32!CoTaskMemFree` at `0x180087742`
- `ole32!CoTaskMemFree` at `0x18008778f`
- `ole32!CoTaskMemFree` at `0x1800877dc`
- `ole32!CoTaskMemFree` at `0x180087742`
- `ole32!CoTaskMemFree` at `0x18008778f`
- `ole32!CoTaskMemFree` at `0x1800877dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
bool __fastcall CSerializedPropertyDefinition::IsValidValue(wchar_t **this, unsigned __int16 *a2)
{
  bool v4; // di
  unsigned __int64 v5; // rax
  __int64 v7; // rsi
  void *v8; // rbx
  _WORD *v9; // rsi
  const wchar_t *i; // rcx
  wchar_t *v11; // rax
  wchar_t *v12; // r15
  const wchar_t *v13; // rcx
  bool v14; // bl
  const wchar_t *v15; // rcx
  wchar_t *v16; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *EndPtr; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v19[3]; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+60h] [rbp-A0h]
  int v21; // [rsp+64h] [rbp-9Ch]
  int v22; // [rsp+68h] [rbp-98h]
  _BYTE v23[96]; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+D0h] [rbp-30h]
  void *Block[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v27; // [rsp+F0h] [rbp-10h]
  _QWORD v28[22]; // [rsp+100h] [rbp+0h] BYREF

  v16 = (wchar_t *)v19;
  v19[0] = L"base\\fs\\fsrm\\utilities\\property\\srmpropdef.cpp";
  v19[1] = L"CSerializedPropertyDefinition::IsValidValue";
  v19[2] = L"PROPDEFC";
  v20 = 171;
  v21 = 17;
  v22 = 255;
  v24 = 0x1000000;
  v4 = 1;
  memset_0(v23, 0, sizeof(v23));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v28, (const struct CSrmDebugInfo *)v19, 0);
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( v5 > 0x3E8 )
  {
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v28,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"FALSE");
    v28[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v28);
    return 0;
  }
  switch ( *((_DWORD *)this + 16) )
  {
    case 1:
      goto LABEL_48;
    case 2:
      pv = 0;
      CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&pv, a2);
      v8 = pv;
      v9 = pv;
      for ( i = (const wchar_t *)pv; ; i = v12 + 1 )
      {
        v11 = wcschr(i, 0x7Cu);
        v12 = v11;
        if ( !v11 )
          break;
        *v11 = 0;
        if ( *v9 )
        {
          std::wstring::wstring(Block, v9);
          std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(
            this + 9,
            &v16,
            Block);
          if ( v27 >= 8 )
            operator delete(Block[0]);
          v27 = 7;
          v26 = 0;
          LOWORD(Block[0]) = 0;
          if ( v16 == this[10] )
          {
            CSrmFunctionTracerBase::TraceInternalWithFormat(
              (CSrmFunctionTracerBase *)v28,
              L"RETURN",
              0xAAu,
              L"Returning BOOL: %s",
              L"FALSE");
            CoTaskMemFree(v8);
            pv = 0;
            v28[0] = &CSrmFunctionTracer::`vftable';
            goto LABEL_27;
          }
        }
        v9 = v12 + 1;
      }
      if ( *v9 )
      {
        std::wstring::wstring(Block, v9);
        std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(
          this + 9,
          &v16,
          Block);
        if ( v27 >= 8 )
          operator delete(Block[0]);
        v27 = 7;
        v26 = 0;
        LOWORD(Block[0]) = 0;
        v4 = v16 != this[10];
        v13 = L"TRUE";
        if ( v16 == this[10] )
          v13 = L"FALSE";
        CSrmFunctionTracerBase::TraceInternalWithFormat(
          (CSrmFunctionTracerBase *)v28,
          L"RETURN",
          0xAAu,
          L"Returning BOOL: %s",
          v13);
        CoTaskMemFree(v8);
        pv = 0;
        v28[0] = &CSrmFunctionTracer::`vftable';
      }
      else
      {
        CSrmFunctionTracerBase::TraceInternalWithFormat(
          (CSrmFunctionTracerBase *)v28,
          L"RETURN",
          0xAAu,
          L"Returning BOOL: %s",
          L"TRUE");
        CoTaskMemFree(v8);
        pv = 0;
        v28[0] = &CSrmFunctionTracer::`vftable';
      }
      goto LABEL_53;
    case 3:
LABEL_48:
      std::wstring::wstring(Block, a2);
      std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(
        this + 9,
        &v16,
        Block);
      if ( v27 >= 8 )
        operator delete(Block[0]);
      v27 = 7;
      v26 = 0;
      LOWORD(Block[0]) = 0;
      v14 = v16 != this[10];
      v15 = L"TRUE";
      if ( v16 == this[10] )
        v15 = L"FALSE";
      CSrmFunctionTracerBase::TraceInternalWithFormat(
        (CSrmFunctionTracerBase *)v28,
        L"RETURN",
        0xAAu,
        L"Returning BOOL: %s",
        v15);
      v28[0] = &CSrmFunctionTracer::`vftable';
      v4 = v14;
      goto LABEL_53;
    case 6:
      v7 = 0;
      if ( *a2 )
      {
        while ( !iswdigit(a2[v7]) )
        {
          if ( !a2[++v7] )
            goto LABEL_26;
        }
        v16 = 0;
        if ( (((wcstol(a2, &v16, 10) - 0x7FFFFFFF) & 0xFFFFFFFE) != 0 || *_errno() != 34) && !*v16 )
        {
          CSrmFunctionTracerBase::TraceInternalWithFormat(
            (CSrmFunctionTracerBase *)v28,
            L"RETURN",
            0xAAu,
            L"Returning BOOL: %s",
            L"TRUE");
          v28[0] = &CSrmFunctionTracer::`vftable';
          goto LABEL_53;
        }
        CSrmFunctionTracerBase::TraceInternalWithFormat(
          (CSrmFunctionTracerBase *)v28,
          L"RETURN",
          0xAAu,
          L"Returning BOOL: %s",
          L"FALSE");
        v28[0] = &CSrmFunctionTracer::`vftable';
        goto LABEL_27;
      }
      goto LABEL_26;
    case 7:
      if ( *a2 == 48 && !a2[1] || *a2 == 49 && !a2[1] )
        break;
LABEL_26:
      CSrmFunctionTracerBase::TraceInternalWithFormat(
        (CSrmFunctionTracerBase *)v28,
        L"RETURN",
        0xAAu,
        L"Returning BOOL: %s",
        L"FALSE");
      v28[0] = &CSrmFunctionTracer::`vftable';
      goto LABEL_27;
    case 8:
      EndPtr = 0;
      if ( (_wcstoui64(a2, &EndPtr, 10) != -1 || *_errno() != 34) && !*EndPtr )
      {
        CSrmFunctionTracerBase::TraceInternalWithFormat(
          (CSrmFunctionTracerBase *)v28,
          L"RETURN",
          0xAAu,
          L"Returning BOOL: %s",
          L"TRUE");
        v28[0] = &CSrmFunctionTracer::`vftable';
        goto LABEL_53;
      }
      CSrmFunctionTracerBase::TraceInternalWithFormat(
        (CSrmFunctionTracerBase *)v28,
        L"RETURN",
        0xAAu,
        L"Returning BOOL: %s",
        L"FALSE");
      v28[0] = &CSrmFunctionTracer::`vftable';
LABEL_27:
      v4 = 0;
      goto LABEL_53;
  }
  CSrmFunctionTracerBase::TraceInternalWithFormat(
    (CSrmFunctionTracerBase *)v28,
    L"RETURN",
    0xAAu,
    L"Returning BOOL: %s",
    L"TRUE");
  v28[0] = &CSrmFunctionTracer::`vftable';
LABEL_53:
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v28);
  return v4;
}

```

## disassembly

```asm
0x180087218  mov     [rsp-8+arg_10], rbx
0x18008721d  mov     [rsp-8+arg_18], rsi
0x180087222  push    rbp
0x180087223  push    rdi
0x180087224  push    r13
0x180087226  push    r14
0x180087228  push    r15
0x18008722a  lea     rbp, [rsp-0C0h]
0x180087232  sub     rsp, 1C0h
0x180087239  mov     rax, cs:__security_cookie
0x180087240  xor     rax, rsp
0x180087243  mov     [rbp+0E0h+var_30], rax
0x18008724a  mov     rbx, rdx
0x18008724d  mov     r14, rcx
0x180087250  lea     rax, [rsp+1E0h+var_198]
0x180087255  mov     [rsp+1E0h+var_1B0], rax
0x18008725a  lea     rax, aBaseFsFsrmUtil_20; "base\\fs\\fsrm\\utilities\\property\\sr"...
0x180087261  mov     [rsp+1E0h+var_198], rax
0x180087266  lea     rax, aCserializedpro; "CSerializedPropertyDefinition::IsValidV"...
0x18008726d  mov     [rsp+1E0h+var_190], rax
0x180087272  lea     rax, aPropdefc; "PROPDEFC"
0x180087279  mov     [rsp+1E0h+var_188], rax
0x18008727e  mov     [rsp+1E0h+var_180], 0ABh
0x180087286  mov     [rsp+1E0h+var_17C], 11h
0x18008728e  mov     [rsp+1E0h+var_178], 0FFh
0x180087296  xor     r13d, r13d
0x180087299  mov     [rbp+0E0h+var_110], 1000000h
0x1800872a0  lea     edi, [r13+1]
0x1800872a4  xor     edx, edx; Val
0x1800872a6  lea     r8d, [r13+60h]; Size
0x1800872aa  lea     rcx, [rsp+1E0h+var_170]; void *
0x1800872af  call    memset_0
0x1800872b4  nop
0x1800872b5  xor     r8d, r8d
0x1800872b8  lea     rdx, [rsp+1E0h+var_198]
0x1800872bd  lea     rcx, [rbp+0E0h+var_E0]
0x1800872c1  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800872c6  nop
0x1800872c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800872cb  inc     rax
0x1800872ce  cmp     [rbx+rax*2], r13w
0x1800872d3  jnz     short loc_1800872CB
0x1800872d5  cmp     rax, 3E8h
0x1800872db  jbe     short loc_180087322
0x1800872dd  lea     rax, aFalse; "FALSE"
0x1800872e4  mov     [rsp+1E0h+var_1C0], rax
0x1800872e9  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1800872f0  mov     r8d, 0AAh; unsigned int
0x1800872f6  lea     rdx, aReturn; "RETURN"
0x1800872fd  lea     rcx, [rbp+0E0h+var_E0]; this
0x180087301  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180087306  nop
0x180087307  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18008730e  mov     [rbp+0E0h+var_E0], rax
0x180087312  lea     rcx, [rbp+0E0h+var_E0]; this
0x180087316  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18008731b  xor     al, al
0x18008731d  jmp     loc_18008789A
0x180087322  mov     ecx, [r14+40h]
0x180087326  sub     ecx, 1
0x180087329  jz      loc_1800877FC
0x18008732f  sub     ecx, 1
0x180087332  jz      loc_18008761C
0x180087338  sub     ecx, 1
0x18008733b  jz      loc_1800877FC
0x180087341  sub     ecx, 3
0x180087344  jz      loc_1800874EC
0x18008734a  sub     ecx, 1
0x18008734d  jz      loc_180087461
0x180087353  cmp     ecx, 1
0x180087356  jz      short loc_180087392
0x180087358  lea     rcx, aTrue_0; "TRUE"
0x18008735f  mov     [rsp+1E0h+var_1C0], rcx
0x180087364  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x18008736b  mov     r8d, 0AAh; unsigned int
0x180087371  lea     rdx, aReturn; "RETURN"
0x180087378  lea     rcx, [rbp+0E0h+var_E0]; this
0x18008737c  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180087381  nop
0x180087382  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180087389  mov     [rbp+0E0h+var_E0], rax
0x18008738d  jmp     loc_18008788E
0x180087392  mov     [rsp+1E0h+EndPtr], r13
0x180087397  mov     r8d, 0Ah; Radix
0x18008739d  lea     rdx, [rsp+1E0h+EndPtr]; EndPtr
0x1800873a2  mov     rcx, rbx; String
0x1800873a5  call    cs:__imp__wcstoui64
0x1800873ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800873af  jnz     short loc_1800873F6
0x1800873b1  call    cs:__imp__errno
0x1800873b7  cmp     dword ptr [rax], 22h ; '"'
0x1800873ba  jnz     short loc_1800873F6
0x1800873bc  lea     rax, aFalse; "FALSE"
0x1800873c3  mov     [rsp+1E0h+var_1C0], rax
0x1800873c8  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1800873cf  mov     r8d, 0AAh; unsigned int
0x1800873d5  lea     rdx, aReturn; "RETURN"
0x1800873dc  lea     rcx, [rbp+0E0h+var_E0]; this
0x1800873e0  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1800873e5  nop
0x1800873e6  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800873ed  mov     [rbp+0E0h+var_E0], rax
0x1800873f1  jmp     loc_180087542
0x1800873f6  mov     rax, [rsp+1E0h+EndPtr]
0x1800873fb  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180087402  mov     r8d, 0AAh; unsigned int
0x180087408  lea     rdx, aReturn; "RETURN"
0x18008740f  cmp     r13w, [rax]
0x180087413  jz      short loc_18008743B
0x180087415  lea     rax, aFalse; "FALSE"
0x18008741c  mov     [rsp+1E0h+var_1C0], rax
0x180087421  lea     rcx, [rbp+0E0h+var_E0]; this
0x180087425  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x18008742a  nop
0x18008742b  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180087432  mov     [rbp+0E0h+var_E0], rax
0x180087436  jmp     loc_180087542
0x18008743b  lea     rcx, aTrue_0; "TRUE"
0x180087442  mov     [rsp+1E0h+var_1C0], rcx
0x180087447  lea     rcx, [rbp+0E0h+var_E0]; this
0x18008744b  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180087450  nop
0x180087451  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180087458  mov     [rbp+0E0h+var_E0], rax
0x18008745c  jmp     loc_18008788E
0x180087461  cmp     word ptr [rbx], 30h ; '0'
0x180087465  jnz     short loc_18008746E
0x180087467  cmp     [rbx+2], r13w
0x18008746c  jz      short loc_18008747B
0x18008746e  cmp     word ptr [rbx], 31h ; '1'
0x180087472  jnz     short loc_1800874B5
0x180087474  cmp     [rbx+2], r13w
0x180087479  jnz     short loc_1800874B5
0x18008747b  lea     rcx, aTrue_0; "TRUE"
0x180087482  mov     [rsp+1E0h+var_1C0], rcx
0x180087487  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x18008748e  mov     r8d, 0AAh; unsigned int
0x180087494  lea     rdx, aReturn; "RETURN"
0x18008749b  lea     rcx, [rbp+0E0h+var_E0]; this
0x18008749f  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1800874a4  nop
0x1800874a5  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800874ac  mov     [rbp+0E0h+var_E0], rax
0x1800874b0  jmp     loc_18008788E
0x1800874b5  lea     rax, aFalse; "FALSE"
0x1800874bc  mov     [rsp+1E0h+var_1C0], rax
0x1800874c1  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1800874c8  mov     r8d, 0AAh; unsigned int
0x1800874ce  lea     rdx, aReturn; "RETURN"
0x1800874d5  lea     rcx, [rbp+0E0h+var_E0]; this
0x1800874d9  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1800874de  nop
0x1800874df  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800874e6  mov     [rbp+0E0h+var_E0], rax
0x1800874ea  jmp     short loc_180087542
0x1800874ec  mov     rsi, r13
0x1800874ef  cmp     r13w, [rbx]
0x1800874f3  jz      short loc_18008750D
0x1800874f5  movzx   ecx, word ptr [rbx+rsi*2]; C
0x1800874f9  call    cs:__imp_iswdigit
0x1800874ff  test    eax, eax
0x180087501  jnz     short loc_18008754A
0x180087503  add     rsi, rdi
0x180087506  cmp     r13w, [rbx+rsi*2]
0x18008750b  jnz     short loc_1800874F5
0x18008750d  lea     rax, aFalse; "FALSE"
0x180087514  mov     [rsp+1E0h+var_1C0], rax
0x180087519  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180087520  mov     r8d, 0AAh; unsigned int
0x180087526  lea     rdx, aReturn; "RETURN"
0x18008752d  lea     rcx, [rbp+0E0h+var_E0]; this
0x180087531  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180087536  nop
0x180087537  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18008753e  mov     [rbp+0E0h+var_E0], rax
0x180087542  mov     dil, r13b
0x180087545  jmp     loc_18008788E
0x18008754a  mov     [rsp+1E0h+var_1B0], r13
0x18008754f  mov     r8d, 0Ah; Radix
0x180087555  lea     rdx, [rsp+1E0h+var_1B0]; EndPtr
0x18008755a  mov     rcx, rbx; String
0x18008755d  call    cs:__imp_wcstol
0x180087563  add     eax, 80000001h
0x180087568  test    eax, 0FFFFFFFEh
0x18008756d  jnz     short loc_1800875B1
0x18008756f  call    cs:__imp__errno
0x180087575  cmp     dword ptr [rax], 22h ; '"'
0x180087578  jnz     short loc_1800875B1
0x18008757a  lea     rax, aFalse; "FALSE"
0x180087581  mov     [rsp+1E0h+var_1C0], rax
0x180087586  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x18008758d  mov     r8d, 0AAh; unsigned int
0x180087593  lea     rdx, aReturn; "RETURN"
0x18008759a  lea     rcx, [rbp+0E0h+var_E0]; this
0x18008759e  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1800875a3  nop
0x1800875a4  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800875ab  mov     [rbp+0E0h+var_E0], rax
0x1800875af  jmp     short loc_180087542
0x1800875b1  mov     rax, [rsp+1E0h+var_1B0]
0x1800875b6  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1800875bd  mov     r8d, 0AAh; unsigned int
0x1800875c3  lea     rdx, aReturn; "RETURN"
0x1800875ca  cmp     r13w, [rax]
0x1800875ce  jz      short loc_1800875F6
0x1800875d0  lea     rax, aFalse; "FALSE"
0x1800875d7  mov     [rsp+1E0h+var_1C0], rax
0x1800875dc  lea     rcx, [rbp+0E0h+var_E0]; this
0x1800875e0  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1800875e5  nop
0x1800875e6  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800875ed  mov     [rbp+0E0h+var_E0], rax
0x1800875f1  jmp     loc_180087542
0x1800875f6  lea     rcx, aTrue_0; "TRUE"
0x1800875fd  mov     [rsp+1E0h+var_1C0], rcx
0x180087602  lea     rcx, [rbp+0E0h+var_E0]; this
0x180087606  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x18008760b  nop
0x18008760c  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180087613  mov     [rbp+0E0h+var_E0], rax
0x180087617  jmp     loc_18008788E
0x18008761c  mov     [rsp+1E0h+pv], r13
0x180087621  mov     rdx, rbx; unsigned __int16 *
0x180087624  lea     rcx, [rsp+1E0h+pv]; this
0x180087629  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18008762e  mov     rbx, [rsp+1E0h+pv]
0x180087633  mov     rsi, rbx
0x180087636  mov     rcx, rbx
0x180087639  jmp     short loc_18008769C
0x18008763b  mov     [r15], r13w
0x18008763f  cmp     r13w, [rsi]
0x180087643  jz      short loc_180087695
0x180087645  mov     rdx, rsi
0x180087648  lea     rcx, [rbp+0E0h+Block]; void *
0x18008764c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180087651  nop
0x180087652  lea     rcx, [r14+48h]
0x180087656  lea     r8, [rbp+0E0h+Block]
0x18008765a  lea     rdx, [rsp+1E0h+var_1B0]
0x18008765f  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(std::wstring const &)
0x180087664  nop
0x180087665  cmp     [rbp+0E0h+var_F0], 8
0x18008766a  jb      short loc_180087675
0x18008766c  mov     rcx, [rbp+0E0h+Block]; Block
0x180087670  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180087675  mov     [rbp+0E0h+var_F0], 7
0x18008767d  mov     [rbp+0E0h+var_F8], r13
0x180087681  mov     word ptr [rbp+0E0h+Block], r13w
0x180087686  mov     rax, [r14+50h]
0x18008768a  cmp     [rsp+1E0h+var_1B0], rax
0x18008768f  jz      loc_180087762
0x180087695  lea     rsi, [r15+2]
0x180087699  mov     rcx, rsi; Str
0x18008769c  mov     edx, 7Ch ; '|'; Ch
0x1800876a1  call    cs:__imp_wcschr
0x1800876a7  test    rax, rax
0x1800876aa  mov     r15, rax
0x1800876ad  jnz     short loc_18008763B
0x1800876af  cmp     r13w, [rsi]
0x1800876b3  jz      loc_1800877AF
0x1800876b9  mov     rdx, rsi
0x1800876bc  lea     rcx, [rbp+0E0h+Block]; void *
0x1800876c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800876c5  nop
0x1800876c6  lea     rcx, [r14+48h]
0x1800876ca  lea     r8, [rbp+0E0h+Block]
0x1800876ce  lea     rdx, [rsp+1E0h+var_1B0]
0x1800876d3  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@V?$CComObject@VCFciPropertyDefinition@@@ATL@@@@@ATL@@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<ATL::CComObject<CFciPropertyDefinition>>>>>,0>>::find(std::wstring const &)
0x1800876d8  nop
0x1800876d9  cmp     [rbp+0E0h+var_F0], 8
0x1800876de  jb      short loc_1800876E9
0x1800876e0  mov     rcx, [rbp+0E0h+Block]; Block
0x1800876e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800876e9  mov     [rbp+0E0h+var_F0], 7
0x1800876f1  mov     [rbp+0E0h+var_F8], r13
0x1800876f5  mov     word ptr [rbp+0E0h+Block], r13w
0x1800876fa  mov     rax, [r14+50h]
0x1800876fe  cmp     [rsp+1E0h+var_1B0], rax
0x180087703  setnz   dil
0x180087707  lea     rax, aFalse; "FALSE"
0x18008770e  lea     rcx, aTrue_0; "TRUE"
0x180087715  test    dil, dil
0x180087718  cmovz   rcx, rax
0x18008771c  mov     [rsp+1E0h+var_1C0], rcx
0x180087721  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180087728  mov     r8d, 0AAh; unsigned int
0x18008772e  lea     rdx, aReturn; "RETURN"
0x180087735  lea     rcx, [rbp+0E0h+var_E0]; this
0x180087739  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x18008773e  nop
0x18008773f  mov     rcx, rbx; pv
0x180087742  call    cs:__imp_CoTaskMemFree
0x180087748  mov     [rsp+1E0h+pv], r13
0x18008774d  mov     [rsp+1E0h+pv], r13
0x180087752  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180087759  mov     [rbp+0E0h+var_E0], rax
0x18008775d  jmp     loc_18008788E
0x180087762  lea     rax, aFalse; "FALSE"
0x180087769  mov     [rsp+1E0h+var_1C0], rax
0x18008776e  lea     r9, aReturningBoolS; "Returning BOOL: %s"
  ... truncated ...
```
