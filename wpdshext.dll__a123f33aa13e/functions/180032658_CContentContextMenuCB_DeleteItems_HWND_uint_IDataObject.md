# CContentContextMenuCB::_DeleteItems(HWND__ *,uint,IDataObject *)

- ea: `0x180032658`
- end: `0x180032913`
- name: `?_DeleteItems@CContentContextMenuCB@@AEAAJPEAUHWND__@@IPEAUIDataObject@@@Z`
- size: `699`
- prototype: `int(CContentContextMenuCB *__hidden this, HWND, unsigned int, struct IDataObject *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180042340`

## callees

- `0x180003f90`
- `0x1800082e0`
- `0x18000d610`
- `0x18002ff5c`
- `0x180032658`
- `0x18003291c`
- `0x180035590`
- `0x1800361ba`
- `0x180041dcc`
- `0x18005fb88`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180032843`
- `KERNEL32!GetLastError` at `0x180032843`
- `KERNEL32!CloseHandle` at `0x180032839`
- `KERNEL32!CloseHandle` at `0x180032839`
- `KERNEL32!GlobalFree` at `0x1800328bb`
- `KERNEL32!GlobalFree` at `0x1800328bb`
- `KERNEL32!CreateThread` at `0x18003281c`
- `KERNEL32!CreateThread` at `0x18003281c`
- `KERNEL32!WaitForSingleObject` at `0x180032830`
- `KERNEL32!WaitForSingleObject` at `0x180032830`
- `SHLWAPI!__imp_SHCreateThread` at `0x180032872`
- `SHLWAPI!__imp_SHCreateThread` at `0x180032872`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800327aa`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800327aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CContentContextMenuCB::_DeleteItems(
        struct CContentFolder **this,
        HWND a2,
        unsigned int a3,
        struct IDataObject *a4)
{
  int v7; // eax
  const struct std::nothrow_t *v8; // rdx
  CContentFolder *v9; // rcx
  unsigned int v10; // ebx
  struct _IDA *v11; // rdi
  __int64 v12; // r9
  __int64 v13; // r8
  const struct CONTENTITEM *v14; // rsi
  CContentFolder *v15; // rcx
  unsigned int v16; // r9d
  void *v17; // rax
  CDeleteThreadData *v18; // rsi
  HANDLE Thread; // rax
  void *v20; // rbx
  unsigned int v21; // edx
  signed int LastError; // eax
  unsigned int v23; // edx
  unsigned __int16 *lpThreadId; // [rsp+28h] [rbp-270h]
  HGLOBAL hMem; // [rsp+30h] [rbp-268h] BYREF
  unsigned __int16 v27; // [rsp+40h] [rbp-258h] BYREF
  _BYTE v28[526]; // [rsp+42h] [rbp-256h] BYREF

