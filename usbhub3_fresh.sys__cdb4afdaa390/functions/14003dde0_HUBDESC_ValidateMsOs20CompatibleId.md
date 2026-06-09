# HUBDESC_ValidateMsOs20CompatibleId

- ea: `0x14003dde0`
- end: `0x14003dfa7`
- name: `HUBDESC_ValidateMsOs20CompatibleId`
- size: `455`
- prototype: `char __fastcall(__int64, unsigned __int64, _WORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14003dde0`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_ValidateMsOs20CompatibleId(__int64 a1, unsigned __int64 a2, _WORD *a3)
{
  unsigned __int64 v4; // rdi
  char v6; // bl
  int v7; // r9d
  __int64 v8; // rdx
  char v10; // r8
  __int64 v11; // r9
  int v12; // ecx
  char v13; // r8
  int v14; // r9d
  int v15; // [rsp+28h] [rbp-40h]

  v4 = a2;
  v6 = 1;
  if ( (*(_BYTE *)a2 & 0x20) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(v4 + 96), a2, 5, 338, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(a1 + 24))(*(_QWORD *)(a1 + 40), 166);
    v6 = 0;
  }
  if ( *a3 != 20 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = 339;
      v15 = (unsigned __int16)*a3;
      goto LABEL_8;
    }
    goto LABEL_9;
  }
  v10 = 0;
  v11 = 0x87FFFFFE03FFLL;
  a2 = 0;
  while ( 1 )
  {
    v12 = *((unsigned __int8 *)a3 + a2 + 4);
    if ( !(_BYTE)v12 )
    {
      v10 = 1;
      goto LABEL_23;
    }
    if ( v10 == 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v14 = 340;
        goto LABEL_33;
      }
LABEL_34:
      v8 = 168;
      goto LABEL_10;
    }
    if ( (unsigned __int8)(v12 - 48) > 0x2Fu || !_bittest64(&v11, (unsigned __int8)(v12 - 48)) )
      break;
LABEL_23:
    a2 = (unsigned int)(a2 + 1);
    if ( (unsigned int)a2 >= 8 )
    {
      v13 = 0;
      a2 = 0;
      while ( 1 )
      {
        v12 = *((unsigned __int8 *)a3 + a2 + 12);
        if ( (_BYTE)v12 )
        {
          if ( v13 == 1 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_34;
            v14 = 342;
LABEL_33:
            LOBYTE(a2) = 2;
            WPP_RECORDER_SF_(*(_QWORD *)(v4 + 96), a2, 5, v14, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
            goto LABEL_34;
          }
          if ( (unsigned __int8)(v12 - 48) > 0x2Fu || !_bittest64(&v11, (unsigned __int8)(v12 - 48)) )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_9;
            v7 = 343;
            goto LABEL_21;
          }
        }
        else
        {
          v13 = 1;
        }
        a2 = (unsigned int)(a2 + 1);
        if ( (unsigned int)a2 >= 8 )
        {
          if ( v6 != 1 )
            goto LABEL_11;
          *(_DWORD *)v4 |= 0x20u;
          *(_QWORD *)(v4 + 32) = a3;
          return v6;
        }
      }
    }
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_9;
  v7 = 341;
LABEL_21:
  v15 = v12;
LABEL_8:
  LOBYTE(a2) = 2;
  WPP_RECORDER_SF_d(*(_QWORD *)(v4 + 96), a2, 5, v7, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v15);
LABEL_9:
  v8 = 167;
LABEL_10:
  (*(void (__fastcall **)(_QWORD, __int64))(a1 + 24))(*(_QWORD *)(a1 + 40), v8);
  v6 = 0;
