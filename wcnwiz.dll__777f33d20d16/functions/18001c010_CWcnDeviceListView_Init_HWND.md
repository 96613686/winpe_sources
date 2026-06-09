# CWcnDeviceListView::Init(HWND__ *)

- ea: `0x18001c010`
- end: `0x18001c390`
- name: `?Init@CWcnDeviceListView@@QEAAJPEAUHWND__@@@Z`
- size: `896`
- prototype: `int(CWcnDeviceListView *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000eec4`

## callees

- `0x180001820`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x180011920`
- `0x180011a14`
- `0x18001c010`
- `0x18001cd90`
- `0x18002de1c`
- `0x18002e284`

## import_xrefs

- `USER32!ShowWindow` at `0x18001c308`
- `USER32!ShowWindow` at `0x18001c308`
- `USER32!SendMessageW` at `0x18001c0e8`
- `USER32!SendMessageW` at `0x18001c158`
- `USER32!SendMessageW` at `0x18001c195`
- `USER32!SendMessageW` at `0x18001c1ab`
- `USER32!SendMessageW` at `0x18001c2e1`
- `USER32!SendMessageW` at `0x18001c2fb`
- `USER32!SendMessageW` at `0x18001c0e8`
- `USER32!SendMessageW` at `0x18001c158`
- `USER32!SendMessageW` at `0x18001c195`
- `USER32!SendMessageW` at `0x18001c1ab`
- `USER32!SendMessageW` at `0x18001c2e1`
- `USER32!SendMessageW` at `0x18001c2fb`
- `USER32!GetSystemMetrics` at `0x18001c171`
- `USER32!GetSystemMetrics` at `0x18001c1b6`
- `USER32!GetSystemMetrics` at `0x18001c1c3`
- `USER32!GetSystemMetrics` at `0x18001c171`
- `USER32!GetSystemMetrics` at `0x18001c1b6`
- `USER32!GetSystemMetrics` at `0x18001c1c3`
- `USER32!GetClientRect` at `0x18001c0a8`
- `USER32!GetClientRect` at `0x18001c0a8`
- `GDI32!DeleteObject` at `0x18001c31d`
- `GDI32!DeleteObject` at `0x18001c31d`
- `UxTheme!SetWindowTheme` at `0x18001c140`
- `UxTheme!SetWindowTheme` at `0x18001c140`

## pseudocode

```c
__int64 __fastcall CWcnDeviceListView::Init(CWcnDeviceListView *this, HWND a2)
{
  const char *Indent; // rax
  __int64 v5; // r10
  int v6; // ebx
  HWND v7; // rcx
  unsigned int v8; // ebx
  _BYTE *v9; // r10
  const char *v10; // rax
  __int64 v11; // r10
  __int64 v12; // rdx
  int v13; // ebx
  int SystemMetrics; // eax
  HWND v15; // rcx
  int v16; // ebx
  int v17; // eax
  LPARAM v18; // rsi
  int ImageScaled; // eax
  HGDIOBJ v20; // r14
  const char *v21; // rax
  __int64 v22; // r10
  unsigned int v23; // eax
  __int64 v24; // r10
  HGDIOBJ ho; // [rsp+30h] [rbp-69h] BYREF
  LPARAM lParam[2]; // [rsp+38h] [rbp-61h] BYREF
  __int128 v28; // [rsp+48h] [rbp-51h]
  __int128 v29; // [rsp+58h] [rbp-41h]
  __int64 v30; // [rsp+68h] [rbp-31h]
  struct tagRECT Rect; // [rsp+70h] [rbp-29h] BYREF
  _DWORD v32[5]; // [rsp+80h] [rbp-19h] BYREF
  __int128 v33; // [rsp+94h] [rbp-5h]
  int v34; // [rsp+A4h] [rbp+Bh]

  ho = 0;
  v32[0] = 40;
  Rect = 0;
  v34 = 0;
  *(_OWORD *)&v32[1] = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 23, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids, Indent);
  }
  *((_QWORD *)this + 2) = a2;
  GetClientRect(a2, &Rect);
  *(_OWORD *)lParam = 0;
  v30 = 0;
  v6 = 0;
  v28 = 0;
  LODWORD(lParam[0]) = 8;
  v29 = 0;
  while ( 1 )
  {
    v7 = (HWND)*((_QWORD *)this + 2);
    if ( v6 >= 2 )
    {
      SetWindowTheme(v7, L"Explorer", 0);
      SendMessageW(*((HWND *)this + 2), 0x1036u, 0x10020u, 65568);
      v13 = Rect.right - Rect.left;
      *(_QWORD *)&v32[1] = 0x100000003LL;
      SystemMetrics = GetSystemMetrics(2);
      v15 = (HWND)*((_QWORD *)this + 2);
      LODWORD(v33) = 1;
      v32[3] = (v13 - SystemMetrics) / 2;
      SendMessageW(v15, 0x10A2u, 0, (LPARAM)v32);
      SendMessageW(*((HWND *)this + 2), 0x108Eu, 4u, 0);
      v16 = GetSystemMetrics(11);
      v17 = GetSystemMetrics(12);
      v18 = IsolationAwareImageList_Create(v16, v17, 32, 1, 0);
      if ( !v18 )
      {
        v8 = -2147024882;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v8;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_31;
        v10 = GetIndent(0);
        v12 = 25;
LABEL_11:
        WPP_SF_s(*(_QWORD *)(v11 + 16), v12, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids, v10);
LABEL_30:
        v9 = WPP_GLOBAL_Control;
        goto LABEL_31;
      }
      ImageScaled = LoadImageScaled(hModule, (unsigned __int16 *)0x2A35, (HBITMAP *)&ho);
      v20 = ho;
      v8 = ImageScaled;
      if ( ImageScaled >= 0 )
      {
        if ( (unsigned int)IsolationAwareImageList_Add(v18, ho) == -1 )
        {
          v8 = -2147418113;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_26;
          v21 = GetIndent(0);
          WPP_SF_s(*(_QWORD *)(v22 + 16), 27, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids, v21);
        }
        else
        {
          SendMessageW(*((HWND *)this + 2), 0x1003u, 0, v18);
          v18 = 0;
          SendMessageW(*((HWND *)this + 2), 0x1036u, 0, 1056);
          ShowWindow(*((HWND *)this + 2), 5);
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_26;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids,
          (unsigned int)ImageScaled);
      }
      v9 = WPP_GLOBAL_Control;
LABEL_26:
      if ( v20 )
      {
        DeleteObject(v20);
        v9 = WPP_GLOBAL_Control;
      }
      if ( !v18 )
        goto LABEL_31;
      IsolationAwareImageList_Destroy(v18);
      goto LABEL_30;
    }
    HIDWORD(v28) = v6;
    if ( (unsigned int)SendMessageW(v7, 0x1061u, v6, (LPARAM)lParam) == -1 )
      break;
    ++v6;
  }
  v8 = -2147418113;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v8;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = GetIndent(0);
    v12 = 24;
    goto LABEL_11;
  }
