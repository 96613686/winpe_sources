# HUBDESC_InternalValidateHighSpeedIsochEndpointCompanionDescriptor

- ea: `0x140038124`
- end: `0x140038449`
- name: `HUBDESC_InternalValidateHighSpeedIsochEndpointCompanionDescriptor`
- size: `805`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14003cce8`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14001cf04`
- `0x14002d940`
- `0x140038124`
- `0x14003f0e4`
- `0x140045570`

## pseudocode

```c
__int16 __fastcall HUBDESC_InternalValidateHighSpeedIsochEndpointCompanionDescriptor(
        char *a1,
        __int64 a2,
        unsigned int *a3,
        int *a4,
        __int64 a5)
{
  int *v5; // rsi
  int v9; // r15d
  unsigned int v10; // eax
  int v11; // ebp
  __int64 v12; // r8
  __int64 *v13; // rdx
  bool v14; // zf
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // r12d
  int v18; // edx
  int v20; // [rsp+20h] [rbp-78h]
  __int64 v21; // [rsp+28h] [rbp-70h]
  int v22; // [rsp+A0h] [rbp+8h] BYREF

  v5 = a4;
  v22 = 0;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v5 = &v22;
  }
  v9 = a5;
  LOWORD(v10) = *(_WORD *)a2 - 544;
  v11 = (_DWORD)a1 - *(_DWORD *)(a2 + 56);
  v12 = 5;
  v13 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
  if ( (unsigned __int16)v10 > 0xDFu )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 3;
      LOWORD(v10) = WPP_RECORDER_SF_d(
                      a5,
                      (_DWORD)v13,
                      5,
                      107,
                      (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                      v11);
    }
    goto LABEL_37;
  }
  v14 = *(_DWORD *)(a2 + 4) == 2;
  v15 = (unsigned __int8)*a1;
  *a3 = v15;
  if ( !v14 )
  {
    *v5 = 2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_d(v9, (_DWORD)v13, 5, 108, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v11);
    }
    v16 = 266;
LABEL_12:
    LOWORD(v10) = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), v16, v12);
    goto LABEL_37;
  }
  v17 = *(_DWORD *)(a2 + 72) - v11;
  if ( (unsigned __int8)v15 >= 8u )
  {
LABEL_18:
    if ( (unsigned __int8)*a1 > 8u )
    {
      *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_DDD(
          v9,
          (_DWORD)v13,
          v12,
          111,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *a1,
          v11,
          8);
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 268, v12);
    }
    if ( (*(_DWORD *)(a2 + 256) & 0x10) != 0 )
    {
      if ( *a3 <= v17 )
      {
        v10 = *((_DWORD *)a1 + 1) - 3073;
        if ( v10 > 0xBFF )
        {
          *v5 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_DDdd(v9, (_DWORD)v13, v12, (_DWORD)a4, v20, v11, *((_DWORD *)a1 + 1));
          LOWORD(v10) = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 272, v12);
        }
        *(_DWORD *)(a2 + 256) |= 0x80u;
        goto LABEL_37;
      }
      *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v21) = v11;
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_d(v9, (_DWORD)v13, 5, 113, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v21);
      }
      v16 = 270;
    }
    else
    {
      *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v21) = v11;
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_d(v9, (_DWORD)v13, 5, 112, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v21);
      }
      v16 = 267;
    }
    goto LABEL_12;
  }
  *v5 = 2;
  LOWORD(v10) = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 269, 5);
  if ( v17 >= 8 )
  {
    *a3 = 8;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = 2;
      WPP_RECORDER_SF_DDDD(v9, v18, 5, 110, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a1, v11, 8, 8);
    }
    v13 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
    goto LABEL_18;
  }
  *v5 = 1;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return v10;
  LOBYTE(v18) = 2;
  LOWORD(v10) = WPP_RECORDER_SF_DDD(
                  v9,
                  v18,
                  v12,
                  109,
                  (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                  *a1,
                  v11,
                  8);
LABEL_37:
  if ( *v5 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = 2;
    LOWORD(v10) = WPP_RECORDER_SF_(v9, (_DWORD)v13, 5, 115, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v10;
}

```

## disassembly

