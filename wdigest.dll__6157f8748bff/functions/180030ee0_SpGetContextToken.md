# SpGetContextToken

- ea: `0x180030ee0`
- end: `0x180031024`
- name: `SpGetContextToken`
- size: `324`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180011fec`
- `0x1800185b8`
- `0x1800192a8`
- `0x18002c498`
- `0x18002c6dc`
- `0x180030ee0`

## pseudocode

```c
__int64 __fastcall SpGetContextToken(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  PVOID *v6; // rcx
  _QWORD *v7; // rbx
  __int64 v8; // r9
  unsigned int v9; // eax
  HLOCAL hMem; // [rsp+50h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, a1);
  hMem = 0;
  v4 = UserCtxtHandlerHandleToContext(a1, 0, 0, &hMem);
  v5 = v4;
  if ( v4 >= 0 )
    goto LABEL_8;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids,
      (unsigned int)v4);
LABEL_8:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = hMem;
  if ( hMem )
  {
    v8 = *((_QWORD *)hMem + 9);
    if ( v8 )
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
        WPP_SF_q(v6[2], 71, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v8);
      *a2 = v7[9];
      goto LABEL_18;
    }
  }
  v5 = -1073741816;
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
  {
    WPP_SF_(v6[2], 72, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
LABEL_18:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    v9 = UserCtxtHandlerRelease(v7);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v5 = v9;
  }
  if ( v6 != &WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 )
    WPP_SF_d(v6[2], 73, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180030ee0  mov     [rsp+arg_0], rbx
0x180030ee5  mov     [rsp+arg_8], rbp
0x180030eea  push    rsi
0x180030eeb  push    rdi
0x180030eec  push    r14
0x180030eee  sub     rsp, 20h
0x180030ef2  mov     rsi, rdx
0x180030ef5  mov     rbx, rcx
0x180030ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x180030eff  lea     rbp, WPP_GLOBAL_Control
0x180030f06  lea     r14, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030f0d  cmp     rcx, rbp
0x180030f10  jz      short loc_180030F2C
0x180030f12  test    byte ptr [rcx+1Ch], 80h
0x180030f16  jz      short loc_180030F2C
0x180030f18  mov     rcx, [rcx+10h]
0x180030f1c  mov     edx, 45h ; 'E'
0x180030f21  mov     r9, rbx
0x180030f24  mov     r8, r14
0x180030f27  call    WPP_SF_q
0x180030f2c  lea     r9, [rsp+38h+hMem]
0x180030f31  mov     [rsp+38h+hMem], 0
0x180030f3a  xor     r8d, r8d
0x180030f3d  xor     edx, edx
0x180030f3f  mov     rcx, rbx
0x180030f42  call    UserCtxtHandlerHandleToContext
0x180030f47  mov     edi, eax
0x180030f49  test    eax, eax
0x180030f4b  jns     short loc_180030F73
0x180030f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030f54  cmp     rcx, rbp
0x180030f57  jz      short loc_180030F7A
0x180030f59  test    byte ptr [rcx+1Ch], 1
0x180030f5d  jz      short loc_180030F7A
0x180030f5f  mov     rcx, [rcx+10h]
0x180030f63  mov     edx, 46h ; 'F'
0x180030f68  mov     r9d, eax
0x180030f6b  mov     r8, r14
0x180030f6e  call    WPP_SF_d
0x180030f73  mov     rcx, cs:WPP_GLOBAL_Control
0x180030f7a  mov     rbx, [rsp+38h+hMem]
0x180030f7f  test    rbx, rbx
0x180030f82  jz      short loc_180030FB2
0x180030f84  mov     r9, [rbx+48h]
0x180030f88  test    r9, r9
0x180030f8b  jz      short loc_180030FB2
0x180030f8d  cmp     rcx, rbp
0x180030f90  jz      short loc_180030FA9
0x180030f92  test    byte ptr [rcx+1Ch], 4
0x180030f96  jz      short loc_180030FA9
0x180030f98  mov     rcx, [rcx+10h]
0x180030f9c  mov     edx, 47h ; 'G'
0x180030fa1  mov     r8, r14
0x180030fa4  call    WPP_SF_q
0x180030fa9  mov     rax, [rbx+48h]
0x180030fad  mov     [rsi], rax
0x180030fb0  jmp     short loc_180030FD3
0x180030fb2  mov     edi, 0C0000008h
0x180030fb7  cmp     rcx, rbp
0x180030fba  jz      short loc_180030FDA
0x180030fbc  test    byte ptr [rcx+1Ch], 1
0x180030fc0  jz      short loc_180030FDA
0x180030fc2  mov     rcx, [rcx+10h]
0x180030fc6  mov     edx, 48h ; 'H'
0x180030fcb  mov     r8, r14
0x180030fce  call    WPP_SF_
0x180030fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180030fda  test    rbx, rbx
0x180030fdd  jz      short loc_180030FF0
0x180030fdf  mov     rcx, rbx; hMem
0x180030fe2  call    UserCtxtHandlerRelease
0x180030fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x180030fee  mov     edi, eax
0x180030ff0  cmp     rcx, rbp
0x180030ff3  jz      short loc_18003100F
0x180030ff5  test    byte ptr [rcx+1Ch], 80h
0x180030ff9  jz      short loc_18003100F
0x180030ffb  mov     rcx, [rcx+10h]
0x180030fff  mov     edx, 49h ; 'I'
0x180031004  mov     r9d, edi
0x180031007  mov     r8, r14
0x18003100a  call    WPP_SF_d
0x18003100f  mov     rbx, [rsp+38h+arg_0]
0x180031014  mov     eax, edi
0x180031016  mov     rbp, [rsp+38h+arg_8]
0x18003101b  add     rsp, 20h
0x18003101f  pop     r14
0x180031021  pop     rdi
0x180031022  pop     rsi
0x180031023  retn
```
