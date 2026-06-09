# CExtensionListItem::_GetCustomStringProperty(ushort const *,ushort * *)

- ea: `0x18007d97c`
- end: `0x18007dae1`
- name: `?_GetCustomStringProperty@CExtensionListItem@@AEAAJPEBGPEAPEAG@Z`
- size: `357`
- prototype: `int(CExtensionListItem *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007d31c`

## callees

- `0x180003d24`
- `0x180016c98`
- `0x180026ee0`
- `0x18002b1b0`
- `0x1800366a0`
- `0x180060c8c`
- `0x180060d08`
- `0x180061130`
- `0x18007d97c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007da16`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007da16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007da8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007da8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007da2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007da2a`

## pseudocode

```c
__int64 __fastcall CExtensionListItem::_GetCustomStringProperty(
        CExtensionListItem *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 **); // rbx
  int v7; // ebx
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  UINT32 length[2]; // [rsp+20h] [rbp-60h] BYREF
  __int64 v15; // [rsp+28h] [rbp-58h] BYREF
  __int64 *v16; // [rsp+30h] [rbp-50h] BYREF
  __int64 v17; // [rsp+38h] [rbp-48h] BYREF
  int v18; // [rsp+40h] [rbp-40h]
  __int64 v19; // [rsp+48h] [rbp-38h] BYREF
  int v20; // [rsp+50h] [rbp-30h]
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-20h] BYREF

  *a3 = 0;
  v5 = *((_QWORD *)this + 4);
  v16 = 0;
  v6 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v5 + 128LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  v7 = v6(v5, &v16);
  if ( v7 >= 0 )
  {
    v17 = 0;
    v8 = -1;
    v18 = 0;
    length[0] = 0;
    do
      ++v8;
    while ( a2[v8] );
    if ( (int)ULongLongToUInt(v8, length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(a2, length[0], &hstringHeader, &string);
    v9 = *v16;
    *(_QWORD *)length = &v17;
    v15 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v9 + 48))(v16, string, &v15);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)length);
    if ( v7 >= 0 )
    {
      v19 = v17;
      v20 = v18;
      *(_QWORD *)length = 0;
      v7 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v19, (HSTRING *)length);
      if ( v7 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)length, 0);
        v7 = _AllocString<CTCoAllocPolicy>(v12, v11, StringRawBuffer, a3);
      }
      Windows::Internal::String::~String((Windows::Internal::String *)length);
    }
    RoVariant::~RoVariant((RoVariant *)&v17);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007d97c  mov     [rsp-28h+arg_18], rbx
0x18007d981  push    rbp
0x18007d982  push    rsi
0x18007d983  push    rdi
0x18007d984  push    r14
0x18007d986  push    r15
0x18007d988  mov     rbp, rsp
0x18007d98b  sub     rsp, 80h
0x18007d992  mov     rax, cs:__security_cookie
0x18007d999  xor     rax, rsp
0x18007d99c  mov     [rbp+var_8], rax
0x18007d9a0  xor     r15d, r15d
0x18007d9a3  mov     r14, r8
0x18007d9a6  mov     [r8], r15
0x18007d9a9  mov     rsi, rdx
0x18007d9ac  mov     rdi, [rcx+20h]
0x18007d9b0  lea     rcx, [rbp+var_50]
0x18007d9b4  mov     [rbp+var_50], r15
0x18007d9b8  mov     rax, [rdi]
0x18007d9bb  mov     rbx, [rax+80h]
0x18007d9c2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d9c7  lea     rdx, [rbp+var_50]
0x18007d9cb  mov     rcx, rdi
0x18007d9ce  mov     rax, rbx
0x18007d9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d9d6  mov     ebx, eax
0x18007d9d8  test    eax, eax
0x18007d9da  js      loc_18007DAB3
0x18007d9e0  mov     [rbp+var_48], r15
0x18007d9e4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007d9e8  mov     [rbp+var_40], r15d
0x18007d9ec  mov     [rbp+length], r15d
0x18007d9f0  inc     rcx; unsigned __int64
0x18007d9f3  cmp     [rsi+rcx*2], r15w
0x18007d9f8  jnz     short loc_18007D9F0
0x18007d9fa  lea     rdx, [rbp+length]; unsigned int *
0x18007d9fe  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18007da03  test    eax, eax
0x18007da05  jns     short loc_18007DA1C
0x18007da07  xor     r9d, r9d; lpArguments
0x18007da0a  xor     r8d, r8d; nNumberOfArguments
0x18007da0d  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007da12  lea     edx, [r9+1]; dwExceptionFlags
0x18007da16  call    cs:__imp_RaiseException
0x18007da1c  mov     edx, [rbp+length]; length
0x18007da1f  lea     r9, [rbp+string]; string
0x18007da23  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18007da27  mov     rcx, rsi; sourceString
0x18007da2a  call    cs:__imp_WindowsCreateStringReference
0x18007da30  mov     rcx, [rbp+var_50]
0x18007da34  lea     rdx, [rbp+var_48]
0x18007da38  lea     r8, [rbp+var_58]
0x18007da3c  mov     rax, [rcx]
0x18007da3f  mov     qword ptr [rbp+length], rdx
0x18007da43  mov     rdx, [rbp+string]
0x18007da47  mov     [rbp+var_58], r15
0x18007da4b  mov     rax, [rax+30h]
0x18007da4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da54  lea     rcx, [rbp+length]; this
0x18007da58  mov     ebx, eax
0x18007da5a  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x18007da5f  test    ebx, ebx
0x18007da61  js      short loc_18007DAAA
0x18007da63  mov     rax, [rbp+var_48]
0x18007da67  lea     rdx, [rbp+length]; HSTRING *
0x18007da6b  mov     [rbp+var_38], rax
0x18007da6f  lea     rcx, [rbp+var_38]; this
0x18007da73  mov     eax, [rbp+var_40]
0x18007da76  mov     [rbp+var_30], eax
0x18007da79  mov     qword ptr [rbp+length], r15
0x18007da7d  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x18007da82  mov     ebx, eax
0x18007da84  test    eax, eax
0x18007da86  js      short loc_18007DAA1
0x18007da88  mov     rcx, qword ptr [rbp+length]; string
0x18007da8c  xor     edx, edx; length
0x18007da8e  call    cs:__imp_WindowsGetStringRawBuffer
0x18007da94  mov     r8, rax
0x18007da97  mov     r9, r14
0x18007da9a  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18007da9f  mov     ebx, eax
0x18007daa1  lea     rcx, [rbp+length]; this
0x18007daa5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007daaa  lea     rcx, [rbp+var_48]; this
0x18007daae  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18007dab3  lea     rcx, [rbp+var_50]
0x18007dab7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007dabc  mov     eax, ebx
0x18007dabe  mov     rcx, [rbp+var_8]
0x18007dac2  xor     rcx, rsp; StackCookie
0x18007dac5  call    __security_check_cookie
0x18007daca  mov     rbx, [rsp+80h+arg_18]
0x18007dad2  add     rsp, 80h
0x18007dad9  pop     r15
0x18007dadb  pop     r14
0x18007dadd  pop     rdi
0x18007dade  pop     rsi
0x18007dadf  pop     rbp
0x18007dae0  retn
```
