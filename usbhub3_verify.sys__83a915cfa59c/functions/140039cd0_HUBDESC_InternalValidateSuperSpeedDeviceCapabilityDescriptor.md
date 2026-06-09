# HUBDESC_InternalValidateSuperSpeedDeviceCapabilityDescriptor

- ea: `0x140039cd0`
- end: `0x14003a273`
- name: `HUBDESC_InternalValidateSuperSpeedDeviceCapabilityDescriptor`
- size: `1443`
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
- `0x140039cd0`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_InternalValidateSuperSpeedDeviceCapabilityDescriptor(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        int *a4,
        _WORD *a5,
        unsigned __int16 *a6,
        _BYTE *a7,
        __int64 a8)
{
  int *v9; // rsi
  int v10; // edx
  _BYTE *v12; // r15
  __int64 *v13; // r8
  int v14; // r13d
  int v15; // r14d
  unsigned int v16; // r12d
  int v17; // r8d
  unsigned int *v18; // rax
  __int64 v19; // r9
  __int64 v20; // rdx
  char v21; // bl
  __int64 v22; // rdx
  int v23; // eax
  __int16 v24; // ax
  unsigned __int16 v25; // ax
  int v27; // [rsp+90h] [rbp+8h] BYREF
  unsigned int *v28; // [rsp+A0h] [rbp+18h]

  v28 = a3;
  v9 = a4;
  v10 = 0;
  v27 = 0;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v9 = &v27;
  }
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  v12 = a7;
  if ( *a7 )
    *a7 = 0;
  v13 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
  v14 = a8;
  v15 = a1 - *(_DWORD *)(a2 + 56);
  v16 = *(_DWORD *)(a2 + 72) - v15;
  if ( *(_BYTE *)a1 >= 0xAu )
  {
LABEL_16:
    v19 = 768;
    if ( *(_BYTE *)a1 > 0xAu )
    {
      if ( *(_BYTE *)(a2 + 12) || (unsigned __int16)(*(_WORD *)a2 - 768) <= 0x10u )
        *v9 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_DDD(
          v14,
          v10,
          (unsigned int)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          206,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          v15,
          *(_BYTE *)a1,
          10);
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64 *, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 135, v13, v19);
    }
    if ( *v28 > v16 )
    {
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
        *v9 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_d(v14, v10, 5, 207, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v15);
      }
      v20 = 140;
      goto LABEL_30;
    }
    if ( (*(_BYTE *)(a1 + 3) & 0xFD) != 0 )
    {
      if ( *(_BYTE *)(a2 + 15) )
        *v9 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_d(
          v14,
          v10,
          5,
          208,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *(_BYTE *)(a1 + 3));
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64 *, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 137, v13, v19);
    }
    if ( (*(_BYTE *)(a1 + 3) & 2) != 0 && *v12 )
      *v12 = 1;
    if ( (*(_WORD *)(a1 + 4) & 0xFFF0) != 0 )
    {
      if ( *(_BYTE *)(a2 + 15) )
        *v9 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_d(
          v14,
          v10,
          5,
          209,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *(_WORD *)(a1 + 4));
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64 *, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 143, v13, v19);
    }
    if ( !*(_WORD *)(a1 + 4) )
    {
      *v9 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_(v14, v10, 5, 210, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64 *, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 144, v13, v19);
    }
    if ( *(_BYTE *)(a1 + 6) <= 3u )
    {
      v23 = *(unsigned __int16 *)(a1 + 4);
      if ( _bittest(&v23, *(unsigned __int8 *)(a1 + 6)) )
      {
LABEL_63:
        v24 = *(unsigned __int8 *)(a1 + 7);
        if ( (unsigned __int8)v24 < 0xBu )
        {
          if ( a5 )
          {
            *a5 = v24;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v10) = 4;
              WPP_RECORDER_SF_d(
                v14,
                v10,
                5,
                214,
                (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                *(_BYTE *)(a1 + 7));
            }
          }
        }
        else
        {
          if ( *(_BYTE *)(a2 + 12) || (unsigned __int16)(*(_WORD *)a2 - 768) <= 0x10u )
            *v9 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v10) = 2;
            WPP_RECORDER_SF_d(
              v14,
              v10,
              5,
              213,
              (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
              *(_BYTE *)(a1 + 7));
          }
          (*(void (__fastcall **)(_QWORD, __int64, __int64 *, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 138, v13, v19);
        }
        v25 = *(_WORD *)(a1 + 8);
        if ( v25 < 0x800u )
        {
          if ( a6 )
          {
            *a6 = v25;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v10) = 4;
              WPP_RECORDER_SF_d(
                v14,
                v10,
                5,
                216,
                (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                *(_WORD *)(a1 + 8));
            }
          }
          goto LABEL_83;
        }
        if ( *(_BYTE *)(a2 + 12) || (unsigned __int16)(*(_WORD *)a2 - 768) <= 0x10u )
          *v9 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 2;
          WPP_RECORDER_SF_d(
            v14,
            v10,
            5,
            215,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            *(_WORD *)(a1 + 8));
        }
        v20 = 139;