  hMem = 0;
  v7 = DataObj_CopyHIDA(a4, (struct _IDA **)&hMem);
  v10 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        402,
        WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        (unsigned int)v7);
    v11 = (struct _IDA *)hMem;
    goto LABEL_33;
  }
  v11 = (struct _IDA *)hMem;
  if ( !hMem )
  {
    v10 = -2147467259;
    goto LABEL_36;
  }
  if ( !*(_DWORD *)hMem )
  {
    v10 = -2147418113;
    goto LABEL_33;
  }
  if ( (a3 & 0x400) == 0 )
  {
    if ( *(_DWORD *)hMem <= 1u )
    {
      v14 = CContentFolder::_IsValid(v9, (const struct _ITEMIDLIST *)((char *)hMem + *((unsigned int *)hMem + 2)));
      if ( !v14 )
      {
        v10 = -2147467259;
        goto LABEL_33;
      }
      v27 = 0;
      memset_0(v28, 0, 0x206u);
      CContentFolder::_DisplayName(v15, v14, &v27, v16);
      v12 = ((*(_DWORD *)((_BYTE *)v14 + 10) & 2) != 0) + 364LL;
      v13 = ((*(_DWORD *)((_BYTE *)v14 + 10) & 2) != 0) + 367LL;
      lpThreadId = &v27;
    }
    else
    {
      LODWORD(lpThreadId) = *(_DWORD *)hMem;
      v12 = 366;
      v13 = 369;
    }
    if ( ShellMessageBoxW(g_hInst, a2, (LPCWSTR)v13, (LPCWSTR)v12, 0x10034u, lpThreadId) != 6 )
    {
      v10 = 0;
      goto LABEL_33;
    }
  }
  v17 = operator new(0x120u, v8);
  hMem = v17;
  if ( v17 )
    v18 = CDeleteThreadData::CDeleteThreadData((CDeleteThreadData *)v17, a2, a3, this[4], v11);
  else
    v18 = 0;
  if ( !v18 )
  {
    v10 = -2147024882;
    goto LABEL_33;
  }
  v11 = 0;
  if ( (a3 & 0x100) != 0 )
  {
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CContentContextMenuCB::s_DoDeleteThreadProc, v18, 0, 0);
    v20 = Thread;
    if ( Thread )
    {
      WaitForSingleObject(Thread, 0xFFFFFFFF);
      CloseHandle(v20);
      v10 = *(_DWORD *)v18;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    CDeleteThreadData::`scalar deleting destructor'(v18, v21);
LABEL_35:
    if ( (v10 & 0x80000000) == 0 )
      return v10;
    goto LABEL_36;
  }
  if ( SHCreateThread((LPTHREAD_START_ROUTINE)CContentContextMenuCB::s_DoDeleteThreadProc, v18, 0, 0) )
    return v10;
  CDeleteThreadData::`scalar deleting destructor'(v18, v23);
  v10 = -2147467259;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 403, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, 2147500037LL);
LABEL_33:
    if ( v11 )
      GlobalFree(v11);
    goto LABEL_35;
  }
