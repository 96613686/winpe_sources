# CFciPropertiesShellExt::OnFciPropsInitDone(HWND__ *,unsigned __int64,__int64)

- ea: `0x18000baf0`
- end: `0x18000bc08`
- name: `?OnFciPropsInitDone@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@_K_J@Z`
- size: `280`
- prototype: `__int64 __fastcall(CFciPropertiesShellExt *this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180007290`

## callees

- `0x18000baf0`
- `0x18000e87c`
- `0x18000f910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000bb16`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000bb16`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18000bb2c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18000bb2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb3e`
- `USER32!GetDlgItem` at `0x18000bbad`
- `USER32!GetDlgItem` at `0x18000bbad`
- `USER32!SendMessageW` at `0x18000bbcb`
- `USER32!SendMessageW` at `0x18000bbcb`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::OnFciPropsInitDone(CFciPropertiesShellExt *this, HWND a2)
{
  void *v4; // rcx
  void *v5; // rcx
  int v6; // esi
  unsigned int v7; // ebp
  HWND DlgItem; // rax

  v4 = (void *)*((_QWORD *)this + 17);
  if ( !v4 )
    return 0;
  if ( WaitForSingleObject(v4, 0xFFFFFFFF) )
    TerminateThread(*((HANDLE *)this + 17), 0x80004005);
  v5 = (void *)*((_QWORD *)this + 17);
  if ( v5 )
    CloseHandle(v5);
  *((_QWORD *)this + 17) = 0;
  if ( *((int *)this + 42) >= 0 )
  {
    CFciPropertiesShellExt::ShowProperties(this, a2);
  }
  else
  {
    v6 = 2;
    if ( (*((_DWORD *)this + 43) & 1) != 0 )
    {
      v7 = 9321;
    }
    else if ( (*((_DWORD *)this + 43) & 2) != 0 )
    {
      v7 = 9341;
      v6 = 0;
    }
    else
    {
      v7 = 9318;
    }
    DlgItem = GetDlgItem(a2, 1001);
    *((_DWORD *)this + 55) = 9330;
    SendMessageW(DlgItem, 0x1054u, 0, 0);
    CFciPropertiesShellExt::UpdateInformationControls(a2, v7, v6);
  }
  return 1;
}

```

## disassembly

```asm
0x18000baf0  push    rbx
0x18000baf2  push    rbp
0x18000baf3  push    rsi
0x18000baf4  push    rdi
0x18000baf5  push    r14
0x18000baf7  push    r15
0x18000baf9  sub     rsp, 38h
0x18000bafd  mov     rbx, rcx
0x18000bb00  mov     r14, rdx
0x18000bb03  mov     rcx, [rcx+88h]; hHandle
0x18000bb0a  test    rcx, rcx
0x18000bb0d  jz      loc_18000BBF9
0x18000bb13  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000bb16  call    cs:__imp_WaitForSingleObject
0x18000bb1c  test    eax, eax
0x18000bb1e  jz      short loc_18000BB32
0x18000bb20  mov     rcx, [rbx+88h]; hThread
0x18000bb27  mov     edx, 80004005h; dwExitCode
0x18000bb2c  call    cs:__imp_TerminateThread
0x18000bb32  mov     rcx, [rbx+88h]; hObject
0x18000bb39  test    rcx, rcx
0x18000bb3c  jz      short loc_18000BB44
0x18000bb3e  call    cs:__imp_CloseHandle
0x18000bb44  mov     qword ptr [rbx+88h], 0
0x18000bb4f  mov     eax, [rbx+0A8h]
0x18000bb55  test    eax, eax
0x18000bb57  jns     loc_18000BBE7
0x18000bb5d  mov     eax, [rbx+0ACh]
0x18000bb63  mov     esi, 2
0x18000bb68  test    al, 1
0x18000bb6a  jz      short loc_18000BB84
0x18000bb6c  mov     al, [rbx+38h]
0x18000bb6f  mov     ebp, 2469h
0x18000bb74  neg     al
0x18000bb76  mov     r15d, 7F03h
0x18000bb7c  sbb     edi, edi
0x18000bb7e  not     edi
0x18000bb80  and     edi, esi
0x18000bb82  jmp     short loc_18000BBA5
0x18000bb84  mov     eax, [rbx+0ACh]
0x18000bb8a  xor     edi, edi
0x18000bb8c  mov     r15d, 7F01h
0x18000bb92  test    sil, al
0x18000bb95  jz      short loc_18000BBA0
0x18000bb97  mov     ebp, 247Dh
0x18000bb9c  xor     esi, esi
0x18000bb9e  jmp     short loc_18000BBA5
0x18000bba0  mov     ebp, 2466h
0x18000bba5  mov     edx, 3E9h; nIDDlgItem
0x18000bbaa  mov     rcx, r14; hDlg
0x18000bbad  call    cs:__imp_GetDlgItem
0x18000bbb3  xor     r9d, r9d; lParam
0x18000bbb6  mov     dword ptr [rbx+0DCh], 2472h
0x18000bbc0  mov     rcx, rax; hWnd
0x18000bbc3  xor     r8d, r8d; wParam
0x18000bbc6  mov     edx, 1054h; Msg
0x18000bbcb  call    cs:__imp_SendMessageW
0x18000bbd1  mov     r9d, edi
0x18000bbd4  mov     [rsp+68h+var_48], esi; int
0x18000bbd8  mov     r8, r15
0x18000bbdb  mov     edx, ebp; unsigned int
0x18000bbdd  mov     rcx, r14; hDlg
0x18000bbe0  call    ?UpdateInformationControls@CFciPropertiesShellExt@@CAXPEAUHWND__@@HPEBGW4ControlState@?$CFciDialogBase@VCFciPropertiesShellExt@@@@2@Z; CFciPropertiesShellExt::UpdateInformationControls(HWND__ *,int,ushort const *,CFciDialogBase<CFciPropertiesShellExt>::ControlState,CFciDialogBase<CFciPropertiesShellExt>::ControlState)
0x18000bbe5  jmp     short loc_18000BBF2
0x18000bbe7  mov     rdx, r14; hDlg
0x18000bbea  mov     rcx, rbx; this
0x18000bbed  call    ?ShowProperties@CFciPropertiesShellExt@@AEAAXPEAUHWND__@@@Z; CFciPropertiesShellExt::ShowProperties(HWND__ *)
0x18000bbf2  mov     eax, 1
0x18000bbf7  jmp     short loc_18000BBFB
0x18000bbf9  xor     eax, eax
0x18000bbfb  add     rsp, 38h
0x18000bbff  pop     r15
0x18000bc01  pop     r14
0x18000bc03  pop     rdi
0x18000bc04  pop     rsi
0x18000bc05  pop     rbp
0x18000bc06  pop     rbx
0x18000bc07  retn
```
