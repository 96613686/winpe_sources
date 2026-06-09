# ListCLMDCards(unsigned __int64,uchar const *,CBuffer &,int)

- ea: `0x180002e84`
- end: `0x180003427`
- name: `?ListCLMDCards@@YAX_KPEBEAEAVCBuffer@@H@Z`
- size: `1443`
- prototype: `void(unsigned __int64, const unsigned __int8 *, struct CBuffer *, int)`
- caller_count: `2`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180002d40`
- `0x180025eb0`

## callees

- `0x180002e84`
- `0x1800040d0`
- `0x180004ca0`
- `0x180005de0`
- `0x180006910`
- `0x180007f40`
- `0x18000e3d0`
- `0x18000e980`
- `0x180015c60`
- `0x1800161f4`
- `0x180016890`
- `0x1800195c8`
- `0x18001c7a8`
- `0x18001e75c`
- `0x18001f340`
- `0x18002898c`
- `0x180028ed8`
- `0x18002ef20`
- `0x18002ef2c`

## string_xrefs

- `0x180002ef5`: `SOFTWARE\Microsoft\Cryptography\Calais\PIV Device ATR Cache`
- `0x18000330d`: `SOFTWARE\Microsoft\Cryptography\Calais\PIV Device ATR Cache`
- `0x180002f2f`: `SOFTWARE\Microsoft\Cryptography\Calais\IDMP ATR Cache`
- `0x180003378`: `SOFTWARE\Microsoft\Cryptography\Calais\IDMP ATR Cache`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
void __fastcall ListCLMDCards(SCARDCONTEXT a1, const unsigned __int8 *a2, struct CBuffer *a3, int a4)
{
  CBuffer *v5; // r15
  LONG v7; // edi
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v8; // r14
  BOOL v9; // r12d
  struct CBuffer *v10; // rcx
  const unsigned __int16 *v11; // rdx
  const char *v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 i; // rcx
  _WORD *v16; // r8
  __int64 v17; // rcx
  unsigned __int64 v18; // rdi
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v19; // rax
  DWORD v20; // r13d
  __int64 v21; // rcx
  __int64 v22; // rdx
  char *v23; // r8
  const WCHAR *v24; // r9
  unsigned __int64 v25; // rax
  __int64 v26; // rax
  unsigned __int64 v27; // r12
  unsigned int *v28; // rax
  char *v29; // r12
  unsigned __int64 v30; // rax
  char *v31; // r12
  unsigned __int64 v32; // rax
  const unsigned __int16 *v33; // r8
  int v34; // [rsp+30h] [rbp-A8h]
  LONG v35; // [rsp+34h] [rbp-A4h]
  int v36; // [rsp+38h] [rbp-A0h]
  int v37; // [rsp+40h] [rbp-98h]
  DWORD pcchReaders[2]; // [rsp+48h] [rbp-90h] BYREF
  SCARDCONTEXT phContext; // [rsp+50h] [rbp-88h] BYREF
  int v40; // [rsp+58h] [rbp-80h]
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v41; // [rsp+60h] [rbp-78h]
  WCHAR mszReaders[4]; // [rsp+68h] [rbp-70h] BYREF
  LONG pExceptionObject; // [rsp+70h] [rbp-68h] BYREF
  DWORD *v44; // [rsp+78h] [rbp-60h]
  BYTE *lpData; // [rsp+80h] [rbp-58h]
  void *Buf2; // [rsp+88h] [rbp-50h]
  void *v47; // [rsp+90h] [rbp-48h] BYREF

  v5 = a3;
  *(_QWORD *)mszReaders = 0;
  *(_QWORD *)pcchReaders = 0xFFFFFFFFLL;
  v7 = 0;
  v8 = 0;
  v41 = 0;
  Buf2 = 0;
  v47 = 0;
  v9 = 0;
  v34 = 0;
  phContext = 0;
  v40 = 0;
  if ( !a2 )
  {
    v7 = -2146435041;
    goto LABEL_80;
  }
  if ( !(unsigned int)I_MatchClmdOpt(a2, L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\PIV Device ATR Cache") )
  {
    CBuffer::Clear(v5);
    v10 = v5;
    if ( a4 )
    {
      v11 = L"Identity Device (NIST SP 800-73 [PIV])";
LABEL_6:
      MStrAdd(v10, v11);
      goto LABEL_68;
    }
    v12 = "Identity Device (NIST SP 800-73 [PIV])";
LABEL_12:
    MStrAdd(v10, v12);
    goto LABEL_68;
  }
  if ( !(unsigned int)I_MatchClmdOpt(a2, L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\IDMP ATR Cache") )
  {
    CBuffer::Clear(v5);
    v10 = v5;
    if ( a4 )
    {
      v11 = L"Identity Device (Microsoft Generic Profile)";
      goto LABEL_6;
    }
    v12 = "Identity Device (Microsoft Generic Profile)";
    goto LABEL_12;
  }
  if ( a1 )
  {
    phContext = a1;
  }
  else
  {
    v7 = SCardEstablishContext(2u, 0, 0, &phContext);
    if ( v7 )
      goto LABEL_68;
    v40 = 1;
  }
  v7 = SCardListReadersW(phContext, 0, mszReaders, pcchReaders);
  if ( !v7 )
  {
    *(_QWORD *)pcchReaders = 0;
    v13 = 0;
    v14 = 0;
    for ( i = 0; ; i = v14 )
    {
      v16 = (_WORD *)(*(_QWORD *)mszReaders + 2 * i);
      if ( !*v16 )
        break;
      ++v13;
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
      v14 += v17 + 1;
      *(_QWORD *)pcchReaders = v14;
    }
    if ( !v13 )
    {
      v7 = -2146435026;
      goto LABEL_68;
    }
    v18 = (unsigned __int64)v13 << 6;
    v19 = (struct $B80B7D01E79FADDB4AAC58DE22BC823F *)AllocH(v18);
    v8 = v19;
    v41 = v19;
    if ( !v19 )
    {
      v7 = -2146435066;
      goto LABEL_68;
    }
    memset_0(v19, 0, v18);
    *(_QWORD *)pcchReaders = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = *(char **)mszReaders;
    while ( 1 )
    {
      v24 = (const WCHAR *)&v23[2 * v22];
      if ( !*v24 )
        break;
      v25 = (unsigned __int64)v20 << 6;
      *(LPCWSTR *)((char *)&v8->szReader + v25) = v24;
      *(DWORD *)((char *)&v8->dwCurrentState + v25) = 0;
      ++v20;
      v23 = *(char **)mszReaders;
      v26 = -1;
      do
        ++v26;
      while ( *(_WORD *)(*(_QWORD *)mszReaders + 2 * v22 + 2 * v26) );
      v21 += v26 + 1;
      *(_QWORD *)pcchReaders = v21;
      v22 = v21;
    }
    v7 = SCardGetStatusChangeW(phContext, 0, v8, v20);
    v35 = v7;
    if ( !v7 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v9 || !v20 )
            goto LABEL_68;
          pcchReaders[0] = --v20;
          v27 = (unsigned __int64)v20 << 6;
          v28 = (DWORD *)((char *)&v8->cbAtr + v27);
          v44 = v28;
          if ( *v28 )
          {
            lpData = &v8->rgbAtr[v27];
            if ( AtrCompare(a2, lpData, 0, *v28) )
            {
              if ( !(unsigned int)CidUtilGetDeviceIdByReaderName(
                                    *(LPCWSTR *)((char *)&v8->szReader + v27),
                                    (__int64)&v47) )
                break;
            }
          }
          v9 = v34;
        }
        v34 = 0;
        v29 = (char *)Buf2;
        v37 = 0;
        if ( Buf2 )
        {
          v30 = -1;
          do
            ++v30;
          while ( *((_WORD *)Buf2 + v30) );
          if ( v30 > 0xD && !memcmp_0(L"SCFILTER\\CID_", Buf2, 0x1Au) )
          {
            if ( !memcmp_0(L"2777BE07-6993-4513-BD80-C184FCB0AB2D", v29 + 26, 0x4Au) )
              goto LABEL_44;
            if ( !memcmp_0(L"E2F748F9-DB8B-4C08-A258-583D8955D94A", v29 + 26, 0x4Au) )
              goto LABEL_45;
          }
        }
        v31 = (char *)v47;
        if ( !v47 )
          goto LABEL_54;
        v32 = -1;
        do
          ++v32;
        while ( *((_WORD *)v47 + v32) );
        if ( v32 > 0xD && !memcmp_0(L"SCFILTER\\CID_", v47, 0x1Au) )
        {
          if ( !memcmp_0(L"2777BE07-6993-4513-BD80-C184FCB0AB2D", v31 + 26, 0x4Au) )
          {
LABEL_44:
            v37 = 1;
LABEL_45:
            v9 = 1;
            v34 = 1;
            v36 = 1;
            goto LABEL_56;
          }
          v9 = memcmp_0(L"E2F748F9-DB8B-4C08-A258-583D8955D94A", v31 + 26, 0x4Au) == 0;
          v34 = v9;
        }
        else
        {
LABEL_54:
          v9 = 0;
        }
        v36 = v9;
        if ( v9 )
        {
LABEL_56:
          CBuffer::Clear(v5);
          if ( v37 )
          {
            try
            {
              if ( a4 )
                MStrAdd(v5, L"Identity Device (NIST SP 800-73 [PIV])");
              else
                MStrAdd(v5, "Identity Device (NIST SP 800-73 [PIV])");
            }
            catch ( ... )
            {
              CBuffer::Set(a3, (const unsigned __int8 *const)&WideCharStr, 4u);
              v5 = a3;
              v7 = v35;
              v8 = v41;
              v9 = v36;
              v34 = v36;
              v20 = pcchReaders[0];
            }
            v33 = L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\PIV Device ATR Cache";
          }
          else
          {
            try
            {
              if ( a4 )
                MStrAdd(v5, L"Identity Device (Microsoft Generic Profile)");
              else
                MStrAdd(v5, "Identity Device (Microsoft Generic Profile)");
            }
            catch ( ... )
            {
              CBuffer::Set(a3, (const unsigned __int8 *const)&WideCharStr, 4u);
              v5 = a3;
              v7 = v35;
              v8 = v41;
              v9 = v36;
              v34 = v36;
              v20 = pcchReaders[0];
            }
            v33 = L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\IDMP ATR Cache";
          }
          I_StoreClmdOpt(lpData, *v44, v33);
        }
      }
    }
  }
LABEL_68:
  if ( *(_QWORD *)mszReaders )
    SCardFreeMemory(phContext, *(LPCVOID *)mszReaders);
  if ( Buf2 )
    CidUtilFreeMemory();
  if ( v47 )
    CidUtilFreeMemory();
  if ( v8 )
    I_CidUtilFreeH(v8);
  if ( phContext )
  {
    if ( v40 == 1 )
      SCardReleaseContext(phContext);
  }
  if ( v7 )
  {
LABEL_80:
    pExceptionObject = v7;
    throw (ulong *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180002e84  mov     r11, rsp
0x180002e87  mov     [r11+20h], r9d
0x180002e8b  mov     [r11+18h], r8
0x180002e8f  mov     [r11+10h], rdx
0x180002e93  push    rbx
0x180002e94  push    rsi
0x180002e95  push    rdi
0x180002e96  push    r12
0x180002e98  push    r13
0x180002e9a  push    r14
0x180002e9c  push    r15
0x180002e9e  sub     rsp, 0A0h
0x180002ea5  mov     r13d, r9d
0x180002ea8  mov     r15, r8
0x180002eab  mov     rax, rdx
0x180002eae  mov     rsi, rcx
0x180002eb1  xor     ebx, ebx
0x180002eb3  mov     [r11-70h], rbx
0x180002eb7  mov     ecx, 0FFFFFFFFh
0x180002ebc  mov     qword ptr [rsp+0D8h+pcchReaders], rcx
0x180002ec1  mov     edi, ebx
0x180002ec3  mov     r14d, ebx
0x180002ec6  mov     [r11-78h], rbx
0x180002eca  mov     [r11-50h], rbx
0x180002ece  mov     [r11-48h], rbx
0x180002ed2  mov     r12d, ebx
0x180002ed5  mov     [rsp+0D8h+var_A8], ebx
0x180002ed9  mov     [rsp+0D8h+var_98], ebx
0x180002edd  mov     [rsp+0D8h+phContext], rbx
0x180002ee2  mov     [rsp+0D8h+var_80], ebx
0x180002ee6  test    rdx, rdx
0x180002ee9  jnz     short loc_180002EF5
0x180002eeb  mov     edi, 8010001Fh
0x180002ef0  jmp     loc_1800033FE
0x180002ef5  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x180002efc  mov     rcx, rax; unsigned __int8 *
0x180002eff  call    ?I_MatchClmdOpt@@YAKPEBEPEBG@Z; I_MatchClmdOpt(uchar const *,ushort const *)
0x180002f04  test    eax, eax
0x180002f06  jnz     short loc_180002F2F
0x180002f08  mov     rcx, r15; this
0x180002f0b  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180002f10  mov     rcx, r15; struct CBuffer *
0x180002f13  test    r13d, r13d
0x180002f16  jz      short loc_180002F26
0x180002f18  lea     rdx, String2; "Identity Device (NIST SP 800-73 [PIV])"
0x180002f1f  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x180002f24  jmp     short loc_180002F6C
0x180002f26  lea     rdx, aIdentityDevice_0; "Identity Device (NIST SP 800-73 [PIV])"
0x180002f2d  jmp     short loc_180002F67
0x180002f2f  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x180002f36  mov     rcx, [rsp+0D8h+arg_8]; unsigned __int8 *
0x180002f3e  call    ?I_MatchClmdOpt@@YAKPEBEPEBG@Z; I_MatchClmdOpt(uchar const *,ushort const *)
0x180002f43  test    eax, eax
0x180002f45  jnz     short loc_180002F76
0x180002f47  mov     rcx, r15; this
0x180002f4a  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180002f4f  mov     rcx, r15; struct CBuffer *
0x180002f52  test    r13d, r13d
0x180002f55  jz      short loc_180002F60
0x180002f57  lea     rdx, aIdentityDevice; "Identity Device (Microsoft Generic Prof"...
0x180002f5e  jmp     short loc_180002F1F
0x180002f60  lea     rdx, aIdentityDevice_2; "Identity Device (Microsoft Generic Prof"...
0x180002f67  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBD@Z; MStrAdd(CBuffer &,char const *)
0x180002f6c  mov     esi, 1
0x180002f71  jmp     loc_1800033A0
0x180002f76  test    rsi, rsi
0x180002f79  jnz     short loc_180002FAC
0x180002f7b  lea     r9, [rsp+0D8h+phContext]; phContext
0x180002f80  xor     r8d, r8d; pvReserved2
0x180002f83  xor     edx, edx; pvReserved1
0x180002f85  lea     ecx, [rsi+2]; dwScope
0x180002f88  call    SCardEstablishContext
0x180002f8d  mov     edi, eax
0x180002f8f  mov     [rsp+0D8h+var_A4], eax
0x180002f93  test    eax, eax
0x180002f95  jz      short loc_180002FA1
0x180002f97  mov     esi, 1
0x180002f9c  jmp     loc_1800033A0
0x180002fa1  mov     esi, 1
0x180002fa6  mov     [rsp+0D8h+var_80], esi
0x180002faa  jmp     short loc_180002FB6
0x180002fac  mov     [rsp+0D8h+phContext], rsi
0x180002fb1  mov     esi, 1
0x180002fb6  lea     r9, [rsp+0D8h+pcchReaders]; pcchReaders
0x180002fbb  lea     r8, [rsp+0D8h+mszReaders]; mszReaders
0x180002fc0  xor     edx, edx; mszGroups
0x180002fc2  mov     rcx, [rsp+0D8h+phContext]; hContext
0x180002fc7  call    SCardListReadersW
0x180002fcc  mov     edi, eax
0x180002fce  mov     [rsp+0D8h+var_A4], eax
0x180002fd2  test    eax, eax
0x180002fd4  jz      short loc_180002FDB
0x180002fd6  jmp     loc_1800033A0
0x180002fdb  mov     qword ptr [rsp+0D8h+pcchReaders], rbx
0x180002fe0  mov     eax, ebx
0x180002fe2  mov     [rsp+0D8h+var_94], ebx
0x180002fe6  mov     rdx, rbx
0x180002fe9  mov     rcx, rbx
0x180002fec  mov     r9, qword ptr [rsp+0D8h+mszReaders]
0x180002ff1  lea     r8, [r9+rcx*2]
0x180002ff5  cmp     bx, [r8]
0x180002ff9  jz      short loc_18000301F
0x180002ffb  add     eax, esi
0x180002ffd  mov     [rsp+0D8h+var_94], eax
0x180003001  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003005  inc     rcx
0x180003008  cmp     [r8+rcx*2], bx
0x18000300d  jnz     short loc_180003005
0x18000300f  inc     rcx
0x180003012  add     rdx, rcx
0x180003015  mov     qword ptr [rsp+0D8h+pcchReaders], rdx
0x18000301a  mov     rcx, rdx
0x18000301d  jmp     short loc_180002FF1
0x18000301f  test    eax, eax
0x180003021  jnz     short loc_180003031
0x180003023  mov     edi, 8010002Eh
0x180003028  mov     [rsp+0D8h+var_A4], edi
0x18000302c  jmp     loc_1800033A0
0x180003031  mov     edi, eax
0x180003033  shl     rdi, 6
0x180003037  mov     rcx, rdi; unsigned __int64
0x18000303a  call    ?AllocH@@YAPEAX_K@Z; AllocH(unsigned __int64)
0x18000303f  mov     r14, rax
0x180003042  mov     [rsp+0D8h+var_78], rax
0x180003047  test    rax, rax
0x18000304a  jnz     short loc_18000305A
0x18000304c  mov     edi, 80100006h
0x180003051  mov     [rsp+0D8h+var_A4], edi
0x180003055  jmp     loc_1800033A0
0x18000305a  mov     r8, rdi; Size
0x18000305d  xor     edx, edx; Val
0x18000305f  mov     rcx, r14; void *
0x180003062  call    memset_0
0x180003067  mov     qword ptr [rsp+0D8h+pcchReaders], rbx
0x18000306c  mov     r13d, ebx
0x18000306f  mov     [rsp+0D8h+var_94], ebx
0x180003073  mov     rcx, rbx
0x180003076  mov     rdx, rbx
0x180003079  mov     r8, qword ptr [rsp+0D8h+mszReaders]
0x18000307e  lea     r9, [r8+rdx*2]
0x180003082  cmp     bx, [r9]
0x180003086  jz      short loc_1800030C7
0x180003088  mov     eax, r13d
0x18000308b  shl     rax, 6
0x18000308f  mov     [rax+r14], r9
0x180003093  mov     [rax+r14+10h], ebx
0x180003098  add     r13d, esi
0x18000309b  mov     [rsp+0D8h+var_94], r13d
0x1800030a0  mov     r8, qword ptr [rsp+0D8h+mszReaders]
0x1800030a5  lea     r9, [r8+rdx*2]
0x1800030a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800030ad  inc     rax
0x1800030b0  cmp     [r9+rax*2], bx
0x1800030b5  jnz     short loc_1800030AD
0x1800030b7  inc     rcx
0x1800030ba  add     rcx, rax
0x1800030bd  mov     qword ptr [rsp+0D8h+pcchReaders], rcx
0x1800030c2  mov     rdx, rcx
0x1800030c5  jmp     short loc_18000307E
0x1800030c7  mov     r9d, r13d; cReaders
0x1800030ca  mov     r8, r14; rgReaderStates
0x1800030cd  xor     edx, edx; dwTimeout
0x1800030cf  mov     rcx, [rsp+0D8h+phContext]; hContext
0x1800030d4  call    SCardGetStatusChangeW
0x1800030d9  mov     edi, eax
0x1800030db  mov     [rsp+0D8h+var_A4], eax
0x1800030df  test    eax, eax
0x1800030e1  jz      short loc_1800030E8
0x1800030e3  jmp     loc_1800033A0
0x1800030e8  test    r12d, r12d
0x1800030eb  jnz     loc_180002F71
0x1800030f1  test    r13d, r13d
0x1800030f4  jz      loc_180002F71
0x1800030fa  dec     r13d
0x1800030fd  mov     [rsp+0D8h+pcchReaders], r13d
0x180003102  mov     r12d, r13d
0x180003105  shl     r12, 6
0x180003109  lea     rax, [r12+18h]
0x18000310e  add     rax, r14
0x180003111  mov     [rsp+0D8h+var_60], rax
0x180003116  cmp     [rax], ebx
0x180003118  jz      loc_180003381
0x18000311e  lea     rcx, [r14+1Ch]
0x180003122  add     rcx, r12
0x180003125  mov     [rsp+0D8h+lpData], rcx
0x18000312d  mov     r9d, [rax]; unsigned int
0x180003130  xor     r8d, r8d; unsigned __int8 *
0x180003133  mov     rdx, rcx; unsigned __int8 *
0x180003136  mov     rcx, [rsp+0D8h+arg_8]; unsigned __int8 *
0x18000313e  call    ?AtrCompare@@YAHPEBE00K@Z; AtrCompare(uchar const *,uchar const *,uchar const *,ulong)
0x180003143  test    eax, eax
0x180003145  jz      loc_180003381
0x18000314b  lea     rax, [rsp+0D8h+var_48]
0x180003153  mov     [rsp+0D8h+var_B8], rax; __int64
0x180003158  lea     r9, [rsp+0D8h+Buf2]
0x180003160  mov     r8, [rsp+0D8h+var_60]
0x180003165  mov     r8d, [r8]
0x180003168  mov     rdx, [rsp+0D8h+lpData]
0x180003170  mov     rcx, [r12+r14]; szReader
0x180003174  call    CidUtilGetDeviceIdByReaderName
0x180003179  test    eax, eax
0x18000317b  jnz     loc_180003381
0x180003181  mov     [rsp+0D8h+var_A8], ebx
0x180003185  mov     [rsp+0D8h+var_9C], ebx
0x180003189  mov     r12, [rsp+0D8h+Buf2]
0x180003191  mov     [rsp+0D8h+var_98], ebx
0x180003195  test    r12, r12
0x180003198  jz      short loc_180003219
0x18000319a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000319e  inc     rax
0x1800031a1  cmp     [r12+rax*2], bx
0x1800031a6  jnz     short loc_18000319E
0x1800031a8  cmp     rax, 0Dh
0x1800031ac  jbe     short loc_180003219
0x1800031ae  mov     r8d, 1Ah; Size
0x1800031b4  mov     rdx, r12; Buf2
0x1800031b7  lea     rcx, aScfilterCid; "SCFILTER\\CID_"
0x1800031be  call    memcmp_0
0x1800031c3  test    eax, eax
0x1800031c5  jnz     short loc_180003219
0x1800031c7  lea     r8d, [rax+4Ah]; Size
0x1800031cb  lea     rdx, [r12+1Ah]; Buf2
0x1800031d0  lea     rcx, a2777be07699345; "2777BE07-6993-4513-BD80-C184FCB0AB2D"
0x1800031d7  call    memcmp_0
0x1800031dc  test    eax, eax
0x1800031de  jnz     short loc_1800031F8
0x1800031e0  mov     [rsp+0D8h+var_9C], esi
0x1800031e4  mov     [rsp+0D8h+var_98], esi
0x1800031e8  mov     r12d, esi
0x1800031eb  mov     [rsp+0D8h+var_A8], esi
0x1800031ef  mov     [rsp+0D8h+var_A0], esi
0x1800031f3  jmp     loc_1800032B1
0x1800031f8  mov     r8d, 4Ah ; 'J'; Size
0x1800031fe  lea     rdx, [r12+1Ah]; Buf2
0x180003203  lea     rcx, aE2f748f9Db8b4c; "E2F748F9-DB8B-4C08-A258-583D8955D94A"
0x18000320a  call    memcmp_0
0x18000320f  test    eax, eax
0x180003211  jnz     short loc_180003219
0x180003213  mov     [rsp+0D8h+var_9C], esi
0x180003217  jmp     short loc_1800031E8
0x180003219  mov     r12, [rsp+0D8h+var_48]
0x180003221  test    r12, r12
0x180003224  jz      short loc_18000329E
0x180003226  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000322a  inc     rax
0x18000322d  cmp     [r12+rax*2], bx
0x180003232  jnz     short loc_18000322A
0x180003234  cmp     rax, 0Dh
0x180003238  jbe     short loc_18000329E
0x18000323a  mov     r8d, 1Ah; Size
0x180003240  mov     rdx, r12; Buf2
0x180003243  lea     rcx, aScfilterCid; "SCFILTER\\CID_"
0x18000324a  call    memcmp_0
0x18000324f  test    eax, eax
0x180003251  jnz     short loc_18000329E
0x180003253  lea     r8d, [rax+4Ah]; Size
0x180003257  lea     rdx, [r12+1Ah]; Buf2
0x18000325c  lea     rcx, a2777be07699345; "2777BE07-6993-4513-BD80-C184FCB0AB2D"
0x180003263  call    memcmp_0
0x180003268  test    eax, eax
0x18000326a  jz      loc_1800031E0
0x180003270  mov     r8d, 4Ah ; 'J'; Size
0x180003276  lea     rdx, [r12+1Ah]; Buf2
0x18000327b  lea     rcx, aE2f748f9Db8b4c; "E2F748F9-DB8B-4C08-A258-583D8955D94A"
0x180003282  call    memcmp_0
0x180003287  mov     r12d, [rsp+0D8h+var_A8]
0x18000328c  test    eax, eax
0x18000328e  cmovz   r12d, esi
0x180003292  mov     [rsp+0D8h+var_A8], r12d
0x180003297  mov     [rsp+0D8h+var_9C], r12d
0x18000329c  jmp     short loc_1800032A3
0x18000329e  mov     r12d, [rsp+0D8h+var_A8]
0x1800032a3  mov     [rsp+0D8h+var_A0], r12d
0x1800032a8  test    r12d, r12d
0x1800032ab  jz      loc_180003386
0x1800032b1  mov     rcx, r15; this
0x1800032b4  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x1800032b9  cmp     [rsp+0D8h+var_98], ebx
0x1800032bd  jz      short loc_18000332A
0x1800032bf  mov     rcx, r15; struct CBuffer *
0x1800032c2  cmp     [rsp+0D8h+arg_18], ebx
0x1800032c9  jz      short loc_1800032D9
0x1800032cb  lea     rdx, String2; "Identity Device (NIST SP 800-73 [PIV])"
0x1800032d2  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x1800032d7  jmp     short loc_1800032E6
0x1800032d9  lea     rdx, aIdentityDevice_0; "Identity Device (NIST SP 800-73 [PIV])"
0x1800032e0  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBD@Z; MStrAdd(CBuffer &,char const *)
0x1800032e5  nop
0x1800032e6  jmp     short loc_18000330D
0x1800032e8  xor     ebx, ebx
0x1800032ea  lea     esi, [rbx+1]
0x1800032ed  mov     r15, [rsp+0D8h+arg_10]
0x1800032f5  mov     edi, [rsp+0D8h+var_A4]
0x1800032f9  mov     r14, [rsp+0D8h+var_78]
0x1800032fe  mov     r12d, [rsp+0D8h+var_A0]
0x180003303  mov     [rsp+0D8h+var_A8], r12d
0x180003308  mov     r13d, [rsp+0D8h+pcchReaders]
0x18000330d  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x180003314  mov     rax, [rsp+0D8h+var_60]
0x180003319  mov     edx, [rax]; cbData
  ... truncated ...
```
