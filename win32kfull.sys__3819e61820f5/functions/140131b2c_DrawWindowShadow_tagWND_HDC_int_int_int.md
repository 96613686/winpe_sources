# DrawWindowShadow(tagWND *,HDC__ *,int,int,int *)

- ea: `0x140131b2c`
- end: `0x140131e65`
- name: `?DrawWindowShadow@@YAHPEAUtagWND@@PEAUHDC__@@HHPEAH@Z`
- size: `825`
- prototype: `__int64 __usercall@<rax>(struct tagWND *this@<rcx>, HDC@<rdx>, int@<r8d>, int@<r9d>, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14013174c`

## callees

- `0x14005a4ac`
- `0x1400bcaa0`
- `0x140131b2c`
- `0x140135194`
- `0x140135b04`
- `0x1402980ac`
- `0x140341ff0`

## import_xrefs

- `win32kbase!GreGetStockObject` at `0x140131d2e`
- `win32kbase!GreGetStockObject` at `0x140131e35`
- `win32kbase!GreGetStockObject` at `0x140131d2e`
- `win32kbase!GreGetStockObject` at `0x140131e35`
- `win32kbase!GreCreateRectRgn` at `0x140131b83`
- `win32kbase!GreCreateRectRgn` at `0x140131b9c`
- `win32kbase!GreCreateRectRgn` at `0x140131b83`
- `win32kbase!GreCreateRectRgn` at `0x140131b9c`
- `win32kbase!SetRectRgnIndirect` at `0x140131bd8`
- `win32kbase!SetRectRgnIndirect` at `0x140131bd8`
- `win32kbase!GreSetRectRgn` at `0x140131d85`
- `win32kbase!GreSetRectRgn` at `0x140131d85`
- `win32kbase!GreCombineRgn` at `0x140131bf1`
- `win32kbase!GreCombineRgn` at `0x140131c45`
- `win32kbase!GreCombineRgn` at `0x140131e27`
- `win32kbase!GreCombineRgn` at `0x140131bf1`
- `win32kbase!GreCombineRgn` at `0x140131c45`
- `win32kbase!GreCombineRgn` at `0x140131e27`
- `win32kbase!GreOffsetRgn` at `0x140131c0c`
- `win32kbase!GreOffsetRgn` at `0x140131c63`
- `win32kbase!GreOffsetRgn` at `0x140131e52`
- `win32kbase!GreOffsetRgn` at `0x140131c0c`
- `win32kbase!GreOffsetRgn` at `0x140131c63`
- `win32kbase!GreOffsetRgn` at `0x140131e52`
- `win32kbase!GreDeleteObject` at `0x140131ccf`
- `win32kbase!GreDeleteObject` at `0x140131ce5`
- `win32kbase!GreDeleteObject` at `0x140131cf4`
- `win32kbase!GreDeleteObject` at `0x140131ccf`
- `win32kbase!GreDeleteObject` at `0x140131ce5`
- `win32kbase!GreDeleteObject` at `0x140131cf4`
- `win32kbase!GreCreateSolidBrush` at `0x140131ca3`
- `win32kbase!GreCreateSolidBrush` at `0x140131ca3`

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
                               *((unsigned __int8 *)&qword_140353960 + v13 - 1)
                             | (*((unsigned __int8 *)&qword_140353960 + v13 - 1) << 16)
                             | _byteswap_ulong(*((unsigned __int8 *)&qword_140353960 + v13 - 1) << 16));
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
0x140131b2c  mov     [rsp-28h+arg_10], rbx
0x140131b31  mov     [rsp-28h+arg_18], rsi
0x140131b36  push    rbp
0x140131b37  push    rdi
0x140131b38  push    r12
0x140131b3a  push    r13
0x140131b3c  push    r14
0x140131b3e  mov     rbp, rsp
0x140131b41  sub     rsp, 60h
0x140131b45  mov     rax, cs:__security_cookie
0x140131b4c  xor     rax, rsp
0x140131b4f  mov     [rbp+var_8], rax
0x140131b53  mov     rax, [rbp+arg_20]
0x140131b57  mov     r12, rdx
0x140131b5a  mov     [rbp+var_28], rax
0x140131b5e  mov     r13, rcx
0x140131b61  mov     rax, [rcx+28h]
0x140131b65  xor     edx, edx
0x140131b67  mov     [rbp+var_2C], r9d
0x140131b6b  xor     ecx, ecx
0x140131b6d  mov     [rbp+var_30], r8d
0x140131b71  xor     r9d, r9d
0x140131b74  xor     r8d, r8d
0x140131b77  xor     r14d, r14d
0x140131b7a  movups  xmm0, xmmword ptr [rax+58h]
0x140131b7e  movdqu  [rbp+var_18], xmm0
0x140131b83  call    cs:__imp_GreCreateRectRgn
0x140131b8a  nop     dword ptr [rax+rax+00h]
0x140131b8f  xor     r9d, r9d
0x140131b92  xor     r8d, r8d
0x140131b95  xor     edx, edx
0x140131b97  xor     ecx, ecx
0x140131b99  mov     rdi, rax
0x140131b9c  call    cs:__imp_GreCreateRectRgn
0x140131ba3  nop     dword ptr [rax+rax+00h]
0x140131ba8  mov     rsi, rax
0x140131bab  test    rdi, rdi
0x140131bae  jz      loc_140131CE2
0x140131bb4  test    rax, rax
0x140131bb7  jz      loc_140131CE2
0x140131bbd  mov     rcx, r13; this
0x140131bc0  call    ?GetExplicitClipRgn@tagWND@@QEBAPEAUHRGN__@@XZ; tagWND::GetExplicitClipRgn(void)
0x140131bc5  mov     rbx, rax
0x140131bc8  test    rax, rax
0x140131bcb  jz      loc_140131D4A
0x140131bd1  lea     rdx, [rbp+var_18]
0x140131bd5  mov     rcx, rdi
0x140131bd8  call    cs:__imp_SetRectRgnIndirect
0x140131bdf  nop     dword ptr [rax+rax+00h]
0x140131be4  lea     r9d, [r14+1]
0x140131be8  mov     r8, rbx
0x140131beb  mov     rdx, rdi
0x140131bee  mov     rcx, rdi
0x140131bf1  call    cs:__imp_GreCombineRgn
0x140131bf8  nop     dword ptr [rax+rax+00h]
0x140131bfd  mov     r8d, dword ptr [rbp+var_18+4]
0x140131c01  mov     rcx, rdi
0x140131c04  mov     edx, dword ptr [rbp+var_18]
0x140131c07  neg     r8d
0x140131c0a  neg     edx
0x140131c0c  call    cs:__imp_GreOffsetRgn
0x140131c13  nop     dword ptr [rax+rax+00h]
0x140131c18  xor     eax, eax
0x140131c1a  mov     rcx, [rbp+var_28]
0x140131c1e  mov     [rcx], eax
0x140131c20  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140131c25  test    rax, rax
0x140131c28  jnz     loc_140131D9B
0x140131c2e  mov     r14d, 1
0x140131c34  mov     ebx, 5
0x140131c39  xor     r8d, r8d
0x140131c3c  mov     r9d, ebx
0x140131c3f  mov     rdx, rdi
0x140131c42  mov     rcx, rsi
0x140131c45  call    cs:__imp_GreCombineRgn
0x140131c4c  nop     dword ptr [rax+rax+00h]
0x140131c51  cmp     [rbp+var_30], 0
0x140131c55  mov     edx, ebx
0x140131c57  jnz     loc_140131E4C
0x140131c5d  mov     r8d, ebx
0x140131c60  mov     rcx, rsi
0x140131c63  call    cs:__imp_GreOffsetRgn
0x140131c6a  nop     dword ptr [rax+rax+00h]
0x140131c6f  mov     rax, [rbp+var_28]
0x140131c73  cmp     dword ptr [rax], 0
0x140131c76  jnz     loc_140131E0E
0x140131c7c  mov     r13, r12
0x140131c7f  test    ebx, ebx
0x140131c81  jle     loc_140131D29
0x140131c87  movsxd  rax, ebx
0x140131c8a  lea     rcx, qword_140353960
0x140131c91  movzx   edx, byte ptr [rax+rcx-1]
0x140131c96  mov     eax, edx
0x140131c98  shl     eax, 10h
0x140131c9b  mov     ecx, eax
0x140131c9d  bswap   ecx
0x140131c9f  or      ecx, eax
0x140131ca1  or      ecx, edx
0x140131ca3  call    cs:__imp_GreCreateSolidBrush
0x140131caa  nop     dword ptr [rax+rax+00h]
0x140131caf  mov     r12, rax
0x140131cb2  test    rax, rax
0x140131cb5  jz      short loc_140131CDF
0x140131cb7  mov     r9d, ebx
0x140131cba  mov     [rsp+60h+var_40], ebx; int
0x140131cbe  mov     r8, rax
0x140131cc1  mov     rdx, rsi
0x140131cc4  mov     rcx, r13; HDC
0x140131cc7  call    GreFrameRgn
0x140131ccc  mov     rcx, r12
0x140131ccf  call    cs:__imp_GreDeleteObject
0x140131cd6  nop     dword ptr [rax+rax+00h]
0x140131cdb  dec     ebx
0x140131cdd  jmp     short loc_140131C7F
0x140131cdf  xor     r14d, r14d
0x140131ce2  mov     rcx, rdi
0x140131ce5  call    cs:__imp_GreDeleteObject
0x140131cec  nop     dword ptr [rax+rax+00h]
0x140131cf1  mov     rcx, rsi
0x140131cf4  call    cs:__imp_GreDeleteObject
0x140131cfb  nop     dword ptr [rax+rax+00h]
0x140131d00  mov     eax, r14d
0x140131d03  mov     rcx, [rbp+var_8]
0x140131d07  xor     rcx, rsp; StackCookie
0x140131d0a  call    __security_check_cookie
0x140131d0f  lea     r11, [rsp+60h+var_s0]
0x140131d14  mov     rbx, [r11+40h]
0x140131d18  mov     rsi, [r11+48h]
0x140131d1c  mov     rsp, r11
0x140131d1f  pop     r14
0x140131d21  pop     r13
0x140131d23  pop     r12
0x140131d25  pop     rdi
0x140131d26  pop     rbp
0x140131d27  retn
0x140131d29  mov     ecx, 4
0x140131d2e  call    cs:__imp_GreGetStockObject
0x140131d35  nop     dword ptr [rax+rax+00h]
0x140131d3a  mov     rdx, rdi
0x140131d3d  mov     rcx, r13; HDC
0x140131d40  mov     r8, rax
0x140131d43  call    GreFillRgn
0x140131d48  jmp     short loc_140131CE2
0x140131d4a  mov     eax, dword ptr [rbp+var_18]
0x140131d4d  mov     ecx, eax
0x140131d4f  mov     r8d, dword ptr [rbp+var_18+4]
0x140131d53  neg     ecx
0x140131d55  mov     r9d, dword ptr [rbp+var_18+8]
0x140131d59  add     eax, ecx
0x140131d5b  mov     edx, r8d
0x140131d5e  mov     dword ptr [rbp+var_18], eax
0x140131d61  mov     eax, dword ptr [rbp+var_18+0Ch]
0x140131d64  neg     edx
0x140131d66  add     r8d, edx
0x140131d69  add     eax, edx
0x140131d6b  add     r9d, ecx
0x140131d6e  mov     dword ptr [rbp+var_18+4], r8d
0x140131d72  xor     edx, edx
0x140131d74  mov     dword ptr [rbp+var_18+0Ch], eax
0x140131d77  xor     r8d, r8d
0x140131d7a  mov     [rsp+60h+var_40], eax
0x140131d7e  mov     rcx, rdi
0x140131d81  mov     dword ptr [rbp+var_18+8], r9d
0x140131d85  call    cs:__imp_GreSetRectRgn
0x140131d8c  nop     dword ptr [rax+rax+00h]
0x140131d91  mov     eax, 1
0x140131d96  jmp     loc_140131C1A
0x140131d9b  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140131da0  cmp     [rax+1E8h], r14
0x140131da7  jz      loc_140131C2E
0x140131dad  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140131db2  mov     rcx, [rax+1E8h]
0x140131db9  mov     rax, [rcx+8]
0x140131dbd  mov     rcx, [rax]
0x140131dc0  mov     eax, [rcx+40h]
0x140131dc3  test    al, 1
0x140131dc5  jz      loc_140131C2E
0x140131dcb  mov     rcx, [r13+28h]
0x140131dcf  mov     eax, [rcx+120h]
0x140131dd5  and     eax, 4000000Fh
0x140131dda  cmp     eax, 40000000h
0x140131ddf  jnz     loc_140131C2E
0x140131de5  movzx   ecx, word ptr [rcx+11Ch]
0x140131dec  cmp     cx, 60h ; '`'
0x140131df0  jz      loc_140131C2E
0x140131df6  mov     rdx, rdi
0x140131df9  call    GreScaleRgnToDestLogPixel
0x140131dfe  mov     r14d, eax
0x140131e01  test    eax, eax
0x140131e03  jz      loc_140131CE2
0x140131e09  jmp     loc_140131C34
0x140131e0e  cmp     [rbp+var_2C], 0
0x140131e12  jnz     loc_140131C7C
0x140131e18  mov     r9d, 4
0x140131e1e  mov     r8, rdi
0x140131e21  mov     rdx, rsi
0x140131e24  mov     rcx, rsi
0x140131e27  call    cs:__imp_GreCombineRgn
0x140131e2e  nop     dword ptr [rax+rax+00h]
0x140131e33  xor     ecx, ecx
0x140131e35  call    cs:__imp_GreGetStockObject
0x140131e3c  nop     dword ptr [rax+rax+00h]
0x140131e41  mov     rdx, rsi
0x140131e44  mov     rcx, r12
0x140131e47  jmp     loc_140131D40
0x140131e4c  xor     r8d, r8d
0x140131e4f  mov     rcx, rdi
0x140131e52  call    cs:__imp_GreOffsetRgn
0x140131e59  nop     dword ptr [rax+rax+00h]
0x140131e5e  xor     edx, edx
0x140131e60  jmp     loc_140131C5D
```
