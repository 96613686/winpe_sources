# HUBDESC_InternalValidateConfigDescriptor

- ea: `0x1400360bc`
- end: `0x14003645f`
- name: `HUBDESC_InternalValidateConfigDescriptor`
- size: `931`
- prototype: `char __fastcall(__int64, __int64, unsigned int *, int *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14003cce8`

## callees

- `0x1400025a4`
- `0x1400067ac`
- `0x14001cf04`
- `0x1400360bc`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_InternalValidateConfigDescriptor(__int64 a1, __int64 a2, unsigned int *a3, int *a4, __int64 a5)
{
  int *v5; // rdi
  __int64 v7; // rbx
  int v9; // ebp
  __int64 *v10; // r8
  char v11; // r15
  int v12; // edx
  unsigned int v13; // ecx
  unsigned int v14; // r14d
  int v16; // [rsp+90h] [rbp+8h] BYREF

  v5 = a4;
  v16 = 0;
  v7 = a2;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v5 = &v16;
  }
  v9 = a5;
  *a3 = 9;
  v10 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
  v11 = 1;
  if ( *(_BYTE *)a1 < 9u )
  {
    *v5 = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DDD(
        v9,
        a2,
        (unsigned int)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
        19,
        (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
        *(_BYTE *)a1,
        9,
        9);
    }
    (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(v7 + 24))(*(_QWORD *)(v7 + 40), 55, v10);
    v10 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
  }
  v12 = 512;
  if ( *(_BYTE *)a1 > 9u )
  {
    if ( *(_WORD *)v7 > 0x200u || *(_BYTE *)(v7 + 12) )
      *v5 = 2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_DDD(
        v9,
        v12,
        (unsigned int)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
        20,
        (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
        *(_BYTE *)a1,
        9,
        9);
    }
    (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(v7 + 24))(*(_QWORD *)(v7 + 40), 54, v10);
  }
  if ( *(_BYTE *)(a1 + 1) != 2 )
  {
    *v5 = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_DDD(
        v9,
        v12,
        (_DWORD)v10,
        21,
        (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
        *(_BYTE *)(a1 + 1),
        2,
        2);
    }
    (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(v7 + 24))(*(_QWORD *)(v7 + 40), 58, v10);
  }
  v13 = *(_DWORD *)(v7 + 72);
  if ( *a3 <= v13 )
  {
    v14 = 9 * (*(unsigned __int8 *)(a1 + 4) + 1);
    if ( v14 > v13 )
    {
      if ( *(_WORD *)v7 > 0x200u || *(_BYTE *)(v7 + 12) || *(_BYTE *)(v7 + 13) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_dD(
          v9,
          v12,
          5,
          23,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *(_DWORD *)(v7 + 72),
          v14);
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(v7 + 24))(*(_QWORD *)(v7 + 40), 57, v10);
    }
    *(_QWORD *)(v7 + 64) = *(_QWORD *)(v7 + 56) + *(unsigned __int16 *)(a1 + 2);
    if ( (unsigned int)*(unsigned __int16 *)(a1 + 2) > *(_DWORD *)(v7 + 72) )
    {
      if ( *(_WORD *)v7 > 0x200u || *(_BYTE *)(v7 + 12) || *(_BYTE *)(v7 + 13) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_DDD(
          v9,
          v12,
          (_DWORD)v10,
          24,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *(_WORD *)(a1 + 2),
          *(_DWORD *)(v7 + 72),
          *(_DWORD *)(v7 + 72));
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(v7 + 24))(*(_QWORD *)(v7 + 40), 61, v10);
      *(_QWORD *)(v7 + 64) = *(_QWORD *)(v7 + 56) + *(unsigned int *)(v7 + 72);
    }
    if ( *(unsigned __int16 *)(a1 + 2) < v14 )
    {
      if ( *(_WORD *)v7 > 0x200u || *(_BYTE *)(v7 + 12) || *(_BYTE *)(v7 + 13) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_DDD(
          v9,
          v12,
          (_DWORD)v10,
          25,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *(_WORD *)(a1 + 2),
          v14,
          *(_DWORD *)(v7 + 72));
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(v7 + 24))(*(_QWORD *)(v7 + 40), 62, v10);
      *(_QWORD *)(v7 + 64) = *(_QWORD *)(v7 + 56) + *(unsigned int *)(v7 + 72);
    }
  }
  else
  {
    if ( *(_WORD *)v7 > 0x200u || *(_BYTE *)(v7 + 12) || *(_BYTE *)(v7 + 13) )
      *v5 = 2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_(v9, v12, 5, 22, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    }
    (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(v7 + 24))(*(_QWORD *)(v7 + 40), 56, v10);
  }
  if ( *v5 )
  {
    v11 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_(v9, v12, 5, 26, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1400360bc  mov     rax, rsp
0x1400360bf  push    rbx
0x1400360c0  push    rbp
0x1400360c1  push    rsi
0x1400360c2  push    rdi
0x1400360c3  push    r12
0x1400360c5  push    r13
0x1400360c7  push    r14
0x1400360c9  push    r15
0x1400360cb  sub     rsp, 48h
0x1400360cf  xor     r12d, r12d
0x1400360d2  mov     rdi, r9
0x1400360d5  mov     [rax+8], r12d
0x1400360d9  mov     r14, r8
0x1400360dc  mov     rbx, rdx
0x1400360df  mov     rsi, rcx
0x1400360e2  test    r9, r9
0x1400360e5  jnz     short loc_1400360ED
0x1400360e7  lea     rdi, [rax+8]
0x1400360eb  jmp     short loc_1400360F6
0x1400360ed  cmp     [rdx+30h], r12b
0x1400360f1  jz      short loc_1400360F6
0x1400360f3  mov     [r9], r12d
0x1400360f6  mov     rbp, [rsp+88h+arg_20]
0x1400360fe  lea     rax, WPP_RECORDER_INITIALIZED
0x140036105  mov     ecx, 9
0x14003610a  mov     [r8], ecx
0x14003610d  lea     r8, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036114  lea     r15d, [rcx-8]
0x140036118  lea     r13d, [rcx-7]
0x14003611c  cmp     [rsi], cl
0x14003611e  jnb     short loc_140036174
0x140036120  mov     [rdi], r15d
0x140036123  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x14003612a  jz      short loc_14003614F
0x14003612c  movzx   eax, byte ptr [rsi]
0x14003612f  lea     r9d, [rcx+0Ah]
0x140036133  mov     [rsp+88h+var_50], ecx
0x140036137  mov     dl, r13b
0x14003613a  mov     [rsp+88h+var_58], ecx
0x14003613e  mov     rcx, rbp
0x140036141  mov     [rsp+88h+var_60], eax
0x140036145  mov     [rsp+88h+var_68], r8
0x14003614a  call    WPP_RECORDER_SF_DDD
0x14003614f  mov     rax, [rbx+18h]
0x140036153  mov     edx, 37h ; '7'
0x140036158  mov     rcx, [rbx+28h]
0x14003615c  call    _guard_dispatch_icall
0x140036161  mov     ecx, 9
0x140036166  lea     rax, WPP_RECORDER_INITIALIZED
0x14003616d  lea     r8, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036174  mov     edx, 200h
0x140036179  cmp     [rsi], cl
0x14003617b  jbe     short loc_1400361CB
0x14003617d  cmp     [rbx], dx
0x140036180  ja      short loc_140036188
0x140036182  cmp     [rbx+0Ch], r12b
0x140036186  jz      short loc_14003618B
0x140036188  mov     [rdi], r13d
0x14003618b  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x140036192  jz      short loc_1400361B9
0x140036194  movzx   eax, byte ptr [rsi]
0x140036197  mov     r9d, 14h
0x14003619d  mov     [rsp+88h+var_50], ecx
0x1400361a1  mov     dl, r13b
0x1400361a4  mov     [rsp+88h+var_58], ecx
0x1400361a8  mov     rcx, rbp
0x1400361ab  mov     [rsp+88h+var_60], eax
0x1400361af  mov     [rsp+88h+var_68], r8
0x1400361b4  call    WPP_RECORDER_SF_DDD
0x1400361b9  mov     rax, [rbx+18h]
0x1400361bd  mov     edx, 36h ; '6'
0x1400361c2  mov     rcx, [rbx+28h]
0x1400361c6  call    _guard_dispatch_icall
0x1400361cb  cmp     [rsi+1], r13b
0x1400361cf  jz      short loc_140036225
0x1400361d1  mov     [rdi], r15d
0x1400361d4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400361db  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400361e2  jz      short loc_140036213
0x1400361e4  movzx   eax, byte ptr [rsi+1]
0x1400361e8  mov     r9d, 15h
0x1400361ee  mov     [rsp+88h+var_50], r13d
0x1400361f3  mov     dl, r13b
0x1400361f6  mov     [rsp+88h+var_58], r13d
0x1400361fb  mov     rcx, rbp
0x1400361fe  mov     [rsp+88h+var_60], eax
0x140036202  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036209  mov     [rsp+88h+var_68], rax
0x14003620e  call    WPP_RECORDER_SF_DDD
0x140036213  mov     rax, [rbx+18h]
0x140036217  mov     edx, 3Ah ; ':'
0x14003621c  mov     rcx, [rbx+28h]
0x140036220  call    _guard_dispatch_icall
0x140036225  mov     ecx, [rbx+48h]
0x140036228  cmp     [r14], ecx
0x14003622b  jbe     short loc_14003628E
0x14003622d  mov     eax, 200h
0x140036232  cmp     [rbx], ax
0x140036235  ja      short loc_140036243
0x140036237  cmp     [rbx+0Ch], r12b
0x14003623b  jnz     short loc_140036243
0x14003623d  cmp     [rbx+0Dh], r12b
0x140036241  jz      short loc_140036246
0x140036243  mov     [rdi], r13d
0x140036246  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003624d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140036254  jz      short loc_140036277
0x140036256  mov     r9d, 16h
0x14003625c  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036263  mov     dl, r13b
0x140036266  mov     [rsp+88h+var_68], rax
0x14003626b  mov     rcx, rbp
0x14003626e  lea     r8d, [r9-11h]
0x140036272  call    WPP_RECORDER_SF_
0x140036277  mov     rax, [rbx+18h]
0x14003627b  mov     edx, 38h ; '8'
0x140036280  mov     rcx, [rbx+28h]
0x140036284  call    _guard_dispatch_icall
0x140036289  jmp     loc_140036418
0x14003628e  movzx   eax, byte ptr [rsi+4]
0x140036292  add     eax, r15d
0x140036295  lea     r14d, [rax+rax*8]
0x140036299  cmp     r14d, ecx
0x14003629c  jbe     short loc_140036306
0x14003629e  mov     eax, 200h
0x1400362a3  cmp     [rbx], ax
0x1400362a6  ja      short loc_1400362B4
0x1400362a8  cmp     [rbx+0Ch], r12b
0x1400362ac  jnz     short loc_1400362B4
0x1400362ae  cmp     [rbx+0Dh], r12b
0x1400362b2  jz      short loc_1400362B7
0x1400362b4  mov     [rdi], r13d
0x1400362b7  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400362be  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400362c5  jz      short loc_1400362F4
0x1400362c7  mov     eax, [rbx+48h]
0x1400362ca  mov     r9d, 17h
0x1400362d0  mov     [rsp+88h+var_58], r14d
0x1400362d5  mov     dl, r13b
0x1400362d8  mov     [rsp+88h+var_60], eax
0x1400362dc  mov     rcx, rbp
0x1400362df  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400362e6  lea     r8d, [r9-12h]
0x1400362ea  mov     [rsp+88h+var_68], rax
0x1400362ef  call    WPP_RECORDER_SF_dD
0x1400362f4  mov     rax, [rbx+18h]
0x1400362f8  mov     edx, 39h ; '9'
0x1400362fd  mov     rcx, [rbx+28h]
0x140036301  call    _guard_dispatch_icall
0x140036306  movzx   eax, word ptr [rsi+2]
0x14003630a  add     rax, [rbx+38h]
0x14003630e  mov     [rbx+40h], rax
0x140036312  movzx   eax, word ptr [rsi+2]
0x140036316  cmp     eax, [rbx+48h]
0x140036319  jbe     short loc_140036391
0x14003631b  mov     eax, 200h
0x140036320  cmp     [rbx], ax
0x140036323  ja      short loc_140036331
0x140036325  cmp     [rbx+0Ch], r12b
0x140036329  jnz     short loc_140036331
0x14003632b  cmp     [rbx+0Dh], r12b
0x14003632f  jz      short loc_140036334
0x140036331  mov     [rdi], r13d
0x140036334  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003633b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036342  jz      short loc_140036374
0x140036344  mov     eax, [rbx+48h]
0x140036347  mov     r9d, 18h
0x14003634d  movzx   ecx, word ptr [rsi+2]
0x140036351  mov     dl, r13b
0x140036354  mov     [rsp+88h+var_50], eax
0x140036358  mov     [rsp+88h+var_58], eax
0x14003635c  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036363  mov     [rsp+88h+var_60], ecx
0x140036367  mov     rcx, rbp
0x14003636a  mov     [rsp+88h+var_68], rax
0x14003636f  call    WPP_RECORDER_SF_DDD
0x140036374  mov     rax, [rbx+18h]
0x140036378  mov     edx, 3Dh ; '='
0x14003637d  mov     rcx, [rbx+28h]
0x140036381  call    _guard_dispatch_icall
0x140036386  mov     eax, [rbx+48h]
0x140036389  add     rax, [rbx+38h]
0x14003638d  mov     [rbx+40h], rax
0x140036391  movzx   eax, word ptr [rsi+2]
0x140036395  cmp     eax, r14d
0x140036398  jnb     short loc_140036411
0x14003639a  mov     eax, 200h
0x14003639f  cmp     [rbx], ax
0x1400363a2  ja      short loc_1400363B0
0x1400363a4  cmp     [rbx+0Ch], r12b
0x1400363a8  jnz     short loc_1400363B0
0x1400363aa  cmp     [rbx+0Dh], r12b
0x1400363ae  jz      short loc_1400363B3
0x1400363b0  mov     [rdi], r13d
0x1400363b3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400363ba  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400363c1  jz      short loc_1400363F4
0x1400363c3  mov     eax, [rbx+48h]
0x1400363c6  mov     r9d, 19h
0x1400363cc  movzx   ecx, word ptr [rsi+2]
0x1400363d0  mov     dl, r13b
0x1400363d3  mov     [rsp+88h+var_50], eax
0x1400363d7  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400363de  mov     [rsp+88h+var_58], r14d
0x1400363e3  mov     [rsp+88h+var_60], ecx
0x1400363e7  mov     rcx, rbp
0x1400363ea  mov     [rsp+88h+var_68], rax
0x1400363ef  call    WPP_RECORDER_SF_DDD
0x1400363f4  mov     rax, [rbx+18h]
0x1400363f8  mov     edx, 3Eh ; '>'
0x1400363fd  mov     rcx, [rbx+28h]
0x140036401  call    _guard_dispatch_icall
0x140036406  mov     eax, [rbx+48h]
0x140036409  add     rax, [rbx+38h]
0x14003640d  mov     [rbx+40h], rax
0x140036411  lea     rsi, WPP_RECORDER_INITIALIZED
0x140036418  cmp     [rdi], r12d
0x14003641b  jz      short loc_14003644A
0x14003641d  mov     r15b, r12b
0x140036420  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140036427  jz      short loc_14003644A
0x140036429  mov     r9d, 1Ah
0x14003642f  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036436  mov     dl, r13b
0x140036439  mov     [rsp+88h+var_68], rax
0x14003643e  mov     rcx, rbp
0x140036441  lea     r8d, [r9-15h]
0x140036445  call    WPP_RECORDER_SF_
0x14003644a  mov     al, r15b
0x14003644d  add     rsp, 48h
0x140036451  pop     r15
0x140036453  pop     r14
0x140036455  pop     r13
0x140036457  pop     r12
0x140036459  pop     rdi
0x14003645a  pop     rsi
0x14003645b  pop     rbp
0x14003645c  pop     rbx
0x14003645d  retn
```
