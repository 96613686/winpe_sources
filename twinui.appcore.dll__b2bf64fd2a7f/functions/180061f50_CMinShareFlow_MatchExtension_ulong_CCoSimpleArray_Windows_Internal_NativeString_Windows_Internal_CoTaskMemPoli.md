# CMinShareFlow::_MatchExtension(ulong,CCoSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>> const &,Windows::Foundation::IExtensionRegistration *,ushort const *)

- ea: `0x180061f50`
- end: `0x180062214`
- name: `?_MatchExtension@CMinShareFlow@@AEAA_NKAEBV?$CCoSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@PEAUIExtensionRegistration@Foundation@Windows@@PEBG@Z`
- size: `708`
- prototype: `__int64 __fastcall(int, int, int, int, PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180061210`

## callees

- `0x180003d24`
- `0x180016c98`
- `0x180026498`
- `0x180026ee0`
- `0x18002b1b0`
- `0x180060b5c`
- `0x180060d08`
- `0x180061130`
- `0x180061d40`
- `0x180061f50`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180062017`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180062017`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800620dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800620dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006202b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006202b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x1800621a9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x1800621a9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800621cd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800621cd`
- `PROPSYS!PropVariantGetElementCount` at `0x180062103`
- `PROPSYS!PropVariantGetElementCount` at `0x180062103`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18006216e`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18006216e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall CMinShareFlow::_MatchExtension(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
        __int64 a4,
        PCWSTR sourceString)
{
  char v8; // r14
  int (__fastcall *v9)(__int64, __int64 *); // rbx
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, HSTRING, ULONG *); // rdi
  unsigned __int64 v12; // rcx
  int v13; // r15d
  __int64 v14; // rsi
  bool v15; // r8
  bool v16; // r9
  PCWSTR v17; // rbx
  int v18; // edi
  const WCHAR *v19; // rax
  const unsigned __int16 *StringRawBuffer; // rax
  ULONG ElementCount; // esi
  __int64 v22; // rbx
  VARTYPE vt; // cx
  __int64 i; // rdi
  UINT32 length; // [rsp+20h] [rbp-71h] BYREF
  PCWSTR pv; // [rsp+28h] [rbp-69h] BYREF
  int v28; // [rsp+30h] [rbp-61h]
  struct tagPROPVARIANT propvar; // [rsp+38h] [rbp-59h] BYREF
  __int64 v30; // [rsp+50h] [rbp-41h] BYREF
  HSTRING v31; // [rsp+58h] [rbp-39h] BYREF
  __int64 v32; // [rsp+60h] [rbp-31h] BYREF
  __int64 v33; // [rsp+68h] [rbp-29h] BYREF
  LONG v34; // [rsp+70h] [rbp-21h]
  HSTRING string; // [rsp+78h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-11h] BYREF

  v8 = 0;
  v32 = a4;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v32);
  v30 = 0;
  v31 = 0;
  v9 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a4 + 128LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  if ( v9(a4, &v30) >= 0 )
  {
    v33 = 0;
    v34 = 0;
    v10 = v30;
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING, ULONG *))(*(_QWORD *)v30 + 48LL);
    *(_QWORD *)&propvar.vt = &v33;
    propvar.hVal.QuadPart = 0;
    length = 0;
    v12 = -1;
    do
      ++v12;
    while ( sourceString[v12] );
    if ( (int)ULongLongToUInt(v12, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(sourceString, length, &hstringHeader, &string);
    v13 = v11(v10, string, &propvar.ulVal);
    v14 = *(_QWORD *)&propvar.vt;
    RoVariant::RoVariant((RoVariant *)&pv, (struct IInspectable *)propvar.hVal.QuadPart, v15, v16);
    v17 = pv;
    pv = 0;
    v18 = v28;
    v28 = 0;
    RoVariant::~RoVariant((RoVariant *)&pv);
    v19 = *(const WCHAR **)v14;
    *(_QWORD *)v14 = v17;
    pv = v19;
    LODWORD(v19) = *(_DWORD *)(v14 + 8);
    *(_DWORD *)(v14 + 8) = v18;
    v28 = (int)v19;
    RoVariant::~RoVariant((RoVariant *)&pv);
    if ( v13 >= 0 )
    {
      *(_QWORD *)&propvar.vt = v33;
      propvar.lVal = v34;
      v13 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&propvar, &v31);
    }
    RoVariant::~RoVariant((RoVariant *)&v33);
    if ( v13 >= 0 )
    {
      memset(&propvar, 0, sizeof(propvar));
      StringRawBuffer = WindowsGetStringRawBuffer(v31, 0);
      if ( (int)_InitPropVariantFromParsedString(StringRawBuffer, &propvar) >= 0 )
      {
        propvar.vt = 4127;
        ElementCount = PropVariantGetElementCount((const PROPVARIANT *const)&propvar);
        v22 = 0;
        vt = propvar.vt;
        while ( 1 )
        {
          v8 = 0;
          if ( (unsigned int)v22 >= ElementCount )
            goto LABEL_28;
          length = v22;
          pv = 0;
          if ( (vt & 0xFFF) == 0x1F || (vt & 0xFFF) == 8 )
          {
            if ( (vt & 0x1000) != 0 )
            {
              pv = *(PCWSTR *)&propvar.bstrblobVal.pData[8 * v22];
              goto LABEL_22;
            }
            if ( (vt & 0x2000) != 0 )
            {
              if ( SafeArrayGetElement(propvar.parray, (LONG *)&length, &pv) < 0 )
              {
LABEL_18:
                vt = propvar.vt;
                goto LABEL_19;
              }
LABEL_22:
              for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
              {
                if ( !StrCmpLogicalW(pv, *(PCWSTR *)(*a3 + 24 * i)) )
                {
                  v8 = 1;
                  goto LABEL_28;
                }
              }
              goto LABEL_18;
            }
            if ( (vt & 0xF000) == 0 )
            {
              pv = propvar.bstrVal;
              goto LABEL_22;
            }
          }
LABEL_19:
          v22 = (unsigned int)(v22 + 1);
        }
      }
      memset(&propvar, 0, sizeof(propvar));
LABEL_28:
      PropVariantClear((PROPVARIANT *)&propvar);
    }
  }
  Windows::Internal::String::~String((Windows::Internal::String *)&v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  return v8;
}

