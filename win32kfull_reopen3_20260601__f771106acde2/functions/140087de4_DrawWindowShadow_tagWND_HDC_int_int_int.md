# DrawWindowShadow(tagWND *,HDC__ *,int,int,int *)

- ea: `0x140087de4`
- end: `0x14008811d`
- name: `?DrawWindowShadow@@YAHPEAUtagWND@@PEAUHDC__@@HHPEAH@Z`
- size: `825`
- prototype: `__int64 __usercall@<rax>(struct tagWND *this@<rcx>, HDC@<rdx>, int@<r8d>, int@<r9d>, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140087a04`

## callees

- `0x14002953c`
- `0x140087de4`
- `0x14008826c`
- `0x140088bd4`
- `0x1400e2cb0`
- `0x14029a57c`
- `0x140342fa0`

## import_xrefs

- `win32kbase!GreGetStockObject` at `0x140087fe6`
- `win32kbase!GreGetStockObject` at `0x1400880ed`
- `win32kbase!GreGetStockObject` at `0x140087fe6`
- `win32kbase!GreGetStockObject` at `0x1400880ed`
- `win32kbase!GreCreateRectRgn` at `0x140087e3b`
- `win32kbase!GreCreateRectRgn` at `0x140087e54`
- `win32kbase!GreCreateRectRgn` at `0x140087e3b`
- `win32kbase!GreCreateRectRgn` at `0x140087e54`
- `win32kbase!SetRectRgnIndirect` at `0x140087e90`
- `win32kbase!SetRectRgnIndirect` at `0x140087e90`
- `win32kbase!GreSetRectRgn` at `0x14008803d`
- `win32kbase!GreSetRectRgn` at `0x14008803d`
- `win32kbase!GreCombineRgn` at `0x140087ea9`
- `win32kbase!GreCombineRgn` at `0x140087efd`
- `win32kbase!GreCombineRgn` at `0x1400880df`
- `win32kbase!GreCombineRgn` at `0x140087ea9`
- `win32kbase!GreCombineRgn` at `0x140087efd`
- `win32kbase!GreCombineRgn` at `0x1400880df`
- `win32kbase!GreOffsetRgn` at `0x140087ec4`
- `win32kbase!GreOffsetRgn` at `0x140087f1b`
- `win32kbase!GreOffsetRgn` at `0x14008810a`
- `win32kbase!GreOffsetRgn` at `0x140087ec4`
- `win32kbase!GreOffsetRgn` at `0x140087f1b`
- `win32kbase!GreOffsetRgn` at `0x14008810a`
- `win32kbase!GreDeleteObject` at `0x140087f87`
- `win32kbase!GreDeleteObject` at `0x140087f9d`
- `win32kbase!GreDeleteObject` at `0x140087fac`
- `win32kbase!GreDeleteObject` at `0x140087f87`
- `win32kbase!GreDeleteObject` at `0x140087f9d`
- `win32kbase!GreDeleteObject` at `0x140087fac`
- `win32kbase!GreCreateSolidBrush` at `0x140087f5b`
- `win32kbase!GreCreateSolidBrush` at `0x140087f5b`

## pseudocode

