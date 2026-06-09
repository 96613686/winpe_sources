# DefFrameProcWorker(HWND__ *,HWND__ *,uint,unsigned __int64,__int64,int)

- ea: `0x180011f38`
- end: `0x180012333`
- name: `?DefFrameProcWorker@@YA_JPEAUHWND__@@0I_K_JH@Z`
- size: `1019`
- prototype: `__int64 __usercall@<rax>(HWND hWndParent@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64, int)`
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting`

## callers

- `0x180011f10`
- `0x18005eb50`

## callees

- `0x1800070e0`
- `0x1800073b4`
- `0x180007640`
- `0x18000cf20`
- `0x18000d210`
- `0x180010950`
- `0x180011f38`
- `0x180019d30`
- `0x180020990`
- `0x180052258`
- `0x180055b24`
- `0x18005cc64`
- `0x180065cb0`
- `0x1800682d0`
- `0x180068f30`
- `0x18006f780`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserSetSysMenu` at `0x1800990da`
- `win32u!NtUserSetSysMenu` at `0x1800990da`
- `win32u!NtUserSetFocus` at `0x180012040`
- `win32u!NtUserSetFocus` at `0x180012040`
- `win32u!NtUserMoveWindow` at `0x1800121fa`
- `win32u!NtUserMoveWindow` at `0x1800121fa`
- `win32u!NtUserGetWindowPlacement` at `0x180012229`
- `win32u!NtUserGetWindowPlacement` at `0x180012229`
- `win32u!NtUserGetSystemMenu` at `0x1800990af`
- `win32u!NtUserGetSystemMenu` at `0x1800990e6`
- `win32u!NtUserGetSystemMenu` at `0x1800990af`
- `win32u!NtUserGetSystemMenu` at `0x1800990e6`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18001218d`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18001218d`
- `ntdll!RtlFreeHeap` at `0x1800121ca`
- `ntdll!RtlFreeHeap` at `0x1800121ca`
- `ntdll!RtlAllocateHeap` at `0x18001216b`
- `ntdll!RtlAllocateHeap` at `0x18001216b`

## pseudocode

