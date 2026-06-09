# ATL::AtlAxWindowProc2

- ea: `0x180014170`
- end: `0x1800144b7`
- name: `ATL::AtlAxWindowProc2`
- size: `839`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002da0`
- `0x18000a1a8`
- `0x18000ac9c`
- `0x180013410`
- `0x180013638`
- `0x180014170`
- `0x180018268`
- `0x18001ab40`
- `0x18005b890`
- `0x180063010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014431`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014482`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014431`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014482`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001429a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001429a`
- `OLEAUT32!__imp_SysFreeString` at `0x180014411`
- `OLEAUT32!__imp_SysFreeString` at `0x180014466`
- `OLEAUT32!__imp_SysFreeString` at `0x180014411`
- `OLEAUT32!__imp_SysFreeString` at `0x180014466`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180014319`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180014319`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180014361`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180014361`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001432a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001432a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001434f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001434f`
- `USER32!GetWindowTextLengthW` at `0x18001423f`
- `USER32!GetWindowTextLengthW` at `0x18001423f`
- `USER32!GetWindowTextW` at `0x1800142d1`
- `USER32!GetWindowTextW` at `0x1800142d1`
- `USER32!SetWindowTextW` at `0x1800142e1`
- `USER32!SetWindowTextW` at `0x1800142e1`
- `USER32!DefWindowProcW` at `0x180014494`
- `USER32!DefWindowProcW` at `0x180014494`
- `USER32!SetWindowLongW` at `0x1800141fc`
- `USER32!SetWindowLongW` at `0x1800141fc`
- `USER32!GetWindowLongW` at `0x1800141d4`
- `USER32!GetWindowLongW` at `0x1800141ec`
- `USER32!GetWindowLongW` at `0x1800141d4`
- `USER32!GetWindowLongW` at `0x1800141ec`
- `USER32!GetWindowLongPtrW` at `0x18001420c`
- `USER32!GetWindowLongPtrW` at `0x18001420c`
- `USER32!SetWindowLongPtrW` at `0x180014448`
- `USER32!SetWindowLongPtrW` at `0x180014448`
- `ole32!OleInitialize` at `0x180014236`
- `ole32!OleInitialize` at `0x180014236`
- `ole32!OleUninitialize` at `0x180014229`
- `ole32!OleUninitialize` at `0x180014229`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
LRESULT __fastcall ATL::AtlAxWindowProc2(HWND hWnd, UINT Msg, WPARAM wParam, HWND lParam)
{
  LONG WindowLongW; // eax
  LONG_PTR WindowLongPtrW; // rax
  int v10; // ebx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdx
  __int64 v13; // rax
  void *v14; // rsp
  WCHAR *v15; // rdi
  WCHAR *v16; // rax
  int v18; // eax
  unsigned __int16 *v19; // rcx
  SIZE_T v20; // rbx
  struct IStream *v21; // rcx
  HGLOBAL v22; // rax
  void *v23; // rsi
  void *v24; // rax
  errno_t v25; // eax
  WCHAR *v26; // rsi
  OLECHAR *v27; // rcx
  WCHAR *v28; // rcx
  OLECHAR *v29; // rbx
  __int64 v30[7]; // [rsp+0h] [rbp-40h] BYREF
  WCHAR String[4]; // [rsp+40h] [rbp+0h] BYREF
  int (__fastcall ***v32)(_QWORD, GUID *, LONG_PTR *); // [rsp+48h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp+10h] BYREF
  __int64 v34; // [rsp+58h] [rbp+18h] BYREF
  LONG_PTR dwNewLong[2]; // [rsp+60h] [rbp+20h] BYREF

  if ( Msg == 1 )
  {
    OleInitialize(0);
    v10 = GetWindowTextLengthW(hWnd) + 1;
    v11 = 2LL * v10;
    v12 = (v11 + 16) & -(__int64)(v11 < v11 + 16);
    if ( v12 )
    {
      if ( v12 > 0x400 )
      {
        v16 = (WCHAR *)malloc((v11 + 16) & -(__int64)(v11 < v11 + 16));
        v15 = v16;
        if ( !v16 )
          goto LABEL_20;
        *(_DWORD *)v16 = 56797;
        goto LABEL_18;
      }
      v13 = v12 + 15;
      if ( v12 + 15 < v12 )
        v13 = 0xFFFFFFFFFFFFFF0LL;
      v14 = alloca(v13 & 0xFFFFFFFFFFFFFFF0uLL);
      v15 = String;
      if ( v30 != (__int64 *)-64LL )
      {
        wcscpy(String, L"쳌");
LABEL_18:
        v15 += 8;
      }
    }
    else
    {
      v15 = 0;
    }
LABEL_20:
    dwNewLong[1] = (LONG_PTR)v15;
    if ( !v15 )
      return -1;
    GetWindowTextW(hWnd, v15, v10);
    SetWindowTextW(hWnd, &::String);
    dwNewLong[0] = 0;
    v18 = 0;
    if ( lParam && (v19 = *(unsigned __int16 **)lParam) != 0 )
    {
      v18 = *v19;
      v20 = *v19;
    }
    else
    {
      v20 = 0;
    }
    v21 = 0;
    *(_QWORD *)String = 0;
    if ( v18 )
    {
      v22 = GlobalAlloc(0x42u, v20);
      v23 = v22;
      if ( !v22 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)String);
        v28 = v15 - 8;
        if ( *((_DWORD *)v15 - 4) != 56797 )
          return -1;
        goto LABEL_38;
      }
      v24 = GlobalLock(v22);
      v25 = memcpy_s_0(v24, v20, (const void *const)(*(_QWORD *)lParam + 2LL), v20);
      ATL::AtlCrtErrorCheck(v25);
      GlobalUnlock(v23);
      CreateStreamOnHGlobal(v23, 1, (LPSTREAM *)String);
      v21 = *(struct IStream **)String;
    }
    bstrString = 0;
    v26 = v15 - 8;
    if ( (int)ATL::_DialogSplitHelper::ParseInitData(v21, &bstrString) >= 0 )
    {
      v34 = 0;
      v32 = 0;
      v29 = bstrString;
      if ( (int)AtlAxCreateControlLicEx(v15, v30[4], (BSTR)v30[5], v30[6], (__int64)bstrString) >= 0
        && (**v32)(v32, &GUID_3935bda8_4ed9_495c_8650_e01fc1e38a4b, dwNewLong) >= 0 )
      {
        SetWindowLongPtrW(hWnd, -21, dwNewLong[0]);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v32);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v34);
        SysFreeString(v29);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)String);
        if ( *(_DWORD *)v26 == 56797 )
          free(v15 - 8);
        return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v32);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v34);
      v27 = v29;
    }
    else
    {
      v27 = bstrString;
    }
    SysFreeString(v27);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)String);
    if ( *(_DWORD *)v26 != 56797 )
      return -1;
    v28 = v15 - 8;
