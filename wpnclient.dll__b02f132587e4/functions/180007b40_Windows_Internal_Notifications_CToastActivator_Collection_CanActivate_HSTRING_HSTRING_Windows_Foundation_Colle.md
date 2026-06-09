# Windows::Internal::Notifications::CToastActivator_Collection::CanActivate(HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,uchar *)

- ea: `0x180007b40`
- end: `0x180007d2e`
- name: `?CanActivate@CToastActivator_Collection@Notifications@Internal@Windows@@UEAAJPEAUHSTRING__@@0PEAUIPropertySet@Collections@Foundation@4@PEAE@Z`
- size: `494`
- prototype: `int(Windows::Internal::Notifications::CToastActivator_Collection *__hidden this, HSTRING, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800070e8`
- `0x1800074d0`
- `0x180007b40`
- `0x180007d34`
- `0x1800082b8`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007c36`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007c36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007c4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007c4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007b7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007b7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007bbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007cc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007bbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007cc7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Notifications::CToastActivator_Collection::CanActivate(
        Windows::Internal::Notifications::CToastActivator_Collection *this,
        HSTRING a2,
        HSTRING a3,
        struct Windows::Foundation::Collections::IPropertySet *a4,
        unsigned __int8 *a5)
{
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned __int64 v9; // rbx
  int HandlerInfoFromCollectionAumid; // eax
  void *v11; // rdi
  int v13; // eax
  unsigned int v14; // ebp
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, HSTRING, HSTRING, struct Windows::Foundation::Collections::IPropertySet *); // rbp
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // ebp
  int v21; // [rsp+20h] [rbp-88h]
  LPVOID pv[3]; // [rsp+30h] [rbp-78h] BYREF
  HSTRING string; // [rsp+48h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *a5 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v9 = -1;
  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  HandlerInfoFromCollectionAumid = Windows::Internal::Notifications::CToastActivator_Collection::GetHandlerInfoFromCollectionAumid(
                                     this,
                                     StringRawBuffer,
                                     (unsigned __int16 **)pv,
                                     0);
  v11 = pv[0];
  if ( HandlerInfoFromCollectionAumid < 0 )
  {
LABEL_2:
    if ( v11 )
      CoTaskMemFree(v11);
    return 0;
  }
  v13 = Windows::Internal::Notifications::CToastActivator_Collection::EnsureSwitchInitialized(this);
  v14 = v13;
  if ( v13 >= 0 )
  {
    if ( *((_DWORD *)this + 20) )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 48LL))(
              *((_QWORD *)this + 8),
              *((unsigned int *)this + 21),
              *((_QWORD *)this + 11),
              *((_QWORD *)this + 12));
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
          (const char *)(unsigned int)v19,
          v21);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
        return v20;
      }
      *((_DWORD *)this + 20) = 0;
    }
    v15 = *((_QWORD *)this + 8);
    v16 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v15 + 64LL);
    do
      ++v9;
    while ( *((_WORD *)v11 + v9) );
    if ( v9 > 0xFFFFFFFF )
    {
      LODWORD(v9) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference((PCWSTR)v11, v9, &hstringHeader, &string);
    v17 = v16(v15, string, a3, a4);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
        (const char *)(unsigned int)v17,
        (int)a5);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
      return v18;
    }
    goto LABEL_2;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x78,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
    (const char *)(unsigned int)v13,
    v21);
  if ( v11 )
    CoTaskMemFree(v11);
  return v14;
}

```

## disassembly