```

## disassembly

```asm
0x180061f50  push    rbp
0x180061f52  push    rbx
0x180061f53  push    rsi
0x180061f54  push    rdi
0x180061f55  push    r12
0x180061f57  push    r13
0x180061f59  push    r14
0x180061f5b  push    r15
0x180061f5d  lea     rbp, [rsp-17h]
0x180061f62  sub     rsp, 0A8h
0x180061f69  mov     rax, cs:__security_cookie
0x180061f70  xor     rax, rsp
0x180061f73  mov     [rbp+4Fh+var_48], rax
0x180061f77  mov     rdi, r9
0x180061f7a  mov     r13, r8
0x180061f7d  mov     r12d, edx
0x180061f80  mov     rsi, [rbp+4Fh+sourceString]
0x180061f84  xor     r15d, r15d
0x180061f87  mov     r14b, r15b
0x180061f8a  mov     [rbp+4Fh+var_80], r9
0x180061f8e  lea     rcx, [rbp+4Fh+var_80]
0x180061f92  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180061f97  nop
0x180061f98  mov     [rbp+4Fh+var_90], r15
0x180061f9c  mov     [rbp+4Fh+var_88], r15
0x180061fa0  mov     rax, [rdi]
0x180061fa3  mov     rbx, [rax+80h]
0x180061faa  lea     rcx, [rbp+4Fh+var_90]
0x180061fae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061fb3  lea     rdx, [rbp+4Fh+var_90]
0x180061fb7  mov     rcx, rdi
0x180061fba  mov     rax, rbx
0x180061fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061fc2  test    eax, eax
0x180061fc4  js      loc_1800621D4
0x180061fca  mov     [rbp+4Fh+var_78], r15
0x180061fce  mov     [rbp+4Fh+var_70], r15d
0x180061fd2  mov     rbx, [rbp+4Fh+var_90]
0x180061fd6  mov     rax, [rbx]
0x180061fd9  mov     rdi, [rax+30h]
0x180061fdd  lea     rax, [rbp+4Fh+var_78]
0x180061fe1  mov     [rbp+4Fh+propvar], rax
0x180061fe5  mov     [rbp+4Fh+propvar+8], r15
0x180061fe9  mov     [rbp+4Fh+length], r15d
0x180061fed  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180061ff1  inc     rcx; unsigned __int64
0x180061ff4  cmp     [rsi+rcx*2], r15w
0x180061ff9  jnz     short loc_180061FF1
0x180061ffb  lea     rdx, [rbp+4Fh+length]; unsigned int *
0x180061fff  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180062004  test    eax, eax
0x180062006  jns     short loc_18006201D
0x180062008  xor     r9d, r9d; lpArguments
0x18006200b  xor     r8d, r8d; nNumberOfArguments
0x18006200e  lea     edx, [r9+1]; dwExceptionFlags
0x180062012  mov     ecx, 0C000000Dh; dwExceptionCode
0x180062017  call    cs:__imp_RaiseException
0x18006201d  lea     r9, [rbp+4Fh+string]; string
0x180062021  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180062025  mov     edx, [rbp+4Fh+length]; length
0x180062028  mov     rcx, rsi; sourceString
0x18006202b  call    cs:__imp_WindowsCreateStringReference
0x180062031  lea     r8, [rbp+4Fh+propvar+8]
0x180062035  mov     rdx, [rbp+4Fh+string]
0x180062039  mov     rcx, rbx
0x18006203c  mov     rax, rdi
0x18006203f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062044  mov     r15d, eax
0x180062047  mov     rsi, [rbp+4Fh+propvar]
0x18006204b  mov     rdx, [rbp+4Fh+propvar+8]; struct IInspectable *
0x18006204f  lea     rcx, [rbp+4Fh+pv]; this
0x180062053  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x180062058  mov     rbx, [rbp+4Fh+pv]
0x18006205c  mov     [rbp+4Fh+pv], 0
0x180062064  mov     edi, [rbp+4Fh+var_B0]
0x180062067  mov     [rbp+4Fh+var_B0], 0
0x18006206e  lea     rcx, [rbp+4Fh+pv]; this
0x180062072  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180062077  mov     rax, [rsi]
0x18006207a  mov     [rsi], rbx
0x18006207d  mov     [rbp+4Fh+pv], rax
0x180062081  mov     eax, [rsi+8]
0x180062084  mov     [rsi+8], edi
0x180062087  mov     [rbp+4Fh+var_B0], eax
0x18006208a  lea     rcx, [rbp+4Fh+pv]; this
0x18006208e  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180062093  nop
0x180062094  test    r15d, r15d
0x180062097  js      short loc_1800620B7
0x180062099  mov     rax, [rbp+4Fh+var_78]
0x18006209d  mov     [rbp+4Fh+propvar], rax
0x1800620a1  mov     eax, [rbp+4Fh+var_70]
0x1800620a4  mov     dword ptr [rbp+4Fh+propvar+8], eax
0x1800620a7  lea     rdx, [rbp+4Fh+var_88]; HSTRING *
0x1800620ab  lea     rcx, [rbp+4Fh+propvar]; this
0x1800620af  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x1800620b4  mov     r15d, eax
0x1800620b7  lea     rcx, [rbp+4Fh+var_78]; this
0x1800620bb  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800620c0  test    r15d, r15d
0x1800620c3  js      loc_1800621D4
0x1800620c9  xorps   xmm0, xmm0
0x1800620cc  xor     eax, eax
0x1800620ce  movups  xmmword ptr [rbp+4Fh+propvar], xmm0
0x1800620d2  mov     [rbp+4Fh+var_98], rax
0x1800620d6  xor     edx, edx; length
0x1800620d8  mov     rcx, [rbp+4Fh+var_88]; string
0x1800620dc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800620e2  lea     rdx, [rbp+4Fh+propvar]; struct tagPROPVARIANT *
0x1800620e6  mov     rcx, rax; unsigned __int16 *
0x1800620e9  call    ?_InitPropVariantFromParsedString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; _InitPropVariantFromParsedString(ushort const *,tagPROPVARIANT *)
0x1800620ee  test    eax, eax
0x1800620f0  js      loc_1800621BC
0x1800620f6  mov     eax, 101Fh
0x1800620fb  mov     word ptr [rbp+4Fh+propvar], ax
0x1800620ff  lea     rcx, [rbp+4Fh+propvar]; propvar
0x180062103  call    cs:__imp_PropVariantGetElementCount
0x180062109  mov     esi, eax
0x18006210b  xor     ebx, ebx
0x18006210d  movzx   ecx, word ptr [rbp+4Fh+propvar]
0x180062111  xor     r14b, r14b
0x180062114  cmp     ebx, esi
0x180062116  jnb     loc_1800621C9
0x18006211c  mov     [rbp+4Fh+length], ebx
0x18006211f  mov     eax, 0FFFh
0x180062124  movzx   edx, cx
0x180062127  and     dx, ax
0x18006212a  mov     [rbp+4Fh+pv], 0
0x180062132  mov     eax, 1Fh
0x180062137  cmp     ax, dx
0x18006213a  jz      short loc_180062146
0x18006213c  mov     eax, 8
0x180062141  cmp     ax, dx
0x180062144  jnz     short loc_18006217C
0x180062146  bt      cx, 0Ch
0x18006214b  jnb     short loc_18006215B
0x18006214d  mov     rax, [rbp+4Fh+var_98]
0x180062151  mov     rcx, [rax+rbx*8]
0x180062155  mov     [rbp+4Fh+pv], rcx
0x180062159  jmp     short loc_180062192
0x18006215b  bt      cx, 0Dh
0x180062160  jnb     short loc_180062180
0x180062162  lea     r8, [rbp+4Fh+pv]; pv
0x180062166  lea     rdx, [rbp+4Fh+length]; rgIndices
0x18006216a  mov     rcx, [rbp+4Fh+propvar+8]; psa
0x18006216e  call    cs:__imp_SafeArrayGetElement
0x180062174  test    eax, eax
0x180062176  jns     short loc_180062192
0x180062178  movzx   ecx, word ptr [rbp+4Fh+propvar]
0x18006217c  inc     ebx
0x18006217e  jmp     short loc_180062111
0x180062180  movzx   eax, cx
0x180062183  test    eax, 0FFFFF000h
0x180062188  jnz     short loc_18006217C
0x18006218a  mov     rax, [rbp+4Fh+propvar+8]
0x18006218e  mov     [rbp+4Fh+pv], rax
0x180062192  xor     edi, edi
0x180062194  cmp     edi, r12d
0x180062197  jnb     short loc_180062178
0x180062199  lea     r8, [rdi+rdi*2]
0x18006219d  mov     rdx, [r13+0]
0x1800621a1  mov     rdx, [rdx+r8*8]; psz2
0x1800621a5  mov     rcx, [rbp+4Fh+pv]; psz1
0x1800621a9  call    cs:__imp_StrCmpLogicalW
0x1800621af  test    eax, eax
0x1800621b1  jz      short loc_1800621B7
0x1800621b3  inc     edi
0x1800621b5  jmp     short loc_180062194
0x1800621b7  mov     r14b, 1
0x1800621ba  jmp     short loc_1800621C9
0x1800621bc  xorps   xmm0, xmm0
0x1800621bf  xor     eax, eax
0x1800621c1  movups  xmmword ptr [rbp+4Fh+propvar], xmm0
0x1800621c5  mov     [rbp+4Fh+var_98], rax
0x1800621c9  lea     rcx, [rbp+4Fh+propvar]; pvar
0x1800621cd  call    cs:__imp_PropVariantClear
0x1800621d3  nop
0x1800621d4  lea     rcx, [rbp+4Fh+var_88]; this
0x1800621d8  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800621dd  nop
0x1800621de  lea     rcx, [rbp+4Fh+var_90]
0x1800621e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800621e7  nop
0x1800621e8  lea     rcx, [rbp+4Fh+var_80]
0x1800621ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800621f1  mov     al, r14b
0x1800621f4  mov     rcx, [rbp+4Fh+var_48]
0x1800621f8  xor     rcx, rsp; StackCookie
0x1800621fb  call    __security_check_cookie
0x180062200  add     rsp, 0A8h
0x180062207  pop     r15
0x180062209  pop     r14
0x18006220b  pop     r13
0x18006220d  pop     r12
0x18006220f  pop     rdi
0x180062210  pop     rsi
0x180062211  pop     rbx
0x180062212  pop     rbp
0x180062213  retn
```