LABEL_38:
    free(v28);
    return -1;
  }
  if ( Msg == 130 )
  {
    WindowLongPtrW = GetWindowLongPtrW(hWnd, -21);
    if ( WindowLongPtrW )
      (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 16LL))(WindowLongPtrW);
    OleUninitialize();
  }
  else if ( Msg == 528 && (_DWORD)wParam == 1 && (GetWindowLongW(lParam, -20) & 0x10000) != 0 )
  {
    WindowLongW = GetWindowLongW(hWnd, -20);
    SetWindowLongW(hWnd, -20, WindowLongW | 0x10000);
  }
  return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
}

```

## disassembly

```asm
0x180014170  push    rbp
0x180014172  push    rbx
0x180014173  push    rsi
0x180014174  push    rdi
0x180014175  push    r12
0x180014177  push    r13
0x180014179  push    r14
0x18001417b  push    r15
0x18001417d  sub     rsp, 88h
0x180014184  lea     rbp, [rsp+40h]
0x180014189  mov     rax, cs:__security_cookie
0x180014190  xor     rax, rbp
0x180014193  mov     [rbp+80h+var_50], rax
0x180014197  mov     r15, r9
0x18001419a  mov     r12, r8
0x18001419d  mov     r13d, edx
0x1800141a0  mov     r14, rcx
0x1800141a3  mov     eax, edx
0x1800141a5  sub     eax, 1
0x1800141a8  jz      loc_180014234
0x1800141ae  sub     eax, 81h
0x1800141b3  jz      short loc_180014207
0x1800141b5  cmp     eax, 18Eh
0x1800141ba  jnz     loc_180014488
0x1800141c0  cmp     r12d, 1
0x1800141c4  jnz     loc_180014488
0x1800141ca  lea     ebx, [r12-15h]
0x1800141cf  mov     edx, ebx; nIndex
0x1800141d1  mov     rcx, r9; hWnd
0x1800141d4  call    cs:__imp_GetWindowLongW
0x1800141da  mov     edi, 10000h
0x1800141df  test    edi, eax
0x1800141e1  jz      loc_180014488
0x1800141e7  mov     edx, ebx; nIndex
0x1800141e9  mov     rcx, r14; hWnd
0x1800141ec  call    cs:__imp_GetWindowLongW
0x1800141f2  or      eax, edi
0x1800141f4  mov     r8d, eax; dwNewLong
0x1800141f7  mov     edx, ebx; nIndex
0x1800141f9  mov     rcx, r14; hWnd
0x1800141fc  call    cs:__imp_SetWindowLongW
0x180014202  jmp     loc_180014488
0x180014207  mov     edx, 0FFFFFFEBh; nIndex
0x18001420c  call    cs:__imp_GetWindowLongPtrW
0x180014212  mov     rdx, rax
0x180014215  test    rax, rax
0x180014218  jz      short loc_180014229
0x18001421a  mov     rcx, [rax]
0x18001421d  mov     rax, [rcx+10h]
0x180014221  mov     rcx, rdx
0x180014224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014229  call    cs:__imp_OleUninitialize
0x18001422f  jmp     loc_180014488
0x180014234  xor     ecx, ecx; pvReserved
0x180014236  call    cs:__imp_OleInitialize
0x18001423c  mov     rcx, r14; hWnd
0x18001423f  call    cs:__imp_GetWindowTextLengthW
0x180014245  lea     ebx, [rax+1]
0x180014248  movsxd  rax, ebx
0x18001424b  add     rax, rax
0x18001424e  lea     rcx, [rax+10h]
0x180014252  cmp     rax, rcx
0x180014255  sbb     rdx, rdx
0x180014258  and     rdx, rcx
0x18001425b  jz      short loc_1800142B4
0x18001425d  cmp     rdx, 400h
0x180014264  ja      short loc_180014297
0x180014266  lea     rax, [rdx+0Fh]
0x18001426a  cmp     rax, rdx
0x18001426d  ja      short loc_180014279
0x18001426f  mov     rax, 0FFFFFFFFFFFFFF0h
0x180014279  and     rax, 0FFFFFFFFFFFFFFF0h
0x18001427d  call    _alloca_probe
0x180014282  sub     rsp, rax
0x180014285  lea     rdi, [rsp+0C0h+String]
0x18001428a  test    rdi, rdi
0x18001428d  jz      short loc_1800142B6
0x18001428f  mov     dword ptr [rdi], 0CCCCh
0x180014295  jmp     short loc_1800142AE
0x180014297  mov     rcx, rdx; Size
0x18001429a  call    cs:__imp_malloc
0x1800142a0  mov     rdi, rax
0x1800142a3  test    rax, rax
0x1800142a6  jz      short loc_1800142B6
0x1800142a8  mov     dword ptr [rax], 0DDDDh
0x1800142ae  add     rdi, 10h
0x1800142b2  jmp     short loc_1800142B6
0x1800142b4  xor     edi, edi
0x1800142b6  mov     [rbp+80h+var_58], rdi
0x1800142ba  test    rdi, rdi
0x1800142bd  jnz     short loc_1800142C8
0x1800142bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800142c3  jmp     loc_18001449A
0x1800142c8  mov     r8d, ebx; nMaxCount
0x1800142cb  mov     rdx, rdi; lpString
0x1800142ce  mov     rcx, r14; hWnd
0x1800142d1  call    cs:__imp_GetWindowTextW
0x1800142d7  lea     rdx, String; lpString
0x1800142de  mov     rcx, r14; hWnd
0x1800142e1  call    cs:__imp_SetWindowTextW
0x1800142e7  mov     [rbp+80h+dwNewLong], 0
0x1800142ef  xor     eax, eax
0x1800142f1  test    r15, r15
0x1800142f4  jz      short loc_180014305
0x1800142f6  mov     rcx, [r15]
0x1800142f9  test    rcx, rcx
0x1800142fc  jz      short loc_180014305
0x1800142fe  movzx   eax, word ptr [rcx]
0x180014301  mov     ebx, eax
0x180014303  jmp     short loc_180014307
0x180014305  xor     ebx, ebx
0x180014307  xor     ecx, ecx
0x180014309  mov     qword ptr [rbp+80h+String], rcx
0x18001430d  test    eax, eax
0x18001430f  jz      short loc_18001436B
0x180014311  mov     rdx, rbx; dwBytes
0x180014314  mov     ecx, 42h ; 'B'; uFlags
0x180014319  call    cs:__imp_GlobalAlloc
0x18001431f  mov     rsi, rax
0x180014322  test    rax, rax
0x180014325  jz      short loc_18001438D
0x180014327  mov     rcx, rax; hMem
0x18001432a  call    cs:__imp_GlobalLock
0x180014330  mov     r8, [r15]
0x180014333  add     r8, 2; Source
0x180014337  mov     r9, rbx; SourceSize
0x18001433a  mov     rdx, rbx; DestinationSize
0x18001433d  mov     rcx, rax; Destination
0x180014340  call    memcpy_s_0
0x180014345  mov     ecx, eax; int
0x180014347  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001434c  mov     rcx, rsi; hMem
0x18001434f  call    cs:__imp_GlobalUnlock
0x180014355  lea     r8, [rbp+80h+String]; ppstm
0x180014359  mov     edx, 1; fDeleteOnRelease
0x18001435e  mov     rcx, rsi; hGlobal
0x180014361  call    cs:__imp_CreateStreamOnHGlobal
0x180014367  mov     rcx, qword ptr [rbp+80h+String]; struct IStream *
0x18001436b  mov     [rbp+80h+bstrString], 0
0x180014373  lea     rdx, [rbp+80h+bstrString]; unsigned __int16 **
0x180014377  call    ?ParseInitData@_DialogSplitHelper@ATL@@SAJPEAUIStream@@PEAPEAG@Z; ATL::_DialogSplitHelper::ParseInitData(IStream *,ushort * *)
0x18001437c  lea     rsi, [rdi-10h]
0x180014380  test    eax, eax
0x180014382  jns     short loc_1800143AC
0x180014384  mov     rcx, [rbp+80h+bstrString]
0x180014388  jmp     loc_180014411
0x18001438d  lea     rcx, [rbp+80h+String]
0x180014391  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014396  nop
0x180014397  lea     rcx, [rdi-10h]
0x18001439b  cmp     dword ptr [rcx], 0DDDDh
0x1800143a1  jnz     loc_1800142BF
0x1800143a7  jmp     loc_180014431
0x1800143ac  mov     [rbp+80h+var_68], 0
0x1800143b4  mov     [rbp+80h+var_78], 0
0x1800143bc  mov     rbx, [rbp+80h+bstrString]
0x1800143c0  mov     [rsp+0C0h+var_88], rbx; __int64
0x1800143c5  lea     r9, [rbp+80h+var_78]
0x1800143c9  mov     r8, qword ptr [rbp+80h+String]
0x1800143cd  mov     rdx, r14
0x1800143d0  mov     rcx, rdi; unsigned __int16 *
0x1800143d3  call    AtlAxCreateControlLicEx
0x1800143d8  test    eax, eax
0x1800143da  js      short loc_1800143FA
0x1800143dc  mov     rcx, [rbp+80h+var_78]
0x1800143e0  mov     rax, [rcx]
0x1800143e3  lea     r8, [rbp+80h+dwNewLong]
0x1800143e7  lea     rdx, _GUID_3935bda8_4ed9_495c_8650_e01fc1e38a4b
0x1800143ee  mov     rax, [rax]
0x1800143f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143f6  test    eax, eax
0x1800143f8  jns     short loc_18001443C
0x1800143fa  lea     rcx, [rbp+80h+var_78]
0x1800143fe  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014403  nop
0x180014404  lea     rcx, [rbp+80h+var_68]
0x180014408  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001440d  nop
0x18001440e  mov     rcx, rbx; bstrString
0x180014411  call    cs:__imp_SysFreeString
0x180014417  nop
0x180014418  lea     rcx, [rbp+80h+String]
0x18001441c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014421  nop
0x180014422  cmp     dword ptr [rsi], 0DDDDh
0x180014428  jnz     loc_1800142BF
0x18001442e  mov     rcx, rsi; Block
0x180014431  call    cs:__imp_free
0x180014437  jmp     loc_1800142BF
0x18001443c  mov     r8, [rbp+80h+dwNewLong]; dwNewLong
0x180014440  mov     edx, 0FFFFFFEBh; nIndex
0x180014445  mov     rcx, r14; hWnd
0x180014448  call    cs:__imp_SetWindowLongPtrW
0x18001444e  nop
0x18001444f  lea     rcx, [rbp+80h+var_78]
0x180014453  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014458  nop
0x180014459  lea     rcx, [rbp+80h+var_68]
0x18001445d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180014462  nop
0x180014463  mov     rcx, rbx; bstrString
0x180014466  call    cs:__imp_SysFreeString
0x18001446c  nop
0x18001446d  lea     rcx, [rbp+80h+String]
0x180014471  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014476  nop
0x180014477  cmp     dword ptr [rsi], 0DDDDh
0x18001447d  jnz     short loc_180014488
0x18001447f  mov     rcx, rsi; Block
0x180014482  call    cs:__imp_free
0x180014488  mov     r9, r15; lParam
0x18001448b  mov     r8, r12; wParam
0x18001448e  mov     edx, r13d; Msg
0x180014491  mov     rcx, r14; hWnd
0x180014494  call    cs:__imp_DefWindowProcW
0x18001449a  mov     rcx, [rbp+80h+var_50]
0x18001449e  xor     rcx, rbp; StackCookie
0x1800144a1  call    __security_check_cookie
0x1800144a6  lea     rsp, [rbp+48h]
0x1800144aa  pop     r15
0x1800144ac  pop     r14
0x1800144ae  pop     r13
0x1800144b0  pop     r12
0x1800144b2  pop     rdi
0x1800144b3  pop     rsi
0x1800144b4  pop     rbx
0x1800144b5  pop     rbp
0x1800144b6  retn
```
