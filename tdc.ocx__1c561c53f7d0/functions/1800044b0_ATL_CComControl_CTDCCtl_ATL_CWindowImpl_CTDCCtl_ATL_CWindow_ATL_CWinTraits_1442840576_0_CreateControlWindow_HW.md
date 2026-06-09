# ATL::CComControl<CTDCCtl,ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>>::CreateControlWindow(HWND__ *,tagRECT &)

- ea: `0x1800044b0`
- end: `0x1800045f1`
- name: `?CreateControlWindow@?$CComControl@VCTDCCtl@@V?$CWindowImpl@VCTDCCtl@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@ATL@@@ATL@@UEAAPEAUHWND__@@PEAU3@AEAUtagRECT@@@Z`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002108`
- `0x1800044b0`
- `0x180009994`
- `0x18001401c`
- `0x180014138`

## import_xrefs

- `USER32!CreateWindowExA` at `0x1800045db`
- `USER32!CreateWindowExA` at `0x1800045db`
- `KERNEL32!SetLastError` at `0x180004507`
- `KERNEL32!SetLastError` at `0x180004507`
- `KERNEL32!GetCurrentThreadId` at `0x180004548`
- `KERNEL32!GetCurrentThreadId` at `0x180004548`
- `KERNEL32!LeaveCriticalSection` at `0x180004577`
- `KERNEL32!LeaveCriticalSection` at `0x180004577`
- `KERNEL32!EnterCriticalSection` at `0x180004558`
- `KERNEL32!EnterCriticalSection` at `0x180004558`

## pseudocode

```c
HWND __fastcall ATL::CComControl<CTDCCtl,ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>>::CreateControlWindow(
        __int64 a1,
        HWND a2,
        struct tagRECT *a3)
{
  HMENU hMenu; // rbx
  const CHAR *v6; // rsi
  AtlThunkData_t *Data; // rax
  unsigned int v9; // edx
  struct tagRECT *v10; // rax

  hMenu = (HMENU)(a1 + 104);
  if ( !qword_18001B050 )
    qword_18001B050 = 0;
  v6 = (const CHAR *)(unsigned __int16)ATL::AtlModuleRegisterWndClassInfoT<ATL::AtlModuleRegisterWndClassInfoParamA>(
                                         a1,
                                         a2,
                                         &`ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>::GetWndClassInfo'::`2'::wc,
                                         a1 + 168);
  Data = (AtlThunkData_t *)*((_QWORD *)hMenu + 5);
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *((_QWORD *)hMenu + 5) = Data;
    if ( !Data )
    {
      SetLastError(0xEu);
      return 0;
    }
  }
  AtlThunk_InitData(Data, 0, 0);
  if ( !(_WORD)v6 )
    return 0;
  if ( hMenu == (HMENU)-16LL || !hMenu )
  {
    ATL::_AtlRaiseException(0xC0000005, v9);
    JUMPOUT(0x1800045F0LL);
  }
  *((_QWORD *)hMenu + 2) = hMenu;
  *((_DWORD *)hMenu + 6) = GetCurrentThreadId();
  EnterCriticalSection(&CriticalSection);
  *((_QWORD *)hMenu + 4) = qword_18001B750;
  qword_18001B750 = (__int64)(hMenu + 4);
  LeaveCriticalSection(&CriticalSection);
  v10 = &ATL::CWindow::rcDefault;
  if ( a3 )
    v10 = a3;
  return CreateWindowExA(
           0,
           v6,
           0,
           0x56000000u,
           v10->left,
           v10->top,
           v10->right - v10->left,
           v10->bottom - v10->top,
           a2,
           hMenu,
           hInstance,
           0);
}

