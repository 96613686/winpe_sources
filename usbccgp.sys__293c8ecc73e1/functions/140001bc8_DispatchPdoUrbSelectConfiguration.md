# DispatchPdoUrbSelectConfiguration

- ea: `0x140001bc8`
- end: `0x1400021f4`
- name: `DispatchPdoUrbSelectConfiguration`
- size: `1580`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140002ad0`

## callees

- `0x140001008`
- `0x140001220`
- `0x140001314`
- `0x1400019d8`
- `0x140001bc8`
- `0x140003388`
- `0x1400049c0`
- `0x1400083c8`
- `0x1400088b4`
- `0x140009450`
- `0x14000b4bc`
- `0x14000ba3c`
- `0x14000c4d0`
- `0x140014e00`

## pseudocode

```c
__int64 __fastcall DispatchPdoUrbSelectConfiguration(__int64 a1, IRP *a2)
{
  __int64 v3; // r13
  _IO_SECURITY_CONTEXT *SecurityContext; // r15
  __int64 SecurityQos_low; // rcx
  __int64 v6; // r8
  unsigned int *p_DesiredAccess; // rsi
  int v8; // ebx
  IRP *v9; // rcx
  __int64 v10; // r8
  __int64 i; // rcx
  _QWORD *v12; // r11
  int v13; // r9d
  __int64 v14; // rax
  char v15; // cl
  int v16; // r8d
  unsigned int v17; // ecx
  __int64 j; // r14
  __int64 v19; // rcx
  __int64 v20; // rdx
  unsigned __int16 v21; // bx
  unsigned __int16 *v22; // rdx
  __int16 v23; // ax
  char v25; // al
  int v26; // r9d
  __int16 v27; // cx
  int v28; // r9d
  unsigned int *v29; // r14
  __int64 v30; // r14
  unsigned int v31; // r13d
  unsigned int v32; // r15d
  __int64 v33; // rdx
  unsigned int v34; // eax
  int v35; // [rsp+20h] [rbp-A8h]
  char v36; // [rsp+30h] [rbp-98h]
  _QWORD *v37; // [rsp+50h] [rbp-78h]
  __int64 v38; // [rsp+58h] [rbp-70h]
  _IO_SECURITY_CONTEXT *v39; // [rsp+60h] [rbp-68h]
  __int64 v40; // [rsp+68h] [rbp-60h]
  IRP *v41; // [rsp+70h] [rbp-58h]
  __int64 v42; // [rsp+78h] [rbp-50h]
  int v43; // [rsp+D0h] [rbp+8h] BYREF
  IRP *v44; // [rsp+D8h] [rbp+10h]
  unsigned int v45; // [rsp+E0h] [rbp+18h]
  int v46; // [rsp+E8h] [rbp+20h]

  v44 = a2;
  v3 = *(_QWORD *)(a1 + 232);
  v40 = v3;
  SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  v39 = SecurityContext;
  if ( !SecurityContext[1].SecurityQos )
  {
    v8 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_q(
        *(_QWORD *)(v3 + 1368),
        (_DWORD)a2,
        1,
        15,
        (__int64)WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids,
        *(_QWORD *)(a1 + 224));
    }
    goto LABEL_26;
  }
  SecurityQos_low = LOWORD(SecurityContext->SecurityQos);
  if ( (unsigned int)SecurityQos_low < 0x40 )
  {
    v8 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        *(_QWORD *)(v3 + 1368),
        (_DWORD)a2,
        8,
        16,
        (__int64)WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids,
        *(_QWORD *)(a1 + 224),
        SecurityQos_low);
      goto LABEL_49;
    }
  }
  else
  {
    v6 = *(_QWORD *)(a1 + 240);
    p_DesiredAccess = &SecurityContext[1].DesiredAccess;
    v8 = 0;
    v42 = v6;
    v9 = (IRP *)((char *)SecurityContext + SecurityQos_low);
    v45 = 0;
    v41 = v9;
    v46 = 0;
    while ( 2 )
    {
      if ( p_DesiredAccess >= (unsigned int *)v9 )
        goto LABEL_25;
      a2 = (IRP *)*(unsigned __int16 *)p_DesiredAccess;
      if ( (unsigned __int16)a2 >= 0x18u && (char *)a2 + (unsigned __int64)p_DesiredAccess <= (char *)v9 )
      {
        v10 = *(_QWORD *)(v6 + 8);
        if ( v10 )
        {
          for ( i = 0; ; i = (unsigned int)(i + 1) )
          {
            if ( (unsigned int)i >= *(_DWORD *)(a1 + 12) )
            {
              v8 = -1073741811;
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_31;
              v28 = 18;
              goto LABEL_48;
            }
            v12 = *(_QWORD **)(v10 + 8 * i);
            v13 = *((unsigned __int8 *)p_DesiredAccess + 2);
            v37 = v12;
            v14 = v12[1];
            if ( *(_BYTE *)(v14 + 2) == (_BYTE)v13 )
              break;
          }
          v15 = *((_BYTE *)p_DesiredAccess + 3);
          v16 = *(unsigned __int8 *)(v14 + 3);
          if ( (_BYTE)v16 != v15 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_DDD(*(_QWORD *)(v3 + 1368), (_DWORD)a2, v16, v13, v35, v13, v16, v15);
            v21 = 24 * *((_WORD *)p_DesiredAccess + 8) + 56;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v25 = *((_BYTE *)p_DesiredAccess + 2);
              v26 = 20;
              LOBYTE(v27) = *((_BYTE *)p_DesiredAccess + 3);
              LOBYTE(a2) = 4;
LABEL_41:
              WPP_RECORDER_SF_qqdd(
                *(_QWORD *)(v3 + 1368),
                (_DWORD)a2,
                v16,
                v26,
                v35,
                *(_QWORD *)(a1 + 224),
                (char)SecurityContext,
                v27,
                v25);
            }
            goto LABEL_19;
          }
          v45 = *(_DWORD *)(v14 + 16);
          v17 = 24 * (v45 + 1);
          if ( (unsigned int)a2 >= v17 )
          {
            for ( j = 0; ; j = (unsigned int)(j + 1) )
            {
              if ( (unsigned int)j >= v45 )
              {
                v22 = (unsigned __int16 *)v12[1];
                v23 = *v22;
                if ( *(_WORD *)p_DesiredAccess >= *v22 )
                {
                  memmove(p_DesiredAccess, v22, *v22);
                  goto LABEL_21;
                }
                v8 = -1073741811;
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  goto LABEL_31;
                LOBYTE(v22) = 2;
                WPP_RECORDER_SF_qDD(
                  *(_QWORD *)(v3 + 1368),
                  (_DWORD)v22,
                  8,
                  25,
                  (__int64)WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids,
                  *(_QWORD *)(a1 + 224),
                  *(_WORD *)p_DesiredAccess,
                  v23);
                goto LABEL_49;
              }
              v19 = 3 * j;
              v38 = 3 * j;
              if ( (p_DesiredAccess[6 * j + 11] & 1) != 0 )
                break;
              v20 = *v12;
              v43 = 0;
              if ( (int)GetEndpointPriority(a1, v20, (unsigned int)j, &v43) >= 0 )
              {
                v21 = 24 * v45 + 56;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(a2) = 2;
                  WPP_RECORDER_SF_qqd(
                    *(_QWORD *)(v3 + 1368),
                    (_DWORD)a2,
                    1,
                    24,
                    (__int64)WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids,
                    *(_QWORD *)(a1 + 224),
                    (char)SecurityContext,
                    BYTE2(p_DesiredAccess[6 * j + 6]));
                }
                goto LABEL_19;
              }
              v12 = v37;
              v8 = 0;
            }
            v29 = &p_DesiredAccess[6 * j];
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(a2) = 2;
              WPP_RECORDER_SF_D(
                *(_QWORD *)(v3 + 1368),
                (_DWORD)a2,
                8,
                22,
                (__int64)WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids,
                *((_WORD *)v29 + 12));
              v19 = v38;
            }
            v21 = 24 * v45 + 56;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v25 = BYTE2(p_DesiredAccess[2 * v19 + 6]);
              v26 = 23;
              v27 = *((_WORD *)v29 + 12);
              LOBYTE(a2) = 2;
              goto LABEL_41;
            }
LABEL_19:
            if ( v45 )
            {
              v30 = 0;
              v31 = v45;
              v32 = 0;
              do
              {
                v33 = *v37;
                v43 = 0;
                if ( (int)GetEndpointPriority(a1, v33, v32, &v43) >= 0 )
                {
                  switch ( v43 )
                  {
                    case 1:
                      p_DesiredAccess[6 * v30 + 11] |= 0x10u;
                      break;
                    case 2:
                      p_DesiredAccess[6 * v30 + 11] |= 0x20u;
                      break;
                    case 3:
                      p_DesiredAccess[6 * v30 + 11] |= 0x30u;
                      break;
                  }
                }
                ++v32;
                ++v30;
              }
              while ( v32 < v31 );
              SecurityContext = v39;
              v3 = v40;
            }
            v8 = SendSelectInterfaceUrb(v21, p_DesiredAccess, a1, v37);
LABEL_21:
            LODWORD(a2) = v46 + 1;
            v46 = (int)a2;
            if ( (unsigned int)a2 < *(_DWORD *)(a1 + 12) )
            {
              v9 = v41;
              p_DesiredAccess = (unsigned int *)((char *)p_DesiredAccess + *(unsigned __int16 *)p_DesiredAccess);
              v6 = v42;
              continue;
            }
            goto LABEL_25;
          }
          v8 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_31;
          v36 = (char)a2;
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_qDD(
            *(_QWORD *)(v3 + 1368),
            (_DWORD)a2,
            8,
            21,
            (__int64)WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids,
            *(_QWORD *)(a1 + 224),
            v36,
            v17);
          goto LABEL_49;
        }
