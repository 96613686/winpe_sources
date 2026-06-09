# Windows::Devices::PointOfService::InboxBarcodeDecoder::Initialize(ulong)

- ea: `0x18046ee00`
- end: `0x18046f040`
- name: `?Initialize@InboxBarcodeDecoder@PointOfService@Devices@Windows@@QEAAJK@Z`
- size: `576`
- prototype: `__int64 __fastcall(Windows::Devices::PointOfService::InboxBarcodeDecoder *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1802d4428`

## callees

- `0x180038f3c`
- `0x1800702a8`
- `0x18008b0b0`
- `0x18046ee00`
- `0x18046f048`
- `0x18046f078`
- `0x18046f0bc`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ee96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046eeaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046eebe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046eed2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046eee6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046eefa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046efb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ee96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046eeaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046eebe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046eed2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046eee6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046eefa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046ef9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18046efb1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18046ee2e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18046ee2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18046ee47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18046ee47`

## string_xrefs

- `0x18046ee27`: `DMRCDecoder.DLL`
- `0x18046eea0`: `DeleteDecoder`
- `0x18046ee8f`: `CreateDecoder`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Devices::PointOfService::InboxBarcodeDecoder::Initialize(__int64 (**this)(void))
{
  HMODULE *v2; // rdi
  HMODULE Library; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 (*v6)(void); // rax
  int v7; // edi
  __int64 v8; // rax
  char v10; // [rsp+40h] [rbp+8h] BYREF

  wil::AcquireSRWLockExclusive(&v10, this);
  v2 = (HMODULE *)(this + 1);
  Library = LoadLibraryExW(L"DMRCDecoder.DLL", 0, 0x800u);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    this + 1,
    Library);
  if ( this[1] )
  {
    this[3] = GetProcAddress((HMODULE)this[1], "CreateDecoder");
    this[4] = GetProcAddress(*v2, "DeleteDecoder");
    this[5] = GetProcAddress(*v2, "GetSupportedBarcodeTypes");
    this[6] = GetProcAddress(*v2, "SetActiveBarcodeTypes");
    this[7] = GetProcAddress(*v2, "GetActiveBarcodeTypes");
    this[8] = GetProcAddress(*v2, "GetBarcodeAttributesSupport");
    this[9] = GetProcAddress(*v2, "SetBarcodeCheckDigitAttribute");
    this[10] = GetProcAddress(*v2, "SetBarcodeTransmitCheckDigitAttribute");
    this[11] = GetProcAddress(*v2, "SetBarcodeDecodeLengthAttribute");
    this[12] = GetProcAddress(*v2, "Detect");
    this[13] = GetProcAddress(*v2, "GetPayloadCount");
    this[14] = GetProcAddress(*v2, "GetPayloadBarcodeType");
    this[15] = GetProcAddress(*v2, "GetPayloadData");
    this[16] = GetProcAddress(*v2, "GetPayloadRawData");
    this[17] = GetProcAddress(*v2, "EnableFalsePositiveMitigation");
    v6 = this[3];
    if ( v6 )
    {
      v7 = 0;
      v8 = v6();
      this[2] = (__int64 (*)(void))v8;
      if ( !v8 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2));
        v7 = -2147024882;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
      v7 = -2147024769;
    }
    v5 = v7;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v10);
  return v5;
}

```

## disassembly

