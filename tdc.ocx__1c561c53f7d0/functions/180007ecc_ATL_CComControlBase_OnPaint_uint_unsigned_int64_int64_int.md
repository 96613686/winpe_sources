# ATL::CComControlBase::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x180007ecc`
- end: `0x180007fc9`
- name: `?OnPaint@CComControlBase@ATL@@QEAA_JI_K_JAEAH@Z`
- size: `253`
- prototype: `__int64 __fastcall(ATL::CComControlBase *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008360`

## callees

- `0x180007ecc`
- `0x18001423e`
- `0x180014270`
- `0x180015010`

## import_xrefs

- `USER32!BeginPaint` at `0x180007f28`
- `USER32!BeginPaint` at `0x180007f28`
- `USER32!GetClientRect` at `0x180007f40`
- `USER32!GetClientRect` at `0x180007f40`
- `USER32!EndPaint` at `0x180007f9d`
- `USER32!EndPaint` at `0x180007f9d`

## pseudocode

```c
__int64 __fastcall ATL::CComControlBase::OnPaint(ATL::CComControlBase *this, __int64 a2, HDC a3)
{
  HWND **v5; // rbx
  HDC v6; // rdi
  __int64 v7; // rax
  _DWORD v9[8]; // [rsp+20h] [rbp-91h] BYREF
  HDC v10; // [rsp+40h] [rbp-71h]
  struct tagRECT *p_Rect; // [rsp+48h] [rbp-69h]
  struct tagRECT Rect; // [rsp+80h] [rbp-31h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+90h] [rbp-21h] BYREF

  Rect = 0;
  memset_0(&Paint, 0, sizeof(Paint));
  v5 = (HWND **)((char *)this + 88);
  if ( a3 )
  {
    v6 = a3;
  }
  else
  {
    v6 = BeginPaint(**v5, &Paint);
    if ( !v6 )
      return 0;
  }
  GetClientRect(**v5, &Rect);
  memset_0(v9, 0, 0x58u);
  v9[0] = 88;
  p_Rect = &Rect;
  v7 = *(_QWORD *)this;
  v9[1] = 1;
  v9[2] = -1;
  v10 = v6;
  (*(void (__fastcall **)(ATL::CComControlBase *, _DWORD *))(v7 + 24))(this, v9);
  if ( !a3 )
    EndPaint(**v5, &Paint);
  return 0;
}

```

## disassembly

```asm
0x180007ecc  mov     [rsp-8+arg_8], rbx
0x180007ed1  mov     [rsp-8+arg_18], rsi
0x180007ed6  push    rbp
0x180007ed7  push    rdi
0x180007ed8  push    r14
0x180007eda  lea     rbp, [rsp-3Fh]
0x180007edf  sub     rsp, 0F0h
0x180007ee6  mov     rax, cs:__security_cookie
0x180007eed  xor     rax, rsp
0x180007ef0  mov     [rbp+4Fh+var_20], rax
0x180007ef4  xor     edx, edx; Val
0x180007ef6  mov     rsi, r8
0x180007ef9  mov     r14, rcx
0x180007efc  xorps   xmm0, xmm0
0x180007eff  lea     rcx, [rbp+4Fh+Paint]; void *
0x180007f03  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x180007f07  lea     r8d, [rdx+48h]; Size
0x180007f0b  call    memset_0
0x180007f10  lea     rbx, [r14+58h]
0x180007f14  test    rsi, rsi
0x180007f17  jz      short loc_180007F1E
0x180007f19  mov     rdi, rsi
0x180007f1c  jmp     short loc_180007F36
0x180007f1e  mov     rcx, [rbx]
0x180007f21  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x180007f25  mov     rcx, [rcx]; hWnd
0x180007f28  call    cs:__imp_BeginPaint
0x180007f2e  mov     rdi, rax
0x180007f31  test    rax, rax
0x180007f34  jz      short loc_180007FA3
0x180007f36  mov     rcx, [rbx]
0x180007f39  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x180007f3d  mov     rcx, [rcx]; hWnd
0x180007f40  call    cs:__imp_GetClientRect
0x180007f46  xor     edx, edx; Val
0x180007f48  lea     rcx, [rsp+100h+var_E0]; void *
0x180007f4d  lea     r8d, [rdx+58h]; Size
0x180007f51  call    memset_0
0x180007f56  lea     rax, [rbp+4Fh+Rect]
0x180007f5a  mov     [rsp+100h+var_E0], 58h ; 'X'
0x180007f62  mov     [rbp+4Fh+var_B8], rax
0x180007f66  lea     rdx, [rsp+100h+var_E0]
0x180007f6b  mov     rax, [r14]
0x180007f6e  mov     rcx, r14
0x180007f71  mov     [rsp+100h+var_DC], 1
0x180007f79  mov     [rsp+100h+var_D8], 0FFFFFFFFh
0x180007f81  mov     [rbp+4Fh+var_C0], rdi
0x180007f85  mov     rax, [rax+18h]
0x180007f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f8e  test    rsi, rsi
0x180007f91  jnz     short loc_180007FA3
0x180007f93  mov     rcx, [rbx]
0x180007f96  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x180007f9a  mov     rcx, [rcx]; hWnd
0x180007f9d  call    cs:__imp_EndPaint
0x180007fa3  xor     eax, eax
0x180007fa5  mov     rcx, [rbp+4Fh+var_20]
0x180007fa9  xor     rcx, rsp; StackCookie
0x180007fac  call    __security_check_cookie
0x180007fb1  lea     r11, [rsp+100h+var_10]
0x180007fb9  mov     rbx, [r11+28h]
0x180007fbd  mov     rsi, [r11+38h]
0x180007fc1  mov     rsp, r11
0x180007fc4  pop     r14
0x180007fc6  pop     rdi
0x180007fc7  pop     rbp
0x180007fc8  retn
```
