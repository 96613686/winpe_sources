# CWamAdmin::EnumerateApplicationsInPool(ushort const *,ushort * *)

- ea: `0x1800030b0`
- end: `0x18000336e`
- name: `?EnumerateApplicationsInPool@CWamAdmin@@UEAAJPEBGPEAPEAG@Z`
- size: `702`
- prototype: `__int64 __fastcall(CWamAdmin *this, wchar_t *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x180001084`
- `0x180002f9c`
- `0x1800030b0`
- `0x18000368c`
- `0x1800058a0`
- `0x180005a50`
- `0x180005cfc`
- `0x180006850`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800032fa`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800032fa`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800030e2`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800030e2`
- `iisutil!?CopyToBuffer@MULTISZ@@QEBAHPEAGPEAK@Z` at `0x180003316`
- `iisutil!?CopyToBuffer@MULTISZ@@QEBAHPEAGPEAK@Z` at `0x180003316`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000333f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000333f`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18000314a`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800031ef`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800032cd`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18000314a`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800031ef`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800032cd`

## pseudocode

```c
__int64 __fastcall CWamAdmin::EnumerateApplicationsInPool(CWamAdmin *this, wchar_t *a2, unsigned __int16 **a3)
{
  WamRegMetabaseConfig *v5; // rcx
  void *v6; // rsi
  int v7; // ebx
  const unsigned __int16 *v8; // rbx
  __int64 v9; // rax
  WamRegMetabaseConfig *v10; // rcx
  WamRegMetabaseConfig *v11; // rcx
  wchar_t *v12; // rbx
  __int64 v13; // rax
  unsigned __int16 *v14; // rdi
  int v15; // r14d
  WamRegMetabaseConfig *v16; // rcx
  unsigned int v17; // r8d
  int v18; // eax
  __int64 v19; // rax
  UINT v20; // ebx
  unsigned __int16 *v21; // rax
  unsigned int v23; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-4Ch] BYREF
  void *Block; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v26[48]; // [rsp+40h] [rbp-40h] BYREF
  UINT ui; // [rsp+70h] [rbp-10h]

  MULTISZ::MULTISZ((MULTISZ *)v26);
  Block = 0;
  v6 = 0;
  v24 = 0;
  if ( a2 && a3 )
  {
    *a3 = 0;
    v7 = WamRegMetabaseConfig::MDGetAllSiteRoots(v5, (unsigned __int16 **)&Block);
    if ( v7 < 0 )
      goto LABEL_41;
    v6 = Block;
    v8 = (const unsigned __int16 *)Block;
    if ( Block )
    {
      while ( *v8 )
      {
        if ( (unsigned int)IsAppInAppPool(v8, a2) && !MULTISZ::Append((MULTISZ *)v26, v8) )
          goto LABEL_40;
        v9 = -1;
        do
          ++v9;
        while ( v8[v9] );
        v8 += v9 + 1;
        if ( !v8 )
          break;
      }
    }
    operator delete(v6);
    Block = 0;
    v7 = WamRegMetabaseConfig::MDGetPropPaths(v10, 0, 0x838u, (unsigned __int16 **)&Block, &v24);
    if ( v7 < 0 )
      goto LABEL_41;
    v6 = Block;
    v12 = (wchar_t *)Block;
    if ( Block )
    {
      while ( *v12 )
      {
        v23 = 0;
        if ( (!(unsigned int)DoesBeginWithLMW3SVCNRoot(v12, &v23) || v23 > 1)
          && (unsigned int)DoesBeginWithLMW3SVCNRoot(v12, 0)
          && (unsigned int)IsAppInAppPool(v12, a2)
          && !MULTISZ::Append((MULTISZ *)v26, v12) )
        {
          goto LABEL_40;
        }
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
        v12 += v13 + 1;
        if ( !v12 )
          break;
      }
    }
    v7 = WamRegMetabaseConfig::MDGetPropPaths(v11, 0, 0x238Du, (unsigned __int16 **)&Block, &v24);
    if ( v7 < 0 )
    {
LABEL_41:
      v6 = Block;
    }
    else
    {
      v6 = Block;
      v14 = (unsigned __int16 *)Block;
      if ( Block )
      {
        while ( *v14 )
        {
          v23 = 0;
          v15 = 0;
          if ( (unsigned int)DoesBeginWithLMW3SVCNRoot(v14, 0) )
          {
            v18 = WamRegMetabaseConfig::MDGetDWORD(v16, v14, v17, &v23);
            v7 = v18;
            if ( v18 != -2146646015 )
            {
              if ( v18 < 0 )
                goto LABEL_43;
              v15 = 1;
            }
          }
          v23 = 0;
          if ( (!(unsigned int)DoesBeginWithLMW3SVCNRoot(v14, &v23) || v23 > 1)
            && (unsigned int)DoesBeginWithLMW3SVCNRoot(v14, 0)
            && !v15
            && (unsigned int)IsAppInAppPool(v14, a2)
            && !MULTISZ::Append((MULTISZ *)v26, v14) )
          {
            goto LABEL_40;
          }
          v19 = -1;
          do
            ++v19;
          while ( v14[v19] );
          v14 += v19 + 1;
          if ( !v14 )
            break;
        }
      }
      v20 = ui;
      v21 = SysAllocStringLen(0, ui);
      *a3 = v21;
      if ( v21 )
      {
        v24 = v20;
        MULTISZ::CopyToBuffer((MULTISZ *)v26, v21, &v24);
        v7 = 0;
      }
      else
      {
LABEL_40:
        v7 = -2147024882;
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
LABEL_43:
  operator delete(v6);
  MULTISZ::~MULTISZ((MULTISZ *)v26);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800030b0  mov     [rsp-38h+arg_0], rbx
0x1800030b5  push    rbp
0x1800030b6  push    rsi
0x1800030b7  push    rdi
0x1800030b8  push    r12
0x1800030ba  push    r13
0x1800030bc  push    r14
0x1800030be  push    r15
0x1800030c0  mov     rbp, rsp
0x1800030c3  sub     rsp, 80h
0x1800030ca  mov     rax, cs:__security_cookie
0x1800030d1  xor     rax, rsp
0x1800030d4  mov     [rbp+var_8], rax
0x1800030d8  lea     rcx, [rbp+var_40]
0x1800030dc  mov     r15, r8
0x1800030df  mov     r12, rdx
0x1800030e2  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800030e8  xor     r13d, r13d
0x1800030eb  mov     [rbp+Block], r13
0x1800030ef  mov     esi, r13d
0x1800030f2  mov     [rbp+var_4C], r13d
0x1800030f6  test    r12, r12
0x1800030f9  jz      loc_18000332E
0x1800030ff  test    r15, r15
0x180003102  jz      loc_18000332E
0x180003108  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18000310c  mov     [r15], r13
0x18000310f  call    ?MDGetAllSiteRoots@WamRegMetabaseConfig@@QEAAJPEAPEAG@Z; WamRegMetabaseConfig::MDGetAllSiteRoots(ushort * *)
0x180003114  mov     ebx, eax
0x180003116  test    eax, eax
0x180003118  js      loc_180003328
0x18000311e  mov     rsi, [rbp+Block]
0x180003122  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003126  mov     rbx, rsi
0x180003129  test    rsi, rsi
0x18000312c  jz      short loc_18000316F
0x18000312e  cmp     [rbx], r13w
0x180003132  jz      short loc_18000316F
0x180003134  mov     rdx, r12; String2
0x180003137  mov     rcx, rbx; unsigned __int16 *
0x18000313a  call    ?IsAppInAppPool@@YAHPEBG0@Z; IsAppInAppPool(ushort const *,ushort const *)
0x18000313f  test    eax, eax
0x180003141  jz      short loc_180003158
0x180003143  mov     rdx, rbx
0x180003146  lea     rcx, [rbp+var_40]
0x18000314a  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180003150  test    eax, eax
0x180003152  jz      loc_180003321
0x180003158  mov     rax, rdi
0x18000315b  inc     rax
0x18000315e  cmp     [rbx+rax*2], r13w
0x180003163  jnz     short loc_18000315B
0x180003165  lea     rbx, [rbx+rax*2]
0x180003169  add     rbx, 2
0x18000316d  jnz     short loc_18000312E
0x18000316f  mov     rcx, rsi; Block
0x180003172  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003177  lea     rax, [rbp+var_4C]
0x18000317b  mov     [rbp+Block], r13
0x18000317f  lea     r9, [rbp+Block]; unsigned __int16 **
0x180003183  mov     [rsp+80h+var_60], rax; unsigned int *
0x180003188  xor     edx, edx; unsigned __int16 *
0x18000318a  mov     r8d, 838h; unsigned int
0x180003190  call    ?MDGetPropPaths@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAGPEAK@Z; WamRegMetabaseConfig::MDGetPropPaths(ushort const *,ulong,ushort * *,ulong *)
0x180003195  mov     ebx, eax
0x180003197  test    eax, eax
0x180003199  js      loc_180003328
0x18000319f  mov     rsi, [rbp+Block]
0x1800031a3  mov     rbx, rsi
0x1800031a6  test    rsi, rsi
0x1800031a9  jz      short loc_180003214
0x1800031ab  cmp     [rbx], r13w
0x1800031af  jz      short loc_180003214
0x1800031b1  lea     rdx, [rbp+var_50]; unsigned int *
0x1800031b5  mov     [rbp+var_50], r13d
0x1800031b9  mov     rcx, rbx; String2
0x1800031bc  call    ?DoesBeginWithLMW3SVCNRoot@@YAHPEBGPEAK@Z; DoesBeginWithLMW3SVCNRoot(ushort const *,ulong *)
0x1800031c1  test    eax, eax
0x1800031c3  jz      short loc_1800031CB
0x1800031c5  cmp     [rbp+var_50], 1
0x1800031c9  jbe     short loc_1800031FD
0x1800031cb  xor     edx, edx; unsigned int *
0x1800031cd  mov     rcx, rbx; String2
0x1800031d0  call    ?DoesBeginWithLMW3SVCNRoot@@YAHPEBGPEAK@Z; DoesBeginWithLMW3SVCNRoot(ushort const *,ulong *)
0x1800031d5  test    eax, eax
0x1800031d7  jz      short loc_1800031FD
0x1800031d9  mov     rdx, r12; String2
0x1800031dc  mov     rcx, rbx; unsigned __int16 *
0x1800031df  call    ?IsAppInAppPool@@YAHPEBG0@Z; IsAppInAppPool(ushort const *,ushort const *)
0x1800031e4  test    eax, eax
0x1800031e6  jz      short loc_1800031FD
0x1800031e8  mov     rdx, rbx
0x1800031eb  lea     rcx, [rbp+var_40]
0x1800031ef  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800031f5  test    eax, eax
0x1800031f7  jz      loc_180003321
0x1800031fd  mov     rax, rdi
0x180003200  inc     rax
0x180003203  cmp     [rbx+rax*2], r13w
0x180003208  jnz     short loc_180003200
0x18000320a  lea     rbx, [rbx+rax*2]
0x18000320e  add     rbx, 2
0x180003212  jnz     short loc_1800031AB
0x180003214  lea     rax, [rbp+var_4C]
0x180003218  xor     edx, edx; unsigned __int16 *
0x18000321a  lea     r9, [rbp+Block]; unsigned __int16 **
0x18000321e  mov     [rsp+80h+var_60], rax; unsigned int *
0x180003223  mov     r8d, 238Dh; unsigned int
0x180003229  call    ?MDGetPropPaths@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAGPEAK@Z; WamRegMetabaseConfig::MDGetPropPaths(ushort const *,ulong,ushort * *,ulong *)
0x18000322e  mov     ebx, eax
0x180003230  test    eax, eax
0x180003232  js      loc_180003328
0x180003238  mov     rsi, [rbp+Block]
0x18000323c  mov     rdi, rsi
0x18000323f  test    rsi, rsi
0x180003242  jz      loc_1800032F3
0x180003248  cmp     [rdi], r13w
0x18000324c  jz      loc_1800032F3
0x180003252  xor     edx, edx; unsigned int *
0x180003254  mov     [rbp+var_50], r13d
0x180003258  mov     rcx, rdi; String2
0x18000325b  mov     r14d, r13d
0x18000325e  call    ?DoesBeginWithLMW3SVCNRoot@@YAHPEBGPEAK@Z; DoesBeginWithLMW3SVCNRoot(ushort const *,ulong *)
0x180003263  test    eax, eax
0x180003265  jz      short loc_18000328A
0x180003267  lea     r9, [rbp+var_50]; unsigned int *
0x18000326b  mov     rdx, rdi; unsigned __int16 *
0x18000326e  call    ?MDGetDWORD@WamRegMetabaseConfig@@QEAAJPEBGKPEAK@Z; WamRegMetabaseConfig::MDGetDWORD(ushort const *,ulong,ulong *)
0x180003273  mov     ebx, eax
0x180003275  cmp     eax, 800CC801h
0x18000327a  jz      short loc_18000328A
0x18000327c  test    eax, eax
0x18000327e  js      loc_180003333
0x180003284  mov     r14d, 1
0x18000328a  lea     rdx, [rbp+var_50]; unsigned int *
0x18000328e  mov     [rbp+var_50], r13d
0x180003292  mov     rcx, rdi; String2
0x180003295  call    ?DoesBeginWithLMW3SVCNRoot@@YAHPEBGPEAK@Z; DoesBeginWithLMW3SVCNRoot(ushort const *,ulong *)
0x18000329a  test    eax, eax
0x18000329c  jz      short loc_1800032A4
0x18000329e  cmp     [rbp+var_50], 1
0x1800032a2  jbe     short loc_1800032D7
0x1800032a4  xor     edx, edx; unsigned int *
0x1800032a6  mov     rcx, rdi; String2
0x1800032a9  call    ?DoesBeginWithLMW3SVCNRoot@@YAHPEBGPEAK@Z; DoesBeginWithLMW3SVCNRoot(ushort const *,ulong *)
0x1800032ae  test    eax, eax
0x1800032b0  jz      short loc_1800032D7
0x1800032b2  test    r14d, r14d
0x1800032b5  jnz     short loc_1800032D7
0x1800032b7  mov     rdx, r12; String2
0x1800032ba  mov     rcx, rdi; unsigned __int16 *
0x1800032bd  call    ?IsAppInAppPool@@YAHPEBG0@Z; IsAppInAppPool(ushort const *,ushort const *)
0x1800032c2  test    eax, eax
0x1800032c4  jz      short loc_1800032D7
0x1800032c6  mov     rdx, rdi
0x1800032c9  lea     rcx, [rbp+var_40]
0x1800032cd  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800032d3  test    eax, eax
0x1800032d5  jz      short loc_180003321
0x1800032d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800032db  inc     rax
0x1800032de  cmp     [rdi+rax*2], r13w
0x1800032e3  jnz     short loc_1800032DB
0x1800032e5  lea     rdi, [rdi+rax*2]
0x1800032e9  add     rdi, 2
0x1800032ed  jnz     loc_180003248
0x1800032f3  mov     ebx, [rbp+ui]
0x1800032f6  xor     ecx, ecx; strIn
0x1800032f8  mov     edx, ebx; ui
0x1800032fa  call    cs:__imp_SysAllocStringLen
0x180003300  mov     [r15], rax
0x180003303  test    rax, rax
0x180003306  jz      short loc_180003321
0x180003308  lea     r8, [rbp+var_4C]
0x18000330c  mov     [rbp+var_4C], ebx
0x18000330f  mov     rdx, rax
0x180003312  lea     rcx, [rbp+var_40]
0x180003316  call    cs:__imp_?CopyToBuffer@MULTISZ@@QEBAHPEAGPEAK@Z; MULTISZ::CopyToBuffer(ushort *,ulong *)
0x18000331c  mov     ebx, r13d
0x18000331f  jmp     short loc_180003333
0x180003321  mov     ebx, 8007000Eh
0x180003326  jmp     short loc_180003333
0x180003328  mov     rsi, [rbp+Block]
0x18000332c  jmp     short loc_180003333
0x18000332e  mov     ebx, 80070057h
0x180003333  mov     rcx, rsi; Block
0x180003336  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000333b  lea     rcx, [rbp+var_40]
0x18000333f  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180003345  mov     eax, ebx
0x180003347  mov     rcx, [rbp+var_8]
0x18000334b  xor     rcx, rsp; StackCookie
0x18000334e  call    __security_check_cookie
0x180003353  mov     rbx, [rsp+80h+arg_0]
0x18000335b  add     rsp, 80h
0x180003362  pop     r15
0x180003364  pop     r14
0x180003366  pop     r13
0x180003368  pop     r12
0x18000336a  pop     rdi
0x18000336b  pop     rsi
0x18000336c  pop     rbp
0x18000336d  retn
```