LABEL_30:
        (*(void (__fastcall **)(_QWORD, __int64, __int64 *, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), v20, v13, v19);
LABEL_83:
        v21 = 1;
LABEL_84:
        if ( !*v9 )
          return v21;
        goto LABEL_85;
      }
      *v9 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_dD(
          v14,
          v10,
          5,
          212,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *(_BYTE *)(a1 + 6),
          *(_WORD *)(a1 + 4));
      }
      v22 = 141;
    }
    else
    {
      if ( *(_BYTE *)(a2 + 15) )
        *v9 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_d(
          v14,
          v10,
          5,
          211,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *(_BYTE *)(a1 + 6));
      }
      v22 = 142;
    }
    (*(void (__fastcall **)(_QWORD, __int64, __int64 *, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), v22, v13, v19);
    goto LABEL_63;
  }
  (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(
    *(_QWORD *)(a2 + 40),
    136,
    WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  if ( v16 >= 0xA )
  {
    v18 = v28;
    *v9 = 2;
    *v18 = 10;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_DDDD(
        v14,
        v10,
        5,
        204,
        (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
        v15,
        *(_BYTE *)a1,
        10,
        10);
    }
    v13 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
    v10 = 0;
    goto LABEL_16;
  }
  v21 = 1;
  *v9 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_DDD(
      v14,
      2,
      v17,
      205,
      (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
      v15,
      *(_BYTE *)a1,
      10);
    goto LABEL_84;
  }
LABEL_85:
  v21 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_(v14, v10, 5, 217, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v21;
}

```

## disassembly

```asm
0x140039cd0  mov     rax, rsp
0x140039cd3  mov     [rax+10h], rbx
0x140039cd7  mov     [rax+18h], r8
0x140039cdb  push    rbp
0x140039cdc  push    rsi
0x140039cdd  push    rdi
0x140039cde  push    r12
0x140039ce0  push    r13
0x140039ce2  push    r14
0x140039ce4  push    r15
0x140039ce6  sub     rsp, 50h
0x140039cea  mov     rbx, rdx
0x140039ced  mov     rsi, r9
0x140039cf0  xor     edx, edx
0x140039cf2  mov     rdi, rcx
0x140039cf5  mov     [rax+8], edx
0x140039cf8  test    r9, r9
0x140039cfb  jnz     short loc_140039D03
0x140039cfd  lea     rsi, [rax+8]
0x140039d01  jmp     short loc_140039D0B
0x140039d03  cmp     [rbx+30h], dl
0x140039d06  jz      short loc_140039D0B
0x140039d08  mov     [r9], edx
0x140039d0b  mov     rcx, [rsp+88h+arg_20]
0x140039d13  test    rcx, rcx
0x140039d16  jz      short loc_140039D1B
0x140039d18  mov     [rcx], dx
0x140039d1b  mov     rcx, [rsp+88h+arg_28]
0x140039d23  test    rcx, rcx
0x140039d26  jz      short loc_140039D2B
0x140039d28  mov     [rcx], dx
0x140039d2b  mov     r15, [rsp+88h+arg_30]
0x140039d33  cmp     [r15], dl
0x140039d36  jz      short loc_140039D3B
0x140039d38  mov     [r15], dl
0x140039d3b  mov     r12d, [rbx+48h]
0x140039d3f  lea     r8, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039d46  mov     r13, [rsp+88h+arg_38]
0x140039d4e  lea     rbp, WPP_RECORDER_INITIALIZED
0x140039d55  mov     r14d, edi
0x140039d58  mov     ecx, 0Ah
0x140039d5d  sub     r14d, [rbx+38h]
0x140039d61  sub     r12d, r14d
0x140039d64  cmp     [rdi], cl
0x140039d66  jnb     short loc_140039DE1
0x140039d68  mov     rax, [rbx+18h]
0x140039d6c  lea     edx, [rcx+7Eh]
0x140039d6f  mov     rcx, [rbx+28h]
0x140039d73  call    _guard_dispatch_icall
0x140039d78  mov     ecx, 0Ah
0x140039d7d  cmp     r12d, ecx
0x140039d80  jb      loc_140039EB4
0x140039d86  mov     rax, [rsp+88h+arg_10]
0x140039d8e  mov     dword ptr [rsi], 2
0x140039d94  mov     [rax], ecx
0x140039d96  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140039d9d  jz      short loc_140039DD8
0x140039d9f  movzx   eax, byte ptr [rdi]
0x140039da2  lea     r8d, [rcx-5]
0x140039da6  mov     [rsp+88h+var_48], ecx
0x140039daa  mov     r9d, 0CCh
0x140039db0  mov     [rsp+88h+var_50], ecx
0x140039db4  mov     dl, 2
0x140039db6  mov     [rsp+88h+var_58], eax
0x140039dba  mov     rcx, r13
0x140039dbd  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039dc4  mov     [rsp+88h+var_60], r14d
0x140039dc9  mov     [rsp+88h+var_68], rax
0x140039dce  call    WPP_RECORDER_SF_DDDD
0x140039dd3  mov     ecx, 0Ah
0x140039dd8  lea     r8, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039ddf  xor     edx, edx
0x140039de1  mov     r9d, 300h
0x140039de7  cmp     [rdi], cl
0x140039de9  jbe     short loc_140039E43
0x140039deb  cmp     [rbx+0Ch], dl
0x140039dee  jnz     short loc_140039DFD
0x140039df0  movzx   eax, word ptr [rbx]
0x140039df3  sub     ax, r9w
0x140039df7  cmp     ax, 10h
0x140039dfb  ja      short loc_140039E03
0x140039dfd  mov     dword ptr [rsi], 2
0x140039e03  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140039e0a  jz      short loc_140039E31
0x140039e0c  movzx   eax, byte ptr [rdi]
0x140039e0f  mov     r9d, 0CEh
0x140039e15  mov     [rsp+88h+var_50], ecx
0x140039e19  mov     dl, 2
0x140039e1b  mov     [rsp+88h+var_58], eax
0x140039e1f  mov     rcx, r13
0x140039e22  mov     [rsp+88h+var_60], r14d
0x140039e27  mov     [rsp+88h+var_68], r8
0x140039e2c  call    WPP_RECORDER_SF_DDD
0x140039e31  mov     rax, [rbx+18h]
0x140039e35  mov     edx, 87h
0x140039e3a  mov     rcx, [rbx+28h]
0x140039e3e  call    _guard_dispatch_icall
0x140039e43  mov     rax, [rsp+88h+arg_10]
0x140039e4b  cmp     [rax], r12d
0x140039e4e  jbe     loc_140039F04
0x140039e54  mov     eax, 200h
0x140039e59  xor     r12d, r12d
0x140039e5c  cmp     [rbx], ax
0x140039e5f  ja      short loc_140039E67
0x140039e61  cmp     [rbx+0Ch], r12b
0x140039e65  jz      short loc_140039E6D
0x140039e67  mov     dword ptr [rsi], 2
0x140039e6d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140039e74  jz      short loc_140039E9D
0x140039e76  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039e7d  mov     [rsp+88h+var_60], r14d
0x140039e82  mov     r9d, 0CFh
0x140039e88  mov     [rsp+88h+var_68], rax
0x140039e8d  mov     r8d, 5
0x140039e93  mov     dl, 2
0x140039e95  mov     rcx, r13
0x140039e98  call    WPP_RECORDER_SF_d
0x140039e9d  mov     edx, 8Ch
0x140039ea2  mov     rax, [rbx+18h]
0x140039ea6  mov     rcx, [rbx+28h]
0x140039eaa  call    _guard_dispatch_icall
0x140039eaf  jmp     loc_14003A21B
0x140039eb4  mov     ebx, 1
0x140039eb9  mov     [rsi], ebx
0x140039ebb  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140039ec2  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140039ec9  jz      loc_14003A227
0x140039ecf  movzx   eax, byte ptr [rdi]
0x140039ed2  lea     r15, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039ed9  mov     [rsp+88h+var_50], ecx
0x140039edd  lea     edx, [rbx+1]
0x140039ee0  mov     [rsp+88h+var_58], eax
0x140039ee4  mov     r9d, 0CDh
0x140039eea  mov     [rsp+88h+var_60], r14d
0x140039eef  mov     rcx, r13
0x140039ef2  mov     [rsp+88h+var_68], r15
0x140039ef7  call    WPP_RECORDER_SF_DDD
0x140039efc  xor     r12d, r12d
0x140039eff  jmp     loc_14003A220
0x140039f04  xor     r12d, r12d
0x140039f07  test    byte ptr [rdi+3], 0FDh
0x140039f0b  jz      short loc_140039F5E
0x140039f0d  cmp     [rbx+0Fh], r12b
0x140039f11  jz      short loc_140039F19
0x140039f13  mov     dword ptr [rsi], 2
0x140039f19  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140039f20  jz      short loc_140039F4C
0x140039f22  movzx   eax, byte ptr [rdi+3]
0x140039f26  mov     r9d, 0D0h
0x140039f2c  mov     [rsp+88h+var_60], eax
0x140039f30  mov     r8d, 5
0x140039f36  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039f3d  mov     dl, 2
0x140039f3f  mov     rcx, r13
0x140039f42  mov     [rsp+88h+var_68], rax
0x140039f47  call    WPP_RECORDER_SF_d
0x140039f4c  mov     rax, [rbx+18h]
0x140039f50  mov     edx, 89h
0x140039f55  mov     rcx, [rbx+28h]
0x140039f59  call    _guard_dispatch_icall
0x140039f5e  mov     r14d, 2
0x140039f64  test    [rdi+3], r14b
0x140039f68  jz      short loc_140039F73
0x140039f6a  cmp     [r15], r12b
0x140039f6d  jz      short loc_140039F73
0x140039f6f  mov     byte ptr [r15], 1
0x140039f73  mov     ecx, 0FFF0h
0x140039f78  test    [rdi+4], cx
0x140039f7c  jz      short loc_140039FCD
0x140039f7e  cmp     [rbx+0Fh], r12b
0x140039f82  jz      short loc_140039F87
0x140039f84  mov     [rsi], r14d
0x140039f87  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140039f8e  jz      short loc_140039FBB
0x140039f90  movzx   eax, word ptr [rdi+4]
0x140039f94  mov     r9d, 0D1h
0x140039f9a  mov     [rsp+88h+var_60], eax
0x140039f9e  mov     r8d, 5
0x140039fa4  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039fab  mov     dl, r14b
0x140039fae  mov     rcx, r13
0x140039fb1  mov     [rsp+88h+var_68], rax
0x140039fb6  call    WPP_RECORDER_SF_d
0x140039fbb  mov     rax, [rbx+18h]
0x140039fbf  mov     edx, 8Fh
0x140039fc4  mov     rcx, [rbx+28h]
0x140039fc8  call    _guard_dispatch_icall
0x140039fcd  cmp     [rdi+4], r12w
0x140039fd2  jnz     short loc_14003A015
0x140039fd4  mov     [rsi], r14d
0x140039fd7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140039fde  jz      short loc_14003A003
0x140039fe0  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140039fe7  mov     r9d, 0D2h
0x140039fed  mov     r8d, 5
0x140039ff3  mov     [rsp+88h+var_68], rax
0x140039ff8  mov     dl, r14b
0x140039ffb  mov     rcx, r13
0x140039ffe  call    WPP_RECORDER_SF_
0x14003a003  mov     rax, [rbx+18h]
0x14003a007  mov     edx, 90h
0x14003a00c  mov     rcx, [rbx+28h]
0x14003a010  call    _guard_dispatch_icall
0x14003a015  movzx   eax, byte ptr [rdi+6]
0x14003a019  cmp     al, 3
0x14003a01b  jbe     short loc_14003A061
0x14003a01d  cmp     [rbx+0Fh], r12b
0x14003a021  jz      short loc_14003A026
0x14003a023  mov     [rsi], r14d
0x14003a026  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a02d  jz      short loc_14003A05A
0x14003a02f  movzx   eax, byte ptr [rdi+6]
0x14003a033  mov     r9d, 0D3h
0x14003a039  mov     [rsp+88h+var_60], eax
0x14003a03d  mov     r8d, 5
0x14003a043  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a04a  mov     dl, r14b
0x14003a04d  mov     rcx, r13
0x14003a050  mov     [rsp+88h+var_68], rax
0x14003a055  call    WPP_RECORDER_SF_d
0x14003a05a  mov     edx, 8Eh
0x14003a05f  jmp     short loc_14003A0B0
0x14003a061  mov     ecx, eax
0x14003a063  movzx   eax, word ptr [rdi+4]
0x14003a067  bt      eax, ecx
0x14003a06a  jb      short loc_14003A0BD
0x14003a06c  mov     [rsi], r14d
0x14003a06f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a076  jz      short loc_14003A0AB
0x14003a078  movzx   eax, word ptr [rdi+4]
0x14003a07c  mov     r9d, 0D4h
0x14003a082  movzx   ecx, byte ptr [rdi+6]
0x14003a086  mov     r8d, 5
0x14003a08c  mov     [rsp+88h+var_58], eax
0x14003a090  mov     dl, r14b
0x14003a093  mov     [rsp+88h+var_60], ecx
0x14003a097  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a09e  mov     rcx, r13
0x14003a0a1  mov     [rsp+88h+var_68], rax
0x14003a0a6  call    WPP_RECORDER_SF_dD
0x14003a0ab  mov     edx, 8Dh
0x14003a0b0  mov     rcx, [rbx+28h]
0x14003a0b4  mov     rax, [rbx+18h]
0x14003a0b8  call    _guard_dispatch_icall
0x14003a0bd  movzx   eax, byte ptr [rdi+7]
0x14003a0c1  cmp     al, 0Bh
0x14003a0c3  jb      loc_14003A193
0x14003a0c9  cmp     [rbx+0Ch], r12b
0x14003a0cd  jnz     short loc_14003A0E0
0x14003a0cf  movzx   eax, word ptr [rbx]
0x14003a0d2  mov     ecx, 300h
0x14003a0d7  sub     ax, cx
0x14003a0da  cmp     ax, 10h
0x14003a0de  ja      short loc_14003A0E3
0x14003a0e0  mov     [rsi], r14d
0x14003a0e3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a0ea  jz      short loc_14003A117
0x14003a0ec  movzx   eax, byte ptr [rdi+7]
0x14003a0f0  mov     r9d, 0D5h
0x14003a0f6  mov     [rsp+88h+var_60], eax
0x14003a0fa  mov     r8d, 5
0x14003a100  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a107  mov     dl, r14b
0x14003a10a  mov     rcx, r13
0x14003a10d  mov     [rsp+88h+var_68], rax
0x14003a112  call    WPP_RECORDER_SF_d
0x14003a117  mov     rax, [rbx+18h]
0x14003a11b  mov     edx, 8Ah
0x14003a120  mov     rcx, [rbx+28h]
0x14003a124  call    _guard_dispatch_icall
0x14003a129  lea     r15, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a130  movzx   eax, word ptr [rdi+8]
0x14003a134  mov     ecx, 800h
0x14003a139  cmp     ax, cx
0x14003a13c  jb      loc_14003A1DF
0x14003a142  cmp     [rbx+0Ch], r12b
0x14003a146  jnz     short loc_14003A159
0x14003a148  movzx   eax, word ptr [rbx]
0x14003a14b  mov     ecx, 300h
0x14003a150  sub     ax, cx
0x14003a153  cmp     ax, 10h
0x14003a157  ja      short loc_14003A15C
0x14003a159  mov     [rsi], r14d
0x14003a15c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a163  jz      short loc_14003A189
0x14003a165  movzx   eax, word ptr [rdi+8]
0x14003a169  mov     r9d, 0D7h
0x14003a16f  mov     [rsp+88h+var_60], eax
0x14003a173  mov     r8d, 5
0x14003a179  mov     dl, r14b
0x14003a17c  mov     [rsp+88h+var_68], r15
0x14003a181  mov     rcx, r13
0x14003a184  call    WPP_RECORDER_SF_d
0x14003a189  mov     edx, 8Bh
0x14003a18e  jmp     loc_140039EA2
0x14003a193  mov     rcx, [rsp+88h+arg_20]
0x14003a19b  test    rcx, rcx
0x14003a19e  jz      short loc_14003A129
0x14003a1a0  mov     [rcx], ax
0x14003a1a3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
  ... truncated ...
```
