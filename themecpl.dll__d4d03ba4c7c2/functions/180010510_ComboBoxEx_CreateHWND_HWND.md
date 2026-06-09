# ComboBoxEx::CreateHWND(HWND__ *)

- ea: `0x180010510`
- end: `0x1800105d7`
- name: `?CreateHWND@ComboBoxEx@@MEAAPEAUHWND__@@PEAU2@@Z`
- size: `199`
- prototype: `HWND __fastcall(ComboBoxEx *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010510`

## import_xrefs

- `DUser!AttachWndProcW` at `0x1800105bc`
- `DUser!AttachWndProcW` at `0x1800105bc`
- `USER32!SendMessageW` at `0x18001059e`
- `USER32!SendMessageW` at `0x18001059e`
- `USER32!CreateWindowExW` at `0x18001057c`
- `USER32!CreateWindowExW` at `0x18001057c`

## string_xrefs

- `0x180010555`: `ComboBoxEx32`

## pseudocode

```c
HWND __fastcall ComboBoxEx::CreateHWND(ComboBoxEx *this, HWND a2)
{
  HWND Window; // rax
  HWND v4; // rbx
  LRESULT v5; // rax

  Window = CreateWindowExW(
             0,
             L"ComboBoxEx32",
             0,
             ((unsigned __int8)((*((_BYTE *)this + 149) & 1) == 0) << 27) + 1342177347,
             0,
             0,
             0,
             0,
             a2,
             0,
             0,
             0);
  v4 = Window;
  if ( Window )
  {
    v5 = SendMessageW(Window, 0x406u, 0, 0);
    if ( v5 )
      AttachWndProcW(v5, ComboBoxEx::s_ComboWndProc, this);
  }
  return v4;
}

```

## disassembly

```asm
0x180010510  mov     rax, rsp
0x180010513  mov     [rax+8], rbx
0x180010517  push    rdi
0x180010518  sub     rsp, 60h
0x18001051c  mov     r9b, [rcx+95h]
0x180010523  mov     rdi, rcx
0x180010526  mov     qword ptr [rax-10h], 0
0x18001052e  not     r9b
0x180010531  mov     qword ptr [rax-18h], 0
0x180010539  and     r9d, 1
0x18001053d  mov     qword ptr [rax-20h], 0
0x180010545  xor     r8d, r8d; lpWindowName
0x180010548  mov     [rax-28h], rdx
0x18001054c  xor     ecx, ecx; dwExStyle
0x18001054e  mov     dword ptr [rax-30h], 0
0x180010555  lea     rdx, aComboboxex32; "ComboBoxEx32"
0x18001055c  mov     dword ptr [rax-38h], 0
0x180010563  shl     r9d, 1Bh
0x180010567  mov     dword ptr [rax-40h], 0
0x18001056e  add     r9d, 50000043h; dwStyle
0x180010575  mov     dword ptr [rax-48h], 0
0x18001057c  call    cs:__imp_CreateWindowExW
0x180010583  nop     dword ptr [rax+rax+00h]
0x180010588  mov     rbx, rax
0x18001058b  test    rax, rax
0x18001058e  jz      short loc_1800105C8
0x180010590  xor     r9d, r9d; lParam
0x180010593  xor     r8d, r8d; wParam
0x180010596  mov     edx, 406h; Msg
0x18001059b  mov     rcx, rax; hWnd
0x18001059e  call    cs:__imp_SendMessageW
0x1800105a5  nop     dword ptr [rax+rax+00h]
0x1800105aa  test    rax, rax
0x1800105ad  jz      short loc_1800105C8
0x1800105af  mov     r8, rdi
0x1800105b2  lea     rdx, ?s_ComboWndProc@ComboBoxEx@@CAHPEAXPEAUHWND__@@I_K_JPEA_J@Z; ComboBoxEx::s_ComboWndProc(void *,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x1800105b9  mov     rcx, rax
0x1800105bc  call    cs:__imp_AttachWndProcW
0x1800105c3  nop     dword ptr [rax+rax+00h]
0x1800105c8  mov     rax, rbx
0x1800105cb  mov     rbx, [rsp+68h+arg_0]
0x1800105d0  add     rsp, 60h
0x1800105d4  pop     rdi
0x1800105d5  retn
```
