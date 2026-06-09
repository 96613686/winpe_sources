# CTsUrbResultSelectConfig::TsUrbResultInitialize(CSimpleHash *,CSimpleHash *,CSimpleHash *,_TS_URB_RESULT *,ulong,ulong *)

- ea: `0x140005f20`
- end: `0x140006159`
- name: `?TsUrbResultInitialize@CTsUrbResultSelectConfig@@EEAAXPEAVCSimpleHash@@00PEAT_TS_URB_RESULT@@KPEAK@Z`
- size: `569`
- prototype: `void(CTsUrbResultSelectConfig *__hidden this, struct CSimpleHash *, struct CSimpleHash *, struct CSimpleHash *, union _TS_URB_RESULT *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000464c`
- `0x140005f20`

## pseudocode

```c
void __fastcall CTsUrbResultSelectConfig::TsUrbResultInitialize(
        CTsUrbResultSelectConfig *this,
        struct CSimpleHash *a2,
        struct CSimpleHash *a3,
        struct CSimpleHash *a4,
        union _TS_URB_RESULT *a5,
        unsigned int a6,
        unsigned int *a7)
{
  bool v7; // cf
  __int64 v10; // rbx
  union _TS_URB_RESULT *v11; // rsi
  unsigned int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  unsigned __int16 *v15; // rdi
  char *v16; // r12
  unsigned __int16 *v17; // rbx
  int v18; // r14d
  unsigned __int64 v19; // rcx
  unsigned int v20; // ecx
  unsigned int v21; // eax
  __int64 i; // rbp
  CSimpleHash *v23; // rcx
  __int64 v24; // r15
  unsigned int v25; // eax
  unsigned int v26; // [rsp+60h] [rbp+8h] BYREF
  CSimpleHash *v27; // [rsp+78h] [rbp+20h]

  v27 = a4;
  v7 = a6 < 0x10;
  v26 = 0;
  *a7 = 0;
  if ( !v7 )
  {
    v10 = *((_QWORD *)this + 212);
    v11 = a5;
    *(_WORD *)a5 = *((_WORD *)this + 853);
    *((_DWORD *)v11 + 1) = *(_DWORD *)(v10 + 4);
    if ( (int)CSimpleHash::AddItemDuplicateOk(a2, *(void **)(v10 + 32), &v26) < 0 )
      goto LABEL_9;
    v12 = v26 <= 0xFFFF ? v26 | 0xFFFF0000 : 0;
    *((_DWORD *)v11 + 2) = v12;
    if ( !v12 )
      goto LABEL_9;
    v13 = *(_QWORD *)(v10 + 24);
    v14 = *((unsigned __int8 *)this + 1720);
    if ( v13 )
    {
      if ( (_BYTE)v14 != *(_BYTE *)(v13 + 4) )
      {
LABEL_9:
        *(_WORD *)v11 = 8;
        *((_DWORD *)v11 + 1) = -2147482880;
        return;
      }
    }
    else if ( (_BYTE)v14 != 1 )
    {
      goto LABEL_9;
    }
    v15 = (unsigned __int16 *)((char *)v11 + 16);
    v16 = (char *)v11 + a6;
    *((_DWORD *)v11 + 3) = v14;
    v17 = (unsigned __int16 *)(v10 + 40);
    v18 = 0;
    if ( v14 )
    {
      while ( 1 )
      {
        v19 = 20LL * *((unsigned int *)v17 + 4);
        if ( v19 > 0xFFFFFFFF )
          goto LABEL_9;
        v20 = v19 + 16;
        if ( v20 - 16 > 0xFFEF )
          goto LABEL_9;
        if ( (char *)v15 + v20 > v16 )
          goto LABEL_9;
        *v15 = v20;
        *((_BYTE *)v15 + 2) = *((_BYTE *)v17 + 2);
        *((_BYTE *)v15 + 3) = *((_BYTE *)v17 + 3);
        *((_DWORD *)v15 + 3) = *((_DWORD *)v17 + 4);
        *((_BYTE *)v15 + 4) = *((_BYTE *)v17 + 4);
        *((_BYTE *)v15 + 5) = *((_BYTE *)v17 + 5);
        *((_BYTE *)v15 + 6) = *((_BYTE *)v17 + 6);
        *((_DWORD *)v15 + 3) = *((_DWORD *)v17 + 4);
        if ( (int)CSimpleHash::AddItemDuplicateOk(a3, *((void **)v17 + 1), &v26) < 0 )
          goto LABEL_9;
        v21 = v26 <= 0xFFFF ? v26 | 0xFFFF0000 : 0;
        *((_DWORD *)v15 + 2) = v21;
        if ( !v21 )
          goto LABEL_9;
        for ( i = 0; (unsigned int)i < *((_DWORD *)v17 + 4); i = (unsigned int)(i + 1) )
        {
          v23 = v27;
          v24 = 5 * i;
          v15[2 * v24 + 8] = v17[12 * i + 12];
          LOBYTE(v15[2 * v24 + 9]) = v17[12 * i + 13];
          HIBYTE(v15[2 * v24 + 9]) = HIBYTE(v17[12 * i + 13]);
          *(_DWORD *)&v15[2 * v24 + 10] = *(_DWORD *)&v17[12 * i + 14];
          *(_DWORD *)&v15[2 * v24 + 14] = *(_DWORD *)&v17[12 * i + 20];
          *(_DWORD *)&v15[2 * v24 + 16] = *(_DWORD *)&v17[12 * i + 22];
          if ( (int)CSimpleHash::AddItemDuplicateOk(v23, *(void **)&v17[12 * i + 16], &v26) < 0 )
            goto LABEL_9;
          v25 = v26 <= 0xFFFF ? v26 | 0xFFFF0000 : 0;
          *(_DWORD *)&v15[10 * i + 12] = v25;
          if ( !v25 )
            goto LABEL_9;
        }
        if ( (unsigned int)++v18 >= *((_DWORD *)v11 + 3) )
          return;
        v17 = (unsigned __int16 *)((char *)v17 + *v17);
        v15 = (unsigned __int16 *)((char *)v15 + *v15);
      }
    }
  }
}

```

