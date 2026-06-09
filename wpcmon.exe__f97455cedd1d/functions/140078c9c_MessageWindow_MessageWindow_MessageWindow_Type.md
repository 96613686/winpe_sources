# MessageWindow::MessageWindow(MessageWindow::Type)

- ea: `0x140078c9c`
- end: `0x140078df1`
- name: `??0MessageWindow@@QEAA@W4Type@0@@Z`
- size: `341`
- prototype: `LONG_PTR __fastcall(LONG_PTR)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14004de58`
- `0x14008e20c`
- `0x140091fd0`

## callees

- `0x1400057f0`
- `0x140006338`
- `0x14004e4e8`
- `0x140060f58`
- `0x140078c9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140078d25`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140078d25`
- `USER32!CreateWindowExW` at `0x140078d9c`
- `USER32!CreateWindowExW` at `0x140078d9c`
- `USER32!SetWindowLongPtrW` at `0x140078db7`
- `USER32!SetWindowLongPtrW` at `0x140078db7`

## pseudocode

```c
LONG_PTR __fastcall MessageWindow::MessageWindow(LONG_PTR a1)
{
  _QWORD *v2; // rax
  LPCWSTR *v3; // rax
  _BYTE pExceptionObject[88]; // [rsp+70h] [rbp-58h] BYREF
  _QWORD *v6; // [rsp+E0h] [rbp+18h]
  char *v7; // [rsp+E8h] [rbp+20h]

  v7 = (char *)operator new(0x30u);
  *(_OWORD *)v7 = 0;
  *((_DWORD *)v7 + 2) = 1;
  *((_DWORD *)v7 + 3) = 1;
  *(_QWORD *)v7 = &std::_Ref_count_obj2<LockBox<std::map<unsigned int,std::weak_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>>>,4294967295>>::`vftable';
  *((_QWORD *)v7 + 2) = &LockBox<std::map<unsigned int,std::weak_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>>>,4294967295>::`vftable';
  *((_QWORD *)v7 + 4) = 0;
  *((_QWORD *)v7 + 5) = 0;
  v2 = operator new(0x38u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *((_QWORD *)v7 + 4) = v2;
  InitializeSRWLock((PSRWLOCK)v7 + 3);
  *(_QWORD *)a1 = v7 + 16;
  *(_QWORD *)(a1 + 8) = v7;
  if ( v7 == (char *)-16LL )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v6 = operator new(8u);
  *v6 = 0;
  *(_QWORD *)(a1 + 16) = v6;
  v3 = (LPCWSTR *)Global<unsigned short const *>::Get((Globals *)&off_1400F17B0);
  **(_QWORD **)(a1 + 16) = CreateWindowExW(0, *v3, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
  SetWindowLongPtrW(**(HWND **)(a1 + 16), -21, a1);
  return a1;
}

```

## disassembly

```asm
0x140078c9c  mov     rax, rsp
0x140078c9f  mov     [rax+8], rcx
0x140078ca3  push    rbx
0x140078ca4  push    rsi
0x140078ca5  push    rdi
0x140078ca6  push    r14
0x140078ca8  push    r15
0x140078caa  sub     rsp, 0A0h
0x140078cb1  mov     r14, rcx
0x140078cb4  xor     r15d, r15d
0x140078cb7  mov     [rax+18h], rcx
0x140078cbb  lea     ecx, [r15+30h]; Size
0x140078cbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140078cc4  mov     rsi, rax
0x140078cc7  mov     [rsp+0C8h+arg_18], rax
0x140078ccf  xorps   xmm0, xmm0
0x140078cd2  movups  xmmword ptr [rax], xmm0
0x140078cd5  mov     dword ptr [rax+8], 1
0x140078cdc  mov     dword ptr [rax+0Ch], 1
0x140078ce3  lea     rax, ??_7?$_Ref_count_obj2@V?$LockBox@V?$map@IV?$weak_ptr@V?$Signal@$$A6A?AV?$Optional@_J@@_K_J@Z@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$weak_ptr@V?$Signal@$$A6A?AV?$Optional@_J@@_K_J@Z@@@std@@@std@@@2@@std@@$0PPPPPPPP@@@@std@@6B@; const std::_Ref_count_obj2<LockBox<std::map<uint,std::weak_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>>>,4294967295>>::`vftable'
0x140078cea  mov     [rsi], rax
0x140078ced  lea     rdi, [rsi+10h]
0x140078cf1  lea     rax, ??_7?$LockBox@V?$map@IV?$weak_ptr@V?$Signal@$$A6A?AV?$Optional@_J@@_K_J@Z@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$weak_ptr@V?$Signal@$$A6A?AV?$Optional@_J@@_K_J@Z@@@std@@@std@@@2@@std@@$0PPPPPPPP@@@6B@; const LockBox<std::map<uint,std::weak_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>>>,4294967295>::`vftable'
0x140078cf8  mov     [rdi], rax
0x140078cfb  mov     [rdi+10h], r15
0x140078cff  mov     [rdi+18h], r15
0x140078d03  lea     ecx, [r15+38h]; Size
0x140078d07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140078d0c  mov     [rax], rax
0x140078d0f  mov     [rax+8], rax
0x140078d13  mov     [rax+10h], rax
0x140078d17  mov     word ptr [rax+18h], 101h
0x140078d1d  mov     [rdi+10h], rax
0x140078d21  lea     rcx, [rdi+8]; SRWLock
0x140078d25  call    cs:__imp_InitializeSRWLock
0x140078d2b  nop
0x140078d2c  mov     [r14], rdi
0x140078d2f  mov     [r14+8], rsi
0x140078d33  xorps   xmm0, xmm0
0x140078d36  movdqu  [rsp+0C8h+var_68], xmm0
0x140078d3c  test    rdi, rdi
0x140078d3f  jz      loc_140078DD0
0x140078d45  lea     ecx, [r15+8]; Size
0x140078d49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140078d4e  mov     [rsp+0C8h+arg_10], rax
0x140078d56  mov     [rax], r15
0x140078d59  mov     [r14+10h], rax
0x140078d5d  lea     rcx, off_1400F17B0; this
0x140078d64  call    ?Get@?$Global@PEBG@@QEAAAEAPEBGXZ; Global<ushort const *>::Get(void)
0x140078d69  mov     [rsp+0C8h+lpParam], r15; lpParam
0x140078d6e  mov     [rsp+0C8h+hInstance], r15; hInstance
0x140078d73  mov     [rsp+0C8h+hMenu], r15; hMenu
0x140078d78  mov     [rsp+0C8h+hWndParent], r15; hWndParent
0x140078d7d  mov     [rsp+0C8h+nHeight], r15d; nHeight
0x140078d82  mov     [rsp+0C8h+nWidth], r15d; nWidth
0x140078d87  mov     [rsp+0C8h+Y], r15d; Y
0x140078d8c  mov     [rsp+0C8h+X], r15d; X
0x140078d91  xor     r9d, r9d; dwStyle
0x140078d94  xor     r8d, r8d; lpWindowName
0x140078d97  mov     rdx, [rax]; lpClassName
0x140078d9a  xor     ecx, ecx; dwExStyle
0x140078d9c  call    cs:__imp_CreateWindowExW
0x140078da2  mov     rcx, [r14+10h]
0x140078da6  mov     [rcx], rax
0x140078da9  mov     rcx, [r14+10h]
0x140078dad  mov     r8, r14; dwNewLong
0x140078db0  lea     edx, [r15-15h]; nIndex
0x140078db4  mov     rcx, [rcx]; hWnd
0x140078db7  call    cs:__imp_SetWindowLongPtrW
0x140078dbd  nop
0x140078dbe  mov     rax, r14
0x140078dc1  add     rsp, 0A0h
0x140078dc8  pop     r15
0x140078dca  pop     r14
0x140078dcc  pop     rdi
0x140078dcd  pop     rsi
0x140078dce  pop     rbx
0x140078dcf  retn
0x140078dd0  mov     edx, 8000FFFFh; int
0x140078dd5  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x140078dda  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140078ddf  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140078de6  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x140078deb  call    _CxxThrowException_0
```
