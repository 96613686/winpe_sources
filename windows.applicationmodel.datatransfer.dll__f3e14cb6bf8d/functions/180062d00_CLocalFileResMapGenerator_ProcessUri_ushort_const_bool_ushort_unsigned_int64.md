# CLocalFileResMapGenerator::ProcessUri(ushort const *,bool,ushort *,unsigned __int64)

- ea: `0x180062d00`
- end: `0x180062f21`
- name: `?ProcessUri@CLocalFileResMapGenerator@@UEAAJPEBG_NPEAG_K@Z`
- size: `545`
- prototype: `__int64 __fastcall(CLocalFileResMapGenerator *__hidden this, PCWSTR pszUrl, bool, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x180006914`
- `0x180008b68`
- `0x180062d00`
- `0x180064d70`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062eda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062eda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062e32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062e32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180062e1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180062e1b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180062e60`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180062e60`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x180062d53`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x180062d53`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLocalFileResMapGenerator::ProcessUri(
        CLocalFileResMapGenerator *this,
        WCHAR *pszUrl,
        __int64 a3,
        unsigned __int16 *a4)
{
  unsigned int v5; // edi
  void **v6; // rax
  const struct _GUID *v7; // r8
  const WCHAR *StringRawBuffer; // rax
  __int64 v9; // rcx
  int v10; // edx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  _BYTE v15[8]; // [rsp+30h] [rbp-D0h] BYREF
  BOOL hasEmbedNull[2]; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcchPath; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v20[4]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR String2[12]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR pszPath[264]; // [rsp+90h] [rbp-70h] BYREF

  string = (HSTRING)pszUrl;
  *a4 = 0;
  v5 = 1;
  pcchPath = 260;
  if ( PathCreateFromUrlW(pszUrl, pszPath, &pcchPath, 0) >= 0 )
  {
    Windows::Internal::StringReference::StringReference(v20, &string);
    v15[0] = 0;
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, _BYTE *))(**((_QWORD **)this + 2) + 64LL))(
           *((_QWORD *)this + 2),
           v20[0],
           v15) >= 0
      && !v15[0] )
    {
      v18 = 0;
      v6 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v18);
      if ( (int)CLocalFileResMapGenerator::_ValidateFileAccessAndCreateStorageFile(this, pszPath, v7, v6) >= 0 )
      {
        string = 0;
        if ( (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 56LL))(v18, &string) >= 0 )
        {
          wcscpy(String2, L"image/");
          hasEmbedNull[0] = 0;
          WindowsStringHasEmbeddedNull(string, hasEmbedNull);
          if ( !hasEmbedNull[0] )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            v9 = -1;
            do
              ++v9;
            while ( StringRawBuffer[v9] );
            v10 = 6;
            if ( (int)v9 < 6 )
              v10 = v9;
            if ( CompareStringOrdinal(StringRawBuffer, v10, String2, 6, 1) == 2 )
            {
              *(_QWORD *)hasEmbedNull = 0;
              if ( (*(int (__fastcall **)(_QWORD, __int64, BOOL *))(**((_QWORD **)this + 3) + 48LL))(
                     *((_QWORD *)this + 3),
                     v18,
                     hasEmbedNull) >= 0 )
              {
                v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _BYTE *))(**((_QWORD **)this + 2) + 80LL))(
                        *((_QWORD *)this + 2),
                        v20[0],
                        *(_QWORD *)hasEmbedNull,
                        v15);
                if ( v11 >= 0 )
                  v11 = 1;
                v5 = v11;
              }
              v12 = *(_QWORD *)hasEmbedNull;
              if ( *(_QWORD *)hasEmbedNull )
              {
                *(_QWORD *)hasEmbedNull = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
              }
            }
          }
        }
        if ( string )
          WindowsDeleteString(string);
      }
      v13 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180062d00  mov     [rsp-8+arg_10], rbx
