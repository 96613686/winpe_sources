# CDialMon::CDialMon(void)

- ea: `0x180004bc0`
- end: `0x180004d21`
- name: `??0CDialMon@@QEAA@XZ`
- size: `353`
- prototype: `CDialMon *__fastcall(CDialMon *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180025034`

## callees

- `0x180002ca0`
- `0x180004bc0`
- `0x180006880`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180004ca5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180004ca5`
- `USER32!ChangeWindowMessageFilter` at `0x180004ccc`
- `USER32!ChangeWindowMessageFilter` at `0x180004cec`
- `USER32!ChangeWindowMessageFilter` at `0x180004d0c`
- `USER32!ChangeWindowMessageFilter` at `0x180004ccc`
- `USER32!ChangeWindowMessageFilter` at `0x180004cec`
- `USER32!ChangeWindowMessageFilter` at `0x180004d0c`
- `USER32!RegisterWindowMessageW` at `0x180004cb9`
- `USER32!RegisterWindowMessageW` at `0x180004cd9`
- `USER32!RegisterWindowMessageW` at `0x180004cf9`
- `USER32!RegisterWindowMessageW` at `0x180004cb9`
- `USER32!RegisterWindowMessageW` at `0x180004cd9`
- `USER32!RegisterWindowMessageW` at `0x180004cf9`
- `USER32!RegisterClassW` at `0x180004c12`
- `USER32!RegisterClassW` at `0x180004c12`
- `USER32!CreateWindowExW` at `0x180004c8d`
- `USER32!CreateWindowExW` at `0x180004c8d`

## pseudocode

```c
CDialMon *__fastcall CDialMon::CDialMon(CDialMon *this)
{
  HINSTANCE hInstance; // rdi
  HWND Window; // rdi
  WNDCLASSW v5; // [rsp+60h] [rbp-78h] BYREF
  ULONG_PTR ulCookie; // [rsp+E0h] [rbp+8h] BYREF

  v5.lpfnWndProc = (WNDPROC)Dialmon_WndProc;
  v5.hInstance = g_hinst;
  *(_QWORD *)&v5.style = 0;
  *(_QWORD *)&v5.cbClsExtra = 0;
  memset(&v5.hIcon, 0, 32);
  v5.lpszClassName = L"MS_WebcheckMonitor";
  RegisterClassW(&v5);
  hInstance = g_hinst;
  ulCookie = 0;
  if ( (unsigned int)SHActivateContext(&ulCookie) )
  {
    if ( g_hActCtx != (HANDLE)-3LL )
      DelayLoadCC();
    Window = CreateWindowExW(
               0,
               L"MS_WebcheckMonitor",
               L"MS_WebcheckMonitor",
               0xCF0000u,
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               0,
               0,
               hInstance,
               this);
    if ( ulCookie )
      DeactivateActCtx(0, ulCookie);
  }
  else
  {
    Window = 0;
  }
  *((_QWORD *)this + 69) = Window;
  dword_180038150 = RegisterWindowMessageW(lpString);
  ChangeWindowMessageFilter(dword_180038150, 1u);
  dword_180038168 = RegisterWindowMessageW(off_180038160);
  ChangeWindowMessageFilter(dword_180038168, 1u);
  dword_180038180 = RegisterWindowMessageW(off_180038178);
  ChangeWindowMessageFilter(dword_180038180, 1u);
  return this;
}