LABEL_25:
        if ( v8 >= 0 )
        {
LABEL_26:
          SecurityContext[1].AccessState = *(_ACCESS_STATE **)(*(_QWORD *)(a1 + 232) + 72LL);
          goto LABEL_27;
        }
LABEL_49:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_qD(
            *(_QWORD *)(v3 + 1368),
            (_DWORD)a2,
            8,
            26,
            (__int64)WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids,
            *(_QWORD *)(a1 + 224),
            v8);
        }
LABEL_27:
        if ( v8 == 0x80000000 )
          goto LABEL_34;
        goto LABEL_31;
      }
      break;
    }
    v8 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v28 = 17;
LABEL_48:
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(v3 + 1368),
        (_DWORD)a2,
        8,
        v28,
        (__int64)WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids);
      goto LABEL_49;
    }
  }
LABEL_31:
  if ( v8 == -1073741811 )
  {
    HIDWORD(SecurityContext->SecurityQos) = -2147482880;
  }
  else if ( v8 )
  {
    v34 = 0x40000000;
    if ( v8 != 259 )
      v34 = 0x80000000;
    HIDWORD(SecurityContext->SecurityQos) = v34;
  }
  else
  {
    HIDWORD(SecurityContext->SecurityQos) = 0;
  }
LABEL_34:
  UsbcCompleteIrp(*(_QWORD *)(a1 + 232), v8, v44);
  UsbcDecrementPendingCount(v3, v44);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140001bc8  mov     [rsp+arg_8], rdx
