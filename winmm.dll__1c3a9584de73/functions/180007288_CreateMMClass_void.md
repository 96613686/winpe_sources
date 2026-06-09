# CreateMMClass(void)

- ea: `0x180007288`
- end: `0x180007376`
- name: `?CreateMMClass@@YAHXZ`
- size: `238`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007020`

## callees

- `0x180007288`
- `0x18000d470`

## import_xrefs

- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconA` at `0x180007307`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconA` at `0x180007307`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassA` at `0x180007347`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassA` at `0x180007347`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18000736b`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18000736b`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetClassInfoA` at `0x1800072db`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetClassInfoA` at `0x1800072db`

## pseudocode

```c
__int64 CreateMMClass(void)
{
  __int64 result; // rax
  HICON IconA; // rax
  tagWNDCLASSA WndClass; // [rsp+20h] [rbp-50h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  if ( classcreated )
    return 1;
  if ( GetClassInfoA(ghInst, (LPCSTR)0x2B, &WndClass) )
  {
    if ( (__int64 (__fastcall *)(HWND, UINT, WPARAM, struct tagMCI_SYSTEM_MESSAGE *))WndClass.lpfnWndProc != mmWndProc )
      UnregisterClassA((LPCSTR)0x2B, ghInst);
  }
  memset_0(&WndClass, 0, sizeof(WndClass));
  IconA = LoadIconA(ghInst, (LPCSTR)0x64);
  WndClass.lpszMenuName = 0;
  WndClass.hIcon = IconA;
  WndClass.hInstance = ghInst;
  WndClass.lpszClassName = (LPCSTR)43;
  WndClass.hbrBackground = (HBRUSH)6;
  WndClass.style = 0x4000;
  WndClass.lpfnWndProc = (WNDPROC)mmWndProc;
  *(_QWORD *)&WndClass.cbClsExtra = 0;
  result = RegisterClassA(&WndClass);
  classcreated = (unsigned __int16)result;
  return result;
}

```

## disassembly

```asm
0x180007288  mov     [rsp-8+arg_0], rdi
0x18000728d  mov     [rsp-8+arg_8], r14
0x180007292  push    rbp
0x180007293  mov     rbp, rsp
0x180007296  sub     rsp, 70h
0x18000729a  xor     edx, edx; Val
0x18000729c  lea     rcx, [rbp+WndClass]; void *
0x1800072a0  lea     r8d, [rdx+48h]; Size
0x1800072a4  call    memset_0
0x1800072a9  cmp     cs:?classcreated@@3HA, 0; int classcreated
0x1800072b0  jz      short loc_1800072C9
0x1800072b2  mov     eax, 1
0x1800072b7  lea     r11, [rsp+70h+var_s0]
0x1800072bc  mov     rdi, [r11+10h]
0x1800072c0  mov     r14, [r11+18h]
0x1800072c4  mov     rsp, r11
0x1800072c7  pop     rbp
0x1800072c8  retn
0x1800072c9  mov     rcx, cs:ghInst; hInstance
0x1800072d0  lea     r8, [rbp+WndClass]; lpWndClass
0x1800072d4  mov     edi, 2Bh ; '+'
0x1800072d9  mov     edx, edi; lpClassName
0x1800072db  call    cs:__imp_GetClassInfoA
0x1800072e1  lea     r14, ?mmWndProc@@YA_JPEAUHWND__@@I_K_J@Z; mmWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800072e8  test    eax, eax
0x1800072ea  jnz     short loc_18000735B
0x1800072ec  xor     edx, edx; Val
0x1800072ee  lea     rcx, [rbp+WndClass]; void *
0x1800072f2  lea     r8d, [rdx+48h]; Size
0x1800072f6  call    memset_0
0x1800072fb  mov     rcx, cs:ghInst; hInstance
0x180007302  mov     edx, 64h ; 'd'; lpIconName
0x180007307  call    cs:__imp_LoadIconA
0x18000730d  lea     rcx, [rbp+WndClass]; lpWndClass
0x180007311  mov     [rbp+WndClass.lpszMenuName], 0
0x180007319  mov     [rbp+WndClass.hIcon], rax
0x18000731d  mov     rax, cs:ghInst
0x180007324  mov     [rbp+WndClass.hInstance], rax
0x180007328  mov     [rbp+WndClass.lpszClassName], rdi
0x18000732c  mov     [rbp+WndClass.hbrBackground], 6
0x180007334  mov     [rbp+WndClass.style], 4000h
0x18000733b  mov     [rbp+WndClass.lpfnWndProc], r14
0x18000733f  mov     qword ptr [rbp+WndClass.cbClsExtra], 0
0x180007347  call    cs:__imp_RegisterClassA
0x18000734d  movzx   eax, ax
0x180007350  mov     cs:?classcreated@@3HA, eax; int classcreated
0x180007356  jmp     loc_1800072B7
0x18000735b  cmp     [rbp+WndClass.lpfnWndProc], r14
0x18000735f  jz      short loc_1800072EC
0x180007361  mov     rdx, cs:ghInst; hInstance
0x180007368  mov     rcx, rdi; lpClassName
0x18000736b  call    cs:__imp_UnregisterClassA
0x180007371  jmp     loc_1800072EC
```