```

## disassembly

```asm
0x180004bc0  mov     r11, rsp
0x180004bc3  push    rbx
0x180004bc4  push    rbp
0x180004bc5  push    rsi
0x180004bc6  push    rdi
0x180004bc7  sub     rsp, 0B8h
0x180004bce  lea     rax, ?Dialmon_WndProc@@YA_JPEAUHWND__@@I_K_J@Z; Dialmon_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180004bd5  mov     rbx, rcx
0x180004bd8  mov     [r11-70h], rax
0x180004bdc  lea     rbp, WindowName; "MS_WebcheckMonitor"
0x180004be3  mov     rax, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x180004bea  lea     rcx, [r11-78h]; lpWndClass
0x180004bee  xor     esi, esi
0x180004bf0  mov     [r11-60h], rax
0x180004bf4  xorps   xmm0, xmm0
0x180004bf7  mov     [r11-78h], rsi
0x180004bfb  xorps   xmm1, xmm1
0x180004bfe  mov     [r11-68h], rsi
0x180004c02  movdqa  xmmword ptr [r11-58h], xmm0
0x180004c08  movdqa  xmmword ptr [r11-48h], xmm1
0x180004c0e  mov     [r11-38h], rbp
0x180004c12  call    cs:__imp_RegisterClassW
0x180004c18  mov     rdi, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x180004c1f  lea     rcx, [rsp+0D8h+ulCookie]
0x180004c27  mov     [rsp+0D8h+ulCookie], rsi
0x180004c2f  call    SHActivateContext
0x180004c34  test    eax, eax
0x180004c36  jnz     short loc_180004C3C
0x180004c38  mov     edi, esi
0x180004c3a  jmp     short loc_180004CAB
0x180004c3c  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x180004c44  jz      short loc_180004C4B
0x180004c46  call    DelayLoadCC
0x180004c4b  mov     [rsp+0D8h+lpParam], rbx; lpParam
0x180004c50  mov     r9d, 0CF0000h; dwStyle
0x180004c56  mov     [rsp+0D8h+hInstance], rdi; hInstance
0x180004c5b  mov     r8, rbp; lpWindowName
0x180004c5e  mov     [rsp+0D8h+hMenu], rsi; hMenu
0x180004c63  mov     rdx, rbp; lpClassName
0x180004c66  mov     [rsp+0D8h+hWndParent], rsi; hWndParent
0x180004c6b  xor     ecx, ecx; dwExStyle
0x180004c6d  mov     [rsp+0D8h+nHeight], 80000000h; nHeight
0x180004c75  mov     [rsp+0D8h+nWidth], 80000000h; nWidth
0x180004c7d  mov     [rsp+0D8h+Y], 80000000h; Y
0x180004c85  mov     [rsp+0D8h+X], 80000000h; X
0x180004c8d  call    cs:__imp_CreateWindowExW
0x180004c93  mov     rdx, [rsp+0D8h+ulCookie]; ulCookie
0x180004c9b  mov     rdi, rax
0x180004c9e  test    rdx, rdx
0x180004ca1  jz      short loc_180004CAB
0x180004ca3  xor     ecx, ecx; dwFlags
0x180004ca5  call    cs:__imp_DeactivateActCtx
0x180004cab  mov     [rbx+228h], rdi
0x180004cb2  mov     rcx, cs:lpString; lpString
0x180004cb9  call    cs:__imp_RegisterWindowMessageW
0x180004cbf  mov     ecx, eax; message
0x180004cc1  mov     cs:dword_180038150, eax
0x180004cc7  mov     edx, 1; dwFlag
0x180004ccc  call    cs:__imp_ChangeWindowMessageFilter
0x180004cd2  mov     rcx, cs:off_180038160; lpString
0x180004cd9  call    cs:__imp_RegisterWindowMessageW
0x180004cdf  mov     ecx, eax; message
0x180004ce1  mov     cs:dword_180038168, eax
0x180004ce7  mov     edx, 1; dwFlag
0x180004cec  call    cs:__imp_ChangeWindowMessageFilter
0x180004cf2  mov     rcx, cs:off_180038178; lpString
0x180004cf9  call    cs:__imp_RegisterWindowMessageW
0x180004cff  mov     ecx, eax; message
0x180004d01  mov     cs:dword_180038180, eax
0x180004d07  mov     edx, 1; dwFlag
0x180004d0c  call    cs:__imp_ChangeWindowMessageFilter
0x180004d12  mov     rax, rbx
0x180004d15  add     rsp, 0B8h
0x180004d1c  pop     rdi
0x180004d1d  pop     rsi
0x180004d1e  pop     rbp
0x180004d1f  pop     rbx
0x180004d20  retn
```
