# Windows::Internal::Notifications::CToastActivator_Collection::Activate(HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IVectorView<HSTRING__ *> *)

- ea: `0x180007760`
- end: `0x180007b34`
- name: `?Activate@CToastActivator_Collection@Notifications@Internal@Windows@@UEAAJPEAUHSTRING__@@00PEAUIPropertySet@Collections@Foundation@4@PEAU?$IVectorView@PEAUHSTRING__@@@784@@Z`
- size: `980`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005670`
- `0x1800070e8`
- `0x1800074d0`
- `0x180007760`
- `0x180007d34`
- `0x1800082b8`
- `0x18000dc30`
- `0x1800149a0`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000791e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007a58`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000791e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007a58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007a6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007a6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800077a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800077a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007807`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007816`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007afe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007807`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007816`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007afe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Notifications::CToastActivator_Collection::Activate(
        Windows::Internal::Notifications::CToastActivator_Collection *this,
        HSTRING string,
        __int64 a3,
        __int64 a4,
        __int64 (__fastcall ***a5)(_QWORD, GUID *, __int64 *),
        __int64 a6)
{
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned __int64 v8; // r14
  int HandlerInfoFromCollectionAumid; // eax
  unsigned int v10; // ebx
  int v12; // eax
  __int64 v13; // rdx
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r15
  __int64 (__fastcall *v18)(__int64, HSTRING, char *); // r12
  unsigned __int64 v19; // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING, __int64, __int64); // rsi
  __int64 v26; // r15
  WCHAR *v27; // rbx
  int v28; // eax
  int v29; // edi
  __int64 v30; // rcx
  int v31; // [rsp+20h] [rbp-C9h]
  char v32; // [rsp+40h] [rbp-A9h] BYREF
  _BYTE v33[7]; // [rsp+41h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+48h] [rbp-A1h] BYREF
  __int64 v35; // [rsp+50h] [rbp-99h] BYREF
  LPVOID pv[3]; // [rsp+58h] [rbp-91h] BYREF
  PCWSTR sourceString[3]; // [rsp+70h] [rbp-79h] BYREF
  __int64 v38; // [rsp+88h] [rbp-61h]
  __int64 v39; // [rsp+90h] [rbp-59h]
  __int64 v40; // [rsp+98h] [rbp-51h]
  HSTRING stringa; // [rsp+A0h] [rbp-49h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-41h] BYREF
  HSTRING v43; // [rsp+C0h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+4Fh]

  v40 = a4;
  v38 = a3;
  v39 = a6;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  sourceString[0] = 0;
  pv[0] = 0;
  v8 = -1;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  sourceString[1] = (PCWSTR)-1LL;
  sourceString[2] = (PCWSTR)-1LL;
  HandlerInfoFromCollectionAumid = Windows::Internal::Notifications::CToastActivator_Collection::GetHandlerInfoFromCollectionAumid(
                                     this,
                                     StringRawBuffer,
                                     (unsigned __int16 **)sourceString,
                                     (unsigned __int16 **)pv);
  v10 = HandlerInfoFromCollectionAumid;
  if ( HandlerInfoFromCollectionAumid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
      (const char *)(unsigned int)HandlerInfoFromCollectionAumid,
      v31);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    if ( sourceString[0] )
      CoTaskMemFree((LPVOID)sourceString[0]);
    return v10;
  }
  v12 = Windows::Internal::Notifications::CToastActivator_Collection::EnsureSwitchInitialized(this);
  v10 = v12;
  if ( v12 < 0 )
  {
    v13 = 71;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
      (const char *)(unsigned int)v12,
      v31);
LABEL_40:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(sourceString);
    return v10;
  }
  if ( *((_DWORD *)this + 20) )
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 48LL))(
            *((_QWORD *)this + 8),
            *((unsigned int *)this + 21),
            *((_QWORD *)this + 11),
            *((_QWORD *)this + 12));
    v10 = v12;
    if ( v12 < 0 )
    {
      v13 = 78;
      goto LABEL_12;
    }
    *((_DWORD *)this + 20) = 0;
  }
  v34 = 0;
  v14 = **a5;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  v15 = v14(a5, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v34);
  v10 = v15;
  if ( v15 < 0 )
  {
    v16 = 84;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
      (const char *)(unsigned int)v15,
      v31);
