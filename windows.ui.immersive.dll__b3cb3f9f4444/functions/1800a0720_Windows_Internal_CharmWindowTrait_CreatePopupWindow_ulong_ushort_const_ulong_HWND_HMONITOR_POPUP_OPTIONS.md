# Windows::Internal::CharmWindowTrait::CreatePopupWindow(ulong,ushort const *,ulong,HWND__ *,HMONITOR__ *,POPUP_OPTIONS)

- ea: `0x1800a0720`
- end: `0x1800a08f5`
- name: `?CreatePopupWindow@CharmWindowTrait@Internal@Windows@@QEAAPEAUHWND__@@KPEBGKPEAU4@PEAUHMONITOR__@@W4POPUP_OPTIONS@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180092220`

## callees

- `0x180030d44`
- `0x18004bba4`
- `0x180054ad4`
- `0x18009db00`
- `0x1800a0720`

## import_xrefs

- `USER32!CreateWindowInBandEx` at `0x1800a0859`
- `USER32!CreateWindowInBandEx` at `0x1800a0859`
- `USER32!RegisterClassW` at `0x1800a07a9`
- `USER32!RegisterClassW` at `0x1800a07a9`
- `USER32!LoadCursorW` at `0x1800a0782`
- `USER32!LoadCursorW` at `0x1800a0782`
- `USER32!SendMessageW` at `0x1800a08c9`
- `USER32!SendMessageW` at `0x1800a08c9`
- `USER32!SetWindowCompositionAttribute` at `0x1800a08ac`
- `USER32!SetWindowCompositionAttribute` at `0x1800a08ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HWND __fastcall Windows::Internal::CharmWindowTrait::CreatePopupWindow(
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
0x1800a0720  mov     [rsp-8+arg_8], rbx
0x1800a0725  mov     [rsp-8+arg_10], rsi
0x1800a072a  push    rbp
0x1800a072b  push    rdi
0x1800a072c  push    r13
0x1800a072e  push    r14
0x1800a0730  push    r15
0x1800a0732  lea     rbp, [rsp-1Fh]
0x1800a0737  sub     rsp, 0E0h
0x1800a073e  mov     r14d, r9d
0x1800a0741  mov     r15, r8
0x1800a0744  mov     ebx, edx
0x1800a0746  mov     rdi, rcx
0x1800a0749  mov     eax, [rbp+3Fh+arg_30]
0x1800a074c  mov     [rcx+8], eax
0x1800a074f  xor     edx, edx; Val
0x1800a0751  lea     r8d, [rdx+48h]; Size
0x1800a0755  lea     rcx, [rbp+3Fh+WndClass]; void *
0x1800a0759  call    memset_0
0x1800a075e  mov     [rbp+3Fh+WndClass.style], 208h
0x1800a0765  lea     rax, ?NoUIAWindowProc@@YA_JPEAUHWND__@@I_K_J@Z; NoUIAWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800a076c  mov     [rbp+3Fh+WndClass.lpfnWndProc], rax
0x1800a0770  lea     rax, __ImageBase
0x1800a0777  mov     [rbp+3Fh+WndClass.hInstance], rax
0x1800a077b  mov     edx, 7F00h; lpCursorName
0x1800a0780  xor     ecx, ecx; hInstance
0x1800a0782  call    cs:__imp_LoadCursorW
0x1800a0789  nop     dword ptr [rax+rax+00h]
0x1800a078e  mov     [rbp+3Fh+WndClass.hCursor], rax
0x1800a0792  mov     [rbp+3Fh+WndClass.hbrBackground], 6
0x1800a079a  lea     r13, aShellCharmwind_0; "Shell_CharmWindow"
0x1800a07a1  mov     [rbp+3Fh+WndClass.lpszClassName], r13
0x1800a07a5  lea     rcx, [rbp+3Fh+WndClass]; lpWndClass
0x1800a07a9  call    cs:__imp_RegisterClassW
0x1800a07b0  nop     dword ptr [rax+rax+00h]
0x1800a07b5  mov     esi, ebx
0x1800a07b7  btr     esi, 15h
0x1800a07bb  test    dword ptr [rdi+8], 100h
0x1800a07c2  cmovz   esi, ebx
0x1800a07c5  mov     rcx, [rbp+3Fh+arg_28]; HMONITOR
0x1800a07c9  call    ?DUIGetScaleFactorForMonitor@@YA?AW4DEVICE_SCALE_FACTOR@@PEAUHMONITOR__@@@Z; DUIGetScaleFactorForMonitor(HMONITOR__ *)
0x1800a07ce  lea     rcx, ??_7CharmWindowPositionTrait@Internal@Windows@@6B@; const Windows::Internal::CharmWindowPositionTrait::`vftable'
0x1800a07d5  mov     [rbp+3Fh+var_90], rcx
0x1800a07d9  mov     ecx, [rdi+0Ch]
0x1800a07dc  mov     dword ptr [rbp+3Fh+var_88], ecx
0x1800a07df  mov     r8d, eax
0x1800a07e2  lea     rdx, [rbp+3Fh+arg_0]; enum DEVICE_SCALE_FACTOR
0x1800a07e6  lea     rcx, [rbp+3Fh+var_90]; this
0x1800a07ea  call    ?MaxSize@CharmWindowPositionTrait@Internal@Windows@@UEBA?AUtagSIZE@@W4DEVICE_SCALE_FACTOR@@@Z; Windows::Internal::CharmWindowPositionTrait::MaxSize(DEVICE_SCALE_FACTOR)
0x1800a07ef  mov     edx, [rax]
0x1800a07f1  test    byte ptr [rdi+8], 4
0x1800a07f5  jz      short loc_1800A07FE
0x1800a07f7  xor     eax, eax
0x1800a07f9  lea     ecx, [rax+1]
0x1800a07fc  jmp     short loc_1800A0806
0x1800a07fe  mov     eax, 1
0x1800a0803  lea     ecx, [rax+0Ch]
0x1800a0806  mov     [rsp+100h+var_98], eax
0x1800a080a  mov     [rsp+100h+var_A0], ecx
0x1800a080e  mov     [rsp+100h+var_A8], 0
0x1800a0817  lea     rax, __ImageBase
0x1800a081e  mov     [rsp+100h+var_B0], rax
0x1800a0823  mov     [rsp+100h+var_B8], 0
0x1800a082c  mov     [rsp+100h+var_C0], 0
0x1800a0835  mov     [rsp+100h+var_C8], 258h
0x1800a083d  mov     [rsp+100h+var_D0], edx
0x1800a0841  mov     eax, 80000000h
0x1800a0846  mov     [rsp+100h+var_D8], eax
0x1800a084a  mov     [rsp+100h+var_E0], eax
0x1800a084e  mov     r9d, r14d
0x1800a0851  mov     r8, r15
0x1800a0854  mov     rdx, r13
0x1800a0857  mov     ecx, esi
0x1800a0859  call    cs:__imp_CreateWindowInBandEx
0x1800a0860  nop     dword ptr [rax+rax+00h]
0x1800a0865  mov     rbx, rax
0x1800a0868  test    rax, rax
0x1800a086b  jz      short loc_1800A08D5
0x1800a086d  test    dword ptr [rdi+8], 4000h
0x1800a0874  jz      short loc_1800A0880
0x1800a0876  mov     rdx, rax; HWND
0x1800a0879  mov     cl, 1; bool
0x1800a087b  call    ?SetIhmRequireTouchInEditField@@YA_N_NPEAUHWND__@@@Z; SetIhmRequireTouchInEditField(bool,HWND__ *)
0x1800a0880  test    byte ptr [rdi+8], 4
0x1800a0884  jz      short loc_1800A08B8
0x1800a0886  mov     [rbp+3Fh+arg_30], 1
0x1800a088d  mov     [rbp+3Fh+var_90], 11h
0x1800a0895  lea     rax, [rbp+3Fh+arg_30]
0x1800a0899  mov     [rbp+3Fh+var_88], rax
0x1800a089d  mov     [rbp+3Fh+var_80], 4
0x1800a08a5  lea     rdx, [rbp+3Fh+var_90]
0x1800a08a9  mov     rcx, rbx
0x1800a08ac  call    cs:__imp_SetWindowCompositionAttribute
0x1800a08b3  nop     dword ptr [rax+rax+00h]
0x1800a08b8  xor     r9d, r9d; lParam
0x1800a08bb  mov     edx, 127h; Msg
0x1800a08c0  mov     r8d, 30001h; wParam
0x1800a08c6  mov     rcx, rbx; hWnd
0x1800a08c9  call    cs:__imp_SendMessageW
0x1800a08d0  nop     dword ptr [rax+rax+00h]
0x1800a08d5  mov     rax, rbx
0x1800a08d8  lea     r11, [rsp+100h+var_20]
0x1800a08e0  mov     rbx, [r11+38h]
0x1800a08e4  mov     rsi, [r11+40h]
0x1800a08e8  mov     rsp, r11
0x1800a08eb  pop     r15
0x1800a08ed  pop     r14
0x1800a08ef  pop     r13
0x1800a08f1  pop     rdi
0x1800a08f2  pop     rbp
0x1800a08f3  retn
```