0x140001bcd  push    rbx
0x140001bce  push    rbp
0x140001bcf  push    rsi
0x140001bd0  push    rdi
0x140001bd1  push    r12
0x140001bd3  push    r13
0x140001bd5  push    r14
0x140001bd7  push    r15
0x140001bd9  sub     rsp, 88h
0x140001be0  mov     rax, [rdx+0B8h]
0x140001be7  mov     rbp, rcx
0x140001bea  mov     r13, [rcx+0E8h]
0x140001bf1  mov     esi, 80000000h
0x140001bf6  mov     [rsp+0C8h+var_60], r13
0x140001bfb  mov     r15, [rax+8]
0x140001bff  mov     [rsp+0C8h+var_68], r15
0x140001c04  cmp     qword ptr [r15+18h], 0
0x140001c09  jz      loc_140001D9F
0x140001c0f  movzx   ecx, word ptr [r15]
0x140001c13  cmp     ecx, 40h ; '@'
0x140001c16  jb      loc_140001F2F
0x140001c1c  mov     r8, [rbp+0F0h]
0x140001c23  lea     rsi, [r15+28h]
0x140001c27  xor     ebx, ebx
0x140001c29  mov     [rsp+0C8h+var_50], r8
0x140001c2e  add     rcx, r15
0x140001c31  mov     [rsp+0C8h+arg_10], ebx
0x140001c38  mov     [rsp+0C8h+var_58], rcx
0x140001c3d  lea     rdi, WPP_RECORDER_INITIALIZED
0x140001c44  mov     [rsp+0C8h+arg_18], ebx
0x140001c4b  lea     r12, WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids
0x140001c52  mov     eax, 18h
0x140001c57  cmp     rsi, rcx
0x140001c5a  jnb     loc_140001DE1
0x140001c60  movzx   edx, word ptr [rsi]
0x140001c63  cmp     dx, ax
0x140001c66  jb      loc_140001FB3
0x140001c6c  lea     rax, [rsi+rdx]
0x140001c70  cmp     rax, rcx
0x140001c73  ja      loc_140001FB3
0x140001c79  mov     r8, [r8+8]
0x140001c7d  test    r8, r8
0x140001c80  jz      loc_140001DE1
0x140001c86  mov     r10d, [rbp+0Ch]
0x140001c8a  xor     ecx, ecx
0x140001c8c  cmp     ecx, r10d
0x140001c8f  jnb     loc_1400021B3
0x140001c95  mov     r11, [r8+rcx*8]
0x140001c99  movzx   r9d, byte ptr [rsi+2]
0x140001c9e  mov     [rsp+0C8h+var_78], r11
0x140001ca3  mov     rax, [r11+8]
0x140001ca7  cmp     [rax+2], r9b
0x140001cab  jnz     loc_140001F7E
0x140001cb1  movzx   ecx, byte ptr [rsi+3]
0x140001cb5  movzx   r8d, byte ptr [rax+3]
0x140001cba  cmp     r8b, cl
0x140001cbd  jnz     loc_140001EC6
0x140001cc3  mov     eax, [rax+10h]
0x140001cc6  mov     [rsp+0C8h+arg_10], eax
0x140001ccd  inc     eax
0x140001ccf  lea     ecx, [rax+rax*2]
0x140001cd2  shl     ecx, 3
0x140001cd5  cmp     edx, ecx
0x140001cd7  jb      loc_140001E82
0x140001cdd  xor     r14d, r14d
0x140001ce0  cmp     r14d, [rsp+0C8h+arg_10]
0x140001ce8  jnb     loc_140001E03
0x140001cee  lea     rcx, [r14+r14*2]
0x140001cf2  mov     eax, [rsi+rcx*8+2Ch]
0x140001cf6  mov     [rsp+0C8h+var_70], rcx
0x140001cfb  test    al, 1
0x140001cfd  jnz     loc_140002079
0x140001d03  mov     rdx, [r11]
0x140001d06  lea     r9, [rsp+0C8h+arg_0]
0x140001d0e  mov     r8d, r14d
0x140001d11  mov     [rsp+0C8h+arg_0], 0
0x140001d1c  mov     rcx, rbp
0x140001d1f  call    GetEndpointPriority
0x140001d24  test    eax, eax
0x140001d26  js      loc_140001F85
0x140001d2c  movzx   ebx, word ptr [rsp+0C8h+arg_10]
0x140001d34  movzx   eax, bx
0x140001d37  add     ax, ax
0x140001d3a  add     bx, ax
0x140001d3d  shl     bx, 3
0x140001d41  add     bx, 38h ; '8'
0x140001d45  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140001d4c  jnz     loc_140002038
0x140001d52  cmp     [rsp+0C8h+arg_10], 0
0x140001d5a  ja      loc_1400020EE
0x140001d60  mov     r9, [rsp+0C8h+var_78]
0x140001d65  mov     r8, rbp
0x140001d68  mov     rdx, rsi
0x140001d6b  movzx   ecx, bx
0x140001d6e  call    SendSelectInterfaceUrb
0x140001d73  mov     ebx, eax
0x140001d75  mov     edx, [rsp+0C8h+arg_18]
0x140001d7c  inc     edx
0x140001d7e  mov     [rsp+0C8h+arg_18], edx
0x140001d85  cmp     edx, [rbp+0Ch]
0x140001d88  jnb     short loc_140001DE1
0x140001d8a  movzx   eax, word ptr [rsi]
0x140001d8d  mov     rcx, [rsp+0C8h+var_58]
0x140001d92  add     rsi, rax
0x140001d95  mov     r8, [rsp+0C8h+var_50]
0x140001d9a  jmp     loc_140001C52
0x140001d9f  xor     ebx, ebx
0x140001da1  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140001da8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140001daf  jz      short loc_140001DEE
0x140001db1  mov     rax, [rcx+0E0h]
0x140001db8  lea     r12, WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids
0x140001dbf  mov     rcx, [r13+558h]
0x140001dc6  lea     r9d, [rbx+0Fh]
0x140001dca  mov     [rsp+0C8h+var_A0], rax
0x140001dcf  lea     r8d, [rbx+1]
0x140001dd3  mov     dl, 4
0x140001dd5  mov     [rsp+0C8h+var_A8], r12
0x140001dda  call    WPP_RECORDER_SF_q
0x140001ddf  jmp     short loc_140001DEE
0x140001de1  test    ebx, ebx
0x140001de3  js      loc_140001FE4
0x140001de9  mov     esi, 80000000h
0x140001dee  mov     rax, [rbp+0E8h]
0x140001df5  mov     rcx, [rax+48h]
0x140001df9  mov     [r15+20h], rcx
0x140001dfd  cmp     ebx, esi
0x140001dff  jnz     short loc_140001E2D
0x140001e01  jmp     short loc_140001E45
0x140001e03  mov     rdx, [r11+8]; Src
0x140001e07  movzx   ecx, word ptr [rsi]
0x140001e0a  movzx   eax, word ptr [rdx]
0x140001e0d  cmp     cx, ax
0x140001e10  jnb     loc_140002028
0x140001e16  mov     ebx, 0C000000Dh
0x140001e1b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140001e22  jnz     loc_14000217D
0x140001e28  mov     esi, 80000000h
0x140001e2d  cmp     ebx, 0C000000Dh
0x140001e33  jz      loc_1400021E7
0x140001e39  test    ebx, ebx
0x140001e3b  jnz     loc_1400021D0
0x140001e41  mov     [r15+4], ebx
0x140001e45  mov     r8, [rsp+0C8h+arg_8]
0x140001e4d  mov     edx, ebx
0x140001e4f  mov     rcx, [rbp+0E8h]
0x140001e56  call    UsbcCompleteIrp
0x140001e5b  mov     rdx, [rsp+0C8h+arg_8]
0x140001e63  mov     rcx, r13
0x140001e66  call    UsbcDecrementPendingCount
0x140001e6b  mov     eax, ebx
0x140001e6d  add     rsp, 88h
0x140001e74  pop     r15
0x140001e76  pop     r14
0x140001e78  pop     r13
0x140001e7a  pop     r12
0x140001e7c  pop     rdi
0x140001e7d  pop     rsi
0x140001e7e  pop     rbp
0x140001e7f  pop     rbx
0x140001e80  retn
0x140001e82  mov     ebx, 0C000000Dh
0x140001e87  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140001e8e  jz      short loc_140001E28
0x140001e90  mov     rax, [rbp+0E0h]
0x140001e97  mov     r9d, 15h
0x140001e9d  mov     [rsp+0C8h+var_90], ecx
0x140001ea1  mov     rcx, [r13+558h]
0x140001ea8  mov     dword ptr [rsp+0C8h+var_98], edx
0x140001eac  mov     dl, 2
0x140001eae  mov     [rsp+0C8h+var_A0], rax
0x140001eb3  lea     r8d, [r9-0Dh]
0x140001eb7  mov     [rsp+0C8h+var_A8], r12
0x140001ebc  call    WPP_RECORDER_SF_qDD
0x140001ec1  jmp     loc_140001FE4
0x140001ec6  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140001ecd  jnz     loc_140001F94
0x140001ed3  movzx   ebx, word ptr [rsi+10h]
0x140001ed7  movzx   eax, bx
0x140001eda  add     ax, ax
0x140001edd  add     bx, ax
0x140001ee0  shl     bx, 3
0x140001ee4  add     bx, 38h ; '8'
0x140001ee8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140001eef  jz      loc_140001D52
0x140001ef5  movzx   eax, byte ptr [rsi+2]
0x140001ef9  mov     r9d, 14h
0x140001eff  movzx   ecx, byte ptr [rsi+3]
0x140001f03  mov     dl, 4
0x140001f05  mov     [rsp+0C8h+var_88], eax
0x140001f09  mov     rax, [rbp+0E0h]
0x140001f10  mov     [rsp+0C8h+var_90], ecx
0x140001f14  mov     rcx, [r13+558h]
0x140001f1b  mov     [rsp+0C8h+var_98], r15
0x140001f20  mov     [rsp+0C8h+var_A0], rax
0x140001f25  call    WPP_RECORDER_SF_qqdd
0x140001f2a  jmp     loc_140001D52
0x140001f2f  mov     ebx, 0C000000Dh
0x140001f34  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140001f3b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140001f42  jz      loc_140001E2D
0x140001f48  mov     rax, [rbp+0E0h]
0x140001f4f  lea     r12, WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids
0x140001f56  mov     dword ptr [rsp+0C8h+var_98], ecx
0x140001f5a  mov     r9d, 10h
0x140001f60  mov     rcx, [r13+558h]
0x140001f67  mov     dl, 2
0x140001f69  mov     [rsp+0C8h+var_A0], rax
0x140001f6e  mov     [rsp+0C8h+var_A8], r12
0x140001f73  lea     r8d, [r9-8]
0x140001f77  call    WPP_RECORDER_SF_qD
0x140001f7c  jmp     short loc_140001FE9
0x140001f7e  inc     ecx
0x140001f80  jmp     loc_140001C8C
0x140001f85  mov     r11, [rsp+0C8h+var_78]
0x140001f8a  xor     ebx, ebx
0x140001f8c  inc     r14d
0x140001f8f  jmp     loc_140001CE0
0x140001f94  mov     [rsp+0C8h+var_90], ecx
0x140001f98  mov     rcx, [r13+558h]
0x140001f9f  mov     dword ptr [rsp+0C8h+var_98], r8d
0x140001fa4  mov     dword ptr [rsp+0C8h+var_A0], r9d
0x140001fa9  call    WPP_RECORDER_SF_DDD
0x140001fae  jmp     loc_140001ED3
0x140001fb3  mov     ebx, 0C000000Dh
0x140001fb8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140001fbf  jz      loc_140001E28
0x140001fc5  mov     r9d, 11h
0x140001fcb  mov     rcx, [r13+558h]
0x140001fd2  mov     r8d, 8
0x140001fd8  mov     dl, 2
0x140001fda  mov     [rsp+0C8h+var_A8], r12
0x140001fdf  call    WPP_RECORDER_SF_
0x140001fe4  mov     esi, 80000000h
0x140001fe9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140001ff0  jz      loc_140001DFD
0x140001ff6  mov     rax, [rbp+0E0h]
0x140001ffd  mov     r9d, 1Ah
0x140002003  mov     rcx, [r13+558h]
0x14000200a  mov     dl, 2
0x14000200c  mov     dword ptr [rsp+0C8h+var_98], ebx
0x140002010  mov     [rsp+0C8h+var_A0], rax
0x140002015  lea     r8d, [r9-12h]
0x140002019  mov     [rsp+0C8h+var_A8], r12
0x14000201e  call    WPP_RECORDER_SF_qD
0x140002023  jmp     loc_140001DFD
0x140002028  mov     r8, rax; Size
0x14000202b  mov     rcx, rsi; void *
0x14000202e  call    memmove
0x140002033  jmp     loc_140001D75
0x140002038  mov     rax, [rsp+0C8h+var_70]
0x14000203d  mov     r9d, 18h
0x140002043  mov     rcx, [r13+558h]
0x14000204a  mov     dl, 2
0x14000204c  movzx   eax, byte ptr [rsi+rax*8+1Ah]
0x140002051  lea     r8d, [r9-17h]
0x140002055  mov     [rsp+0C8h+var_90], eax
0x140002059  mov     rax, [rbp+0E0h]
0x140002060  mov     [rsp+0C8h+var_98], r15
0x140002065  mov     [rsp+0C8h+var_A0], rax
0x14000206a  mov     [rsp+0C8h+var_A8], r12
0x14000206f  call    WPP_RECORDER_SF_qqd
0x140002074  jmp     loc_140001D52
0x140002079  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140002080  lea     r14, [rsi+rcx*8]
0x140002084  jz      short loc_1400020B1
0x140002086  movzx   eax, word ptr [r14+18h]
0x14000208b  mov     r9d, 16h
0x140002091  mov     rcx, [r13+558h]
0x140002098  mov     dl, 2
0x14000209a  mov     dword ptr [rsp+0C8h+var_A0], eax
0x14000209e  mov     [rsp+0C8h+var_A8], r12
0x1400020a3  lea     r8d, [r9-0Eh]
0x1400020a7  call    WPP_RECORDER_SF_D
0x1400020ac  mov     rcx, [rsp+0C8h+var_70]
0x1400020b1  movzx   ebx, word ptr [rsp+0C8h+arg_10]
0x1400020b9  movzx   eax, bx
0x1400020bc  add     ax, ax
0x1400020bf  add     bx, ax
0x1400020c2  shl     bx, 3
0x1400020c6  add     bx, 38h ; '8'
0x1400020ca  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400020d1  jz      loc_140001D52
0x1400020d7  movzx   eax, byte ptr [rsi+rcx*8+1Ah]
0x1400020dc  mov     r9d, 17h
0x1400020e2  movzx   ecx, word ptr [r14+18h]
0x1400020e7  mov     dl, 2
0x1400020e9  jmp     loc_140001F05
0x1400020ee  mov     r12, [rsp+0C8h+var_78]
0x1400020f3  xor     r14d, r14d
0x1400020f6  mov     r13d, [rsp+0C8h+arg_10]
0x1400020fe  mov     r15d, r14d
0x140002101  mov     rdx, [r12]
0x140002105  lea     r9, [rsp+0C8h+arg_0]
0x14000210d  mov     r8d, r15d
0x140002110  mov     [rsp+0C8h+arg_0], 0
0x14000211b  mov     rcx, rbp
0x14000211e  call    GetEndpointPriority
0x140002123  test    eax, eax
  ... truncated ...
```