LABEL_17:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    goto LABEL_40;
  }
  v32 = 0;
  v33[0] = 0;
  v17 = v34;
  v18 = *(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v34 + 64LL);
  v19 = -1;
  do
    ++v19;
  while ( c_IsGroupActivationHintKey[v19] );
  if ( v19 > 0xFFFFFFFF )
  {
    LODWORD(v19) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(c_IsGroupActivationHintKey, v19, &hstringHeader, &stringa);
  v15 = v18(v17, stringa, &v32);
  v10 = v15;
  if ( v15 < 0 )
  {
    v16 = 90;
    goto LABEL_16;
  }
  if ( v32 )
  {
    v35 = 0;
    v20 = v34;
    v21 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v34 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)&stringa,
      c_IsGroupActivationHintKey);
    v22 = v21(v20, stringa, &v35);
    v10 = v22;
    if ( v22 < 0 )
    {
      v23 = 94;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
        (const char *)(unsigned int)v22,
        v31);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      goto LABEL_17;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v35 + 144LL))(v35, v33);
    v10 = v22;
    if ( v22 < 0 )
    {
      v23 = 95;
      goto LABEL_27;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  }
  v24 = *((_QWORD *)this + 8);
  v25 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64))(*(_QWORD *)v24 + 56LL);
  if ( v33[0] )
    v26 = *(_QWORD *)Windows::Internal::StringReference::StringReference(&v43);
  else
    v26 = v38;
  v27 = (WCHAR *)sourceString[0];
  do
    ++v8;
  while ( sourceString[0][v8] );
  if ( v8 > 0xFFFFFFFF )
  {
    LODWORD(v8) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v27, v8, &hstringHeader, &stringa);
  v28 = v25(v24, stringa, v26, v40);
  v29 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
      (const char *)(unsigned int)v28,
      (int)a5);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v10 = v29;
    goto LABEL_40;
  }
  v30 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  if ( v27 )
    CoTaskMemFree(v27);
  return 0;
}

