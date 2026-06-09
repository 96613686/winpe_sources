# Windows::System::Internal::_QueryActiveDirectory(ushort const *,ulong,ushort const * *,ushort const *,bool,bool,bool *,Windows::Internal::String &)

- ea: `0x1800d3c60`
- end: `0x1800d3eed`
- name: `?_QueryActiveDirectory@Internal@System@Windows@@YAJPEBGKPEAPEBG0_N2PEA_NAEAVString@13@@Z`
- size: `653`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpszPathName@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, const unsigned __int16 **@<r9>, const unsigned __int16 *, bool, bool, bool *, struct Windows::Internal::String *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d34a0`
- `0x1800d3538`

## callees

- `0x1800088e8`
- `0x18000ce48`
- `0x1800d2154`
- `0x1800d2ad0`
- `0x1800d303c`
- `0x1800d3a1c`
- `0x1800d3c60`
- `0x1800ec010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800d3e0f`
- `msvcrt!wcschr` at `0x1800d3e0f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d3c8d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d3c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3c9c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d3dd8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d3dd8`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsGetObject` at `0x1800d3cf5`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsGetObject` at `0x1800d3cf5`

## string_xrefs

- `0x1800d3cc0`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`
- `0x1800d3c86`: `activeds.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::System::Internal::_QueryActiveDirectory(
        LPCWSTR lpszPathName,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 **a4,
        const unsigned __int16 *a5,
        bool a6,
        void *ppObject,
        Windows::Internal::String *a8)
{
  signed int LastError; // eax
  int Object; // ebx
  char v13; // r15
  int v14; // eax
  __int64 v15; // r14
  __int64 v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // r8
  const wchar_t *v19; // rsi
  wchar_t *v20; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-60h]
  __int64 v23; // [rsp+30h] [rbp-50h] BYREF
  HMODULE Library; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 *v25[3]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v26; // [rsp+58h] [rbp-28h] BYREF
  __int128 v27; // [rsp+68h] [rbp-18h]
  __int64 v28; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  Library = LoadLibraryExW(L"activeds.dll", 0, 0x800u);
  if ( Library )
  {
    ppObject = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppObject);
    Object = ADsGetObject(lpszPathName, &GUID_109ba8ec_92f0_11d0_a790_00c04fd8d5a8, &ppObject);
    if ( Object >= 0 )
    {
      v23 = 0;
      Object = (*(__int64 (__fastcall **)(void *, const unsigned __int16 **, __int64, __int64, __int64 *))(*(_QWORD *)ppObject + 32LL))(
                 ppObject,
                 a4,
                 a3,
                 2,
                 &v23);
      if ( Object >= 0 )
      {
        v13 = 0;
        v14 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppObject + 48LL))(ppObject, v23);
LABEL_27:
        Object = v14;
        if ( v14 )
        {
          if ( v14 == 20498 )
            Object = 0;
        }
        else
        {
          v15 = 0;
          while ( 1 )
          {
            v26 = 0;
            v27 = 0;
            v28 = 0;
            Object = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, __int128 *))(*(_QWORD *)ppObject + 80LL))(
                       ppObject,
                       v23,
                       *(_QWORD *)(a3 + 8 * v15),
                       &v26);
            if ( Object >= 0 )
            {
              v16 = 0;
              v17 = v27;
              v18 = DWORD2(v26);
              while ( (unsigned int)v16 < DWORD2(v27) )
              {
                if ( (_DWORD)v18 == 1 || (unsigned int)(v18 - 2) <= 1 )
                {
                  v19 = *(const wchar_t **)(v17 + 24 * v16 + 8);
                  if ( v19 )
                  {
                    if ( CompareStringOrdinal(L"sip:", 4, v19, 4, 1) == 2 )
                    {
                      memset(v25, 0, sizeof(v25));
                      v20 = wcschr(v19, 0x3Au);
                      Object = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::InitializeFormat(
                                 v25,
                                 L"%s//%s",
                                 L"sip:",
                                 v20 + 1);
                      if ( Object >= 0 )
                      {
                        if ( v25[0] )
                          Object = Windows::Internal::String::_InitializeHelper(a8, v25[0]);
                        else
                          Object = -2147467261;
                      }
                      v13 = 1;
                      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(v25);
                      break;
                    }
                    v17 = v27;
                    v18 = DWORD2(v26);
                  }
                }
                v16 = (unsigned int)(v16 + 1);
              }
              (*(void (__fastcall **)(void *, __int128 *, __int64))(*(_QWORD *)ppObject + 88LL))(ppObject, &v26, v18);
              if ( v13 )
                break;
            }
            v15 = (unsigned int)(v15 + 1);
            if ( (unsigned int)v15 >= 2 )
            {
              v14 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppObject + 56LL))(ppObject, v23);
              goto LABEL_27;
            }
          }
        }
      }
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)ppObject + 96LL))(ppObject, v23);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppObject);
  }
  else
  {
    LastError = GetLastError();
    Object = LastError;
    if ( LastError > 0 )
      Object = (unsigned __int16)LastError | 0x80070000;
    if ( Object < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x204,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
        (const char *)(unsigned int)Object,
        bIgnoreCase);
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&Library);
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x1800d3c60  push    rbp
0x1800d3c62  push    rbx
0x1800d3c63  push    rsi
0x1800d3c64  push    rdi
0x1800d3c65  push    r12
0x1800d3c67  push    r14
0x1800d3c69  push    r15
0x1800d3c6b  mov     rbp, rsp
0x1800d3c6e  sub     rsp, 80h
0x1800d3c75  mov     rdi, r9
0x1800d3c78  mov     r12, r8
0x1800d3c7b  mov     rbx, rcx
0x1800d3c7e  xor     edx, edx; hFile
0x1800d3c80  mov     r8d, 800h; dwFlags
0x1800d3c86  lea     rcx, aActivedsDll; "activeds.dll"
0x1800d3c8d  call    cs:__imp_LoadLibraryExW
0x1800d3c93  mov     [rbp+var_48], rax
0x1800d3c97  test    rax, rax
0x1800d3c9a  jnz     short loc_1800D3CD6
0x1800d3c9c  call    cs:__imp_GetLastError
0x1800d3ca2  mov     ebx, eax
0x1800d3ca4  test    eax, eax
0x1800d3ca6  jle     short loc_1800D3CB1
0x1800d3ca8  movzx   ebx, ax
0x1800d3cab  or      ebx, 80070000h
0x1800d3cb1  test    ebx, ebx
0x1800d3cb3  jns     loc_1800D3ED0
0x1800d3cb9  mov     rcx, [rbp+38h]; this
0x1800d3cbd  mov     r9d, ebx; char *
0x1800d3cc0  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x1800d3cc7  mov     edx, 204h; void *
0x1800d3ccc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3cd1  jmp     loc_1800D3ED0
0x1800d3cd6  mov     [rbp+ppObject], 0
0x1800d3cde  lea     rcx, [rbp+ppObject]
0x1800d3ce2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d3ce7  lea     r8, [rbp+ppObject]; ppObject
0x1800d3ceb  lea     rdx, _GUID_109ba8ec_92f0_11d0_a790_00c04fd8d5a8; riid
0x1800d3cf2  mov     rcx, rbx; lpszPathName
0x1800d3cf5  call    cs:__imp_ADsGetObject
0x1800d3cfb  mov     ebx, eax
0x1800d3cfd  test    eax, eax
0x1800d3cff  js      loc_1800D3EC6
0x1800d3d05  mov     [rbp+var_50], 0
0x1800d3d0d  mov     rcx, [rbp+ppObject]
0x1800d3d11  mov     rax, [rcx]
0x1800d3d14  lea     rdx, [rbp+var_50]
0x1800d3d18  mov     qword ptr [rsp+80h+bIgnoreCase], rdx
0x1800d3d1d  mov     r9d, 2
0x1800d3d23  mov     r8, r12
0x1800d3d26  mov     rdx, rdi
0x1800d3d29  mov     rax, [rax+20h]
0x1800d3d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3d32  mov     ebx, eax
0x1800d3d34  test    eax, eax
0x1800d3d36  js      loc_1800D3EB1
0x1800d3d3c  xor     r15b, r15b
0x1800d3d3f  mov     rcx, [rbp+ppObject]
0x1800d3d43  mov     rax, [rcx]
0x1800d3d46  mov     rax, [rax+30h]
0x1800d3d4a  jmp     loc_1800D3E93
0x1800d3d4f  xor     r14d, r14d
0x1800d3d52  xorps   xmm0, xmm0
0x1800d3d55  xor     eax, eax
0x1800d3d57  movups  [rbp+var_28], xmm0
0x1800d3d5b  movups  [rbp+var_18], xmm0
0x1800d3d5f  mov     [rbp+var_8], rax
0x1800d3d63  mov     rcx, [rbp+ppObject]
0x1800d3d67  mov     rax, [rcx]
0x1800d3d6a  lea     r9, [rbp+var_28]
0x1800d3d6e  mov     r8, [r12+r14*8]
0x1800d3d72  mov     rdx, [rbp+var_50]
0x1800d3d76  mov     rax, [rax+50h]
0x1800d3d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3d7f  mov     ebx, eax
0x1800d3d81  test    eax, eax
0x1800d3d83  js      loc_1800D3E76
0x1800d3d89  xor     edi, edi
0x1800d3d8b  mov     rdx, qword ptr [rbp+var_18]
0x1800d3d8f  mov     r8d, dword ptr [rbp+var_28+8]
0x1800d3d93  cmp     edi, dword ptr [rbp+var_18+8]
0x1800d3d96  jnb     loc_1800D3E5D
0x1800d3d9c  mov     ecx, r8d
0x1800d3d9f  sub     ecx, 1
0x1800d3da2  jz      short loc_1800D3DAE
0x1800d3da4  sub     ecx, 1
0x1800d3da7  jz      short loc_1800D3DAE
0x1800d3da9  cmp     ecx, 1
0x1800d3dac  jnz     short loc_1800D3DEB
0x1800d3dae  lea     rcx, [rdi+rdi*2]
0x1800d3db2  mov     rsi, [rdx+rcx*8+8]
0x1800d3db7  test    rsi, rsi
0x1800d3dba  jz      short loc_1800D3DEB
0x1800d3dbc  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x1800d3dc4  mov     eax, 4
0x1800d3dc9  mov     r9d, eax; cchCount2
0x1800d3dcc  mov     r8, rsi; lpString2
0x1800d3dcf  mov     edx, eax; cchCount1
0x1800d3dd1  lea     rcx, aSip; "sip:"
0x1800d3dd8  call    cs:__imp_CompareStringOrdinal
0x1800d3dde  cmp     eax, 2
0x1800d3de1  jz      short loc_1800D3DEF
0x1800d3de3  mov     rdx, qword ptr [rbp+var_18]
0x1800d3de7  mov     r8d, dword ptr [rbp+var_28+8]
0x1800d3deb  inc     edi
0x1800d3ded  jmp     short loc_1800D3D93
0x1800d3def  mov     [rbp+var_40], 0
0x1800d3df7  mov     [rbp+var_38], 0
0x1800d3dff  mov     [rbp+var_30], 0
0x1800d3e07  mov     edx, 3Ah ; ':'; Ch
0x1800d3e0c  mov     rcx, rsi; Str
0x1800d3e0f  call    cs:__imp_wcschr
0x1800d3e15  lea     r9, [rax+2]
0x1800d3e19  lea     r8, aSip; "sip:"
0x1800d3e20  lea     rdx, aSS_0; "%s//%s"
0x1800d3e27  lea     rcx, [rbp+var_40]
0x1800d3e2b  call    ?InitializeFormat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800d3e30  mov     ebx, eax
0x1800d3e32  test    eax, eax
0x1800d3e34  js      short loc_1800D3E51
0x1800d3e36  mov     rdx, [rbp+var_40]; unsigned __int16 *
0x1800d3e3a  test    rdx, rdx
0x1800d3e3d  jz      short loc_1800D3E4C
0x1800d3e3f  mov     rcx, [rbp+arg_38]; this
0x1800d3e43  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x1800d3e48  mov     ebx, eax
0x1800d3e4a  jmp     short loc_1800D3E51
0x1800d3e4c  mov     ebx, 80004003h
0x1800d3e51  mov     r15b, 1
0x1800d3e54  lea     rcx, [rbp+var_40]
0x1800d3e58  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1800d3e5d  mov     rcx, [rbp+ppObject]
0x1800d3e61  mov     rax, [rcx]
0x1800d3e64  lea     rdx, [rbp+var_28]
0x1800d3e68  mov     rax, [rax+58h]
0x1800d3e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3e71  test    r15b, r15b
0x1800d3e74  jnz     short loc_1800D3EB1
0x1800d3e76  inc     r14d
0x1800d3e79  cmp     r14d, 2
0x1800d3e7d  jb      loc_1800D3D52
0x1800d3e83  test    r15b, r15b
0x1800d3e86  jnz     short loc_1800D3EB1
0x1800d3e88  mov     rcx, [rbp+ppObject]
0x1800d3e8c  mov     rax, [rcx]
0x1800d3e8f  mov     rax, [rax+38h]
0x1800d3e93  mov     rdx, [rbp+var_50]
0x1800d3e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3e9c  test    eax, eax
0x1800d3e9e  mov     ebx, eax
0x1800d3ea0  jz      loc_1800D3D4F
0x1800d3ea6  xor     eax, eax
0x1800d3ea8  cmp     ebx, 5012h
0x1800d3eae  cmovz   ebx, eax
0x1800d3eb1  mov     rcx, [rbp+ppObject]
0x1800d3eb5  mov     rax, [rcx]
0x1800d3eb8  mov     rdx, [rbp+var_50]
0x1800d3ebc  mov     rax, [rax+60h]
0x1800d3ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3ec5  nop
0x1800d3ec6  lea     rcx, [rbp+ppObject]
0x1800d3eca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d3ecf  nop
0x1800d3ed0  lea     rcx, [rbp+var_48]
0x1800d3ed4  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800d3ed9  mov     eax, ebx
0x1800d3edb  add     rsp, 80h
0x1800d3ee2  pop     r15
0x1800d3ee4  pop     r14
0x1800d3ee6  pop     r12
0x1800d3ee8  pop     rdi
0x1800d3ee9  pop     rsi
0x1800d3eea  pop     rbx
0x1800d3eeb  pop     rbp
0x1800d3eec  retn
```
