# Tpm20CmdPcrRead(TpmTransport *,uint,ushort,ushort *,void *)

- ea: `0x140006b70`
- end: `0x140006e35`
- name: `?Tpm20CmdPcrRead@@YAJPEAVTpmTransport@@IGPEAGPEAX@Z`
- size: `709`
- prototype: `__int64 __usercall@<rax>(struct TpmTransport *this@<rcx>, unsigned int@<edx>, unsigned __int16@<r8w>, unsigned __int16 *@<r9>, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000660c`

## callees

- `0x140006b70`
- `0x1400078b8`
- `0x140009278`
- `0x140009660`
- `0x14001a770`
- `0x140039740`
- `0x140039840`
- `0x140039b40`

## pseudocode

```c
__int64 __fastcall Tpm20CmdPcrRead(struct TpmTransport *this, __int64 a2, __int16 a3, unsigned __int16 *a4, void *a5)
{
  __int64 result; // rax
  __int16 v9; // dx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int v13; // [rsp+40h] [rbp-71h] BYREF
  __int16 v14; // [rsp+48h] [rbp-69h] BYREF
  int v15; // [rsp+4Ah] [rbp-67h]
  int v16; // [rsp+4Eh] [rbp-63h]
  int v17; // [rsp+52h] [rbp-5Fh]
  __int16 v18; // [rsp+56h] [rbp-5Bh]
  int v19; // [rsp+58h] [rbp-59h]
  unsigned int v20[24]; // [rsp+60h] [rbp-51h] BYREF

  memset(v20, 0, 0x5Eu);
  if ( a4 )
  {
    *a4 = 0;
    if ( a3 == 4 || (unsigned __int16)(a3 - 11) <= 1u )
    {
      v14 = 384;
      v18 = __ROR2__(a3, 8);
      v15 = 335544320;
      v16 = 2113994752;
      v17 = 0x1000000;
      v19 = 8195;
      v13 = 94;
      result = TpmTransport::DispatchCommand(this, (char *)&v14, 0x14u, (char *)v20, &v13, 1, 0);
      if ( (int)result < 0 )
        return result;
      if ( v13 - 50 > 0x2C
        || *(unsigned int *)((char *)v20 + 2) != _byteswap_ulong(v13)
        || LOWORD(v20[0]) != 384
        || *(unsigned int *)((char *)&v20[1] + 2) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids);
        return 3221225862LL;
      }
      if ( v20[6] != 0x1000000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            27,
            WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids,
            _byteswap_ulong(v20[6]));
        return 3221225862LL;
      }
      v9 = v20[7];
      switch ( a3 )
      {
        case 4:
          if ( LOWORD(v20[7]) != 5120 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              return 3221225862LL;
            }
            v11 = 28;
            v12 = 20;
LABEL_18:
            WPP_SF_Dd(v10->AttachedDevice, v11, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids, v12);
            return 3221225862LL;
          }
          *a4 = 20;
          break;
        case 11:
          if ( LOWORD(v20[7]) != 0x2000 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              return 3221225862LL;
            }
            v12 = 32;
            v11 = 29;
            goto LABEL_18;
          }
          *a4 = 32;
LABEL_32:
          memmove(a5, (char *)&v20[7] + 2, *a4);
          return 0;
        case 12:
          if ( v9 != 12288 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              return 3221225862LL;
            }
            v11 = 30;
            v12 = 48;
            goto LABEL_18;
          }
          *a4 = 48;
          break;
      }
      goto LABEL_32;
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140006b70  push    rbp
0x140006b72  push    rbx
0x140006b73  push    rsi
0x140006b74  push    rdi
0x140006b75  push    r13
0x140006b77  push    r14
0x140006b79  push    r15
0x140006b7b  lea     rbp, [rsp-1Fh]
0x140006b80  sub     rsp, 0D0h
0x140006b87  mov     rax, cs:__security_cookie
0x140006b8e  xor     rax, rsp
0x140006b91  mov     [rbp+4Fh+var_40], rax
0x140006b95  mov     r14, [rbp+4Fh+arg_20]
0x140006b99  xor     edx, edx; Val
0x140006b9b  movzx   edi, r8w
0x140006b9f  mov     rsi, rcx
0x140006ba2  lea     rcx, [rbp+4Fh+var_A0]; void *
0x140006ba6  mov     rbx, r9
0x140006ba9  lea     r8d, [rdx+5Eh]; Size
0x140006bad  call    memset
0x140006bb2  test    rbx, rbx
0x140006bb5  jz      loc_140006E11
0x140006bbb  xor     eax, eax
0x140006bbd  mov     [rbx], ax
0x140006bc0  lea     r15d, [rax+1]
0x140006bc4  cmp     di, 4
0x140006bc8  jz      short loc_140006BD7
0x140006bca  lea     eax, [rdi-0Bh]
0x140006bcd  cmp     ax, r15w
0x140006bd1  ja      loc_140006E11
0x140006bd7  mov     eax, 180h
0x140006bdc  mov     [rsp+100h+var_D0], 0; struct TpmTransport::TpmTimeouts *
0x140006be5  mov     [rbp+4Fh+var_B8], ax
0x140006be9  lea     r9, [rbp+4Fh+var_A0]; void *
0x140006bed  movzx   eax, di
0x140006bf0  mov     [rsp+100h+var_D8], r15d; int
0x140006bf5  ror     ax, 8
0x140006bf9  lea     rdx, [rbp+4Fh+var_B8]; void *
0x140006bfd  mov     [rbp+4Fh+var_AA], ax
0x140006c01  mov     r13d, 20h ; ' '
0x140006c07  lea     rax, [rbp+4Fh+var_C0]
0x140006c0b  mov     [rbp+4Fh+var_B6], 14000000h
0x140006c12  mov     rcx, rsi; this
0x140006c15  mov     [rsp+100h+var_E0], rax; unsigned int *
0x140006c1a  mov     [rbp+4Fh+var_B2], 7E010000h
0x140006c21  lea     r8d, [r13-0Ch]; unsigned int
0x140006c25  mov     [rbp+4Fh+var_AE], 1000000h
0x140006c2c  mov     [rbp+4Fh+var_A8], 2003h
0x140006c33  mov     [rbp+4Fh+var_C0], 5Eh ; '^'
0x140006c3a  call    ?DispatchCommand@TpmTransport@@QEAAJPEAXI0PEAIHPEAVTpmTimeouts@1@@Z; TpmTransport::DispatchCommand(void *,uint,void *,uint *,int,TpmTransport::TpmTimeouts *)
0x140006c3f  test    eax, eax
0x140006c41  js      loc_140006E16
0x140006c47  mov     ecx, [rbp+4Fh+var_C0]
0x140006c4a  lea     eax, [rcx-32h]
0x140006c4d  cmp     eax, 2Ch ; ','
0x140006c50  ja      loc_140006DDA
0x140006c56  bswap   ecx
0x140006c58  cmp     [rbp+4Fh+var_9E], ecx
0x140006c5b  jnz     loc_140006DDA
0x140006c61  mov     eax, 180h
0x140006c66  cmp     [rbp+4Fh+var_A0], ax
0x140006c6a  jnz     loc_140006DDA
0x140006c70  cmp     [rbp+4Fh+var_9A], 0
0x140006c74  jnz     loc_140006DDA
0x140006c7a  mov     r9d, [rbp+4Fh+var_88]
0x140006c7e  cmp     r9d, 1000000h
0x140006c85  jz      short loc_140006CC6
0x140006c87  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006c8e  lea     rax, WPP_GLOBAL_Control
0x140006c95  cmp     rcx, rax
0x140006c98  jz      loc_140006E0A
0x140006c9e  mov     eax, [rcx+2Ch]
0x140006ca1  test    r15b, al
0x140006ca4  jz      loc_140006E0A
0x140006caa  mov     rcx, [rcx+18h]
0x140006cae  lea     edx, [r13-5]
0x140006cb2  bswap   r9d
0x140006cb5  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x140006cbc  call    WPP_SF_d
0x140006cc1  jmp     loc_140006E0A
0x140006cc6  movzx   edx, [rbp+4Fh+var_84]
0x140006cca  cmp     di, 4
0x140006cce  jnz     loc_140006D78
0x140006cd4  mov     eax, 1400h
0x140006cd9  cmp     dx, ax
0x140006cdc  jz      short loc_140006D2A
0x140006cde  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006ce5  lea     rax, WPP_GLOBAL_Control
0x140006cec  cmp     rcx, rax
0x140006cef  jz      loc_140006E0A
0x140006cf5  mov     eax, [rcx+2Ch]
0x140006cf8  test    r15b, al
0x140006cfb  jz      loc_140006E0A
0x140006d01  ror     dx, 8
0x140006d05  movzx   eax, dx
0x140006d08  mov     edx, 1Ch
0x140006d0d  lea     r9d, [rdx-8]
0x140006d11  mov     rcx, [rcx+18h]
0x140006d15  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x140006d1c  mov     dword ptr [rsp+100h+var_E0], eax
0x140006d20  call    WPP_SF_Dd
0x140006d25  jmp     loc_140006E0A
0x140006d2a  mov     word ptr [rbx], 14h
0x140006d2f  cmp     di, 0Ch
0x140006d33  jnz     loc_140006DC6
0x140006d39  mov     eax, 3000h
0x140006d3e  cmp     dx, ax
0x140006d41  jz      short loc_140006DC1
0x140006d43  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006d4a  lea     rax, WPP_GLOBAL_Control
0x140006d51  cmp     rcx, rax
0x140006d54  jz      loc_140006E0A
0x140006d5a  mov     eax, [rcx+2Ch]
0x140006d5d  test    r15b, al
0x140006d60  jz      loc_140006E0A
0x140006d66  ror     dx, 8
0x140006d6a  movzx   eax, dx
0x140006d6d  mov     edx, 1Eh
0x140006d72  lea     r9d, [rdx+12h]
0x140006d76  jmp     short loc_140006D11
0x140006d78  cmp     di, 0Bh
0x140006d7c  jnz     short loc_140006D2F
0x140006d7e  movzx   edx, [rbp+4Fh+var_84]
0x140006d82  mov     eax, 2000h
0x140006d87  cmp     dx, ax
0x140006d8a  jz      short loc_140006DBB
0x140006d8c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006d93  lea     rax, WPP_GLOBAL_Control
0x140006d9a  cmp     rcx, rax
0x140006d9d  jz      short loc_140006E0A
0x140006d9f  mov     eax, [rcx+2Ch]
0x140006da2  test    r15b, al
0x140006da5  jz      short loc_140006E0A
0x140006da7  ror     dx, 8
0x140006dab  mov     r9d, r13d
0x140006dae  movzx   eax, dx
0x140006db1  mov     edx, 1Dh
0x140006db6  jmp     loc_140006D11
0x140006dbb  mov     [rbx], r13w
0x140006dbf  jmp     short loc_140006DC6
0x140006dc1  mov     word ptr [rbx], 30h ; '0'
0x140006dc6  movzx   r8d, word ptr [rbx]; Size
0x140006dca  lea     rdx, [rbp+4Fh+Src]; Src
0x140006dce  mov     rcx, r14; void *
0x140006dd1  call    memmove
0x140006dd6  xor     eax, eax
0x140006dd8  jmp     short loc_140006E16
0x140006dda  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006de1  lea     rax, WPP_GLOBAL_Control
0x140006de8  cmp     rcx, rax
0x140006deb  jz      short loc_140006E0A
0x140006ded  mov     eax, [rcx+2Ch]
0x140006df0  test    r15b, al
0x140006df3  jz      short loc_140006E0A
0x140006df5  mov     rcx, [rcx+18h]
0x140006df9  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x140006e00  mov     edx, 1Ah
0x140006e05  call    WPP_SF_
0x140006e0a  mov     eax, 0C0000186h
0x140006e0f  jmp     short loc_140006E16
0x140006e11  mov     eax, 0C000000Dh
0x140006e16  mov     rcx, [rbp+4Fh+var_40]
0x140006e1a  xor     rcx, rsp; StackCookie
0x140006e1d  call    __security_check_cookie
0x140006e22  add     rsp, 0D0h
0x140006e29  pop     r15
0x140006e2b  pop     r14
0x140006e2d  pop     r13
0x140006e2f  pop     rdi
0x140006e30  pop     rsi
0x140006e31  pop     rbx
0x140006e32  pop     rbp
0x140006e33  retn
```
