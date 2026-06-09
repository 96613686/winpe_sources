# CWMPRichPreviewAXWindow::OnOpenPlayback(uint,unsigned __int64,__int64,int &)

- ea: `0x1400065f8`
- end: `0x1400066bb`
- name: `?OnOpenPlayback@CWMPRichPreviewAXWindow@@QEAA_JI_K_JAEAH@Z`
- size: `195`
- prototype: `__int64 __fastcall(CWMPRichPreviewAXWindow *this, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007320`

## callees

- `0x1400065f8`
- `0x1400099e0`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewAXWindow::OnOpenPlayback(
        CWMPRichPreviewAXWindow *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5)
{
  _QWORD *v6; // rcx
  __int64 v7; // rbx

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_a1620705688d36e506283508f1a041e6_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = *((_QWORD *)this + 8);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 40LL))(v7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v6 = WPP_GLOBAL_Control;
  }
  *a5 = 1;
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_(v6[2], 41, &WPP_a1620705688d36e506283508f1a041e6_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1400065f8  mov     [rsp+arg_0], rbx
0x1400065fd  push    rdi
0x1400065fe  sub     rsp, 20h
0x140006602  mov     rbx, rcx
0x140006605  mov     rcx, cs:WPP_GLOBAL_Control
0x14000660c  lea     rdi, WPP_GLOBAL_Control
0x140006613  cmp     rcx, rdi
0x140006616  jz      short loc_140006640
0x140006618  test    byte ptr [rcx+1Ch], 1
0x14000661c  jz      short loc_140006640
0x14000661e  cmp     byte ptr [rcx+19h], 5
0x140006622  jb      short loc_140006640
0x140006624  mov     rcx, [rcx+10h]
0x140006628  lea     r8, WPP_a1620705688d36e506283508f1a041e6_Traceguids
0x14000662f  mov     edx, 28h ; '('
0x140006634  call    WPP_SF_
0x140006639  mov     rcx, cs:WPP_GLOBAL_Control
0x140006640  mov     rbx, [rbx+40h]
0x140006644  test    rbx, rbx
0x140006647  jz      short loc_14000667D
0x140006649  mov     rax, [rbx]
0x14000664c  mov     rcx, rbx
0x14000664f  mov     rax, [rax+8]
0x140006653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006658  mov     rax, [rbx]
0x14000665b  mov     rcx, rbx
0x14000665e  mov     rax, [rax+28h]
0x140006662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006667  mov     rax, [rbx]
0x14000666a  mov     rcx, rbx
0x14000666d  mov     rax, [rax+10h]
0x140006671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006676  mov     rcx, cs:WPP_GLOBAL_Control
0x14000667d  mov     rax, [rsp+28h+arg_20]
0x140006682  mov     dword ptr [rax], 1
0x140006688  cmp     rcx, rdi
0x14000668b  jz      short loc_1400066AE
0x14000668d  test    byte ptr [rcx+1Ch], 1
0x140006691  jz      short loc_1400066AE
0x140006693  cmp     byte ptr [rcx+19h], 5
0x140006697  jb      short loc_1400066AE
0x140006699  mov     rcx, [rcx+10h]
0x14000669d  lea     r8, WPP_a1620705688d36e506283508f1a041e6_Traceguids
0x1400066a4  mov     edx, 29h ; ')'
0x1400066a9  call    WPP_SF_
0x1400066ae  mov     rbx, [rsp+28h+arg_0]
0x1400066b3  xor     eax, eax
0x1400066b5  add     rsp, 20h
0x1400066b9  pop     rdi
0x1400066ba  retn
```