LABEL_11:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(v4 + 96), a2, 5, 344, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x14003dde0  push    rbx
0x14003dde2  push    rbp
0x14003dde3  push    rsi
0x14003dde4  push    rdi
0x14003dde5  push    r12
0x14003dde7  push    r14
0x14003dde9  push    r15
0x14003ddeb  sub     rsp, 30h
0x14003ddef  test    byte ptr [rdx], 20h
0x14003ddf2  lea     rbp, WPP_RECORDER_INITIALIZED
0x14003ddf9  mov     r14, r8
0x14003ddfc  lea     r12, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003de03  mov     rdi, rdx
0x14003de06  mov     rsi, rcx
0x14003de09  mov     bl, 1
0x14003de0b  mov     r15d, 5
0x14003de11  jz      short loc_14003DE49
0x14003de13  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003de1a  jz      short loc_14003DE35
0x14003de1c  mov     rcx, [rdi+60h]
0x14003de20  mov     r9d, 152h
0x14003de26  mov     r8d, r15d
0x14003de29  mov     [rsp+68h+var_48], r12
0x14003de2e  mov     dl, 2
0x14003de30  call    WPP_RECORDER_SF_
0x14003de35  mov     rax, [rsi+18h]
0x14003de39  mov     edx, 0A6h
0x14003de3e  mov     rcx, [rsi+28h]
0x14003de42  call    _guard_dispatch_icall
0x14003de47  xor     bl, bl
0x14003de49  movzx   eax, word ptr [r14]
0x14003de4d  cmp     eax, 14h
0x14003de50  jz      short loc_14003DEC0
0x14003de52  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003de59  jz      short loc_14003DE78
0x14003de5b  mov     r9d, 153h
0x14003de61  mov     [rsp+68h+var_40], eax
0x14003de65  mov     rcx, [rdi+60h]
0x14003de69  mov     r8d, r15d
0x14003de6c  mov     dl, 2
0x14003de6e  mov     [rsp+68h+var_48], r12
0x14003de73  call    WPP_RECORDER_SF_d
0x14003de78  mov     edx, 0A7h
0x14003de7d  mov     rax, [rsi+18h]
0x14003de81  mov     rcx, [rsi+28h]
0x14003de85  call    _guard_dispatch_icall
0x14003de8a  xor     bl, bl
0x14003de8c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003de93  jz      short loc_14003DEAE
0x14003de95  mov     rcx, [rdi+60h]
0x14003de99  mov     r9d, 158h
0x14003de9f  mov     r8d, r15d
0x14003dea2  mov     [rsp+68h+var_48], r12
0x14003dea7  mov     dl, 2
0x14003dea9  call    WPP_RECORDER_SF_
0x14003deae  mov     al, bl
0x14003deb0  add     rsp, 30h
0x14003deb4  pop     r15
0x14003deb6  pop     r14
0x14003deb8  pop     r12
0x14003deba  pop     rdi
0x14003debb  pop     rsi
0x14003debc  pop     rbp
0x14003debd  pop     rbx
0x14003debe  retn
0x14003dec0  xor     r8b, r8b
0x14003dec3  mov     r9, 87FFFFFE03FFh
0x14003decd  xor     edx, edx
0x14003decf  movzx   ecx, byte ptr [rdx+r14+4]
0x14003ded5  test    cl, cl
0x14003ded7  jz      short loc_14003DF07
0x14003ded9  cmp     r8b, 1
0x14003dedd  jz      short loc_14003DF4B
0x14003dedf  lea     eax, [rcx-30h]
0x14003dee2  cmp     al, 2Fh ; '/'
0x14003dee4  ja      short loc_14003DEEF
0x14003dee6  movzx   eax, al
0x14003dee9  bt      r9, rax
0x14003deed  jb      short loc_14003DF0A
0x14003deef  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003def6  jz      short loc_14003DE78
0x14003def8  mov     r9d, 155h
0x14003defe  mov     [rsp+68h+var_40], ecx
0x14003df02  jmp     loc_14003DE65
0x14003df07  mov     r8b, 1
0x14003df0a  inc     edx
0x14003df0c  cmp     edx, 8
0x14003df0f  jb      short loc_14003DECF
0x14003df11  xor     r8b, r8b
0x14003df14  xor     edx, edx
0x14003df16  movzx   ecx, byte ptr [rdx+r14+0Ch]
0x14003df1c  test    cl, cl
0x14003df1e  jz      short loc_14003DF77
0x14003df20  cmp     r8b, 1
0x14003df24  jz      short loc_14003DF96
0x14003df26  lea     eax, [rcx-30h]
0x14003df29  cmp     al, 2Fh ; '/'
0x14003df2b  ja      short loc_14003DF36
0x14003df2d  movzx   eax, al
0x14003df30  bt      r9, rax
0x14003df34  jb      short loc_14003DF7A
0x14003df36  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003df3d  jz      loc_14003DE78
0x14003df43  mov     r9d, 157h
0x14003df49  jmp     short loc_14003DEFE
0x14003df4b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003df52  jz      short loc_14003DF6D
0x14003df54  mov     r9d, 154h
0x14003df5a  mov     rcx, [rdi+60h]
0x14003df5e  mov     r8d, r15d
0x14003df61  mov     dl, 2
0x14003df63  mov     [rsp+68h+var_48], r12
0x14003df68  call    WPP_RECORDER_SF_
0x14003df6d  mov     edx, 0A8h
0x14003df72  jmp     loc_14003DE7D
0x14003df77  mov     r8b, 1
0x14003df7a  inc     edx
0x14003df7c  cmp     edx, 8
0x14003df7f  jb      short loc_14003DF16
0x14003df81  cmp     bl, 1
0x14003df84  jnz     loc_14003DE8C
0x14003df8a  or      dword ptr [rdi], 20h
0x14003df8d  mov     [rdi+20h], r14
0x14003df91  jmp     loc_14003DEAE
0x14003df96  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003df9d  jz      short loc_14003DF6D
0x14003df9f  mov     r9d, 156h
0x14003dfa5  jmp     short loc_14003DF5A
```