```asm
0x180007b40  push    rbx
0x180007b42  push    rbp
0x180007b43  push    rsi
0x180007b44  push    rdi
0x180007b45  push    r12
0x180007b47  push    r14
0x180007b49  push    r15
0x180007b4b  sub     rsp, 70h
0x180007b4f  mov     rax, cs:__security_cookie
0x180007b56  xor     rax, rsp
0x180007b59  mov     [rsp+0A8h+var_40], rax
0x180007b5e  mov     r14, [rsp+0A8h+arg_20]
0x180007b66  mov     rax, rdx
0x180007b69  mov     rsi, rcx
0x180007b6c  xor     edx, edx; length
0x180007b6e  mov     rcx, rax; string
0x180007b71  mov     r12, r9
0x180007b74  mov     r15, r8
0x180007b77  mov     byte ptr [r14], 0
0x180007b7b  call    cs:__imp_WindowsGetStringRawBuffer
0x180007b81  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180007b88  mov     [rsp+0A8h+pv], 0
0x180007b91  mov     rdx, rax; unsigned __int16 *
0x180007b94  mov     [rsp+0A8h+var_70], rbx
0x180007b99  xor     r9d, r9d; unsigned __int16 **
0x180007b9c  mov     [rsp+0A8h+var_68], rbx
0x180007ba1  lea     r8, [rsp+0A8h+pv]; unsigned __int16 **
0x180007ba6  mov     rcx, rsi; this
0x180007ba9  call    ?GetHandlerInfoFromCollectionAumid@CToastActivator_Collection@Notifications@Internal@Windows@@AEAAJPEBGPEAPEAG1@Z; Windows::Internal::Notifications::CToastActivator_Collection::GetHandlerInfoFromCollectionAumid(ushort const *,ushort * *,ushort * *)
0x180007bae  mov     rdi, [rsp+0A8h+pv]
0x180007bb3  test    eax, eax
0x180007bb5  jns     short loc_180007BE3
0x180007bb7  test    rdi, rdi
0x180007bba  jz      short loc_180007BC5
0x180007bbc  mov     rcx, rdi; pv
0x180007bbf  call    cs:__imp_CoTaskMemFree
0x180007bc5  xor     eax, eax
0x180007bc7  mov     rcx, [rsp+0A8h+var_40]
0x180007bcc  xor     rcx, rsp; StackCookie
0x180007bcf  call    __security_check_cookie
0x180007bd4  add     rsp, 70h
0x180007bd8  pop     r15
0x180007bda  pop     r14
0x180007bdc  pop     r12
0x180007bde  pop     rdi
0x180007bdf  pop     rsi
0x180007be0  pop     rbp
0x180007be1  pop     rbx
0x180007be2  retn
0x180007be3  mov     rcx, rsi; this
0x180007be6  call    ?EnsureSwitchInitialized@CToastActivator_Collection@Notifications@Internal@Windows@@AEAAJXZ; Windows::Internal::Notifications::CToastActivator_Collection::EnsureSwitchInitialized(void)
0x180007beb  mov     ebp, eax
0x180007bed  test    eax, eax
0x180007bef  js      loc_180007CA3
0x180007bf5  cmp     dword ptr [rsi+50h], 0
0x180007bf9  jnz     loc_180007CD4
0x180007bff  mov     rsi, [rsi+40h]
0x180007c03  mov     rax, [rsi]
0x180007c06  mov     rbp, [rax+40h]
0x180007c0a  nop     word ptr [rax+rax+00h]
0x180007c10  inc     rbx
0x180007c13  cmp     word ptr [rdi+rbx*2], 0
0x180007c18  jnz     short loc_180007C10
0x180007c1a  mov     eax, 0FFFFFFFFh
0x180007c1f  cmp     rbx, rax
0x180007c22  jbe     short loc_180007C3C
0x180007c24  xor     r9d, r9d; lpArguments
0x180007c27  xor     r8d, r8d; nNumberOfArguments
0x180007c2a  mov     edx, 1; dwExceptionFlags
0x180007c2f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180007c34  mov     ebx, eax
0x180007c36  call    cs:__imp_RaiseException
0x180007c3c  lea     r9, [rsp+0A8h+string]; string
0x180007c41  mov     edx, ebx; length
0x180007c43  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x180007c48  mov     rcx, rdi; sourceString
0x180007c4b  call    cs:__imp_WindowsCreateStringReference
0x180007c51  mov     rdx, [rsp+0A8h+string]
0x180007c56  mov     r9, r12
0x180007c59  mov     r8, r15
0x180007c5c  mov     qword ptr [rsp+0A8h+var_88], r14; int
0x180007c61  mov     rcx, rsi
0x180007c64  mov     rax, rbp
0x180007c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c6c  mov     ebx, eax
0x180007c6e  test    eax, eax
0x180007c70  jns     loc_180007BB7
0x180007c76  mov     rcx, [rsp+0A8h]; this
0x180007c7e  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007c85  mov     r9d, eax; char *
0x180007c88  mov     edx, 88h; void *
0x180007c8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c92  lea     rcx, [rsp+0A8h+pv]
0x180007c97  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180007c9c  mov     eax, ebx
0x180007c9e  jmp     loc_180007BC7
0x180007ca3  mov     rcx, [rsp+0A8h]; this
0x180007cab  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007cb2  mov     r9d, ebp; char *
0x180007cb5  mov     edx, 78h ; 'x'; void *
0x180007cba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007cbf  test    rdi, rdi
0x180007cc2  jz      short loc_180007CCD
0x180007cc4  mov     rcx, rdi; pv
0x180007cc7  call    cs:__imp_CoTaskMemFree
0x180007ccd  mov     eax, ebp
0x180007ccf  jmp     loc_180007BC7
0x180007cd4  mov     rcx, [rsi+40h]
0x180007cd8  mov     r9, [rsi+60h]
0x180007cdc  mov     r8, [rsi+58h]
0x180007ce0  mov     edx, [rsi+54h]
0x180007ce3  mov     rax, [rcx]
0x180007ce6  mov     rax, [rax+30h]
0x180007cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cef  mov     ebp, eax
0x180007cf1  test    eax, eax
0x180007cf3  jns     short loc_180007D22
0x180007cf5  mov     rcx, [rsp+0A8h]; this
0x180007cfd  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007d04  mov     r9d, eax; char *
0x180007d07  mov     edx, 7Fh; void *
0x180007d0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d11  lea     rcx, [rsp+0A8h+pv]
0x180007d16  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180007d1b  mov     eax, ebp
0x180007d1d  jmp     loc_180007BC7
0x180007d22  mov     dword ptr [rsi+50h], 0
0x180007d29  jmp     loc_180007BFF
```
