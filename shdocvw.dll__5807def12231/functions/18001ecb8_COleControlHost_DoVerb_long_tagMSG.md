# COleControlHost::_DoVerb(long,tagMSG *)

- ea: `0x18001ecb8`
- end: `0x18001ed50`
- name: `?_DoVerb@COleControlHost@@IEAAJJPEAUtagMSG@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(COleControlHost *__hidden this, int, struct tagMSG *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e1b0`

## callees

- `0x180008320`
- `0x18001ecb8`
- `0x180029010`

## import_xrefs

- `USER32!SetRectEmpty` at `0x18001ecf7`
- `USER32!SetRectEmpty` at `0x18001ecf7`
- `USER32!GetClientRect` at `0x18001ece8`
- `USER32!GetClientRect` at `0x18001ece8`

## pseudocode

```c
__int64 __fastcall COleControlHost::_DoVerb(COleControlHost *this, unsigned int a2, struct tagMSG *a3)
{
  HWND v5; // rcx
  __int64 result; // rax
  struct tagRECT Rect; // [rsp+40h] [rbp-38h] BYREF

  v5 = (HWND)*((_QWORD *)this + 10);
  Rect = 0;
  if ( !GetClientRect(v5, &Rect) )
    SetRectEmpty(&Rect);
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagMSG *, COleControlHost *, _DWORD, _QWORD, struct tagRECT *))(**((_QWORD **)this + 14) + 88LL))(
             *((_QWORD *)this + 14),
             a2,
             a3,
             this,
             0,
             *((_QWORD *)this + 10),
             &Rect);
  if ( (int)result >= 0 )
    *((_DWORD *)this + 18) = 1;
  return result;
}

```

## disassembly

```asm
0x18001ecb8  push    rbx
0x18001ecba  push    rsi
0x18001ecbb  push    rdi
0x18001ecbc  sub     rsp, 60h
0x18001ecc0  mov     rax, cs:__security_cookie
0x18001ecc7  xor     rax, rsp
0x18001ecca  mov     [rsp+78h+var_28], rax
0x18001eccf  mov     edi, edx
0x18001ecd1  mov     rbx, rcx
0x18001ecd4  mov     rcx, [rcx+50h]; hWnd
0x18001ecd8  lea     rdx, [rsp+78h+Rect]; lpRect
0x18001ecdd  xorps   xmm0, xmm0
0x18001ece0  mov     rsi, r8
0x18001ece3  movups  xmmword ptr [rsp+78h+Rect.left], xmm0
0x18001ece8  call    cs:__imp_GetClientRect
0x18001ecee  test    eax, eax
0x18001ecf0  jnz     short loc_18001ECFD
0x18001ecf2  lea     rcx, [rsp+78h+Rect]; lprc
0x18001ecf7  call    cs:__imp_SetRectEmpty
0x18001ecfd  mov     r9, [rbx+50h]
0x18001ed01  lea     rdx, [rsp+78h+Rect]
0x18001ed06  mov     rcx, [rbx+70h]
0x18001ed0a  mov     r8, rsi
0x18001ed0d  mov     [rsp+78h+var_48], rdx
0x18001ed12  mov     edx, edi
0x18001ed14  mov     [rsp+78h+var_50], r9
0x18001ed19  mov     r9, rbx
0x18001ed1c  mov     [rsp+78h+var_58], 0
0x18001ed24  mov     rax, [rcx]
0x18001ed27  mov     rax, [rax+58h]
0x18001ed2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed30  test    eax, eax
0x18001ed32  js      short loc_18001ED3B
0x18001ed34  mov     dword ptr [rbx+48h], 1
0x18001ed3b  mov     rcx, [rsp+78h+var_28]
0x18001ed40  xor     rcx, rsp; StackCookie
0x18001ed43  call    __security_check_cookie
0x18001ed48  add     rsp, 60h
0x18001ed4c  pop     rdi
0x18001ed4d  pop     rsi
0x18001ed4e  pop     rbx
0x18001ed4f  retn
```
