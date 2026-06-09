# COleControlHost::_Activate(void)

- ea: `0x18001ebd4`
- end: `0x18001ecaf`
- name: `?_Activate@COleControlHost@@IEAAJXZ`
- size: `219`
- prototype: `__int64 __fastcall(COleControlHost *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f0a4`

## callees

- `0x180008320`
- `0x18001ebd4`
- `0x18001f3dc`
- `0x180029010`

## import_xrefs

- `USER32!SetRectEmpty` at `0x18001ec19`
- `USER32!SetRectEmpty` at `0x18001ec19`
- `USER32!GetClientRect` at `0x18001ec0a`
- `USER32!GetClientRect` at `0x18001ec0a`

## pseudocode

```c
__int64 __fastcall COleControlHost::_Activate(HWND *this)
{
  __int64 result; // rax
  struct tagRECT Rect; // [rsp+40h] [rbp-28h] BYREF

  Rect = 0;
  COleControlHost::_SendNotify((COleControlHost *)this, 0x1303u, 0);
  if ( !GetClientRect(this[10], &Rect) )
    SetRectEmpty(&Rect);
  result = (*(__int64 (__fastcall **)(HWND, __int64, _QWORD, HWND *, _DWORD, HWND, struct tagRECT *))(*(_QWORD *)this[14] + 88LL))(
             this[14],
             4294967291LL,
             0,
             this,
             0,
             this[10],
             &Rect);
  if ( (int)result >= 0 )
    *((_DWORD *)this + 18) = 1;
  if ( ((_DWORD)this[8] & 0x400) == 0 )
    return (*(__int64 (__fastcall **)(HWND, __int64, _QWORD, HWND *, _DWORD, HWND, struct tagRECT *))(*(_QWORD *)this[14] + 88LL))(
             this[14],
             0xFFFFFFFFLL,
             0,
             this,
             0,
             this[10],
             &Rect);
  return result;
}

```

## disassembly

```asm
0x18001ebd4  push    rbx
0x18001ebd6  sub     rsp, 60h
0x18001ebda  mov     rax, cs:__security_cookie
0x18001ebe1  xor     rax, rsp
0x18001ebe4  mov     [rsp+68h+var_18], rax
0x18001ebe9  xorps   xmm0, xmm0
0x18001ebec  xor     r8d, r8d; struct tagNMHDR *
0x18001ebef  mov     edx, 1303h; unsigned int
0x18001ebf4  mov     rbx, rcx
0x18001ebf7  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x18001ebfc  call    ?_SendNotify@COleControlHost@@IEAA_JIPEAUtagNMHDR@@@Z; COleControlHost::_SendNotify(uint,tagNMHDR *)
0x18001ec01  mov     rcx, [rbx+50h]; hWnd
0x18001ec05  lea     rdx, [rsp+68h+Rect]; lpRect
0x18001ec0a  call    cs:__imp_GetClientRect
0x18001ec10  test    eax, eax
0x18001ec12  jnz     short loc_18001EC1F
0x18001ec14  lea     rcx, [rsp+68h+Rect]; lprc
0x18001ec19  call    cs:__imp_SetRectEmpty
0x18001ec1f  mov     rcx, [rbx+70h]
0x18001ec23  lea     rdx, [rsp+68h+Rect]
0x18001ec28  mov     [rsp+68h+var_38], rdx
0x18001ec2d  xor     r8d, r8d
0x18001ec30  mov     rdx, [rbx+50h]
0x18001ec34  mov     r9, rbx
0x18001ec37  mov     [rsp+68h+var_40], rdx
0x18001ec3c  mov     rax, [rcx]
0x18001ec3f  lea     edx, [r8-5]
0x18001ec43  mov     [rsp+68h+var_48], 0
0x18001ec4b  mov     rax, [rax+58h]
0x18001ec4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec54  test    eax, eax
0x18001ec56  js      short loc_18001EC5F
0x18001ec58  mov     dword ptr [rbx+48h], 1
0x18001ec5f  test    dword ptr [rbx+40h], 400h
0x18001ec66  jnz     short loc_18001EC9C
0x18001ec68  mov     rcx, [rbx+70h]
0x18001ec6c  lea     rdx, [rsp+68h+Rect]
0x18001ec71  mov     [rsp+68h+var_38], rdx
0x18001ec76  mov     r9, rbx
0x18001ec79  mov     rdx, [rbx+50h]
0x18001ec7d  xor     r8d, r8d
0x18001ec80  mov     [rsp+68h+var_40], rdx
0x18001ec85  or      edx, 0FFFFFFFFh
0x18001ec88  mov     rax, [rcx]
0x18001ec8b  mov     [rsp+68h+var_48], 0
0x18001ec93  mov     rax, [rax+58h]
0x18001ec97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec9c  mov     rcx, [rsp+68h+var_18]
0x18001eca1  xor     rcx, rsp; StackCookie
0x18001eca4  call    __security_check_cookie
0x18001eca9  add     rsp, 60h
0x18001ecad  pop     rbx
0x18001ecae  retn
```
