# HUBDESC_ValidateMsOs20DescriptorSet

- ea: `0x14003e298`
- end: `0x14003e5e7`
- name: `HUBDESC_ValidateMsOs20DescriptorSet`
- size: `847`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140025590`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x140035764`
- `0x14003e298`
- `0x14003e5f0`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_ValidateMsOs20DescriptorSet(__int64 a1, __int64 a2)
{
  int v2; // r8d
  __int64 v3; // rsi
  __int64 v4; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned __int16 *v9; // rcx
  unsigned __int64 v10; // r15
  unsigned __int16 v11; // ax
  char v12; // r14
  unsigned int v13; // r13d
  int v14; // edx
  int v15; // r9d
  __int64 v17; // [rsp+28h] [rbp-40h]
  int v18; // [rsp+28h] [rbp-40h]
  unsigned __int16 *v19; // [rsp+78h] [rbp+10h] BYREF

  v2 = *(unsigned __int16 *)(a2 + 20);
  v3 = a2;
  v4 = *(unsigned int *)(a2 + 12);
  if ( (_DWORD)v4 != v2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = *(_QWORD *)(a2 + 96);
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_dD(v6, a2, 5, 368, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v4, v2);
    }
    v7 = 188;
    goto LABEL_44;
  }
  if ( (unsigned int)v4 < 0xA )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = *(_QWORD *)(a2 + 96);
      v18 = *(_DWORD *)(a2 + 12);
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(v8, a2, 5, 369, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v18);
    }
    v7 = 189;
    goto LABEL_44;
  }
  v9 = *(unsigned __int16 **)(a2 + 24);
  v10 = (unsigned __int64)v9 + v4;
  if ( v9 > (unsigned __int16 *)((char *)v9 + v4)
    || (unsigned __int64)(v9 + 2) > v10
    || (a2 = *v9, (unsigned int)a2 < 4)
    || (unsigned __int64)v9 + a2 > v10 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_43:
      v7 = 194;
      goto LABEL_44;
    }
    v15 = 370;
LABEL_42:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(v3 + 96), a2, 5, v15, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    goto LABEL_43;
  }
  if ( (_WORD)a2 != 10 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(v3 + 96), a2, 5, 371, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *v9);
    }
    v7 = 190;
    goto LABEL_44;
  }
  v11 = v9[4];
  if ( (_WORD)v2 != v11 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(v3 + 96),
        a2,
        5,
        372,
        (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
        v2,
        v11);
    }
    v7 = 191;
    goto LABEL_44;
  }
  LODWORD(a2) = *((_DWORD *)v9 + 1);
  if ( (unsigned int)a2 <= *(_DWORD *)(v3 + 16) )
  {
    v12 = 1;
    v19 = v9;
    while ( 1 )
    {
      v13 = v9[1];
      if ( v13 >= 9 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v17) = v9[1];
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(v3 + 96),
            a2,
            5,
            375,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            v17);
        }
      }
      else
      {
        if ( !((unsigned __int8 (__fastcall *)(__int64, __int64, unsigned __int16 *, unsigned __int64))*(&MsOs20DispatchTable + 2 * v9[1]))(
                a1,
                v3,
                v9,
                v10) )
          goto LABEL_45;
        if ( v13 - 1 > 1 && (*(_BYTE *)v3 & 0x18) != 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v14) = 2;
            WPP_RECORDER_SF_(
              *(_QWORD *)(v3 + 96),
              v14,
              5,
              374,
              (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
          }
          v7 = 193;
          goto LABEL_44;
        }
      }
      if ( !(unsigned __int8)HUBDESC_GetNextMsOs20Descriptor(v10, &v19) )
        break;
      v9 = v19;
      if ( !v19 )
        return v12;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_43;
    v15 = 376;
    goto LABEL_42;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_dD(
      *(_QWORD *)(v3 + 96),
      a2,
      5,
      373,
      (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
      *((_DWORD *)v9 + 1),
      *(_DWORD *)(v3 + 16));
  }
  v7 = 192;
LABEL_44:
  (*(void (__fastcall **)(_QWORD, __int64))(a1 + 24))(*(_QWORD *)(a1 + 40), v7);
LABEL_45:
  v12 = 0;
  *(_DWORD *)v3 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(v3 + 96), v14, 5, 377, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v12;
}

