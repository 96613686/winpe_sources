# CShellNotification::Create(HINSTANCE__ *,_NOTIFYICONDATAW *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64,void *),void *)

- ea: `0x18001405c`
- end: `0x180014394`
- name: `?Create@CShellNotification@@QEAAJPEAUHINSTANCE__@@PEAU_NOTIFYICONDATAW@@P6A_JPEAUHWND__@@I_K_JPEAX@Z5@Z`
- size: `824`
- prototype: `__int64 __fastcall(CShellNotification *__hidden this, HINSTANCE, struct _NOTIFYICONDATAW *, __int64 (*)(HWND, unsigned int, unsigned __int64, __int64, void *), void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18000fc94`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003fe4`
- `0x180013ef0`
- `0x180013f70`
- `0x18001405c`
- `0x180014438`
- `0x1800144b4`
- `0x180016c1e`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180014134`
- `KERNEL32!EnterCriticalSection` at `0x180014134`
- `KERNEL32!GetLastError` at `0x1800141d9`
- `KERNEL32!GetLastError` at `0x180014273`
- `KERNEL32!GetLastError` at `0x18001435d`
- `KERNEL32!GetLastError` at `0x1800141d9`
- `KERNEL32!GetLastError` at `0x180014273`
- `KERNEL32!GetLastError` at `0x18001435d`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x180014123`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x180014123`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x180014264`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x180014264`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180014190`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180014190`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassExW` at `0x1800141ce`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassExW` at `0x1800141ce`

## string_xrefs

