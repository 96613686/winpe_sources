# CSrmResource::LoadStringW(uint)

- ea: `0x180017e90`
- end: `0x180018098`
- name: `?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z`
- size: `520`
- prototype: `_QWORD *__fastcall(_QWORD *Src, UINT uID)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180016a98`
- `0x180016dd0`
- `0x180017158`

## callees

- `0x180001e44`
- `0x1800106fc`
- `0x1800161e8`
- `0x180017e90`
- `0x180018cbc`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001801d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001801d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017eeb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017eeb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017f2a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017f2a`

## string_xrefs

- `0x180017fe8`: `Error loading SRM.DLL resource with ID = 0x%08lx [0x%08lx]`
- `0x180018063`: `Error loading SRM.DLL [0x%08lx]`
- `0x180017ee4`: `srm.dll`

## pseudocode

```c
_QWORD *__fastcall CSrmResource::LoadStringW(_QWORD *Src, UINT uID)
{
  HMODULE Library; // rsi
  unsigned __int64 v5; // r8
  DWORD v7; // ebx
  __int64 v8; // rax
  DWORD LastError; // ebx
  __int64 v10; // rax
  __int64 v11; // [rsp+20h] [rbp-E0h]
  __int64 v12; // [rsp+20h] [rbp-E0h]
  __int64 v13; // [rsp+28h] [rbp-D8h]
  _QWORD pExceptionObject[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v15[152]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v17[2046]; // [rsp+F2h] [rbp-Eh] BYREF

  pExceptionObject[1] = Src;
  Library = `CSrmResource::GetResourceModule'::`2'::hMod;
  if ( !`CSrmResource::GetResourceModule'::`2'::hMod )
  {
    Library = LoadLibraryExW(L"srm.dll", 0, 2u);
    `CSrmResource::GetResourceModule'::`2'::hMod = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      pExceptionObject[0] = v15;
      v10 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v15,
              (__int64)L"base\\fs\\fsrm\\utilities\\inc\\resload.h",
              (__int64)L"HRESLOAD",
              (__int64)L"CSrmResource::GetResourceModule",
              364,
              17);
      LODWORD(v12) = LastError;
      CSrmFunctionTracerBase::StaticTrace(v10, 40, L"SrmLoadString", L"Error loading SRM.DLL [0x%08lx]", v12);
      LODWORD(pExceptionObject[0]) = -2147418113;
      throw (long *)pExceptionObject;
    }
  }
  Buffer = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( !LoadStringW(Library, uID, &Buffer, 1024) )
  {
    v7 = GetLastError();
    pExceptionObject[0] = v15;
    v8 = CSrmDebugInfo::CSrmDebugInfo(
           (__int64)v15,
           (__int64)L"base\\fs\\fsrm\\utilities\\inc\\resload.h",
           (__int64)L"HRESLOAD",
           (__int64)L"CSrmResource::LoadStringW",
           79,
           17);
    LODWORD(v13) = v7;
    LODWORD(v11) = uID;
    CSrmFunctionTracerBase::StaticTrace(
      v8,
      40,
      L"SrmLoadString",
      L"Error loading SRM.DLL resource with ID = 0x%08lx [0x%08lx]",
      v11,
      v13);
    LODWORD(pExceptionObject[0]) = -2147418113;
    throw (long *)pExceptionObject;
  }
  Src[3] = 7;
  Src[2] = 0;
  *(_WORD *)Src = 0;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)&v17[2 * v5 - 2] );
  std::wstring::assign(Src, (char *)&Buffer, v5);
  return Src;
}

