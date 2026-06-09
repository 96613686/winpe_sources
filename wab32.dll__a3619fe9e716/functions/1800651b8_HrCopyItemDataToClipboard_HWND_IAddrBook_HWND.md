# HrCopyItemDataToClipboard(HWND__ *,IAddrBook *,HWND__ *)

- ea: `0x1800651b8`
- end: `0x1800653b4`
- name: `?HrCopyItemDataToClipboard@@YAJPEAUHWND__@@PEAUIAddrBook@@0@Z`
- size: `508`
- prototype: `int(HWND, struct IAddrBook *, HWND)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180047e90`
- `0x18005abf0`
- `0x18005ca00`
- `0x180060850`

## callees

- `0x1800045e4`
- `0x18001d778`
- `0x18001dcb8`
- `0x180033ae0`
- `0x1800651b8`
- `0x180066114`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800652a9`
- `KERNEL32!LocalAlloc` at `0x1800652a9`
- `USER32!SendMessageW` at `0x1800651ea`
- `USER32!SendMessageW` at `0x180065234`
- `USER32!SendMessageW` at `0x1800651ea`
- `USER32!SendMessageW` at `0x180065234`
- `USER32!OpenClipboard` at `0x18006535b`
- `USER32!OpenClipboard` at `0x18006535b`
- `USER32!EmptyClipboard` at `0x180065361`
- `USER32!EmptyClipboard` at `0x180065361`
- `USER32!SetClipboardData` at `0x18006536f`
- `USER32!SetClipboardData` at `0x18006537d`
- `USER32!SetClipboardData` at `0x18006536f`
- `USER32!SetClipboardData` at `0x18006537d`
- `USER32!CloseClipboard` at `0x180065383`
- `USER32!CloseClipboard` at `0x180065383`

## pseudocode

```c
__int64 __fastcall HrCopyItemDataToClipboard(HWND a1, struct IAddrBook *a2, HWND a3)
{
  struct IAddrBook *v4; // rbx
  int v5; // r15d
  unsigned __int16 *v6; // rdi
  int LVItemDataString; // esi
  int v9; // r13d
  int v10; // r14d
  int v11; // edx
  __int64 v12; // rax
  __int64 v13; // rax
  SIZE_T v14; // rbx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rbp
  unsigned __int64 v17; // rbx
  char *v18; // rbx
  void *v19[9]; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int16 *v22; // [rsp+88h] [rbp+20h] BYREF

  v4 = a2;
  v5 = SendMessageW(a3, 0x1032u, 0, 0);
  v19[0] = 0;
  v6 = 0;
  if ( v5 <= 0 )
    return 2147500037LL;
  LVItemDataString = 0;
  v9 = -1;
  v10 = 0;
  while ( LVItemDataString >= 0 )
  {
    v22 = 0;
    v9 = SendMessageW(a3, 0x100Cu, v9, 2);
    LVItemDataString = HrGetLVItemDataString(v4, a3, v9, &v22);
    if ( LVItemDataString >= 0 && v22 )
    {
      v11 = 0;
      if ( v6 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v6[v12] );
        v11 = 2 * v12 + 4;
      }
      v13 = -1;
      do
        ++v13;
      while ( v22[v13] );
      v14 = (unsigned int)(v11 + 6 + 2 * v13);
      v15 = (unsigned __int16 *)LocalAlloc(0x40u, v14);
      v16 = v15;
      if ( v15 )
      {
        v17 = v14 >> 1;
        if ( v6 )
        {
          StringCchCopyW(v15, v17, v6);
          StringCchCatW(v16, v17, L"\r\n");
        }
        StringCchCatW(v16, v17, v22);
        StringCchCatW(v16, v17, L"\r\n");
        if ( v6 )
          LocalFreeAndNull(v19);
        v6 = v16;
        v19[0] = v16;
      }
      else
      {
        LVItemDataString = -2147024882;
      }
      LocalFreeAndNull((void **)&v22);
      v4 = a2;
    }
    if ( ++v10 >= v5 )
    {
      if ( LVItemDataString >= 0 )
      {
        if ( v6 )
        {
          v18 = ConvertWtoA(v6);
          OpenClipboard(a1);
          EmptyClipboard();
          SetClipboardData(1u, v18);
          SetClipboardData(0xDu, v6);
          CloseClipboard();
        }
        return (unsigned int)LVItemDataString;
      }
      break;
    }
  }
  if ( v6 )
    LocalFreeAndNull(v19);
  return (unsigned int)LVItemDataString;
}