```

## disassembly

```asm
0x180007760  push    rbp
0x180007762  push    rbx
0x180007763  push    rsi
0x180007764  push    rdi
0x180007765  push    r12
0x180007767  push    r13
0x180007769  push    r14
0x18000776b  push    r15
0x18000776d  lea     rbp, [rsp-0Fh]
0x180007772  sub     rsp, 0F8h
0x180007779  mov     rax, cs:__security_cookie
0x180007780  xor     rax, rsp
0x180007783  mov     [rbp+47h+var_50], rax
0x180007787  mov     [rbp+47h+var_98], r9
0x18000778b  mov     [rbp+47h+var_A8], r8
0x18000778f  mov     rax, rdx
0x180007792  mov     rsi, rcx
0x180007795  mov     r13, [rbp+47h+arg_20]
0x180007799  mov     rcx, [rbp+47h+arg_28]
0x18000779d  mov     [rbp+47h+var_A0], rcx
0x1800077a1  xor     edx, edx; length
0x1800077a3  mov     rcx, rax; string
0x1800077a6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800077ac  xor     edi, edi
0x1800077ae  mov     [rbp+47h+sourceString], rdi
0x1800077b2  mov     [rsp+130h+pv], rdi
0x1800077b7  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800077bb  mov     [rsp+130h+var_D0], r14
0x1800077c0  mov     [rsp+130h+var_C8], r14
0x1800077c5  mov     [rbp+47h+var_B8], r14
0x1800077c9  mov     [rbp+47h+var_B0], r14
0x1800077cd  lea     r9, [rsp+130h+pv]; unsigned __int16 **
0x1800077d2  lea     r8, [rbp+47h+sourceString]; unsigned __int16 **
0x1800077d6  mov     rdx, rax; unsigned __int16 *
0x1800077d9  mov     rcx, rsi; this
0x1800077dc  call    ?GetHandlerInfoFromCollectionAumid@CToastActivator_Collection@Notifications@Internal@Windows@@AEAAJPEBGPEAPEAG1@Z; Windows::Internal::Notifications::CToastActivator_Collection::GetHandlerInfoFromCollectionAumid(ushort const *,ushort * *,ushort * *)
0x1800077e1  mov     ebx, eax
0x1800077e3  test    eax, eax
0x1800077e5  jns     short loc_180007823
0x1800077e7  mov     rcx, [rbp+4Fh]; this
0x1800077eb  mov     r9d, eax; char *
0x1800077ee  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800077f5  lea     edx, [rdi+45h]; void *
0x1800077f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077fd  mov     rcx, [rsp+130h+pv]; pv
0x180007802  test    rcx, rcx
0x180007805  jz      short loc_18000780D
0x180007807  call    cs:__imp_CoTaskMemFree
0x18000780d  mov     rcx, [rbp+47h+sourceString]; pv
0x180007811  test    rcx, rcx
0x180007814  jz      short loc_18000781C
0x180007816  call    cs:__imp_CoTaskMemFree
0x18000781c  mov     eax, ebx
0x18000781e  jmp     loc_180007B14
0x180007823  mov     rcx, rsi; this
0x180007826  call    ?EnsureSwitchInitialized@CToastActivator_Collection@Notifications@Internal@Windows@@AEAAJXZ; Windows::Internal::Notifications::CToastActivator_Collection::EnsureSwitchInitialized(void)
0x18000782b  mov     ebx, eax
0x18000782d  test    eax, eax
0x18000782f  jns     short loc_180007838
0x180007831  mov     edx, 47h ; 'G'
0x180007836  jmp     short loc_180007863
0x180007838  cmp     [rsi+50h], edi
0x18000783b  jz      short loc_18000787E
0x18000783d  mov     rcx, [rsi+40h]
0x180007841  mov     rax, [rcx]
0x180007844  mov     r9, [rsi+60h]
0x180007848  mov     r8, [rsi+58h]
0x18000784c  mov     edx, [rsi+54h]
0x18000784f  mov     rax, [rax+30h]
0x180007853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007858  mov     ebx, eax
0x18000785a  test    eax, eax
0x18000785c  jns     short loc_18000787B
0x18000785e  mov     edx, 4Eh ; 'N'; void *
0x180007863  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000786a  mov     r9d, eax; char *
0x18000786d  mov     rcx, [rbp+4Fh]; this
0x180007871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007876  jmp     loc_180007AC0
0x18000787b  mov     [rsi+50h], edi
0x18000787e  mov     [rsp+130h+var_E8], rdi
0x180007883  mov     rax, [r13+0]
0x180007887  mov     rbx, [rax]
0x18000788a  lea     rcx, [rsp+130h+var_E8]
0x18000788f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007894  lea     r8, [rsp+130h+var_E8]
0x180007899  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800078a0  mov     rcx, r13
0x1800078a3  mov     rax, rbx
0x1800078a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ab  mov     ebx, eax
0x1800078ad  test    eax, eax
0x1800078af  jns     short loc_1800078D8
0x1800078b1  mov     edx, 54h ; 'T'; void *
0x1800078b6  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800078bd  mov     r9d, eax; char *
0x1800078c0  mov     rcx, [rbp+4Fh]; this
0x1800078c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800078c9  lea     rcx, [rsp+130h+var_E8]
0x1800078ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800078d3  jmp     loc_180007AC0
0x1800078d8  mov     [rsp+130h+var_F0], dil
0x1800078dd  mov     [rsp+130h+var_EF], dil
0x1800078e2  mov     r15, [rsp+130h+var_E8]
0x1800078e7  mov     rax, [r15]
0x1800078ea  mov     r12, [rax+40h]
0x1800078ee  mov     rdi, cs:?c_IsGroupActivationHintKey@@3QEBGEB; ushort const * const c_IsGroupActivationHintKey
0x1800078f5  mov     rbx, r14
0x1800078f8  xor     eax, eax
0x1800078fa  inc     rbx
0x1800078fd  cmp     [rdi+rbx*2], ax
0x180007901  jnz     short loc_1800078FA
0x180007903  mov     eax, 0FFFFFFFFh
0x180007908  cmp     rbx, rax
0x18000790b  jbe     short loc_180007924
0x18000790d  mov     ebx, eax
0x18000790f  xor     r9d, r9d; lpArguments
0x180007912  xor     r8d, r8d; nNumberOfArguments
0x180007915  lea     edx, [r9+1]; dwExceptionFlags
0x180007919  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000791e  call    cs:__imp_RaiseException
0x180007924  lea     r9, [rbp+47h+string]; string
0x180007928  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x18000792c  mov     edx, ebx; length
0x18000792e  mov     rcx, rdi; sourceString
0x180007931  call    cs:__imp_WindowsCreateStringReference
0x180007937  lea     r8, [rsp+130h+var_F0]
0x18000793c  mov     rdx, [rbp+47h+string]
0x180007940  mov     rcx, r15
0x180007943  mov     rax, r12
0x180007946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000794b  mov     ebx, eax
0x18000794d  xor     r12d, r12d
0x180007950  test    eax, eax
0x180007952  jns     short loc_18000795E
0x180007954  lea     edx, [r12+5Ah]
0x180007959  jmp     loc_1800078B6
0x18000795e  cmp     [rsp+130h+var_F0], r12b
0x180007963  jz      loc_180007A05
0x180007969  mov     [rsp+130h+var_E0], r12
0x18000796e  mov     rdi, [rsp+130h+var_E8]
0x180007973  mov     rax, [rdi]
0x180007976  mov     rbx, [rax+30h]
0x18000797a  lea     rcx, [rsp+130h+var_E0]
0x18000797f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007984  mov     rdx, cs:?c_IsGroupActivationHintKey@@3QEBGEB; unsigned __int16 *
0x18000798b  lea     rcx, [rbp+47h+string]; this
0x18000798f  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180007994  lea     r8, [rsp+130h+var_E0]
0x180007999  mov     rdx, [rbp+47h+string]
0x18000799d  mov     rcx, rdi
0x1800079a0  mov     rax, rbx
0x1800079a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079a8  mov     ebx, eax
0x1800079aa  test    eax, eax
0x1800079ac  jns     short loc_1800079D5
0x1800079ae  mov     edx, 5Eh ; '^'; void *
0x1800079b3  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800079ba  mov     r9d, eax; char *
0x1800079bd  mov     rcx, [rbp+4Fh]; this
0x1800079c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800079c6  lea     rcx, [rsp+130h+var_E0]
0x1800079cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800079d0  jmp     loc_1800078C9
0x1800079d5  mov     rcx, [rsp+130h+var_E0]
0x1800079da  mov     rax, [rcx]
0x1800079dd  lea     rdx, [rsp+130h+var_EF]
0x1800079e2  mov     rax, [rax+90h]
0x1800079e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079ee  mov     ebx, eax
0x1800079f0  test    eax, eax
0x1800079f2  jns     short loc_1800079FB
0x1800079f4  mov     edx, 5Fh ; '_'
0x1800079f9  jmp     short loc_1800079B3
0x1800079fb  lea     rcx, [rsp+130h+var_E0]
0x180007a00  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007a05  mov     rdi, [rsi+40h]
0x180007a09  mov     rax, [rdi]
0x180007a0c  mov     rsi, [rax+38h]
0x180007a10  cmp     [rsp+130h+var_EF], r12b
0x180007a15  jz      short loc_180007A2A
0x180007a17  lea     rdx, [rsp+130h+pv]
0x180007a1c  lea     rcx, [rbp+47h+var_70]; string
0x180007a20  call    ??$?0V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@StringReference@Internal@Windows@@QEAA@AEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@12@Udummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,Windows::Internal::_StringDetail::dummy_t)
0x180007a25  mov     r15, [rax]
0x180007a28  jmp     short loc_180007A2E
0x180007a2a  mov     r15, [rbp+47h+var_A8]
0x180007a2e  mov     rbx, [rbp+47h+sourceString]
0x180007a32  inc     r14
0x180007a35  cmp     [rbx+r14*2], r12w
0x180007a3a  jnz     short loc_180007A32
0x180007a3c  mov     eax, 0FFFFFFFFh
0x180007a41  cmp     r14, rax
0x180007a44  jbe     short loc_180007A5E
0x180007a46  mov     r14d, eax
0x180007a49  xor     r9d, r9d; lpArguments
0x180007a4c  xor     r8d, r8d; nNumberOfArguments
0x180007a4f  lea     edx, [r9+1]; dwExceptionFlags
0x180007a53  mov     ecx, 0C000000Dh; dwExceptionCode
0x180007a58  call    cs:__imp_RaiseException
0x180007a5e  lea     r9, [rbp+47h+string]; string
0x180007a62  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x180007a66  mov     edx, r14d; length
0x180007a69  mov     rcx, rbx; sourceString
0x180007a6c  call    cs:__imp_WindowsCreateStringReference
0x180007a72  mov     rax, [rbp+47h+var_A0]
0x180007a76  mov     [rsp+130h+var_108], rax
0x180007a7b  mov     qword ptr [rsp+130h+var_110], r13; int
0x180007a80  mov     r9, [rbp+47h+var_98]
0x180007a84  mov     r8, r15
0x180007a87  mov     rdx, [rbp+47h+string]
0x180007a8b  mov     rcx, rdi
0x180007a8e  mov     rax, rsi
0x180007a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a96  mov     edi, eax
0x180007a98  test    eax, eax
0x180007a9a  jns     short loc_180007AD8
0x180007a9c  mov     rcx, [rbp+4Fh]; this
0x180007aa0  mov     r9d, eax; char *
0x180007aa3  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007aaa  mov     edx, 67h ; 'g'; void *
0x180007aaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ab4  lea     rcx, [rsp+130h+var_E8]
0x180007ab9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007abe  mov     ebx, edi
0x180007ac0  lea     rcx, [rsp+130h+pv]
0x180007ac5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180007aca  lea     rcx, [rbp+47h+sourceString]
0x180007ace  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180007ad3  jmp     loc_18000781C
0x180007ad8  mov     rcx, [rsp+130h+var_E8]
0x180007add  test    rcx, rcx
0x180007ae0  jz      short loc_180007AF4
0x180007ae2  mov     [rsp+130h+var_E8], r12
0x180007ae7  mov     rax, [rcx]
0x180007aea  mov     rax, [rax+10h]
0x180007aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af3  nop
0x180007af4  mov     rcx, [rsp+130h+pv]; pv
0x180007af9  test    rcx, rcx
0x180007afc  jz      short loc_180007B04
0x180007afe  call    cs:__imp_CoTaskMemFree
0x180007b04  test    rbx, rbx
0x180007b07  jz      short loc_180007B12
0x180007b09  mov     rcx, rbx; pv
0x180007b0c  call    cs:__imp_CoTaskMemFree
0x180007b12  xor     eax, eax
0x180007b14  mov     rcx, [rbp+47h+var_50]
0x180007b18  xor     rcx, rsp; StackCookie
0x180007b1b  call    __security_check_cookie
0x180007b20  add     rsp, 0F8h
0x180007b27  pop     r15
0x180007b29  pop     r14
0x180007b2b  pop     r13
0x180007b2d  pop     r12
0x180007b2f  pop     rdi
0x180007b30  pop     rsi
0x180007b31  pop     rbx
0x180007b32  pop     rbp
0x180007b33  retn
```