- `0x18001411c`: `TaskbarCreated`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShellNotification::Create(
        CShellNotification *this,
        HINSTANCE a2,
        struct _NOTIFYICONDATAW *a3,
        __int64 (*a4)(HWND, unsigned int, unsigned __int64, __int64, void *))
{
  CShellNotification *v6; // rcx
  unsigned int Shell32Apis; // ebx
  signed int LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HWND Window; // rax
  DWORD v13; // eax
  _OWORD *v14; // rax
  struct _NOTIFYICONDATAW *v15; // rcx
  __int64 v16; // rdx
  DWORD v17; // eax
  char *v18; // [rsp+60h] [rbp-31h] BYREF
  char v19; // [rsp+68h] [rbp-29h]
  WNDCLASSEXW hInstance; // [rsp+70h] [rbp-21h] BYREF

  memset_0(&hInstance, 0, sizeof(hInstance));
  if ( a3 )
  {
    Shell32Apis = CShellNotification::AreUser32ApisPresent(v6);
    if ( (Shell32Apis & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_721966d903033a5712e56ad66803da37_Traceguids);
      return Shell32Apis;
    }
    Shell32Apis = CShellNotification::LoadShell32Apis(this);
    if ( (Shell32Apis & 0x80000000) != 0 )
      return Shell32Apis;
    *((_DWORD *)this + 20) = RegisterWindowMessageW(L"TaskbarCreated");
    v18 = (char *)this + 24;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v19 = 1;
    if ( *(_DWORD *)this )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_721966d903033a5712e56ad66803da37_Traceguids);
      Shell32Apis = -2147467259;
      goto LABEL_16;
    }
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
    if ( !IsWindow(a3->hWnd) )
    {
      hInstance.cbSize = 80;
      hInstance.lpfnWndProc = (WNDPROC)CShellNotification::Static_NotificationWindowProc;
      hInstance.hInstance = &_ImageBase;
      hInstance.lpszClassName = L"WERCLASS";
      *(_QWORD *)&hInstance.cbClsExtra = 0;
      if ( !RegisterClassExW(&hInstance) )
      {
        LastError = GetLastError();
        Shell32Apis = LastError;
        if ( LastError > 0 )
          Shell32Apis = (unsigned __int16)LastError | 0x80070000;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_16;
        v11 = 18;
        goto LABEL_24;
      }
      Window = CreateWindowExW(0, hInstance.lpszClassName, 0, 0, 0, 0, 0, 0, 0, 0, hInstance.hInstance, this);
      *((_QWORD *)this + 1) = Window;
      if ( !Window )
      {
        v13 = GetLastError();
        Shell32Apis = ERROR_HR_FROM_WIN32(v13);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_16;
        v11 = 19;
LABEL_24:
        WPP_SF_d(v10[2], v11, WPP_721966d903033a5712e56ad66803da37_Traceguids, Shell32Apis);
LABEL_16:
        utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v18);
        return Shell32Apis;
      }
      *((_DWORD *)this + 266) = 1;
      a3->hWnd = Window;
    }
    v14 = (_OWORD *)((char *)this + 88);
    v15 = a3;
    v16 = 7;
    do
    {
      *v14 = *(_OWORD *)&v15->cbSize;
      v14[1] = *(_OWORD *)&v15->uID;
      v14[2] = *(_OWORD *)&v15->hIcon;
      v14[3] = *(_OWORD *)&v15->szTip[4];
      v14[4] = *(_OWORD *)&v15->szTip[12];
      v14[5] = *(_OWORD *)&v15->szTip[20];
      v14[6] = *(_OWORD *)&v15->szTip[28];
      v14[7] = *(_OWORD *)&v15->szTip[36];
      v14 += 8;
      v15 = (struct _NOTIFYICONDATAW *)((char *)v15 + 128);
      --v16;
    }
    while ( v16 );
    *v14 = *(_OWORD *)&v15->cbSize;
    v14[1] = *(_OWORD *)&v15->uID;
    v14[2] = *(_OWORD *)&v15->hIcon;
    v14[3] = *(_OWORD *)&v15->szTip[4];
    v14[4] = *(_OWORD *)&v15->szTip[12];
    if ( !a3->uCallbackMessage )
    {
      *((_DWORD *)this + 28) = 1279;
      *((_DWORD *)this + 27) |= 1u;
    }
    if ( (unsigned int)CShellNotification::InvokeShell_NotifyIcon(
                         this,
                         0,
                         (struct _NOTIFYICONDATAW *)((char *)this + 88)) )
    {
      *(_DWORD *)this = 1;
      utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v18);
      return 0;
    }
    v17 = GetLastError();
    Shell32Apis = ERROR_HR_FROM_WIN32(v17);
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_721966d903033a5712e56ad66803da37_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001405c  push    rbp
0x18001405e  push    rbx
0x18001405f  push    rdi
0x180014060  push    r14
0x180014062  push    r15
0x180014064  lea     rbp, [rsp-2Fh]
0x180014069  sub     rsp, 0C0h
0x180014070  mov     r14, r8
0x180014073  mov     rdi, rcx
0x180014076  xor     edx, edx; Val
0x180014078  lea     r8d, [rdx+50h]; Size
0x18001407c  lea     rcx, [rbp+4Fh+var_70]; void *
0x180014080  call    memset_0
0x180014085  xor     r15d, r15d
0x180014088  test    r14, r14
0x18001408b  jnz     short loc_1800140C4
0x18001408d  lea     rax, WPP_GLOBAL_Control
0x180014094  mov     rcx, cs:WPP_GLOBAL_Control
0x18001409b  cmp     rcx, rax
0x18001409e  jz      short loc_1800140BA
0x1800140a0  test    byte ptr [rcx+1Ch], 1
0x1800140a4  jz      short loc_1800140BA
0x1800140a6  lea     edx, [r15+0Fh]
0x1800140aa  lea     r8, WPP_721966d903033a5712e56ad66803da37_Traceguids
0x1800140b1  mov     rcx, [rcx+10h]
0x1800140b5  call    WPP_SF_
0x1800140ba  mov     eax, 80070057h
0x1800140bf  jmp     loc_180014385
0x1800140c4  call    ?AreUser32ApisPresent@CShellNotification@@AEAAJXZ; CShellNotification::AreUser32ApisPresent(void)
0x1800140c9  mov     ebx, eax
0x1800140cb  test    eax, eax
0x1800140cd  jns     short loc_18001410A
0x1800140cf  lea     rax, WPP_GLOBAL_Control
0x1800140d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140dd  cmp     rcx, rax
0x1800140e0  jz      loc_180014383
0x1800140e6  test    byte ptr [rcx+1Ch], 4
0x1800140ea  jz      loc_180014383
0x1800140f0  mov     edx, 10h
0x1800140f5  lea     r8, WPP_721966d903033a5712e56ad66803da37_Traceguids
0x1800140fc  mov     rcx, [rcx+10h]
0x180014100  call    WPP_SF_
0x180014105  jmp     loc_180014383
0x18001410a  mov     rcx, rdi; this
0x18001410d  call    ?LoadShell32Apis@CShellNotification@@AEAAJXZ; CShellNotification::LoadShell32Apis(void)
0x180014112  mov     ebx, eax
0x180014114  test    eax, eax
0x180014116  js      loc_180014383
0x18001411c  lea     rcx, aTaskbarcreated; "TaskbarCreated"
0x180014123  call    cs:__imp_RegisterWindowMessageW
0x180014129  mov     [rdi+50h], eax
0x18001412c  lea     rcx, [rdi+18h]; lpCriticalSection
0x180014130  mov     [rbp+4Fh+var_80], rcx
0x180014134  call    cs:__imp_EnterCriticalSection
0x18001413a  mov     [rbp+4Fh+var_78], 1
0x18001413e  cmp     [rdi], r15d
0x180014141  jz      short loc_180014184
0x180014143  lea     rax, WPP_GLOBAL_Control
0x18001414a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014151  cmp     rcx, rax
0x180014154  jz      short loc_180014171
0x180014156  test    byte ptr [rcx+1Ch], 1
0x18001415a  jz      short loc_180014171
0x18001415c  mov     edx, 11h
0x180014161  lea     r8, WPP_721966d903033a5712e56ad66803da37_Traceguids
0x180014168  mov     rcx, [rcx+10h]
0x18001416c  call    WPP_SF_
0x180014171  mov     ebx, 80004005h
0x180014176  lea     rcx, [rbp+4Fh+var_80]
0x18001417a  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x18001417f  jmp     loc_180014383
0x180014184  mov     [rdi+40h], r15
0x180014188  mov     [rdi+48h], r15
0x18001418c  mov     rcx, [r14+8]; hWnd
0x180014190  call    cs:__imp_IsWindow
0x180014196  test    eax, eax
0x180014198  jnz     loc_1800142BB
0x18001419e  mov     [rbp+4Fh+var_70.cbSize], 50h ; 'P'
0x1800141a5  lea     rax, ?Static_NotificationWindowProc@CShellNotification@@CA_JPEAUHWND__@@I_K_J@Z; CShellNotification::Static_NotificationWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800141ac  mov     [rbp+4Fh+var_70.lpfnWndProc], rax
0x1800141b0  lea     rax, __ImageBase
0x1800141b7  mov     [rbp+4Fh+var_70.hInstance], rax
0x1800141bb  lea     rax, aWerclass; "WERCLASS"
0x1800141c2  mov     [rbp+4Fh+var_70.lpszClassName], rax
0x1800141c6  mov     qword ptr [rbp+4Fh+var_70.cbClsExtra], r15
0x1800141ca  lea     rcx, [rbp+4Fh+var_70]; WNDCLASSEXW *
0x1800141ce  call    cs:__imp_RegisterClassExW
0x1800141d4  test    ax, ax
0x1800141d7  jnz     short loc_18001422C
0x1800141d9  call    cs:__imp_GetLastError
0x1800141df  mov     ebx, eax
0x1800141e1  test    eax, eax
0x1800141e3  jle     short loc_1800141EE
0x1800141e5  movzx   ebx, ax
0x1800141e8  or      ebx, 80070000h
0x1800141ee  lea     rax, WPP_GLOBAL_Control
0x1800141f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141fc  cmp     rcx, rax
0x1800141ff  jz      loc_180014176
0x180014205  test    byte ptr [rcx+1Ch], 1
0x180014209  jz      loc_180014176
0x18001420f  mov     edx, 12h
0x180014214  mov     r9d, ebx
0x180014217  lea     r8, WPP_721966d903033a5712e56ad66803da37_Traceguids
0x18001421e  mov     rcx, [rcx+10h]
0x180014222  call    WPP_SF_d
0x180014227  jmp     loc_180014176
0x18001422c  mov     [rsp+0E0h+lpParam], rdi; lpParam
0x180014231  mov     rax, [rbp+4Fh+var_70.hInstance]
0x180014235  mov     [rsp+0E0h+hInstance], rax; hInstance
0x18001423a  mov     [rsp+0E0h+hMenu], r15; hMenu
0x18001423f  mov     [rsp+0E0h+hWndParent], r15; hWndParent
0x180014244  mov     [rsp+0E0h+nHeight], r15d; nHeight
0x180014249  mov     [rsp+0E0h+nWidth], r15d; nWidth
0x18001424e  mov     [rsp+0E0h+Y], r15d; Y
0x180014253  mov     [rsp+0E0h+X], r15d; X
0x180014258  xor     r9d, r9d; dwStyle
0x18001425b  xor     r8d, r8d; lpWindowName
0x18001425e  mov     rdx, [rbp+4Fh+var_70.lpszClassName]; lpClassName
0x180014262  xor     ecx, ecx; dwExStyle
0x180014264  call    cs:__imp_CreateWindowExW
0x18001426a  mov     [rdi+8], rax
0x18001426e  test    rax, rax
0x180014271  jnz     short loc_1800142AD
0x180014273  call    cs:__imp_GetLastError
0x180014279  mov     ecx, eax; unsigned int
0x18001427b  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180014280  mov     ebx, eax
0x180014282  lea     rax, WPP_GLOBAL_Control
0x180014289  mov     rcx, cs:WPP_GLOBAL_Control
0x180014290  cmp     rcx, rax
0x180014293  jz      loc_180014176
0x180014299  test    byte ptr [rcx+1Ch], 1
0x18001429d  jz      loc_180014176
0x1800142a3  mov     edx, 13h
0x1800142a8  jmp     loc_180014214
0x1800142ad  mov     dword ptr [rdi+428h], 1
0x1800142b7  mov     [r14+8], rax
0x1800142bb  lea     r8, [rdi+58h]; struct _NOTIFYICONDATAW *
0x1800142bf  mov     rax, r8
0x1800142c2  mov     rcx, r14
0x1800142c5  mov     edx, 7
0x1800142ca  lea     r9d, [rdx+79h]
0x1800142ce  movups  xmm0, xmmword ptr [rcx]
0x1800142d1  movups  xmmword ptr [rax], xmm0
0x1800142d4  movups  xmm1, xmmword ptr [rcx+10h]
0x1800142d8  movups  xmmword ptr [rax+10h], xmm1
0x1800142dc  movups  xmm0, xmmword ptr [rcx+20h]
0x1800142e0  movups  xmmword ptr [rax+20h], xmm0
0x1800142e4  movups  xmm1, xmmword ptr [rcx+30h]
0x1800142e8  movups  xmmword ptr [rax+30h], xmm1
0x1800142ec  movups  xmm0, xmmword ptr [rcx+40h]
0x1800142f0  movups  xmmword ptr [rax+40h], xmm0
0x1800142f4  movups  xmm1, xmmword ptr [rcx+50h]
0x1800142f8  movups  xmmword ptr [rax+50h], xmm1
0x1800142fc  movups  xmm0, xmmword ptr [rcx+60h]
0x180014300  movups  xmmword ptr [rax+60h], xmm0
0x180014304  movups  xmm1, xmmword ptr [rcx+70h]
0x180014308  movups  xmmword ptr [rax+70h], xmm1
0x18001430c  add     rax, r9
0x18001430f  add     rcx, r9
0x180014312  sub     rdx, 1
0x180014316  jnz     short loc_1800142CE
0x180014318  movups  xmm0, xmmword ptr [rcx]
0x18001431b  movups  xmmword ptr [rax], xmm0
0x18001431e  movups  xmm1, xmmword ptr [rcx+10h]
0x180014322  movups  xmmword ptr [rax+10h], xmm1
0x180014326  movups  xmm0, xmmword ptr [rcx+20h]
0x18001432a  movups  xmmword ptr [rax+20h], xmm0
0x18001432e  movups  xmm1, xmmword ptr [rcx+30h]
0x180014332  movups  xmmword ptr [rax+30h], xmm1
0x180014336  movups  xmm0, xmmword ptr [rcx+40h]
0x18001433a  movups  xmmword ptr [rax+40h], xmm0
0x18001433e  cmp     [r14+18h], r15d
0x180014342  jnz     short loc_18001434F
0x180014344  mov     dword ptr [rdi+70h], 4FFh
0x18001434b  or      dword ptr [rdi+6Ch], 1
0x18001434f  xor     edx, edx; unsigned int
0x180014351  mov     rcx, rdi; this
0x180014354  call    ?InvokeShell_NotifyIcon@CShellNotification@@AEAAHKPEAU_NOTIFYICONDATAW@@@Z; CShellNotification::InvokeShell_NotifyIcon(ulong,_NOTIFYICONDATAW *)
0x180014359  test    eax, eax
0x18001435b  jnz     short loc_180014371
0x18001435d  call    cs:__imp_GetLastError
0x180014363  mov     ecx, eax; unsigned int
0x180014365  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001436a  mov     ebx, eax
0x18001436c  jmp     loc_180014176
0x180014371  mov     dword ptr [rdi], 1
0x180014377  lea     rcx, [rbp+4Fh+var_80]
0x18001437b  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x180014380  mov     ebx, r15d
0x180014383  mov     eax, ebx
0x180014385  add     rsp, 0C0h
0x18001438c  pop     r15
0x18001438e  pop     r14
0x180014390  pop     rdi
0x180014391  pop     rbx
0x180014392  pop     rbp
0x180014393  retn
```
