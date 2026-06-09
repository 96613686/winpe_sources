# CheckTrust(ushort const *,void * &)

- ea: `0x180008d98`
- end: `0x180008ebb`
- name: `?CheckTrust@@YAJPEBGAEAPEAX@Z`
- size: `291`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180007854`
- `0x180007938`
- `0x180009ac8`

## callees

- `0x180008058`
- `0x180008d98`
- `0x18000a616`
- `0x18000a640`

## import_xrefs

- `WINTRUST!WinVerifyTrust` at `0x180008e37`
- `WINTRUST!WinVerifyTrust` at `0x180008e37`

## pseudocode

```c
__int64 __fastcall CheckTrust(const unsigned __int16 *a1, void **a2)
{
  LONG v4; // eax
  unsigned int v5; // ebx
  _QWORD v7[2]; // [rsp+20h] [rbp-49h] BYREF
  __int128 v8; // [rsp+30h] [rbp-39h]
  _DWORD pWVTData[10]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD *v10; // [rsp+68h] [rbp-1h]
  int v11; // [rsp+70h] [rbp+7h]
  void *v12; // [rsp+78h] [rbp+Fh]
  int v13; // [rsp+88h] [rbp+1Fh]
  GUID pgActionID; // [rsp+A0h] [rbp+37h] BYREF

  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  memset_0(pWVTData, 0, 0x58u);
  pWVTData[0] = 88;
  v10 = v7;
  pWVTData[6] = 2;
  v13 = 4160;
  pWVTData[8] = 1;
  v8 = 0;
  v11 = 1;
  v7[0] = 32;
  v7[1] = a1;
  v4 = WinVerifyTrust(0, &pgActionID, pWVTData);
  *a2 = v12;
  if ( v4 )
  {
    v5 = (unsigned __int16)v4 | (((v4 >> 16) & 0x1FFF) << 16) | 0x80000000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_cb0f6c3d13033bcf7b6cbf92e57c650f_Traceguids,
        (unsigned int)v4);
  }
  else
  {
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180008d98  mov     [rsp-8+arg_0], rbx
0x180008d9d  mov     [rsp-8+arg_10], rdi
0x180008da2  push    rbp
0x180008da3  lea     rbp, [rsp-57h]
0x180008da8  sub     rsp, 0C0h
0x180008daf  mov     rax, cs:__security_cookie
0x180008db6  xor     rax, rsp
0x180008db9  mov     [rbp+57h+var_10], rax
0x180008dbd  mov     rdi, rdx
0x180008dc0  mov     [rbp+57h+pgActionID.Data1], 0AAC56Bh
0x180008dc7  xor     edx, edx; Val
0x180008dc9  mov     dword ptr [rbp+57h+pgActionID.Data2], 11D0CD44h
0x180008dd0  mov     rbx, rcx
0x180008dd3  mov     dword ptr [rbp+57h+pgActionID.Data4], 0C000C28Ch
0x180008dda  lea     rcx, [rbp+57h+pWVTData]; void *
0x180008dde  mov     dword ptr [rbp+57h+pgActionID.Data4+4], 0EE95C24Fh
0x180008de5  lea     r8d, [rdx+58h]; Size
0x180008de9  call    memset_0
0x180008dee  lea     rax, [rbp+57h+var_A0]
0x180008df2  mov     [rbp+57h+pWVTData], 58h ; 'X'
0x180008df9  xorps   xmm0, xmm0
0x180008dfc  mov     [rbp+57h+var_58], rax
0x180008e00  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x180008e04  mov     [rbp+57h+var_68], 2
0x180008e0b  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x180008e0f  mov     [rbp+57h+var_38], 1040h
0x180008e16  xor     ecx, ecx; hwnd
0x180008e18  mov     [rbp+57h+var_60], 1
0x180008e1f  movdqu  [rbp+57h+var_90], xmm0
0x180008e24  mov     [rbp+57h+var_50], 1
0x180008e2b  mov     [rbp+57h+var_A0], 20h ; ' '
0x180008e33  mov     [rbp+57h+var_98], rbx
0x180008e37  call    cs:__imp_WinVerifyTrust
0x180008e3d  mov     rcx, [rbp+57h+var_48]
0x180008e41  mov     r9d, eax
0x180008e44  mov     [rdi], rcx
0x180008e47  test    eax, eax
0x180008e49  jnz     short loc_180008E4F
0x180008e4b  xor     ebx, ebx
0x180008e4d  jmp     short loc_180008E98
0x180008e4f  mov     ebx, r9d
0x180008e52  movzx   eax, r9w
0x180008e56  sar     ebx, 10h
0x180008e59  and     ebx, 1FFFh
0x180008e5f  shl     ebx, 10h
0x180008e62  or      ebx, eax
0x180008e64  or      ebx, 80000000h
0x180008e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e71  lea     rax, WPP_GLOBAL_Control
0x180008e78  cmp     rcx, rax
0x180008e7b  jz      short loc_180008E98
0x180008e7d  test    byte ptr [rcx+1Ch], 1
0x180008e81  jz      short loc_180008E98
0x180008e83  mov     rcx, [rcx+10h]
0x180008e87  lea     r8, WPP_cb0f6c3d13033bcf7b6cbf92e57c650f_Traceguids
0x180008e8e  mov     edx, 0Ah
0x180008e93  call    WPP_SF_d
0x180008e98  mov     eax, ebx
0x180008e9a  mov     rcx, [rbp+57h+var_10]
0x180008e9e  xor     rcx, rsp; StackCookie
0x180008ea1  call    __security_check_cookie
0x180008ea6  lea     r11, [rsp+0C0h+var_s0]
0x180008eae  mov     rbx, [r11+10h]
0x180008eb2  mov     rdi, [r11+20h]
0x180008eb6  mov     rsp, r11
0x180008eb9  pop     rbp
0x180008eba  retn
```
