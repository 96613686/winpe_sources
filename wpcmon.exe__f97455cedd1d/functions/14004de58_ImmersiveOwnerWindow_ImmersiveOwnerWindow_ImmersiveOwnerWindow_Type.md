# ImmersiveOwnerWindow::ImmersiveOwnerWindow(ImmersiveOwnerWindow::Type)

- ea: `0x14004de58`
- end: `0x14004e1f7`
- name: `??0ImmersiveOwnerWindow@@QEAA@W4Type@0@@Z`
- size: `927`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x14003ebe0`

## callees

- `0x140005530`
- `0x1400057f0`
- `0x140006338`
- `0x140042c44`
- `0x14004d9c0`
- `0x14004dd64`
- `0x14004de58`
- `0x14004e3d4`
- `0x14004e4e8`
- `0x140060f58`
- `0x140078c9c`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004e1c8`
- `KERNEL32!GetLastError` at `0x14004e1c8`
- `USER32!CreateWindowInBand` at `0x14004df7f`
- `USER32!CreateWindowInBand` at `0x14004df7f`
- `USER32!SetWindowLongPtrW` at `0x14004e005`
- `USER32!SetWindowLongPtrW` at `0x14004e005`
- `USER32!InvalidateRect` at `0x14004e013`
- `USER32!InvalidateRect` at `0x14004e013`

## pseudocode

