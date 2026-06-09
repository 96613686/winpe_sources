# LocationDataSource::InitializeInDisconnectableContext(tagComCallData *)

- ea: `0x1800117d0`
- end: `0x180011aa3`
- name: `?InitializeInDisconnectableContext@LocationDataSource@@CAJPEAUtagComCallData@@@Z`
- size: `723`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000166c`
- `0x1800018fc`
- `0x1800051f0`
- `0x180006844`
- `0x18000885c`
- `0x18001052c`
- `0x1800105cc`
- `0x18001063c`
- `0x1800117d0`
- `0x18001b150`
- `0x18001d010`

## string_xrefs

- `0x180011842`: `onecore\base\win32\winnls\tzautoupdate\locationdatasource.cpp`
- `0x1800118bb`: `onecore\base\win32\winnls\tzautoupdate\locationdatasource.cpp`

## pseudocode

```c
__int64 __fastcall LocationDataSource::InitializeInDisconnectableContext(struct tagComCallData *a1)
{
  _QWORD *pUserDefined; // r15
  _QWORD *v2; // r14
  int v3; // ebx
  __int64 v4; // rdx
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rdx
  BOOL v10; // edi
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  char *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  char *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // r14
  __int64 (__fastcall *v26)(_QWORD, GUID *, __int64 *); // rsi
  int v27; // [rsp+20h] [rbp-60h]
  __int64 v28; // [rsp+30h] [rbp-50h] BYREF
  __int64 v29; // [rsp+38h] [rbp-48h] BYREF
  char v30; // [rsp+40h] [rbp-40h] BYREF
  char v31; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v33; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  pUserDefined = a1->pUserDefined;
  v2 = pUserDefined + 4;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Devices.Geolocation.Geolocator",
    0x27u,
    0x26u);
  v3 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>(
         v33,
         pUserDefined + 4);
  if ( v3 < 0 )
  {
    v4 = 101;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\locationdatasource.cpp",
      (const char *)(unsigned int)v3,
      v27);
    return (unsigned int)v3;
  }
  if ( !*((_BYTE *)pUserDefined + 76) )
  {
    v28 = 0;
    v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v2;
    v7 = **(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v2;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
    v8 = v7(v6, &GUID_d1b42e6d_8891_43b4_ad36_27c6fe9a97b1, &v28);
    v3 = v8;
    if ( v8 < 0 )
    {
      v9 = 106;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\locationdatasource.cpp",
        (const char *)(unsigned int)v8,
        v27);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
      return (unsigned int)v3;
    }
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 48LL))(v28);
    v3 = v8;
    if ( v8 < 0 )
    {
      v9 = 107;
      goto LABEL_10;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
  }
  v10 = *((_DWORD *)pUserDefined + 3) == 1;
  v3 = (*(__int64 (__fastcall **)(_QWORD, bool))(*(_QWORD *)*v2 + 56LL))(*v2, *((_DWORD *)pUserDefined + 3) == 1);
  if ( v3 < 0 )
  {
    v4 = 116;
    goto LABEL_3;
  }
  if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL, v12) )
  {
    LODWORD(v28) = v10;
    v29 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v13,
      (__int64)byte_180029301,
      v14,
      v15,
      (__int64)&v29,
      (__int64)&v28);
  }
  v29 = (__int64)pUserDefined;
  v16 = (char *)Microsoft::WRL::Callback_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___(
                  &v28,
                  &v29);
  v17 = 0;
  if ( &v30 != v16 )
  {
    v17 = *(_QWORD *)v16;
    *(_QWORD *)v16 = 0;
  }
  v18 = pUserDefined[5];
  pUserDefined[5] = v17;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v19 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v29 = (__int64)pUserDefined;
  v20 = (char *)Microsoft::WRL::Callback_Windows::Foundation::ITypedEventHandler_Windows::Devices::Geolocation::Geolocator___Windows::Devices::Geolocation::PositionChangedEventArgs_____lambda_c300570cc2d0924e916db4b97c5536e3___(
                  &v28,
                  &v29);
  v21 = 0;
  if ( &v31 != v20 )
  {
    v21 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
  }
  v22 = pUserDefined[7];
  pUserDefined[7] = v21;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v23 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = 10000000LL * *((unsigned int *)pUserDefined + 18);
  v25 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v2;
  v26 = (*v25)[14];
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(pUserDefined + 6);
  v3 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64, __int64, _QWORD *))v26)(
         v25,
         6000000000LL,
         v24,
         pUserDefined + 6);
  if ( v3 < 0 )
  {
    v4 = 147;
    goto LABEL_3;
  }
  return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)pUserDefined[6] + 48LL))(
           pUserDefined[6],
           pUserDefined[5]);
}

