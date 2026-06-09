# VMX_RAW_CONFIG::AtomicUpdatePhase1(VMX_TRANSACTION *)

- ea: `0x14005818c`
- end: `0x140058443`
- name: `?AtomicUpdatePhase1@VMX_RAW_CONFIG@@QEAAJPEAVVMX_TRANSACTION@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(VMX_RAW_CONFIG *__hidden this, struct VMX_TRANSACTION *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002a3f4`
- `0x14004e3ac`

## callees

- `0x1400097c0`
- `0x1400099d8`
- `0x140031adc`
- `0x14005818c`
- `0x140058b9c`
- `0x140058efc`
- `0x1400591f0`

## pseudocode

```c
__int64 __fastcall VMX_RAW_CONFIG::AtomicUpdatePhase1(VMX_RAW_CONFIG *this, struct VMX_TRANSACTION *a2)
{
  unsigned __int64 v2; // rbp
  unsigned __int8 v4; // r15
  bool v5; // zf
  __int64 v6; // rax
  __int128 v7; // xmm1
  struct VMX_RECORD *i; // r14
  _DWORD *v9; // rsi
  _DWORD *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // r12d
  VMX_NOTIFICATION_QUEUE *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int128 v17; // xmm1
  struct VMX_RAW_RECORD *v18; // r14
  __int16 v19; // cx
  struct VMX_RAW_RECORD *v20; // r8
  struct VMX_RAW_RECORD *v21; // rdx
  struct VMX_RAW_RECORD *v23; // [rsp+60h] [rbp+8h] BYREF

  v23 = 0;
  v2 = (unsigned __int64)a2;
  v4 = 1;
  v5 = *((_WORD *)a2 + 24) == 1;
  *((_WORD *)this + 36) = 2;
  if ( !v5 )
    v2 = 0;
  *((_QWORD *)this + 8) = *(_QWORD *)a2;
  v6 = *(_QWORD *)this;
  *(_OWORD *)((char *)this + 172) = *(_OWORD *)((char *)a2 + 8);
  v7 = *(_OWORD *)((char *)a2 + 20);
  *((_WORD *)this + 52) |= 1u;
  *(_OWORD *)((char *)this + 184) = v7;
  for ( i = *(struct VMX_RECORD **)(v6 + 16);
        i != (struct VMX_RECORD *)(*(_QWORD *)this + 16LL);
        i = *(struct VMX_RECORD **)i )
  {
    if ( (*((_BYTE *)i + 64) & 2) != 0 )
    {
      *((_WORD *)this + 52) |= 2u;
      v9 = (_DWORD *)((char *)this + 80);
      v10 = (_DWORD *)((char *)this + 100);
      if ( (*((_BYTE *)i + 64) & 4) == 0 )
      {
        v11 = *(_QWORD *)(*((_QWORD *)i + 5) + 56LL);
        v12 = *(unsigned int *)(v11 + 32);
        *(_WORD *)(v11 + 22) |= 1u;
        *(_WORD *)(*((_QWORD *)this + 17) + 24 * v12 + 20) |= 1u;
        *v10 += (*v9 - 16 + *(_DWORD *)(v11 + 28) + 7) / (unsigned int)(*v9 - 16);
      }
      if ( (*((_BYTE *)i + 64) & 8) == 0 )
      {
        v13 = VMX_RAW_CONFIG::CreateRawRecord(this, i, &v23);
        if ( v13 < 0 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v15 = 32;
            goto LABEL_20;
          }
          goto LABEL_21;
        }
      }
    }
  }
  v9 = (_DWORD *)((char *)this + 80);
  v10 = (_DWORD *)((char *)this + 100);
  if ( (unsigned int)(*((_DWORD *)this + 19) - *((_DWORD *)this + 21) / *((_DWORD *)this + 20) - *((_DWORD *)this + 25)) > *((_DWORD *)this + 25) )
  {
    v13 = -1070071807;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v15 = 33;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v14 + 3), v15, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids, (unsigned int)v13);
    }
LABEL_21:
    v16 = *((_QWORD *)this + 7);
    v17 = *(_OWORD *)((char *)this + 156);
    v18 = (struct VMX_RAW_RECORD *)*((_QWORD *)this + 14);
    *(_OWORD *)((char *)this + 172) = *((_OWORD *)this + 9);
    *((_WORD *)this + 36) = 1;
    *(_OWORD *)((char *)this + 184) = v17;
    *((_QWORD *)this + 8) = v16;
    while ( v18 != (VMX_RAW_CONFIG *)((char *)this + 112) )
    {
      v19 = *((_WORD *)v18 + 11);
      v20 = v18;
      v21 = v18;
      v18 = *(struct VMX_RAW_RECORD **)v18;
      if ( (v19 & 2) != 0 )
      {
        VMX_RAW_CONFIG::DeleteRawRecord(this, v21);
      }
      else if ( (v19 & 1) != 0 )
      {
        *((_WORD *)v20 + 11) &= ~1u;
        *(_WORD *)(*((_QWORD *)this + 17) + 24LL * *((unsigned int *)v20 + 8) + 20) |= 1u;
        *v10 -= (*v9 - 16 + *((_DWORD *)v20 + 7) + 7) / (unsigned int)(*v9 - 16);
      }
    }
    VMX_RAW_CONFIG::Untouch(this);
    return (unsigned int)v13;
  }
  VMX_RAW_CONFIG::IncrementalWrite(
    this,
    (struct VMX_CHANGE_IDENTITY_TRANSACTION *)(v2 & ((unsigned __int128)-(__int128)v2 >> 64)),
    0,
    v2 == 0,
    0);
  VMX_RAW_CONFIG::Untouch(this);
  *((_WORD *)this + 52) |= 1u;
  *((_WORD *)this + 36) = 3;
  if ( v2 )
  {
    *(_OWORD *)((char *)this + 8) = *(_OWORD *)(v2 + 112);
    RtlStringCbCopyA((NTSTRSAFE_PSTR)this + 24, 0x20u, (NTSTRSAFE_PCSTR)(v2 + 128));
    v4 = 0;
  }
  VMX_RAW_CONFIG::IncrementalWrite(this, (struct VMX_CHANGE_IDENTITY_TRANSACTION *)v2, 0, v4, 0);
  VMX_RAW_CONFIG::Untouch(this);
  return 0;
}

```