```

## disassembly

```asm
0x1800651b8  mov     [rsp+arg_10], rbx
0x1800651bd  mov     [rsp+arg_8], rdx
0x1800651c2  mov     [rsp+hWndNewOwner], rcx
0x1800651c7  push    rbp
0x1800651c8  push    rsi
0x1800651c9  push    rdi
0x1800651ca  push    r12
0x1800651cc  push    r13
0x1800651ce  push    r14
0x1800651d0  push    r15
0x1800651d2  sub     rsp, 30h
0x1800651d6  mov     r12, r8
0x1800651d9  mov     rbx, rdx
0x1800651dc  mov     rcx, r12; hWnd
0x1800651df  xor     r9d, r9d; lParam
0x1800651e2  xor     r8d, r8d; wParam
0x1800651e5  mov     edx, 1032h; Msg
0x1800651ea  call    cs:__imp_SendMessageW
0x1800651f0  xor     ebp, ebp
0x1800651f2  mov     r15, rax
0x1800651f5  mov     [rsp+68h+var_48], rbp
0x1800651fa  mov     edi, ebp
0x1800651fc  test    eax, eax
0x1800651fe  jg      short loc_18006520A
0x180065200  mov     eax, 80004005h
0x180065205  jmp     loc_18006539C
0x18006520a  mov     esi, ebp
0x18006520c  or      r13d, 0FFFFFFFFh
0x180065210  mov     r14d, ebp
0x180065213  test    esi, esi
0x180065215  js      loc_18006538B
0x18006521b  movsxd  r8, r13d; wParam
0x18006521e  mov     edx, 100Ch; Msg
0x180065223  mov     r9d, 2; lParam
0x180065229  mov     [rsp+68h+arg_18], rbp
0x180065231  mov     rcx, r12; hWnd
0x180065234  call    cs:__imp_SendMessageW
0x18006523a  lea     r9, [rsp+68h+arg_18]; unsigned __int16 **
0x180065242  mov     rdx, r12; hWnd
0x180065245  mov     r8d, eax; int
0x180065248  mov     rcx, rbx; struct IAddrBook *
0x18006524b  mov     r13, rax
0x18006524e  call    ?HrGetLVItemDataString@@YAJPEAUIAddrBook@@PEAUHWND__@@HPEAPEAG@Z; HrGetLVItemDataString(IAddrBook *,HWND__ *,int,ushort * *)
0x180065253  mov     esi, eax
0x180065255  test    eax, eax
0x180065257  js      loc_180065336
0x18006525d  mov     rcx, [rsp+68h+arg_18]
0x180065265  test    rcx, rcx
0x180065268  jz      loc_180065336
0x18006526e  mov     rdx, rbp
0x180065271  test    rdi, rdi
0x180065274  jz      short loc_18006528B
0x180065276  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006527a  inc     rax
0x18006527d  cmp     [rdi+rax*2], bp
0x180065281  jnz     short loc_18006527A
0x180065283  lea     rdx, ds:4[rax*2]
0x18006528b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006528f  inc     rax
0x180065292  cmp     [rcx+rax*2], bp
0x180065296  jnz     short loc_18006528F
0x180065298  add     rdx, 6
0x18006529c  mov     ecx, 40h ; '@'; uFlags
0x1800652a1  lea     rax, [rdx+rax*2]
0x1800652a5  mov     edx, eax; uBytes
0x1800652a7  mov     ebx, eax
0x1800652a9  call    cs:__imp_LocalAlloc
0x1800652af  mov     rbp, rax
0x1800652b2  test    rax, rax
0x1800652b5  jz      short loc_18006531D
0x1800652b7  shr     rbx, 1
0x1800652ba  test    rdi, rdi
0x1800652bd  jz      short loc_1800652DF
0x1800652bf  mov     r8, rdi; unsigned __int16 *
0x1800652c2  mov     rdx, rbx; unsigned __int64
0x1800652c5  mov     rcx, rax; unsigned __int16 *
0x1800652c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800652cd  lea     r8, lParam; "\r\n"
0x1800652d4  mov     rdx, rbx; unsigned __int64
0x1800652d7  mov     rcx, rbp; unsigned __int16 *
0x1800652da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800652df  mov     r8, [rsp+68h+arg_18]; unsigned __int16 *
0x1800652e7  mov     rdx, rbx; unsigned __int64
0x1800652ea  mov     rcx, rbp; unsigned __int16 *
0x1800652ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800652f2  lea     r8, lParam; "\r\n"
0x1800652f9  mov     rdx, rbx; unsigned __int64
0x1800652fc  mov     rcx, rbp; unsigned __int16 *
0x1800652ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180065304  test    rdi, rdi
0x180065307  jz      short loc_180065313
0x180065309  lea     rcx, [rsp+68h+var_48]; void **
0x18006530e  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180065313  mov     rdi, rbp
0x180065316  mov     [rsp+68h+var_48], rbp
0x18006531b  jmp     short loc_180065322
0x18006531d  mov     esi, 8007000Eh
0x180065322  lea     rcx, [rsp+68h+arg_18]; void **
0x18006532a  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x18006532f  mov     rbx, [rsp+68h+arg_8]
0x180065334  xor     ebp, ebp
0x180065336  inc     r14d
0x180065339  cmp     r14d, r15d
0x18006533c  jl      loc_180065213
0x180065342  test    esi, esi
0x180065344  js      short loc_18006538B
0x180065346  test    rdi, rdi
0x180065349  jz      short loc_18006539A
0x18006534b  mov     rcx, rdi; lpWideCharStr
0x18006534e  call    ?ConvertWtoA@@YAPEADPEBG@Z; ConvertWtoA(ushort const *)
0x180065353  mov     rcx, [rsp+68h+hWndNewOwner]; hWndNewOwner
0x180065358  mov     rbx, rax
0x18006535b  call    cs:__imp_OpenClipboard
0x180065361  call    cs:__imp_EmptyClipboard
0x180065367  mov     rdx, rbx; hMem
0x18006536a  mov     ecx, 1; uFormat
0x18006536f  call    cs:__imp_SetClipboardData
0x180065375  mov     rdx, rdi; hMem
0x180065378  mov     ecx, 0Dh; uFormat
0x18006537d  call    cs:__imp_SetClipboardData
0x180065383  call    cs:__imp_CloseClipboard
0x180065389  jmp     short loc_18006539A
0x18006538b  test    rdi, rdi
0x18006538e  jz      short loc_18006539A
0x180065390  lea     rcx, [rsp+68h+var_48]; void **
0x180065395  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x18006539a  mov     eax, esi
0x18006539c  mov     rbx, [rsp+68h+arg_10]
0x1800653a4  add     rsp, 30h
0x1800653a8  pop     r15
0x1800653aa  pop     r14
0x1800653ac  pop     r13
0x1800653ae  pop     r12
0x1800653b0  pop     rdi
0x1800653b1  pop     rsi
0x1800653b2  pop     rbp
0x1800653b3  retn
```