```c
__int64 __fastcall DrawWindowShadow(struct tagWND *this, HDC a2, int a3, int a4, int *a5)
{
  unsigned int v7; // r14d
  __int64 RectRgn; // rdi
  __int64 v9; // rax
  HRGN v10; // rsi
  HRGN ExplicitClipRgn; // rbx
  int v12; // eax
  int v13; // ebx
  __int64 v14; // rdx
  HDC v15; // r13
  HBRUSH SolidBrush; // rax
  HBRUSH v17; // r12
  HBRUSH StockObject; // rax
  HRGN v20; // rdx
  HDC v21; // rcx
  int v22; // ecx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int128 v28; // [rsp+48h] [rbp-18h] BYREF

  v7 = 0;
  v28 = *(_OWORD *)(*((_QWORD *)this + 5) + 88LL);
  RectRgn = GreCreateRectRgn(0, 0, 0, 0);
  v9 = GreCreateRectRgn(0, 0, 0, 0);
  v10 = (HRGN)v9;
  if ( RectRgn && v9 )
  {
    ExplicitClipRgn = tagWND::GetExplicitClipRgn(this);
    if ( ExplicitClipRgn )
    {
      SetRectRgnIndirect(RectRgn, &v28);
      GreCombineRgn(RectRgn, RectRgn, ExplicitClipRgn, 1);
      GreOffsetRgn(RectRgn, (unsigned int)-(int)v28, (unsigned int)-DWORD1(v28));
      v12 = 0;
    }
    else
    {
      v22 = -(int)v28;
      LODWORD(v28) = 0;
      v23 = HIDWORD(v28) - DWORD1(v28);
      DWORD1(v28) = 0;
      HIDWORD(v28) = v23;
      DWORD2(v28) += v22;
      GreSetRectRgn(RectRgn, 0, 0, DWORD2(v28), v23);
      v12 = 1;
    }
    *a5 = v12;
    if ( PtiCurrent()
      && *((_QWORD *)PtiCurrent() + 61)
      && (*(_DWORD *)(**(_QWORD **)(*((_QWORD *)PtiCurrent() + 61) + 8LL) + 64LL) & 1) != 0
      && (v24 = *((_QWORD *)this + 5), (*(_DWORD *)(v24 + 288) & 0x4000000F) == 0x40000000)
      && (v25 = *(unsigned __int16 *)(v24 + 284), (_WORD)v25 != 96) )
    {
      v7 = GreScaleRgnToDestLogPixel(v25, RectRgn);
      if ( !v7 )
        goto LABEL_15;
    }
    else
    {
      v7 = 1;
    }
    v13 = 5;
    GreCombineRgn(v10, RectRgn, 0, 5);
    v14 = 5;
    if ( a3 )
    {
      GreOffsetRgn(RectRgn, 5, 0);
      v14 = 0;
    }
    GreOffsetRgn(v10, v14, 5);
    if ( !*a5 || a4 )
    {
      v15 = a2;
      while ( v13 > 0 )
      {
        SolidBrush = (HBRUSH)GreCreateSolidBrush(
                               *((unsigned __int8 *)&dword_140351E24 + v13 - 1)
                             | (*((unsigned __int8 *)&dword_140351E24 + v13 - 1) << 16)
                             | _byteswap_ulong(*((unsigned __int8 *)&dword_140351E24 + v13 - 1) << 16));
        v17 = SolidBrush;
        if ( !SolidBrush )
        {
          v7 = 0;
          goto LABEL_15;
        }
        GreFrameRgn(v15, v10, SolidBrush, v13, v13);
        GreDeleteObject(v17);
        --v13;
      }
      StockObject = (HBRUSH)GreGetStockObject(4);
      v20 = (HRGN)RectRgn;
      v21 = v15;
    }
    else
    {
      GreCombineRgn(v10, v10, RectRgn, 4);
      StockObject = (HBRUSH)GreGetStockObject(0);
      v20 = v10;
      v21 = a2;
    }
    GreFillRgn(v21, v20, StockObject);
  }
LABEL_15:
  GreDeleteObject(RectRgn);
  GreDeleteObject(v10);
  return v7;
}

```

## disassembly