LABEL_31:
  if ( v9 != (_BYTE *)&WPP_GLOBAL_Control && ((v8 & 0x80000000) != 0 || v9[25] >= 6u) )
  {
    v23 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v24 + 16), 28, (unsigned int)WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids, v23, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x18001c010  push    rbp
0x18001c012  push    rbx
0x18001c013  push    rsi
0x18001c014  push    rdi
0x18001c015  push    r12
0x18001c017  push    r13
0x18001c019  push    r14
0x18001c01b  push    r15
0x18001c01d  lea     rbp, [rsp-1Fh]
0x18001c022  sub     rsp, 0B8h
0x18001c029  mov     rax, cs:__security_cookie
0x18001c030  xor     rax, rsp
0x18001c033  mov     [rbp+57h+var_48], rax
0x18001c037  xorps   xmm0, xmm0
0x18001c03a  mov     [rbp+57h+ho], 0
0x18001c042  xor     eax, eax
0x18001c044  mov     dword ptr [rbp+57h+var_70], 28h ; '('
0x18001c04b  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18001c04f  mov     [rbp+57h+var_4C], eax
0x18001c052  mov     rbx, rdx
0x18001c055  movups  xmmword ptr [rbp+57h+var_70+4], xmm0
0x18001c059  mov     rdi, rcx
0x18001c05c  movups  [rbp+57h+var_5C], xmm0
0x18001c060  mov     r10, cs:WPP_GLOBAL_Control
0x18001c067  lea     r15, WPP_GLOBAL_Control
0x18001c06e  lea     esi, [rax+1]
0x18001c071  lea     r13, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids
0x18001c078  cmp     r10, r15
0x18001c07b  jz      short loc_18001C09D
0x18001c07d  cmp     byte ptr [r10+19h], 6
0x18001c082  jb      short loc_18001C09D
0x18001c084  mov     ecx, esi; int
0x18001c086  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001c08b  mov     rcx, [r10+10h]
0x18001c08f  lea     edx, [rsi+16h]
0x18001c092  mov     r9, rax
0x18001c095  mov     r8, r13
0x18001c098  call    WPP_SF_s
0x18001c09d  lea     rdx, [rbp+57h+Rect]; lpRect
0x18001c0a1  mov     [rdi+10h], rbx
0x18001c0a5  mov     rcx, rbx; hWnd
0x18001c0a8  call    cs:__imp_GetClientRect
0x18001c0ae  xor     eax, eax
0x18001c0b0  xorps   xmm0, xmm0
0x18001c0b3  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x18001c0b7  mov     [rbp+57h+var_88], rax
0x18001c0bb  xor     ebx, ebx
0x18001c0bd  movups  [rbp+57h+var_A8], xmm0
0x18001c0c1  lea     r12d, [rax+2]
0x18001c0c5  mov     dword ptr [rbp+57h+lParam], 8
0x18001c0cc  movups  [rbp+57h+var_98], xmm0
0x18001c0d0  mov     rcx, [rdi+10h]; hwnd
0x18001c0d4  cmp     ebx, r12d
0x18001c0d7  jge     short loc_18001C136
0x18001c0d9  movsxd  r8, ebx; wParam
0x18001c0dc  lea     r9, [rbp+57h+lParam]; lParam
0x18001c0e0  mov     edx, 1061h; Msg
0x18001c0e5  mov     dword ptr [rbp+57h+var_A8+0Ch], ebx
0x18001c0e8  call    cs:__imp_SendMessageW
0x18001c0ee  cmp     eax, 0FFFFFFFFh
0x18001c0f1  jz      short loc_18001C0F7
0x18001c0f3  add     ebx, esi
0x18001c0f5  jmp     short loc_18001C0D0
0x18001c0f7  mov     ebx, 8000FFFFh
0x18001c0fc  mov     r10, cs:WPP_GLOBAL_Control
0x18001c103  cmp     r10, r15
0x18001c106  jz      loc_18001C36E
0x18001c10c  cmp     [r10+19h], r12b
0x18001c110  jb      loc_18001C33E
0x18001c116  xor     ecx, ecx; int
0x18001c118  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001c11d  mov     edx, 18h
0x18001c122  mov     rcx, [r10+10h]
0x18001c126  mov     r9, rax
0x18001c129  mov     r8, r13
0x18001c12c  call    WPP_SF_s
0x18001c131  jmp     loc_18001C337
0x18001c136  xor     r8d, r8d; pszSubIdList
0x18001c139  lea     rdx, pszSubAppName; "Explorer"
0x18001c140  call    cs:__imp_SetWindowTheme
0x18001c146  mov     rcx, [rdi+10h]; hWnd
0x18001c14a  mov     r8d, 10020h; wParam
0x18001c150  mov     r9d, r8d; lParam
0x18001c153  mov     edx, 1036h; Msg
0x18001c158  call    cs:__imp_SendMessageW
0x18001c15e  mov     ebx, [rbp+57h+Rect.right]
0x18001c161  mov     ecx, r12d; nIndex
0x18001c164  sub     ebx, [rbp+57h+Rect.left]
0x18001c167  mov     dword ptr [rbp+57h+var_70+4], 3
0x18001c16e  mov     dword ptr [rbp+57h+var_70+8], esi
0x18001c171  call    cs:__imp_GetSystemMetrics
0x18001c177  mov     rcx, [rdi+10h]; hWnd
0x18001c17b  lea     r9, [rbp+57h+var_70]; lParam
0x18001c17f  sub     ebx, eax
0x18001c181  mov     dword ptr [rbp+57h+var_5C], esi
0x18001c184  mov     eax, ebx
0x18001c186  xor     r8d, r8d; wParam
0x18001c189  cdq
0x18001c18a  idiv    r12d
0x18001c18d  mov     edx, 10A2h; Msg
0x18001c192  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x18001c195  call    cs:__imp_SendMessageW
0x18001c19b  mov     rcx, [rdi+10h]; hWnd
0x18001c19f  xor     r9d, r9d; lParam
0x18001c1a2  mov     edx, 108Eh; Msg
0x18001c1a7  lea     r8d, [r9+4]; wParam
0x18001c1ab  call    cs:__imp_SendMessageW
0x18001c1b1  mov     ecx, 0Bh; nIndex
0x18001c1b6  call    cs:__imp_GetSystemMetrics
0x18001c1bc  mov     ecx, 0Ch; nIndex
0x18001c1c1  mov     ebx, eax
0x18001c1c3  call    cs:__imp_GetSystemMetrics
0x18001c1c9  mov     r9d, esi
0x18001c1cc  mov     dword ptr [rsp+0F0h+var_D0], 0
0x18001c1d4  mov     edx, eax
0x18001c1d6  mov     r8d, 20h ; ' '
0x18001c1dc  mov     ecx, ebx
0x18001c1de  mov     r14d, eax
0x18001c1e1  call    IsolationAwareImageList_Create
0x18001c1e6  mov     rsi, rax
0x18001c1e9  test    rax, rax
0x18001c1ec  jnz     short loc_18001C21C
0x18001c1ee  mov     ebx, 8007000Eh
0x18001c1f3  mov     r10, cs:WPP_GLOBAL_Control
0x18001c1fa  cmp     r10, r15
0x18001c1fd  jz      loc_18001C36E
0x18001c203  cmp     [r10+19h], r12b
0x18001c207  jb      loc_18001C33E
0x18001c20d  xor     ecx, ecx; int
0x18001c20f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001c214  lea     edx, [rsi+19h]
0x18001c217  jmp     loc_18001C122
0x18001c21c  mov     rcx, cs:hModule; HINSTANCE
0x18001c223  lea     edx, [r14+r14*2]
0x18001c227  shl     edx, 5
0x18001c22a  mov     eax, 38E38E39h
0x18001c22f  imul    edx
0x18001c231  lea     rax, [rbp+57h+ho]
0x18001c235  sar     edx, 4
0x18001c238  mov     r8d, edx
0x18001c23b  mov     [rsp+0F0h+var_D0], rax; HBITMAP *
0x18001c240  shr     r8d, 1Fh
0x18001c244  add     r8d, edx
0x18001c247  mov     edx, 2A35h; unsigned __int16 *
0x18001c24c  call    LoadImageScaled
0x18001c251  mov     r14, [rbp+57h+ho]
0x18001c255  mov     ebx, eax
0x18001c257  test    eax, eax
0x18001c259  jns     short loc_18001C28E
0x18001c25b  mov     r10, cs:WPP_GLOBAL_Control
0x18001c262  cmp     r10, r15
0x18001c265  jz      loc_18001C315
0x18001c26b  cmp     [r10+19h], r12b
0x18001c26f  jb      loc_18001C315
0x18001c275  mov     rcx, [r10+10h]
0x18001c279  mov     edx, 1Ah
0x18001c27e  mov     r9d, eax
0x18001c281  mov     r8, r13
0x18001c284  call    WPP_SF_d
0x18001c289  jmp     loc_18001C30E
0x18001c28e  mov     rdx, r14
0x18001c291  mov     rcx, rsi
0x18001c294  call    IsolationAwareImageList_Add
0x18001c299  cmp     eax, 0FFFFFFFFh
0x18001c29c  jnz     short loc_18001C2D2
0x18001c29e  mov     ebx, 8000FFFFh
0x18001c2a3  mov     r10, cs:WPP_GLOBAL_Control
0x18001c2aa  cmp     r10, r15
0x18001c2ad  jz      short loc_18001C315
0x18001c2af  cmp     [r10+19h], r12b
0x18001c2b3  jb      short loc_18001C315
0x18001c2b5  xor     ecx, ecx; int
0x18001c2b7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001c2bc  mov     rcx, [r10+10h]
0x18001c2c0  mov     edx, 1Bh
0x18001c2c5  mov     r9, rax
0x18001c2c8  mov     r8, r13
0x18001c2cb  call    WPP_SF_s
0x18001c2d0  jmp     short loc_18001C30E
0x18001c2d2  mov     rcx, [rdi+10h]; hWnd
0x18001c2d6  mov     r9, rsi; lParam
0x18001c2d9  xor     r8d, r8d; wParam
0x18001c2dc  mov     edx, 1003h; Msg
0x18001c2e1  call    cs:__imp_SendMessageW
0x18001c2e7  mov     rcx, [rdi+10h]; hWnd
0x18001c2eb  mov     r9d, 420h; lParam
0x18001c2f1  xor     r8d, r8d; wParam
0x18001c2f4  mov     edx, 1036h; Msg
0x18001c2f9  xor     esi, esi
0x18001c2fb  call    cs:__imp_SendMessageW
0x18001c301  mov     rcx, [rdi+10h]; hWnd
0x18001c305  lea     edx, [rsi+5]; nCmdShow
0x18001c308  call    cs:__imp_ShowWindow
0x18001c30e  mov     r10, cs:WPP_GLOBAL_Control
0x18001c315  test    r14, r14
0x18001c318  jz      short loc_18001C32A
0x18001c31a  mov     rcx, r14; ho
0x18001c31d  call    cs:__imp_DeleteObject
0x18001c323  mov     r10, cs:WPP_GLOBAL_Control
0x18001c32a  test    rsi, rsi
0x18001c32d  jz      short loc_18001C33E
0x18001c32f  mov     rcx, rsi
0x18001c332  call    IsolationAwareImageList_Destroy
0x18001c337  mov     r10, cs:WPP_GLOBAL_Control
0x18001c33e  cmp     r10, r15
0x18001c341  jz      short loc_18001C36E
0x18001c343  test    ebx, ebx
0x18001c345  js      short loc_18001C34E
0x18001c347  cmp     byte ptr [r10+19h], 6
0x18001c34c  jb      short loc_18001C36E
0x18001c34e  or      ecx, 0FFFFFFFFh; int
0x18001c351  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001c356  mov     rcx, [r10+10h]
0x18001c35a  mov     edx, 1Ch
0x18001c35f  mov     r9, rax
0x18001c362  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18001c366  mov     r8, r13
0x18001c369  call    WPP_SF_sd
0x18001c36e  mov     eax, ebx
0x18001c370  mov     rcx, [rbp+57h+var_48]
0x18001c374  xor     rcx, rsp; StackCookie
0x18001c377  call    __security_check_cookie
0x18001c37c  add     rsp, 0B8h
0x18001c383  pop     r15
0x18001c385  pop     r14
0x18001c387  pop     r13
0x18001c389  pop     r12
0x18001c38b  pop     rdi
0x18001c38c  pop     rsi
0x18001c38d  pop     rbx
0x18001c38e  pop     rbp
0x18001c38f  retn
```
