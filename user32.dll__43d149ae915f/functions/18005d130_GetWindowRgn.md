# GetWindowRgn

- ea: `0x18005d130`
- end: `0x18005d347`
- name: `GetWindowRgn`
- size: `535`
- prototype: `int __stdcall(HWND hWnd, HRGN hRgn)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180035be0`

## callees

- `0x18000d210`
- `0x180014a4c`
- `0x180014c10`
- `0x180052d64`
- `0x18005d130`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserTransformRect` at `0x18005d2a0`
- `win32u!NtUserTransformRect` at `0x18005d2a0`
- `win32u!NtUserGetThreadState` at `0x18005d2c7`
- `win32u!NtUserGetThreadState` at `0x18005d2c7`
- `GDI32!MirrorRgn` at `0x18005d33c`
- `GDI32!MirrorRgn` at `0x18005d33c`
- `GDI32!OffsetRgn` at `0x18005d329`
- `GDI32!OffsetRgn` at `0x18005d329`
- `GDI32!CombineRgn` at `0x18005d1a5`
- `GDI32!CombineRgn` at `0x18005d1a5`

## pseudocode

```c
int __stdcall GetWindowRgn(HWND hWnd, HRGN hRgn)
{
  struct tagWND *v3; // rax
  __int64 v4; // rbx
  HRGN v5; // rdx
  int v7; // ebp
  unsigned int v8; // edi
  int v9; // edx
  struct tagMONITOR *PrimaryMonitor; // rax
  __int64 v11; // rax
  __int128 v12; // [rsp+20h] [rbp-48h] BYREF
  __int128 v13; // [rsp+30h] [rbp-38h] BYREF

  v13 = 0;
  if ( !hRgn )
    return 0;
  v3 = ValidateHwnd(hWnd);
  v4 = (__int64)v3;
  if ( !v3 )
    return 0;
  v5 = (HRGN)*((_QWORD *)v3 + 21);
  if ( !v5 )
    return 0;
  if ( (*((_BYTE *)v3 + 21) & 8) != 0 )
    return 0;
  v7 = CombineRgn(hRgn, v5, 0, 5);
  if ( !v7 )
    return 0;
  if ( *(_DWORD *)&gfServerProcess || NtCurrentTeb() == (struct _TEB *)-2048LL && !NtUserGetThreadState(14) )
    v8 = 18;
  else
    v8 = LODWORD(NtCurrentTeb()->Win32ClientInfo[29])
       ? LODWORD(NtCurrentTeb()->Win32ClientInfo[29])
       : gDefaultDpiContext;
  if ( (*(_WORD *)(v4 + 42) & 0x2FFF) == 0x29D )
  {
    PrimaryMonitor = GetPrimaryMonitor();
    GetMonitorRect(&v12, PrimaryMonitor);
    v13 = v12;
  }
  else
  {
    v13 = *(_OWORD *)(v4 + 88);
  }
  if ( (NtCurrentTeb()->Win32ClientInfo[28] & 0x20) == 0
    && (((unsigned __int16)(v8 >> 8) ^ (unsigned __int16)(*(_DWORD *)(v4 + 288) >> 8)) & 0x1FF) != 0 )
  {
    v9 = v13;
    v11 = v13 - *(_QWORD *)(v4 + 88);
    if ( (_QWORD)v13 == *(_QWORD *)(v4 + 88) )
      v11 = *((_QWORD *)&v13 + 1) - *(_QWORD *)(v4 + 96);
    if ( v11 )
      goto LABEL_15;
    NtUserTransformRect(&v13, v8, *(unsigned int *)(v4 + 288), *(_QWORD *)(v4 + 256));
    v7 = UserScaleRgn(hRgn, v8, v4);
    if ( !v7 )
      return 0;
  }
  v9 = v13;
LABEL_15:
  if ( (*(_WORD *)(v4 + 42) & 0x2FFF) != 0x29D )
    v7 = OffsetRgn(hRgn, -v9, -DWORD1(v13));
  if ( (*(_BYTE *)(v4 + 26) & 0x40) != 0 )
    MirrorRgn(*(_QWORD *)v4, hRgn);
  return v7;
}

