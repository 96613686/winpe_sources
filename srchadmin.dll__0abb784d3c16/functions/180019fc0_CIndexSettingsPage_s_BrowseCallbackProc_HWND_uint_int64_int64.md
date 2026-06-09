# CIndexSettingsPage::s_BrowseCallbackProc(HWND__ *,uint,__int64,__int64)

- ea: `0x180019fc0`
- end: `0x18001a0a4`
- name: `?s_BrowseCallbackProc@CIndexSettingsPage@@CAHPEAUHWND__@@I_J1@Z`
- size: `228`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800038ac`
- `0x180018bc0`
- `0x180019fc0`
- `0x180032010`

## import_xrefs

- `SHLWAPI!PathStripToRootW` at `0x18001a076`
- `SHLWAPI!PathStripToRootW` at `0x18001a076`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18001a069`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18001a091`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18001a069`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18001a091`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CIndexSettingsPage::s_BrowseCallbackProc(
        HWND hWnd,
        int a2,
        int (__fastcall ***a3)(_QWORD, GUID *, __int64 *),
        WCHAR *a4)
{
  int v6; // edx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v10; // [rsp+20h] [rbp-18h] BYREF
  __int64 v11[2]; // [rsp+28h] [rbp-10h] BYREF

  v6 = a2 - 1;
  if ( v6 )
  {
    if ( v6 == 4 && a3 )
    {
      v11[0] = 0;
      if ( (**a3)(a3, &GUID_c0a651f5_b48b_11d2_b5ed_006097c686f6, v11) >= 0 )
      {
        v10 = 0;
        if ( (int)ATL::CComCreator<ATL::CComObject<CFolderFilter>>::CreateInstance(v8, v7, &v10) >= 0 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11[0] + 24LL))(v11[0], v10);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v11);
    }
  }
  else if ( a4 && !(unsigned int)SendMessageW(hWnd, 0x467u, 1u, (LPARAM)a4) && PathStripToRootW(a4) )
  {
    SendMessageW(hWnd, 0x467u, 1u, (LPARAM)a4);
  }
  return 0;
}

```

## disassembly

```asm
0x180019fc0  mov     [rsp+arg_0], rbx
0x180019fc5  push    rdi
0x180019fc6  sub     rsp, 30h
0x180019fca  mov     rbx, r9
0x180019fcd  mov     r9, r8
0x180019fd0  mov     rdi, rcx
0x180019fd3  sub     edx, 1
0x180019fd6  jz      short loc_18001A056
0x180019fd8  cmp     edx, 4
0x180019fdb  jnz     loc_18001A097
0x180019fe1  test    r8, r8
0x180019fe4  jz      loc_18001A097
0x180019fea  mov     [rsp+38h+var_10], 0
0x180019ff3  mov     rax, [r8]
0x180019ff6  lea     r8, [rsp+38h+var_10]
0x180019ffb  lea     rdx, _GUID_c0a651f5_b48b_11d2_b5ed_006097c686f6
0x18001a002  mov     rcx, r9
0x18001a005  mov     rax, [rax]
0x18001a008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a00d  test    eax, eax
0x18001a00f  js      short loc_18001A04A
0x18001a011  mov     [rsp+38h+var_18], 0
0x18001a01a  lea     r8, [rsp+38h+var_18]
0x18001a01f  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCFolderFilter@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CFolderFilter>>::CreateInstance(void *,_GUID const &,void * *)
0x18001a024  test    eax, eax
0x18001a026  js      short loc_18001A03F
0x18001a028  mov     rcx, [rsp+38h+var_10]
0x18001a02d  mov     rax, [rcx]
0x18001a030  mov     rdx, [rsp+38h+var_18]
0x18001a035  mov     rax, [rax+18h]
0x18001a039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a03e  nop
0x18001a03f  lea     rcx, [rsp+38h+var_18]
0x18001a044  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001a049  nop
0x18001a04a  lea     rcx, [rsp+38h+var_10]
0x18001a04f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001a054  jmp     short loc_18001A097
0x18001a056  test    rbx, rbx
0x18001a059  jz      short loc_18001A097
0x18001a05b  mov     r9, rbx; lParam
0x18001a05e  mov     edx, 467h; Msg
0x18001a063  mov     r8d, 1; wParam
0x18001a069  call    cs:__imp_SendMessageW
0x18001a06f  test    eax, eax
0x18001a071  jnz     short loc_18001A097
0x18001a073  mov     rcx, rbx; pszPath
0x18001a076  call    cs:__imp_PathStripToRootW
0x18001a07c  test    eax, eax
0x18001a07e  jz      short loc_18001A097
0x18001a080  mov     r9, rbx; lParam
0x18001a083  mov     edx, 467h; Msg
0x18001a088  mov     r8d, 1; wParam
0x18001a08e  mov     rcx, rdi; hWnd
0x18001a091  call    cs:__imp_SendMessageW
0x18001a097  xor     eax, eax
0x18001a099  mov     rbx, [rsp+38h+arg_0]
0x18001a09e  add     rsp, 30h
0x18001a0a2  pop     rdi
0x18001a0a3  retn
```
