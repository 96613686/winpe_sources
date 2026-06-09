# xxxLBCreate(tagLBIV *,tagWND *,tagCREATESTRUCTW *)

- ea: `0x18005ba14`
- end: `0x18005bdc7`
- name: `?xxxLBCreate@@YAJPEAUtagLBIV@@PEAUtagWND@@PEAUtagCREATESTRUCTW@@@Z`
- size: `947`
- prototype: `__int64 __fastcall(struct tagLBIV *, struct tagWND *, struct tagCREATESTRUCTW *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180039fc0`

## callees

- `0x18000cf20`
- `0x180020990`
- `0x18003b404`
- `0x18004f69c`
- `0x18005ba14`
- `0x18005bdd0`
- `0x1800865ac`
- `0x1800968f4`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserReleaseDC` at `0x18005bc43`
- `win32u!NtUserReleaseDC` at `0x18005bc43`
- `win32u!NtUserGetDC` at `0x18005bc22`
- `win32u!NtUserGetDC` at `0x18005bc22`
- `ntdll!RtlSetLastWin32Error` at `0x18009fdb9`
- `ntdll!RtlSetLastWin32Error` at `0x18009fdb9`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18005bba3`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18005bba3`
- `GDI32!GdiGetCharDimensions` at `0x18005bc37`
- `GDI32!GdiGetCharDimensions` at `0x18005bc37`

## pseudocode

```c
__int64 __fastcall xxxLBCreate(struct tagLBIV *a1, struct tagWND *a2, struct tagCREATESTRUCTW *a3)
{
  __int64 v3; // rax
  int v5; // ebx
  char *CurrentThreadDesktopWindow; // rax
  unsigned int v8; // edx
  unsigned int v9; // eax
  int v10; // ecx
  int v11; // r8d
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r9d
  unsigned int v15; // eax
  int *v17; // r14
  HDC DC; // rbx
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rcx
  HWND v22; // rcx
  WPARAM v23; // r8
  int v24; // eax
  LPARAM lParam[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v26; // [rsp+30h] [rbp-38h]

  *((_DWORD *)a1 + 23) |= 0x40000000u;
  v3 = *((_QWORD *)a2 + 6);
  v5 = *((_DWORD *)a2 + 7);
  *(_OWORD *)lParam = 0;
  v26 = 0;
  if ( v3 )
    CurrentThreadDesktopWindow = (char *)a2 + v3 - *((_QWORD *)a2 + 1);
  else
    CurrentThreadDesktopWindow = (char *)GetCurrentThreadDesktopWindow(a1, a2, a3);
  *(_QWORD *)a1 = CurrentThreadDesktopWindow;
  v8 = (4 * (v5 & 0x300000)) | ((*((_DWORD *)a1 + 23) & 0xFFFFFF73 | ~(_BYTE)v5 & 4) ^ ((v5 & 1) << 7)) & 0xFF3FFFFF;
  v9 = *((_DWORD *)a1 + 24) & 0xFFFFFFFE;
  *((_DWORD *)a1 + 23) = v8;
  v10 = v9 | (*((unsigned __int8 *)a2 + 25) >> 5) & 1;
  *((_DWORD *)a1 + 24) = v10;
  v11 = v8 & 0x7FDFFFFF | ((*((_BYTE *)a2 + 25) & 0xF0) << 27);
  *((_DWORD *)a1 + 24) = v10 | 2;
  v12 = ((v5 & 0x1000) << 9) | v11 & 0xFFDFFFFF;
  if ( (v5 & 0x4000) != 0 )
  {
    v13 = v12 & 0xFDFFFFCF | 0x2000000;
  }
  else if ( (v5 & 0x800) != 0 )
  {
    v13 = v12 & 0xFFFFFFCF | 0x20;
  }
  else
  {
    v13 = v12 & 0xFFFFFFCF | (2 * (v5 & 8));
  }
  v14 = v13 & 0xFFE5FFFF | ((v5 & 0x80) != 0 ? 0x20000 : 0) | ((v5 & 0x400 | (2 * (v5 & 0x100))) << 10);
  *((_DWORD *)a1 + 23) = v14;
  if ( (v5 & 0x80) != 0 )
  {
    LBSetTabStops(a1, 0, 0);
    v14 = *((_DWORD *)a1 + 23);
  }
  *((_DWORD *)a1 + 26) = -1;
  *((_DWORD *)a1 + 27) = -1;
  *((_DWORD *)a1 + 28) = -1;
  v15 = v14 & 0xFFFBFFFF | ((v5 & 0x200 | 0x20) << 9);
  if ( (v5 & 0x10) != 0 )
  {
    v15 = v14 & 0xFFFBFFFC | ((v5 & 0x200 | 0x20) << 9) | 1;
  }
  else if ( (v5 & 0x20) != 0 && (((v5 & 0x200 | 0x20) << 9) & 0x40000) == 0 )
  {
    v15 = v14 & 0xFFF3FFFC | ((v5 & 0x200 | 0x20) << 9) & 0xFFF7FFFC | 0x80002;
  }
  if ( (v15 & 3) != 0 && (v5 & 0x40) == 0 )
    v15 &= ~0x4000u;
  *((_DWORD *)a1 + 23) = v15 & 0xFFFFFFBF | (32 * (v5 & 2 | 0x400));
  if ( (v5 & 0x2000) != 0 )
  {
    if ( (v15 & 3) != 1 || v15 & 0x4000 | (32 * (v5 & 2)) & 0x40 )
      RtlSetLastWin32Error(0x3ECu);
    else
      *((_DWORD *)a1 + 23) = v15 & 0xFFFF7FBF | (unsigned __int8)(32 * (v5 & 2));
  }
  *((_DWORD *)a1 + 40) = GetThreadLocale();
  if ( (v5 & 0x8000) != 0 && *(_DWORD *)(*(_QWORD *)a1 + 200LL) )
    *((_QWORD *)a1 + 18) = **(_QWORD **)(*(_QWORD *)a1 + 296LL);
  *((_DWORD *)a1 + 23) |= 0x10000u;
  *((_DWORD *)a1 + 5) = -1;
  *((_QWORD *)a1 + 19) = 0;
  InitHStrings(a1);
  if ( (*((_DWORD *)a1 + 23) & 0x4000) != 0 && !*((_QWORD *)a1 + 6) )
    return 0xFFFFFFFFLL;
  v17 = (int *)((char *)a1 + 68);
  DC = (HDC)NtUserGetDC(*(_QWORD *)a2);
  *((_DWORD *)a1 + 16) = GdiGetCharDimensions(DC, 0, (LONG *)a1 + 17);
  NtUserReleaseDC(DC);
  if ( !*((_DWORD *)a1 + 16) )
  {
    v21 = *(unsigned int *)(GetDpiServerInfoForCurrentThread(v19) + 32);
    *((_DWORD *)a1 + 16) = v21;
    *v17 = *(_DWORD *)(GetDpiServerInfoForCurrentThread(v21) + 36);
  }
  v20 = *((_DWORD *)a1 + 23);
  if ( (v20 & 3) == 1 )
  {
    v22 = *(HWND *)a1;
    v23 = *((unsigned int *)a2 + 80);
    v24 = *v17;
    LODWORD(lParam[0]) = 2;
    HIDWORD(lParam[0]) = v23;
    LODWORD(v26) = v24;
    HIDWORD(lParam[1]) = 0;
    *((_QWORD *)&v26 + 1) = 0;
    if ( v22 )
      v22 = *(HWND *)v22;
    SendMessageW(v22, 0x2Cu, v23, (LPARAM)lParam);
    if ( (_DWORD)v26 )
      *v17 = v26;
    v20 = *((_DWORD *)a1 + 23);
    if ( (v20 & 0x40000) == 0 )
      goto LABEL_24;
    *((_DWORD *)a1 + 18) = HIDWORD(lParam[1]);
  }
  else if ( (v20 & 3) == 2 )
  {
    *v17 = 0;
  }
  if ( (v20 & 0x40000) != 0 )
  {
    if ( *((int *)a1 + 18) <= 0 )
      *((_DWORD *)a1 + 18) = 15 * *((_DWORD *)a1 + 16);
    *((_DWORD *)a1 + 19) = 1;
    *((_DWORD *)a1 + 20) = 1;
  }
LABEL_24:
  LBSetCItemFullMax(a1);
  if ( (*((_DWORD *)a1 + 23) & 0x80000) == 0 )
    PostMessageW(*(HWND *)a2, 5u, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x18005ba14  mov     [rsp+arg_10], rbx
0x18005ba19  push    rsi
0x18005ba1a  push    rdi
0x18005ba1b  push    r14
0x18005ba1d  sub     rsp, 50h
0x18005ba21  mov     rax, cs:__security_cookie
0x18005ba28  xor     rax, rsp
0x18005ba2b  mov     [rsp+68h+var_28], rax
0x18005ba30  bts     dword ptr [rcx+5Ch], 1Eh
0x18005ba35  xorps   xmm0, xmm0
0x18005ba38  mov     rax, [rdx+30h]
0x18005ba3c  mov     rsi, rdx
0x18005ba3f  mov     ebx, [rdx+1Ch]
0x18005ba42  mov     rdi, rcx
0x18005ba45  movups  xmmword ptr [rsp+68h+lParam], xmm0
0x18005ba4a  movups  [rsp+68h+var_38], xmm0
0x18005ba4f  test    rax, rax
0x18005ba52  jz      loc_18005BC96
0x18005ba58  sub     rax, [rdx+8]
0x18005ba5c  add     rax, rdx
0x18005ba5f  mov     [rdi], rax
0x18005ba62  mov     ecx, ebx
0x18005ba64  mov     eax, [rdi+5Ch]
0x18005ba67  not     ecx
0x18005ba69  and     eax, 0FFFFFFF3h
0x18005ba6c  and     ecx, 4
0x18005ba6f  or      ecx, eax
0x18005ba71  mov     edx, ebx
0x18005ba73  btr     ecx, 7
0x18005ba77  and     edx, 1
0x18005ba7a  shl     edx, 7
0x18005ba7d  mov     eax, ebx
0x18005ba7f  xor     edx, ecx
0x18005ba81  and     eax, 300000h
0x18005ba86  shl     eax, 2
0x18005ba89  and     edx, 0FF3FFFFFh
0x18005ba8f  or      edx, eax
0x18005ba91  mov     eax, [rdi+60h]
0x18005ba94  and     eax, 0FFFFFFFEh
0x18005ba97  mov     [rdi+5Ch], edx
0x18005ba9a  movzx   ecx, byte ptr [rsi+19h]
0x18005ba9e  and     edx, 7FDFFFFFh
0x18005baa4  shr     ecx, 5
0x18005baa7  and     ecx, 1
0x18005baaa  or      ecx, eax
0x18005baac  mov     eax, ebx
0x18005baae  mov     [rdi+60h], ecx
0x18005bab1  and     eax, 1000h
0x18005bab6  movzx   r8d, byte ptr [rsi+19h]
0x18005babb  or      ecx, 2
0x18005babe  and     r8d, 0FFFFFFF0h
0x18005bac2  shl     eax, 9
0x18005bac5  shl     r8d, 1Bh
0x18005bac9  or      r8d, edx
0x18005bacc  mov     [rdi+60h], ecx
0x18005bacf  btr     r8d, 15h
0x18005bad4  or      r8d, eax
0x18005bad7  bt      ebx, 0Eh
0x18005badb  jb      loc_18005BC11
0x18005bae1  bt      ebx, 0Bh
0x18005bae5  jb      loc_18005BCA0
0x18005baeb  mov     eax, r8d
0x18005baee  mov     ecx, ebx
0x18005baf0  and     ecx, 8
0x18005baf3  and     eax, 0FFFFFFCFh
0x18005baf6  add     ecx, ecx
0x18005baf8  mov     r8d, ecx
0x18005bafb  or      r8d, eax
0x18005bafe  mov     r9d, ebx
0x18005bb01  mov     eax, ebx
0x18005bb03  and     r9d, 100h
0x18005bb0a  and     eax, 400h
0x18005bb0f  add     r9d, r9d
0x18005bb12  mov     edx, ebx
0x18005bb14  or      r9d, eax
0x18005bb17  and     edx, 80h
0x18005bb1d  shl     r9d, 0Ah
0x18005bb21  mov     eax, edx
0x18005bb23  neg     eax
0x18005bb25  sbb     ecx, ecx
0x18005bb27  and     r8d, 0FFE5FFFFh
0x18005bb2e  and     ecx, 20000h
0x18005bb34  or      r9d, ecx
0x18005bb37  or      r9d, r8d
0x18005bb3a  mov     [rdi+5Ch], r9d
0x18005bb3e  test    edx, edx
0x18005bb40  jnz     loc_18005BCAD
0x18005bb46  or      r14d, 0FFFFFFFFh
0x18005bb4a  btr     r9d, 12h
0x18005bb4f  mov     eax, ebx
0x18005bb51  mov     [rdi+68h], r14d
0x18005bb55  and     eax, 200h
0x18005bb5a  mov     [rdi+6Ch], r14d
0x18005bb5e  or      eax, 20h
0x18005bb61  mov     [rdi+70h], r14d
0x18005bb65  shl     eax, 9
0x18005bb68  or      eax, r9d
0x18005bb6b  test    bl, 10h
0x18005bb6e  jnz     loc_18005BC06
0x18005bb74  test    bl, 20h
0x18005bb77  jnz     loc_18005BCC3
0x18005bb7d  test    al, 3
0x18005bb7f  jnz     loc_18005BCDA
0x18005bb85  and     eax, 0FFFFFFBFh
0x18005bb88  mov     ecx, ebx
0x18005bb8a  and     ecx, 2
0x18005bb8d  bts     ecx, 0Ah
0x18005bb91  shl     ecx, 5
0x18005bb94  or      ecx, eax
0x18005bb96  mov     [rdi+5Ch], ecx
0x18005bb99  bt      ebx, 0Dh
0x18005bb9d  jb      loc_18005BCEC
0x18005bba3  call    cs:__imp_GetThreadLocale
0x18005bba9  mov     [rdi+0A0h], eax
0x18005bbaf  bt      ebx, 0Fh
0x18005bbb3  jb      loc_18005BD10
0x18005bbb9  bts     dword ptr [rdi+5Ch], 10h
0x18005bbbe  mov     rcx, rdi; struct tagLBIV *
0x18005bbc1  mov     [rdi+14h], r14d
0x18005bbc5  mov     qword ptr [rdi+98h], 0
0x18005bbd0  call    ?InitHStrings@@YAXPEAUtagLBIV@@@Z; InitHStrings(tagLBIV *)
0x18005bbd5  test    dword ptr [rdi+5Ch], 4000h
0x18005bbdc  jz      short loc_18005BC1F
0x18005bbde  cmp     qword ptr [rdi+30h], 0
0x18005bbe3  jnz     short loc_18005BC1F
0x18005bbe5  mov     eax, r14d
0x18005bbe8  mov     rcx, [rsp+68h+var_28]
0x18005bbed  xor     rcx, rsp; StackCookie
0x18005bbf0  call    __security_check_cookie
0x18005bbf5  mov     rbx, [rsp+68h+arg_10]
0x18005bbfd  add     rsp, 50h
0x18005bc01  pop     r14
0x18005bc03  pop     rdi
0x18005bc04  pop     rsi
0x18005bc05  retn
0x18005bc06  and     eax, 0FFFFFFFDh
0x18005bc09  or      eax, 1
0x18005bc0c  jmp     loc_18005BB7D
0x18005bc11  and     r8d, 0FFFFFFCFh
0x18005bc15  bts     r8d, 19h
0x18005bc1a  jmp     loc_18005BAFE
0x18005bc1f  mov     rcx, [rsi]
0x18005bc22  call    cs:__imp_NtUserGetDC
0x18005bc28  lea     r14, [rdi+44h]
0x18005bc2c  xor     edx, edx; LPTEXTMETRICW
0x18005bc2e  mov     r8, r14; LONG *
0x18005bc31  mov     rcx, rax; HDC
0x18005bc34  mov     rbx, rax
0x18005bc37  call    cs:__imp_GdiGetCharDimensions
0x18005bc3d  mov     rcx, rbx
0x18005bc40  mov     [rdi+40h], eax
0x18005bc43  call    cs:__imp_NtUserReleaseDC
0x18005bc49  cmp     dword ptr [rdi+40h], 0
0x18005bc4d  jz      loc_18005BD36
0x18005bc53  mov     ecx, [rdi+5Ch]
0x18005bc56  mov     eax, ecx
0x18005bc58  and     eax, 3
0x18005bc5b  cmp     eax, 1
0x18005bc5e  jz      loc_18005BD51
0x18005bc64  cmp     eax, 2
0x18005bc67  jz      loc_18005BD8E
0x18005bc6d  bt      ecx, 12h
0x18005bc71  jb      loc_18005BD9A
0x18005bc77  mov     rcx, rdi; struct tagLBIV *
0x18005bc7a  call    ?LBSetCItemFullMax@@YAXPEAUtagLBIV@@@Z; LBSetCItemFullMax(tagLBIV *)
0x18005bc7f  test    dword ptr [rdi+5Ch], 80000h
0x18005bc86  jz      loc_18005BDB0
0x18005bc8c  mov     eax, 1
0x18005bc91  jmp     loc_18005BBE8
0x18005bc96  call    GetCurrentThreadDesktopWindow
0x18005bc9b  jmp     loc_18005BA5F
0x18005bca0  and     r8d, 0FFFFFFEFh
0x18005bca4  or      r8d, 20h
0x18005bca8  jmp     loc_18005BAFE
0x18005bcad  xor     r8d, r8d; int *
0x18005bcb0  xor     edx, edx; unsigned int
0x18005bcb2  mov     rcx, rdi; struct tagLBIV *
0x18005bcb5  call    ?LBSetTabStops@@YAHPEAUtagLBIV@@IPEAH@Z; LBSetTabStops(tagLBIV *,uint,int *)
0x18005bcba  mov     r9d, [rdi+5Ch]
0x18005bcbe  jmp     loc_18005BB46
0x18005bcc3  bt      eax, 12h
0x18005bcc7  jb      loc_18005BB7D
0x18005bccd  and     eax, 0FFFFFFFEh
0x18005bcd0  or      eax, 80002h
0x18005bcd5  jmp     loc_18005BB7D
0x18005bcda  test    bl, 40h
0x18005bcdd  jnz     loc_18005BB85
0x18005bce3  btr     eax, 0Eh
0x18005bce7  jmp     loc_18005BB85
0x18005bcec  mov     eax, ecx
0x18005bcee  and     al, 3
0x18005bcf0  cmp     al, 1
0x18005bcf2  jnz     loc_18009FDB4
0x18005bcf8  test    ecx, 4040h
0x18005bcfe  jnz     loc_18009FDB4
0x18005bd04  btr     ecx, 0Fh
0x18005bd08  mov     [rdi+5Ch], ecx
0x18005bd0b  jmp     loc_18005BBA3
0x18005bd10  mov     rax, [rdi]
0x18005bd13  cmp     dword ptr [rax+0C8h], 0
0x18005bd1a  jz      loc_18005BBB9
0x18005bd20  mov     rax, [rax+128h]
0x18005bd27  mov     rcx, [rax]
0x18005bd2a  mov     [rdi+90h], rcx
0x18005bd31  jmp     loc_18005BBB9
0x18005bd36  call    GetDpiServerInfoForCurrentThread
0x18005bd3b  mov     ecx, [rax+20h]
0x18005bd3e  mov     [rdi+40h], ecx
0x18005bd41  call    GetDpiServerInfoForCurrentThread
0x18005bd46  mov     ecx, [rax+24h]
0x18005bd49  mov     [r14], ecx
0x18005bd4c  jmp     loc_18005BC53
0x18005bd51  mov     rcx, [rdi]
0x18005bd54  mov     r8d, [rsi+140h]; wParam
0x18005bd5b  mov     eax, [r14]
0x18005bd5e  mov     dword ptr [rsp+68h+lParam], 2
0x18005bd66  mov     dword ptr [rsp+68h+lParam+4], r8d
0x18005bd6b  mov     dword ptr [rsp+68h+var_38], eax
0x18005bd6f  mov     dword ptr [rsp+68h+lParam+0Ch], 0
0x18005bd77  mov     qword ptr [rsp+68h+var_38+8], 0
0x18005bd80  test    rcx, rcx
0x18005bd83  jnz     loc_18009FDC5
0x18005bd89  jmp     loc_18009FDC8
0x18005bd8e  mov     dword ptr [r14], 0
0x18005bd95  jmp     loc_18005BC6D
0x18005bd9a  cmp     dword ptr [rdi+48h], 0
0x18005bd9e  jg      loc_18009FDFB
0x18005bda4  imul    eax, [rdi+40h], 0Fh
0x18005bda8  mov     [rdi+48h], eax
0x18005bdab  jmp     loc_18009FDFB
0x18005bdb0  mov     rcx, [rsi]; hWnd
0x18005bdb3  xor     r9d, r9d; lParam
0x18005bdb6  xor     r8d, r8d; wParam
0x18005bdb9  lea     edx, [r9+5]; Msg
0x18005bdbd  call    PostMessageW
0x18005bdc2  jmp     loc_18005BC8C
0x18009fdb4  mov     ecx, 3ECh; LastError
0x18009fdb9  call    cs:__imp_RtlSetLastWin32Error
0x18009fdbf  nop
0x18009fdc0  jmp     loc_18005BBA3
0x18009fdc5  mov     rcx, [rcx]; hWnd
0x18009fdc8  lea     r9, [rsp+68h+lParam]; lParam
0x18009fdcd  mov     edx, 2Ch ; ','; Msg
0x18009fdd2  call    SendMessageW
0x18009fdd7  mov     eax, dword ptr [rsp+68h+var_38]
0x18009fddb  test    eax, eax
0x18009fddd  jz      short loc_18009FDE2
0x18009fddf  mov     [r14], eax
0x18009fde2  mov     ecx, [rdi+5Ch]
0x18009fde5  bt      ecx, 12h
0x18009fde9  jnb     loc_18005BC77
0x18009fdef  mov     eax, dword ptr [rsp+68h+lParam+0Ch]
0x18009fdf3  mov     [rdi+48h], eax
0x18009fdf6  jmp     loc_18005BC6D
0x18009fdfb  mov     dword ptr [rdi+4Ch], 1
0x18009fe02  mov     dword ptr [rdi+50h], 1
0x18009fe09  jmp     loc_18005BC77
```
