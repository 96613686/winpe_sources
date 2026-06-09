# Windows::Internal::DockedCharmWindowTrait::CreatePopupWindow(ulong,ushort const *,ulong,HWND__ *,HMONITOR__ *,POPUP_OPTIONS)

- ea: `0x1800a33b8`
- end: `0x1800a3595`
- name: `?CreatePopupWindow@DockedCharmWindowTrait@Internal@Windows@@QEAAPEAUHWND__@@KPEBGKPEAU4@PEAUHMONITOR__@@W4POPUP_OPTIONS@@@Z`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18009ced0`

## callees

- `0x180030d44`
- `0x18004bba4`
- `0x180054ad4`
- `0x18009db00`
- `0x1800a33b8`

## import_xrefs

- `USER32!CreateWindowInBandEx` at `0x1800a34f9`
- `USER32!CreateWindowInBandEx` at `0x1800a34f9`
- `USER32!RegisterClassW` at `0x1800a3441`
- `USER32!RegisterClassW` at `0x1800a3441`
- `USER32!LoadCursorW` at `0x1800a341a`
- `USER32!LoadCursorW` at `0x1800a341a`
- `USER32!SendMessageW` at `0x1800a3569`
- `USER32!SendMessageW` at `0x1800a3569`
- `USER32!SetWindowCompositionAttribute` at `0x1800a354c`
- `USER32!SetWindowCompositionAttribute` at `0x1800a354c`

## pseudocode

```c
HWND __fastcall Windows::Internal::DockedCharmWindowTrait::CreatePopupWindow(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        HMONITOR a6,
        int a7)
{
  unsigned int v11; // esi
  int v12; // edx
  int v13; // eax
  int v14; // ecx
  HWND WindowInBand; // rax
  HWND v16; // rbx
  __int64 v18; // [rsp+70h] [rbp-51h] BYREF
  int *v19; // [rsp+78h] [rbp-49h]
  __int64 v20; // [rsp+80h] [rbp-41h]
  WNDCLASSW WndClass; // [rsp+90h] [rbp-31h] BYREF
  enum DEVICE_SCALE_FACTOR v22; // [rsp+110h] [rbp+4Fh] BYREF

  *(_DWORD *)(a1 + 8) = a7;
  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.style = 520;
  WndClass.lpfnWndProc = (WNDPROC)NoUIAWindowProc;
  WndClass.hInstance = &_ImageBase;
  WndClass.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  WndClass.hbrBackground = (HBRUSH)6;
  WndClass.lpszClassName = L"Shell_CharmWindow";
  RegisterClassW(&WndClass);
  v11 = a2 & 0xFFDFFFFF;
  if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
    v11 = a2;
  DUIGetScaleFactorForMonitor(a6);
  v18 = (__int64)&Windows::Internal::CharmWindowPositionTrait::`vftable';
  LODWORD(v19) = *(_DWORD *)(a1 + 12);
  v12 = *(_DWORD *)Windows::Internal::CharmWindowPositionTrait::MaxSize(
                     (Windows::Internal::CharmWindowPositionTrait *)&v18,
                     (enum DEVICE_SCALE_FACTOR)&v22).cx;
  *(_QWORD *)(a1 + 32) = a5;
  if ( (*(_BYTE *)(a1 + 8) & 4) != 0 )
  {
    v13 = 0;
    v14 = 1;
  }
  else
  {
    v13 = 1;
    v14 = 13;
  }
  WindowInBand = (HWND)CreateWindowInBandEx(
                         v11,
                         L"Shell_CharmWindow",
                         a3,
                         a4,
                         0x80000000,
                         0x80000000,
                         v12,
                         600,
                         0,
                         0,
                         &_ImageBase,
                         0,
                         v14,
                         v13);
  v16 = WindowInBand;
  if ( WindowInBand )
  {
    if ( (*(_DWORD *)(a1 + 8) & 0x4000) != 0 )
      SetIhmRequireTouchInEditField(1, WindowInBand);
    if ( (*(_BYTE *)(a1 + 8) & 4) != 0 )
    {
      a7 = 1;
      v18 = 17;
      v19 = &a7;
      v20 = 4;
      SetWindowCompositionAttribute(v16, &v18);
    }
    SendMessageW(v16, 0x127u, 0x30001u, 0);
  }
  return v16;
}

```

## disassembly

```asm
0x1800a33b8  mov     [rsp-8+arg_8], rbx
0x1800a33bd  mov     [rsp-8+arg_10], rsi
0x1800a33c2  push    rbp
0x1800a33c3  push    rdi
0x1800a33c4  push    r13
0x1800a33c6  push    r14
0x1800a33c8  push    r15
0x1800a33ca  lea     rbp, [rsp-1Fh]
0x1800a33cf  sub     rsp, 0E0h
0x1800a33d6  mov     r14d, r9d
0x1800a33d9  mov     r15, r8
0x1800a33dc  mov     ebx, edx
0x1800a33de  mov     rdi, rcx
0x1800a33e1  mov     eax, [rbp+3Fh+arg_30]
0x1800a33e4  mov     [rcx+8], eax
0x1800a33e7  xor     edx, edx; Val
0x1800a33e9  lea     r8d, [rdx+48h]; Size
0x1800a33ed  lea     rcx, [rbp+3Fh+WndClass]; void *
0x1800a33f1  call    memset_0
0x1800a33f6  mov     [rbp+3Fh+WndClass.style], 208h
0x1800a33fd  lea     rax, ?NoUIAWindowProc@@YA_JPEAUHWND__@@I_K_J@Z; NoUIAWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800a3404  mov     [rbp+3Fh+WndClass.lpfnWndProc], rax
0x1800a3408  lea     rax, __ImageBase
0x1800a340f  mov     [rbp+3Fh+WndClass.hInstance], rax
0x1800a3413  mov     edx, 7F00h; lpCursorName
0x1800a3418  xor     ecx, ecx; hInstance
0x1800a341a  call    cs:__imp_LoadCursorW
0x1800a3421  nop     dword ptr [rax+rax+00h]
0x1800a3426  mov     [rbp+3Fh+WndClass.hCursor], rax
0x1800a342a  mov     [rbp+3Fh+WndClass.hbrBackground], 6
0x1800a3432  lea     r13, aShellCharmwind_2; "Shell_CharmWindow"
0x1800a3439  mov     [rbp+3Fh+WndClass.lpszClassName], r13
0x1800a343d  lea     rcx, [rbp+3Fh+WndClass]; lpWndClass
0x1800a3441  call    cs:__imp_RegisterClassW
0x1800a3448  nop     dword ptr [rax+rax+00h]
0x1800a344d  mov     esi, ebx
0x1800a344f  btr     esi, 15h
0x1800a3453  test    dword ptr [rdi+8], 100h
0x1800a345a  cmovz   esi, ebx
0x1800a345d  mov     rcx, [rbp+3Fh+arg_28]; HMONITOR
0x1800a3461  call    ?DUIGetScaleFactorForMonitor@@YA?AW4DEVICE_SCALE_FACTOR@@PEAUHMONITOR__@@@Z; DUIGetScaleFactorForMonitor(HMONITOR__ *)
0x1800a3466  lea     rcx, ??_7CharmWindowPositionTrait@Internal@Windows@@6B@; const Windows::Internal::CharmWindowPositionTrait::`vftable'
0x1800a346d  mov     [rbp+3Fh+var_90], rcx
0x1800a3471  mov     ecx, [rdi+0Ch]
0x1800a3474  mov     dword ptr [rbp+3Fh+var_88], ecx
0x1800a3477  mov     r8d, eax
0x1800a347a  lea     rdx, [rbp+3Fh+arg_0]; enum DEVICE_SCALE_FACTOR
0x1800a347e  lea     rcx, [rbp+3Fh+var_90]; this
0x1800a3482  call    ?MaxSize@CharmWindowPositionTrait@Internal@Windows@@UEBA?AUtagSIZE@@W4DEVICE_SCALE_FACTOR@@@Z; Windows::Internal::CharmWindowPositionTrait::MaxSize(DEVICE_SCALE_FACTOR)
0x1800a3487  mov     edx, [rax]
0x1800a3489  mov     rax, [rbp+3Fh+arg_20]
0x1800a348d  mov     [rdi+20h], rax
0x1800a3491  test    byte ptr [rdi+8], 4
0x1800a3495  jz      short loc_1800A349E
0x1800a3497  xor     eax, eax
0x1800a3499  lea     ecx, [rax+1]
0x1800a349c  jmp     short loc_1800A34A6
0x1800a349e  mov     eax, 1
0x1800a34a3  lea     ecx, [rax+0Ch]
0x1800a34a6  mov     [rsp+100h+var_98], eax
0x1800a34aa  mov     [rsp+100h+var_A0], ecx
0x1800a34ae  mov     [rsp+100h+var_A8], 0
0x1800a34b7  lea     rax, __ImageBase
0x1800a34be  mov     [rsp+100h+var_B0], rax
0x1800a34c3  mov     [rsp+100h+var_B8], 0
0x1800a34cc  mov     [rsp+100h+var_C0], 0
0x1800a34d5  mov     [rsp+100h+var_C8], 258h
0x1800a34dd  mov     [rsp+100h+var_D0], edx
0x1800a34e1  mov     eax, 80000000h
0x1800a34e6  mov     [rsp+100h+var_D8], eax
0x1800a34ea  mov     [rsp+100h+var_E0], eax
0x1800a34ee  mov     r9d, r14d
0x1800a34f1  mov     r8, r15
0x1800a34f4  mov     rdx, r13
0x1800a34f7  mov     ecx, esi
0x1800a34f9  call    cs:__imp_CreateWindowInBandEx
0x1800a3500  nop     dword ptr [rax+rax+00h]
0x1800a3505  mov     rbx, rax
0x1800a3508  test    rax, rax
0x1800a350b  jz      short loc_1800A3575
0x1800a350d  test    dword ptr [rdi+8], 4000h
0x1800a3514  jz      short loc_1800A3520
0x1800a3516  mov     rdx, rax; HWND
0x1800a3519  mov     cl, 1; bool
0x1800a351b  call    ?SetIhmRequireTouchInEditField@@YA_N_NPEAUHWND__@@@Z; SetIhmRequireTouchInEditField(bool,HWND__ *)
0x1800a3520  test    byte ptr [rdi+8], 4
0x1800a3524  jz      short loc_1800A3558
0x1800a3526  mov     [rbp+3Fh+arg_30], 1
0x1800a352d  mov     [rbp+3Fh+var_90], 11h
0x1800a3535  lea     rax, [rbp+3Fh+arg_30]
0x1800a3539  mov     [rbp+3Fh+var_88], rax
0x1800a353d  mov     [rbp+3Fh+var_80], 4
0x1800a3545  lea     rdx, [rbp+3Fh+var_90]
0x1800a3549  mov     rcx, rbx
0x1800a354c  call    cs:__imp_SetWindowCompositionAttribute
0x1800a3553  nop     dword ptr [rax+rax+00h]
0x1800a3558  xor     r9d, r9d; lParam
0x1800a355b  mov     edx, 127h; Msg
0x1800a3560  mov     r8d, 30001h; wParam
0x1800a3566  mov     rcx, rbx; hWnd
0x1800a3569  call    cs:__imp_SendMessageW
0x1800a3570  nop     dword ptr [rax+rax+00h]
0x1800a3575  mov     rax, rbx
0x1800a3578  lea     r11, [rsp+100h+var_20]
0x1800a3580  mov     rbx, [r11+38h]
0x1800a3584  mov     rsi, [r11+40h]
0x1800a3588  mov     rsp, r11
0x1800a358b  pop     r15
0x1800a358d  pop     r14
0x1800a358f  pop     r13
0x1800a3591  pop     rdi
0x1800a3592  pop     rbp
0x1800a3593  retn
```
