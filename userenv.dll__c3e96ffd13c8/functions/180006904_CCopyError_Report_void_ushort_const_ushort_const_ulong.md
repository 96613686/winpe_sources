# CCopyError::Report(void *,ushort const *,ushort const *,ulong)

- ea: `0x180006904`
- end: `0x180006b1e`
- name: `?Report@CCopyError@@QEAAJPEAXPEBG1K@Z`
- size: `538`
- prototype: `__int64 __fastcall(CCopyError *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *, DWORD dwMessageId)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800084f0`
- `0x18000a200`
- `0x18000b2d0`

## callees

- `0x180003f60`
- `0x180004f28`
- `0x180005de0`
- `0x180006904`
- `0x180006bf0`
- `0x18000d9b0`
- `0x18001992c`
- `0x180019c00`
- `0x18001a2d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800069e0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800069e0`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800069ee`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800069ee`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800069cb`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800069cb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006a79`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006a79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ac1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ac1`

## string_xrefs

- `0x180006984`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall CCopyError::Report(
        CCopyError *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwMessageId)
{
  int v5; // r15d
  int v6; // r14d
  char v7; // di
  int v8; // ebx
  int v9; // eax
  HRSRC Resource; // rax
  HGLOBAL v11; // rax
  unsigned __int16 *v12; // rax
  __int64 v13; // rcx
  const size_t *v14; // rdx
  int v15; // ecx
  const wchar_t *v16; // rax
  const wchar_t *v17; // rcx
  __int64 v19[3]; // [rsp+40h] [rbp-51h] BYREF
  int v20; // [rsp+58h] [rbp-39h] BYREF
  __int64 v21; // [rsp+60h] [rbp-31h]
  __int64 v22; // [rsp+68h] [rbp-29h]
  int v23; // [rsp+70h] [rbp-21h]
  __int128 v24; // [rsp+78h] [rbp-19h]
  WCHAR Buffer[4]; // [rsp+88h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  v5 = (int)a4;
  *(_DWORD *)Buffer = 0;
  v6 = (int)a3;
  v7 = 0;
  v8 = _InterlockedIncrement((volatile signed __int32 *)this);
  if ( v8 <= 10 )
  {
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    if ( a2 )
    {
      v9 = CThreadContext::ImpersonateUser((CThreadContext *)&v20, a2);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x57,
          (int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
          (const char *)(unsigned int)v9);
    }
    if ( v8 >= 10 )
    {
      if ( (Microsoft_Windows_User_Profiles_GeneralEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(this, EVENT_TOO_MANY_COPY_ERRORS, a3, 1);
    }
    else
    {
      memset(v19, 0, sizeof(v19));
      if ( dwMessageId == 6002
        && (Resource = FindResourceExW(&_ImageBase, (LPCWSTR)6, (LPCWSTR)0x7E, 0)) != 0
        && (v11 = LoadResource(&_ImageBase, Resource)) != 0
        && (v12 = (unsigned __int16 *)LockResource(v11)) != 0
        && ((v13 = *v12, !v12[v13 + 1]) ? (v14 = &Format) : (v14 = (const size_t *)&v12[v13 + 2]),
            (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Initialize(
                   v19,
                   v14) >= 0) )
      {
        if ( (Microsoft_Windows_User_Profiles_GeneralEnableBits & 1) != 0 )
          McTemplateU0zzz_EventWriteTransfer(v15, (unsigned int)EVENT_COPYERROR, v6, v5, v19[0]);
      }
      else
      {
        if ( (Microsoft_Windows_User_Profiles_GeneralEnableBits & 1) != 0 )
        {
          if ( FormatMessageW(0x1100u, 0, dwMessageId, 0, Buffer, 1u, 0) )
          {
            v16 = *(const wchar_t **)Buffer;
          }
          else
          {
            v16 = 0;
            *(_QWORD *)Buffer = 0;
          }
          v17 = L"???";
          if ( v16 )
            v17 = v16;
          McTemplateU0zzz_EventWriteTransfer((_DWORD)v17, (unsigned int)EVENT_COPYERROR, v6, v5, (__int64)v17);
          v7 = 1;
        }
        if ( (v7 & 1) != 0 )
          LocalFree(*(HLOCAL *)Buffer);
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v19);
    }
    CThreadContext::~CThreadContext((CThreadContext *)&v20);
  }
  return 0;
}

```

