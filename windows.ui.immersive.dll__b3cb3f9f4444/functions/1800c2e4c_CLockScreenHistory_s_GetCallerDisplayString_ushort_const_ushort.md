# CLockScreenHistory::s_GetCallerDisplayString(ushort const *,ushort * *)

- ea: `0x1800c2e4c`
- end: `0x1800c309d`
- name: `?s_GetCallerDisplayString@CLockScreenHistory@@SAJPEBGPEAPEAG@Z`
- size: `593`
- prototype: `__int64 __fastcall(LPCWCH lpString1, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b7ac0`

## callees

- `0x1800343ec`
- `0x180050fc0`
- `0x1800c2e4c`
- `0x1800e19f8`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c2e7f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c2ea7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c2ecf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c2efa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c2f57`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c2fc7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c2e7f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c2ea7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c2ecf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c2efa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c2f57`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c2fc7`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800c2f96`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800c2f96`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800c2ffb`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800c2ffb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3052`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLockScreenHistory::s_GetCallerDisplayString(LPCWCH lpString1, unsigned __int16 **a2)
{
  int v4; // edi
  __int64 v5; // rbx
  int v6; // r8d
  int v7; // edx
  LPCWCH v8; // rbx
  HRESULT v9; // eax
  void *bIgnoreCase; // [rsp+20h] [rbp-28h]
  void *ppv; // [rsp+58h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  v4 = 0;
  v5 = -1;
  if ( CompareStringOrdinal(lpString1, -1, L"IMMERSIVE_CPL", -1, 0) != 2
    && CompareStringOrdinal(lpString1, -1, L"CREATIVE", -1, 0) != 2 )
  {
    if ( CompareStringOrdinal(lpString1, -1, L"ROAMING", -1, 0) == 2 )
    {
      v7 = 38915;
      return (unsigned int)TResourceStringAllocCopyEx<unsigned short *>(
                             (int)&_ImageBase,
                             v7,
                             v6,
                             (int)&ResourceStringAllocCopyExCoAlloc,
                             bIgnoreCase,
                             a2);
    }
    if ( CompareStringOrdinal(lpString1, -1, L"POLICY", -1, 0) == 2 )
    {
      v7 = 38928;
      return (unsigned int)TResourceStringAllocCopyEx<unsigned short *>(
                             (int)&_ImageBase,
                             v7,
                             v6,
                             (int)&ResourceStringAllocCopyExCoAlloc,
                             bIgnoreCase,
                             a2);
    }
    do
      ++v5;
    while ( lpString1[v5] );
    ppv = 0;
    if ( (int)v5 > 6 && CompareStringOrdinal(lpString1, 6, L"APPID:", 6, 0) == 2 )
    {
      v8 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      v9 = SHCreateItemInKnownFolder(
             &FOLDERID_AppsFolder,
             0x4000u,
             lpString1 + 6,
             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
             &ppv);
    }
    else
    {
      v4 = -2147467259;
      if ( (int)v5 <= 10 || CompareStringOrdinal(lpString1, 10, L"IMAGENAME:", 10, 0) != 2 )
      {
LABEL_20:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        return (unsigned int)v4;
      }
      v8 = lpString1 + 10;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      v9 = SHCreateItemFromParsingName(lpString1 + 10, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    }
    v4 = v9;
    if ( v9 < 0
      || (pv = 0, v4 = (*(__int64 (__fastcall **)(void *, _QWORD, LPVOID *))(*(_QWORD *)ppv + 40LL))(ppv, 0, &pv),
                  v4 < 0)
      || (v4 = ResourceStringCoAllocFormatMessage(&_ImageBase, 38916, a2, pv), CoTaskMemFree(pv), v4 < 0) )
    {
      if ( v8 )
        v4 = ResourceStringCoAllocFormatMessage(&_ImageBase, 38916, a2, v8);
    }
    goto LABEL_20;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800c2e4c  mov     [rsp+arg_0], rbx
0x1800c2e51  mov     [rsp+arg_18], rbp
0x1800c2e56  push    rsi
0x1800c2e57  push    rdi
0x1800c2e58  push    r14
0x1800c2e5a  sub     rsp, 30h
0x1800c2e5e  mov     r14, rdx
0x1800c2e61  mov     rsi, rcx
0x1800c2e64  xor     ebp, ebp
0x1800c2e66  mov     [rdx], rbp
0x1800c2e69  mov     edi, ebp
0x1800c2e6b  mov     [rsp+48h+bIgnoreCase], ebp; bIgnoreCase
0x1800c2e6f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800c2e73  mov     r9d, ebx; cchCount2
0x1800c2e76  lea     r8, aImmersiveCpl; "IMMERSIVE_CPL"
0x1800c2e7d  mov     edx, ebx; cchCount1
0x1800c2e7f  call    cs:__imp_CompareStringOrdinal
0x1800c2e86  nop     dword ptr [rax+rax+00h]
0x1800c2e8b  cmp     eax, 2
0x1800c2e8e  jz      loc_1800C3087
0x1800c2e94  mov     [rsp+48h+bIgnoreCase], ebp; bIgnoreCase
0x1800c2e98  mov     r9d, ebx; cchCount2
0x1800c2e9b  lea     r8, aCreative; "CREATIVE"
0x1800c2ea2  mov     edx, ebx; cchCount1
0x1800c2ea4  mov     rcx, rsi; lpString1
0x1800c2ea7  call    cs:__imp_CompareStringOrdinal
0x1800c2eae  nop     dword ptr [rax+rax+00h]
0x1800c2eb3  cmp     eax, 2
0x1800c2eb6  jz      loc_1800C3087
0x1800c2ebc  mov     [rsp+48h+bIgnoreCase], ebp; bIgnoreCase
0x1800c2ec0  mov     r9d, ebx; cchCount2
0x1800c2ec3  lea     r8, aRoaming; "ROAMING"
0x1800c2eca  mov     edx, ebx; cchCount1
0x1800c2ecc  mov     rcx, rsi; lpString1
0x1800c2ecf  call    cs:__imp_CompareStringOrdinal
0x1800c2ed6  nop     dword ptr [rax+rax+00h]
0x1800c2edb  cmp     eax, 2
0x1800c2ede  jnz     short loc_1800C2EE7
0x1800c2ee0  mov     edx, 9803h
0x1800c2ee5  jmp     short loc_1800C2F10
0x1800c2ee7  mov     [rsp+48h+bIgnoreCase], ebp; Src
0x1800c2eeb  mov     r9d, ebx; cchCount2
0x1800c2eee  lea     r8, aPolicy; "POLICY"
0x1800c2ef5  mov     edx, ebx; cchCount1
0x1800c2ef7  mov     rcx, rsi; lpString1
0x1800c2efa  call    cs:__imp_CompareStringOrdinal
0x1800c2f01  nop     dword ptr [rax+rax+00h]
0x1800c2f06  cmp     eax, 2
0x1800c2f09  jnz     short loc_1800C2F2F
0x1800c2f0b  mov     edx, 9810h; int
0x1800c2f10  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x1800c2f17  mov     [rsp+48h+var_20], r14; void *
0x1800c2f1c  lea     rcx, __ImageBase; int
0x1800c2f23  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800c2f28  mov     edi, eax
0x1800c2f2a  jmp     loc_1800C3087
0x1800c2f2f  inc     rbx
0x1800c2f32  cmp     [rsi+rbx*2], bp
0x1800c2f36  jnz     short loc_1800C2F2F
0x1800c2f38  mov     [rsp+48h+ppv], rbp
0x1800c2f3d  mov     edx, 6; cchCount1
0x1800c2f42  cmp     ebx, edx
0x1800c2f44  jle     short loc_1800C2FA4
0x1800c2f46  mov     [rsp+48h+bIgnoreCase], ebp; bIgnoreCase
0x1800c2f4a  mov     r9d, edx; cchCount2
0x1800c2f4d  lea     r8, aAppid; "APPID:"
0x1800c2f54  mov     rcx, rsi; lpString1
0x1800c2f57  call    cs:__imp_CompareStringOrdinal
0x1800c2f5e  nop     dword ptr [rax+rax+00h]
0x1800c2f63  cmp     eax, 2
0x1800c2f66  jnz     short loc_1800C2FA4
0x1800c2f68  mov     rbx, rbp
0x1800c2f6b  lea     rcx, [rsp+48h+ppv]
0x1800c2f70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c2f75  lea     r8, [rsi+0Ch]; pszItem
0x1800c2f79  lea     rax, [rsp+48h+ppv]
0x1800c2f7e  mov     qword ptr [rsp+48h+bIgnoreCase], rax; ppv
0x1800c2f83  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800c2f8a  mov     edx, 4000h; dwKFFlags
0x1800c2f8f  lea     rcx, FOLDERID_AppsFolder; kfid
0x1800c2f96  call    cs:__imp_SHCreateItemInKnownFolder
0x1800c2f9d  nop     dword ptr [rax+rax+00h]
0x1800c2fa2  jmp     short loc_1800C3007
0x1800c2fa4  mov     edi, 80004005h
0x1800c2fa9  mov     edx, 0Ah; cchCount1
0x1800c2fae  cmp     ebx, edx
0x1800c2fb0  jle     loc_1800C307D
0x1800c2fb6  mov     [rsp+48h+bIgnoreCase], ebp; bIgnoreCase
0x1800c2fba  mov     r9d, edx; cchCount2
0x1800c2fbd  lea     r8, aImagename; "IMAGENAME:"
0x1800c2fc4  mov     rcx, rsi; lpString1
0x1800c2fc7  call    cs:__imp_CompareStringOrdinal
0x1800c2fce  nop     dword ptr [rax+rax+00h]
0x1800c2fd3  cmp     eax, 2
0x1800c2fd6  jnz     loc_1800C307D
0x1800c2fdc  lea     rbx, [rsi+14h]
0x1800c2fe0  lea     rcx, [rsp+48h+ppv]
0x1800c2fe5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c2fea  lea     r9, [rsp+48h+ppv]; ppv
0x1800c2fef  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800c2ff6  xor     edx, edx; pbc
0x1800c2ff8  mov     rcx, rbx; pszPath
0x1800c2ffb  call    cs:__imp_SHCreateItemFromParsingName
0x1800c3002  nop     dword ptr [rax+rax+00h]
0x1800c3007  mov     edi, eax
0x1800c3009  mov     esi, 9804h
0x1800c300e  test    eax, eax
0x1800c3010  js      short loc_1800C3062
0x1800c3012  mov     [rsp+48h+pv], rbp
0x1800c3017  mov     rcx, [rsp+48h+ppv]
0x1800c301c  mov     rax, [rcx]
0x1800c301f  lea     r8, [rsp+48h+pv]
0x1800c3024  xor     edx, edx
0x1800c3026  mov     rax, [rax+28h]
0x1800c302a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c302f  mov     edi, eax
0x1800c3031  test    eax, eax
0x1800c3033  js      short loc_1800C3062
0x1800c3035  mov     r9, [rsp+48h+pv]
0x1800c303a  mov     r8, r14
0x1800c303d  mov     edx, esi
0x1800c303f  lea     rcx, __ImageBase
0x1800c3046  call    ResourceStringCoAllocFormatMessage
0x1800c304b  mov     edi, eax
0x1800c304d  mov     rcx, [rsp+48h+pv]; pv
0x1800c3052  call    cs:__imp_CoTaskMemFree
0x1800c3059  nop     dword ptr [rax+rax+00h]
0x1800c305e  test    edi, edi
0x1800c3060  jns     short loc_1800C307D
0x1800c3062  test    rbx, rbx
0x1800c3065  jz      short loc_1800C307D
0x1800c3067  mov     r9, rbx
0x1800c306a  mov     r8, r14
0x1800c306d  mov     edx, esi
0x1800c306f  lea     rcx, __ImageBase
0x1800c3076  call    ResourceStringCoAllocFormatMessage
0x1800c307b  mov     edi, eax
0x1800c307d  lea     rcx, [rsp+48h+ppv]
0x1800c3082  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c3087  mov     eax, edi
0x1800c3089  mov     rbx, [rsp+48h+arg_0]
0x1800c308e  mov     rbp, [rsp+48h+arg_18]
0x1800c3093  add     rsp, 30h
0x1800c3097  pop     r14
0x1800c3099  pop     rdi
0x1800c309a  pop     rsi
0x1800c309b  retn
```
