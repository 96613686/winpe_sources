# CInfraConnectPage::ValidateSecurity(int)

- ea: `0x180022dd8`
- end: `0x180022f43`
- name: `?ValidateSecurity@CInfraConnectPage@@AEAAHH@Z`
- size: `363`
- prototype: `__int64 __fastcall(CInfraConnectPage *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021c98`

## callees

- `0x180020800`
- `0x180022738`
- `0x180022dd8`

## import_xrefs

- `wlanapi!ConvertPassPhraseKeyStringToBuffer` at `0x180022e73`
- `wlanapi!ConvertPassPhraseKeyStringToBuffer` at `0x180022e73`

## pseudocode

```c
__int64 __fastcall CInfraConnectPage::ValidateSecurity(CInfraConnectPage *this)
{
  __int64 v3; // r8
  __int64 v4; // r9
  int v5; // eax
  char *v6; // rcx
  unsigned int v7; // esi
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned int v10; // eax
  bool v11; // sf

  if ( *((_BYTE *)this + 1500) )
    return 1;
  v3 = *((unsigned int *)this + 373);
  v4 = *((unsigned int *)this + 374);
  if ( __PAIR64__(v4, v3) != 0x10100000001LL )
  {
    if ( (unsigned int)v3 > 9 || (v5 = 660, !_bittest(&v5, v3)) )
    {
      v8 = 0;
      goto LABEL_16;
    }
  }
  v6 = (char *)this + 466;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&v6[2 * v9] );
    v10 = ConvertPassPhraseKeyStringToBuffer(v6, v9, v3, v4);
    v8 = 0;
    if ( v10 != 234 )
    {
      v7 = 0;
      if ( v10 != 11 )
        v8 = v10;
      v11 = (int)v8 < 0;
      if ( (int)v8 <= 0 )
        goto LABEL_18;
      goto LABEL_14;
    }
LABEL_16:
    v7 = 1;
    goto LABEL_17;
  }
  v7 = 0;
  LOWORD(v8) = 87;
LABEL_14:
  v8 = (unsigned __int16)v8 | 0x80070000;
LABEL_17:
  v11 = (int)v8 < 0;
LABEL_18:
  if ( v11
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145)
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 32, WPP_1064fdabddc73196039d87943bb008b3_Traceguids, v8);
  }
  if ( !v7 )
  {
    if ( *(_QWORD *)((char *)this + 1492) == 0x10100000001LL || *((_DWORD *)this + 373) == 2 )
      CTooltip::ShowErrBalloon((CInfraConnectPage *)((char *)this + 376), 0x2840u, 0x2904u, 0x27EDu);
    else
      CTooltip::ShowErrBalloon((CInfraConnectPage *)((char *)this + 376), 0x2840u, 0x27E8u, 0x27E7u);
  }
  return v7;
}

```

## disassembly

```asm
0x180022dd8  mov     [rsp+arg_10], rbp
0x180022ddd  mov     [rsp+arg_18], rsi
0x180022de2  mov     [rsp+arg_8], edx
0x180022de6  push    rdi
0x180022de7  sub     rsp, 40h
0x180022deb  xor     ebp, ebp
0x180022ded  mov     rdi, rcx
0x180022df0  cmp     [rcx+5DCh], bpl
0x180022df7  jz      short loc_180022E01
0x180022df9  lea     eax, [rbp+1]
0x180022dfc  jmp     loc_180022F33
0x180022e01  mov     r8d, [rcx+5D4h]
0x180022e08  mov     r9d, [rcx+5D8h]
0x180022e0f  mov     [rsp+48h+arg_0], ebp
0x180022e13  mov     [rsp+48h+arg_8], ebp
0x180022e17  cmp     r8d, 1
0x180022e1b  jnz     short loc_180022E26
0x180022e1d  cmp     r9d, 101h
0x180022e24  jz      short loc_180022E37
0x180022e26  cmp     r8d, 9
0x180022e2a  ja      short loc_180022E9E
0x180022e2c  mov     eax, 294h
0x180022e31  bt      eax, r8d
0x180022e35  jnb     short loc_180022E9E
0x180022e37  add     rcx, 1D2h
0x180022e3e  jnz     short loc_180022E48
0x180022e40  mov     esi, ebp
0x180022e42  lea     r9d, [rcx+57h]
0x180022e46  jmp     short loc_180022E91
0x180022e48  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180022e4c  inc     rdx
0x180022e4f  cmp     [rcx+rdx*2], bp
0x180022e53  jnz     short loc_180022E4C
0x180022e55  mov     [rsp+48h+var_10], rbp
0x180022e5a  lea     rax, [rsp+48h+arg_8]
0x180022e5f  mov     [rsp+48h+var_18], rax
0x180022e64  lea     rax, [rsp+48h+arg_0]
0x180022e69  mov     [rsp+48h+var_20], rax
0x180022e6e  mov     [rsp+48h+var_28], rbp
0x180022e73  call    cs:__imp_ConvertPassPhraseKeyStringToBuffer
0x180022e79  mov     r9d, ebp
0x180022e7c  cmp     eax, 0EAh
0x180022e81  jz      short loc_180022EA1
0x180022e83  cmp     eax, 0Bh
0x180022e86  mov     esi, ebp
0x180022e88  cmovnz  r9d, eax
0x180022e8c  test    r9d, r9d
0x180022e8f  jle     short loc_180022EA9
0x180022e91  movzx   r9d, r9w
0x180022e95  or      r9d, 80070000h
0x180022e9c  jmp     short loc_180022EA6
0x180022e9e  mov     r9d, ebp
0x180022ea1  mov     esi, 1
0x180022ea6  test    r9d, r9d
0x180022ea9  jns     short loc_180022EE8
0x180022eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180022eb2  lea     rax, WPP_GLOBAL_Control
0x180022eb9  cmp     rcx, rax
0x180022ebc  jz      short loc_180022EE8
0x180022ebe  cmp     byte ptr [rcx+91h], 1
0x180022ec5  jb      short loc_180022EE8
0x180022ec7  test    byte ptr [rcx+94h], 1
0x180022ece  jz      short loc_180022EE8
0x180022ed0  mov     rcx, [rcx+88h]
0x180022ed7  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x180022ede  mov     edx, 20h ; ' '
0x180022ee3  call    WPP_SF_d
0x180022ee8  test    esi, esi
0x180022eea  jnz     short loc_180022F31
0x180022eec  mov     eax, [rdi+5D4h]
0x180022ef2  cmp     eax, 1
0x180022ef5  jnz     short loc_180022F03
0x180022ef7  cmp     dword ptr [rdi+5D8h], 101h
0x180022f01  jz      short loc_180022F14
0x180022f03  cmp     eax, 2
0x180022f06  jz      short loc_180022F14
0x180022f08  mov     r9d, 27E7h
0x180022f0e  lea     r8d, [r9+1]
0x180022f12  jmp     short loc_180022F20
0x180022f14  mov     r9d, 27EDh; unsigned int
0x180022f1a  mov     r8d, 2904h; unsigned int
0x180022f20  mov     edx, 2840h; unsigned int
0x180022f25  lea     rcx, [rdi+178h]; this
0x180022f2c  call    ?ShowErrBalloon@CTooltip@@QEAAXIIIZZ; CTooltip::ShowErrBalloon(uint,uint,uint,...)
0x180022f31  mov     eax, esi
0x180022f33  mov     rbp, [rsp+48h+arg_10]
0x180022f38  mov     rsi, [rsp+48h+arg_18]
0x180022f3d  add     rsp, 40h
0x180022f41  pop     rdi
0x180022f42  retn
```
