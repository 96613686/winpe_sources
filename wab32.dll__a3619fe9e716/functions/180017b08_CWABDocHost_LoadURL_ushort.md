# CWABDocHost::LoadURL(ushort *)

- ea: `0x180017b08`
- end: `0x180017c3f`
- name: `?LoadURL@CWABDocHost@@QEAAJPEAG@Z`
- size: `311`
- prototype: `__int64 __fastcall(CWABDocHost *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004cb0c`

## callees

- `0x180017934`
- `0x180017b08`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180017b85`
- `ole32!CoCreateInstance` at `0x180017b85`
- `USER32!LoadCursorW` at `0x180017b3c`
- `USER32!LoadCursorW` at `0x180017b3c`
- `USER32!GetClientRect` at `0x180017bd3`
- `USER32!GetClientRect` at `0x180017bd3`
- `USER32!SetCursor` at `0x180017b45`
- `USER32!SetCursor` at `0x180017c16`
- `USER32!SetCursor` at `0x180017b45`
- `USER32!SetCursor` at `0x180017c16`

## pseudocode

```c
__int64 __fastcall CWABDocHost::LoadURL(CWABDocHost *this, unsigned __int16 *a2)
{
  HCURSOR CursorW; // rax
  HCURSOR v5; // rbp
  HRESULT Instance; // ebx
  _QWORD *v7; // rsi
  struct tagRECT Rect; // [rsp+40h] [rbp-48h] BYREF

  Rect = 0;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v5 = SetCursor(CursorW);
  if ( a2 )
  {
    Instance = 0;
    v7 = (_QWORD *)((char *)this + 56);
    if ( !*((_QWORD *)this + 7) )
    {
      Instance = CoCreateInstance(&CLSID_HTMLDocument, 0, 3u, &IID_IOleObject, (LPVOID *)this + 7);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*v7 + 24LL))(
                     *v7,
                     ((unsigned __int64)this + 16) & -(__int64)(this != 0));
        if ( Instance >= 0 )
        {
          Instance = HrLoadTheURL(this, a2);
          if ( Instance >= 0 )
          {
            GetClientRect(*((HWND *)this + 5), &Rect);
            Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, unsigned __int64, _DWORD, _QWORD, struct tagRECT *))(*(_QWORD *)*v7 + 88LL))(
                         *v7,
                         0xFFFFFFFFLL,
                         0,
                         ((unsigned __int64)this + 16) & -(__int64)(this != 0),
                         0,
                         *((_QWORD *)this + 5),
                         &Rect);
          }
        }
      }
    }
  }
  else
  {
    Instance = -2147024809;
  }
  if ( v5 )
    SetCursor(v5);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180017b08  mov     [rsp+arg_10], rbx
0x180017b0d  push    rbp
0x180017b0e  push    rsi
0x180017b0f  push    rdi
0x180017b10  push    r14
0x180017b12  push    r15
0x180017b14  sub     rsp, 60h
0x180017b18  mov     rax, cs:__security_cookie
0x180017b1f  xor     rax, rsp
0x180017b22  mov     [rsp+88h+var_38], rax
0x180017b27  mov     r15, rdx
0x180017b2a  mov     rdi, rcx
0x180017b2d  xorps   xmm0, xmm0
0x180017b30  mov     edx, 7F02h; lpCursorName
0x180017b35  xor     ecx, ecx; hInstance
0x180017b37  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x180017b3c  call    cs:__imp_LoadCursorW
0x180017b42  mov     rcx, rax; hCursor
0x180017b45  call    cs:__imp_SetCursor
0x180017b4b  mov     rbp, rax
0x180017b4e  test    r15, r15
0x180017b51  jnz     short loc_180017B5D
0x180017b53  mov     ebx, 80070057h
0x180017b58  jmp     loc_180017C0E
0x180017b5d  xor     ebx, ebx
0x180017b5f  lea     rsi, [rdi+38h]
0x180017b63  cmp     [rsi], rbx
0x180017b66  jnz     loc_180017C0E
0x180017b6c  lea     r9, IID_IOleObject; riid
0x180017b73  mov     [rsp+88h+ppv], rsi; ppv
0x180017b78  xor     edx, edx; pUnkOuter
0x180017b7a  lea     r8d, [rbx+3]; dwClsContext
0x180017b7e  lea     rcx, CLSID_HTMLDocument; rclsid
0x180017b85  call    cs:__imp_CoCreateInstance
0x180017b8b  mov     ebx, eax
0x180017b8d  test    eax, eax
0x180017b8f  js      short loc_180017C0E
0x180017b91  mov     rcx, [rsi]
0x180017b94  lea     r8, [rdi+10h]
0x180017b98  mov     rax, rdi
0x180017b9b  neg     rax
0x180017b9e  mov     rax, [rcx]
0x180017ba1  sbb     r14, r14
0x180017ba4  and     r14, r8
0x180017ba7  mov     rdx, r14
0x180017baa  mov     rax, [rax+18h]
0x180017bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bb3  mov     ebx, eax
0x180017bb5  test    eax, eax
0x180017bb7  js      short loc_180017C0E
0x180017bb9  mov     rdx, r15; unsigned __int16 *
0x180017bbc  mov     rcx, rdi; this
0x180017bbf  call    ?HrLoadTheURL@@YAJPEAVCWABDocHost@@PEAG@Z; HrLoadTheURL(CWABDocHost *,ushort *)
0x180017bc4  mov     ebx, eax
0x180017bc6  test    eax, eax
0x180017bc8  js      short loc_180017C0E
0x180017bca  mov     rcx, [rdi+28h]; hWnd
0x180017bce  lea     rdx, [rsp+88h+Rect]; lpRect
0x180017bd3  call    cs:__imp_GetClientRect
0x180017bd9  mov     rcx, [rsi]
0x180017bdc  lea     rdx, [rsp+88h+Rect]
0x180017be1  mov     [rsp+88h+var_58], rdx
0x180017be6  mov     r9, r14
0x180017be9  mov     rdx, [rdi+28h]
0x180017bed  xor     r8d, r8d
0x180017bf0  mov     [rsp+88h+var_60], rdx
0x180017bf5  or      edx, 0FFFFFFFFh
0x180017bf8  mov     rax, [rcx]
0x180017bfb  mov     dword ptr [rsp+88h+ppv], 0
0x180017c03  mov     rax, [rax+58h]
0x180017c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c0c  mov     ebx, eax
0x180017c0e  test    rbp, rbp
0x180017c11  jz      short loc_180017C1C
0x180017c13  mov     rcx, rbp; hCursor
0x180017c16  call    cs:__imp_SetCursor
0x180017c1c  mov     eax, ebx
0x180017c1e  mov     rcx, [rsp+88h+var_38]
0x180017c23  xor     rcx, rsp; StackCookie
0x180017c26  call    __security_check_cookie
0x180017c2b  mov     rbx, [rsp+88h+arg_10]
0x180017c33  add     rsp, 60h
0x180017c37  pop     r15
0x180017c39  pop     r14
0x180017c3b  pop     rdi
0x180017c3c  pop     rsi
0x180017c3d  pop     rbp
0x180017c3e  retn
```