```asm
0x18046ee00  mov     [rsp+arg_8], rbx
0x18046ee05  push    rdi
0x18046ee06  sub     rsp, 30h
0x18046ee0a  mov     rbx, rcx
0x18046ee0d  mov     rdx, rcx
0x18046ee10  lea     rcx, [rsp+38h+arg_0]
0x18046ee15  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18046ee1a  nop
0x18046ee1b  lea     rdi, [rbx+8]
0x18046ee1f  xor     edx, edx; hFile
0x18046ee21  mov     r8d, 800h; dwFlags
0x18046ee27  lea     rcx, aDmrcdecoderDll; "DMRCDecoder.DLL"
0x18046ee2e  call    cs:__imp_LoadLibraryExW
0x18046ee34  mov     rdx, rax
0x18046ee37  mov     rcx, rdi
0x18046ee3a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18046ee3f  mov     rcx, [rdi]; hModule
0x18046ee42  test    rcx, rcx
0x18046ee45  jnz     short loc_18046EE8F
0x18046ee47  call    cs:__imp_GetLastError
0x18046ee4d  mov     ebx, eax
0x18046ee4f  test    eax, eax
0x18046ee51  jle     short loc_18046EE5C
0x18046ee53  movzx   ebx, ax
0x18046ee56  or      ebx, 80070000h
0x18046ee5c  lea     rax, WPP_GLOBAL_Control
0x18046ee63  mov     rcx, cs:WPP_GLOBAL_Control
0x18046ee6a  cmp     rcx, rax
0x18046ee6d  jz      loc_18046F029
0x18046ee73  test    byte ptr [rcx+1Ch], 1
0x18046ee77  jz      loc_18046F029
0x18046ee7d  mov     [rsp+38h+var_18], ebx
0x18046ee81  mov     rcx, [rcx+10h]
0x18046ee85  call    WPP_SF_Sd
0x18046ee8a  jmp     loc_18046F029
0x18046ee8f  lea     rdx, aCreatedecoder; "CreateDecoder"
0x18046ee96  call    cs:__imp_GetProcAddress
0x18046ee9c  mov     [rbx+18h], rax
0x18046eea0  lea     rdx, aDeletedecoder; "DeleteDecoder"
0x18046eea7  mov     rcx, [rdi]; hModule
0x18046eeaa  call    cs:__imp_GetProcAddress
0x18046eeb0  mov     [rbx+20h], rax
0x18046eeb4  lea     rdx, aGetsupportedba; "GetSupportedBarcodeTypes"
0x18046eebb  mov     rcx, [rdi]; hModule
0x18046eebe  call    cs:__imp_GetProcAddress
0x18046eec4  mov     [rbx+28h], rax
0x18046eec8  lea     rdx, aSetactivebarco; "SetActiveBarcodeTypes"
0x18046eecf  mov     rcx, [rdi]; hModule
0x18046eed2  call    cs:__imp_GetProcAddress
0x18046eed8  mov     [rbx+30h], rax
0x18046eedc  lea     rdx, aGetactivebarco; "GetActiveBarcodeTypes"
0x18046eee3  mov     rcx, [rdi]; hModule
0x18046eee6  call    cs:__imp_GetProcAddress
0x18046eeec  mov     [rbx+38h], rax
0x18046eef0  lea     rdx, aGetbarcodeattr; "GetBarcodeAttributesSupport"
0x18046eef7  mov     rcx, [rdi]; hModule
0x18046eefa  call    cs:__imp_GetProcAddress
0x18046ef00  mov     [rbx+40h], rax
0x18046ef04  lea     rdx, aSetbarcodechec; "SetBarcodeCheckDigitAttribute"
0x18046ef0b  mov     rcx, [rdi]; hModule
0x18046ef0e  call    cs:__imp_GetProcAddress
0x18046ef14  mov     [rbx+48h], rax
0x18046ef18  lea     rdx, aSetbarcodetran; "SetBarcodeTransmitCheckDigitAttribute"
0x18046ef1f  mov     rcx, [rdi]; hModule
0x18046ef22  call    cs:__imp_GetProcAddress
0x18046ef28  mov     [rbx+50h], rax
0x18046ef2c  lea     rdx, aSetbarcodedeco; "SetBarcodeDecodeLengthAttribute"
0x18046ef33  mov     rcx, [rdi]; hModule
0x18046ef36  call    cs:__imp_GetProcAddress
0x18046ef3c  mov     [rbx+58h], rax
0x18046ef40  lea     rdx, aDetect; "Detect"
0x18046ef47  mov     rcx, [rdi]; hModule
0x18046ef4a  call    cs:__imp_GetProcAddress
0x18046ef50  mov     [rbx+60h], rax
0x18046ef54  lea     rdx, aGetpayloadcoun; "GetPayloadCount"
0x18046ef5b  mov     rcx, [rdi]; hModule
0x18046ef5e  call    cs:__imp_GetProcAddress
0x18046ef64  mov     [rbx+68h], rax
0x18046ef68  lea     rdx, aGetpayloadbarc; "GetPayloadBarcodeType"
0x18046ef6f  mov     rcx, [rdi]; hModule
0x18046ef72  call    cs:__imp_GetProcAddress
0x18046ef78  mov     [rbx+70h], rax
0x18046ef7c  lea     rdx, aGetpayloaddata; "GetPayloadData"
0x18046ef83  mov     rcx, [rdi]; hModule
0x18046ef86  call    cs:__imp_GetProcAddress
0x18046ef8c  mov     [rbx+78h], rax
0x18046ef90  lea     rdx, aGetpayloadrawd; "GetPayloadRawData"
0x18046ef97  mov     rcx, [rdi]; hModule
0x18046ef9a  call    cs:__imp_GetProcAddress
0x18046efa0  mov     [rbx+80h], rax
0x18046efa7  lea     rdx, aEnablefalsepos; "EnableFalsePositiveMitigation"
0x18046efae  mov     rcx, [rdi]; hModule
0x18046efb1  call    cs:__imp_GetProcAddress
0x18046efb7  mov     [rbx+88h], rax
0x18046efbe  mov     rax, [rbx+18h]
0x18046efc2  test    rax, rax
0x18046efc5  jz      short loc_18046F000
0x18046efc7  xor     edi, edi
0x18046efc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18046efce  mov     [rbx+10h], rax
0x18046efd2  test    rax, rax
0x18046efd5  jnz     short loc_18046F027
0x18046efd7  lea     rax, WPP_GLOBAL_Control
0x18046efde  mov     rcx, cs:WPP_GLOBAL_Control
0x18046efe5  cmp     rcx, rax
0x18046efe8  jz      short loc_18046EFF9
0x18046efea  test    byte ptr [rcx+1Ch], 1
0x18046efee  jz      short loc_18046EFF9
0x18046eff0  mov     rcx, [rcx+10h]
0x18046eff4  call    WPP_SF_
0x18046eff9  mov     edi, 8007000Eh
0x18046effe  jmp     short loc_18046F027
0x18046f000  lea     rax, WPP_GLOBAL_Control
0x18046f007  mov     rcx, cs:WPP_GLOBAL_Control
0x18046f00e  cmp     rcx, rax
0x18046f011  jz      short loc_18046F022
0x18046f013  test    byte ptr [rcx+1Ch], 1
0x18046f017  jz      short loc_18046F022
0x18046f019  mov     rcx, [rcx+10h]
0x18046f01d  call    WPP_SF_S
0x18046f022  mov     edi, 8007007Fh
0x18046f027  mov     ebx, edi
0x18046f029  lea     rcx, [rsp+38h+arg_0]
0x18046f02e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18046f033  mov     eax, ebx
0x18046f035  mov     rbx, [rsp+38h+arg_8]
0x18046f03a  add     rsp, 30h
0x18046f03e  pop     rdi
0x18046f03f  retn
```
