# ATL::AtlAxWindowProc

- ea: `0x1800144c0`
- end: `0x1800147d2`
- name: `ATL::AtlAxWindowProc`
- size: `786`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002da0`
- `0x18000a1a8`
- `0x18000ac9c`
- `0x180013410`
- `0x180013638`
- `0x1800144c0`
- `0x18001ab40`
- `0x18005b890`
- `0x180063010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001473d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001479d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001473d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001479d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800145ed`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800145ed`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180014669`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180014669`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800146b5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800146b5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001467e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001467e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800146a3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800146a3`
- `USER32!GetWindowTextLengthW` at `0x18001458c`
- `USER32!GetWindowTextLengthW` at `0x18001458c`
- `USER32!GetWindowTextW` at `0x180014621`
- `USER32!GetWindowTextW` at `0x180014621`
- `USER32!SetWindowTextW` at `0x180014631`
- `USER32!SetWindowTextW` at `0x180014631`
- `USER32!DefWindowProcW` at `0x1800147af`
- `USER32!DefWindowProcW` at `0x1800147af`
- `USER32!SetWindowLongW` at `0x180014549`
- `USER32!SetWindowLongW` at `0x180014549`
- `USER32!GetWindowLongW` at `0x180014521`
- `USER32!GetWindowLongW` at `0x180014539`
- `USER32!GetWindowLongW` at `0x180014521`
- `USER32!GetWindowLongW` at `0x180014539`
- `USER32!GetWindowLongPtrW` at `0x180014559`
- `USER32!GetWindowLongPtrW` at `0x180014559`
- `USER32!SetWindowLongPtrW` at `0x180014770`
- `USER32!SetWindowLongPtrW` at `0x180014770`
- `ole32!OleInitialize` at `0x180014583`
- `ole32!OleInitialize` at `0x180014583`
- `ole32!OleUninitialize` at `0x180014576`
- `ole32!OleUninitialize` at `0x180014576`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LRESULT __fastcall ATL::AtlAxWindowProc(HWND hWnd, UINT Msg, WPARAM wParam, HWND lParam)
{
  LONG WindowLongW; // eax
  LONG_PTR WindowLongPtrW; // rax
  int v10; // esi
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdx
  __int64 v13; // rax
  void *v14; // rsp
  WCHAR *v15; // rbx
  WCHAR *v16; // rax
  int v18; // eax
  unsigned __int16 *v19; // rcx
  SIZE_T v20; // rsi
  HGLOBAL v21; // rax
  void *v22; // r15
  void *v23; // rax
  errno_t v24; // eax
  int ControlLic; // eax
  WCHAR *v26; // rbx
  WCHAR *v27; // rcx
  __int64 v28[7]; // [rsp+0h] [rbp-40h] BYREF
  WCHAR String[4]; // [rsp+40h] [rbp+0h] BYREF
  int (__fastcall ***v30)(_QWORD, GUID *, LONG_PTR *); // [rsp+48h] [rbp+8h] BYREF
  __int64 v31; // [rsp+50h] [rbp+10h] BYREF
  LONG_PTR dwNewLong[2]; // [rsp+58h] [rbp+18h] BYREF

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
      if ( v28 != (__int64 *)-64LL )
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
    *(_QWORD *)String = 0;
    if ( v18 )
    {
      v21 = GlobalAlloc(0x42u, v20);
      v22 = v21;
      if ( !v21 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)String);
        v27 = v15 - 8;
        if ( *((_DWORD *)v15 - 4) != 56797 )
          return -1;
        goto LABEL_33;
      }
      v23 = GlobalLock(v21);
      v24 = memcpy_s_0(v23, v20, (const void *const)(*(_QWORD *)lParam + 2LL), v20);
      ATL::AtlCrtErrorCheck(v24);
      GlobalUnlock(v22);
      CreateStreamOnHGlobal(v22, 1, (LPSTREAM *)String);
    }
    v31 = 0;
    v30 = 0;
    ControlLic = AtlAxCreateControlLicEx(v15, v28[4], (BSTR)v28[5], v28[6], 0);
    v26 = v15 - 8;
    if ( ControlLic >= 0 && (**v30)(v30, &GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e, dwNewLong) >= 0 )
    {
      SetWindowLongPtrW(hWnd, -21, dwNewLong[0]);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v30);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v31);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)String);
      if ( *(_DWORD *)v26 == 56797 )
        free(v26);
      return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)lParam);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v30);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v31);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)String);
    if ( *(_DWORD *)v26 != 56797 )
      return -1;
    v27 = v26;
LABEL_33:
    free(v27);
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
0x1800144c0  push    rbp
0x1800144c2  push    rbx
0x1800144c3  push    rsi
0x1800144c4  push    rdi
0x1800144c5  push    r12
0x1800144c7  push    r13
0x1800144c9  push    r14
0x1800144cb  push    r15
0x1800144cd  sub     rsp, 78h
0x1800144d1  lea     rbp, [rsp+40h]
0x1800144d6  mov     rax, cs:__security_cookie
0x1800144dd  xor     rax, rbp
0x1800144e0  mov     [rbp+70h+var_48], rax
0x1800144e4  mov     r14, r9
0x1800144e7  mov     r12, r8
0x1800144ea  mov     r13d, edx
0x1800144ed  mov     rdi, rcx
0x1800144f0  mov     eax, edx
0x1800144f2  sub     eax, 1
0x1800144f5  jz      loc_180014581
0x1800144fb  sub     eax, 81h
0x180014500  jz      short loc_180014554
0x180014502  cmp     eax, 18Eh
0x180014507  jnz     loc_1800147A3
0x18001450d  cmp     r12d, 1
0x180014511  jnz     loc_1800147A3
0x180014517  lea     ebx, [r12-15h]
0x18001451c  mov     edx, ebx; nIndex
0x18001451e  mov     rcx, r9; hWnd
0x180014521  call    cs:__imp_GetWindowLongW
0x180014527  mov     esi, 10000h
0x18001452c  test    esi, eax
0x18001452e  jz      loc_1800147A3
0x180014534  mov     edx, ebx; nIndex
0x180014536  mov     rcx, rdi; hWnd
0x180014539  call    cs:__imp_GetWindowLongW
0x18001453f  or      eax, esi
0x180014541  mov     r8d, eax; dwNewLong
0x180014544  mov     edx, ebx; nIndex
0x180014546  mov     rcx, rdi; hWnd
0x180014549  call    cs:__imp_SetWindowLongW
0x18001454f  jmp     loc_1800147A3
0x180014554  mov     edx, 0FFFFFFEBh; nIndex
0x180014559  call    cs:__imp_GetWindowLongPtrW
0x18001455f  mov     rdx, rax
0x180014562  test    rax, rax
0x180014565  jz      short loc_180014576
0x180014567  mov     rcx, [rax]
0x18001456a  mov     rax, [rcx+10h]
0x18001456e  mov     rcx, rdx
0x180014571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014576  call    cs:__imp_OleUninitialize
0x18001457c  jmp     loc_1800147A3
0x180014581  xor     ecx, ecx; pvReserved
0x180014583  call    cs:__imp_OleInitialize
0x180014589  mov     rcx, rdi; hWnd
0x18001458c  call    cs:__imp_GetWindowTextLengthW
0x180014592  lea     esi, [rax+1]
0x180014595  movsxd  rax, esi
0x180014598  add     rax, rax
0x18001459b  lea     rcx, [rax+10h]
0x18001459f  cmp     rax, rcx
0x1800145a2  sbb     rdx, rdx
0x1800145a5  mov     r15d, 0DDDDh
0x1800145ab  and     rdx, rcx
0x1800145ae  jz      short loc_180014604
0x1800145b0  cmp     rdx, 400h
0x1800145b7  ja      short loc_1800145EA
0x1800145b9  lea     rax, [rdx+0Fh]
0x1800145bd  cmp     rax, rdx
0x1800145c0  ja      short loc_1800145CC
0x1800145c2  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800145cc  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800145d0  call    _alloca_probe
0x1800145d5  sub     rsp, rax
0x1800145d8  lea     rbx, [rsp+0B0h+String]
0x1800145dd  test    rbx, rbx
0x1800145e0  jz      short loc_180014606
0x1800145e2  mov     dword ptr [rbx], 0CCCCh
0x1800145e8  jmp     short loc_1800145FE
0x1800145ea  mov     rcx, rdx; Size
0x1800145ed  call    cs:__imp_malloc
0x1800145f3  mov     rbx, rax
0x1800145f6  test    rax, rax
0x1800145f9  jz      short loc_180014606
0x1800145fb  mov     [rax], r15d
0x1800145fe  add     rbx, 10h
0x180014602  jmp     short loc_180014606
0x180014604  xor     ebx, ebx
0x180014606  mov     [rbp+70h+var_50], rbx
0x18001460a  test    rbx, rbx
0x18001460d  jnz     short loc_180014618
0x18001460f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014613  jmp     loc_1800147B5
0x180014618  mov     r8d, esi; nMaxCount
0x18001461b  mov     rdx, rbx; lpString
0x18001461e  mov     rcx, rdi; hWnd
0x180014621  call    cs:__imp_GetWindowTextW
0x180014627  lea     rdx, String; lpString
0x18001462e  mov     rcx, rdi; hWnd
0x180014631  call    cs:__imp_SetWindowTextW
0x180014637  mov     [rbp+70h+dwNewLong], 0
0x18001463f  xor     eax, eax
0x180014641  test    r14, r14
0x180014644  jz      short loc_180014655
0x180014646  mov     rcx, [r14]
0x180014649  test    rcx, rcx
0x18001464c  jz      short loc_180014655
0x18001464e  movzx   eax, word ptr [rcx]
0x180014651  mov     esi, eax
0x180014653  jmp     short loc_180014657
0x180014655  xor     esi, esi
0x180014657  xor     r8d, r8d
0x18001465a  mov     qword ptr [rbp+70h+String], r8
0x18001465e  test    eax, eax
0x180014660  jz      short loc_1800146C5
0x180014662  mov     rdx, rsi; dwBytes
0x180014665  lea     ecx, [r8+42h]; uFlags
0x180014669  call    cs:__imp_GlobalAlloc
0x18001466f  mov     r15, rax
0x180014672  test    rax, rax
0x180014675  jz      loc_180014748
0x18001467b  mov     rcx, rax; hMem
0x18001467e  call    cs:__imp_GlobalLock
0x180014684  mov     r8, [r14]
0x180014687  add     r8, 2; Source
0x18001468b  mov     r9, rsi; SourceSize
0x18001468e  mov     rdx, rsi; DestinationSize
0x180014691  mov     rcx, rax; Destination
0x180014694  call    memcpy_s_0
0x180014699  mov     ecx, eax; int
0x18001469b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800146a0  mov     rcx, r15; hMem
0x1800146a3  call    cs:__imp_GlobalUnlock
0x1800146a9  lea     r8, [rbp+70h+String]; ppstm
0x1800146ad  mov     edx, 1; fDeleteOnRelease
0x1800146b2  mov     rcx, r15; hGlobal
0x1800146b5  call    cs:__imp_CreateStreamOnHGlobal
0x1800146bb  mov     r8, qword ptr [rbp+70h+String]
0x1800146bf  mov     r15d, 0DDDDh
0x1800146c5  mov     [rbp+70h+var_60], 0
0x1800146cd  mov     [rbp+70h+var_68], 0
0x1800146d5  mov     [rsp+0B0h+var_78], 0; __int64
0x1800146de  lea     r9, [rbp+70h+var_68]
0x1800146e2  mov     rdx, rdi
0x1800146e5  mov     rcx, rbx; unsigned __int16 *
0x1800146e8  call    AtlAxCreateControlLicEx
0x1800146ed  add     rbx, 0FFFFFFFFFFFFFFF0h
0x1800146f1  test    eax, eax
0x1800146f3  js      short loc_180014713
0x1800146f5  mov     rcx, [rbp+70h+var_68]
0x1800146f9  mov     rax, [rcx]
0x1800146fc  lea     r8, [rbp+70h+dwNewLong]
0x180014700  lea     rdx, _GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e
0x180014707  mov     rax, [rax]
0x18001470a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001470f  test    eax, eax
0x180014711  jns     short loc_180014764
0x180014713  lea     rcx, [rbp+70h+var_68]
0x180014717  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001471c  nop
0x18001471d  lea     rcx, [rbp+70h+var_60]
0x180014721  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180014726  nop
0x180014727  lea     rcx, [rbp+70h+String]
0x18001472b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014730  nop
0x180014731  cmp     [rbx], r15d
0x180014734  jnz     loc_18001460F
0x18001473a  mov     rcx, rbx; Block
0x18001473d  call    cs:__imp_free
0x180014743  jmp     loc_18001460F
0x180014748  lea     rcx, [rbp+70h+String]
0x18001474c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014751  nop
0x180014752  lea     rcx, [rbx-10h]
0x180014756  cmp     dword ptr [rcx], 0DDDDh
0x18001475c  jnz     loc_18001460F
0x180014762  jmp     short loc_18001473D
0x180014764  mov     r8, [rbp+70h+dwNewLong]; dwNewLong
0x180014768  mov     edx, 0FFFFFFEBh; nIndex
0x18001476d  mov     rcx, rdi; hWnd
0x180014770  call    cs:__imp_SetWindowLongPtrW
0x180014776  nop
0x180014777  lea     rcx, [rbp+70h+var_68]
0x18001477b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014780  nop
0x180014781  lea     rcx, [rbp+70h+var_60]
0x180014785  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001478a  nop
0x18001478b  lea     rcx, [rbp+70h+String]
0x18001478f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014794  nop
0x180014795  cmp     [rbx], r15d
0x180014798  jnz     short loc_1800147A3
0x18001479a  mov     rcx, rbx; Block
0x18001479d  call    cs:__imp_free
0x1800147a3  mov     r9, r14; lParam
0x1800147a6  mov     r8, r12; wParam
0x1800147a9  mov     edx, r13d; Msg
0x1800147ac  mov     rcx, rdi; hWnd
0x1800147af  call    cs:__imp_DefWindowProcW
0x1800147b5  mov     rcx, [rbp+70h+var_48]
0x1800147b9  xor     rcx, rbp; StackCookie
0x1800147bc  call    __security_check_cookie
0x1800147c1  lea     rsp, [rbp+38h]
0x1800147c5  pop     r15
0x1800147c7  pop     r14
0x1800147c9  pop     r13
0x1800147cb  pop     r12
0x1800147cd  pop     rdi
0x1800147ce  pop     rsi
0x1800147cf  pop     rbx
0x1800147d0  pop     rbp
0x1800147d1  retn
```