0x180062d05  push    rbp
0x180062d06  push    rsi
0x180062d07  push    rdi
0x180062d08  lea     rbp, [rsp-1B0h]
0x180062d10  sub     rsp, 2B0h
0x180062d17  mov     rax, cs:__security_cookie
0x180062d1e  xor     rax, rsp
0x180062d21  mov     [rbp+1C0h+var_20], rax
0x180062d28  mov     r10, rdx
0x180062d2b  mov     rbx, rcx
0x180062d2e  mov     [rsp+2C0h+string], rdx
0x180062d33  xor     esi, esi
0x180062d35  mov     [r9], si
0x180062d39  lea     edi, [rsi+1]
0x180062d3c  mov     [rsp+2C0h+pcchPath], 104h
0x180062d44  xor     r9d, r9d; dwFlags
0x180062d47  lea     r8, [rsp+2C0h+pcchPath]; pcchPath
0x180062d4c  lea     rdx, [rbp+1C0h+pszPath]; pszPath
0x180062d50  mov     rcx, r10; pszUrl
0x180062d53  call    cs:__imp_PathCreateFromUrlW
0x180062d59  test    eax, eax
0x180062d5b  js      loc_180062EFD
0x180062d61  lea     rdx, [rsp+2C0h+string]
0x180062d66  lea     rcx, [rsp+2C0h+var_268]
0x180062d6b  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x180062d70  mov     [rsp+2C0h+var_290], sil
0x180062d75  mov     rcx, [rbx+10h]
0x180062d79  mov     rax, [rcx]
0x180062d7c  lea     r8, [rsp+2C0h+var_290]
0x180062d81  mov     rdx, [rsp+2C0h+var_268]
0x180062d86  mov     rax, [rax+40h]
0x180062d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d8f  test    eax, eax
0x180062d91  js      loc_180062EFD
0x180062d97  cmp     [rsp+2C0h+var_290], sil
0x180062d9c  jnz     loc_180062EFD
0x180062da2  mov     [rsp+2C0h+var_278], rsi
0x180062da7  lea     rcx, [rsp+2C0h+var_278]
0x180062dac  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x180062db1  mov     r9, rax; void **
0x180062db4  lea     rdx, [rbp+1C0h+pszPath]; unsigned __int16 *
0x180062db8  mov     rcx, rbx; this
0x180062dbb  call    ?_ValidateFileAccessAndCreateStorageFile@CLocalFileResMapGenerator@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z; CLocalFileResMapGenerator::_ValidateFileAccessAndCreateStorageFile(ushort const *,_GUID const &,void * *)
0x180062dc0  test    eax, eax
0x180062dc2  js      loc_180062EE1
0x180062dc8  mov     [rsp+2C0h+string], rsi
0x180062dcd  mov     rcx, [rsp+2C0h+var_278]
0x180062dd2  mov     rax, [rcx]
0x180062dd5  lea     rdx, [rsp+2C0h+string]
0x180062dda  mov     rax, [rax+38h]
0x180062dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062de3  test    eax, eax
0x180062de5  js      loc_180062ED0
0x180062deb  movsd   xmm0, qword ptr cs:aImage; "image/"
0x180062df3  movsd   qword ptr [rsp+2C0h+String2], xmm0
0x180062df9  mov     eax, dword ptr cs:aImage+8; "e/"
0x180062dff  mov     [rbp+1C0h+var_240], eax
0x180062e02  movzx   eax, word ptr cs:aImage+0Ch; ""
0x180062e09  mov     [rbp+1C0h+var_23C], ax
0x180062e0d  mov     [rsp+2C0h+hasEmbedNull], esi
0x180062e11  lea     rdx, [rsp+2C0h+hasEmbedNull]; hasEmbedNull
0x180062e16  mov     rcx, [rsp+2C0h+string]; string
0x180062e1b  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180062e21  cmp     [rsp+2C0h+hasEmbedNull], esi
0x180062e25  jnz     loc_180062ED0
0x180062e2b  xor     edx, edx; length
0x180062e2d  mov     rcx, [rsp+2C0h+string]; string
0x180062e32  call    cs:__imp_WindowsGetStringRawBuffer
0x180062e38  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180062e3c  inc     rcx
0x180062e3f  cmp     [rax+rcx*2], si
0x180062e43  jnz     short loc_180062E3C
0x180062e45  mov     r9d, 6; cchCount2
0x180062e4b  mov     edx, r9d
0x180062e4e  cmp     ecx, r9d
0x180062e51  cmovl   edx, ecx; cchCount1
0x180062e54  mov     [rsp+2C0h+bIgnoreCase], edi; bIgnoreCase
0x180062e58  lea     r8, [rsp+2C0h+String2]; lpString2
0x180062e5d  mov     rcx, rax; lpString1
0x180062e60  call    cs:__imp_CompareStringOrdinal
0x180062e66  cmp     eax, 2
0x180062e69  jnz     short loc_180062ED0
0x180062e6b  mov     qword ptr [rsp+2C0h+hasEmbedNull], rsi
0x180062e70  mov     rcx, [rbx+18h]
0x180062e74  mov     rax, [rcx]
0x180062e77  lea     r8, [rsp+2C0h+hasEmbedNull]
0x180062e7c  mov     rdx, [rsp+2C0h+var_278]
0x180062e81  mov     rax, [rax+30h]
0x180062e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e8a  test    eax, eax
0x180062e8c  js      short loc_180062EB4
0x180062e8e  mov     rcx, [rbx+10h]
0x180062e92  mov     rax, [rcx]
0x180062e95  lea     r9, [rsp+2C0h+var_290]
0x180062e9a  mov     r8, qword ptr [rsp+2C0h+hasEmbedNull]
0x180062e9f  mov     rdx, [rsp+2C0h+var_268]
0x180062ea4  mov     rax, [rax+50h]
0x180062ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062ead  test    eax, eax
0x180062eaf  cmovns  eax, edi
0x180062eb2  mov     edi, eax
0x180062eb4  mov     rcx, qword ptr [rsp+2C0h+hasEmbedNull]
0x180062eb9  test    rcx, rcx
0x180062ebc  jz      short loc_180062ED0
0x180062ebe  mov     qword ptr [rsp+2C0h+hasEmbedNull], rsi
0x180062ec3  mov     rax, [rcx]
0x180062ec6  mov     rax, [rax+10h]
0x180062eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062ecf  nop
0x180062ed0  mov     rcx, [rsp+2C0h+string]; string
0x180062ed5  test    rcx, rcx
0x180062ed8  jz      short loc_180062EE1
0x180062eda  call    cs:__imp_WindowsDeleteString
0x180062ee0  nop
0x180062ee1  mov     rcx, [rsp+2C0h+var_278]
0x180062ee6  test    rcx, rcx
0x180062ee9  jz      short loc_180062EFD
0x180062eeb  mov     [rsp+2C0h+var_278], rsi
0x180062ef0  mov     rdx, [rcx]
0x180062ef3  mov     rax, [rdx+10h]
0x180062ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062efc  nop
0x180062efd  mov     eax, edi
0x180062eff  mov     rcx, [rbp+1C0h+var_20]
0x180062f06  xor     rcx, rsp; StackCookie
0x180062f09  call    __security_check_cookie
0x180062f0e  mov     rbx, [rsp+2C0h+arg_10]
0x180062f16  add     rsp, 2B0h
0x180062f1d  pop     rdi
0x180062f1e  pop     rsi
0x180062f1f  pop     rbp
0x180062f20  retn
```