LABEL_36:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 404, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180032658  push    rbx
0x18003265a  push    rbp
0x18003265b  push    rsi
0x18003265c  push    rdi
0x18003265d  push    r13
0x18003265f  push    r14
0x180032661  push    r15
0x180032663  sub     rsp, 260h
0x18003266a  mov     rax, cs:__security_cookie
0x180032671  xor     rax, rsp
0x180032674  mov     [rsp+298h+var_48], rax
0x18003267c  mov     ebp, r8d
0x18003267f  mov     r14, rdx
0x180032682  mov     r15, rcx
0x180032685  mov     [rsp+298h+hMem], 0
0x18003268e  lea     rdx, [rsp+298h+hMem]; struct _IDA **
0x180032693  mov     rcx, r9; struct IDataObject *
0x180032696  call    ?DataObj_CopyHIDA@@YAJPEAUIDataObject@@PEAPEAU_IDA@@@Z; DataObj_CopyHIDA(IDataObject *,_IDA * *)
0x18003269b  mov     ebx, eax
0x18003269d  lea     r13, WPP_GLOBAL_Control
0x1800326a4  test    eax, eax
0x1800326a6  jns     short loc_1800326DC
0x1800326a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326af  cmp     rcx, r13
0x1800326b2  jz      short loc_1800326D2
0x1800326b4  test    byte ptr [rcx+1Ch], 2
0x1800326b8  jz      short loc_1800326D2
0x1800326ba  mov     edx, 192h
0x1800326bf  mov     r9d, eax
0x1800326c2  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800326c9  mov     rcx, [rcx+10h]
0x1800326cd  call    WPP_SF_d
0x1800326d2  mov     rdi, [rsp+298h+hMem]
0x1800326d7  jmp     loc_1800328B3
0x1800326dc  mov     rdi, [rsp+298h+hMem]
0x1800326e1  test    rdi, rdi
0x1800326e4  jnz     short loc_1800326F0
0x1800326e6  mov     ebx, 80004005h
0x1800326eb  jmp     loc_1800328C5
0x1800326f0  mov     eax, [rdi]
0x1800326f2  test    eax, eax
0x1800326f4  jnz     short loc_180032700
0x1800326f6  mov     ebx, 8000FFFFh
0x1800326fb  jmp     loc_1800328B3
0x180032700  bt      ebp, 0Ah
0x180032704  jb      loc_1800327BC
0x18003270a  cmp     eax, 1
0x18003270d  jbe     short loc_18003271F
0x18003270f  mov     dword ptr [rsp+298h+lpThreadId], eax
0x180032713  mov     r9d, 16Eh
0x180032719  lea     r8d, [r9+3]
0x18003271d  jmp     short loc_180032798
0x18003271f  jnz     loc_1800327B5
0x180032725  mov     edx, [rdi+8]
0x180032728  add     rdx, rdi; struct _ITEMIDLIST *
0x18003272b  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180032730  mov     rsi, rax
0x180032733  test    rax, rax
0x180032736  jnz     short loc_180032742
0x180032738  mov     ebx, 80004005h
0x18003273d  jmp     loc_1800328B3
0x180032742  xor     eax, eax
0x180032744  mov     [rsp+298h+var_258], ax
0x180032749  xor     edx, edx; Val
0x18003274b  mov     r8d, 206h; Size
0x180032751  lea     rcx, [rsp+298h+var_256]; void *
0x180032756  call    memset_0
0x18003275b  lea     r8, [rsp+298h+var_258]; unsigned __int16 *
0x180032760  mov     rdx, rsi; struct CONTENTITEM *
0x180032763  call    ?_DisplayName@CContentFolder@@AEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z; CContentFolder::_DisplayName(CONTENTITEM const *,ushort *,uint)
0x180032768  mov     ecx, [rsi+0Ah]
0x18003276b  and     ecx, 2
0x18003276e  mov     eax, ecx
0x180032770  neg     eax
0x180032772  sbb     r9, r9
0x180032775  neg     r9
0x180032778  add     r9, 16Ch; lpcTitle
0x18003277f  neg     ecx
0x180032781  sbb     r8, r8
0x180032784  neg     r8
0x180032787  add     r8, 16Fh; lpcText
0x18003278e  lea     rax, [rsp+298h+var_258]
0x180032793  mov     [rsp+298h+lpThreadId], rax
0x180032798  mov     [rsp+298h+fuStyle], 10034h; fuStyle
0x1800327a0  mov     rdx, r14; hWnd
0x1800327a3  mov     rcx, cs:g_hInst; hAppInst
0x1800327aa  call    cs:__imp_ShellMessageBoxW
0x1800327b0  cmp     eax, 6
0x1800327b3  jz      short loc_1800327BC
0x1800327b5  xor     ebx, ebx
0x1800327b7  jmp     loc_1800328B3
0x1800327bc  mov     ecx, 120h; unsigned __int64
0x1800327c1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800327c6  mov     [rsp+298h+hMem], rax
0x1800327cb  test    rax, rax
0x1800327ce  jz      short loc_1800327EC
0x1800327d0  mov     qword ptr [rsp+298h+fuStyle], rdi; struct _IDA *
0x1800327d5  mov     r9, [r15+20h]; struct CContentFolder *
0x1800327d9  mov     r8d, ebp; unsigned int
0x1800327dc  mov     rdx, r14; HWND
0x1800327df  mov     rcx, rax; this
0x1800327e2  call    ??0CDeleteThreadData@@QEAA@PEAUHWND__@@IPEAVCContentFolder@@PEAU_IDA@@@Z; CDeleteThreadData::CDeleteThreadData(HWND__ *,uint,CContentFolder *,_IDA *)
0x1800327e7  mov     rsi, rax
0x1800327ea  jmp     short loc_1800327EE
0x1800327ec  xor     esi, esi
0x1800327ee  test    rsi, rsi
0x1800327f1  jnz     short loc_1800327FD
0x1800327f3  mov     ebx, 8007000Eh
0x1800327f8  jmp     loc_1800328B3
0x1800327fd  xor     edi, edi
0x1800327ff  bt      ebp, 8
0x180032803  jnb     short loc_180032862
0x180032805  mov     [rsp+298h+lpThreadId], rdi; lpThreadId
0x18003280a  mov     [rsp+298h+fuStyle], edi; dwCreationFlags
0x18003280e  mov     r9, rsi; lpParameter
0x180032811  lea     r8, ?s_DoDeleteThreadProc@CContentContextMenuCB@@SAKPEAX@Z; lpStartAddress
0x180032818  xor     edx, edx; dwStackSize
0x18003281a  xor     ecx, ecx; lpThreadAttributes
0x18003281c  call    cs:__imp_CreateThread
0x180032822  mov     rbx, rax
0x180032825  test    rax, rax
0x180032828  jz      short loc_180032843
0x18003282a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003282d  mov     rcx, rax; hHandle
0x180032830  call    cs:__imp_WaitForSingleObject
0x180032836  mov     rcx, rbx; hObject
0x180032839  call    cs:__imp_CloseHandle
0x18003283f  mov     ebx, [rsi]
0x180032841  jmp     short loc_180032858
0x180032843  call    cs:__imp_GetLastError
0x180032849  mov     ebx, eax
0x18003284b  test    eax, eax
0x18003284d  jle     short loc_180032858
0x18003284f  movzx   ebx, ax
0x180032852  or      ebx, 80070000h
0x180032858  mov     rcx, rsi; this
0x18003285b  call    ??_GCDeleteThreadData@@QEAAPEAXI@Z; CDeleteThreadData::`scalar deleting destructor'(uint)
0x180032860  jmp     short loc_1800328C1
0x180032862  xor     r9d, r9d; pfnCallback
0x180032865  xor     r8d, r8d; flags
0x180032868  mov     rdx, rsi; pData
0x18003286b  lea     rcx, ?s_DoDeleteThreadProc@CContentContextMenuCB@@SAKPEAX@Z; pfnThreadProc
0x180032872  call    cs:__imp_SHCreateThread
0x180032878  test    eax, eax
0x18003287a  jnz     short loc_1800328EF
0x18003287c  mov     rcx, rsi; this
0x18003287f  call    ??_GCDeleteThreadData@@QEAAPEAXI@Z; CDeleteThreadData::`scalar deleting destructor'(uint)
0x180032884  mov     ebx, 80004005h
0x180032889  mov     rcx, cs:WPP_GLOBAL_Control
0x180032890  cmp     rcx, r13
0x180032893  jz      short loc_1800328EF
0x180032895  test    byte ptr [rcx+1Ch], 2
0x180032899  jz      short loc_1800328C5
0x18003289b  mov     edx, 193h
0x1800328a0  mov     r9d, ebx
0x1800328a3  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800328aa  mov     rcx, [rcx+10h]
0x1800328ae  call    WPP_SF_d
0x1800328b3  test    rdi, rdi
0x1800328b6  jz      short loc_1800328C1
0x1800328b8  mov     rcx, rdi; hMem
0x1800328bb  call    cs:__imp_GlobalFree
0x1800328c1  test    ebx, ebx
0x1800328c3  jns     short loc_1800328EF
0x1800328c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328cc  cmp     rcx, r13
0x1800328cf  jz      short loc_1800328EF
0x1800328d1  test    byte ptr [rcx+1Ch], 2
0x1800328d5  jz      short loc_1800328EF
0x1800328d7  mov     edx, 194h
0x1800328dc  mov     r9d, ebx
0x1800328df  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800328e6  mov     rcx, [rcx+10h]
0x1800328ea  call    WPP_SF_d
0x1800328ef  mov     eax, ebx
0x1800328f1  mov     rcx, [rsp+298h+var_48]
0x1800328f9  xor     rcx, rsp; StackCookie
0x1800328fc  call    __security_check_cookie
0x180032901  add     rsp, 260h
0x180032908  pop     r15
0x18003290a  pop     r14
0x18003290c  pop     r13
0x18003290e  pop     rdi
0x18003290f  pop     rsi
0x180032910  pop     rbp
0x180032911  pop     rbx
0x180032912  retn
```
