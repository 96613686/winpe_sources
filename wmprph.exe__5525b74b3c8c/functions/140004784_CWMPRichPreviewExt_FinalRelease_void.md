# CWMPRichPreviewExt::FinalRelease(void)

- ea: `0x140004784`
- end: `0x140004911`
- name: `?FinalRelease@CWMPRichPreviewExt@@QEAAJXZ`
- size: `397`
- prototype: `__int64 __fastcall(CWMPRichPreviewExt *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x14000ac24`
- `0x14000ad2c`
- `0x14000c550`
- `0x14000c630`

## callees

- `0x140004784`
- `0x1400099e0`
- `0x14000d978`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400048a7`
- `KERNEL32!GetModuleHandleW` at `0x1400048a7`
- `USER32!DestroyWindow` at `0x140004869`
- `USER32!DestroyWindow` at `0x140004887`
- `USER32!DestroyWindow` at `0x140004869`
- `USER32!DestroyWindow` at `0x140004887`
- `USER32!SendMessageW` at `0x1400047e1`
- `USER32!SendMessageW` at `0x1400047e1`
- `USER32!UnregisterClassW` at `0x1400048bc`
- `USER32!UnregisterClassW` at `0x1400048bc`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewExt::FinalRelease(CWMPRichPreviewExt *this)
{
  HWND v2; // rcx
  __int64 (__fastcall ***v3)(_QWORD, _QWORD, _QWORD); // rax
  __int64 (__fastcall ***v4)(_QWORD, _QWORD, _QWORD); // rsi
  int v5; // edi
  __int64 v6; // rcx
  HWND v7; // rcx
  HWND v8; // rcx
  HMODULE ModuleHandleW; // rax
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x10u, &WPP_a1620705688d36e506283508f1a041e6_Traceguids);
  }
  v2 = (HWND)*((_QWORD *)this + 16);
  v11 = 0;
  v3 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))SendMessageW(v2, ATL::WM_ATLGETHOST, 0, 0);
  v4 = v3;
  if ( v3 )
  {
    v5 = (**v3)(v3, &GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352, &v11);
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v4)[2])(v4);
    if ( v5 >= 0 )
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 24LL))(v11, 0);
  }
  else
  {
    v5 = -2147467259;
  }
  v6 = *((_QWORD *)this + 6);
  if ( v6 )
  {
    *((_QWORD *)this + 6) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  WString::DeleteString((unsigned __int16 **)this + 7);
  v7 = (HWND)*((_QWORD *)this + 10);
  if ( v7 )
  {
    DestroyWindow(v7);
    *(_QWORD *)(*((_QWORD *)this + 17) + 64LL) = 0;
  }
  v8 = (HWND)*((_QWORD *)this + 12);
  if ( v8 )
    DestroyWindow(v8);
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 15) = 0;
  ModuleHandleW = GetModuleHandleW(0);
  if ( ModuleHandleW )
    UnregisterClassW(L"RPHInnerParent", ModuleHandleW);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x11u, &WPP_a1620705688d36e506283508f1a041e6_Traceguids);
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140004784  push    rbx
0x140004786  push    rsi
0x140004787  push    rdi
0x140004788  push    r14
0x14000478a  sub     rsp, 28h
0x14000478e  mov     rbx, rcx
0x140004791  mov     rcx, cs:WPP_GLOBAL_Control
0x140004798  lea     r14, WPP_GLOBAL_Control
0x14000479f  cmp     rcx, r14
0x1400047a2  jz      short loc_1400047C5
0x1400047a4  test    byte ptr [rcx+1Ch], 1
0x1400047a8  jz      short loc_1400047C5
0x1400047aa  cmp     byte ptr [rcx+19h], 5
0x1400047ae  jb      short loc_1400047C5
0x1400047b0  mov     rcx, [rcx+10h]
0x1400047b4  lea     r8, WPP_a1620705688d36e506283508f1a041e6_Traceguids
0x1400047bb  mov     edx, 10h
0x1400047c0  call    WPP_SF_
0x1400047c5  mov     edx, cs:?WM_ATLGETHOST@ATL@@3IA; Msg
0x1400047cb  xor     r9d, r9d; lParam
0x1400047ce  mov     rcx, [rbx+80h]; hWnd
0x1400047d5  xor     r8d, r8d; wParam
0x1400047d8  mov     [rsp+48h+arg_0], 0
0x1400047e1  call    cs:__imp_SendMessageW
0x1400047e7  mov     rsi, rax
0x1400047ea  test    rax, rax
0x1400047ed  jz      short loc_140004835
0x1400047ef  mov     rcx, [rax]
0x1400047f2  lea     r8, [rsp+48h+arg_0]
0x1400047f7  lea     rdx, _GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352
0x1400047fe  mov     rax, [rcx]
0x140004801  mov     rcx, rsi
0x140004804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004809  mov     rcx, [rsi]
0x14000480c  mov     edi, eax
0x14000480e  mov     rax, [rcx+10h]
0x140004812  mov     rcx, rsi
0x140004815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000481a  test    edi, edi
0x14000481c  js      short loc_14000483A
0x14000481e  mov     rcx, [rsp+48h+arg_0]
0x140004823  xor     edx, edx
0x140004825  mov     rax, [rcx]
0x140004828  mov     rax, [rax+18h]
0x14000482c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004831  mov     edi, eax
0x140004833  jmp     short loc_14000483A
0x140004835  mov     edi, 80004005h
0x14000483a  mov     rcx, [rbx+30h]
0x14000483e  test    rcx, rcx
0x140004841  jz      short loc_140004857
0x140004843  mov     qword ptr [rbx+30h], 0
0x14000484b  mov     rax, [rcx]
0x14000484e  mov     rax, [rax+10h]
0x140004852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004857  lea     rcx, [rbx+38h]; this
0x14000485b  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x140004860  mov     rcx, [rbx+50h]; hWnd
0x140004864  test    rcx, rcx
0x140004867  jz      short loc_14000487E
0x140004869  call    cs:__imp_DestroyWindow
0x14000486f  mov     rax, [rbx+88h]
0x140004876  mov     qword ptr [rax+40h], 0
0x14000487e  mov     rcx, [rbx+60h]; hWnd
0x140004882  test    rcx, rcx
0x140004885  jz      short loc_14000488D
0x140004887  call    cs:__imp_DestroyWindow
0x14000488d  xor     ecx, ecx; lpModuleName
0x14000488f  mov     qword ptr [rbx+58h], 0
0x140004897  mov     qword ptr [rbx+50h], 0
0x14000489f  mov     qword ptr [rbx+78h], 0
0x1400048a7  call    cs:__imp_GetModuleHandleW
0x1400048ad  test    rax, rax
0x1400048b0  jz      short loc_1400048C2
0x1400048b2  mov     rdx, rax; hInstance
0x1400048b5  lea     rcx, szClass; "RPHInnerParent"
0x1400048bc  call    cs:__imp_UnregisterClassW
0x1400048c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400048c9  cmp     rcx, r14
0x1400048cc  jz      short loc_1400048EF
0x1400048ce  test    byte ptr [rcx+1Ch], 1
0x1400048d2  jz      short loc_1400048EF
0x1400048d4  cmp     byte ptr [rcx+19h], 5
0x1400048d8  jb      short loc_1400048EF
0x1400048da  mov     rcx, [rcx+10h]
0x1400048de  lea     r8, WPP_a1620705688d36e506283508f1a041e6_Traceguids
0x1400048e5  mov     edx, 11h
0x1400048ea  call    WPP_SF_
0x1400048ef  mov     rcx, [rsp+48h+arg_0]
0x1400048f4  test    rcx, rcx
0x1400048f7  jz      short loc_140004905
0x1400048f9  mov     rax, [rcx]
0x1400048fc  mov     rax, [rax+10h]
0x140004900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004905  mov     eax, edi
0x140004907  add     rsp, 28h
0x14000490b  pop     r14
0x14000490d  pop     rdi
0x14000490e  pop     rsi
0x14000490f  pop     rbx
0x140004910  retn
```
