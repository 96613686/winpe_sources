# ATL::CComControlBase::OnDrawAdvanced(ATL_DRAWINFO &)

- ea: `0x180007ca0`
- end: `0x180007eac`
- name: `?OnDrawAdvanced@CComControlBase@ATL@@UEAAJAEAUATL_DRAWINFO@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(ATL::CComControlBase *__hidden this, struct ATL_DRAWINFO *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002fd8`
- `0x180007ca0`
- `0x180014270`
- `0x180015010`

## import_xrefs

- `USER32!GetDC` at `0x180007d99`
- `USER32!GetDC` at `0x180007d99`
- `USER32!ReleaseDC` at `0x180007dc7`
- `USER32!ReleaseDC` at `0x180007dc7`
- `GDI32!LPtoDP` at `0x180007d26`
- `GDI32!LPtoDP` at `0x180007d26`
- `GDI32!SaveDC` at `0x180007d30`
- `GDI32!SaveDC` at `0x180007d30`
- `GDI32!DeleteDC` at `0x180007e6d`
- `GDI32!DeleteDC` at `0x180007e6d`
- `GDI32!SetMapMode` at `0x180007d41`
- `GDI32!SetMapMode` at `0x180007d41`
- `GDI32!SetWindowOrgEx` at `0x180007d53`
- `GDI32!SetWindowOrgEx` at `0x180007d53`
- `GDI32!SetViewportOrgEx` at `0x180007d65`
- `GDI32!SetViewportOrgEx` at `0x180007d65`
- `GDI32!GetDeviceCaps` at `0x180007d03`
- `GDI32!GetDeviceCaps` at `0x180007daa`
- `GDI32!GetDeviceCaps` at `0x180007dba`
- `GDI32!GetDeviceCaps` at `0x180007d03`
- `GDI32!GetDeviceCaps` at `0x180007daa`
- `GDI32!GetDeviceCaps` at `0x180007dba`
- `GDI32!RestoreDC` at `0x180007e7f`
- `GDI32!RestoreDC` at `0x180007e7f`
- `KERNEL32!MulDiv` at `0x180007dd9`
- `KERNEL32!MulDiv` at `0x180007ded`
- `KERNEL32!MulDiv` at `0x180007dd9`
- `KERNEL32!MulDiv` at `0x180007ded`

## pseudocode

```c
__int64 __fastcall ATL::CComControlBase::OnDrawAdvanced(ATL::CComControlBase *this, struct ATL_DRAWINFO *a2)
{
  int v2; // r12d
  HDC TargetDC; // rax
  bool v6; // zf
  HDC v7; // rcx
  int v8; // r13d
  __int64 v9; // rax
  HDC DC; // rbx
  int DeviceCaps; // edi
  int v12; // esi
  int v13; // ebx
  int v14; // edx
  int v15; // ecx
  int v16; // eax
  unsigned int v17; // ebx
  int nNumerator[2]; // [rsp+20h] [rbp-58h]
  tagPOINT pt[2]; // [rsp+28h] [rbp-50h] BYREF

  v2 = 0;
  if ( !*((_QWORD *)a2 + 3) )
  {
    TargetDC = ATL::AtlCreateTargetDC(*((HDC *)a2 + 4), *((struct tagDVTARGETDEVICE **)a2 + 2));
    v6 = TargetDC == *((HDC *)a2 + 4);
    *((_QWORD *)a2 + 3) = TargetDC;
    LOBYTE(v2) = !v6;
  }
  v7 = (HDC)*((_QWORD *)a2 + 4);
  *(_OWORD *)&pt[0].x = *(_OWORD *)*((_QWORD *)a2 + 5);
  if ( GetDeviceCaps(v7, 2) == 5 )
  {
    v8 = 1;
  }
  else
  {
    v8 = 0;
    LPtoDP(*((HDC *)a2 + 4), pt, 2);
    SaveDC(*((HDC *)a2 + 4));
    SetMapMode(*((HDC *)a2 + 4), 1);
    SetWindowOrgEx(*((HDC *)a2 + 4), 0, 0, 0);
    SetViewportOrgEx(*((HDC *)a2 + 4), 0, 0, 0);
    *((_DWORD *)a2 + 14) = 1;
  }
  *((_QWORD *)a2 + 5) = pt;
  if ( (*((_DWORD *)this + 25) & 0x1000) != 0 )
    v9 = *((_QWORD *)this + 7);
  else
    v9 = *((_QWORD *)this + 8);
  *(_QWORD *)nNumerator = v9;
  if ( *((_DWORD *)a2 + 16) )
  {
    v14 = HIDWORD(v9);
    v13 = v9;
  }
  else
  {
    DC = GetDC(0);
    DeviceCaps = GetDeviceCaps(DC, 88);
    v12 = GetDeviceCaps(DC, 90);
    ReleaseDC(0, DC);
    v13 = MulDiv(DeviceCaps, nNumerator[0], 2540);
    v14 = MulDiv(v12, nNumerator[1], 2540);
  }
  v15 = pt[1].x - pt[0].x;
  v16 = pt[1].y - pt[0].y;
  *((_DWORD *)a2 + 17) = pt[1].x - pt[0].x;
  *((_DWORD *)a2 + 18) = v16;
  *((_DWORD *)a2 + 19) = v13;
  *((_DWORD *)a2 + 20) = v14;
  if ( v13 && v14 && v15 && v16 )
  {
    if ( v15 != v13 || v16 != v14 )
    {
      *((_DWORD *)a2 + 15) = 1;
      goto LABEL_21;
    }
  }
  else
  {
    *((_DWORD *)a2 + 20) = 1;
    *((_DWORD *)a2 + 19) = 1;
    *((_DWORD *)a2 + 18) = 1;
    *((_DWORD *)a2 + 17) = 1;
  }
  *((_DWORD *)a2 + 15) = 0;
LABEL_21:
  v17 = (*(__int64 (__fastcall **)(ATL::CComControlBase *, struct ATL_DRAWINFO *))(*(_QWORD *)this + 32LL))(this, a2);
  if ( v2 )
    DeleteDC(*((HDC *)a2 + 3));
  if ( !v8 )
    RestoreDC(*((HDC *)a2 + 4), -1);
  return v17;
}

```