## disassembly

```asm
0x140005f20  mov     [rsp+arg_8], rbx
0x140005f25  mov     [rsp+arg_18], r9
0x140005f2a  push    rbp
0x140005f2b  push    rsi
0x140005f2c  push    rdi
0x140005f2d  push    r12
0x140005f2f  push    r13
0x140005f31  push    r14
0x140005f33  push    r15
0x140005f35  sub     rsp, 20h
0x140005f39  cmp     [rsp+58h+arg_28], 10h
0x140005f41  mov     r13, r8
0x140005f44  mov     rax, [rsp+58h+arg_30]
0x140005f4c  mov     r10, rdx
0x140005f4f  mov     rdi, rcx
0x140005f52  mov     [rsp+58h+arg_0], 0
0x140005f5a  mov     dword ptr [rax], 0
0x140005f60  jb      short loc_140005FD2
0x140005f62  mov     rbx, [rcx+6A0h]
0x140005f69  lea     r8, [rsp+58h+arg_0]; unsigned int *
0x140005f6e  movzx   eax, word ptr [rcx+6AAh]
0x140005f75  mov     rcx, r10; this
0x140005f78  mov     rsi, [rsp+58h+arg_20]
0x140005f80  mov     [rsi], ax
0x140005f83  mov     eax, [rbx+4]
0x140005f86  mov     [rsi+4], eax
0x140005f89  mov     rdx, [rbx+20h]; void *
0x140005f8d  call    ?AddItemDuplicateOk@CSimpleHash@@QEAAJPEAXPEAK@Z; CSimpleHash::AddItemDuplicateOk(void *,ulong *)
0x140005f92  test    eax, eax
0x140005f94  js      short loc_140005FC6
0x140005f96  mov     eax, [rsp+58h+arg_0]
0x140005f9a  cmp     eax, 0FFFFh
0x140005f9f  jbe     short loc_140005FA5
0x140005fa1  xor     eax, eax
0x140005fa3  jmp     short loc_140005FAA
0x140005fa5  or      eax, 0FFFF0000h
0x140005faa  mov     [rsi+8], eax
0x140005fad  test    eax, eax
0x140005faf  jz      short loc_140005FC6
0x140005fb1  mov     rcx, [rbx+18h]
0x140005fb5  movzx   eax, byte ptr [rdi+6B8h]
0x140005fbc  test    rcx, rcx
0x140005fbf  jz      short loc_140005FE8
0x140005fc1  cmp     al, [rcx+4]
0x140005fc4  jz      short loc_140005FEC
0x140005fc6  mov     word ptr [rsi], 8
0x140005fcb  mov     dword ptr [rsi+4], 80000300h
0x140005fd2  mov     rbx, [rsp+58h+arg_8]
0x140005fd7  add     rsp, 20h
0x140005fdb  pop     r15
0x140005fdd  pop     r14
0x140005fdf  pop     r13
0x140005fe1  pop     r12
0x140005fe3  pop     rdi
0x140005fe4  pop     rsi
0x140005fe5  pop     rbp
0x140005fe6  retn
0x140005fe8  cmp     al, 1
0x140005fea  jnz     short loc_140005FC6
0x140005fec  mov     r12d, [rsp+58h+arg_28]
0x140005ff4  lea     rdi, [rsi+10h]
0x140005ff8  add     r12, rsi
0x140005ffb  mov     [rsi+0Ch], eax
0x140005ffe  add     rbx, 28h ; '('
0x140006002  xor     r14d, r14d
0x140006005  test    eax, eax
0x140006007  jz      short loc_140005FD2
0x140006009  mov     eax, [rbx+10h]
0x14000600c  lea     rcx, [rax+rax*4]
0x140006010  mov     eax, 0FFFFFFFFh
0x140006015  shl     rcx, 2
0x140006019  cmp     rcx, rax
0x14000601c  ja      short loc_140005FC6
0x14000601e  add     ecx, 10h
0x140006021  lea     eax, [rcx-10h]
0x140006024  cmp     eax, 0FFEFh
0x140006029  ja      short loc_140005FC6
0x14000602b  mov     eax, ecx
0x14000602d  add     rax, rdi
0x140006030  cmp     rax, r12
0x140006033  ja      short loc_140005FC6
0x140006035  mov     [rdi], cx
0x140006038  lea     r8, [rsp+58h+arg_0]; unsigned int *
0x14000603d  mov     al, [rbx+2]
0x140006040  mov     rcx, r13; this
0x140006043  mov     [rdi+2], al
0x140006046  mov     al, [rbx+3]
0x140006049  mov     [rdi+3], al
0x14000604c  mov     eax, [rbx+10h]
0x14000604f  mov     [rdi+0Ch], eax
0x140006052  mov     al, [rbx+4]
0x140006055  mov     [rdi+4], al
0x140006058  mov     al, [rbx+5]
0x14000605b  mov     [rdi+5], al
0x14000605e  mov     al, [rbx+6]
0x140006061  mov     [rdi+6], al
0x140006064  mov     eax, [rbx+10h]
0x140006067  mov     [rdi+0Ch], eax
0x14000606a  mov     rdx, [rbx+8]; void *
0x14000606e  call    ?AddItemDuplicateOk@CSimpleHash@@QEAAJPEAXPEAK@Z; CSimpleHash::AddItemDuplicateOk(void *,ulong *)
0x140006073  test    eax, eax
0x140006075  js      loc_140005FC6
0x14000607b  mov     eax, [rsp+58h+arg_0]
0x14000607f  cmp     eax, 0FFFFh
0x140006084  jbe     short loc_14000608A
0x140006086  xor     eax, eax
0x140006088  jmp     short loc_14000608F
0x14000608a  or      eax, 0FFFF0000h
0x14000608f  mov     [rdi+8], eax
0x140006092  test    eax, eax
0x140006094  jz      loc_140005FC6
0x14000609a  xor     ebp, ebp
0x14000609c  cmp     [rbx+10h], ebp
0x14000609f  jbe     loc_14000613B
0x1400060a5  mov     rcx, [rsp+58h+arg_18]; this
0x1400060aa  lea     rdx, ds:0[rbp*2]
0x1400060b2  add     rdx, rbp
0x1400060b5  lea     r15, ds:0[rbp*4]
0x1400060bd  add     r15, rbp
0x1400060c0  lea     r8, [rsp+58h+arg_0]; unsigned int *
0x1400060c5  movzx   eax, word ptr [rbx+rdx*8+18h]
0x1400060ca  mov     [rdi+r15*4+10h], ax
0x1400060d0  mov     al, [rbx+rdx*8+1Ah]
0x1400060d4  mov     [rdi+r15*4+12h], al
0x1400060d9  mov     al, [rbx+rdx*8+1Bh]
0x1400060dd  mov     [rdi+r15*4+13h], al
0x1400060e2  mov     eax, [rbx+rdx*8+1Ch]
0x1400060e6  mov     [rdi+r15*4+14h], eax
0x1400060eb  mov     eax, [rbx+rdx*8+28h]
0x1400060ef  mov     [rdi+r15*4+1Ch], eax
0x1400060f4  mov     eax, [rbx+rdx*8+2Ch]
0x1400060f8  mov     [rdi+r15*4+20h], eax
0x1400060fd  mov     rdx, [rbx+rdx*8+20h]; void *
0x140006102  call    ?AddItemDuplicateOk@CSimpleHash@@QEAAJPEAXPEAK@Z; CSimpleHash::AddItemDuplicateOk(void *,ulong *)
0x140006107  test    eax, eax
0x140006109  js      loc_140005FC6
0x14000610f  mov     eax, [rsp+58h+arg_0]
0x140006113  cmp     eax, 0FFFFh
0x140006118  jbe     short loc_14000611E
0x14000611a  xor     eax, eax
0x14000611c  jmp     short loc_140006123
0x14000611e  or      eax, 0FFFF0000h
0x140006123  mov     [rdi+r15*4+18h], eax
0x140006128  test    eax, eax
0x14000612a  jz      loc_140005FC6
0x140006130  inc     ebp
0x140006132  cmp     ebp, [rbx+10h]
0x140006135  jb      loc_1400060A5
0x14000613b  inc     r14d
0x14000613e  cmp     r14d, [rsi+0Ch]
0x140006142  jnb     loc_140005FD2
0x140006148  movzx   eax, word ptr [rbx]
0x14000614b  add     rbx, rax
0x14000614e  movzx   eax, word ptr [rdi]
0x140006151  add     rdi, rax
0x140006154  jmp     loc_140006009
```