```c
LRESULT __fastcall DefFrameProcWorker(
        HWND hWndParent,
        HWND a2,
        ULONG a3,
        unsigned __int64 a4,
        unsigned __int16 *lParam,
        unsigned int a6)
{
  unsigned __int16 *v6; // r14
  struct tagWND *v10; // r15
  struct tagWND *v11; // rax
  __int64 v12; // rdx
  struct tagWND *v13; // r13
  __int64 v14; // rsi
  unsigned int v16; // ecx
  __int64 v17; // rbx
  HWND v18; // r12
  struct tagWND *v19; // rax
  struct tagWND *v20; // rsi
  int v21; // ebx
  bool v22; // zf
  unsigned __int16 *v23; // rbx
  __int64 v24; // rax
  ULONG BytesInMultiByteString; // edi
  WCHAR *Heap; // rax
  __int64 v27; // r8
  int v28; // eax
  int v29; // edx
  int v30; // esi
  int v31; // r13d
  unsigned int DpiForSystem; // eax
  int v33; // ebx
  unsigned int v34; // eax
  int DpiDependentMetric; // eax
  INT_PTR v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rbx
  struct tagWND *v40; // rax
  HWND v41; // rcx
  WPARAM *PwndChild; // rax
  WPARAM v43; // r8
  WPARAM *v44; // rbx
  ULONG BytesInUnicodeString; // [rsp+30h] [rbp-49h] BYREF
  int v46; // [rsp+34h] [rbp-45h]
  HWND v47; // [rsp+38h] [rbp-41h]
  _OWORD v48[3]; // [rsp+40h] [rbp-39h] BYREF

  v6 = lParam;
  BytesInUnicodeString = a3;
  v47 = hWndParent;
  memset(v48, 0, 44);
  v10 = ValidateHwnd(hWndParent);
  if ( !v10 )
    return 0;
  if ( !a2 )
    return DefWindowProcWorker(v10, BytesInUnicodeString, a4, (__int64)lParam, a6);
  v11 = ValidateHwnd(a2);
  v13 = v11;
  if ( !v11 || (*((_WORD *)v11 + 21) & 0x2A7) == 0 )
    return 0;
  v14 = *(_QWORD *)(*((_QWORD *)v11 + 37) + 8LL);
  switch ( BytesInUnicodeString )
  {
    case 5u:
      if ( a4 == 1 )
      {
        LODWORD(v48[0]) = 44;
        if ( (unsigned int)NtUserGetWindowPlacement(hWndParent, v48, 0) )
        {
          v28 = -(int)GetWindowBorders(*((unsigned int *)v10 + 7), *((unsigned int *)v10 + 6), v27, 1);
          v29 = v28 + DWORD1(v48[2]);
          v30 = LODWORD(v48[2]) - v28;
          v31 = v28 + DWORD2(v48[2]);
          LODWORD(v47) = HIDWORD(v48[1]) - v28;
          LOBYTE(v28) = *((_BYTE *)v10 + 30) & 0xC0;
          v46 = v29;
          if ( (_BYTE)v28 == 0xC0 )
          {
            DpiForSystem = GetDpiForSystem();
            v33 = v30 + GetDpiDependentMetric(2, DpiForSystem);
          }
          else
          {
            v33 = v30;
          }
          v34 = GetDpiForSystem();
          DpiDependentMetric = GetDpiDependentMetric(9, v34);
          NtUserMoveWindow(a2, 0, 0, (unsigned int)(v46 - (_DWORD)v47), v31 - v33 - DpiDependentMetric, 1);
        }
      }
      else
      {
        NtUserMoveWindow(a2, 0, 0, (unsigned __int16)lParam, WORD1(lParam), 1);
      }
      return DefWindowProcWorker(v10, BytesInUnicodeString, a4, (__int64)lParam, a6);
    case 7u:
      NtUserSetFocus(a2);
      return 0;
    case 0xCu:
      v23 = 0;
      if ( a6 && lParam )
      {
        BytesInUnicodeString = 0;
        v24 = -1;
        do
          ++v24;
        while ( *((_BYTE *)lParam + v24) );
        BytesInMultiByteString = v24 + 1;
        if ( (_DWORD)v24 == -1 )
          return 0;
        Heap = (WCHAR *)RtlAllocateHeap(pUserHeap, 8u, 2 * BytesInMultiByteString);
        v23 = Heap;
        if ( !Heap )
          return 0;
        if ( RtlMultiByteToUnicodeN(
               Heap,
               2 * BytesInMultiByteString,
               &BytesInUnicodeString,
               (const CHAR *)lParam,
               BytesInMultiByteString) < 0 )
          goto LABEL_42;
        if ( (BytesInUnicodeString & 0xFFFFFFFE) == 0 )
          return 0;
        v6 = v23;
      }
      xxxSetFrameTitle(v10, v13, v6);
      if ( !v23 )
        return 0;
LABEL_42:
      RtlFreeHeap(pUserHeap, 0, v23);
      return 0;
    case 0x86u:
      SendMessageW(a2, 0x86u, a4, (LPARAM)lParam);
      return DefWindowProcWorker(v10, BytesInUnicodeString, a4, (__int64)lParam, a6);
    case 0x111u:
      v16 = *(_DWORD *)(v14 + 32);
      if ( (unsigned __int16)a4 == v16 + 9 )
      {
        if ( a6 )
          v36 = DialogBoxParamA(hmodUser, (LPCSTR)9, hWndParent, MDIActivateDlgProcW, (LPARAM)v11);
        else
          v36 = DialogBoxParamW(hmodUser, (LPCWSTR)9, hWndParent, MDIActivateDlgProcW, (LPARAM)v11);
        a4 = v36;
        if ( (int)v36 >= 0 )
        {
          LOWORD(a4) = *(_DWORD *)(v14 + 32) + v36;
LABEL_80:
          PwndChild = (WPARAM *)FindPwndChild(v13, (unsigned __int16)a4);
          v44 = PwndChild;
          if ( PwndChild )
            v43 = *PwndChild;
          SendMessageW(a2, 0x222u, v43, 0);
          if ( v44 && (*((_BYTE *)v44 + 31) & 0x20) != 0 )
            SendMessageW((HWND)*v44, 0x112u, 0xF120u, 0);
          return 0;
        }
      }
      else if ( (unsigned __int16)a4 >= v16 && (unsigned __int16)a4 < *(_DWORD *)v14 + v16 )
      {
        goto LABEL_80;
      }
      v17 = (unsigned __int16)a4 & 0xFFF0;
      if ( v17 != 61440
        && (a4 & 0xFFF0) != 0xF010
        && (a4 & 0xFFF0) != 0xF020
        && (a4 & 0xFFF0) != 0xF030
        && (a4 & 0xFFF0) != 0xF040
        && (a4 & 0xFFF0) != 0xF050
        && (a4 & 0xFFF0) != 0xF060
        && (a4 & 0xFFF0) != 0xF120 )
      {
        return DefWindowProcWorker(v10, BytesInUnicodeString, a4, (__int64)lParam, a6);
      }
      v18 = *(HWND *)(v14 + 8);
      if ( !v18 )
        return DefWindowProcWorker(v10, BytesInUnicodeString, a4, (__int64)lParam, a6);
      v19 = ValidateHwnd(*(HWND *)(v14 + 8));
      v20 = v19;
      if ( !v19 )
        return DefWindowProcWorker(v10, BytesInUnicodeString, a4, (__int64)lParam, a6);
      if ( v17 == 61536 )
      {
        SetWindowState(v19, 0xE08u);
        v21 = xxxMNCanClose(v20);
        ClearWindowState(v20, 0xE08u);
        v22 = v21 == 0;
      }
      else
      {
        if ( v17 != 61472 )
          return SendMessageW(v18, 0x112u, a4, (LPARAM)lParam);
        v22 = (*((_BYTE *)v19 + 30) & 2) == 0;
      }
      if ( v22 )
        return DefWindowProcWorker(v10, BytesInUnicodeString, a4, (__int64)lParam, a6);
      return SendMessageW(v18, 0x112u, a4, (LPARAM)lParam);
  }
  if ( BytesInUnicodeString != 288 )
  {
    if ( BytesInUnicodeString != 531 )
      return DefWindowProcWorker(v10, BytesInUnicodeString, a4, (__int64)lParam, a6);
    if ( (*((_BYTE *)v10 + 30) & 8) == 0 )
      return 0;
    if ( (*((_BYTE *)v10 + 31) & 0x20) != 0 )
      return 0;
    if ( !*(_QWORD *)(v14 + 16) )
      return 0;
    if ( *(_QWORD *)(v14 + 8) )
      return 0;
    LOBYTE(v12) = 2;
    v37 = HMValidateHandleNoRip(*(_QWORD *)lParam, v12);
    if ( !v37 )
      return 0;
    if ( a4 != 37 )
      goto LABEL_87;
    v38 = *((_QWORD *)v10 + 19);
    if ( !v38 )
      return 0;
    if ( (struct tagWND *)v37 != (struct tagWND *)((char *)v10 + v38 - *((_QWORD *)v10 + 1)) )
    {
LABEL_87:
      if ( a4 != 39 )
        return 0;
      v39 = *(_QWORD *)lParam;
      if ( v39 != NtUserGetSystemMenu(v47, 0) )
        return 0;
    }
    v40 = ValidateHwnd(*(HWND *)(v14 + 16));
    if ( v40 )
    {
      if ( (*((_BYTE *)v40 + 31) & 1) == 0 )
        NtUserSetSysMenu(*(_QWORD *)(v14 + 16));
      *((_QWORD *)lParam + 1) = NtUserGetSystemMenu(*(_QWORD *)(v14 + 16), 0);
      *((_QWORD *)lParam + 2) = *(_QWORD *)(v14 + 16);
      return 1;
    }
    return 0;
  }
  if ( (*((_BYTE *)v10 + 31) & 0x20) != 0 || (_WORD)a4 != 45 )
    return DefWindowProcWorker(v10, BytesInUnicodeString, a4, (__int64)lParam, a6);
  if ( *(_QWORD *)(v14 + 8) )
    return 0x20000;
  v41 = *(HWND *)(v14 + 16);
  if ( !v41 )
    return DefWindowProcWorker(v10, BytesInUnicodeString, a4, (__int64)lParam, a6);
  PostMessageW(v41, 0x112u, 0xF100u, 45);
  return 0x10000;
}

```