```asm
0x140038124  mov     r11, rsp
0x140038127  push    rbx
0x140038128  push    rbp
0x140038129  push    rsi
0x14003812a  push    rdi
0x14003812b  push    r12
0x14003812d  push    r13
0x14003812f  push    r14
0x140038131  push    r15
0x140038133  sub     rsp, 58h
0x140038137  xor     eax, eax
0x140038139  mov     rsi, r9
0x14003813c  mov     [r11+8], eax
0x140038140  mov     r13, r8
0x140038143  mov     rbx, rdx
0x140038146  mov     r14, rcx
0x140038149  test    r9, r9
0x14003814c  jnz     short loc_140038154
0x14003814e  lea     rsi, [r11+8]
0x140038152  jmp     short loc_14003815C
0x140038154  cmp     [rdx+30h], al
0x140038157  jz      short loc_14003815C
0x140038159  mov     [r9], eax
0x14003815c  movzx   eax, word ptr [rdx]
0x14003815f  mov     ecx, 220h
0x140038164  mov     r15, [rsp+98h+arg_20]
0x14003816c  sub     ax, cx
0x14003816f  mov     ebp, r14d
0x140038172  mov     ecx, 0DFh
0x140038177  sub     ebp, [rdx+38h]
0x14003817a  mov     r8d, 5
0x140038180  lea     rdx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038187  cmp     ax, cx
0x14003818a  jbe     short loc_1400381BC
0x14003818c  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140038193  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003819a  jz      loc_140038409
0x1400381a0  lea     r9d, [rcx-74h]
0x1400381a4  mov     dword ptr [rsp+98h+var_70], ebp
0x1400381a8  mov     [rsp+98h+var_78], rdx
0x1400381ad  mov     rcx, r15
0x1400381b0  mov     dl, 3
0x1400381b2  call    WPP_RECORDER_SF_d
0x1400381b7  jmp     loc_140038409
0x1400381bc  cmp     dword ptr [rbx+4], 2
0x1400381c0  movzx   eax, byte ptr [r14]
0x1400381c4  mov     [r13+0], eax
0x1400381c8  jz      short loc_140038210
0x1400381ca  mov     dword ptr [rsi], 2
0x1400381d0  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400381d7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400381de  jz      short loc_1400381F9
0x1400381e0  mov     dword ptr [rsp+98h+var_70], ebp
0x1400381e4  mov     r9d, 6Ch ; 'l'
0x1400381ea  mov     [rsp+98h+var_78], rdx
0x1400381ef  mov     rcx, r15
0x1400381f2  mov     dl, 2
0x1400381f4  call    WPP_RECORDER_SF_d
0x1400381f9  mov     edx, 10Ah
0x1400381fe  mov     rax, [rbx+18h]
0x140038202  mov     rcx, [rbx+28h]
0x140038206  call    _guard_dispatch_icall
0x14003820b  jmp     loc_140038409
0x140038210  mov     r12d, [rbx+48h]
0x140038214  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003821b  sub     r12d, ebp
0x14003821e  mov     ecx, 8
0x140038223  cmp     al, cl
0x140038225  jnb     short loc_140038298
0x140038227  mov     dword ptr [rsi], 2
0x14003822d  mov     edx, 10Dh
0x140038232  mov     rax, [rbx+18h]
0x140038236  mov     rcx, [rbx+28h]
0x14003823a  call    _guard_dispatch_icall
0x14003823f  mov     ecx, 8
0x140038244  cmp     r12d, ecx
0x140038247  jb      loc_14003832E
0x14003824d  mov     [r13+0], ecx
0x140038251  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140038258  jz      short loc_140038291
0x14003825a  movzx   eax, byte ptr [r14]
0x14003825e  lea     r9d, [rcx+66h]
0x140038262  mov     [rsp+98h+var_58], ecx
0x140038266  lea     r8d, [rcx-3]
0x14003826a  mov     [rsp+98h+var_60], ecx
0x14003826e  mov     dl, 2
0x140038270  mov     [rsp+98h+var_68], ebp
0x140038274  mov     rcx, r15
0x140038277  mov     dword ptr [rsp+98h+var_70], eax
0x14003827b  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038282  mov     [rsp+98h+var_78], rax
0x140038287  call    WPP_RECORDER_SF_DDDD
0x14003828c  mov     ecx, 8
0x140038291  lea     rdx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038298  cmp     [r14], cl
0x14003829b  jbe     short loc_1400382E3
0x14003829d  mov     dword ptr [rsi], 2
0x1400382a3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400382aa  jz      short loc_1400382D1
0x1400382ac  movzx   eax, byte ptr [r14]
0x1400382b0  mov     r9d, 6Fh ; 'o'
0x1400382b6  mov     [rsp+98h+var_60], ecx
0x1400382ba  mov     rcx, r15
0x1400382bd  mov     [rsp+98h+var_68], ebp
0x1400382c1  mov     dword ptr [rsp+98h+var_70], eax
0x1400382c5  mov     [rsp+98h+var_78], rdx
0x1400382ca  mov     dl, 2
0x1400382cc  call    WPP_RECORDER_SF_DDD
0x1400382d1  mov     rax, [rbx+18h]
0x1400382d5  mov     edx, 10Ch
0x1400382da  mov     rcx, [rbx+28h]
0x1400382de  call    _guard_dispatch_icall
0x1400382e3  mov     eax, [rbx+100h]
0x1400382e9  test    al, 10h
0x1400382eb  jnz     loc_140038379
0x1400382f1  mov     dword ptr [rsi], 2
0x1400382f7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400382fe  jz      short loc_140038324
0x140038300  mov     r9d, 70h ; 'p'
0x140038306  mov     dword ptr [rsp+98h+var_70], ebp
0x14003830a  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038311  mov     dl, 2
0x140038313  mov     rcx, r15
0x140038316  mov     [rsp+98h+var_78], rax
0x14003831b  lea     r8d, [r9-6Bh]
0x14003831f  call    WPP_RECORDER_SF_d
0x140038324  mov     edx, 10Bh
0x140038329  jmp     loc_1400381FE
0x14003832e  mov     dword ptr [rsi], 1
0x140038334  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003833b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140038342  jz      loc_140038437
0x140038348  movzx   eax, byte ptr [r14]
0x14003834c  mov     r9d, 6Dh ; 'm'
0x140038352  mov     [rsp+98h+var_60], ecx
0x140038356  mov     dl, 2
0x140038358  mov     [rsp+98h+var_68], ebp
0x14003835c  mov     rcx, r15
0x14003835f  mov     dword ptr [rsp+98h+var_70], eax
0x140038363  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003836a  mov     [rsp+98h+var_78], rax
0x14003836f  call    WPP_RECORDER_SF_DDD
0x140038374  jmp     loc_140038409
0x140038379  cmp     [r13+0], r12d
0x14003837d  jbe     short loc_1400383BC
0x14003837f  mov     dword ptr [rsi], 2
0x140038385  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003838c  jz      short loc_1400383B2
0x14003838e  mov     r9d, 71h ; 'q'
0x140038394  mov     dword ptr [rsp+98h+var_70], ebp
0x140038398  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003839f  mov     dl, 2
0x1400383a1  mov     rcx, r15
0x1400383a4  mov     [rsp+98h+var_78], rax
0x1400383a9  lea     r8d, [r9-6Ch]
0x1400383ad  call    WPP_RECORDER_SF_d
0x1400383b2  mov     edx, 10Eh
0x1400383b7  jmp     loc_1400381FE
0x1400383bc  mov     eax, [r14+4]
0x1400383c0  sub     eax, 0C01h
0x1400383c5  cmp     eax, 0BFFh
0x1400383ca  jbe     short loc_140038401
0x1400383cc  mov     dword ptr [rsi], 2
0x1400383d2  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400383d9  jz      short loc_1400383EF
0x1400383db  mov     eax, [r14+4]
0x1400383df  mov     rcx, r15
0x1400383e2  mov     [rsp+98h+var_68], eax
0x1400383e6  mov     dword ptr [rsp+98h+var_70], ebp
0x1400383ea  call    WPP_RECORDER_SF_DDdd
0x1400383ef  mov     rax, [rbx+18h]
0x1400383f3  mov     edx, 110h
0x1400383f8  mov     rcx, [rbx+28h]
0x1400383fc  call    _guard_dispatch_icall
0x140038401  bts     dword ptr [rbx+100h], 7
0x140038409  cmp     dword ptr [rsi], 0
0x14003840c  jz      short loc_140038437
0x14003840e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140038415  jz      short loc_140038437
0x140038417  mov     r9d, 73h ; 's'
0x14003841d  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038424  mov     dl, 2
0x140038426  mov     [rsp+98h+var_78], rax
0x14003842b  mov     rcx, r15
0x14003842e  lea     r8d, [r9-6Eh]
0x140038432  call    WPP_RECORDER_SF_
0x140038437  add     rsp, 58h
0x14003843b  pop     r15
0x14003843d  pop     r14
0x14003843f  pop     r13
0x140038441  pop     r12
0x140038443  pop     rdi
0x140038444  pop     rsi
0x140038445  pop     rbp
0x140038446  pop     rbx
0x140038447  retn
```
