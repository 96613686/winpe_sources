# CInteractiveObjectHapticsImpl::RuntimeClassInitialize(ulong,CInteractiveObjectDevice *,tagSIMPLEHAPTICSCTRL_DEVICE_INFO &)

- ea: `0x1800be9f0`
- end: `0x1800beb61`
- name: `?RuntimeClassInitialize@CInteractiveObjectHapticsImpl@@UEAAJKPEAVCInteractiveObjectDevice@@AEAUtagSIMPLEHAPTICSCTRL_DEVICE_INFO@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(CInteractiveObjectHapticsImpl *__hidden this, unsigned int, struct CInteractiveObjectDevice *, struct tagSIMPLEHAPTICSCTRL_DEVICE_INFO *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180004dd4`
- `0x180014754`
- `0x180020760`
- `0x180033f08`
- `0x1800411a0`
- `0x1800b4030`
- `0x1800be16c`
- `0x1800be918`
- `0x1800be9f0`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800bea9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800bea9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bea86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bea86`

## pseudocode

```c
__int64 __fastcall CInteractiveObjectHapticsImpl::RuntimeClassInitialize(
        CInteractiveObjectHapticsImpl *this,
        int a2,
        struct CInteractiveObjectDevice *a3,
        struct tagSIMPLEHAPTICSCTRL_DEVICE_INFO *a4)
{
  __int64 v6; // r9
  unsigned __int64 v7; // rcx
  HRESULT String; // ebx
  UINT32 v9; // edx
  _QWORD *v10; // rbx
  __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // edi
  __int64 v15; // rdx
  UINT32 length; // [rsp+20h] [rbp-48h] BYREF
  WCHAR sourceString[12]; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *((_DWORD *)this + 22) = a2;
  Microsoft::WRL::ComPtr<Windows::Devices::Haptics::ISimpleHapticsController>::operator=((char *)this + 120, a3);
  v6 = *((unsigned __int16 *)this + 44);
  *((_DWORD *)this + 23) = *((_DWORD *)a4 + 1);
  *((_DWORD *)this + 24) = *(_DWORD *)a4;
  memset(sourceString, 0, 22);
  StringCchPrintfW(sourceString, 0xBu, L"%d", v6);
  length = 0;
  v7 = -1;
  do
    ++v7;
  while ( sourceString[v7] );
  String = ULongLongToUInt(v7, &length);
  if ( String < 0
    || (WindowsDeleteString(*((HSTRING *)this + 10)),
        v9 = length,
        *((_QWORD *)this + 10) = 0,
        String = WindowsCreateString(sourceString, v9, (HSTRING *)this + 10),
        String < 0) )
  {
    v15 = 61;
  }
  else
  {
    v10 = (_QWORD *)((char *)this + 104);
    Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease((char *)this + 104);
    v12 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Devices::Haptics::SimpleHapticsControllerFeedback,Windows::Foundation::Collections::Internal::Vector<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>>>(
            v11,
            (char *)this + 104);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\radialdevice\\lib\\interactiveobjecthapticsimpl.cpp",
        (const char *)(unsigned int)v12,
        length);
      return v13;
    }
    if ( *v10 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *,Windows::Foundation::Collections::IVector<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::NoVersionTag,0>>::InternalRelease((char *)this + 112);
      String = Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *,Windows::Foundation::Collections::IVector<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::NoVersionTag,0>::Make(
                 *v10,
                 (char *)this + 112);
      if ( String >= 0 )
      {
        if ( *((_QWORD *)this + 14) )
          return 0;
        String = -2147024882;
        v15 = 67;
      }
      else
      {
        v15 = 66;
      }
    }
    else
    {
      String = -2147024882;
      v15 = 64;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\radialdevice\\lib\\interactiveobjecthapticsimpl.cpp",
    (const char *)(unsigned int)String,
    length);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800be9f0  mov     [rsp+arg_8], rbx
