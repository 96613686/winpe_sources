# COleControlHost::OCHostWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001e1b0`
- end: `0x18001e527`
- name: `?OCHostWndProc@COleControlHost@@KA_JPEAUHWND__@@I_K_J@Z`
- size: `887`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, unsigned __int64, struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004370`
- `0x180008320`
- `0x180009018`
- `0x18001dd2c`
- `0x18001e1b0`
- `0x18001ecb8`
- `0x18001ed58`
- `0x18001edd8`
- `0x18001f0a4`
- `0x18001f120`
- `0x18001f204`
- `0x18001f3dc`
- `0x18001f458`
- `0x180029010`

## import_xrefs

- `USER32!DefWindowProcW` at `0x18001e1ff`
- `USER32!DefWindowProcW` at `0x18001e1ff`
- `USER32!EndPaint` at `0x18001e28f`
- `USER32!EndPaint` at `0x18001e28f`
- `USER32!BeginPaint` at `0x18001e275`
- `USER32!BeginPaint` at `0x18001e275`
- `USER32!SetFocus` at `0x18001e2d4`
- `USER32!SetFocus` at `0x18001e2d4`
- `USER32!SendMessageW` at `0x18001e435`
- `USER32!SendMessageW` at `0x18001e435`
- `USER32!SetWindowLongPtrW` at `0x18001e306`
- `USER32!SetWindowLongPtrW` at `0x18001e306`
- `USER32!GetWindowLongPtrW` at `0x18001e1dd`
- `USER32!GetWindowLongPtrW` at `0x18001e1dd`

## pseudocode

```c
__int64 __fastcall COleControlHost::OCHostWndProc(HWND hWnd, UINT Msg, WPARAM a3, struct tagCREATESTRUCTW *a4)
{
  LONG_PTR WindowLongPtrW; // rax
  HWND v9; // rdx
  LONG_PTR v10; // rbx
  __int64 result; // rax
  HDC v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  HWND v15; // rax
  COleControlHost *v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rcx
  HWND hWnda[2]; // [rsp+30h] [rbp-98h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+40h] [rbp-88h] BYREF

  WindowLongPtrW = GetWindowLongPtrW(hWnd, 0);
  v10 = WindowLongPtrW;
  if ( !WindowLongPtrW )
  {
    if ( Msg != 1 )
      return DefWindowProcW(hWnd, Msg, a3, (LPARAM)a4);
LABEL_25:
    v15 = (HWND)operator new(0xB0u);
    hWnda[0] = v15;
    if ( v15 )
    {
      *((_DWORD *)v15 + 14) = 1;
      *(_QWORD *)v15 = &COleControlHost::`vftable'{for `IOleClientSite'};
      *((_DWORD *)v15 + 15) = 1;
      *((_QWORD *)v15 + 1) = &COleControlHost::`vftable'{for `IAdviseSink'};
      *((_QWORD *)v15 + 2) = &COleControlHost::`vftable'{for `IOleInPlaceSite'};
      *((_QWORD *)v15 + 3) = &COleControlHost::`vftable'{for `IOleInPlaceFrame'};
      *((_QWORD *)v15 + 4) = &COleControlHost::`vftable'{for `IServiceProvider'};
      *((_QWORD *)v15 + 5) = &COleControlHost::`vftable'{for `IOleCommandTarget'};
      *((_QWORD *)v15 + 6) = &COleControlHost::`vftable'{for `IDispatch'};
      *((_QWORD *)v15 + 10) = hWnd;
      CProxyUIHandler::CProxyUIHandler((CProxyUIHandler *)(v15 + 36));
      if ( v16 )
        return COleControlHost::_OnCreate(v16, hWnd, a4);
    }
    return -1;
  }
  if ( Msg <= 0x311 )
  {
    switch ( Msg )
    {
      case 0x311u:
        v17 = *(_QWORD *)(WindowLongPtrW + 128);
        if ( v17 )
        {
          hWnda[0] = 0;
          if ( (*(int (__fastcall **)(__int64, HWND *))(*(_QWORD *)v17 + 24LL))(v17, hWnda) >= 0 )
            SendMessageW(hWnda[0], 0x311u, a3, (LPARAM)a4);
        }
        break;
      case 1u:
        goto LABEL_25;
      case 2u:
        SetWindowLongPtrW(*(HWND *)(WindowLongPtrW + 80), 0, 0);
        COleControlHost::_SendNotify((COleControlHost *)v10, 0x1304u, 0);
        v14 = *(_QWORD *)(v10 + 128);
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
        COleControlHost::_Exit((COleControlHost *)v10);
        (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)v10 + 16LL))(v10);
        break;
      case 5u:
        return COleControlHost::_OnSize((COleControlHost *)WindowLongPtrW, v9, (__int64)a4);
      case 7u:
        if ( (*(_DWORD *)(WindowLongPtrW + 64) & 0x4000) != 0 )
        {
          v13 = *(_QWORD *)(WindowLongPtrW + 128);
          hWnda[0] = 0;
          if ( v13 && (*(int (__fastcall **)(__int64, HWND *))(*(_QWORD *)v13 + 24LL))(v13, hWnda) >= 0 )
            SetFocus(hWnda[0]);
        }
        else
        {
          COleControlHost::_DoVerb((COleControlHost *)WindowLongPtrW, 0xFFFFFFFC, 0);
        }
        break;
      case 0xFu:
        memset_0(&Paint, 0, sizeof(Paint));
        v12 = BeginPaint(*(HWND *)(v10 + 80), &Paint);
        COleControlHost::_Draw((COleControlHost *)v10, v12);
        EndPaint(*(HWND *)(v10 + 80), &Paint);
        break;
      case 0x14u:
        if ( *(_QWORD *)(WindowLongPtrW + 112) )
          return *(_DWORD *)(WindowLongPtrW + 72) != 0;
        break;
      default:
        return DefWindowProcW(hWnd, Msg, a3, (LPARAM)a4);
    }
    return 0;
  }
  if ( Msg != 1024 )
  {
    switch ( Msg )
    {
      case 0x401u:
        LODWORD(result) = COleControlHost::_InitOCStruct((COleControlHost *)WindowLongPtrW, (struct _OCHINITSTRUCT *)a4);
        break;
      case 0x402u:
        return COleControlHost::_SetOwner((COleControlHost *)WindowLongPtrW, (struct IUnknown *)a4);
      case 0x403u:
        LODWORD(result) = COleControlHost::_DoVerb((COleControlHost *)WindowLongPtrW, a3, (struct tagMSG *)a4);
        break;
      case 0x405u:
        v18 = *(_QWORD *)(WindowLongPtrW + 168);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        if ( (*((int (__fastcall **)(struct tagCREATESTRUCTW *, GUID *, GUID *, LONG_PTR))a4->lpCreateParams + 3))(
               a4,
               &IID_IOleControlSite,
               &GUID_00020400_0000_0000_c000_000000000046,
               v10 + 168) < 0 )
          *(_QWORD *)(v10 + 168) = 0;
        return 0;
      default:
        return DefWindowProcW(hWnd, Msg, a3, (LPARAM)a4);
    }
    return (int)result;
  }
  if ( a4 )
  {
    LODWORD(result) = (***(__int64 (__fastcall ****)(_QWORD, LPVOID, HINSTANCE))(WindowLongPtrW + 112))(
                        *(_QWORD *)(WindowLongPtrW + 112),
                        a4->lpCreateParams,
                        a4->hInstance);
    return (int)result;
  }
  return -1;
}