```c
_QWORD *__fastcall ImmersiveOwnerWindow::ImmersiveOwnerWindow(_QWORD *a1)
{
  _QWORD *v2; // rbx
  _DWORD *v3; // rax
  _QWORD *v4; // rax
  __int64 WindowInBand; // rbx
  _QWORD *v6; // rdx
  HWND v7; // rsi
  __int64 v8; // rax
  HWND v9; // rbx
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rdi
  _QWORD *v13; // rax
  _QWORD *v14; // rdx
  volatile signed __int32 *v15; // rdi
  volatile signed __int32 *v16; // rdi
  signed int LastError; // eax
  int *p_pExceptionObject; // [rsp+70h] [rbp-90h] BYREF
  HWND hWnd[2]; // [rsp+78h] [rbp-88h] BYREF
  int pExceptionObject; // [rsp+88h] [rbp-78h] BYREF
  HWND v22; // [rsp+90h] [rbp-70h]
  HWND v23; // [rsp+98h] [rbp-68h]
  __int64 v24; // [rsp+C0h] [rbp-40h]
  _QWORD *v25; // [rsp+C8h] [rbp-38h]
  _BYTE v26[8]; // [rsp+D0h] [rbp-30h] BYREF
  volatile signed __int32 *v27; // [rsp+D8h] [rbp-28h]
  _QWORD v28[7]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v29; // [rsp+118h] [rbp+18h]

  v25 = a1;
  v2 = operator new(0x40u);
  MessageWindow::MessageWindow(v2);
  v2[3] = 0;
  v2[4] = 0;
  v2[5] = 0;
  v2[6] = 0;
  v2[7] = 0;
  *a1 = 0;
  a1[1] = 0;
  v3 = operator new(0x18u);
  HIDWORD(p_pExceptionObject) = HIDWORD(v3);
  *(_OWORD *)v3 = 0;
  v3[2] = 1;
  v3[3] = 1;
  *(_QWORD *)v3 = std::_Ref_count<`anonymous namespace'::ImmersiveOwnerWindowImpl>::`vftable';
  *((_QWORD *)v3 + 2) = v2;
  *a1 = v2;
  a1[1] = v3;
  LODWORD(p_pExceptionObject) = 1;
  lambda_f3a3799627553aa18d3421542b4bc18a_::operator()(&p_pExceptionObject, hWnd);
  v28[0] = &std::_Func_impl_no_alloc<_lambda_5a23f881ed71537ce9c1466d6c70b6dd_,void,HWND__ *>::`vftable';
  v29 = v28;
  v4 = (_QWORD *)Global<unsigned short const *>::Get((Globals *)&off_1400F1470);
  WindowInBand = CreateWindowInBand(
                   0,
                   *v4,
                   0,
                   2415919104LL,
                   hWnd[0],
                   HIDWORD(hWnd[0]),
                   LODWORD(hWnd[1]) - LODWORD(hWnd[0]),
                   HIDWORD(hWnd[1]) - HIDWORD(hWnd[0]),
                   0,
                   0,
                   0,
                   0,
                   4);
  *(_OWORD *)hWnd = 0;
  if ( !WindowInBand )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, LastError);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  p_pExceptionObject = &pExceptionObject;
  v24 = 0;
  if ( v29 )
    v24 = (*(__int64 (__fastcall **)(_QWORD *, int *))*v29)(v29, &pExceptionObject);
  std::shared_ptr<HWND__>::reset<HWND__,std::function<void (HWND__ *)>,0>(hWnd, WindowInBand, &pExceptionObject);
  if ( v29 )
  {
    v6 = v28;
    LOBYTE(v6) = v29 != v28;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v29 + 32LL))(v29, v6);
  }
  v7 = hWnd[0];
  SetWindowLongPtrW(hWnd[0], -21, 3);
  InvalidateRect(v7, 0, 1);
  v8 = *a1;
  v9 = hWnd[1];
  if ( hWnd[1] )
    _InterlockedAdd((volatile signed __int32 *)hWnd[1] + 2, 1u);
  *(_QWORD *)(v8 + 48) = v7;
  v10 = *(volatile signed __int32 **)(v8 + 56);
  *(_QWORD *)(v8 + 56) = v9;
  if ( v10 )
  {
    if ( !_InterlockedDecrement(v10 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( !_InterlockedDecrement(v10 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  pExceptionObject = 1;
  if ( v9 )
    _InterlockedAdd((volatile signed __int32 *)v9 + 2, 1u);
  v22 = v7;
  v23 = v9;
  v11 = *a1;
  v12 = *a1 + 24LL;
  LODWORD(p_pExceptionObject) = 126;
  v13 = (_QWORD *)SignalMap_unsigned_int_Optional___int64____cdecl_unsigned___int64___int64__::Connect__lambda_b8bbf78375783adafe59a0f4fa3033e9__const___(
                    v11,
                    v26,
                    &p_pExceptionObject,
                    &pExceptionObject);
  v14 = *(_QWORD **)(v12 + 8);
  if ( v14 == *(_QWORD **)(v12 + 16) )
  {
    std::vector<std::shared_ptr<void>>::_Emplace_reallocate<std::shared_ptr<void>>(v12, v14, v13);
  }
  else
  {
    *v14 = 0;
    v14[1] = 0;
    *v14 = *v13;
    v14[1] = v13[1];
    *v13 = 0;
    v13[1] = 0;
    *(_QWORD *)(v12 + 8) += 16LL;
  }
  v15 = v27;
  if ( v27 )
  {
    if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  v16 = (volatile signed __int32 *)v23;
  if ( v23 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(HWND))v9)(v9);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(HWND))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14004de58  push    rbp
0x14004de5a  push    rbx
0x14004de5b  push    rsi
0x14004de5c  push    rdi
0x14004de5d  push    r12
0x14004de5f  push    r13
0x14004de61  push    r14
0x14004de63  push    r15
0x14004de65  lea     rbp, [rsp-38h]
0x14004de6a  sub     rsp, 138h
0x14004de71  mov     rax, cs:__security_cookie
0x14004de78  xor     rax, rsp
0x14004de7b  mov     [rbp+70h+var_50], rax
0x14004de7f  mov     r14, rcx
0x14004de82  mov     [rbp+70h+var_A8], rcx
0x14004de86  mov     ecx, 40h ; '@'; Size
0x14004de8b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004de90  mov     rbx, rax
0x14004de93  mov     [rsp+170h+var_100], rax
0x14004de98  mov     rcx, rax
0x14004de9b  call    ??0MessageWindow@@QEAA@W4Type@0@@Z; MessageWindow::MessageWindow(MessageWindow::Type)
0x14004dea0  xor     r12d, r12d
0x14004dea3  mov     [rbx+18h], r12
0x14004dea7  mov     [rbx+20h], r12
0x14004deab  mov     [rbx+28h], r12
0x14004deaf  mov     [rbx+30h], r12
0x14004deb3  mov     [rbx+38h], r12
0x14004deb7  mov     [r14], r12
0x14004deba  mov     [r14+8], r12
0x14004debe  mov     [rsp+170h+var_100], rbx
0x14004dec3  lea     ecx, [r12+18h]; Size
0x14004dec8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004decd  mov     [rsp+170h+var_100], rax
0x14004ded2  xorps   xmm0, xmm0
0x14004ded5  movups  xmmword ptr [rax], xmm0
0x14004ded8  lea     r13d, [r12+1]
0x14004dedd  mov     [rax+8], r13d
0x14004dee1  mov     [rax+0Ch], r13d
0x14004dee5  lea     rcx, ??_7?$_Ref_count@UImmersiveOwnerWindowImpl@?A0xd70dfc3a@@@std@@6B@; const std::_Ref_count<`anonymous namespace'::ImmersiveOwnerWindowImpl>::`vftable'
0x14004deec  mov     [rax], rcx
0x14004deef  mov     [rax+10h], rbx
0x14004def3  mov     [r14], rbx
0x14004def6  mov     [r14+8], rax
0x14004defa  mov     dword ptr [rsp+170h+var_100], r13d
0x14004deff  lea     rdx, [rsp+170h+hWnd]
0x14004df04  lea     rcx, [rsp+170h+var_100]
0x14004df09  call    _lambda_f3a3799627553aa18d3421542b4bc18a___operator__
0x14004df0e  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_5a23f881ed71537ce9c1466d6c70b6dd_@@XPEAUHWND__@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_5a23f881ed71537ce9c1466d6c70b6dd_,void,HWND__ *>::`vftable'
0x14004df15  mov     [rbp+70h+var_90], rax
0x14004df19  lea     rax, [rbp+70h+var_90]
0x14004df1d  mov     [rbp+70h+var_58], rax
0x14004df21  lea     rcx, off_1400F1470; this
0x14004df28  call    ?Get@?$Global@PEBG@@QEAAAEAPEBGXZ; Global<ushort const *>::Get(void)
0x14004df2d  mov     r10, rax
0x14004df30  mov     edx, dword ptr [rbp+70h+hWnd+0Ch]
0x14004df33  mov     r8d, dword ptr [rsp+170h+hWnd+4]
0x14004df38  sub     edx, r8d
0x14004df3b  mov     eax, dword ptr [rbp+70h+hWnd+8]
0x14004df3e  mov     ecx, dword ptr [rsp+170h+hWnd]
0x14004df42  sub     eax, ecx
0x14004df44  mov     [rsp+170h+var_110], 4
0x14004df4c  mov     [rsp+170h+var_118], r12
0x14004df51  mov     [rsp+170h+var_120], r12
0x14004df56  mov     [rsp+170h+var_128], r12
0x14004df5b  mov     [rsp+170h+var_130], r12
0x14004df60  mov     [rsp+170h+var_138], edx
0x14004df64  mov     [rsp+170h+var_140], eax
0x14004df68  mov     [rsp+170h+var_148], r8d
0x14004df6d  mov     [rsp+170h+var_150], ecx
0x14004df71  mov     r9d, 90000000h
0x14004df77  xor     r8d, r8d
0x14004df7a  mov     rdx, [r10]
0x14004df7d  xor     ecx, ecx
0x14004df7f  call    cs:__imp_CreateWindowInBand
0x14004df85  mov     rbx, rax
0x14004df88  xorps   xmm0, xmm0
0x14004df8b  movdqu  xmmword ptr [rsp+170h+hWnd], xmm0
0x14004df91  test    rax, rax
0x14004df94  jz      loc_14004E1C8
0x14004df9a  lea     rax, [rbp+70h+pExceptionObject]
0x14004df9e  mov     [rsp+170h+var_100], rax
0x14004dfa3  mov     [rbp+70h+var_B0], r12
0x14004dfa7  mov     rcx, [rbp+70h+var_58]
0x14004dfab  test    rcx, rcx
0x14004dfae  jz      short loc_14004DFC3
0x14004dfb0  mov     rax, [rcx]
0x14004dfb3  lea     rdx, [rbp+70h+pExceptionObject]
0x14004dfb7  mov     rax, [rax]
0x14004dfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dfbf  mov     [rbp+70h+var_B0], rax
0x14004dfc3  lea     r8, [rbp+70h+pExceptionObject]
0x14004dfc7  mov     rdx, rbx
0x14004dfca  lea     rcx, [rsp+170h+hWnd]
0x14004dfcf  call    ??$reset@UHWND__@@V?$function@$$A6AXPEAUHWND__@@@Z@std@@$0A@@?$shared_ptr@UHWND__@@@std@@QEAAXPEAUHWND__@@V?$function@$$A6AXPEAUHWND__@@@Z@1@@Z; std::shared_ptr<HWND__>::reset<HWND__,std::function<void (HWND__ *)>,0>(HWND__ *,std::function<void (HWND__ *)>)
0x14004dfd4  nop
0x14004dfd5  mov     rcx, [rbp+70h+var_58]
0x14004dfd9  test    rcx, rcx
0x14004dfdc  jz      short loc_14004DFF4
0x14004dfde  mov     rax, [rcx]
0x14004dfe1  lea     rdx, [rbp+70h+var_90]
0x14004dfe5  cmp     rcx, rdx
0x14004dfe8  setnz   dl
0x14004dfeb  mov     rax, [rax+20h]
0x14004dfef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dff4  mov     edx, 0FFFFFFEBh; nIndex
0x14004dff9  lea     r8d, [rdx+18h]; dwNewLong
0x14004dffd  mov     rsi, [rsp+170h+hWnd]
0x14004e002  mov     rcx, rsi; hWnd
0x14004e005  call    cs:__imp_SetWindowLongPtrW
0x14004e00b  mov     r8d, r13d; bErase
0x14004e00e  xor     edx, edx; lpRect
0x14004e010  mov     rcx, rsi; hWnd
0x14004e013  call    cs:__imp_InvalidateRect
0x14004e019  mov     rax, [r14]
0x14004e01c  mov     rbx, [rbp+70h+hWnd+8]
0x14004e020  test    rbx, rbx
0x14004e023  jz      short loc_14004E02A
0x14004e025  lock add [rbx+8], r13d
0x14004e02a  mov     [rax+30h], rsi
0x14004e02e  mov     rdi, [rax+38h]
0x14004e032  mov     [rax+38h], rbx
0x14004e036  or      r15d, 0FFFFFFFFh
0x14004e03a  test    rdi, rdi
0x14004e03d  jz      short loc_14004E076
0x14004e03f  mov     eax, r15d
0x14004e042  lock xadd [rdi+8], eax
0x14004e047  add     eax, r15d
0x14004e04a  jnz     short loc_14004E076
0x14004e04c  mov     rax, [rdi]
0x14004e04f  mov     rcx, rdi
0x14004e052  mov     rax, [rax]
0x14004e055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e05a  mov     eax, r15d
0x14004e05d  lock xadd [rdi+0Ch], eax
0x14004e062  add     eax, r15d
0x14004e065  jnz     short loc_14004E076
0x14004e067  mov     rax, [rdi]
0x14004e06a  mov     rcx, rdi
0x14004e06d  mov     rax, [rax+8]
0x14004e071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e076  mov     [rbp+70h+pExceptionObject], r13d
0x14004e07a  test    rbx, rbx
0x14004e07d  jz      short loc_14004E084
0x14004e07f  lock add [rbx+8], r13d
0x14004e084  mov     [rbp+70h+var_E0], rsi
0x14004e088  mov     [rbp+70h+var_D8], rbx
0x14004e08c  mov     rcx, [r14]
0x14004e08f  lea     rdi, [rcx+18h]
0x14004e093  mov     dword ptr [rsp+170h+var_100], 7Eh ; '~'
0x14004e09b  lea     r9, [rbp+70h+pExceptionObject]
0x14004e09f  lea     r8, [rsp+170h+var_100]
0x14004e0a4  lea     rdx, [rbp+70h+var_A0]
0x14004e0a8  call    SignalMap_unsigned_int_Optional___int64____cdecl_unsigned___int64___int64____Connect__lambda_b8bbf78375783adafe59a0f4fa3033e9__const___
0x14004e0ad  mov     r8, rax
0x14004e0b0  mov     rdx, [rdi+8]
0x14004e0b4  cmp     rdx, [rdi+10h]
0x14004e0b8  jz      short loc_14004E0DD
0x14004e0ba  mov     [rdx], r12
0x14004e0bd  mov     [rdx+8], r12
0x14004e0c1  mov     rax, [rax]
0x14004e0c4  mov     [rdx], rax
0x14004e0c7  mov     rax, [r8+8]
0x14004e0cb  mov     [rdx+8], rax
0x14004e0cf  mov     [r8], r12
0x14004e0d2  mov     [r8+8], r12
0x14004e0d6  add     qword ptr [rdi+8], 10h
0x14004e0db  jmp     short loc_14004E0E6
0x14004e0dd  mov     rcx, rdi
0x14004e0e0  call    ??$_Emplace_reallocate@V?$shared_ptr@X@std@@@?$vector@V?$shared_ptr@X@std@@V?$allocator@V?$shared_ptr@X@std@@@2@@std@@AEAAPEAV?$shared_ptr@X@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<void>>::_Emplace_reallocate<std::shared_ptr<void>>(std::shared_ptr<void> * const,std::shared_ptr<void> &&)
0x14004e0e5  nop
0x14004e0e6  mov     rdi, [rbp+70h+var_98]
0x14004e0ea  test    rdi, rdi
0x14004e0ed  jz      short loc_14004E127
0x14004e0ef  mov     eax, r15d
0x14004e0f2  lock xadd [rdi+8], eax
0x14004e0f7  add     eax, r15d
0x14004e0fa  jnz     short loc_14004E127
0x14004e0fc  mov     rax, [rdi]
0x14004e0ff  mov     rcx, rdi
0x14004e102  mov     rax, [rax]
0x14004e105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e10a  mov     eax, r15d
0x14004e10d  lock xadd [rdi+0Ch], eax
0x14004e112  add     eax, r15d
0x14004e115  jnz     short loc_14004E127
0x14004e117  mov     rax, [rdi]
0x14004e11a  mov     rcx, rdi
0x14004e11d  mov     rax, [rax+8]
0x14004e121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e126  nop
0x14004e127  mov     rdi, [rbp+70h+var_D8]
0x14004e12b  test    rdi, rdi
0x14004e12e  jz      short loc_14004E168
0x14004e130  mov     eax, r15d
0x14004e133  lock xadd [rdi+8], eax
0x14004e138  add     eax, r15d
0x14004e13b  jnz     short loc_14004E168
0x14004e13d  mov     rax, [rdi]
0x14004e140  mov     rcx, rdi
0x14004e143  mov     rax, [rax]
0x14004e146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e14b  mov     eax, r15d
0x14004e14e  lock xadd [rdi+0Ch], eax
0x14004e153  add     eax, r15d
0x14004e156  jnz     short loc_14004E168
0x14004e158  mov     rax, [rdi]
0x14004e15b  mov     rcx, rdi
0x14004e15e  mov     rax, [rax+8]
0x14004e162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e167  nop
0x14004e168  test    rbx, rbx
0x14004e16b  jz      short loc_14004E1A5
0x14004e16d  mov     eax, r15d
0x14004e170  lock xadd [rbx+8], eax
0x14004e175  add     eax, r15d
0x14004e178  jnz     short loc_14004E1A5
0x14004e17a  mov     rax, [rbx]
0x14004e17d  mov     rcx, rbx
0x14004e180  mov     rax, [rax]
0x14004e183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e188  mov     edx, r15d
0x14004e18b  lock xadd [rbx+0Ch], edx
0x14004e190  add     edx, r15d
0x14004e193  jnz     short loc_14004E1A5
0x14004e195  mov     rdx, [rbx]
0x14004e198  mov     rcx, rbx
0x14004e19b  mov     rax, [rdx+8]
0x14004e19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e1a4  nop
0x14004e1a5  mov     rax, r14
0x14004e1a8  mov     rcx, [rbp+70h+var_50]
0x14004e1ac  xor     rcx, rsp; StackCookie
0x14004e1af  call    __security_check_cookie
0x14004e1b4  add     rsp, 138h
0x14004e1bb  pop     r15
0x14004e1bd  pop     r14
0x14004e1bf  pop     r13
0x14004e1c1  pop     r12
0x14004e1c3  pop     rdi
0x14004e1c4  pop     rsi
0x14004e1c5  pop     rbx
0x14004e1c6  pop     rbp
0x14004e1c7  retn
0x14004e1c8  call    cs:__imp_GetLastError
0x14004e1ce  nop
0x14004e1cf  test    eax, eax
0x14004e1d1  jle     short loc_14004E1DB
0x14004e1d3  movzx   eax, ax
0x14004e1d6  or      eax, 80070000h
0x14004e1db  mov     edx, eax; int
0x14004e1dd  lea     rcx, [rbp+70h+pExceptionObject]; this
0x14004e1e1  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14004e1e6  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14004e1ed  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x14004e1f1  call    _CxxThrowException_0
```
