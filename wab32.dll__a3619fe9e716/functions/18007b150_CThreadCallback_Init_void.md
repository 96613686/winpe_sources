# CThreadCallback::_Init(void)

- ea: `0x18007b150`
- end: `0x18007b288`
- name: `?_Init@CThreadCallback@@AEAAJXZ`
- size: `312`
- prototype: `__int64 __fastcall(CThreadCallback *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18007b01c`

## callees

- `0x180009428`
- `0x18007b0f0`
- `0x18007b150`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007b207`
- `KERNEL32!GetLastError` at `0x18007b207`
- `USER32!CreateWindowExW` at `0x18007b256`
- `USER32!CreateWindowExW` at `0x18007b256`
- `USER32!RegisterClassW` at `0x18007b1f6`
- `USER32!RegisterClassW` at `0x18007b1f6`

## string_xrefs

- `0x18007b1ab`: `CThreadCallback WNDCLASS %p`

## pseudocode

```c
signed int __fastcall CThreadCallback::_Init(CThreadCallback *this)
{
  signed int result; // eax
  ATOM v3; // ax
  HWND Window; // rax
  WNDCLASSW WndClass; // [rsp+60h] [rbp-278h] BYREF
  WCHAR WindowName[264]; // [rsp+B0h] [rbp-228h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  memset_0(WindowName, 0, 0x208u);
  result = GetCurrentHINSTANCE((char *)this + 40);
  if ( result >= 0 )
  {
    result = StringCchPrintfW(WindowName, 0x104u, L"CThreadCallback WNDCLASS %p", this);
    if ( result >= 0 )
    {
      WndClass.lpszClassName = WindowName;
      WndClass.lpfnWndProc = (WNDPROC)CThreadCallback::_s_WndProc;
      WndClass.hInstance = (HINSTANCE)*((_QWORD *)this + 5);
      v3 = RegisterClassW(&WndClass);
      *((_WORD *)this + 12) = v3;
      if ( v3
        && (Window = CreateWindowExW(
                       0,
                       (LPCWSTR)v3,
                       WindowName,
                       0,
                       0x80000000,
                       0x80000000,
                       0x80000000,
                       0x80000000,
                       HWND_MESSAGE,
                       0,
                       0,
                       0),
            (*((_QWORD *)this + 4) = Window) != 0) )
      {
        return 0;
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007b150  mov     [rsp+arg_8], rbx
0x18007b155  push    rdi
0x18007b156  sub     rsp, 2D0h
0x18007b15d  mov     rax, cs:__security_cookie
0x18007b164  xor     rax, rsp
0x18007b167  mov     [rsp+2D8h+var_18], rax
0x18007b16f  xor     edx, edx; Val
0x18007b171  mov     rbx, rcx
0x18007b174  lea     rcx, [rsp+2D8h+WndClass]; void *
0x18007b179  lea     r8d, [rdx+48h]; Size
0x18007b17d  call    memset_0
0x18007b182  xor     edx, edx; Val
0x18007b184  lea     rcx, [rsp+2D8h+WindowName]; void *
0x18007b18c  mov     r8d, 208h; Size
0x18007b192  call    memset_0
0x18007b197  lea     rcx, [rbx+28h]
0x18007b19b  call    _GetCurrentHINSTANCE
0x18007b1a0  test    eax, eax
0x18007b1a2  js      loc_18007B267
0x18007b1a8  mov     r9, rbx
0x18007b1ab  lea     r8, aCthreadcallbac; "CThreadCallback WNDCLASS %p"
0x18007b1b2  mov     edx, 104h; unsigned __int64
0x18007b1b7  lea     rcx, [rsp+2D8h+WindowName]; unsigned __int16 *
0x18007b1bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007b1c4  test    eax, eax
0x18007b1c6  js      loc_18007B267
0x18007b1cc  lea     rax, [rsp+2D8h+WindowName]
0x18007b1d4  mov     [rsp+2D8h+WndClass.lpszClassName], rax
0x18007b1dc  lea     rcx, [rsp+2D8h+WndClass]; lpWndClass
0x18007b1e1  lea     rax, ?_s_WndProc@CThreadCallback@@CA_JPEAUHWND__@@I_K_J@Z; CThreadCallback::_s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18007b1e8  mov     [rsp+2D8h+WndClass.lpfnWndProc], rax
0x18007b1ed  mov     rax, [rbx+28h]
0x18007b1f1  mov     [rsp+2D8h+WndClass.hInstance], rax
0x18007b1f6  call    cs:__imp_RegisterClassW
0x18007b1fc  xor     ecx, ecx; dwExStyle
0x18007b1fe  mov     [rbx+18h], ax
0x18007b202  cmp     cx, ax
0x18007b205  jnz     short loc_18007B21B
0x18007b207  call    cs:__imp_GetLastError
0x18007b20d  test    eax, eax
0x18007b20f  jle     short loc_18007B267
0x18007b211  movzx   eax, ax
0x18007b214  or      eax, 80070000h
0x18007b219  jmp     short loc_18007B267
0x18007b21b  mov     [rsp+2D8h+lpParam], rcx; lpParam
0x18007b220  lea     r8, [rsp+2D8h+WindowName]; lpWindowName
0x18007b228  mov     [rsp+2D8h+hInstance], rcx; hInstance
0x18007b22d  xor     r9d, r9d; dwStyle
0x18007b230  mov     [rsp+2D8h+hMenu], rcx; hMenu
0x18007b235  mov     [rsp+2D8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18007b23e  movzx   edx, ax; lpClassName
0x18007b241  mov     eax, 80000000h
0x18007b246  mov     [rsp+2D8h+nHeight], eax; nHeight
0x18007b24a  mov     [rsp+2D8h+nWidth], eax; nWidth
0x18007b24e  mov     [rsp+2D8h+Y], eax; Y
0x18007b252  mov     [rsp+2D8h+X], eax; X
0x18007b256  call    cs:__imp_CreateWindowExW
0x18007b25c  mov     [rbx+20h], rax
0x18007b260  test    rax, rax
0x18007b263  jz      short loc_18007B207
0x18007b265  xor     eax, eax
0x18007b267  mov     rcx, [rsp+2D8h+var_18]
0x18007b26f  xor     rcx, rsp; StackCookie
0x18007b272  call    __security_check_cookie
0x18007b277  mov     rbx, [rsp+2D8h+arg_8]
0x18007b27f  add     rsp, 2D0h
0x18007b286  pop     rdi
0x18007b287  retn
```