## disassembly

```asm
0x14005818c  mov     [rsp+arg_8], rbx
0x140058191  mov     [rsp+arg_10], rbp
0x140058196  push    rsi
0x140058197  push    rdi
0x140058198  push    r12
0x14005819a  push    r14
0x14005819c  push    r15
0x14005819e  sub     rsp, 30h
0x1400581a2  xor     eax, eax
0x1400581a4  mov     [rsp+58h+arg_0], 0
0x1400581ad  mov     rbp, rdx
0x1400581b0  mov     rbx, rcx
0x1400581b3  lea     r15d, [rax+1]
0x1400581b7  cmp     [rdx+30h], r15w
0x1400581bc  lea     r9d, [rax+2]
0x1400581c0  mov     [rcx+48h], r9w
0x1400581c5  cmovnz  rbp, rax
0x1400581c9  mov     rax, [rdx]
0x1400581cc  mov     [rcx+40h], rax
0x1400581d0  movups  xmm0, xmmword ptr [rdx+8]
0x1400581d4  mov     rax, [rcx]
0x1400581d7  movups  xmmword ptr [rcx+0ACh], xmm0
0x1400581de  movups  xmm1, xmmword ptr [rdx+14h]
0x1400581e2  or      [rcx+68h], r15w
0x1400581e7  movups  xmmword ptr [rcx+0B8h], xmm1
0x1400581ee  mov     r14, [rax+10h]
0x1400581f2  mov     rax, [rbx]
0x1400581f5  add     rax, 10h
0x1400581f9  cmp     r14, rax
0x1400581fc  jz      loc_1400582A8
0x140058202  test    [r14+40h], r9b
0x140058206  jz      short loc_140058274
0x140058208  or      [rbx+68h], r9w
0x14005820d  lea     rsi, [rbx+50h]
0x140058211  test    byte ptr [r14+40h], 4
0x140058216  lea     rdi, [rbx+64h]
0x14005821a  jnz     short loc_140058250
0x14005821c  mov     rax, [r14+28h]
0x140058220  mov     rdx, [rax+38h]
0x140058224  mov     eax, [rdx+20h]
0x140058227  or      [rdx+16h], r15w
0x14005822c  lea     rcx, [rax+rax*2]
0x140058230  mov     rax, [rbx+88h]
0x140058237  or      [rax+rcx*8+14h], r15w
0x14005823d  mov     eax, [rdx+1Ch]
0x140058240  xor     edx, edx
0x140058242  mov     ecx, [rsi]
0x140058244  add     eax, 7
0x140058247  add     ecx, 0FFFFFFF0h
0x14005824a  add     eax, ecx
0x14005824c  div     ecx
0x14005824e  add     [rdi], eax
0x140058250  test    byte ptr [r14+40h], 8
0x140058255  jnz     short loc_140058274
0x140058257  lea     r8, [rsp+58h+arg_0]; struct VMX_RAW_RECORD **
0x14005825c  mov     rdx, r14; struct VMX_RECORD *
0x14005825f  mov     rcx, rbx; this
0x140058262  call    ?CreateRawRecord@VMX_RAW_CONFIG@@QEAAJPEAVVMX_RECORD@@PEAPEAVVMX_RAW_RECORD@@@Z; VMX_RAW_CONFIG::CreateRawRecord(VMX_RECORD *,VMX_RAW_RECORD * *)
0x140058267  mov     r12d, eax
0x14005826a  test    eax, eax
0x14005826c  js      short loc_14005827C
0x14005826e  mov     r9d, 2
0x140058274  mov     r14, [r14]
0x140058277  jmp     loc_1400581F2
0x14005827c  mov     rcx, cs:WPP_GLOBAL_Control
0x140058283  lea     rax, WPP_GLOBAL_Control
0x14005828a  mov     r9d, 2
0x140058290  cmp     rcx, rax
0x140058293  jz      short loc_14005830F
0x140058295  mov     eax, [rcx+2Ch]
0x140058298  test    al, 40h
0x14005829a  jz      short loc_14005830F
0x14005829c  cmp     [rcx+29h], r9b
0x1400582a0  jb      short loc_14005830F
0x1400582a2  lea     edx, [r9+1Eh]
0x1400582a6  jmp     short loc_1400582F6
0x1400582a8  mov     eax, [rbx+54h]
0x1400582ab  lea     rsi, [rbx+50h]
0x1400582af  mov     ecx, [rbx+4Ch]
0x1400582b2  lea     rdi, [rbx+64h]
0x1400582b6  mov     r8d, [rdi]
0x1400582b9  xor     edx, edx
0x1400582bb  div     dword ptr [rsi]
0x1400582bd  sub     ecx, eax
0x1400582bf  sub     ecx, r8d
0x1400582c2  cmp     ecx, r8d
0x1400582c5  jbe     loc_1400583AF
0x1400582cb  mov     r12d, 0C0380001h
0x1400582d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400582d8  lea     rax, WPP_GLOBAL_Control
0x1400582df  cmp     rcx, rax
0x1400582e2  jz      short loc_14005830F
0x1400582e4  mov     eax, [rcx+2Ch]
0x1400582e7  test    al, 40h
0x1400582e9  jz      short loc_14005830F
0x1400582eb  cmp     [rcx+29h], r9b
0x1400582ef  jb      short loc_14005830F
0x1400582f1  mov     edx, 21h ; '!'
0x1400582f6  mov     rcx, [rcx+18h]
0x1400582fa  lea     r8, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids
0x140058301  mov     r9d, r12d
0x140058304  call    WPP_SF_d
0x140058309  mov     r9d, 2
0x14005830f  movups  xmm0, xmmword ptr [rbx+90h]
0x140058316  mov     rax, [rbx+38h]
0x14005831a  lea     rbp, [rbx+70h]
0x14005831e  movups  xmm1, xmmword ptr [rbx+9Ch]
0x140058325  mov     r14, [rbp+0]
0x140058329  movups  xmmword ptr [rbx+0ACh], xmm0
0x140058330  mov     [rbx+48h], r15w
0x140058335  movups  xmmword ptr [rbx+0B8h], xmm1
0x14005833c  mov     [rbx+40h], rax
0x140058340  jmp     short loc_14005839D
0x140058342  movzx   ecx, word ptr [r14+16h]
0x140058347  mov     r8, r14
0x14005834a  mov     rdx, r14; struct VMX_RAW_RECORD *
0x14005834d  mov     r14, [r14]
0x140058350  test    r9b, cl
0x140058353  jz      short loc_140058365
0x140058355  mov     rcx, rbx; this
0x140058358  call    ?DeleteRawRecord@VMX_RAW_CONFIG@@AEAAXPEAVVMX_RAW_RECORD@@@Z; VMX_RAW_CONFIG::DeleteRawRecord(VMX_RAW_RECORD *)
0x14005835d  mov     r9d, 2
0x140058363  jmp     short loc_14005839D
0x140058365  test    r15b, cl
0x140058368  jz      short loc_14005839D
0x14005836a  mov     eax, 0FFFEh
0x14005836f  xor     edx, edx
0x140058371  and     [r8+16h], ax
0x140058376  mov     eax, [r8+20h]
0x14005837a  lea     rcx, [rax+rax*2]
0x14005837e  mov     rax, [rbx+88h]
0x140058385  or      [rax+rcx*8+14h], r15w
0x14005838b  mov     eax, [r8+1Ch]
0x14005838f  mov     ecx, [rsi]
0x140058391  add     eax, 7
0x140058394  add     ecx, 0FFFFFFF0h
0x140058397  add     eax, ecx
0x140058399  div     ecx
0x14005839b  sub     [rdi], eax
0x14005839d  cmp     r14, rbp
0x1400583a0  jnz     short loc_140058342
0x1400583a2  mov     rcx, rbx; this
0x1400583a5  call    ?Untouch@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::Untouch(void)
0x1400583aa  mov     eax, r12d
0x1400583ad  jmp     short loc_14005842B
0x1400583af  mov     rax, rbp
0x1400583b2  mov     [rsp+58h+var_38], 0; unsigned __int8
0x1400583b7  neg     rax
0x1400583ba  mov     rcx, rbx; this
0x1400583bd  sbb     rdx, rdx
0x1400583c0  and     rdx, rbp; struct VMX_CHANGE_IDENTITY_TRANSACTION *
0x1400583c3  test    rbp, rbp
0x1400583c6  setz    r9b; unsigned __int8
0x1400583ca  xor     r8d, r8d; struct VMX_CONFIG_COPY *
0x1400583cd  call    ?IncrementalWrite@VMX_RAW_CONFIG@@AEAAJPEAVVMX_CHANGE_IDENTITY_TRANSACTION@@PEAVVMX_CONFIG_COPY@@EE@Z; VMX_RAW_CONFIG::IncrementalWrite(VMX_CHANGE_IDENTITY_TRANSACTION *,VMX_CONFIG_COPY *,uchar,uchar)
0x1400583d2  mov     rcx, rbx; this
0x1400583d5  call    ?Untouch@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::Untouch(void)
0x1400583da  or      [rbx+68h], r15w
0x1400583df  mov     word ptr [rbx+48h], 3
0x1400583e5  test    rbp, rbp
0x1400583e8  jz      short loc_14005840B
0x1400583ea  movups  xmm0, xmmword ptr [rbp+70h]
0x1400583ee  lea     r8, [rbp+80h]; pszSrc
0x1400583f5  mov     edx, 20h ; ' '; cbDest
0x1400583fa  lea     rcx, [rbx+18h]; pszDest
0x1400583fe  movdqu  xmmword ptr [rbx+8], xmm0
0x140058403  call    RtlStringCbCopyA
0x140058408  xor     r15b, r15b
0x14005840b  mov     r9b, r15b; unsigned __int8
0x14005840e  mov     [rsp+58h+var_38], 0; unsigned __int8
0x140058413  xor     r8d, r8d; struct VMX_CONFIG_COPY *
0x140058416  mov     rdx, rbp; struct VMX_CHANGE_IDENTITY_TRANSACTION *
0x140058419  mov     rcx, rbx; this
0x14005841c  call    ?IncrementalWrite@VMX_RAW_CONFIG@@AEAAJPEAVVMX_CHANGE_IDENTITY_TRANSACTION@@PEAVVMX_CONFIG_COPY@@EE@Z; VMX_RAW_CONFIG::IncrementalWrite(VMX_CHANGE_IDENTITY_TRANSACTION *,VMX_CONFIG_COPY *,uchar,uchar)
0x140058421  mov     rcx, rbx; this
0x140058424  call    ?Untouch@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::Untouch(void)
0x140058429  xor     eax, eax
0x14005842b  mov     rbx, [rsp+58h+arg_8]
0x140058430  mov     rbp, [rsp+58h+arg_10]
0x140058435  add     rsp, 30h
0x140058439  pop     r15
0x14005843b  pop     r14
0x14005843d  pop     r12
0x14005843f  pop     rdi
0x140058440  pop     rsi
0x140058441  retn
```
