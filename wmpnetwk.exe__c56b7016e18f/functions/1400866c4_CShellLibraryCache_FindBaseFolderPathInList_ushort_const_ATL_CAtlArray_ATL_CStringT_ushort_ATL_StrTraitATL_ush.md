# CShellLibraryCache::FindBaseFolderPathInList(ushort const *,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> const &,ushort * *)

- ea: `0x1400866c4`
- end: `0x140086787`
- name: `?FindBaseFolderPathInList@CShellLibraryCache@@IEBA_NPEBGAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAPEAG@Z`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140086618`

## callees

- `0x140039480`
- `0x1400866c4`
- `0x14009acec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14008676e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14008676e`
- `ole32!CoTaskMemAlloc` at `0x14008673b`
- `ole32!CoTaskMemAlloc` at `0x14008673b`

## pseudocode

```c
char __fastcall CShellLibraryCache::FindBaseFolderPathInList(__int64 a1, const wchar_t *a2, _QWORD *a3, LPVOID *a4)
{
  char v4; // bp
  unsigned __int64 v5; // rdi
  unsigned int v9; // ebx
  const wchar_t **v10; // rax
  _QWORD *v11; // rax
  __int64 v12; // rbx
  _QWORD *v13; // rax

  v4 = 0;
  v5 = 0;
  if ( a3[1] )
  {
    while ( 1 )
    {
      v9 = *(_DWORD *)(*(_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](
                                    a3,
                                    v5)
                     - 16LL);
      v10 = (const wchar_t **)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](
                                a3,
                                v5);
      if ( !wcsncmp_0(a2, *v10, v9) )
        break;
      if ( ++v5 >= a3[1] )
        return v4;
    }
    v11 = (_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](
                      a3,
                      v5);
    *a4 = CoTaskMemAlloc(2LL * (*(_DWORD *)(*v11 - 16LL) + 1));
    v12 = *(_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](
                       a3,
                       v5);
    v13 = (_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](
                      a3,
                      v5);
    _o_wcscpy_s(*a4, *(_DWORD *)(*v13 - 16LL) + 1, v12);
    return 1;
  }
  return v4;
}

```

## disassembly

```asm
0x1400866c4  push    rbx
0x1400866c6  push    rbp
0x1400866c7  push    rsi
0x1400866c8  push    rdi
0x1400866c9  push    r14
0x1400866cb  push    r15
0x1400866cd  sub     rsp, 28h
0x1400866d1  xor     bpl, bpl
0x1400866d4  xor     edi, edi
0x1400866d6  mov     r15, r9
0x1400866d9  mov     rsi, r8
0x1400866dc  mov     r14, rdx
0x1400866df  cmp     [r8+8], rdi
0x1400866e3  jbe     loc_140086777
0x1400866e9  mov     rdx, rdi
0x1400866ec  mov     rcx, rsi
0x1400866ef  call    ??A?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](unsigned __int64)
0x1400866f4  mov     rdx, rdi
0x1400866f7  mov     rcx, [rax]
0x1400866fa  mov     ebx, [rcx-10h]
0x1400866fd  mov     rcx, rsi
0x140086700  call    ??A?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](unsigned __int64)
0x140086705  mov     r8d, ebx; MaxCount
0x140086708  mov     rcx, r14; String1
0x14008670b  mov     rdx, [rax]; String2
0x14008670e  call    wcsncmp_0
0x140086713  test    eax, eax
0x140086715  jz      short loc_140086722
0x140086717  inc     rdi
0x14008671a  cmp     rdi, [rsi+8]
0x14008671e  jb      short loc_1400866E9
0x140086720  jmp     short loc_140086777
0x140086722  mov     rdx, rdi
0x140086725  mov     rcx, rsi
0x140086728  call    ??A?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](unsigned __int64)
0x14008672d  mov     rcx, [rax]
0x140086730  mov     eax, [rcx-10h]
0x140086733  inc     eax
0x140086735  movsxd  rcx, eax
0x140086738  add     rcx, rcx; cb
0x14008673b  call    cs:__imp_CoTaskMemAlloc
0x140086741  mov     rdx, rdi
0x140086744  mov     rcx, rsi
0x140086747  mov     [r15], rax
0x14008674a  call    ??A?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](unsigned __int64)
0x14008674f  mov     rdx, rdi
0x140086752  mov     rcx, rsi
0x140086755  mov     rbx, [rax]
0x140086758  call    ??A?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](unsigned __int64)
0x14008675d  mov     r8, rbx
0x140086760  mov     rcx, [rax]
0x140086763  mov     eax, [rcx-10h]
0x140086766  mov     rcx, [r15]
0x140086769  inc     eax
0x14008676b  movsxd  rdx, eax
0x14008676e  call    cs:__imp__o_wcscpy_s
0x140086774  mov     bpl, 1
0x140086777  mov     al, bpl
0x14008677a  add     rsp, 28h
0x14008677e  pop     r15
0x140086780  pop     r14
0x140086782  pop     rdi
0x140086783  pop     rsi
0x140086784  pop     rbp
0x140086785  pop     rbx
0x140086786  retn
```