## disassembly

```asm
0x180011f38  push    rbp
0x180011f3a  push    rbx
0x180011f3b  push    rsi
0x180011f3c  push    rdi
0x180011f3d  push    r12
0x180011f3f  push    r13
0x180011f41  push    r14
0x180011f43  push    r15
0x180011f45  lea     rbp, [rsp-0Fh]
0x180011f4a  sub     rsp, 88h
0x180011f51  mov     rax, cs:__security_cookie
0x180011f58  xor     rax, rsp
0x180011f5b  mov     [rbp+47h+var_50], rax
0x180011f5f  mov     r14, [rbp+47h+lParam]
0x180011f63  xorps   xmm0, xmm0
0x180011f66  movups  [rbp+47h+var_70], xmm0
0x180011f6a  mov     rdi, r9
0x180011f6d  mov     [rbp+47h+BytesInUnicodeString], r8d
0x180011f71  movups  [rbp+47h+var_70+0Ch], xmm0
0x180011f75  mov     r12, rdx
0x180011f78  mov     [rbp+47h+var_88], rcx
0x180011f7c  mov     rbx, rcx
0x180011f7f  movups  [rbp+47h+var_80], xmm0
0x180011f83  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180011f88  mov     r15, rax
0x180011f8b  test    rax, rax
0x180011f8e  jz      loc_180012046
0x180011f94  test    r12, r12
0x180011f97  jz      short loc_180012005
0x180011f99  mov     rcx, r12; HWND
0x180011f9c  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180011fa1  xor     r8d, r8d
0x180011fa4  mov     r13, rax
0x180011fa7  test    rax, rax
0x180011faa  jz      loc_180012046
0x180011fb0  mov     eax, 2A7h
0x180011fb5  test    [r13+2Ah], ax
0x180011fba  jz      loc_180012046
0x180011fc0  mov     rax, [r13+128h]
0x180011fc7  mov     rsi, [rax+8]
0x180011fcb  mov     eax, [rbp+47h+BytesInUnicodeString]
0x180011fce  sub     eax, 5
0x180011fd1  jz      loc_1800121D5
0x180011fd7  sub     eax, 2
0x180011fda  jz      short loc_18001203D
0x180011fdc  sub     eax, 5
0x180011fdf  jz      loc_18001212F
0x180011fe5  sub     eax, 7Ah ; 'z'
0x180011fe8  jz      short loc_18001204A
0x180011fea  sub     eax, 8Bh
0x180011fef  jz      short loc_18001205F
0x180011ff1  sub     eax, 0Fh
0x180011ff4  jz      loc_1800122BE
0x180011ffa  cmp     eax, 0F3h
0x180011fff  jz      loc_18009903A
0x180012005  mov     eax, [rbp+47h+arg_28]
0x180012008  mov     r9, r14; __int64
0x18001200b  mov     edx, [rbp+47h+BytesInUnicodeString]; unsigned int
0x18001200e  mov     r8, rdi; unsigned __int64
0x180012011  mov     rcx, r15; struct tagWND *
0x180012014  mov     [rsp+0C0h+BytesInMultiByteString], eax; unsigned int
0x180012018  call    ?DefWindowProcWorker@@YA_JPEAUtagWND@@I_K_JK@Z; DefWindowProcWorker(tagWND *,uint,unsigned __int64,__int64,ulong)
0x18001201d  mov     rcx, [rbp+47h+var_50]
0x180012021  xor     rcx, rsp; StackCookie
0x180012024  call    __security_check_cookie
0x180012029  add     rsp, 88h
0x180012030  pop     r15
0x180012032  pop     r14
0x180012034  pop     r13
0x180012036  pop     r12
0x180012038  pop     rdi
0x180012039  pop     rsi
0x18001203a  pop     rbx
0x18001203b  pop     rbp
0x18001203c  retn
0x18001203d  mov     rcx, r12
0x180012040  call    cs:__imp_NtUserSetFocus
0x180012046  xor     eax, eax
0x180012048  jmp     short loc_18001201D
0x18001204a  mov     r9, r14; lParam
0x18001204d  mov     r8, rdi; wParam
0x180012050  mov     edx, 86h; Msg
0x180012055  mov     rcx, r12; hWnd
0x180012058  call    SendMessageW
0x18001205d  jmp     short loc_180012005
0x18001205f  mov     ecx, [rsi+20h]
0x180012062  movzx   edx, di
0x180012065  lea     eax, [rcx+9]
0x180012068  cmp     edx, eax
0x18001206a  jz      loc_1800122ED
0x180012070  cmp     edx, ecx
0x180012072  jnb     loc_18001231D
0x180012078  mov     rbx, rdi
0x18001207b  and     ebx, 0FFF0h
0x180012081  mov     eax, ebx
0x180012083  sub     rax, 0F000h
0x180012089  jz      short loc_1800120BB
0x18001208b  sub     rax, 10h
0x18001208f  jz      short loc_1800120BB
0x180012091  sub     rax, 10h
0x180012095  jz      short loc_1800120BB
0x180012097  sub     rax, 10h
0x18001209b  jz      short loc_1800120BB
0x18001209d  sub     rax, 10h
0x1800120a1  jz      short loc_1800120BB
0x1800120a3  sub     rax, 10h
0x1800120a7  jz      short loc_1800120BB
0x1800120a9  sub     rax, 10h
0x1800120ad  jz      short loc_1800120BB
0x1800120af  cmp     rax, 0C0h
0x1800120b5  jnz     loc_180012005
0x1800120bb  mov     r12, [rsi+8]
0x1800120bf  test    r12, r12
0x1800120c2  jz      loc_180012005
0x1800120c8  mov     rcx, r12; HWND
0x1800120cb  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x1800120d0  mov     rsi, rax
0x1800120d3  test    rax, rax
0x1800120d6  jz      loc_180012005
0x1800120dc  cmp     rbx, 0F060h
0x1800120e3  jnz     loc_180012205
0x1800120e9  mov     r13d, 0E08h
0x1800120ef  mov     rcx, rax; struct tagWND *
0x1800120f2  mov     edx, r13d; unsigned int
0x1800120f5  call    ?SetWindowState@@YAXPEAUtagWND@@I@Z; SetWindowState(tagWND *,uint)
0x1800120fa  mov     rcx, rsi
0x1800120fd  call    xxxMNCanClose
0x180012102  mov     edx, r13d; unsigned int
0x180012105  mov     rcx, rsi; struct tagWND *
0x180012108  mov     ebx, eax
0x18001210a  call    ?ClearWindowState@@YAXPEAUtagWND@@I@Z; ClearWindowState(tagWND *,uint)
0x18001210f  test    ebx, ebx
0x180012111  jz      loc_180012005
0x180012117  mov     r9, r14; lParam
0x18001211a  mov     r8, rdi; wParam
0x18001211d  mov     edx, 112h; Msg
0x180012122  mov     rcx, r12; hWnd
0x180012125  call    SendMessageW
0x18001212a  jmp     loc_18001201D
0x18001212f  mov     rbx, r8
0x180012132  cmp     [rbp+47h+arg_28], r8d
0x180012136  jz      short loc_1800121A7
0x180012138  test    r14, r14
0x18001213b  jz      short loc_1800121A7
0x18001213d  mov     [rbp+47h+BytesInUnicodeString], r8d
0x180012141  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012145  inc     rax
0x180012148  cmp     [r14+rax], r8b
0x18001214c  jnz     short loc_180012145
0x18001214e  lea     edi, [rax+1]
0x180012151  test    edi, edi
0x180012153  jz      loc_180012046
0x180012159  mov     rcx, cs:pUserHeap; HeapHandle
0x180012160  lea     esi, [rdi+rdi]
0x180012163  mov     r8d, esi; Size
0x180012166  mov     edx, 8; Flags
0x18001216b  call    cs:__imp_RtlAllocateHeap
0x180012171  mov     rbx, rax
0x180012174  test    rax, rax
0x180012177  jz      loc_180012046
0x18001217d  mov     r9, r14; MultiByteString
0x180012180  mov     [rsp+0C0h+BytesInMultiByteString], edi; BytesInMultiByteString
0x180012184  lea     r8, [rbp+47h+BytesInUnicodeString]; BytesInUnicodeString
0x180012188  mov     edx, esi; MaxBytesInUnicodeString
0x18001218a  mov     rcx, rax; UnicodeString
0x18001218d  call    cs:__imp_RtlMultiByteToUnicodeN
0x180012193  test    eax, eax
0x180012195  js      short loc_1800121BE
0x180012197  test    [rbp+47h+BytesInUnicodeString], 0FFFFFFFEh
0x18001219e  jz      loc_180012046
0x1800121a4  mov     r14, rbx
0x1800121a7  mov     r8, r14; unsigned __int16 *
0x1800121aa  mov     rdx, r13; struct tagWND *
0x1800121ad  mov     rcx, r15; struct tagWND *
0x1800121b0  call    ?xxxSetFrameTitle@@YAXPEAUtagWND@@0PEAG@Z; xxxSetFrameTitle(tagWND *,tagWND *,ushort *)
0x1800121b5  test    rbx, rbx
0x1800121b8  jz      loc_180012046
0x1800121be  mov     rcx, cs:pUserHeap; HeapHandle
0x1800121c5  mov     r8, rbx; P
0x1800121c8  xor     edx, edx; Flags
0x1800121ca  call    cs:__imp_RtlFreeHeap
0x1800121d0  jmp     loc_180012046
0x1800121d5  cmp     rdi, 1
0x1800121d9  jz      short loc_18001221B
0x1800121db  mov     rax, r14
0x1800121de  mov     [rsp+0C0h+var_98], 1
0x1800121e6  shr     rax, 10h
0x1800121ea  movzx   ecx, ax
0x1800121ed  mov     [rsp+0C0h+BytesInMultiByteString], ecx
0x1800121f1  movzx   r9d, r14w
0x1800121f5  xor     edx, edx
0x1800121f7  mov     rcx, r12
0x1800121fa  call    cs:__imp_NtUserMoveWindow
0x180012200  jmp     loc_180012005
0x180012205  cmp     rbx, 0F020h
0x18001220c  jnz     loc_180012117
0x180012212  test    byte ptr [rax+1Eh], 2
0x180012216  jmp     loc_180012111
0x18001221b  lea     rdx, [rbp+47h+var_80]
0x18001221f  mov     dword ptr [rbp+47h+var_80], 2Ch ; ','
0x180012226  mov     rcx, rbx
0x180012229  call    cs:__imp_NtUserGetWindowPlacement
0x18001222f  test    eax, eax
0x180012231  jz      loc_180012005
0x180012237  mov     edx, [r15+18h]
0x18001223b  mov     r9d, 1
0x180012241  mov     ecx, [r15+1Ch]
0x180012245  call    GetWindowBorders
0x18001224a  mov     ecx, dword ptr [rbp+47h+var_70+0Ch]
0x18001224d  neg     eax
0x18001224f  mov     edx, [rbp+47h+var_5C]
0x180012252  sub     ecx, eax
0x180012254  mov     esi, [rbp+47h+var_60]
0x180012257  add     edx, eax
0x180012259  mov     r13d, [rbp+47h+var_58]
0x18001225d  sub     esi, eax
0x18001225f  add     r13d, eax
0x180012262  mov     dword ptr [rbp+47h+var_88], ecx
0x180012265  mov     al, [r15+1Eh]
0x180012269  and     al, 0C0h
0x18001226b  mov     [rbp+47h+var_8C], edx
0x18001226e  cmp     al, 0C0h
0x180012270  jnz     loc_18001232C
0x180012276  call    GetDpiForSystem
0x18001227b  mov     edx, eax
0x18001227d  mov     ecx, 2
0x180012282  call    GetDpiDependentMetric
0x180012287  lea     ebx, [rsi+rax]
0x18001228a  call    GetDpiForSystem
0x18001228f  mov     edx, eax
0x180012291  mov     ecx, 9
0x180012296  call    GetDpiDependentMetric
0x18001229b  mov     r9d, [rbp+47h+var_8C]
0x18001229f  sub     r13d, ebx
0x1800122a2  sub     r9d, dword ptr [rbp+47h+var_88]
0x1800122a6  sub     r13d, eax
0x1800122a9  mov     [rsp+0C0h+var_98], 1
0x1800122b1  xor     r8d, r8d
0x1800122b4  mov     [rsp+0C0h+BytesInMultiByteString], r13d
0x1800122b9  jmp     loc_1800121F5
0x1800122be  test    byte ptr [r15+1Fh], 20h
0x1800122c3  jnz     loc_180012005
0x1800122c9  mov     r9d, 2Dh ; '-'; lParam
0x1800122cf  cmp     di, r9w
0x1800122d3  jnz     loc_180012005
0x1800122d9  cmp     [rsi+8], r8
0x1800122dd  jz      loc_180099102
0x1800122e3  mov     eax, 20000h
0x1800122e8  jmp     loc_18001201D
0x1800122ed  cmp     [rbp+47h+arg_28], r8d
0x1800122f1  mov     edx, 9; lpTemplateName
0x1800122f6  mov     rcx, cs:hmodUser; hInstance
0x1800122fd  mov     r8, rbx; hWndParent
0x180012300  mov     qword ptr [rsp+0C0h+BytesInMultiByteString], r13; dwInitParam
0x180012305  jz      loc_180099129
0x18001230b  lea     r9, ?MDIActivateDlgProcW@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180012312  call    DialogBoxParamA
0x180012317  nop
0x180012318  jmp     loc_180099135
0x18001231d  add     ecx, [rsi]
0x18001231f  cmp     edx, ecx
0x180012321  jnb     loc_180012078
0x180012327  jmp     loc_180099149
0x18001232c  mov     ebx, esi
0x18001232e  jmp     loc_18001228A
0x18009903a  test    byte ptr [r15+1Eh], 8
0x18009903f  jz      loc_180012046
0x180099045  test    byte ptr [r15+1Fh], 20h
0x18009904a  jnz     loc_180012046
0x180099050  cmp     [rsi+10h], r8
0x180099054  jz      loc_180012046
0x18009905a  cmp     [rsi+8], r8
0x18009905e  jnz     loc_180012046
0x180099064  mov     rcx, [r14]
0x180099067  mov     dl, 2
0x180099069  call    HMValidateHandleNoRip
0x18009906e  mov     rdx, rax
0x180099071  test    rax, rax
0x180099074  jz      loc_180012046
0x18009907a  cmp     rdi, 25h ; '%'
0x18009907e  jnz     short loc_18009909C
0x180099080  mov     rax, [r15+98h]
0x180099087  test    rax, rax
0x18009908a  jz      loc_180012046
0x180099090  sub     rax, [r15+8]
0x180099094  add     rax, r15
0x180099097  cmp     rdx, rax
0x18009909a  jz      short loc_1800990BE
0x18009909c  cmp     rdi, 27h ; '''
0x1800990a0  jnz     loc_180012046
0x1800990a6  mov     rcx, [rbp+47h+var_88]
0x1800990aa  xor     edx, edx
0x1800990ac  mov     rbx, [r14]
0x1800990af  call    cs:__imp_NtUserGetSystemMenu
0x1800990b5  cmp     rbx, rax
0x1800990b8  jnz     loc_180012046
0x1800990be  mov     rcx, [rsi+10h]; HWND
0x1800990c2  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x1800990c7  test    rax, rax
0x1800990ca  jz      loc_180012046
  ... truncated ...
```
