# HUBDESC_InternalValidateUSB20DeviceCapabilityDescriptor

- ea: `0x14003b9a8`
- end: `0x14003bd58`
- name: `HUBDESC_InternalValidateUSB20DeviceCapabilityDescriptor`
- size: `944`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14003676c`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x14001cf04`
- `0x14002d940`
- `0x14003b9a8`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_InternalValidateUSB20DeviceCapabilityDescriptor(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        int *a4,
        int *a5,
        __int64 a6)
{
  int *v6; // rdi
  int v10; // r15d
  __int64 *v11; // r8
  int v12; // r13d
  int v13; // r14d
  int v14; // edx
  unsigned int v15; // r15d
  int v16; // r8d
  __int64 v17; // rdx
  char v18; // bl
  int v19; // eax
  int *v20; // r14
  int v21; // ecx
  int v22; // ecx
  int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // ecx
  int v27; // [rsp+A0h] [rbp+8h] BYREF

  v27 = 0;
  v6 = a4;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v6 = &v27;
  }
  v10 = *(_DWORD *)(a2 + 72);
  v11 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
  v12 = a6;
  v13 = a1 - *(_DWORD *)(a2 + 56);
  v14 = 7;
  v15 = v10 - v13;
  if ( *(_BYTE *)a1 >= 7u )
  {
LABEL_10:
    if ( *(_BYTE *)a1 > 7u )
    {
      if ( *(_BYTE *)(a2 + 12) || (unsigned __int16)(*(_WORD *)a2 - 513) <= 0xEu )
        *v6 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_DDD(
          v12,
          v14,
          (unsigned int)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          220,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          v13,
          *(_BYTE *)a1,
          7);
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(*(_QWORD *)(a2 + 40), 145, v11);
    }
    if ( *a3 <= v15 )
    {
      if ( (*(_DWORD *)(a1 + 3) & 0xFFFF00E1) != 0 )
      {
        if ( *(_BYTE *)(a2 + 15) )
          *v6 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = 2;
          WPP_RECORDER_SF_d(
            v12,
            v14,
            5,
            222,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            *(_DWORD *)(a1 + 3));
        }
        (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(*(_QWORD *)(a2 + 40), 147, v11);
      }
      v19 = *(_DWORD *)(a1 + 3);
      if ( (v19 & 2) != 0 )
      {
        v20 = a5;
        *a5 |= 1u;
        v21 = *v20 ^ ((unsigned __int8)*v20 ^ (unsigned __int8)(*(_DWORD *)(a1 + 3) >> 1)) & 2;
        *v20 = v21;
        if ( (*(_BYTE *)(a1 + 3) & 8) != 0 )
        {
          v22 = v21 | 4;
          *v20 = v22;
          *v20 = v22 ^ ((unsigned __int8)v22 ^ (unsigned __int8)(*(_DWORD *)(a1 + 3) >> 4)) & 0xF0;
        }
        v23 = *(_DWORD *)(a1 + 3);
        if ( (v23 & 0x10) != 0 )
        {
          if ( (v23 & 8) != 0 )
          {
            v24 = (unsigned __int16)v23 >> 12;
            v25 = (*(_DWORD *)(a1 + 3) >> 8) & 0xF;
            if ( v24 <= v25 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v14) = 2;
                WPP_RECORDER_SF_dD(v12, v14, 5, 223, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v24, v25);
              }
              (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(*(_QWORD *)(a2 + 40), 151, v11);
            }
          }
          *v20 |= 8u;
          *v20 ^= ((unsigned __int16)*v20 ^ (unsigned __int16)(*(_DWORD *)(a1 + 3) >> 4)) & 0xF00;
        }
        goto LABEL_50;
      }
      if ( (v19 & 4) == 0 )
      {
LABEL_50:
        v18 = 1;
LABEL_51:
        if ( !*v6 )
          return v18;
        goto LABEL_52;
      }
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
        *v6 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_d(
          v12,
          v14,
          5,
          224,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *(_DWORD *)(a1 + 3));
      }
      v17 = 150;
    }
    else
    {
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
        *v6 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_d(v12, v14, 5, 221, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v13);
      }
      v17 = 148;
    }
    (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(*(_QWORD *)(a2 + 40), v17, v11);
    goto LABEL_50;
  }
  (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(
    *(_QWORD *)(a2 + 40),
    146,
    WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  v14 = 7;
  if ( v15 >= 7 )
  {
    *v6 = 2;
    *a3 = 7;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_DDDD(
        v12,
        v14,
        5,
        218,
        (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
        v13,
        *(_BYTE *)a1,
        7,
        7);
      v14 = 7;
    }
    v11 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
    goto LABEL_10;
  }
  v18 = 1;
  *v6 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_DDD(
      v12,
      v14,
      v16,
      219,
      (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
      v13,
      *(_BYTE *)a1,
      7);
    goto LABEL_51;
  }
LABEL_52:
  v18 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_(v12, v14, 5, 225, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v18;
}

```

## disassembly

```asm
0x14003b9a8  mov     rax, rsp
0x14003b9ab  push    rbx
0x14003b9ac  push    rbp
0x14003b9ad  push    rsi
0x14003b9ae  push    rdi
0x14003b9af  push    r12
0x14003b9b1  push    r13
0x14003b9b3  push    r14
0x14003b9b5  push    r15
0x14003b9b7  sub     rsp, 58h
0x14003b9bb  mov     dword ptr [rax+8], 0
0x14003b9c2  mov     rdi, r9
0x14003b9c5  mov     r12, r8
0x14003b9c8  mov     rbx, rdx
0x14003b9cb  mov     rsi, rcx
0x14003b9ce  test    r9, r9
0x14003b9d1  jnz     short loc_14003B9D9
0x14003b9d3  lea     rdi, [rax+8]
0x14003b9d7  jmp     short loc_14003B9E6
0x14003b9d9  cmp     byte ptr [rdx+30h], 0
0x14003b9dd  jz      short loc_14003B9E6
0x14003b9df  mov     dword ptr [r9], 0
0x14003b9e6  mov     r15d, [rdx+48h]
0x14003b9ea  lea     r8, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003b9f1  mov     r13, [rsp+98h+arg_28]
0x14003b9f9  lea     rbp, WPP_RECORDER_INITIALIZED
0x14003ba00  mov     r14d, esi
0x14003ba03  sub     r14d, [rdx+38h]
0x14003ba07  mov     edx, 7
0x14003ba0c  sub     r15d, r14d
0x14003ba0f  cmp     [rcx], dl
0x14003ba11  jnb     short loc_14003BA86
0x14003ba13  mov     rax, [rbx+18h]
0x14003ba17  mov     edx, 92h
0x14003ba1c  mov     rcx, [rbx+28h]
0x14003ba20  call    _guard_dispatch_icall
0x14003ba25  mov     edx, 7
0x14003ba2a  cmp     r15d, edx
0x14003ba2d  jb      loc_14003BB41
0x14003ba33  mov     dword ptr [rdi], 2
0x14003ba39  mov     [r12], edx
0x14003ba3d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003ba44  jz      short loc_14003BA7F
0x14003ba46  movzx   eax, byte ptr [rsi]
0x14003ba49  lea     r8d, [rdx-2]
0x14003ba4d  mov     [rsp+98h+var_58], edx
0x14003ba51  mov     r9d, 0DAh
0x14003ba57  mov     [rsp+98h+var_60], edx
0x14003ba5b  mov     rcx, r13
0x14003ba5e  mov     [rsp+98h+var_68], eax
0x14003ba62  mov     dl, 2
0x14003ba64  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003ba6b  mov     [rsp+98h+var_70], r14d
0x14003ba70  mov     [rsp+98h+var_78], rax
0x14003ba75  call    WPP_RECORDER_SF_DDDD
0x14003ba7a  mov     edx, 7
0x14003ba7f  lea     r8, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003ba86  cmp     [rsi], dl
0x14003ba88  jbe     short loc_14003BAE7
0x14003ba8a  cmp     byte ptr [rbx+0Ch], 0
0x14003ba8e  jnz     short loc_14003BAA1
0x14003ba90  movzx   eax, word ptr [rbx]
0x14003ba93  mov     ecx, 201h
0x14003ba98  sub     ax, cx
0x14003ba9b  cmp     ax, 0Eh
0x14003ba9f  ja      short loc_14003BAA7
0x14003baa1  mov     dword ptr [rdi], 2
0x14003baa7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003baae  jz      short loc_14003BAD5
0x14003bab0  movzx   eax, byte ptr [rsi]
0x14003bab3  mov     r9d, 0DCh
0x14003bab9  mov     [rsp+98h+var_60], edx
0x14003babd  mov     rcx, r13
0x14003bac0  mov     [rsp+98h+var_68], eax
0x14003bac4  mov     dl, 2
0x14003bac6  mov     [rsp+98h+var_70], r14d
0x14003bacb  mov     [rsp+98h+var_78], r8
0x14003bad0  call    WPP_RECORDER_SF_DDD
0x14003bad5  mov     rax, [rbx+18h]
0x14003bad9  mov     edx, 91h
0x14003bade  mov     rcx, [rbx+28h]
0x14003bae2  call    _guard_dispatch_icall
0x14003bae7  cmp     [r12], r15d
0x14003baeb  jbe     loc_14003BB8D
0x14003baf1  mov     eax, 200h
0x14003baf6  cmp     [rbx], ax
0x14003baf9  ja      short loc_14003BB01
0x14003bafb  cmp     byte ptr [rbx+0Ch], 0
0x14003baff  jz      short loc_14003BB07
0x14003bb01  mov     dword ptr [rdi], 2
0x14003bb07  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003bb0e  jz      short loc_14003BB37
0x14003bb10  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003bb17  mov     [rsp+98h+var_70], r14d
0x14003bb1c  mov     r9d, 0DDh
0x14003bb22  mov     [rsp+98h+var_78], rax
0x14003bb27  mov     r8d, 5
0x14003bb2d  mov     dl, 2
0x14003bb2f  mov     rcx, r13
0x14003bb32  call    WPP_RECORDER_SF_d
0x14003bb37  mov     edx, 94h
0x14003bb3c  jmp     loc_14003BD00
0x14003bb41  mov     ebx, 1
0x14003bb46  mov     [rdi], ebx
0x14003bb48  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003bb4f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14003bb56  jz      loc_14003BD17
0x14003bb5c  movzx   eax, byte ptr [rsi]
0x14003bb5f  mov     r9d, 0DBh
0x14003bb65  mov     [rsp+98h+var_60], edx
0x14003bb69  mov     rcx, r13
0x14003bb6c  mov     [rsp+98h+var_68], eax
0x14003bb70  mov     dl, 2
0x14003bb72  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003bb79  mov     [rsp+98h+var_70], r14d
0x14003bb7e  mov     [rsp+98h+var_78], rax
0x14003bb83  call    WPP_RECORDER_SF_DDD
0x14003bb88  jmp     loc_14003BD12
0x14003bb8d  test    dword ptr [rsi+3], 0FFFF00E1h
0x14003bb94  jz      short loc_14003BBE6
0x14003bb96  cmp     byte ptr [rbx+0Fh], 0
0x14003bb9a  jz      short loc_14003BBA2
0x14003bb9c  mov     dword ptr [rdi], 2
0x14003bba2  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003bba9  jz      short loc_14003BBD4
0x14003bbab  mov     eax, [rsi+3]
0x14003bbae  mov     r9d, 0DEh
0x14003bbb4  mov     [rsp+98h+var_70], eax
0x14003bbb8  mov     r8d, 5
0x14003bbbe  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003bbc5  mov     dl, 2
0x14003bbc7  mov     rcx, r13
0x14003bbca  mov     [rsp+98h+var_78], rax
0x14003bbcf  call    WPP_RECORDER_SF_d
0x14003bbd4  mov     rax, [rbx+18h]
0x14003bbd8  mov     edx, 93h
0x14003bbdd  mov     rcx, [rbx+28h]
0x14003bbe1  call    _guard_dispatch_icall
0x14003bbe6  mov     eax, [rsi+3]
0x14003bbe9  test    al, 2
0x14003bbeb  jz      loc_14003BCAF
0x14003bbf1  mov     r14, [rsp+98h+arg_20]
0x14003bbf9  or      dword ptr [r14], 1
0x14003bbfd  mov     eax, [r14]
0x14003bc00  mov     ecx, [rsi+3]
0x14003bc03  shr     ecx, 1
0x14003bc05  xor     ecx, eax
0x14003bc07  and     ecx, 2
0x14003bc0a  xor     ecx, eax
0x14003bc0c  mov     [r14], ecx
0x14003bc0f  test    byte ptr [rsi+3], 8
0x14003bc13  jz      short loc_14003BC2D
0x14003bc15  or      ecx, 4
0x14003bc18  mov     [r14], ecx
0x14003bc1b  mov     eax, [rsi+3]
0x14003bc1e  shr     eax, 4
0x14003bc21  xor     eax, ecx
0x14003bc23  and     eax, 0F0h
0x14003bc28  xor     eax, ecx
0x14003bc2a  mov     [r14], eax
0x14003bc2d  mov     eax, [rsi+3]
0x14003bc30  test    al, 10h
0x14003bc32  jz      loc_14003BD0D
0x14003bc38  test    al, 8
0x14003bc3a  jz      short loc_14003BC93
0x14003bc3c  mov     ecx, eax
0x14003bc3e  shr     eax, 0Ch
0x14003bc41  shr     ecx, 8
0x14003bc44  and     eax, 0Fh
0x14003bc47  and     ecx, 0Fh
0x14003bc4a  cmp     eax, ecx
0x14003bc4c  ja      short loc_14003BC93
0x14003bc4e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003bc55  jz      short loc_14003BC81
0x14003bc57  mov     [rsp+98h+var_68], ecx
0x14003bc5b  mov     r9d, 0DFh
0x14003bc61  mov     [rsp+98h+var_70], eax
0x14003bc65  mov     r8d, 5
0x14003bc6b  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003bc72  mov     dl, 2
0x14003bc74  mov     rcx, r13
0x14003bc77  mov     [rsp+98h+var_78], rax
0x14003bc7c  call    WPP_RECORDER_SF_dD
0x14003bc81  mov     rax, [rbx+18h]
0x14003bc85  mov     edx, 97h
0x14003bc8a  mov     rcx, [rbx+28h]
0x14003bc8e  call    _guard_dispatch_icall
0x14003bc93  or      dword ptr [r14], 8
0x14003bc97  mov     eax, [r14]
0x14003bc9a  mov     ecx, [rsi+3]
0x14003bc9d  shr     ecx, 4
0x14003bca0  xor     ecx, eax
0x14003bca2  and     ecx, 0F00h
0x14003bca8  xor     ecx, eax
0x14003bcaa  mov     [r14], ecx
0x14003bcad  jmp     short loc_14003BD0D
0x14003bcaf  test    al, 4
0x14003bcb1  jz      short loc_14003BD0D
0x14003bcb3  mov     eax, 200h
0x14003bcb8  cmp     [rbx], ax
0x14003bcbb  ja      short loc_14003BCC3
0x14003bcbd  cmp     byte ptr [rbx+0Ch], 0
0x14003bcc1  jz      short loc_14003BCC9
0x14003bcc3  mov     dword ptr [rdi], 2
0x14003bcc9  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003bcd0  jz      short loc_14003BCFB
0x14003bcd2  mov     eax, [rsi+3]
0x14003bcd5  mov     r9d, 0E0h
0x14003bcdb  mov     [rsp+98h+var_70], eax
0x14003bcdf  mov     r8d, 5
0x14003bce5  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003bcec  mov     dl, 2
0x14003bcee  mov     rcx, r13
0x14003bcf1  mov     [rsp+98h+var_78], rax
0x14003bcf6  call    WPP_RECORDER_SF_d
0x14003bcfb  mov     edx, 96h
0x14003bd00  mov     rcx, [rbx+28h]
0x14003bd04  mov     rax, [rbx+18h]
0x14003bd08  call    _guard_dispatch_icall
0x14003bd0d  mov     ebx, 1
0x14003bd12  cmp     dword ptr [rdi], 0
0x14003bd15  jz      short loc_14003BD44
0x14003bd17  xor     bl, bl
0x14003bd19  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003bd20  jz      short loc_14003BD44
0x14003bd22  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003bd29  mov     r9d, 0E1h
0x14003bd2f  mov     r8d, 5
0x14003bd35  mov     [rsp+98h+var_78], rax
0x14003bd3a  mov     dl, 2
0x14003bd3c  mov     rcx, r13
0x14003bd3f  call    WPP_RECORDER_SF_
0x14003bd44  mov     al, bl
0x14003bd46  add     rsp, 58h
0x14003bd4a  pop     r15
0x14003bd4c  pop     r14
0x14003bd4e  pop     r13
0x14003bd50  pop     r12
0x14003bd52  pop     rdi
0x14003bd53  pop     rsi
0x14003bd54  pop     rbp
0x14003bd55  pop     rbx
0x14003bd56  retn
```
