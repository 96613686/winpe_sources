# DuiView::DisplayDuiFromEapConfig(HWND__ *,HINSTANCE__ *,_CREDS_DLG_PARAMETERS *,ulong,_PLAP_INPUT_FIELD_DATA *)

- ea: `0x180017ca0`
- end: `0x180017df8`
- name: `?DisplayDuiFromEapConfig@DuiView@@QEAAJPEAUHWND__@@PEAUHINSTANCE__@@PEAU_CREDS_DLG_PARAMETERS@@KPEAU_PLAP_INPUT_FIELD_DATA@@@Z`
- size: `344`
- prototype: `__int64 __usercall@<rax>(DuiView *__hidden this@<rcx>, HWND@<rdx>, HINSTANCE@<r8>, struct _CREDS_DLG_PARAMETERS *@<r9>, unsigned int, struct _PLAP_INPUT_FIELD_DATA *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800160f0`

## callees

- `0x1800011d0`
- `0x180017ca0`
- `0x180017fcc`
- `0x180018668`
- `0x18001ab44`

## import_xrefs

- `USER32!ShowWindow` at `0x180017d9d`
- `USER32!ShowWindow` at `0x180017d9d`
- `USER32!DispatchMessageW` at `0x180017dc6`
- `USER32!DispatchMessageW` at `0x180017dc6`
- `USER32!TranslateMessage` at `0x180017dbc`
- `USER32!TranslateMessage` at `0x180017dbc`
- `USER32!GetMessageW` at `0x180017dd8`
- `USER32!GetMessageW` at `0x180017dd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DuiView::DisplayDuiFromEapConfig(
        DuiView *this,
        HWND a2,
        HINSTANCE a3,
        struct _CREDS_DLG_PARAMETERS *a4,
        unsigned int a5,
        struct _PLAP_INPUT_FIELD_DATA *a6)
{
  DuiDataHandler *v7; // rbx
  DuiDataHandler *v8; // rax
  DuiDataHandler *v9; // rax
  __int64 result; // rax
  int MessageW; // eax
  _QWORD v12[2]; // [rsp+20h] [rbp-40h] BYREF
  MSG Msg; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 *v14; // [rsp+70h] [rbp+10h] BYREF
  DuiDataHandler *v15; // [rsp+78h] [rbp+18h]

  v12[0] = 1;
  v12[1] = a4;
  *((_QWORD *)this + 6) = a2;
  *((_QWORD *)this + 7) = a3;
  v14 = 0;
  v7 = (DuiDataHandler *)*((_QWORD *)this + 5);
  if ( !v7 )
  {
    v8 = (DuiDataHandler *)operator new(0x20u);
    v7 = v8;
    v15 = v8;
    if ( v8 )
    {
      *(_QWORD *)v8 = 0;
      v9 = (DuiDataHandler *)operator new(0x18u);
      v15 = v9;
      if ( v9 )
      {
        *(_QWORD *)v9 = 0;
        *((_QWORD *)v9 + 1) = 0;
        *((_QWORD *)v9 + 2) = 0;
      }
      *((_QWORD *)v7 + 1) = v9;
      *((_QWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 3) = v12;
    }
    else
    {
      v7 = 0;
    }
    *((_QWORD *)this + 5) = v7;
  }
  DuiDataHandler::EapConfig2DuiMarkup(v7, a5, a6, (const unsigned __int16 **)&v14);
  result = DuiView::Initialize(this, v14, (struct _CREDSDLG_PROPERTIES *)v12);
  if ( (int)result >= 0 )
  {
    result = TopViewer::Load(*((TopViewer **)this + 1), *((HINSTANCE *)this + 7), (DuiView *)((char *)this + 24));
    if ( (int)result >= 0 )
    {
      memset(&Msg, 0, sizeof(Msg));
      LODWORD(v14) = 0;
      ShowWindow(*(HWND *)(*(_QWORD *)this + 8LL), 10);
      *(_QWORD *)(*((_QWORD *)this + 1) + 832LL) = &v14;
      while ( 1 )
      {
        MessageW = GetMessageW(&Msg, 0, 0, 0);
        if ( MessageW == -1 || !MessageW )
          break;
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
      return (unsigned int)v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180017ca0  mov     [rsp-8+arg_10], rbx
0x180017ca5  mov     [rsp-8+arg_18], rdi
0x180017caa  push    rbp
0x180017cab  mov     rbp, rsp
0x180017cae  sub     rsp, 60h
0x180017cb2  mov     rdi, rcx
0x180017cb5  mov     [rbp+var_40], 1
0x180017cbd  mov     [rbp+var_38], r9
0x180017cc1  mov     [rcx+30h], rdx
0x180017cc5  mov     [rcx+38h], r8
0x180017cc9  mov     [rbp+arg_0], 0
0x180017cd1  mov     rbx, [rcx+28h]
0x180017cd5  test    rbx, rbx
0x180017cd8  jnz     short loc_180017D3B
0x180017cda  lea     ecx, [rbx+20h]; Size
0x180017cdd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017ce2  mov     rbx, rax
0x180017ce5  mov     [rbp+arg_8], rax
0x180017ce9  test    rax, rax
0x180017cec  jz      short loc_180017D35
0x180017cee  mov     qword ptr [rax], 0
0x180017cf5  mov     ecx, 18h; Size
0x180017cfa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017cff  mov     [rbp+arg_8], rax
0x180017d03  test    rax, rax
0x180017d06  jz      short loc_180017D1F
0x180017d08  mov     qword ptr [rax], 0
0x180017d0f  mov     qword ptr [rax+8], 0
0x180017d17  mov     qword ptr [rax+10h], 0
0x180017d1f  mov     [rbx+8], rax
0x180017d23  mov     qword ptr [rbx+10h], 0
0x180017d2b  lea     rax, [rbp+var_40]
0x180017d2f  mov     [rbx+18h], rax
0x180017d33  jmp     short loc_180017D37
0x180017d35  xor     ebx, ebx
0x180017d37  mov     [rdi+28h], rbx
0x180017d3b  lea     r9, [rbp+arg_0]; unsigned __int16 **
0x180017d3f  mov     r8, [rbp+arg_28]; struct _PLAP_INPUT_FIELD_DATA *
0x180017d43  mov     edx, [rbp+arg_20]; unsigned int
0x180017d46  mov     rcx, rbx; this
0x180017d49  call    ?EapConfig2DuiMarkup@DuiDataHandler@@QEAAJKPEAU_PLAP_INPUT_FIELD_DATA@@PEAPEBG@Z; DuiDataHandler::EapConfig2DuiMarkup(ulong,_PLAP_INPUT_FIELD_DATA *,ushort const * *)
0x180017d4e  lea     r8, [rbp+var_40]; struct _CREDSDLG_PROPERTIES *
0x180017d52  mov     rdx, [rbp+arg_0]; unsigned __int16 *
0x180017d56  mov     rcx, rdi; this
0x180017d59  call    ?Initialize@DuiView@@AEAAJPEBGPEAU_CREDSDLG_PROPERTIES@@@Z; DuiView::Initialize(ushort const *,_CREDSDLG_PROPERTIES *)
0x180017d5e  test    eax, eax
0x180017d60  js      loc_180017DE6
0x180017d66  lea     r8, [rdi+18h]; struct _CREDSDLG_PROPERTIES *
0x180017d6a  mov     rdx, [rdi+38h]; HINSTANCE
0x180017d6e  mov     rcx, [rdi+8]; this
0x180017d72  call    ?Load@TopViewer@@QEAAJPEAUHINSTANCE__@@PEAU_CREDSDLG_PROPERTIES@@@Z; TopViewer::Load(HINSTANCE__ *,_CREDSDLG_PROPERTIES *)
0x180017d77  test    eax, eax
0x180017d79  js      short loc_180017DE6
0x180017d7b  xorps   xmm0, xmm0
0x180017d7e  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x180017d82  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x180017d86  movups  xmmword ptr [rbp+Msg.time], xmm0
0x180017d8a  mov     dword ptr [rbp+arg_0], 0
0x180017d91  mov     rcx, [rdi]
0x180017d94  mov     edx, 0Ah; nCmdShow
0x180017d99  mov     rcx, [rcx+8]; hWnd
0x180017d9d  call    cs:__imp_ShowWindow
0x180017da3  mov     rax, [rdi+8]
0x180017da7  lea     rcx, [rbp+arg_0]
0x180017dab  mov     [rax+340h], rcx
0x180017db2  jmp     short loc_180017DCC
0x180017db4  test    eax, eax
0x180017db6  jz      short loc_180017DE3
0x180017db8  lea     rcx, [rbp+Msg]; lpMsg
0x180017dbc  call    cs:__imp_TranslateMessage
0x180017dc2  lea     rcx, [rbp+Msg]; lpMsg
0x180017dc6  call    cs:__imp_DispatchMessageW
0x180017dcc  xor     r9d, r9d; wMsgFilterMax
0x180017dcf  xor     r8d, r8d; wMsgFilterMin
0x180017dd2  xor     edx, edx; hWnd
0x180017dd4  lea     rcx, [rbp+Msg]; lpMsg
0x180017dd8  call    cs:__imp_GetMessageW
0x180017dde  cmp     eax, 0FFFFFFFFh
0x180017de1  jnz     short loc_180017DB4
0x180017de3  mov     eax, dword ptr [rbp+arg_0]
0x180017de6  lea     r11, [rsp+60h+var_s0]
0x180017deb  mov     rbx, [r11+20h]
0x180017def  mov     rdi, [r11+28h]
0x180017df3  mov     rsp, r11
0x180017df6  pop     rbp
0x180017df7  retn
```