```

## disassembly

```asm
0x18001e1b0  push    rbx
0x18001e1b2  push    rbp
0x18001e1b3  push    rsi
0x18001e1b4  push    rdi
0x18001e1b5  push    r14
0x18001e1b7  sub     rsp, 0A0h
0x18001e1be  mov     rax, cs:__security_cookie
0x18001e1c5  xor     rax, rsp
0x18001e1c8  mov     [rsp+0C8h+var_38], rax
0x18001e1d0  mov     esi, edx
0x18001e1d2  mov     rdi, r9
0x18001e1d5  xor     edx, edx; nIndex
0x18001e1d7  mov     rbp, r8
0x18001e1da  mov     r14, rcx
0x18001e1dd  call    cs:__imp_GetWindowLongPtrW
0x18001e1e3  mov     rbx, rax
0x18001e1e6  test    rax, rax
0x18001e1e9  jnz     short loc_18001E20A
0x18001e1eb  cmp     esi, 1
0x18001e1ee  jz      loc_18001E350
0x18001e1f4  mov     r9, rdi; lParam
0x18001e1f7  mov     r8, rbp; wParam
0x18001e1fa  mov     edx, esi; Msg
0x18001e1fc  mov     rcx, r14; hWnd
0x18001e1ff  call    cs:__imp_DefWindowProcW
0x18001e205  jmp     loc_18001E509
0x18001e20a  cmp     esi, 311h
0x18001e210  ja      loc_18001E440
0x18001e216  jz      loc_18001E3F3
0x18001e21c  mov     eax, esi
0x18001e21e  sub     eax, 1
0x18001e221  jz      loc_18001E350
0x18001e227  sub     eax, 1
0x18001e22a  jz      loc_18001E2FD
0x18001e230  sub     eax, 3
0x18001e233  jz      loc_18001E2ED
0x18001e239  sub     eax, 2
0x18001e23c  jz      short loc_18001E29C
0x18001e23e  sub     eax, 8
0x18001e241  jz      short loc_18001E25C
0x18001e243  cmp     eax, 5
0x18001e246  jnz     short loc_18001E1F4
0x18001e248  cmp     qword ptr [rbx+70h], 0
0x18001e24d  jz      short loc_18001E295
0x18001e24f  xor     eax, eax
0x18001e251  cmp     [rbx+48h], eax
0x18001e254  setnz   al
0x18001e257  jmp     loc_18001E509
0x18001e25c  xor     edx, edx; Val
0x18001e25e  lea     rcx, [rsp+0C8h+Paint]; void *
0x18001e263  lea     r8d, [rdx+48h]; Size
0x18001e267  call    memset_0
0x18001e26c  mov     rcx, [rbx+50h]; hWnd
0x18001e270  lea     rdx, [rsp+0C8h+Paint]; lpPaint
0x18001e275  call    cs:__imp_BeginPaint
0x18001e27b  mov     rdx, rax; HDC
0x18001e27e  mov     rcx, rbx; this
0x18001e281  call    ?_Draw@COleControlHost@@IEAAJPEAUHDC__@@@Z; COleControlHost::_Draw(HDC__ *)
0x18001e286  mov     rcx, [rbx+50h]; hWnd
0x18001e28a  lea     rdx, [rsp+0C8h+Paint]; lpPaint
0x18001e28f  call    cs:__imp_EndPaint
0x18001e295  xor     eax, eax
0x18001e297  jmp     loc_18001E509
0x18001e29c  test    dword ptr [rbx+40h], 4000h
0x18001e2a3  jz      short loc_18001E2DC
0x18001e2a5  mov     rcx, [rbx+80h]
0x18001e2ac  mov     [rsp+0C8h+hWnd], 0
0x18001e2b5  test    rcx, rcx
0x18001e2b8  jz      short loc_18001E295
0x18001e2ba  mov     rax, [rcx]
0x18001e2bd  lea     rdx, [rsp+0C8h+hWnd]
0x18001e2c2  mov     rax, [rax+18h]
0x18001e2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2cb  test    eax, eax
0x18001e2cd  js      short loc_18001E295
0x18001e2cf  mov     rcx, [rsp+0C8h+hWnd]; hWnd
0x18001e2d4  call    cs:__imp_SetFocus
0x18001e2da  jmp     short loc_18001E295
0x18001e2dc  xor     r8d, r8d; struct tagMSG *
0x18001e2df  mov     rcx, rbx; this
0x18001e2e2  lea     edx, [r8-4]; int
0x18001e2e6  call    ?_DoVerb@COleControlHost@@IEAAJJPEAUtagMSG@@@Z; COleControlHost::_DoVerb(long,tagMSG *)
0x18001e2eb  jmp     short loc_18001E295
0x18001e2ed  mov     r8, rdi; __int64
0x18001e2f0  mov     rcx, rbx; this
0x18001e2f3  call    ?_OnSize@COleControlHost@@IEAA_JPEAUHWND__@@_J@Z; COleControlHost::_OnSize(HWND__ *,__int64)
0x18001e2f8  jmp     loc_18001E509
0x18001e2fd  mov     rcx, [rbx+50h]; hWnd
0x18001e301  xor     r8d, r8d; dwNewLong
0x18001e304  xor     edx, edx; nIndex
0x18001e306  call    cs:__imp_SetWindowLongPtrW
0x18001e30c  xor     r8d, r8d; struct tagNMHDR *
0x18001e30f  mov     edx, 1304h; unsigned int
0x18001e314  mov     rcx, rbx; this
0x18001e317  call    ?_SendNotify@COleControlHost@@IEAA_JIPEAUtagNMHDR@@@Z; COleControlHost::_SendNotify(uint,tagNMHDR *)
0x18001e31c  mov     rcx, [rbx+80h]
0x18001e323  test    rcx, rcx
0x18001e326  jz      short loc_18001E334
0x18001e328  mov     rax, [rcx]
0x18001e32b  mov     rax, [rax+28h]
0x18001e32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e334  mov     rcx, rbx; this
0x18001e337  call    ?_Exit@COleControlHost@@IEAAJXZ; COleControlHost::_Exit(void)
0x18001e33c  mov     rax, [rbx]
0x18001e33f  mov     rcx, rbx
0x18001e342  mov     rax, [rax+10h]
0x18001e346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e34b  jmp     loc_18001E295
0x18001e350  mov     ecx, 0B0h; unsigned __int64
0x18001e355  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e35a  mov     [rsp+0C8h+hWnd], rax
0x18001e35f  mov     r9, rax
0x18001e362  test    rax, rax
0x18001e365  jz      loc_18001E505
0x18001e36b  lea     rax, ??_7COleControlHost@@6BIOleClientSite@@@; const COleControlHost::`vftable'{for `IOleClientSite'}
0x18001e372  mov     dword ptr [r9+38h], 1
0x18001e37a  mov     [r9], rax
0x18001e37d  lea     rcx, [r9+90h]; this
0x18001e384  lea     rax, ??_7COleControlHost@@6BIAdviseSink@@@; const COleControlHost::`vftable'{for `IAdviseSink'}
0x18001e38b  mov     dword ptr [r9+3Ch], 1
0x18001e393  mov     [r9+8], rax
0x18001e397  lea     rax, ??_7COleControlHost@@6BIOleInPlaceSite@@@; const COleControlHost::`vftable'{for `IOleInPlaceSite'}
0x18001e39e  mov     [r9+10h], rax
0x18001e3a2  lea     rax, ??_7COleControlHost@@6BIOleInPlaceFrame@@@; const COleControlHost::`vftable'{for `IOleInPlaceFrame'}
0x18001e3a9  mov     [r9+18h], rax
0x18001e3ad  lea     rax, ??_7COleControlHost@@6BIServiceProvider@@@; const COleControlHost::`vftable'{for `IServiceProvider'}
0x18001e3b4  mov     [r9+20h], rax
0x18001e3b8  lea     rax, ??_7COleControlHost@@6BIOleCommandTarget@@@; const COleControlHost::`vftable'{for `IOleCommandTarget'}
0x18001e3bf  mov     [r9+28h], rax
0x18001e3c3  lea     rax, ??_7COleControlHost@@6BIDispatch@@@; const COleControlHost::`vftable'{for `IDispatch'}
0x18001e3ca  mov     [r9+30h], rax
0x18001e3ce  mov     [r9+50h], r14
0x18001e3d2  call    ??0CProxyUIHandler@@QEAA@XZ; CProxyUIHandler::CProxyUIHandler(void)
0x18001e3d7  test    r9, r9
0x18001e3da  jz      loc_18001E505
0x18001e3e0  mov     r8, rdi; struct tagCREATESTRUCTW *
0x18001e3e3  mov     rdx, r14; hWnd
0x18001e3e6  mov     rcx, r9; this
0x18001e3e9  call    ?_OnCreate@COleControlHost@@IEAA_JPEAUHWND__@@PEAUtagCREATESTRUCTW@@@Z; COleControlHost::_OnCreate(HWND__ *,tagCREATESTRUCTW *)
0x18001e3ee  jmp     loc_18001E509
0x18001e3f3  mov     rcx, [rax+80h]
0x18001e3fa  test    rcx, rcx
0x18001e3fd  jz      loc_18001E295
0x18001e403  mov     [rsp+0C8h+hWnd], 0
0x18001e40c  lea     rdx, [rsp+0C8h+hWnd]
0x18001e411  mov     rax, [rcx]
0x18001e414  mov     rax, [rax+18h]
0x18001e418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e41d  test    eax, eax
0x18001e41f  js      loc_18001E295
0x18001e425  mov     rcx, [rsp+0C8h+hWnd]; hWnd
0x18001e42a  mov     r9, rdi; lParam
0x18001e42d  mov     r8, rbp; wParam
0x18001e430  mov     edx, 311h; Msg
0x18001e435  call    cs:__imp_SendMessageW
0x18001e43b  jmp     loc_18001E295
0x18001e440  mov     eax, esi
0x18001e442  sub     eax, 400h
0x18001e447  jz      loc_18001E4E6
0x18001e44d  sub     eax, 1
0x18001e450  jz      loc_18001E4D9
0x18001e456  sub     eax, 1
0x18001e459  jz      short loc_18001E4CC
0x18001e45b  sub     eax, 1
0x18001e45e  jz      short loc_18001E4BD
0x18001e460  cmp     eax, 2
0x18001e463  jnz     loc_18001E1F4
0x18001e469  mov     rcx, [rbx+0A8h]
0x18001e470  test    rcx, rcx
0x18001e473  jz      short loc_18001E481
0x18001e475  mov     rax, [rcx]
0x18001e478  mov     rax, [rax+10h]
0x18001e47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e481  mov     rax, [rdi]
0x18001e484  lea     r9, [rbx+0A8h]
0x18001e48b  lea     r8, _GUID_00020400_0000_0000_c000_000000000046
0x18001e492  mov     rcx, rdi
0x18001e495  lea     rdx, IID_IOleControlSite
0x18001e49c  mov     rax, [rax+18h]
0x18001e4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4a5  test    eax, eax
0x18001e4a7  jns     loc_18001E295
0x18001e4ad  mov     qword ptr [rbx+0A8h], 0
0x18001e4b8  jmp     loc_18001E295
0x18001e4bd  mov     edx, ebp; int
0x18001e4bf  mov     r8, rdi; struct tagMSG *
0x18001e4c2  mov     rcx, rbx; this
0x18001e4c5  call    ?_DoVerb@COleControlHost@@IEAAJJPEAUtagMSG@@@Z; COleControlHost::_DoVerb(long,tagMSG *)
0x18001e4ca  jmp     short loc_18001E501
0x18001e4cc  mov     rdx, rdi; struct IUnknown *
0x18001e4cf  mov     rcx, rbx; this
0x18001e4d2  call    ?_SetOwner@COleControlHost@@IEAA_JPEAUIUnknown@@@Z; COleControlHost::_SetOwner(IUnknown *)
0x18001e4d7  jmp     short loc_18001E509
0x18001e4d9  mov     rdx, rdi; struct _OCHINITSTRUCT *
0x18001e4dc  mov     rcx, rbx; this
0x18001e4df  call    ?_InitOCStruct@COleControlHost@@IEAAJPEAU_OCHINITSTRUCT@@@Z; COleControlHost::_InitOCStruct(_OCHINITSTRUCT *)
0x18001e4e4  jmp     short loc_18001E501
0x18001e4e6  test    rdi, rdi
0x18001e4e9  jz      short loc_18001E505
0x18001e4eb  mov     rcx, [rbx+70h]
0x18001e4ef  mov     r8, [rdi+8]
0x18001e4f3  mov     rdx, [rdi]
0x18001e4f6  mov     rax, [rcx]
0x18001e4f9  mov     rax, [rax]
0x18001e4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e501  cdqe
0x18001e503  jmp     short loc_18001E509
0x18001e505  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e509  mov     rcx, [rsp+0C8h+var_38]
0x18001e511  xor     rcx, rsp; StackCookie
0x18001e514  call    __security_check_cookie
0x18001e519  add     rsp, 0A0h
0x18001e520  pop     r14
0x18001e522  pop     rdi
0x18001e523  pop     rsi
0x18001e524  pop     rbp
0x18001e525  pop     rbx
0x18001e526  retn
```