```

## disassembly

```asm
0x1800044b0  push    rbx
0x1800044b2  push    rbp
0x1800044b3  push    rsi
0x1800044b4  push    rdi
0x1800044b5  push    r14
0x1800044b7  push    r15
0x1800044b9  sub     rsp, 68h
0x1800044bd  xor     r15d, r15d
0x1800044c0  lea     rbx, [rcx+68h]
0x1800044c4  cmp     cs:qword_18001B050, r15
0x1800044cb  mov     rbp, r8
0x1800044ce  mov     r14, rdx
0x1800044d1  jnz     short loc_1800044DA
0x1800044d3  mov     cs:qword_18001B050, r15
0x1800044da  lea     r9, [rbx+40h]
0x1800044de  lea     r8, ?wc@?1??GetWndClassInfo@?$CWindowImpl@VCTDCCtl@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@ATL@@SAAEAU_ATL_WNDCLASSINFOA@3@XZ@4U43@A; ATL::_ATL_WNDCLASSINFOA `ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>::GetWndClassInfo(void)'::`2'::wc
0x1800044e5  call    ??$AtlModuleRegisterWndClassInfoT@VAtlModuleRegisterWndClassInfoParamA@ATL@@@ATL@@YAGPEAU_ATL_BASE_MODULE70@0@PEAU_ATL_WIN_MODULE70@0@PEAU_ATL_WNDCLASSINFOA@0@PEAP6A_JPEAUHWND__@@I_K_J@ZVAtlModuleRegisterWndClassInfoParamA@0@@Z; ATL::AtlModuleRegisterWndClassInfoT<ATL::AtlModuleRegisterWndClassInfoParamA>(ATL::_ATL_BASE_MODULE70 *,ATL::_ATL_WIN_MODULE70 *,ATL::_ATL_WNDCLASSINFOA *,__int64 (**)(HWND__ *,uint,unsigned __int64,__int64),ATL::AtlModuleRegisterWndClassInfoParamA)
0x1800044ea  movzx   esi, ax
0x1800044ed  mov     rax, [rbx+28h]
0x1800044f1  test    rax, rax
0x1800044f4  jnz     short loc_18000451D
0x1800044f6  call    AtlThunk_AllocateData
0x1800044fb  mov     [rbx+28h], rax
0x1800044ff  test    rax, rax
0x180004502  jnz     short loc_18000451D
0x180004504  lea     ecx, [rax+0Eh]; dwErrCode
0x180004507  call    cs:__imp_SetLastError
0x18000450d  mov     rax, r15
0x180004510  add     rsp, 68h
0x180004514  pop     r15
0x180004516  pop     r14
0x180004518  pop     rdi
0x180004519  pop     rsi
0x18000451a  pop     rbp
0x18000451b  pop     rbx
0x18000451c  retn
0x18000451d  xor     r8d, r8d; FirstParameter
0x180004520  xor     edx, edx; Proc
0x180004522  mov     rcx, rax; Thunk
0x180004525  call    AtlThunk_InitData
0x18000452a  test    si, si
0x18000452d  jz      short loc_18000450D
0x18000452f  lea     rdi, [rbx+10h]
0x180004533  test    rdi, rdi
0x180004536  jz      loc_1800045E6
0x18000453c  test    rbx, rbx
0x18000453f  jz      loc_1800045E6
0x180004545  mov     [rdi], rbx
0x180004548  call    cs:__imp_GetCurrentThreadId
0x18000454e  lea     rcx, CriticalSection; lpCriticalSection
0x180004555  mov     [rdi+8], eax
0x180004558  call    cs:__imp_EnterCriticalSection
0x18000455e  mov     rax, cs:qword_18001B750
0x180004565  lea     rcx, CriticalSection; lpCriticalSection
0x18000456c  mov     [rdi+10h], rax
0x180004570  mov     cs:qword_18001B750, rdi
0x180004577  call    cs:__imp_LeaveCriticalSection
0x18000457d  mov     r8, cs:hInstance
0x180004584  lea     rax, ?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x18000458b  mov     [rsp+98h+lpParam], r15; lpParam
0x180004590  test    rbp, rbp
0x180004593  mov     [rsp+98h+hInstance], r8; hInstance
0x180004598  mov     rdx, rsi; lpClassName
0x18000459b  cmovnz  rax, rbp
0x18000459f  mov     [rsp+98h+hMenu], rbx; hMenu
0x1800045a4  mov     [rsp+98h+hWndParent], r14; hWndParent
0x1800045a9  xor     r8d, r8d; lpWindowName
0x1800045ac  mov     r10d, [rax+4]
0x1800045b0  mov     r11d, [rax]
0x1800045b3  mov     r9d, [rax+0Ch]
0x1800045b7  mov     ecx, [rax+8]
0x1800045ba  sub     r9d, r10d
0x1800045bd  mov     [rsp+98h+nHeight], r9d; nHeight
0x1800045c2  sub     ecx, r11d
0x1800045c5  mov     [rsp+98h+nWidth], ecx; nWidth
0x1800045c9  mov     r9d, 56000000h; dwStyle
0x1800045cf  mov     [rsp+98h+Y], r10d; Y
0x1800045d4  xor     ecx, ecx; dwExStyle
0x1800045d6  mov     [rsp+98h+X], r11d; X
0x1800045db  call    cs:__imp_CreateWindowExA
0x1800045e1  jmp     loc_180004510
0x1800045e6  mov     ecx, 0C0000005h; unsigned int
0x1800045eb  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