## disassembly

```asm
0x180006904  push    rbp
0x180006906  push    rbx
0x180006907  push    rsi
0x180006908  push    rdi
0x180006909  push    r12
0x18000690b  push    r13
0x18000690d  push    r14
0x18000690f  push    r15
0x180006911  lea     rbp, [rsp-17h]
0x180006916  sub     rsp, 0A8h
0x18000691d  mov     rax, cs:__security_cookie
0x180006924  xor     rax, rsp
0x180006927  mov     [rbp+4Fh+var_48], rax
0x18000692b  mov     esi, [rbp+4Fh+dwMessageId]
0x18000692e  xor     r12d, r12d
0x180006931  mov     r15, r9
0x180006934  mov     dword ptr [rbp+4Fh+Buffer], r12d
0x180006938  mov     r14, r8
0x18000693b  mov     edi, r12d
0x18000693e  lea     r13d, [r12+1]
0x180006943  mov     ebx, r13d
0x180006946  lock xadd [rcx], ebx
0x18000694a  add     ebx, r13d
0x18000694d  cmp     ebx, 0Ah
0x180006950  jg      loc_180006AFC
0x180006956  mov     [rbp+4Fh+var_88], r12d
0x18000695a  xorps   xmm0, xmm0
0x18000695d  mov     [rbp+4Fh+var_80], r12
0x180006961  mov     [rbp+4Fh+var_78], r12
0x180006965  mov     [rbp+4Fh+var_70], r12d
0x180006969  movdqu  [rbp+4Fh+var_68], xmm0
0x18000696e  test    rdx, rdx
0x180006971  jz      short loc_180006998
0x180006973  lea     rcx, [rbp+4Fh+var_88]; this
0x180006977  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x18000697c  test    eax, eax
0x18000697e  jns     short loc_180006998
0x180006980  mov     rcx, [rbp+57h]; this
0x180006984  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000698b  mov     r9d, eax; char *
0x18000698e  lea     edx, [r12+57h]; void *
0x180006993  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006998  cmp     ebx, 0Ah
0x18000699b  jge     loc_180006AD2
0x1800069a1  mov     [rbp+4Fh+var_A0], r12
0x1800069a5  mov     [rbp+4Fh+var_98], r12
0x1800069a9  mov     [rbp+4Fh+var_90], r12
0x1800069ad  cmp     esi, 1772h
0x1800069b3  jnz     loc_180006A50
0x1800069b9  xor     r9d, r9d; wLanguage
0x1800069bc  lea     rcx, __ImageBase; hModule
0x1800069c3  lea     edx, [r9+6]; lpType
0x1800069c7  lea     r8d, [r9+7Eh]; lpName
0x1800069cb  call    cs:__imp_FindResourceExW
0x1800069d1  test    rax, rax
0x1800069d4  jz      short loc_180006A50
0x1800069d6  mov     rdx, rax; hResInfo
0x1800069d9  lea     rcx, __ImageBase; hModule
0x1800069e0  call    cs:__imp_LoadResource
0x1800069e6  test    rax, rax
0x1800069e9  jz      short loc_180006A50
0x1800069eb  mov     rcx, rax; hResData
0x1800069ee  call    cs:__imp_LockResource
0x1800069f4  test    rax, rax
0x1800069f7  jz      short loc_180006A50
0x1800069f9  movzx   ecx, word ptr [rax]
0x1800069fc  movzx   r8d, word ptr [rax+rcx*2+2]
0x180006a02  test    r8w, r8w
0x180006a06  jz      short loc_180006A12
0x180006a08  lea     rdx, [rcx+2]
0x180006a0c  lea     rdx, [rax+rdx*2]
0x180006a10  jmp     short loc_180006A19
0x180006a12  lea     rdx, Format
0x180006a19  lea     rcx, [rbp+4Fh+var_A0]
0x180006a1d  call    ?_Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180006a22  test    eax, eax
0x180006a24  js      short loc_180006A50
0x180006a26  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, r13b
0x180006a2d  jz      loc_180006AC7
0x180006a33  mov     rax, [rbp+4Fh+var_A0]
0x180006a37  lea     rdx, EVENT_COPYERROR
0x180006a3e  mov     r9, r15
0x180006a41  mov     [rsp+0E0h+lpBuffer], rax
0x180006a46  mov     r8, r14
0x180006a49  call    McTemplateU0zzz_EventWriteTransfer
0x180006a4e  jmp     short loc_180006AC7
0x180006a50  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, r13b
0x180006a57  jz      short loc_180006AB8
0x180006a59  mov     [rsp+0E0h+Arguments], r12; Arguments
0x180006a5e  lea     rax, [rbp+4Fh+Buffer]
0x180006a62  mov     [rsp+0E0h+nSize], r13d; nSize
0x180006a67  xor     r9d, r9d; dwLanguageId
0x180006a6a  mov     r8d, esi; dwMessageId
0x180006a6d  mov     [rsp+0E0h+lpBuffer], rax; lpBuffer
0x180006a72  xor     edx, edx; lpSource
0x180006a74  mov     ecx, 1100h; dwFlags
0x180006a79  call    cs:__imp_FormatMessageW
0x180006a7f  test    eax, eax
0x180006a81  jnz     short loc_180006A8C
0x180006a83  mov     rax, r12
0x180006a86  mov     qword ptr [rbp+4Fh+Buffer], rax
0x180006a8a  jmp     short loc_180006A90
0x180006a8c  mov     rax, qword ptr [rbp+4Fh+Buffer]
0x180006a90  test    rax, rax
0x180006a93  lea     rcx, asc_18001FC18; "???"
0x180006a9a  mov     r9, r15
0x180006a9d  lea     rdx, EVENT_COPYERROR
0x180006aa4  cmovnz  rcx, rax
0x180006aa8  mov     r8, r14
0x180006aab  mov     [rsp+0E0h+lpBuffer], rcx
0x180006ab0  call    McTemplateU0zzz_EventWriteTransfer
0x180006ab5  mov     edi, r13d
0x180006ab8  test    r13b, dil
0x180006abb  jz      short loc_180006AC7
0x180006abd  mov     rcx, qword ptr [rbp+4Fh+Buffer]; hMem
0x180006ac1  call    cs:__imp_LocalFree
0x180006ac7  lea     rcx, [rbp+4Fh+var_A0]
0x180006acb  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180006ad0  jmp     short loc_180006AF3
0x180006ad2  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, r13b
0x180006ad9  jz      short loc_180006AF3
0x180006adb  lea     rax, [rbp+4Fh+Buffer]
0x180006adf  mov     r9d, r13d
0x180006ae2  lea     rdx, EVENT_TOO_MANY_COPY_ERRORS
0x180006ae9  mov     [rsp+0E0h+lpBuffer], rax
0x180006aee  call    McGenEventWrite_EventWriteTransfer
0x180006af3  lea     rcx, [rbp+4Fh+var_88]; this
0x180006af7  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180006afc  xor     eax, eax
0x180006afe  mov     rcx, [rbp+4Fh+var_48]
0x180006b02  xor     rcx, rsp; StackCookie
0x180006b05  call    __security_check_cookie
0x180006b0a  add     rsp, 0A8h
0x180006b11  pop     r15
0x180006b13  pop     r14
0x180006b15  pop     r13
0x180006b17  pop     r12
0x180006b19  pop     rdi
0x180006b1a  pop     rsi
0x180006b1b  pop     rbx
0x180006b1c  pop     rbp
0x180006b1d  retn
```