```

## disassembly

```asm
0x14003e298  mov     r11, rsp
0x14003e29b  mov     [r11+8], rbx
0x14003e29f  mov     [r11+18h], rbp
0x14003e2a3  push    rsi
0x14003e2a4  push    rdi
0x14003e2a5  push    r13
0x14003e2a7  push    r14
0x14003e2a9  push    r15
0x14003e2ab  sub     rsp, 40h
0x14003e2af  movzx   r8d, word ptr [rdx+14h]
0x14003e2b4  mov     rsi, rdx
0x14003e2b7  mov     eax, [rdx+0Ch]
0x14003e2ba  mov     rbp, rcx
0x14003e2bd  cmp     eax, r8d
0x14003e2c0  jz      short loc_14003E306
0x14003e2c2  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e2c9  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003e2d0  lea     rdi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003e2d7  jz      short loc_14003E2FC
0x14003e2d9  mov     rcx, [rsi+60h]
0x14003e2dd  mov     r9d, 170h
0x14003e2e3  mov     [r11-38h], r8d
0x14003e2e7  mov     dl, 2
0x14003e2e9  mov     dword ptr [rsp+68h+var_40], eax
0x14003e2ed  mov     r8d, 5
0x14003e2f3  mov     [r11-48h], rdi
0x14003e2f7  call    WPP_RECORDER_SF_dD
0x14003e2fc  mov     edx, 0BCh
0x14003e301  jmp     loc_14003E58F
0x14003e306  mov     r10d, 0Ah
0x14003e30c  cmp     eax, r10d
0x14003e30f  jnb     short loc_14003E350
0x14003e311  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e318  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003e31f  lea     rdi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003e326  jz      short loc_14003E346
0x14003e328  mov     rcx, [rsi+60h]
0x14003e32c  lea     r8d, [r10-5]
0x14003e330  mov     dword ptr [rsp+68h+var_40], eax
0x14003e334  mov     r9d, 171h
0x14003e33a  mov     dl, 2
0x14003e33c  mov     [rsp+68h+var_48], rdi
0x14003e341  call    WPP_RECORDER_SF_d
0x14003e346  mov     edx, 0BDh
0x14003e34b  jmp     loc_14003E58F
0x14003e350  mov     rcx, [rdx+18h]
0x14003e354  lea     r15, [rcx+rax]
0x14003e358  cmp     rcx, r15
0x14003e35b  ja      loc_14003E557
0x14003e361  lea     r9, [rcx+4]
0x14003e365  cmp     r9, r15
0x14003e368  ja      loc_14003E557
0x14003e36e  movzx   edx, word ptr [rcx]
0x14003e371  cmp     edx, 4
0x14003e374  jb      loc_14003E557
0x14003e37a  lea     rax, [rcx+rdx]
0x14003e37e  cmp     rax, r15
0x14003e381  ja      loc_14003E557
0x14003e387  cmp     dx, r10w
0x14003e38b  jz      short loc_14003E3CE
0x14003e38d  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e394  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003e39b  lea     rdi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003e3a2  jz      short loc_14003E3C4
0x14003e3a4  mov     rcx, [rsi+60h]
0x14003e3a8  mov     r9d, 173h
0x14003e3ae  mov     dword ptr [rsp+68h+var_40], edx
0x14003e3b2  mov     r8d, 5
0x14003e3b8  mov     dl, 2
0x14003e3ba  mov     [rsp+68h+var_48], rdi
0x14003e3bf  call    WPP_RECORDER_SF_d
0x14003e3c4  mov     edx, 0BEh
0x14003e3c9  jmp     loc_14003E58F
0x14003e3ce  movzx   eax, word ptr [rcx+8]
0x14003e3d2  cmp     r8w, ax
0x14003e3d6  jz      short loc_14003E41E
0x14003e3d8  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e3df  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003e3e6  lea     rdi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003e3ed  jz      short loc_14003E414
0x14003e3ef  mov     rcx, [rsi+60h]
0x14003e3f3  mov     r9d, 174h
0x14003e3f9  mov     [rsp+68h+var_38], eax
0x14003e3fd  mov     dl, 2
0x14003e3ff  mov     dword ptr [rsp+68h+var_40], r8d
0x14003e404  mov     r8d, 5
0x14003e40a  mov     [rsp+68h+var_48], rdi
0x14003e40f  call    WPP_RECORDER_SF_dD
0x14003e414  mov     edx, 0BFh
0x14003e419  jmp     loc_14003E58F
0x14003e41e  mov     eax, [rsi+10h]
0x14003e421  mov     edx, [r9]
0x14003e424  cmp     edx, eax
0x14003e426  jbe     short loc_14003E46D
0x14003e428  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e42f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003e436  lea     rdi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003e43d  jz      short loc_14003E463
0x14003e43f  mov     rcx, [rsi+60h]
0x14003e443  mov     r9d, 175h
0x14003e449  mov     [rsp+68h+var_38], eax
0x14003e44d  mov     r8d, 5
0x14003e453  mov     dword ptr [rsp+68h+var_40], edx
0x14003e457  mov     dl, 2
0x14003e459  mov     [rsp+68h+var_48], rdi
0x14003e45e  call    WPP_RECORDER_SF_dD
0x14003e463  mov     edx, 0C0h
0x14003e468  jmp     loc_14003E58F
0x14003e46d  mov     r14d, 1
0x14003e473  mov     [rsp+68h+arg_8], rcx
0x14003e478  lea     rbx, WPP_RECORDER_INITIALIZED
0x14003e47f  lea     rdi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003e486  movzx   r13d, word ptr [rcx+2]
0x14003e48b  cmp     r13d, 9
0x14003e48f  jnb     short loc_14003E4F8
0x14003e491  lea     rdx, MsOs20DispatchTable
0x14003e498  mov     r8, rcx
0x14003e49b  mov     eax, r13d
0x14003e49e  mov     r9, r15
0x14003e4a1  add     rax, rax
0x14003e4a4  mov     rcx, rbp
0x14003e4a7  mov     rax, (MsOs20DispatchTable - 14006B000h)[rdx+rax*8]
0x14003e4ab  mov     rdx, rsi
0x14003e4ae  call    _guard_dispatch_icall
0x14003e4b3  test    al, al
0x14003e4b5  jz      loc_14003E59C
0x14003e4bb  lea     eax, [r13-1]
0x14003e4bf  cmp     eax, r14d
0x14003e4c2  jbe     short loc_14003E522
0x14003e4c4  test    byte ptr [rsi], 18h
0x14003e4c7  jz      short loc_14003E522
0x14003e4c9  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14003e4d0  jz      short loc_14003E4EE
0x14003e4d2  mov     rcx, [rsi+60h]
0x14003e4d6  mov     r9d, 176h
0x14003e4dc  mov     r8d, 5
0x14003e4e2  mov     [rsp+68h+var_48], rdi
0x14003e4e7  mov     dl, 2
0x14003e4e9  call    WPP_RECORDER_SF_
0x14003e4ee  mov     edx, 0C1h
0x14003e4f3  jmp     loc_14003E58F
0x14003e4f8  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14003e4ff  jz      short loc_14003E522
0x14003e501  mov     rcx, [rsi+60h]
0x14003e505  mov     r9d, 177h
0x14003e50b  mov     dword ptr [rsp+68h+var_40], r13d
0x14003e510  mov     r8d, 5
0x14003e516  mov     dl, 2
0x14003e518  mov     [rsp+68h+var_48], rdi
0x14003e51d  call    WPP_RECORDER_SF_d
0x14003e522  lea     rdx, [rsp+68h+arg_8]
0x14003e527  mov     rcx, r15
0x14003e52a  call    HUBDESC_GetNextMsOs20Descriptor
0x14003e52f  test    al, al
0x14003e531  jz      short loc_14003E546
0x14003e533  mov     rcx, [rsp+68h+arg_8]
0x14003e538  test    rcx, rcx
0x14003e53b  jnz     loc_14003E486
0x14003e541  jmp     loc_14003E5CA
0x14003e546  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14003e54d  jz      short loc_14003E58A
0x14003e54f  mov     r9d, 178h
0x14003e555  jmp     short loc_14003E574
0x14003e557  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003e55e  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14003e565  lea     rdi, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003e56c  jz      short loc_14003E58A
0x14003e56e  mov     r9d, 172h
0x14003e574  mov     rcx, [rsi+60h]
0x14003e578  mov     r8d, 5
0x14003e57e  mov     dl, 2
0x14003e580  mov     [rsp+68h+var_48], rdi
0x14003e585  call    WPP_RECORDER_SF_
0x14003e58a  mov     edx, 0C2h
0x14003e58f  mov     rcx, [rbp+28h]
0x14003e593  mov     rax, [rbp+18h]
0x14003e597  call    _guard_dispatch_icall
0x14003e59c  xor     r14b, r14b
0x14003e59f  mov     dword ptr [rsi], 0
0x14003e5a5  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14003e5ac  jz      short loc_14003E5CA
0x14003e5ae  mov     rcx, [rsi+60h]
0x14003e5b2  mov     r9d, 179h
0x14003e5b8  mov     r8d, 5
0x14003e5be  mov     [rsp+68h+var_48], rdi
0x14003e5c3  mov     dl, 2
0x14003e5c5  call    WPP_RECORDER_SF_
0x14003e5ca  lea     r11, [rsp+68h+var_28]
0x14003e5cf  mov     al, r14b
0x14003e5d2  mov     rbx, [r11+30h]
0x14003e5d6  mov     rbp, [r11+40h]
0x14003e5da  mov     rsp, r11
0x14003e5dd  pop     r15
0x14003e5df  pop     r14
0x14003e5e1  pop     r13
0x14003e5e3  pop     rdi
0x14003e5e4  pop     rsi
0x14003e5e5  retn
```