```asm
0x140087de4  mov     [rsp-28h+arg_10], rbx
0x140087de9  mov     [rsp-28h+arg_18], rsi
0x140087dee  push    rbp
0x140087def  push    rdi
0x140087df0  push    r12
0x140087df2  push    r13
0x140087df4  push    r14
0x140087df6  mov     rbp, rsp
0x140087df9  sub     rsp, 60h
0x140087dfd  mov     rax, cs:__security_cookie
0x140087e04  xor     rax, rsp
0x140087e07  mov     [rbp+var_8], rax
0x140087e0b  mov     rax, [rbp+arg_20]
0x140087e0f  mov     r12, rdx
0x140087e12  mov     [rbp+var_28], rax
0x140087e16  mov     r13, rcx
0x140087e19  mov     rax, [rcx+28h]
0x140087e1d  xor     edx, edx
0x140087e1f  mov     [rbp+var_2C], r9d
0x140087e23  xor     ecx, ecx
0x140087e25  mov     [rbp+var_30], r8d
0x140087e29  xor     r9d, r9d
0x140087e2c  xor     r8d, r8d
0x140087e2f  xor     r14d, r14d
0x140087e32  movups  xmm0, xmmword ptr [rax+58h]
0x140087e36  movdqu  [rbp+var_18], xmm0
0x140087e3b  call    cs:__imp_GreCreateRectRgn
0x140087e42  nop     dword ptr [rax+rax+00h]
0x140087e47  xor     r9d, r9d
0x140087e4a  xor     r8d, r8d
0x140087e4d  xor     edx, edx
0x140087e4f  xor     ecx, ecx
0x140087e51  mov     rdi, rax
0x140087e54  call    cs:__imp_GreCreateRectRgn
0x140087e5b  nop     dword ptr [rax+rax+00h]
0x140087e60  mov     rsi, rax
0x140087e63  test    rdi, rdi
0x140087e66  jz      loc_140087F9A
0x140087e6c  test    rax, rax
0x140087e6f  jz      loc_140087F9A
0x140087e75  mov     rcx, r13; this
0x140087e78  call    ?GetExplicitClipRgn@tagWND@@QEBAPEAUHRGN__@@XZ; tagWND::GetExplicitClipRgn(void)
0x140087e7d  mov     rbx, rax
0x140087e80  test    rax, rax
0x140087e83  jz      loc_140088002
0x140087e89  lea     rdx, [rbp+var_18]
0x140087e8d  mov     rcx, rdi
0x140087e90  call    cs:__imp_SetRectRgnIndirect
0x140087e97  nop     dword ptr [rax+rax+00h]
0x140087e9c  lea     r9d, [r14+1]
0x140087ea0  mov     r8, rbx
0x140087ea3  mov     rdx, rdi
0x140087ea6  mov     rcx, rdi
0x140087ea9  call    cs:__imp_GreCombineRgn
0x140087eb0  nop     dword ptr [rax+rax+00h]
0x140087eb5  mov     r8d, dword ptr [rbp+var_18+4]
0x140087eb9  mov     rcx, rdi
0x140087ebc  mov     edx, dword ptr [rbp+var_18]
0x140087ebf  neg     r8d
0x140087ec2  neg     edx
0x140087ec4  call    cs:__imp_GreOffsetRgn
0x140087ecb  nop     dword ptr [rax+rax+00h]
0x140087ed0  xor     eax, eax
0x140087ed2  mov     rcx, [rbp+var_28]
0x140087ed6  mov     [rcx], eax
0x140087ed8  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140087edd  test    rax, rax
0x140087ee0  jnz     loc_140088053
0x140087ee6  mov     r14d, 1
0x140087eec  mov     ebx, 5
0x140087ef1  xor     r8d, r8d
0x140087ef4  mov     r9d, ebx
0x140087ef7  mov     rdx, rdi
0x140087efa  mov     rcx, rsi
0x140087efd  call    cs:__imp_GreCombineRgn
0x140087f04  nop     dword ptr [rax+rax+00h]
0x140087f09  cmp     [rbp+var_30], 0
0x140087f0d  mov     edx, ebx
0x140087f0f  jnz     loc_140088104
0x140087f15  mov     r8d, ebx
0x140087f18  mov     rcx, rsi
0x140087f1b  call    cs:__imp_GreOffsetRgn
0x140087f22  nop     dword ptr [rax+rax+00h]
0x140087f27  mov     rax, [rbp+var_28]
0x140087f2b  cmp     dword ptr [rax], 0
0x140087f2e  jnz     loc_1400880C6
0x140087f34  mov     r13, r12
0x140087f37  test    ebx, ebx
0x140087f39  jle     loc_140087FE1
0x140087f3f  movsxd  rax, ebx
0x140087f42  lea     rcx, dword_140351E24
0x140087f49  movzx   edx, byte ptr [rax+rcx-1]
0x140087f4e  mov     eax, edx
0x140087f50  shl     eax, 10h
0x140087f53  mov     ecx, eax
0x140087f55  bswap   ecx
0x140087f57  or      ecx, eax
0x140087f59  or      ecx, edx
0x140087f5b  call    cs:__imp_GreCreateSolidBrush
0x140087f62  nop     dword ptr [rax+rax+00h]
0x140087f67  mov     r12, rax
0x140087f6a  test    rax, rax
0x140087f6d  jz      short loc_140087F97
0x140087f6f  mov     r9d, ebx
0x140087f72  mov     [rsp+60h+var_40], ebx; int
0x140087f76  mov     r8, rax
0x140087f79  mov     rdx, rsi
0x140087f7c  mov     rcx, r13; HDC
0x140087f7f  call    GreFrameRgn
0x140087f84  mov     rcx, r12
0x140087f87  call    cs:__imp_GreDeleteObject
0x140087f8e  nop     dword ptr [rax+rax+00h]
0x140087f93  dec     ebx
0x140087f95  jmp     short loc_140087F37
0x140087f97  xor     r14d, r14d
0x140087f9a  mov     rcx, rdi
0x140087f9d  call    cs:__imp_GreDeleteObject
0x140087fa4  nop     dword ptr [rax+rax+00h]
0x140087fa9  mov     rcx, rsi
0x140087fac  call    cs:__imp_GreDeleteObject
0x140087fb3  nop     dword ptr [rax+rax+00h]
0x140087fb8  mov     eax, r14d
0x140087fbb  mov     rcx, [rbp+var_8]
0x140087fbf  xor     rcx, rsp; StackCookie
0x140087fc2  call    __security_check_cookie
0x140087fc7  lea     r11, [rsp+60h+var_s0]
0x140087fcc  mov     rbx, [r11+40h]
0x140087fd0  mov     rsi, [r11+48h]
0x140087fd4  mov     rsp, r11
0x140087fd7  pop     r14
0x140087fd9  pop     r13
0x140087fdb  pop     r12
0x140087fdd  pop     rdi
0x140087fde  pop     rbp
0x140087fdf  retn
0x140087fe1  mov     ecx, 4
0x140087fe6  call    cs:__imp_GreGetStockObject
0x140087fed  nop     dword ptr [rax+rax+00h]
0x140087ff2  mov     rdx, rdi
0x140087ff5  mov     rcx, r13; HDC
0x140087ff8  mov     r8, rax
0x140087ffb  call    GreFillRgn
0x140088000  jmp     short loc_140087F9A
0x140088002  mov     eax, dword ptr [rbp+var_18]
0x140088005  mov     ecx, eax
0x140088007  mov     r8d, dword ptr [rbp+var_18+4]
0x14008800b  neg     ecx
0x14008800d  mov     r9d, dword ptr [rbp+var_18+8]
0x140088011  add     eax, ecx
0x140088013  mov     edx, r8d
0x140088016  mov     dword ptr [rbp+var_18], eax
0x140088019  mov     eax, dword ptr [rbp+var_18+0Ch]
0x14008801c  neg     edx
0x14008801e  add     r8d, edx
0x140088021  add     eax, edx
0x140088023  add     r9d, ecx
0x140088026  mov     dword ptr [rbp+var_18+4], r8d
0x14008802a  xor     edx, edx
0x14008802c  mov     dword ptr [rbp+var_18+0Ch], eax
0x14008802f  xor     r8d, r8d
0x140088032  mov     [rsp+60h+var_40], eax
0x140088036  mov     rcx, rdi
0x140088039  mov     dword ptr [rbp+var_18+8], r9d
0x14008803d  call    cs:__imp_GreSetRectRgn
0x140088044  nop     dword ptr [rax+rax+00h]
0x140088049  mov     eax, 1
0x14008804e  jmp     loc_140087ED2
0x140088053  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140088058  cmp     [rax+1E8h], r14
0x14008805f  jz      loc_140087EE6
0x140088065  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14008806a  mov     rcx, [rax+1E8h]
0x140088071  mov     rax, [rcx+8]
0x140088075  mov     rcx, [rax]
0x140088078  mov     eax, [rcx+40h]
0x14008807b  test    al, 1
0x14008807d  jz      loc_140087EE6
0x140088083  mov     rcx, [r13+28h]
0x140088087  mov     eax, [rcx+120h]
0x14008808d  and     eax, 4000000Fh
0x140088092  cmp     eax, 40000000h
0x140088097  jnz     loc_140087EE6
0x14008809d  movzx   ecx, word ptr [rcx+11Ch]
0x1400880a4  cmp     cx, 60h ; '`'
0x1400880a8  jz      loc_140087EE6
0x1400880ae  mov     rdx, rdi
0x1400880b1  call    GreScaleRgnToDestLogPixel
0x1400880b6  mov     r14d, eax
0x1400880b9  test    eax, eax
0x1400880bb  jz      loc_140087F9A
0x1400880c1  jmp     loc_140087EEC
0x1400880c6  cmp     [rbp+var_2C], 0
0x1400880ca  jnz     loc_140087F34
0x1400880d0  mov     r9d, 4
0x1400880d6  mov     r8, rdi
0x1400880d9  mov     rdx, rsi
0x1400880dc  mov     rcx, rsi
0x1400880df  call    cs:__imp_GreCombineRgn
0x1400880e6  nop     dword ptr [rax+rax+00h]
0x1400880eb  xor     ecx, ecx
0x1400880ed  call    cs:__imp_GreGetStockObject
0x1400880f4  nop     dword ptr [rax+rax+00h]
0x1400880f9  mov     rdx, rsi
0x1400880fc  mov     rcx, r12
0x1400880ff  jmp     loc_140087FF8
0x140088104  xor     r8d, r8d
0x140088107  mov     rcx, rdi
0x14008810a  call    cs:__imp_GreOffsetRgn
0x140088111  nop     dword ptr [rax+rax+00h]
0x140088116  xor     edx, edx
0x140088118  jmp     loc_140087F15
```
