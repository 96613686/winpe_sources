# CEventUI::UploadDlgProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x18000884c`
- end: `0x180008993`
- name: `?UploadDlgProc@CEventUI@@AEAAJPEAUHWND__@@I_K_J2@Z`
- size: `327`
- prototype: `__int64 __fastcall(DWORD_PTR dwRefData, HWND hWnd, unsigned int, unsigned __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007c90`

## callees

- `0x1800045cc`
- `0x18000884c`
- `0x18000c8a0`
- `0x180018010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800088c9`
- `KERNEL32!SetEvent` at `0x1800088ea`
- `KERNEL32!SetEvent` at `0x1800088c9`
- `KERNEL32!SetEvent` at `0x1800088ea`
- `COMCTL32!__imp_SetWindowSubclass` at `0x180008942`
- `COMCTL32!__imp_SetWindowSubclass` at `0x180008942`
- `COMCTL32!__imp_RemoveWindowSubclass` at `0x180008890`
- `COMCTL32!__imp_RemoveWindowSubclass` at `0x180008890`
- `USER32!EndDialog` at `0x1800088d4`
- `USER32!EndDialog` at `0x1800088d4`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x1800088fc`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x1800088fc`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008914`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000892c`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008914`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000892c`

## pseudocode

```c
__int64 __fastcall CEventUI::UploadDlgProc(DWORD_PTR dwRefData, HWND hWnd, int a3, __int64 a4)
{
  HICON IconW; // rbx

  if ( a3 )
  {
    if ( a3 == 2 )
    {
      if ( a4 == 1112 )
      {
        CUIDlgBase::UICallback(dwRefData + 8, 14);
        SetEvent(*(HANDLE *)(dwRefData + 952));
        EndDialog(hWnd, 0);
      }
    }
    else if ( a3 == 5 && *(_DWORD *)(dwRefData + 936) )
    {
      RemoveWindowSubclass(hWnd, CEventUI::Static_UploadDialogSubclassProc, 0);
      *(_DWORD *)(dwRefData + 936) = 0;
    }
  }
  else
  {
    *(_QWORD *)(dwRefData + 112) = hWnd;
    SetEvent(*(HANDLE *)(dwRefData + 160));
    IconW = LoadIconW(&_ImageBase, (LPCWSTR)0x194);
    SendMessageW(*(HWND *)(dwRefData + 112), 0x80u, 0, (LPARAM)IconW);
    SendMessageW(*(HWND *)(dwRefData + 112), 0x80u, 1u, (LPARAM)IconW);
    *(_DWORD *)(dwRefData + 936) = SetWindowSubclass(hWnd, CEventUI::Static_UploadDialogSubclassProc, 0, dwRefData);
    (*(void (__fastcall **)(DWORD_PTR, __int64, __int64, __int64))(*(_QWORD *)dwRefData + 24LL))(dwRefData, 3, 1, 100);
    UIAnimateWindowNotificationArea(*(HWND *)(dwRefData + 112), 0);
    CUIDlgBase::UICallback(dwRefData + 8, 19);
  }
  return 0;
}

```

## disassembly

```asm
0x18000884c  mov     [rsp+arg_0], rbx
0x180008851  mov     [rsp+arg_8], rsi
0x180008856  push    rdi
0x180008857  sub     rsp, 30h
0x18000885b  mov     rsi, rdx
0x18000885e  mov     rdi, rcx
0x180008861  test    r8d, r8d
0x180008864  jz      short loc_1800088DF
0x180008866  cmp     r8d, 2
0x18000886a  jz      short loc_1800088A5
0x18000886c  cmp     r8d, 5
0x180008870  jnz     loc_180008981
0x180008876  cmp     dword ptr [rcx+3A8h], 0
0x18000887d  jz      loc_180008981
0x180008883  xor     r8d, r8d; uIdSubclass
0x180008886  lea     rdx, ?Static_UploadDialogSubclassProc@CEventUI@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x18000888d  mov     rcx, rsi; hWnd
0x180008890  call    cs:__imp_RemoveWindowSubclass
0x180008896  mov     dword ptr [rdi+3A8h], 0
0x1800088a0  jmp     loc_180008981
0x1800088a5  cmp     r9, 458h
0x1800088ac  jnz     loc_180008981
0x1800088b2  xor     r8d, r8d
0x1800088b5  add     rcx, 8
0x1800088b9  lea     edx, [r8+0Eh]
0x1800088bd  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x1800088c2  mov     rcx, [rdi+3B8h]; hEvent
0x1800088c9  call    cs:__imp_SetEvent
0x1800088cf  xor     edx, edx; nResult
0x1800088d1  mov     rcx, rsi; hDlg
0x1800088d4  call    cs:__imp_EndDialog
0x1800088da  jmp     loc_180008981
0x1800088df  mov     [rcx+70h], rsi
0x1800088e3  mov     rcx, [rcx+0A0h]; hEvent
0x1800088ea  call    cs:__imp_SetEvent
0x1800088f0  mov     edx, 194h; lpIconName
0x1800088f5  lea     rcx, __ImageBase; hInstance
0x1800088fc  call    cs:__imp_LoadIconW
0x180008902  mov     rcx, [rdi+70h]; hWnd
0x180008906  xor     r8d, r8d; wParam
0x180008909  mov     r9, rax; lParam
0x18000890c  mov     edx, 80h; Msg
0x180008911  mov     rbx, rax
0x180008914  call    cs:__imp_SendMessageW
0x18000891a  mov     rcx, [rdi+70h]; hWnd
0x18000891e  mov     r9, rbx; lParam
0x180008921  mov     ebx, 1
0x180008926  mov     r8d, ebx; wParam
0x180008929  lea     edx, [rbx+7Fh]; Msg
0x18000892c  call    cs:__imp_SendMessageW
0x180008932  mov     r9, rdi; dwRefData
0x180008935  lea     rdx, ?Static_UploadDialogSubclassProc@CEventUI@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x18000893c  xor     r8d, r8d; uIdSubclass
0x18000893f  mov     rcx, rsi; hWnd
0x180008942  call    cs:__imp_SetWindowSubclass
0x180008948  mov     [rdi+3A8h], eax
0x18000894e  lea     r9d, [rbx+63h]
0x180008952  mov     rax, [rdi]
0x180008955  mov     r8d, ebx
0x180008958  lea     edx, [rbx+2]
0x18000895b  mov     rcx, rdi
0x18000895e  mov     rax, [rax+18h]
0x180008962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008967  mov     rcx, [rdi+70h]; hWnd
0x18000896b  xor     edx, edx; int
0x18000896d  call    ?UIAnimateWindowNotificationArea@@YAJPEAUHWND__@@H@Z; UIAnimateWindowNotificationArea(HWND__ *,int)
0x180008972  lea     rcx, [rdi+8]
0x180008976  mov     r8, rsi
0x180008979  lea     edx, [rbx+12h]
0x18000897c  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x180008981  mov     rbx, [rsp+38h+arg_0]
0x180008986  xor     eax, eax
0x180008988  mov     rsi, [rsp+38h+arg_8]
0x18000898d  add     rsp, 30h
0x180008991  pop     rdi
0x180008992  retn
```
