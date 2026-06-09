# SetCommandLinkIcon(HWND__ *,HICON__ *)

- ea: `0x180020214`
- end: `0x1800202f0`
- name: `?SetCommandLinkIcon@@YAJPEAUHWND__@@PEAUHICON__@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(HWND hWnd, HICON)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009d80`

## callees

- `0x180020214`
- `0x180020568`
- `0x18002064c`
- `0x180020718`
- `0x18002d840`

## import_xrefs

- `USER32!SendMessageW` at `0x18002024f`
- `USER32!SendMessageW` at `0x1800202b3`
- `USER32!SendMessageW` at `0x18002024f`
- `USER32!SendMessageW` at `0x1800202b3`
- `USER32!GetSystemMetrics` at `0x18002025e`
- `USER32!GetSystemMetrics` at `0x18002026b`
- `USER32!GetSystemMetrics` at `0x18002025e`
- `USER32!GetSystemMetrics` at `0x18002026b`

## pseudocode

```c
__int64 __fastcall SetCommandLinkIcon(HWND hWnd, __int64 a2)
{
  unsigned int SystemMetrics; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  LPARAM v7; // rdi
  int i; // ebx
  unsigned int v9; // ebx
  LPARAM lParam[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v12; // [rsp+40h] [rbp-38h]

  *(_OWORD *)lParam = 0;
  v12 = 0;
  if ( (unsigned int)SendMessageW(hWnd, 0x1603u, 0, (LPARAM)lParam)
    && (SystemMetrics = GetSystemMetrics(12),
        v5 = GetSystemMetrics(11),
        (v7 = IsolationAwareImageList_Create(v5, SystemMetrics)) != 0) )
  {
    for ( i = 0; i < 6; ++i )
    {
      if ( i != (unsigned int)IsolationAwareImageList_ReplaceIcon(v7, v6, a2) )
        goto LABEL_8;
    }
    lParam[0] = v7;
    v9 = 0;
    if ( (unsigned int)SendMessageW(hWnd, 0x1602u, 0, (LPARAM)lParam) )
      return v9;
LABEL_8:
    v9 = -2147467259;
    IsolationAwareImageList_Destroy(v7);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v9;
}

```

## disassembly

```asm
0x180020214  mov     [rsp+arg_10], rbx
0x180020219  push    rbp
0x18002021a  push    rsi
0x18002021b  push    rdi
0x18002021c  sub     rsp, 60h
0x180020220  mov     rax, cs:__security_cookie
0x180020227  xor     rax, rsp
0x18002022a  mov     [rsp+78h+var_28], rax
0x18002022f  xorps   xmm0, xmm0
0x180020232  lea     r9, [rsp+78h+lParam]; lParam
0x180020237  mov     rbp, rdx
0x18002023a  xor     r8d, r8d; wParam
0x18002023d  mov     edx, 1603h; Msg
0x180020242  mov     rsi, rcx
0x180020245  movups  xmmword ptr [rsp+78h+lParam], xmm0
0x18002024a  movups  [rsp+78h+var_38], xmm0
0x18002024f  call    cs:__imp_SendMessageW
0x180020255  test    eax, eax
0x180020257  jz      short loc_1800202CC
0x180020259  mov     ecx, 0Ch; nIndex
0x18002025e  call    cs:__imp_GetSystemMetrics
0x180020264  mov     ecx, 0Bh; nIndex
0x180020269  mov     ebx, eax
0x18002026b  call    cs:__imp_GetSystemMetrics
0x180020271  mov     ecx, eax
0x180020273  mov     edx, ebx
0x180020275  call    IsolationAwareImageList_Create
0x18002027a  mov     rdi, rax
0x18002027d  test    rax, rax
0x180020280  jz      short loc_1800202CC
0x180020282  xor     ebx, ebx
0x180020284  cmp     ebx, 6
0x180020287  jge     short loc_18002029C
0x180020289  mov     r8, rbp
0x18002028c  mov     rcx, rdi
0x18002028f  call    IsolationAwareImageList_ReplaceIcon
0x180020294  cmp     ebx, eax
0x180020296  jnz     short loc_1800202BD
0x180020298  inc     ebx
0x18002029a  jmp     short loc_180020284
0x18002029c  lea     r9, [rsp+78h+lParam]; lParam
0x1800202a1  mov     [rsp+78h+lParam], rdi
0x1800202a6  xor     r8d, r8d; wParam
0x1800202a9  mov     edx, 1602h; Msg
0x1800202ae  mov     rcx, rsi; hWnd
0x1800202b1  xor     ebx, ebx
0x1800202b3  call    cs:__imp_SendMessageW
0x1800202b9  test    eax, eax
0x1800202bb  jnz     short loc_1800202D1
0x1800202bd  mov     rcx, rdi
0x1800202c0  mov     ebx, 80004005h
0x1800202c5  call    IsolationAwareImageList_Destroy
0x1800202ca  jmp     short loc_1800202D1
0x1800202cc  mov     ebx, 80004005h
0x1800202d1  mov     eax, ebx
0x1800202d3  mov     rcx, [rsp+78h+var_28]
0x1800202d8  xor     rcx, rsp; StackCookie
0x1800202db  call    __security_check_cookie
0x1800202e0  mov     rbx, [rsp+78h+arg_10]
0x1800202e8  add     rsp, 60h
0x1800202ec  pop     rdi
0x1800202ed  pop     rsi
0x1800202ee  pop     rbp
0x1800202ef  retn
```
