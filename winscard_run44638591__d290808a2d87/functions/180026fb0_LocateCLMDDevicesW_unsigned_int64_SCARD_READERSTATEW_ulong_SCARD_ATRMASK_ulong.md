# LocateCLMDDevicesW(unsigned __int64,SCARD_READERSTATEW *,ulong,_SCARD_ATRMASK * *,ulong *)

- ea: `0x180026fb0`
- end: `0x18002728b`
- name: `?LocateCLMDDevicesW@@YAX_KPEAUSCARD_READERSTATEW@@KPEAPEAU_SCARD_ATRMASK@@PEAK@Z`
- size: `731`
- prototype: `void __fastcall(unsigned __int64, struct SCARD_READERSTATEW *, unsigned int, struct _SCARD_ATRMASK **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180028300`

## callees

- `0x180005de0`
- `0x18001b9b8`
- `0x18001b9c4`
- `0x18001ba04`
- `0x18001c7a8`
- `0x180026fb0`
- `0x180028ed8`
- `0x18002ef20`
- `0x18002ef2c`
- `0x18002ef38`

## pseudocode

```c
void __fastcall LocateCLMDDevicesW(
        SCARDCONTEXT a1,
        struct SCARD_READERSTATEW *a2,
        unsigned int a3,
        struct _SCARD_ATRMASK **a4,
        unsigned int *a5)
{
  struct _SCARD_ATRMASK *v5; // r12
  LONG v6; // esi
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v7; // rax
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v8; // r14
  unsigned int v9; // ebx
  __int64 i; // rax
  unsigned __int64 v11; // rax
  char *v12; // rbx
  unsigned __int64 v13; // rax
  __int64 v14; // rbx
  unsigned int v15; // [rsp+30h] [rbp-68h]
  int v16; // [rsp+34h] [rbp-64h]
  int v17; // [rsp+38h] [rbp-60h]
  LONG pExceptionObject; // [rsp+3Ch] [rbp-5Ch] BYREF
  void *Buf2; // [rsp+40h] [rbp-58h]
  void *v20; // [rsp+48h] [rbp-50h] BYREF
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v21; // [rsp+50h] [rbp-48h]

  Buf2 = 0;
  v20 = 0;
  if ( !a1 || !a2 || !a4 || !a5 )
  {
    v6 = -2146435041;
LABEL_37:
    pExceptionObject = v6;
    throw (ulong *)&pExceptionObject;
  }
  v5 = (struct _SCARD_ATRMASK *)operator new[](saturated_mul(a3, 0x4Cu));
  if ( !v5 )
  {
    v6 = -2146435066;
    goto LABEL_37;
  }
  v7 = (struct $B80B7D01E79FADDB4AAC58DE22BC823F *)operator new(0x40u);
  v8 = v7;
  v21 = v7;
  if ( v7 )
  {
    v6 = 0;
    v16 = 0;
    v9 = 0;
    v15 = 0;
    memset_0(v7, 0, sizeof(struct $B80B7D01E79FADDB4AAC58DE22BC823F));
    for ( i = 0; ; i = (unsigned int)(v17 + 1) )
    {
      v17 = i;
      if ( (unsigned int)i >= a3 )
        break;
      v8->szReader = a2[i].szReader;
      v8->dwCurrentState = 0;
      v6 = SCardGetStatusChangeW(a1, 0, v8, 1u);
      v16 = v6;
      if ( v6 )
        goto LABEL_38;
      if ( v8->cbAtr && !(unsigned int)CidUtilGetDeviceIdByReaderName(v8->szReader, (__int64)&v20) )
      {
        if ( Buf2 )
        {
          v11 = -1;
          do
            ++v11;
          while ( *((_WORD *)Buf2 + v11) );
          if ( v11 > 0xD
            && !memcmp_0(L"SCFILTER\\CID_", Buf2, 0x1Au)
            && (!memcmp_0(L"2777BE07-6993-4513-BD80-C184FCB0AB2D", (char *)Buf2 + 26, 0x4Au)
             || !memcmp_0(L"E2F748F9-DB8B-4C08-A258-583D8955D94A", (char *)Buf2 + 26, 0x4Au)) )
          {
            goto LABEL_28;
          }
        }
        v12 = (char *)v20;
        if ( !v20 )
          goto LABEL_29;
        v13 = -1;
        do
          ++v13;
        while ( *((_WORD *)v20 + v13) );
        if ( v13 > 0xD
          && !memcmp_0(L"SCFILTER\\CID_", v20, 0x1Au)
          && (!memcmp_0(L"2777BE07-6993-4513-BD80-C184FCB0AB2D", v12 + 26, 0x4Au)
           || !memcmp_0(L"E2F748F9-DB8B-4C08-A258-583D8955D94A", v12 + 26, 0x4Au)) )
        {
LABEL_28:
          v14 = v15;
          memcpy_0(v5[v14].rgbAtr, v8->rgbAtr, v8->cbAtr);
          memset_0(v5[v14].rgbMask, 255, v8->cbAtr);
          v5[v14].cbAtr = v8->cbAtr;
          v9 = ++v15;
        }
        else
        {
LABEL_29:
          v9 = v15;
        }
      }
    }
    *a4 = v5;
    *a5 = v9;
    goto LABEL_43;
  }
  v6 = -2146435066;
  v16 = -2146435066;
LABEL_38:
  try
  {
    operator delete(v5);
  }
  catch ( ... )
  {
    v6 = v16;
    v8 = v21;
  }
  if ( v8 )
  {
LABEL_43:
    try
    {
      operator delete(v8);
    }
    catch ( ... )
    {
      v6 = v16;
    }
  }
  if ( v6 )
    goto LABEL_37;
}

```

