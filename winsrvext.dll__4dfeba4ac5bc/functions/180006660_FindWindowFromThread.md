# FindWindowFromThread

- ea: `0x180006660`
- end: `0x180006781`
- name: `FindWindowFromThread`
- size: `289`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800013cc`
- `0x180006660`
- `0x18000a69c`
- `0x1800138d1`
- `0x1800138f0`

## import_xrefs

- `USER32!IsInDesktopWindowBand` at `0x1800066e7`
- `USER32!IsInDesktopWindowBand` at `0x1800066e7`
- `USER32!GetClassNameW` at `0x18000668a`
- `USER32!GetClassNameW` at `0x18000668a`
- `USER32!GetWindow` at `0x18000673d`
- `USER32!GetWindow` at `0x18000673d`
- `USER32!GetClassLongW` at `0x1800066d2`
- `USER32!GetClassLongW` at `0x1800066d2`

## pseudocode

```c
_BOOL8 __fastcall FindWindowFromThread(HWND a1, _QWORD *a2)
{
  int ClassNameW; // eax
  HWND Window; // rax
  wchar_t ClassName[16]; // [rsp+20h] [rbp-38h] BYREF

  ClassNameW = GetClassNameW(a1, ClassName, 15);
  if ( ClassNameW )
  {
    if ( (unsigned __int64)(2LL * ClassNameW) >= 0x20 )
      _report_rangecheckfailure();
    ClassName[ClassNameW] = 0;
    if ( !wcsncmp_0(ClassName, L"IME", 3u) || (GetClassLongW(a1, -26) & 0x10000) != 0 )
      return 1;
  }
  if ( !(unsigned int)IsInDesktopWindowBand(a1) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_95618e15e79d3e424986cec7c2aa39d0_Traceguids, a1);
    }
    return 1;
  }
  Window = GetWindow(a1, 4u);
  if ( !*a2 || !Window )
    *a2 = a1;
  return Window != 0;
}

```

## disassembly

```asm
0x180006660  mov     [rsp+arg_10], rbx
0x180006665  push    rdi
0x180006666  sub     rsp, 50h
0x18000666a  mov     rax, cs:__security_cookie
0x180006671  xor     rax, rsp
0x180006674  mov     [rsp+58h+var_18], rax
0x180006679  mov     rdi, rdx
0x18000667c  mov     r8d, 0Fh; nMaxCount
0x180006682  lea     rdx, [rsp+58h+ClassName]; lpClassName
0x180006687  mov     rbx, rcx
0x18000668a  call    cs:__imp_GetClassNameW
0x180006691  nop     dword ptr [rax+rax+00h]
0x180006696  test    eax, eax
0x180006698  jz      short loc_1800066E4
0x18000669a  cdqe
0x18000669c  lea     rcx, [rax+rax]
0x1800066a0  cmp     rcx, 20h ; ' '
0x1800066a4  jnb     loc_18000677B
0x1800066aa  xor     eax, eax
0x1800066ac  lea     rdx, aIme; "IME"
0x1800066b3  mov     [rsp+rcx+58h+ClassName], ax
0x1800066b8  lea     rcx, [rsp+58h+ClassName]; String1
0x1800066bd  lea     r8d, [rax+3]; MaxCount
0x1800066c1  call    wcsncmp_0
0x1800066c6  test    eax, eax
0x1800066c8  jz      short loc_18000672E
0x1800066ca  mov     edx, 0FFFFFFE6h; nIndex
0x1800066cf  mov     rcx, rbx; hWnd
0x1800066d2  call    cs:__imp_GetClassLongW
0x1800066d9  nop     dword ptr [rax+rax+00h]
0x1800066de  bt      eax, 10h
0x1800066e2  jb      short loc_18000672E
0x1800066e4  mov     rcx, rbx
0x1800066e7  call    cs:__imp_IsInDesktopWindowBand
0x1800066ee  nop     dword ptr [rax+rax+00h]
0x1800066f3  test    eax, eax
0x1800066f5  jnz     short loc_180006735
0x1800066f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066fe  lea     rax, WPP_GLOBAL_Control
0x180006705  cmp     rcx, rax
0x180006708  jz      short loc_18000672E
0x18000670a  test    byte ptr [rcx+1Ch], 1
0x18000670e  jz      short loc_18000672E
0x180006710  cmp     byte ptr [rcx+19h], 4
0x180006714  jb      short loc_18000672E
0x180006716  mov     rcx, [rcx+10h]
0x18000671a  lea     r8, WPP_95618e15e79d3e424986cec7c2aa39d0_Traceguids
0x180006721  mov     edx, 0Eh
0x180006726  mov     r9, rbx
0x180006729  call    WPP_SF_q
0x18000672e  mov     eax, 1
0x180006733  jmp     short loc_180006762
0x180006735  mov     edx, 4; uCmd
0x18000673a  mov     rcx, rbx; hWnd
0x18000673d  call    cs:__imp_GetWindow
0x180006744  nop     dword ptr [rax+rax+00h]
0x180006749  cmp     qword ptr [rdi], 0
0x18000674d  mov     rcx, rax
0x180006750  jz      short loc_180006757
0x180006752  test    rax, rax
0x180006755  jnz     short loc_18000675A
0x180006757  mov     [rdi], rbx
0x18000675a  xor     eax, eax
0x18000675c  test    rcx, rcx
0x18000675f  setnz   al
0x180006762  mov     rcx, [rsp+58h+var_18]
0x180006767  xor     rcx, rsp; StackCookie
0x18000676a  call    __security_check_cookie
0x18000676f  mov     rbx, [rsp+58h+arg_10]
0x180006774  add     rsp, 50h
0x180006778  pop     rdi
0x180006779  retn
0x18000677b  call    __report_rangecheckfailure
```