0x1800be9f5  push    rbp
0x1800be9f6  push    rsi
0x1800be9f7  push    rdi
0x1800be9f8  sub     rsp, 50h
0x1800be9fc  mov     rax, cs:__security_cookie
0x1800bea03  xor     rax, rsp
0x1800bea06  mov     [rsp+68h+var_28], rax
0x1800bea0b  mov     [rcx+58h], edx
0x1800bea0e  mov     rsi, rcx
0x1800bea11  add     rcx, 78h ; 'x'
0x1800bea15  mov     rdx, r8
0x1800bea18  mov     rbx, r9
0x1800bea1b  call    ??4?$ComPtr@UISimpleHapticsController@Haptics@Devices@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUISimpleHapticsController@Haptics@Devices@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Devices::Haptics::ISimpleHapticsController>::operator=(Windows::Devices::Haptics::ISimpleHapticsController *)
0x1800bea20  mov     eax, [rbx+4]
0x1800bea23  lea     r8, aD; "%d"
0x1800bea2a  movzx   r9d, word ptr [rsi+58h]
0x1800bea2f  lea     rcx, [rsp+68h+sourceString]; unsigned __int16 *
0x1800bea34  mov     [rsi+5Ch], eax
0x1800bea37  xorps   xmm0, xmm0
0x1800bea3a  mov     eax, [rbx]
0x1800bea3c  mov     [rsi+60h], eax
0x1800bea3f  xor     eax, eax
0x1800bea41  movups  xmmword ptr [rsp+68h+sourceString], xmm0
0x1800bea46  mov     qword ptr [rsp+68h+sourceString+0Eh], rax
0x1800bea4b  lea     edx, [rax+0Bh]; unsigned __int64
0x1800bea4e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bea53  xor     ebp, ebp
0x1800bea55  lea     rax, [rsp+68h+sourceString]
0x1800bea5a  mov     [rsp+68h+length], ebp; int
0x1800bea5e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800bea62  inc     rcx; unsigned __int64
0x1800bea65  cmp     [rax+rcx*2], bp
0x1800bea69  jnz     short loc_1800BEA62
0x1800bea6b  lea     rdx, [rsp+68h+length]; unsigned int *
0x1800bea70  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bea75  mov     ebx, eax
0x1800bea77  test    eax, eax
0x1800bea79  js      loc_1800BEB2C
0x1800bea7f  lea     rbx, [rsi+50h]
0x1800bea83  mov     rcx, [rbx]; string
0x1800bea86  call    cs:__imp_WindowsDeleteString
0x1800bea8c  mov     edx, [rsp+68h+length]; length
0x1800bea90  lea     rcx, [rsp+68h+sourceString]; sourceString
0x1800bea95  mov     r8, rbx; string
0x1800bea98  mov     [rbx], rbp
0x1800bea9b  call    cs:__imp_WindowsCreateString
0x1800beaa1  mov     ebx, eax
0x1800beaa3  test    eax, eax
0x1800beaa5  js      loc_1800BEB2C
0x1800beaab  lea     rbx, [rsi+68h]
0x1800beaaf  mov     rcx, rbx
0x1800beab2  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800beab7  mov     rdx, rbx
0x1800beaba  call    ??$CreateExternalObjectVector@VSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@V?$Vector@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@U?$DefaultEqualityPredicate@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@@6784@U?$DefaultVectorOptions@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@U?$DefaultEqualityPredicate@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@@6784@U?$DefaultVectorOptions@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@@6784@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Devices::Haptics::SimpleHapticsControllerFeedback,Windows::Foundation::Collections::Internal::Vector<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>> * *)
0x1800beabf  mov     edi, eax
0x1800beac1  test    eax, eax
0x1800beac3  jns     short loc_1800BEAE2
0x1800beac5  mov     rcx, [rsp+68h]; this
0x1800beaca  lea     r8, aOnecoreuapWind_27; "onecoreuap\\windows\\advcore\\winrt\\ra"...
0x1800bead1  mov     r9d, eax; char *
0x1800bead4  mov     edx, 3Fh ; '?'; void *
0x1800bead9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800beade  mov     eax, edi
0x1800beae0  jmp     short loc_1800BEB47
0x1800beae2  cmp     [rbx], rbp
0x1800beae5  jnz     short loc_1800BEAF3
0x1800beae7  mov     ebx, 8007000Eh
0x1800beaec  mov     edx, 40h ; '@'
0x1800beaf1  jmp     short loc_1800BEB31
0x1800beaf3  lea     rdi, [rsi+70h]
0x1800beaf7  mov     rcx, rdi
0x1800beafa  call    ?InternalRelease@?$ComPtr@V?$SimpleVectorView@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@U?$IVector@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@@Internal@674@UNoVersionTag@9674@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *,Windows::Foundation::Collections::IVector<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::NoVersionTag,0>>::InternalRelease(void)
0x1800beaff  mov     rcx, [rbx]
0x1800beb02  mov     rdx, rdi
0x1800beb05  call    ?Make@?$SimpleVectorView@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@U?$IVector@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@@Internal@674@UNoVersionTag@9674@$0A@@Internal@Collections@Foundation@Windows@@SAJPEAU?$IVector@PEAVSimpleHapticsControllerFeedback@Haptics@Devices@Windows@@@345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *,Windows::Foundation::Collections::IVector<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::NoVersionTag,0>::Make(Windows::Foundation::Collections::IVector<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *> *,Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *,Windows::Foundation::Collections::IVector<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Devices::Haptics::SimpleHapticsControllerFeedback *>,Windows::Foundation::Collections::Internal::NoVersionTag,0> * *)
0x1800beb0a  mov     ebx, eax
0x1800beb0c  test    eax, eax
0x1800beb0e  jns     short loc_1800BEB17
0x1800beb10  mov     edx, 42h ; 'B'
0x1800beb15  jmp     short loc_1800BEB31
0x1800beb17  cmp     [rdi], rbp
0x1800beb1a  jnz     short loc_1800BEB28
0x1800beb1c  mov     ebx, 8007000Eh
0x1800beb21  mov     edx, 43h ; 'C'
0x1800beb26  jmp     short loc_1800BEB31
0x1800beb28  xor     eax, eax
0x1800beb2a  jmp     short loc_1800BEB47
0x1800beb2c  mov     edx, 3Dh ; '='; void *
0x1800beb31  mov     rcx, [rsp+68h]; this
0x1800beb36  lea     r8, aOnecoreuapWind_27; "onecoreuap\\windows\\advcore\\winrt\\ra"...
0x1800beb3d  mov     r9d, ebx; char *
0x1800beb40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800beb45  mov     eax, ebx
0x1800beb47  mov     rcx, [rsp+68h+var_28]
0x1800beb4c  xor     rcx, rsp; StackCookie
0x1800beb4f  call    __security_check_cookie
0x1800beb54  mov     rbx, [rsp+68h+arg_8]
0x1800beb59  add     rsp, 50h
0x1800beb5d  pop     rdi
0x1800beb5e  pop     rsi
0x1800beb5f  pop     rbp
0x1800beb60  retn
```
