# Tpm20ResourceMgr::GetSessions(TpmBufferAccessor *,ushort,Tpm20Request *)

- ea: `0x140007d88`
- end: `0x14000809d`
- name: `?GetSessions@Tpm20ResourceMgr@@AEAA_NPEAVTpmBufferAccessor@@GPEAVTpm20Request@@@Z`
- size: `789`
- prototype: `bool __fastcall(Tpm20ResourceMgr *__hidden this, struct TpmBufferAccessor *, unsigned __int16, struct Tpm20Request *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140016afc`

## callees

- `0x140007d88`
- `0x1400080a4`
- `0x140009224`
- `0x140009278`

## pseudocode

```c
bool __fastcall Tpm20ResourceMgr::GetSessions(
        Tpm20ResourceMgr *this,
        struct TpmBufferAccessor *a2,
        __int16 a3,
        struct Tpm20Request *a4)
{
  struct Tpm20Request *v4; // r11
  struct TpmBufferAccessor *v5; // r10
  __int64 v6; // rdx
  int v8; // ebx
  __int64 v9; // rcx
  unsigned __int64 v10; // rsi
  __int64 v11; // r9
  __int64 v12; // r15
  signed int v13; // r8d
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // r13
  unsigned int v18; // r12d
  _QWORD *v19; // r13
  __int64 v20; // rcx
  __int64 v21; // r9
  signed int v22; // r8d
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rcx
  __int64 v27; // r9
  signed int v28; // r8d
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // r14
  __int64 v34; // rdi
  __int64 v35; // rcx
  __int64 v36; // r9
  signed int v37; // r8d
  __int64 v38; // rcx
  __int64 v39; // rax
  int v40; // r8d
  __int64 **v41; // r9
  __int64 *i; // rcx
  unsigned __int8 v43; // al
  Tpm20ResourceMgr *v44; // [rsp+70h] [rbp+8h]
  int v45; // [rsp+80h] [rbp+18h]

  v44 = this;
  v4 = a4;
  v45 = 0;
  v5 = a2;
  if ( a3 == -32767 )
  {
    *((_DWORD *)a4 + 50) = 0;
    LOBYTE(v6) = 1;
  }
  else
  {
    v8 = *(_DWORD *)a2;
    v9 = (unsigned int)(*((_DWORD *)a2 + 4) - *(_DWORD *)a2);
    if ( (int)v9 + 4 < (unsigned int)v9 || (v10 = *((unsigned int *)a2 + 2), v11 = (unsigned int)v9, v9 + 4 > v10) )
    {
LABEL_44:
      LOBYTE(v6) = 0;
    }
    else
    {
      v12 = *(_QWORD *)a2;
      v13 = 0;
      v6 = 1;
      do
      {
        v14 = v13;
        v15 = v11 - v13++;
        *((_BYTE *)&v45 + v14) = *(_BYTE *)(v15 + v12 + 3);
      }
      while ( (unsigned int)v13 < 4 );
      *((_QWORD *)v5 + 2) += 4LL;
      v16 = 0;
      v17 = *((unsigned int *)v4 + 49);
      v18 = v45 + *((_DWORD *)v5 + 4) - v8;
      *((_QWORD *)v4 + 25) = 0;
      v19 = (_QWORD *)((char *)v4 + 8 * v17 + 48);
      while ( 1 )
      {
        v20 = (unsigned int)(*((_DWORD *)v5 + 4) - v8);
        if ( (unsigned int)v20 >= v18 )
          break;
        if ( v16 >= 8 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids, 8);
          }
          goto LABEL_44;
        }
        LODWORD(v44) = 0;
        LOWORD(v45) = 0;
        if ( (int)v20 + 4 < (unsigned int)v20 )
          goto LABEL_34;
        v21 = (unsigned int)v20;
        if ( v20 + 4 > v10 )
          goto LABEL_34;
        v22 = 0;
        do
        {
          v23 = v22;
          v24 = v21 - v22;
          v22 += v6;
          *((_BYTE *)&v44 + v23) = *(_BYTE *)(v24 + v12 + 3);
        }
        while ( (unsigned int)v22 < 4 );
        *((_QWORD *)v5 + 2) += 4LL;
        v25 = *((_QWORD *)v5 + 2);
        v26 = (unsigned int)(v25 - v8);
        if ( (int)v26 + 2 < (unsigned int)v26 )
          goto LABEL_34;
        v27 = (unsigned int)v26;
        if ( v26 + 2 > v10 )
          goto LABEL_34;
        v28 = 0;
        do
        {
          v29 = v28;
          v30 = v27 - v28;
          v28 += v6;
          *((_BYTE *)&v45 + v29) = *(_BYTE *)(v30 + v12 + 1);
        }
        while ( (unsigned int)v28 < 2 );
        *((_QWORD *)v5 + 2) = v25 + 2;
        if ( (unsigned __int16)v45 > (unsigned int)(v10 + v8 - (v25 + 2)) )
          goto LABEL_34;
        v31 = v25 + 2 + (unsigned __int16)v45;
        *((_QWORD *)v5 + 2) = v31;
        v32 = (unsigned int)(v31 - v8);
        if ( (int)v32 + 1 < (unsigned int)v32 )
          goto LABEL_34;
        v33 = (unsigned int)v32;
        if ( v32 + 1 > v10 )
          goto LABEL_34;
        v34 = v31 + 1;
        *((_QWORD *)v5 + 2) = v31 + 1;
        v35 = (unsigned int)(v31 + 1 - v8);
        if ( (int)v35 + 2 < (unsigned int)v35 )
          goto LABEL_34;
        v36 = (unsigned int)v35;
        if ( v35 + 2 > v10 )
          goto LABEL_34;
        v37 = 0;
        do
        {
          v38 = v37;
          v39 = v12 + 1 - v37;
          v37 += v6;
          *((_BYTE *)&v45 + v38) = *(_BYTE *)(v39 + v36);
        }
        while ( (unsigned int)v37 < 2 );
        *((_QWORD *)v5 + 2) = v34 + 2;
        if ( (unsigned __int16)v45 > (unsigned int)(v8 + v10 - (v34 + 2)) )
          goto LABEL_34;
        *((_QWORD *)v5 + 2) = v34 + 2 + (unsigned __int16)v45;
        if ( (unsigned int)Tpm20Info::GetSlotTypeFromHandle(
                             (unsigned int)v44,
                             v6,
                             (unsigned int)v44,
                             *((_QWORD *)v4 + 2)) )
        {
          for ( i = v41[1]; i != (__int64 *)(v41 + 1); i = (__int64 *)*i )
          {
            if ( *((_DWORD *)i + 13) == v40 )
              goto LABEL_29;
          }
LABEL_33:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids, v41, v40);
          }
LABEL_34:
          LOBYTE(v6) = 0;
          return v6;
        }
        i = *v41;
LABEL_29:
        if ( !i )
          goto LABEL_33;
        v43 = *(_BYTE *)(v33 + v12);
        *v19++ = i;
        if ( (v43 & (unsigned __int8)v6) == 0 )
          *((_DWORD *)v4 + 51) |= 1 << *((_BYTE *)v4 + 200);
        *((_DWORD *)v4 + 50) += v6;
        v16 = *((_DWORD *)v4 + 50);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140007d88  mov     rax, rsp
0x140007d8b  mov     [rax+10h], rbx
0x140007d8f  mov     [rax+8], rcx
0x140007d93  push    rbp
0x140007d94  push    rsi
0x140007d95  push    rdi
0x140007d96  push    r12
0x140007d98  push    r13
0x140007d9a  push    r14
0x140007d9c  push    r15
0x140007d9e  sub     rsp, 30h
0x140007da2  xor     r14d, r14d
0x140007da5  mov     r11, r9
0x140007da8  mov     [rax+18h], r14d
0x140007dac  mov     r10, rdx
0x140007daf  mov     eax, 8001h
0x140007db4  cmp     r8w, ax
0x140007db8  jnz     short loc_140007DDD
0x140007dba  mov     [r9+0C8h], r14d
0x140007dc1  lea     edx, [r14+1]
0x140007dc5  mov     rbx, [rsp+68h+arg_8]
0x140007dca  mov     al, dl
0x140007dcc  add     rsp, 30h
0x140007dd0  pop     r15
0x140007dd2  pop     r14
0x140007dd4  pop     r13
0x140007dd6  pop     r12
0x140007dd8  pop     rdi
0x140007dd9  pop     rsi
0x140007dda  pop     rbp
0x140007ddb  retn
0x140007ddd  mov     ecx, [rdx+10h]
0x140007de0  mov     ebx, [rdx]
0x140007de2  sub     ecx, ebx
0x140007de4  lea     eax, [rcx+4]
0x140007de7  cmp     eax, ecx
0x140007de9  jb      loc_140008095
0x140007def  mov     esi, [rdx+8]
0x140007df2  lea     rax, [rcx+4]
0x140007df6  mov     r9d, ecx
0x140007df9  cmp     rax, rsi
0x140007dfc  ja      loc_140008095
0x140007e02  mov     r15, [rdx]
0x140007e05  mov     r8d, r14d
0x140007e08  mov     edx, 1
0x140007e0d  movsxd  rcx, r8d
0x140007e10  mov     rax, r9
0x140007e13  sub     rax, rcx
0x140007e16  add     r8d, edx
0x140007e19  mov     al, [rax+r15+3]
0x140007e1e  mov     byte ptr [rsp+rcx+68h+arg_10], al
0x140007e25  cmp     r8d, 4
0x140007e29  jb      short loc_140007E0D
0x140007e2b  add     qword ptr [r10+10h], 4
0x140007e30  mov     r12d, [r10+10h]
0x140007e34  mov     eax, r14d
0x140007e37  mov     r13d, [r11+0C4h]
0x140007e3e  sub     r12d, ebx
0x140007e41  add     r12d, [rsp+68h+arg_10]
0x140007e49  add     r13, 6
0x140007e4d  mov     [r11+0C8h], r14
0x140007e54  lea     r13, [r11+r13*8]
0x140007e58  mov     ecx, [r10+10h]
0x140007e5c  sub     ecx, ebx
0x140007e5e  cmp     ecx, r12d
0x140007e61  jnb     loc_140007DC5
0x140007e67  cmp     eax, 8
0x140007e6a  jnb     loc_140008062
0x140007e70  lea     eax, [rcx+4]
0x140007e73  mov     dword ptr [rsp+68h+arg_0], r14d
0x140007e78  mov     word ptr [rsp+68h+arg_10], r14w
0x140007e81  cmp     eax, ecx
0x140007e83  jb      loc_140008021
0x140007e89  lea     rax, [rcx+4]
0x140007e8d  mov     r9d, ecx
0x140007e90  cmp     rax, rsi
0x140007e93  ja      loc_140008021
0x140007e99  mov     r8d, r14d
0x140007e9c  movsxd  rcx, r8d
0x140007e9f  mov     rax, r9
0x140007ea2  sub     rax, rcx
0x140007ea5  add     r8d, edx
0x140007ea8  mov     al, [rax+r15+3]
0x140007ead  mov     byte ptr [rsp+rcx+68h+arg_0], al
0x140007eb1  cmp     r8d, 4
0x140007eb5  jb      short loc_140007E9C
0x140007eb7  add     qword ptr [r10+10h], 4
0x140007ebc  mov     rdi, [r10+10h]
0x140007ec0  mov     ecx, edi
0x140007ec2  sub     ecx, ebx
0x140007ec4  lea     eax, [rcx+2]
0x140007ec7  cmp     eax, ecx
0x140007ec9  jb      loc_140008021
0x140007ecf  lea     rax, [rcx+2]
0x140007ed3  mov     r9d, ecx
0x140007ed6  cmp     rax, rsi
0x140007ed9  ja      loc_140008021
0x140007edf  mov     r8d, r14d
0x140007ee2  movsxd  rcx, r8d
0x140007ee5  mov     rax, r9
0x140007ee8  sub     rax, rcx
0x140007eeb  add     r8d, edx
0x140007eee  mov     al, [rax+r15+1]
0x140007ef3  mov     byte ptr [rsp+rcx+68h+arg_10], al
0x140007efa  cmp     r8d, 2
0x140007efe  jb      short loc_140007EE2
0x140007f00  lea     rcx, [rdi+2]
0x140007f04  mov     [r10+10h], rcx
0x140007f08  movzx   r8d, word ptr [rsp+68h+arg_10]
0x140007f11  mov     eax, ebx
0x140007f13  sub     eax, ecx
0x140007f15  add     eax, esi
0x140007f17  cmp     r8d, eax
0x140007f1a  ja      loc_140008021
0x140007f20  add     r8, rcx
0x140007f23  mov     [r10+10h], r8
0x140007f27  mov     ecx, r8d
0x140007f2a  sub     ecx, ebx
0x140007f2c  lea     eax, [rcx+1]
0x140007f2f  cmp     eax, ecx
0x140007f31  jb      loc_140008021
0x140007f37  lea     rax, [rcx+1]
0x140007f3b  mov     r14d, ecx
0x140007f3e  cmp     rax, rsi
0x140007f41  ja      loc_140008021
0x140007f47  lea     rdi, [r8+1]
0x140007f4b  mov     [r10+10h], rdi
0x140007f4f  mov     ecx, edi
0x140007f51  sub     ecx, ebx
0x140007f53  lea     eax, [rcx+2]
0x140007f56  cmp     eax, ecx
0x140007f58  jb      loc_140008021
0x140007f5e  lea     rax, [rcx+2]
0x140007f62  mov     r9d, ecx
0x140007f65  cmp     rax, rsi
0x140007f68  ja      loc_140008021
0x140007f6e  xor     r8d, r8d
0x140007f71  movsxd  rcx, r8d
0x140007f74  lea     rax, [r15+1]
0x140007f78  sub     rax, rcx
0x140007f7b  add     r8d, edx
0x140007f7e  mov     al, [rax+r9]
0x140007f82  mov     byte ptr [rsp+rcx+68h+arg_10], al
0x140007f89  cmp     r8d, 2
0x140007f8d  jb      short loc_140007F71
0x140007f8f  lea     rcx, [rdi+2]
0x140007f93  mov     [r10+10h], rcx
0x140007f97  movzx   r8d, word ptr [rsp+68h+arg_10]
0x140007fa0  mov     eax, esi
0x140007fa2  sub     eax, ecx
0x140007fa4  add     eax, ebx
0x140007fa6  cmp     r8d, eax
0x140007fa9  ja      short loc_140008021
0x140007fab  lea     rax, [rcx+r8]
0x140007faf  mov     [r10+10h], rax
0x140007fb3  mov     r8d, dword ptr [rsp+68h+arg_0]
0x140007fb8  mov     ecx, r8d
0x140007fbb  mov     r9, [r11+10h]
0x140007fbf  call    ?GetSlotTypeFromHandle@Tpm20Info@@SA?AW4_TPM20_SLOT_TYPE@@T_TPM20_HANDLE@@@Z; Tpm20Info::GetSlotTypeFromHandle(_TPM20_HANDLE)
0x140007fc4  test    eax, eax
0x140007fc6  jnz     short loc_140008028
0x140007fc8  mov     rcx, [r9]
0x140007fcb  test    rcx, rcx
0x140007fce  jz      short loc_14000800E
0x140007fd0  mov     al, [r14+r15]
0x140007fd4  xor     r14d, r14d
0x140007fd7  mov     [r13+0], rcx
0x140007fdb  add     r13, 8
0x140007fdf  test    dl, al
0x140007fe1  jnz     short loc_140007FFB
0x140007fe3  mov     ecx, [r11+0CCh]
0x140007fea  mov     eax, [r11+0C8h]
0x140007ff1  bts     ecx, eax
0x140007ff4  mov     [r11+0CCh], ecx
0x140007ffb  add     [r11+0C8h], edx
0x140008002  mov     eax, [r11+0C8h]
0x140008009  jmp     loc_140007E58
0x14000800e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008015  lea     rax, WPP_GLOBAL_Control
0x14000801c  cmp     rcx, rax
0x14000801f  jnz     short loc_14000803F
0x140008021  xor     dl, dl
0x140008023  jmp     loc_140007DC5
0x140008028  lea     rax, [r9+8]
0x14000802c  mov     rcx, [rax]
0x14000802f  cmp     rcx, rax
0x140008032  jz      short loc_14000800E
0x140008034  cmp     [rcx+34h], r8d
0x140008038  jz      short loc_140007FCB
0x14000803a  mov     rcx, [rcx]
0x14000803d  jmp     short loc_14000802F
0x14000803f  mov     eax, [rcx+2Ch]
0x140008042  test    al, 2
0x140008044  jz      short loc_140008021
0x140008046  mov     rcx, [rcx+18h]
0x14000804a  mov     edx, 21h ; '!'
0x14000804f  mov     [rsp+68h+var_48], r8d
0x140008054  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x14000805b  call    WPP_SF_qD
0x140008060  jmp     short loc_140008021
0x140008062  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008069  lea     rax, WPP_GLOBAL_Control
0x140008070  cmp     rcx, rax
0x140008073  jz      short loc_140008095
0x140008075  mov     eax, [rcx+2Ch]
0x140008078  test    al, 2
0x14000807a  jz      short loc_140008095
0x14000807c  mov     rcx, [rcx+18h]
0x140008080  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x140008087  mov     edx, 20h ; ' '
0x14000808c  lea     r9d, [rdx-18h]
0x140008090  call    WPP_SF_d
0x140008095  mov     dl, r14b
0x140008098  jmp     loc_140007DC5
```