```

## disassembly

```asm
0x18005d130  mov     [rsp+arg_10], rbx
0x18005d135  push    rbp
0x18005d136  push    rsi
0x18005d137  push    rdi
0x18005d138  sub     rsp, 50h
0x18005d13c  mov     rax, cs:__security_cookie
0x18005d143  xor     rax, rsp
0x18005d146  mov     [rsp+68h+var_28], rax
0x18005d14b  xorps   xmm0, xmm0
0x18005d14e  mov     rsi, rdx
0x18005d151  movups  [rsp+68h+var_38], xmm0
0x18005d156  test    rdx, rdx
0x18005d159  jz      short loc_18005D174
0x18005d15b  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x18005d160  mov     rbx, rax
0x18005d163  test    rax, rax
0x18005d166  jz      short loc_18005D174
0x18005d168  mov     rdx, [rax+0A8h]; hrgnSrc1
0x18005d16f  test    rdx, rdx
0x18005d172  jnz     short loc_18005D193
0x18005d174  xor     eax, eax
0x18005d176  mov     rcx, [rsp+68h+var_28]
0x18005d17b  xor     rcx, rsp; StackCookie
0x18005d17e  call    __security_check_cookie
0x18005d183  mov     rbx, [rsp+68h+arg_10]
0x18005d18b  add     rsp, 50h
0x18005d18f  pop     rdi
0x18005d190  pop     rsi
0x18005d191  pop     rbp
0x18005d192  retn
0x18005d193  test    byte ptr [rax+15h], 8
0x18005d197  jnz     short loc_18005D174
0x18005d199  mov     r9d, 5; iMode
0x18005d19f  xor     r8d, r8d; hrgnSrc2
0x18005d1a2  mov     rcx, rsi; hrgnDst
0x18005d1a5  call    cs:__imp_CombineRgn
0x18005d1ab  mov     ebp, eax
0x18005d1ad  test    eax, eax
0x18005d1af  jz      short loc_18005D174
0x18005d1b1  cmp     cs:gfServerProcess, 0
0x18005d1b8  jnz     loc_18005D2D6
0x18005d1be  mov     rcx, gs:30h
0x18005d1c7  add     rcx, 800h
0x18005d1ce  jz      loc_18005D2C2
0x18005d1d4  mov     rax, gs:30h
0x18005d1dd  cmp     dword ptr [rax+8E8h], 0
0x18005d1e4  jnz     loc_18005D2E0
0x18005d1ea  mov     edi, cs:gDefaultDpiContext
0x18005d1f0  movzx   eax, word ptr [rbx+2Ah]
0x18005d1f4  and     eax, 0FFFF2FFFh
0x18005d1f9  cmp     eax, 29Dh
0x18005d1fe  jz      short loc_18005D253
0x18005d200  movups  xmm0, xmmword ptr [rbx+58h]
0x18005d204  movdqu  [rsp+68h+var_38], xmm0
0x18005d20a  mov     rax, gs:30h
0x18005d213  mov     r8d, 58h ; 'X'
0x18005d219  mov     r9, rbx
0x18005d21c  test    byte ptr [rax+8E0h], 20h
0x18005d223  jz      loc_18005D2F4
0x18005d229  mov     rdx, qword ptr [rsp+68h+var_38]
0x18005d22e  movzx   eax, word ptr [rbx+2Ah]
0x18005d232  and     eax, 0FFFF2FFFh
0x18005d237  cmp     eax, 29Dh
0x18005d23c  jnz     loc_18005D31C
0x18005d242  test    byte ptr [rbx+1Ah], 40h
0x18005d246  jnz     loc_18005D336
0x18005d24c  mov     eax, ebp
0x18005d24e  jmp     loc_18005D176
0x18005d253  call    ?GetPrimaryMonitor@@YAPEAUtagMONITOR@@XZ; GetPrimaryMonitor(void)
0x18005d258  mov     rdx, rax
0x18005d25b  lea     rcx, [rsp+68h+var_48]
0x18005d260  call    GetMonitorRect
0x18005d265  movaps  xmm0, [rsp+68h+var_48]
0x18005d26a  movdqa  [rsp+68h+var_38], xmm0
0x18005d270  jmp     short loc_18005D20A
0x18005d272  mov     rdx, qword ptr [rsp+68h+var_38]
0x18005d277  mov     rax, rdx
0x18005d27a  sub     rax, [r9+r8]
0x18005d27e  jnz     short loc_18005D28A
0x18005d280  mov     rax, qword ptr [rsp+68h+var_38+8]
0x18005d285  sub     rax, [r9+r8+8]
0x18005d28a  test    rax, rax
0x18005d28d  jnz     short loc_18005D22E
0x18005d28f  mov     r9, [rbx+100h]
0x18005d296  lea     rcx, [rsp+68h+var_38]
0x18005d29b  mov     r8d, r10d
0x18005d29e  mov     edx, edi
0x18005d2a0  call    cs:__imp_NtUserTransformRect
0x18005d2a6  mov     r8, rbx
0x18005d2a9  mov     edx, edi
0x18005d2ab  mov     rcx, rsi; hrgnDst
0x18005d2ae  call    UserScaleRgn
0x18005d2b3  mov     ebp, eax
0x18005d2b5  test    eax, eax
0x18005d2b7  jz      loc_18005D174
0x18005d2bd  jmp     loc_18005D229
0x18005d2c2  mov     ecx, 0Eh
0x18005d2c7  call    cs:__imp_NtUserGetThreadState
0x18005d2cd  test    rax, rax
0x18005d2d0  jnz     loc_18005D1D4
0x18005d2d6  mov     edi, 12h
0x18005d2db  jmp     loc_18005D1F0
0x18005d2e0  mov     rax, gs:30h
0x18005d2e9  mov     edi, [rax+8E8h]
0x18005d2ef  jmp     loc_18005D1F0
0x18005d2f4  mov     r10d, [rbx+120h]
0x18005d2fb  mov     eax, edi
0x18005d2fd  shr     eax, 8
0x18005d300  mov     ecx, r10d
0x18005d303  shr     ecx, 8
0x18005d306  xor     cx, ax
0x18005d309  mov     eax, 1FFh
0x18005d30e  test    ax, cx
0x18005d311  jz      loc_18005D229
0x18005d317  jmp     loc_18005D272
0x18005d31c  mov     r8d, dword ptr [rsp+68h+var_38+4]
0x18005d321  neg     edx; x
0x18005d323  neg     r8d; y
0x18005d326  mov     rcx, rsi; hrgn
0x18005d329  call    cs:__imp_OffsetRgn
0x18005d32f  mov     ebp, eax
0x18005d331  jmp     loc_18005D242
0x18005d336  mov     rcx, [rbx]
0x18005d339  mov     rdx, rsi
0x18005d33c  call    cs:__imp_MirrorRgn
0x18005d342  jmp     loc_18005D24C
```