## disassembly

```asm
0x180007ca0  mov     [rsp+arg_10], rbx
0x180007ca5  push    rbp
0x180007ca6  push    rsi
0x180007ca7  push    rdi
0x180007ca8  push    r12
0x180007caa  push    r13
0x180007cac  push    r14
0x180007cae  push    r15
0x180007cb0  sub     rsp, 40h
0x180007cb4  mov     rax, cs:__security_cookie
0x180007cbb  xor     rax, rsp
0x180007cbe  mov     [rsp+78h+var_40], rax
0x180007cc3  xor     r12d, r12d
0x180007cc6  mov     rbp, rdx
0x180007cc9  mov     r15, rcx
0x180007ccc  cmp     [rdx+18h], r12
0x180007cd0  jnz     short loc_180007CEB
0x180007cd2  mov     rdx, [rdx+10h]; struct tagDVTARGETDEVICE *
0x180007cd6  mov     rcx, [rbp+20h]; HDC
0x180007cda  call    ?AtlCreateTargetDC@ATL@@YAPEAUHDC__@@PEAU2@PEAUtagDVTARGETDEVICE@@@Z; ATL::AtlCreateTargetDC(HDC__ *,tagDVTARGETDEVICE *)
0x180007cdf  cmp     rax, [rbp+20h]
0x180007ce3  mov     [rbp+18h], rax
0x180007ce7  setnz   r12b
0x180007ceb  mov     rax, [rbp+28h]
0x180007cef  mov     ebx, 2
0x180007cf4  mov     rcx, [rbp+20h]; hdc
0x180007cf8  mov     edx, ebx; index
0x180007cfa  movups  xmm0, xmmword ptr [rax]
0x180007cfd  movdqu  xmmword ptr [rsp+78h+pt.x], xmm0
0x180007d03  call    cs:__imp_GetDeviceCaps
0x180007d09  cmp     eax, 5
0x180007d0c  jnz     short loc_180007D17
0x180007d0e  lea     r14d, [rbx-1]
0x180007d12  mov     r13d, r14d
0x180007d15  jmp     short loc_180007D6F
0x180007d17  mov     rcx, [rbp+20h]; hdc
0x180007d1b  lea     rdx, [rsp+78h+pt]; lppt
0x180007d20  mov     r8d, ebx; c
0x180007d23  xor     r13d, r13d
0x180007d26  call    cs:__imp_LPtoDP
0x180007d2c  mov     rcx, [rbp+20h]; hdc
0x180007d30  call    cs:__imp_SaveDC
0x180007d36  mov     rcx, [rbp+20h]; hdc
0x180007d3a  lea     r14d, [r13+1]
0x180007d3e  mov     edx, r14d; iMode
0x180007d41  call    cs:__imp_SetMapMode
0x180007d47  mov     rcx, [rbp+20h]; hdc
0x180007d4b  xor     r9d, r9d; lppt
0x180007d4e  xor     r8d, r8d; y
0x180007d51  xor     edx, edx; x
0x180007d53  call    cs:__imp_SetWindowOrgEx
0x180007d59  mov     rcx, [rbp+20h]; hdc
0x180007d5d  xor     r9d, r9d; lppt
0x180007d60  xor     r8d, r8d; y
0x180007d63  xor     edx, edx; x
0x180007d65  call    cs:__imp_SetViewportOrgEx
0x180007d6b  mov     [rbp+38h], r14d
0x180007d6f  lea     rax, [rsp+78h+pt]
0x180007d74  mov     [rbp+28h], rax
0x180007d78  test    dword ptr [r15+64h], 1000h
0x180007d80  jz      short loc_180007D88
0x180007d82  mov     rax, [r15+38h]
0x180007d86  jmp     short loc_180007D8C
0x180007d88  mov     rax, [r15+40h]
0x180007d8c  cmp     dword ptr [rbp+40h], 0
0x180007d90  mov     qword ptr [rsp+78h+nNumerator], rax
0x180007d95  jnz     short loc_180007DF7
0x180007d97  xor     ecx, ecx; hWnd
0x180007d99  call    cs:__imp_GetDC
0x180007d9f  mov     rcx, rax; hdc
0x180007da2  mov     edx, 58h ; 'X'; index
0x180007da7  mov     rbx, rax
0x180007daa  call    cs:__imp_GetDeviceCaps
0x180007db0  mov     edx, 5Ah ; 'Z'; index
0x180007db5  mov     rcx, rbx; hdc
0x180007db8  mov     edi, eax
0x180007dba  call    cs:__imp_GetDeviceCaps
0x180007dc0  mov     rdx, rbx; hDC
0x180007dc3  xor     ecx, ecx; hWnd
0x180007dc5  mov     esi, eax
0x180007dc7  call    cs:__imp_ReleaseDC
0x180007dcd  mov     edx, [rsp+78h+nNumerator]; nNumerator
0x180007dd1  mov     r8d, 9ECh; nDenominator
0x180007dd7  mov     ecx, edi; nNumber
0x180007dd9  call    cs:__imp_MulDiv
0x180007ddf  mov     edx, [rsp+78h+nNumerator+4]; nNumerator
0x180007de3  mov     r8d, 9ECh; nDenominator
0x180007de9  mov     ecx, esi; nNumber
0x180007deb  mov     ebx, eax
0x180007ded  call    cs:__imp_MulDiv
0x180007df3  mov     edx, eax
0x180007df5  jmp     short loc_180007DFF
0x180007df7  mov     edx, [rsp+78h+nNumerator+4]
0x180007dfb  mov     ebx, [rsp+78h+nNumerator]
0x180007dff  mov     ecx, [rsp+78h+pt.x+8]
0x180007e03  sub     ecx, [rsp+78h+pt.x]
0x180007e07  mov     eax, [rsp+78h+pt.y+8]
0x180007e0b  sub     eax, [rsp+78h+pt.y]
0x180007e0f  mov     [rbp+44h], ecx
0x180007e12  mov     [rbp+48h], eax
0x180007e15  mov     [rbp+4Ch], ebx
0x180007e18  mov     [rbp+50h], edx
0x180007e1b  test    ebx, ebx
0x180007e1d  jz      short loc_180007E39
0x180007e1f  test    edx, edx
0x180007e21  jz      short loc_180007E39
0x180007e23  test    ecx, ecx
0x180007e25  jz      short loc_180007E39
0x180007e27  test    eax, eax
0x180007e29  jz      short loc_180007E39
0x180007e2b  cmp     ecx, ebx
0x180007e2d  jnz     short loc_180007E33
0x180007e2f  cmp     eax, edx
0x180007e31  jz      short loc_180007E49
0x180007e33  mov     [rbp+3Ch], r14d
0x180007e37  jmp     short loc_180007E50
0x180007e39  mov     [rbp+50h], r14d
0x180007e3d  mov     [rbp+4Ch], r14d
0x180007e41  mov     [rbp+48h], r14d
0x180007e45  mov     [rbp+44h], r14d
0x180007e49  mov     dword ptr [rbp+3Ch], 0
0x180007e50  mov     rax, [r15]
0x180007e53  mov     rdx, rbp
0x180007e56  mov     rcx, r15
0x180007e59  mov     rax, [rax+20h]
0x180007e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e62  mov     ebx, eax
0x180007e64  test    r12d, r12d
0x180007e67  jz      short loc_180007E73
0x180007e69  mov     rcx, [rbp+18h]; hdc
0x180007e6d  call    cs:__imp_DeleteDC
0x180007e73  test    r13d, r13d
0x180007e76  jnz     short loc_180007E85
0x180007e78  mov     rcx, [rbp+20h]; hdc
0x180007e7c  or      edx, 0FFFFFFFFh; nSavedDC
0x180007e7f  call    cs:__imp_RestoreDC
0x180007e85  mov     eax, ebx
0x180007e87  mov     rcx, [rsp+78h+var_40]
0x180007e8c  xor     rcx, rsp; StackCookie
0x180007e8f  call    __security_check_cookie
0x180007e94  mov     rbx, [rsp+78h+arg_10]
0x180007e9c  add     rsp, 40h
0x180007ea0  pop     r15
0x180007ea2  pop     r14
0x180007ea4  pop     r13
0x180007ea6  pop     r12
0x180007ea8  pop     rdi
0x180007ea9  pop     rsi
0x180007eaa  pop     rbp
0x180007eab  retn
```