```

## disassembly

```asm
0x1800117d0  mov     [rsp-28h+arg_8], rbx
0x1800117d5  mov     [rsp-28h+arg_10], rsi
0x1800117da  push    rbp
0x1800117db  push    rdi
0x1800117dc  push    r12
0x1800117de  push    r14
0x1800117e0  push    r15
0x1800117e2  mov     rbp, rsp
0x1800117e5  sub     rsp, 80h
0x1800117ec  mov     rax, cs:__security_cookie
0x1800117f3  xor     rax, rsp
0x1800117f6  mov     [rbp+var_10], rax
0x1800117fa  mov     r15, [rcx+8]
0x1800117fe  lea     r14, [r15+20h]
0x180011802  mov     [rbp+var_18], 0
0x18001180a  mov     r9d, 26h ; '&'; unsigned int
0x180011810  lea     r8d, [r9+1]; unsigned int
0x180011814  lea     rdx, ?RuntimeClass_Windows_Devices_Geolocation_Geolocator@@3QBGB; "Windows.Devices.Geolocation.Geolocator"
0x18001181b  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001181f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011824  mov     rdx, r14
0x180011827  mov     rcx, [rbp+var_18]
0x18001182b  call    ??$ActivateInstance@V?$ComPtr@UIGeolocator@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIGeolocator@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>)
0x180011830  mov     ebx, eax
0x180011832  test    eax, eax
0x180011834  jns     short loc_180011855
0x180011836  mov     edx, 65h ; 'e'; void *
0x18001183b  mov     rcx, [rbp+28h]; this
0x18001183f  mov     r9d, ebx; char *
0x180011842  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x180011849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001184e  mov     eax, ebx
0x180011850  jmp     loc_180011A7B
0x180011855  cmp     byte ptr [r15+4Ch], 0
0x18001185a  jnz     loc_1800118E3
0x180011860  mov     [rbp+var_50], 0
0x180011868  mov     rdi, [r14]
0x18001186b  mov     rax, [rdi]
0x18001186e  mov     rbx, [rax]
0x180011871  lea     rcx, [rbp+var_50]
0x180011875  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001187a  lea     r8, [rbp+var_50]
0x18001187e  lea     rdx, _GUID_d1b42e6d_8891_43b4_ad36_27c6fe9a97b1
0x180011885  mov     rcx, rdi
0x180011888  mov     rax, rbx
0x18001188b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011890  mov     ebx, eax
0x180011892  test    eax, eax
0x180011894  jns     short loc_18001189D
0x180011896  mov     edx, 6Ah ; 'j'
0x18001189b  jmp     short loc_1800118B8
0x18001189d  mov     rcx, [rbp+var_50]
0x1800118a1  mov     rax, [rcx]
0x1800118a4  mov     rax, [rax+30h]
0x1800118a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118ad  mov     ebx, eax
0x1800118af  test    eax, eax
0x1800118b1  jns     short loc_1800118DA
0x1800118b3  mov     edx, 6Bh ; 'k'; void *
0x1800118b8  mov     r9d, eax; char *
0x1800118bb  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x1800118c2  mov     rcx, [rbp+28h]; this
0x1800118c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800118cb  nop
0x1800118cc  lea     rcx, [rbp+var_50]
0x1800118d0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800118d5  jmp     loc_18001184E
0x1800118da  lea     rcx, [rbp+var_50]
0x1800118de  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800118e3  xor     edi, edi
0x1800118e5  cmp     dword ptr [r15+0Ch], 1
0x1800118ea  setz    dil
0x1800118ee  mov     rcx, [r14]
0x1800118f1  mov     rax, [rcx]
0x1800118f4  mov     edx, edi
0x1800118f6  mov     rax, [rax+38h]
0x1800118fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118ff  mov     ebx, eax
0x180011901  test    eax, eax
0x180011903  jns     short loc_18001190F
0x180011905  mov     edx, 74h ; 't'
0x18001190a  jmp     loc_18001183B
0x18001190f  mov     eax, cs:dword_180030000
0x180011915  cmp     eax, 5
0x180011918  jbe     short loc_180011956
0x18001191a  mov     rdx, 200000000000h
0x180011924  call    _tlgKeywordOn
0x180011929  test    al, al
0x18001192b  jz      short loc_180011956
0x18001192d  mov     dword ptr [rbp+var_50], edi
0x180011930  mov     [rbp+var_48], 1000000h
0x180011938  lea     rax, [rbp+var_50]
0x18001193c  mov     [rsp+80h+var_58], rax
0x180011941  lea     rax, [rbp+var_48]
0x180011945  mov     [rsp+80h+var_60], rax
0x18001194a  lea     rdx, byte_180029301
0x180011951  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180011956  mov     [rbp+var_48], r15
0x18001195a  lea     rdx, [rbp+var_48]
0x18001195e  lea     rcx, [rbp+var_50]
0x180011962  call    Microsoft__WRL__Callback_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Devices__Geolocation__Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___
0x180011967  xor     ecx, ecx
0x180011969  lea     rdx, [rbp+var_40]
0x18001196d  cmp     rdx, rax
0x180011970  jz      short loc_18001197C
0x180011972  mov     rcx, [rax]
0x180011975  mov     qword ptr [rax], 0
0x18001197c  mov     rdx, [r15+28h]
0x180011980  mov     [r15+28h], rcx
0x180011984  test    rdx, rdx
0x180011987  jz      short loc_180011999
0x180011989  mov     rax, [rdx]
0x18001198c  mov     rcx, rdx
0x18001198f  mov     rax, [rax+10h]
0x180011993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011998  nop
0x180011999  mov     rcx, [rbp+var_50]
0x18001199d  test    rcx, rcx
0x1800119a0  jz      short loc_1800119B7
0x1800119a2  mov     [rbp+var_50], 0
0x1800119aa  mov     rax, [rcx]
0x1800119ad  mov     rax, [rax+10h]
0x1800119b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119b6  nop
0x1800119b7  mov     [rbp+var_48], r15
0x1800119bb  lea     rdx, [rbp+var_48]
0x1800119bf  lea     rcx, [rbp+var_50]
0x1800119c3  call    Microsoft__WRL__Callback_Windows__Foundation__ITypedEventHandler_Windows__Devices__Geolocation__Geolocator___Windows__Devices__Geolocation__PositionChangedEventArgs_____lambda_c300570cc2d0924e916db4b97c5536e3___
0x1800119c8  xor     ecx, ecx
0x1800119ca  lea     rdx, [rbp+var_38]
0x1800119ce  cmp     rdx, rax
0x1800119d1  jz      short loc_1800119DD
0x1800119d3  mov     rcx, [rax]
0x1800119d6  mov     qword ptr [rax], 0
0x1800119dd  mov     rdx, [r15+38h]
0x1800119e1  mov     [r15+38h], rcx
0x1800119e5  test    rdx, rdx
0x1800119e8  jz      short loc_1800119FA
0x1800119ea  mov     rax, [rdx]
0x1800119ed  mov     rcx, rdx
0x1800119f0  mov     rax, [rax+10h]
0x1800119f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119f9  nop
0x1800119fa  mov     rcx, [rbp+var_50]
0x1800119fe  test    rcx, rcx
0x180011a01  jz      short loc_180011A18
0x180011a03  mov     [rbp+var_50], 0
0x180011a0b  mov     rax, [rcx]
0x180011a0e  mov     rax, [rax+10h]
0x180011a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a17  nop
0x180011a18  mov     rdi, 165A0BC00h
0x180011a22  mov     eax, [r15+48h]
0x180011a26  imul    rbx, rax, 989680h
0x180011a2d  mov     r14, [r14]
0x180011a30  mov     rax, [r14]
0x180011a33  mov     rsi, [rax+70h]
0x180011a37  lea     r12, [r15+30h]
0x180011a3b  mov     rcx, r12
0x180011a3e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180011a43  mov     r9, r12
0x180011a46  mov     r8, rbx
0x180011a49  mov     rdx, rdi
0x180011a4c  mov     rcx, r14
0x180011a4f  mov     rax, rsi
0x180011a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a57  mov     ebx, eax
0x180011a59  test    eax, eax
0x180011a5b  jns     short loc_180011A67
0x180011a5d  mov     edx, 93h
0x180011a62  jmp     loc_18001183B
0x180011a67  mov     rcx, [r12]
0x180011a6b  mov     rax, [rcx]
0x180011a6e  mov     rdx, [r15+28h]
0x180011a72  mov     rax, [rax+30h]
0x180011a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a7b  mov     rcx, [rbp+var_10]
0x180011a7f  xor     rcx, rsp; StackCookie
0x180011a82  call    __security_check_cookie
0x180011a87  lea     r11, [rsp+80h+var_s0]
0x180011a8f  mov     rbx, [r11+38h]
0x180011a93  mov     rsi, [r11+40h]
0x180011a97  mov     rsp, r11
0x180011a9a  pop     r15
0x180011a9c  pop     r14
0x180011a9e  pop     r12
0x180011aa0  pop     rdi
0x180011aa1  pop     rbp
0x180011aa2  retn
```