```

## disassembly

```asm
0x180017e90  mov     [rsp-8+arg_10], rbx
0x180017e95  push    rbp
0x180017e96  push    rsi
0x180017e97  push    rdi
0x180017e98  push    r14
0x180017e9a  push    r15
0x180017e9c  lea     rbp, [rsp-800h]
0x180017ea4  sub     rsp, 900h
0x180017eab  mov     rax, cs:__security_cookie
0x180017eb2  xor     rax, rsp
0x180017eb5  mov     [rbp+820h+var_30], rax
0x180017ebc  mov     r14d, edx
0x180017ebf  mov     rdi, rcx
0x180017ec2  mov     [rsp+920h+var_8D0], rcx
0x180017ec7  xor     r15d, r15d
0x180017eca  mov     [rsp+920h+var_8E0], r15d
0x180017ecf  lea     ebx, [r15+2]
0x180017ed3  mov     rsi, cs:?hMod@?1??GetResourceModule@CSrmResource@@CAPEAUHINSTANCE__@@XZ@4PEAU3@EA; HINSTANCE__ * `CSrmResource::GetResourceModule(void)'::`2'::hMod
0x180017eda  test    rsi, rsi
0x180017edd  jnz     short loc_180017F04
0x180017edf  mov     r8d, ebx; dwFlags
0x180017ee2  xor     edx, edx; hFile
0x180017ee4  lea     rcx, aSrmDll_0; "srm.dll"
0x180017eeb  call    cs:__imp_LoadLibraryExW
0x180017ef1  mov     rsi, rax
0x180017ef4  mov     cs:?hMod@?1??GetResourceModule@CSrmResource@@CAPEAUHINSTANCE__@@XZ@4PEAU3@EA, rax; HINSTANCE__ * `CSrmResource::GetResourceModule(void)'::`2'::hMod
0x180017efb  test    rax, rax
0x180017efe  jz      loc_18001801D
0x180017f04  mov     [rbp+820h+Buffer], r15w
0x180017f09  xor     edx, edx; Val
0x180017f0b  mov     r8d, 7FEh; Size
0x180017f11  lea     rcx, [rbp+820h+var_82E]; void *
0x180017f15  call    memset_0
0x180017f1a  mov     r9d, 400h; cchBufferMax
0x180017f20  lea     r8, [rbp+820h+Buffer]; lpBuffer
0x180017f24  mov     edx, r14d; uID
0x180017f27  mov     rcx, rsi; hInstance
0x180017f2a  call    cs:__imp_LoadStringW
0x180017f30  test    eax, eax
0x180017f32  jz      short loc_180017F9D
0x180017f34  mov     qword ptr [rdi+18h], 7
0x180017f3c  mov     [rdi+10h], r15
0x180017f40  mov     [rdi], r15w
0x180017f44  lea     rax, [rbp+820h+Buffer]
0x180017f48  or      r8, 0FFFFFFFFFFFFFFFFh
0x180017f4c  inc     r8
0x180017f4f  cmp     [rax+r8*2], r15w
0x180017f54  jnz     short loc_180017F4C
0x180017f56  lea     rdx, [rbp+820h+Buffer]; void *
0x180017f5a  mov     rcx, rdi; Src
0x180017f5d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180017f62  mov     [rsp+920h+var_8E0], ebx
0x180017f66  and     ebx, 0FFFFFFFDh
0x180017f69  mov     [rsp+920h+var_8E0], ebx
0x180017f6d  or      ebx, 1
0x180017f70  mov     [rsp+920h+var_8E0], ebx
0x180017f74  mov     rax, rdi
0x180017f77  mov     rcx, [rbp+820h+var_30]
0x180017f7e  xor     rcx, rsp; StackCookie
0x180017f81  call    __security_check_cookie
0x180017f86  mov     rbx, [rsp+920h+arg_10]
0x180017f8e  add     rsp, 900h
0x180017f95  pop     r15
0x180017f97  pop     r14
0x180017f99  pop     rdi
0x180017f9a  pop     rsi
0x180017f9b  pop     rbp
0x180017f9c  retn
0x180017f9d  call    cs:__imp_GetLastError
0x180017fa3  mov     ebx, eax
0x180017fa5  lea     rax, [rsp+920h+var_8C8]
0x180017faa  mov     [rsp+920h+pExceptionObject], rax
0x180017faf  mov     dword ptr [rsp+920h+var_8F8], 11h
0x180017fb7  mov     dword ptr [rsp+920h+var_900], 4Fh ; 'O'
0x180017fbf  lea     r9, aCsrmresourceLo; "CSrmResource::LoadStringW"
0x180017fc6  lea     r8, aHresload; "HRESLOAD"
0x180017fcd  lea     rdx, aBaseFsFsrmUtil_4; "base\\fs\\fsrm\\utilities\\inc\\resload"...
0x180017fd4  lea     rcx, [rsp+920h+var_8C8]
0x180017fd9  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180017fde  nop
0x180017fdf  mov     dword ptr [rsp+920h+var_8F8], ebx
0x180017fe3  mov     dword ptr [rsp+920h+var_900], r14d
0x180017fe8  lea     r9, aErrorLoadingSr; "Error loading SRM.DLL resource with ID "...
0x180017fef  lea     r8, aSrmloadstring; "SrmLoadString"
0x180017ff6  mov     edx, 28h ; '('
0x180017ffb  mov     rcx, rax
0x180017ffe  call    ?StaticTrace@CSrmFunctionTracerBase@@SAXUCSrmDebugInfo@@KPEBG1ZZ; CSrmFunctionTracerBase::StaticTrace(CSrmDebugInfo,ulong,ushort const *,ushort const *,...)
0x180018003  mov     dword ptr [rsp+920h+pExceptionObject], 8000FFFFh
0x18001800b  lea     rdx, _TI1J; pThrowInfo
0x180018012  lea     rcx, [rsp+920h+pExceptionObject]; pExceptionObject
0x180018017  call    _CxxThrowException_0
0x18001801d  call    cs:__imp_GetLastError
0x180018023  mov     ebx, eax
0x180018025  lea     rax, [rsp+920h+var_8C8]
0x18001802a  mov     [rsp+920h+pExceptionObject], rax
0x18001802f  mov     dword ptr [rsp+920h+var_8F8], 11h
0x180018037  mov     dword ptr [rsp+920h+var_900], 16Ch
0x18001803f  lea     r9, aCsrmresourceGe; "CSrmResource::GetResourceModule"
0x180018046  lea     r8, aHresload; "HRESLOAD"
0x18001804d  lea     rdx, aBaseFsFsrmUtil_4; "base\\fs\\fsrm\\utilities\\inc\\resload"...
0x180018054  lea     rcx, [rsp+920h+var_8C8]
0x180018059  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001805e  nop
0x18001805f  mov     dword ptr [rsp+920h+var_900], ebx
0x180018063  lea     r9, aErrorLoadingSr_0; "Error loading SRM.DLL [0x%08lx]"
0x18001806a  lea     r8, aSrmloadstring; "SrmLoadString"
0x180018071  mov     edx, 28h ; '('
0x180018076  mov     rcx, rax
0x180018079  call    ?StaticTrace@CSrmFunctionTracerBase@@SAXUCSrmDebugInfo@@KPEBG1ZZ; CSrmFunctionTracerBase::StaticTrace(CSrmDebugInfo,ulong,ushort const *,ushort const *,...)
0x18001807e  mov     dword ptr [rsp+920h+pExceptionObject], 8000FFFFh
0x180018086  lea     rdx, _TI1J; pThrowInfo
0x18001808d  lea     rcx, [rsp+920h+pExceptionObject]; pExceptionObject
0x180018092  call    _CxxThrowException_0
```