## disassembly

```asm
0x180026fb0  mov     r11, rsp
0x180026fb3  mov     [r11+20h], r9
0x180026fb7  mov     [r11+18h], r8d
0x180026fbb  mov     [r11+10h], rdx
0x180026fbf  mov     [r11+8], rcx
0x180026fc3  push    rbx
0x180026fc4  push    rsi
0x180026fc5  push    rdi
0x180026fc6  push    r12
0x180026fc8  push    r13
0x180026fca  push    r14
0x180026fcc  sub     rsp, 68h
0x180026fd0  mov     rbx, r9
0x180026fd3  mov     rax, rdx
0x180026fd6  xor     edi, edi
0x180026fd8  mov     [r11-58h], rdi
0x180026fdc  mov     [r11-50h], rdi
0x180026fe0  test    rcx, rcx
0x180026fe3  jz      loc_180027270
0x180026fe9  test    rax, rax
0x180026fec  jz      loc_180027270
0x180026ff2  test    rbx, rbx
0x180026ff5  jz      loc_180027270
0x180026ffb  mov     r13, [rsp+98h+arg_20]
0x180027003  test    r13, r13
0x180027006  jz      loc_180027270
0x18002700c  mov     ecx, r8d
0x18002700f  lea     eax, [rdi+4Ch]
0x180027012  mul     rcx
0x180027015  lea     rcx, [rdi-1]
0x180027019  cmovb   rax, rcx
0x18002701d  mov     rcx, rax; unsigned __int64
0x180027020  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180027025  mov     r12, rax
0x180027028  test    rax, rax
0x18002702b  jnz     short loc_180027037
0x18002702d  mov     esi, 80100006h
0x180027032  jmp     loc_180027275
0x180027037  mov     ecx, 40h ; '@'; Size
0x18002703c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027041  mov     r14, rax
0x180027044  mov     [rsp+98h+var_48], rax
0x180027049  test    rax, rax
0x18002704c  jnz     short loc_180027065
0x18002704e  mov     esi, 80100006h
0x180027053  mov     [rsp+98h+var_64], esi
0x180027057  mov     rcx, r12; void *
0x18002705a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002705f  nop
0x180027060  jmp     loc_180027234
0x180027065  mov     esi, edi
0x180027067  mov     [rsp+98h+var_64], edi
0x18002706b  mov     ebx, edi
0x18002706d  mov     [rsp+98h+var_68], ebx
0x180027071  xor     edx, edx; Val
0x180027073  lea     r8d, [rdx+40h]; Size
0x180027077  mov     rcx, r14; void *
0x18002707a  call    memset_0
0x18002707f  mov     eax, edi
0x180027081  mov     [rsp+98h+var_60], eax
0x180027085  cmp     eax, [rsp+98h+arg_10]
0x18002708c  jnb     loc_18002723B
0x180027092  shl     rax, 6
0x180027096  mov     rcx, [rsp+98h+arg_8]
0x18002709e  mov     rax, [rax+rcx]
0x1800270a2  mov     [r14], rax
0x1800270a5  mov     [r14+10h], edi
0x1800270a9  mov     r9d, 1; cReaders
0x1800270af  mov     r8, r14; rgReaderStates
0x1800270b2  xor     edx, edx; dwTimeout
0x1800270b4  mov     rcx, [rsp+98h+hContext]; hContext
0x1800270bc  call    SCardGetStatusChangeW
0x1800270c1  mov     esi, eax
0x1800270c3  mov     [rsp+98h+var_64], eax
0x1800270c7  test    eax, eax
0x1800270c9  jnz     short loc_180027057
0x1800270cb  mov     r8d, [r14+18h]
0x1800270cf  test    r8d, r8d
0x1800270d2  jz      loc_180027220
0x1800270d8  lea     rdx, [r14+1Ch]
0x1800270dc  lea     rcx, [rsp+98h+var_50]
0x1800270e1  mov     [rsp+98h+var_78], rcx; __int64
0x1800270e6  lea     r9, [rsp+98h+Buf2]
0x1800270eb  mov     rcx, [r14]; szReader
0x1800270ee  call    CidUtilGetDeviceIdByReaderName
0x1800270f3  test    eax, eax
0x1800270f5  jnz     loc_180027220
0x1800270fb  mov     rbx, [rsp+98h+Buf2]
0x180027100  test    rbx, rbx
0x180027103  jz      short loc_180027167
0x180027105  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027109  inc     rax
0x18002710c  cmp     [rbx+rax*2], di
0x180027110  jnz     short loc_180027109
0x180027112  cmp     rax, 0Dh
0x180027116  jbe     short loc_180027167
0x180027118  mov     r8d, 1Ah; Size
0x18002711e  mov     rdx, rbx; Buf2
0x180027121  lea     rcx, aScfilterCid; "SCFILTER\\CID_"
0x180027128  call    memcmp_0
0x18002712d  test    eax, eax
0x18002712f  jnz     short loc_180027167
0x180027131  lea     r8d, [rax+4Ah]; Size
0x180027135  lea     rdx, [rbx+1Ah]; Buf2
0x180027139  lea     rcx, a2777be07699345; "2777BE07-6993-4513-BD80-C184FCB0AB2D"
0x180027140  call    memcmp_0
0x180027145  test    eax, eax
0x180027147  jz      loc_1800271D7
0x18002714d  mov     r8d, 4Ah ; 'J'; Size
0x180027153  lea     rdx, [rbx+1Ah]; Buf2
0x180027157  lea     rcx, aE2f748f9Db8b4c; "E2F748F9-DB8B-4C08-A258-583D8955D94A"
0x18002715e  call    memcmp_0
0x180027163  test    eax, eax
0x180027165  jz      short loc_1800271D7
0x180027167  mov     rbx, [rsp+98h+var_50]
0x18002716c  test    rbx, rbx
0x18002716f  jz      loc_18002721C
0x180027175  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027179  inc     rax
0x18002717c  cmp     [rbx+rax*2], di
0x180027180  jnz     short loc_180027179
0x180027182  cmp     rax, 0Dh
0x180027186  jbe     loc_18002721C
0x18002718c  mov     r8d, 1Ah; Size
0x180027192  mov     rdx, rbx; Buf2
0x180027195  lea     rcx, aScfilterCid; "SCFILTER\\CID_"
0x18002719c  call    memcmp_0
0x1800271a1  test    eax, eax
0x1800271a3  jnz     short loc_18002721C
0x1800271a5  lea     r8d, [rax+4Ah]; Size
0x1800271a9  lea     rdx, [rbx+1Ah]; Buf2
0x1800271ad  lea     rcx, a2777be07699345; "2777BE07-6993-4513-BD80-C184FCB0AB2D"
0x1800271b4  call    memcmp_0
0x1800271b9  test    eax, eax
0x1800271bb  jz      short loc_1800271D7
0x1800271bd  mov     r8d, 4Ah ; 'J'; Size
0x1800271c3  lea     rdx, [rbx+1Ah]; Buf2
0x1800271c7  lea     rcx, aE2f748f9Db8b4c; "E2F748F9-DB8B-4C08-A258-583D8955D94A"
0x1800271ce  call    memcmp_0
0x1800271d3  test    eax, eax
0x1800271d5  jnz     short loc_18002721C
0x1800271d7  mov     eax, [rsp+98h+var_68]
0x1800271db  imul    rbx, rax, 4Ch ; 'L'
0x1800271df  mov     r8d, [r14+18h]; Size
0x1800271e3  lea     rcx, [rbx+4]
0x1800271e7  add     rcx, r12; void *
0x1800271ea  lea     rdx, [r14+1Ch]; Src
0x1800271ee  call    memcpy_0
0x1800271f3  mov     r8d, [r14+18h]; Size
0x1800271f7  lea     rcx, [rbx+28h]
0x1800271fb  add     rcx, r12; void *
0x1800271fe  mov     edx, 0FFh; Val
0x180027203  call    memset_0
0x180027208  mov     eax, [r14+18h]
0x18002720c  mov     [rbx+r12], eax
0x180027210  mov     ebx, [rsp+98h+var_68]
0x180027214  inc     ebx
0x180027216  mov     [rsp+98h+var_68], ebx
0x18002721a  jmp     short loc_180027220
0x18002721c  mov     ebx, [rsp+98h+var_68]
0x180027220  mov     eax, [rsp+98h+var_60]
0x180027224  inc     eax
0x180027226  jmp     loc_180027081
0x18002722b  mov     esi, [rsp+98h+var_64]
0x18002722f  mov     r14, [rsp+98h+var_48]
0x180027234  test    r14, r14
0x180027237  jz      short loc_18002725E
0x180027239  jmp     short loc_18002724A
0x18002723b  mov     rax, [rsp+98h+arg_18]
0x180027243  mov     [rax], r12
0x180027246  mov     [r13+0], ebx
0x18002724a  mov     edx, 40h ; '@'; unsigned __int64
0x18002724f  mov     rcx, r14; void *
0x180027252  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027257  nop
0x180027258  jmp     short loc_18002725E
0x18002725a  mov     esi, [rsp+98h+var_64]
0x18002725e  test    esi, esi
0x180027260  jnz     short loc_180027275
0x180027262  add     rsp, 68h
0x180027266  pop     r14
0x180027268  pop     r13
0x18002726a  pop     r12
0x18002726c  pop     rdi
0x18002726d  pop     rsi
0x18002726e  pop     rbx
0x18002726f  retn
0x180027270  mov     esi, 8010001Fh
0x180027275  mov     [rsp+98h+pExceptionObject], esi
0x180027279  lea     rdx, _TI1K; pThrowInfo
0x180027280  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180027285  call    _CxxThrowException_0
```
