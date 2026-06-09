# CFciPropertiesShellExt::OnSetActive(HWND__ *,_PSHNOTIFY const *)

- ea: `0x18000c398`
- end: `0x18000c49b`
- name: `?OnSetActive@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@PEBU_PSHNOTIFY@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(CFciPropertiesShellExt *__hidden this, HWND, const struct _PSHNOTIFY *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007290`

## callees

- `0x18000c398`
- `0x18000ca10`
- `0x18000f294`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c452`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c452`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18000c3d4`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18000c3f5`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18000c3d4`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18000c3f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c46c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c46c`
- `USER32!GetDlgItem` at `0x18000c422`
- `USER32!GetDlgItem` at `0x18000c422`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::OnSetActive(
        CFciPropertiesShellExt *this,
        HWND a2,
        const struct _PSHNOTIFY *a3)
{
  _WORD *v5; // rdi
  unsigned __int64 i; // rdi
  HWND DlgItem; // rax
  HANDLE EventW; // rdi
  void *v9; // rcx

  if ( !*((_BYTE *)this + 216) )
  {
    v5 = (_WORD *)((char *)this + 248);
    *((_BYTE *)this + 216) = 1;
    if ( !GetLocaleInfoEx(0, 0x20u, (LPWSTR)this + 124, 100) )
      *v5 = 0;
    if ( !GetLocaleInfoEx(0, 0x1003u, (LPWSTR)this + 224, 100) )
      *((_WORD *)this + 224) = 0;
    for ( i = 0; i < 8; ++i )
    {
      if ( *(&CFciPropertiesShellExt::s_valueControls + 6 * i + 2) )
      {
        DlgItem = GetDlgItem(a2, *((_DWORD *)&CFciPropertiesShellExt::s_valueControls + 12 * i + 1));
        ((void (__fastcall *)(char *, HWND))*(&funcs_18000C438 + 6 * i))(
          (char *)this + *((int *)&CFciPropertiesShellExt::s_valueControls + 12 * i + 6),
          DlgItem);
      }
    }
    EventW = CreateEventW(0, 1, 0, 0);
    if ( EventW )
    {
      v9 = (void *)*((_QWORD *)this + 19);
      if ( v9 )
        CloseHandle(v9);
      *((_QWORD *)this + 19) = EventW;
      CFciPropertiesShellExt::StartBackgroundThread(
        this,
        (LPTHREAD_START_ROUTINE)CFciPropertiesShellExt::ThreadProcStatic<{private: void CFciPropertiesShellExt::InitializeThreadProc(void),0},32768>,
        a2);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000c398  push    rbx
0x18000c39a  push    rbp
0x18000c39b  push    rsi
0x18000c39c  push    rdi
0x18000c39d  push    r15
0x18000c39f  sub     rsp, 20h
0x18000c3a3  cmp     byte ptr [rcx+0D8h], 0
0x18000c3aa  mov     rbp, rdx
0x18000c3ad  mov     rbx, rcx
0x18000c3b0  jnz     loc_18000C48B
0x18000c3b6  lea     rdi, [rcx+0F8h]
0x18000c3bd  mov     byte ptr [rcx+0D8h], 1
0x18000c3c4  mov     esi, 64h ; 'd'
0x18000c3c9  mov     r8, rdi; lpLCData
0x18000c3cc  mov     r9d, esi; cchData
0x18000c3cf  xor     ecx, ecx; lpLocaleName
0x18000c3d1  lea     edx, [rsi-44h]; LCType
0x18000c3d4  call    cs:__imp_GetLocaleInfoEx
0x18000c3da  test    eax, eax
0x18000c3dc  jnz     short loc_18000C3E1
0x18000c3de  mov     [rdi], ax
0x18000c3e1  lea     rdi, [rbx+1C0h]
0x18000c3e8  mov     r9d, esi; cchData
0x18000c3eb  mov     r8, rdi; lpLCData
0x18000c3ee  mov     edx, 1003h; LCType
0x18000c3f3  xor     ecx, ecx; lpLocaleName
0x18000c3f5  call    cs:__imp_GetLocaleInfoEx
0x18000c3fb  test    eax, eax
0x18000c3fd  jnz     short loc_18000C402
0x18000c3ff  mov     [rdi], ax
0x18000c402  xor     edi, edi
0x18000c404  lea     r15, ?s_valueControls@CFciPropertiesShellExt@@0PAUValueControlInfo@1@A; CFciPropertiesShellExt::ValueControlInfo near * CFciPropertiesShellExt::s_valueControls
0x18000c40b  lea     rsi, [rdi+rdi*2]
0x18000c40f  add     rsi, rsi
0x18000c412  cmp     qword ptr [r15+rsi*8+10h], 0
0x18000c418  jz      short loc_18000C43D
0x18000c41a  mov     edx, [r15+rsi*8+4]; nIDDlgItem
0x18000c41f  mov     rcx, rbp; hDlg
0x18000c422  call    cs:__imp_GetDlgItem
0x18000c428  movsxd  rcx, dword ptr [r15+rsi*8+18h]
0x18000c42d  mov     rdx, rax; HWND
0x18000c430  mov     rax, (funcs_18000C438 - 18002B0A0h)[r15+rsi*8]
0x18000c435  add     rcx, rbx; this
0x18000c438  call    _guard_dispatch_icall$thunk$10345483385596137414; CFciPropertiesShellExt::PostCreateSingleSelection(HWND__ *) ...
0x18000c43d  inc     rdi
0x18000c440  cmp     rdi, 8
0x18000c444  jb      short loc_18000C40B
0x18000c446  xor     r9d, r9d; lpName
0x18000c449  xor     r8d, r8d; bInitialState
0x18000c44c  xor     ecx, ecx; lpEventAttributes
0x18000c44e  lea     edx, [r9+1]; bManualReset
0x18000c452  call    cs:__imp_CreateEventW
0x18000c458  mov     rdi, rax
0x18000c45b  test    rax, rax
0x18000c45e  jz      short loc_18000C48B
0x18000c460  mov     rcx, [rbx+98h]; hObject
0x18000c467  test    rcx, rcx
0x18000c46a  jz      short loc_18000C472
0x18000c46c  call    cs:__imp_CloseHandle
0x18000c472  mov     r8, rbp; HWND
0x18000c475  mov     [rbx+98h], rdi
0x18000c47c  lea     rdx, ??$ThreadProcStatic@$H?InitializeThreadProc@CFciPropertiesShellExt@@AEAAXXZA@$0IAAA@@CFciPropertiesShellExt@@CAKPEAX@Z; lpStartAddress
0x18000c483  mov     rcx, rbx; this
0x18000c486  call    ?StartBackgroundThread@CFciPropertiesShellExt@@AEAAJP6AKPEAX@ZPEAUHWND__@@@Z; CFciPropertiesShellExt::StartBackgroundThread(ulong (*)(void *),HWND__ *)
0x18000c48b  mov     eax, 1
0x18000c490  add     rsp, 20h
0x18000c494  pop     r15
0x18000c496  pop     rdi
0x18000c497  pop     rsi
0x18000c498  pop     rbp
0x18000c499  pop     rbx
0x18000c49a  retn
```
