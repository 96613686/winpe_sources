# CSSCompiler::CompileNGramRules(CWriteStream *,ENGINEDATABLOCKHEADER *,ulong)

- ea: `0x18005478c`
- end: `0x1800549d7`
- name: `?CompileNGramRules@CSSCompiler@@AEAAJPEAVCWriteStream@@PEAUENGINEDATABLOCKHEADER@@K@Z`
- size: `587`
- prototype: `__int64 __fastcall(CSpCfgInst **this, struct CWriteStream *, struct ENGINEDATABLOCKHEADER *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054388`

## callees

- `0x1800034b0`
- `0x18005478c`
- `0x1800549e0`
- `0x18005de20`
- `0x1800d4920`
- `0x1800d4a2c`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800549ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800549ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSSCompiler::CompileNGramRules(
        CSpCfgInst **this,
        struct CWriteStream *a2,
        struct ENGINEDATABLOCKHEADER *a3,
        unsigned int a4)
{
  int NGramRuleByIndex; // ebx
  CSpCfgInst *v9; // rcx
  CSpCfgData *v10; // r14
  int v11; // r13d
  unsigned int i; // r12d
  unsigned int v13; // r9d
  unsigned int v14; // ecx
  signed int v15; // edx
  unsigned int NGramRuleCount; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v18; // [rsp+24h] [rbp-DCh] BYREF
  CSSCompiler *v19; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v20; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+40h] [rbp-C0h]
  __int128 v22; // [rsp+90h] [rbp-70h]
  _BYTE v23[112]; // [rsp+130h] [rbp+30h] BYREF
  LPVOID pv[2]; // [rsp+1A0h] [rbp+A0h]

  v19 = (CSSCompiler *)this;
  *(_OWORD *)pv = 0;
  v18 = 0;
  NGramRuleByIndex = (*(__int64 (__fastcall **)(struct CWriteStream *, unsigned int *))(*(_QWORD *)a2 + 32LL))(a2, &v18);
  if ( NGramRuleByIndex >= 0 )
  {
    v9 = this[6];
    v10 = (CSpCfgData *)*((_QWORD *)v9 + 32);
    if ( v10 )
    {
      v22 = *((_OWORD *)v10 + 4);
      v11 = 0;
      NGramRuleCount = CSpCfgInst::GetNGramRuleCount(v9);
      for ( i = 0; i < DWORD2(v22); ++i )
      {
        v20 = 0;
        v21 = 0;
        CSpCfgData::GetRuleDataByIndex(v10, i, (struct SPRULEDATA *)&v20);
        if ( !BYTE3(v20) )
        {
          if ( BYTE8(v21) )
          {
            NGramRuleByIndex = CSpCfgData::GetNGramRuleByIndex(v10, i, (struct CSpNGramRule *)v23, v13);
            if ( NGramRuleByIndex < 0 )
              goto LABEL_23;
            NGramRuleByIndex = CSSCompiler::CompileOneNGramRule(
                                 v19,
                                 a2,
                                 (struct CSpNGramRule *)v23,
                                 NGramRuleCount == ++v11);
            if ( NGramRuleByIndex < 0 )
              goto LABEL_23;
          }
        }
      }
      if ( NGramRuleCount )
      {
        NGramRuleCount = 0;
        NGramRuleByIndex = (*(__int64 (__fastcall **)(struct CWriteStream *, unsigned int *))(*(_QWORD *)a2 + 32LL))(
                             a2,
                             &NGramRuleCount);
        if ( NGramRuleByIndex >= 0 )
        {
          v14 = NGramRuleCount;
          LODWORD(v19) = NGramRuleCount;
          v15 = v18;
          if ( v18 <= a4
            || (*((_DWORD *)a3 + 14) = v18 - a4, (int)v14 <= v15)
            || (*((_DWORD *)a3 + 15) = v14 - v15, v14 <= a4) )
          {
            NGramRuleByIndex = -2147467259;
          }
          else
          {
            *(_DWORD *)a3 = v14 - a4;
            NGramRuleByIndex = (*(__int64 (__fastcall **)(struct CWriteStream *, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
                                 a2,
                                 a4,
                                 0);
            if ( NGramRuleByIndex >= 0 )
            {
              NGramRuleByIndex = (*(__int64 (__fastcall **)(struct CWriteStream *, struct ENGINEDATABLOCKHEADER *, __int64))(*(_QWORD *)a2 + 16LL))(
                                   a2,
                                   a3,
                                   64);
              if ( NGramRuleByIndex >= 0 )
              {
                NGramRuleByIndex = (*(__int64 (__fastcall **)(struct CWriteStream *, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
                                     a2,
                                     0,
                                     0);
                if ( NGramRuleByIndex >= 0 )
                {
                  NGramRuleByIndex = (*(__int64 (__fastcall **)(struct CWriteStream *, CSSCompiler **, __int64))(*(_QWORD *)a2 + 16LL))(
                                       a2,
                                       &v19,
                                       4);
                  if ( NGramRuleByIndex >= 0 )
                    NGramRuleByIndex = (*(__int64 (__fastcall **)(struct CWriteStream *, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
                                         a2,
                                         (unsigned int)v19,
                                         0);
                }
              }
            }
          }
        }
      }
      else
      {
        *((_QWORD *)a3 + 7) = 0;
      }
    }
    else
    {
      NGramRuleByIndex = -2147024809;
    }
  }
LABEL_23:
  CoTaskMemFree(pv[1]);
  return (unsigned int)NGramRuleByIndex;
}

```

## disassembly

```asm
0x18005478c  push    rbp
0x18005478e  push    rbx
0x18005478f  push    rsi
0x180054790  push    rdi
0x180054791  push    r12
0x180054793  push    r13
0x180054795  push    r14
0x180054797  push    r15
0x180054799  lea     rbp, [rsp-348h]
0x1800547a1  sub     rsp, 448h
0x1800547a8  mov     rax, cs:__security_cookie
0x1800547af  xor     rax, rsp
0x1800547b2  mov     [rbp+380h+var_50], rax
0x1800547b9  mov     r15d, r9d
0x1800547bc  mov     rsi, r8
0x1800547bf  mov     rdi, rdx
0x1800547c2  mov     r14, rcx
0x1800547c5  mov     [rsp+480h+var_458], rcx
0x1800547ca  xorps   xmm0, xmm0
0x1800547cd  movdqa  xmmword ptr [rbp+380h+pv], xmm0
0x1800547d5  mov     [rsp+480h+var_45C], 0
0x1800547dd  mov     rax, [rdx]
0x1800547e0  lea     rdx, [rsp+480h+var_45C]
0x1800547e5  mov     rcx, rdi
0x1800547e8  mov     rax, [rax+20h]
0x1800547ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800547f1  mov     ebx, eax
0x1800547f3  test    eax, eax
0x1800547f5  js      loc_1800549A5
0x1800547fb  mov     rcx, [r14+30h]; this
0x1800547ff  mov     r14, [rcx+100h]
0x180054806  test    r14, r14
0x180054809  jnz     short loc_180054815
0x18005480b  mov     ebx, 80070057h
0x180054810  jmp     loc_1800549A5
0x180054815  movups  xmm0, xmmword ptr [r14+40h]
0x18005481a  movups  [rbp+380h+var_3F0], xmm0
0x18005481e  xor     r13d, r13d
0x180054821  call    ?GetNGramRuleCount@CSpCfgInst@@QEAAKXZ; CSpCfgInst::GetNGramRuleCount(void)
0x180054826  mov     [rsp+480h+var_460], eax
0x18005482a  xor     r12d, r12d
0x18005482d  cmp     r12d, dword ptr [rbp+380h+var_3F0+8]
0x180054831  jnb     short loc_1800548A6
0x180054833  xorps   xmm0, xmm0
0x180054836  movups  [rsp+480h+var_450], xmm0
0x18005483b  movups  [rsp+480h+var_440], xmm0
0x180054840  lea     r8, [rsp+480h+var_450]; struct SPRULEDATA *
0x180054845  mov     edx, r12d; unsigned int
0x180054848  mov     rcx, r14; this
0x18005484b  call    ?GetRuleDataByIndex@CSpCfgData@@QEAAXKPEAUSPRULEDATA@@@Z; CSpCfgData::GetRuleDataByIndex(ulong,SPRULEDATA *)
0x180054850  cmp     byte ptr [rsp+480h+var_450+3], 0
0x180054855  jnz     short loc_1800548A1
0x180054857  cmp     byte ptr [rsp+480h+var_440+8], 0
0x18005485c  jz      short loc_1800548A1
0x18005485e  lea     r8, [rbp+380h+var_350]; struct CSpNGramRule *
0x180054862  mov     edx, r12d; unsigned int
0x180054865  mov     rcx, r14; this
0x180054868  call    ?GetNGramRuleByIndex@CSpCfgData@@QEAAJKPEAVCSpNGramRule@@K@Z; CSpCfgData::GetNGramRuleByIndex(ulong,CSpNGramRule *,ulong)
0x18005486d  mov     ebx, eax
0x18005486f  test    eax, eax
0x180054871  js      loc_1800549A5
0x180054877  inc     r13d
0x18005487a  xor     r9d, r9d
0x18005487d  cmp     [rsp+480h+var_460], r13d
0x180054882  setz    r9b; int
0x180054886  lea     r8, [rbp+380h+var_350]; struct CSpNGramRule *
0x18005488a  mov     rdx, rdi; struct CWriteStream *
0x18005488d  mov     rcx, [rsp+480h+var_458]; this
0x180054892  call    ?CompileOneNGramRule@CSSCompiler@@AEAAJPEAVCWriteStream@@PEAVCSpNGramRule@@H@Z; CSSCompiler::CompileOneNGramRule(CWriteStream *,CSpNGramRule *,int)
0x180054897  mov     ebx, eax
0x180054899  test    eax, eax
0x18005489b  js      loc_1800549A5
0x1800548a1  inc     r12d
0x1800548a4  jmp     short loc_18005482D
0x1800548a6  xor     r14d, r14d
0x1800548a9  cmp     [rsp+480h+var_460], r14d
0x1800548ae  jbe     loc_1800549A1
0x1800548b4  mov     [rsp+480h+var_460], r14d
0x1800548b9  mov     rax, [rdi]
0x1800548bc  lea     rdx, [rsp+480h+var_460]
0x1800548c1  mov     rcx, rdi
0x1800548c4  mov     rax, [rax+20h]
0x1800548c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548cd  mov     ebx, eax
0x1800548cf  test    eax, eax
0x1800548d1  js      loc_1800549A5
0x1800548d7  mov     ecx, [rsp+480h+var_460]
0x1800548db  mov     dword ptr [rsp+480h+var_458], ecx
0x1800548df  mov     edx, [rsp+480h+var_45C]
0x1800548e3  cmp     edx, r15d
0x1800548e6  jbe     loc_18005499A
0x1800548ec  mov     eax, edx
0x1800548ee  sub     eax, r15d
0x1800548f1  mov     [rsi+38h], eax
0x1800548f4  cmp     ecx, edx
0x1800548f6  jle     loc_18005499A
0x1800548fc  mov     eax, ecx
0x1800548fe  sub     eax, edx
0x180054900  mov     [rsi+3Ch], eax
0x180054903  cmp     ecx, r15d
0x180054906  jbe     loc_18005499A
0x18005490c  sub     ecx, r15d
0x18005490f  mov     [rsi], ecx
0x180054911  mov     rax, [rdi]
0x180054914  xor     r8d, r8d
0x180054917  mov     edx, r15d
0x18005491a  mov     rcx, rdi
0x18005491d  mov     rax, [rax+18h]
0x180054921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054926  mov     ebx, eax
0x180054928  test    eax, eax
0x18005492a  js      short loc_1800549A5
0x18005492c  mov     rax, [rdi]
0x18005492f  lea     r8d, [r14+40h]
0x180054933  mov     rdx, rsi
0x180054936  mov     rcx, rdi
0x180054939  mov     rax, [rax+10h]
0x18005493d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054942  mov     ebx, eax
0x180054944  test    eax, eax
0x180054946  js      short loc_1800549A5
0x180054948  mov     rax, [rdi]
0x18005494b  xor     r8d, r8d
0x18005494e  xor     edx, edx
0x180054950  mov     rcx, rdi
0x180054953  mov     rax, [rax+18h]
0x180054957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005495c  mov     ebx, eax
0x18005495e  test    eax, eax
0x180054960  js      short loc_1800549A5
0x180054962  mov     rax, [rdi]
0x180054965  lea     r8d, [r14+4]
0x180054969  lea     rdx, [rsp+480h+var_458]
0x18005496e  mov     rcx, rdi
0x180054971  mov     rax, [rax+10h]
0x180054975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005497a  mov     ebx, eax
0x18005497c  test    eax, eax
0x18005497e  js      short loc_1800549A5
0x180054980  mov     rax, [rdi]
0x180054983  xor     r8d, r8d
0x180054986  mov     edx, dword ptr [rsp+480h+var_458]
0x18005498a  mov     rcx, rdi
0x18005498d  mov     rax, [rax+18h]
0x180054991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054996  mov     ebx, eax
0x180054998  jmp     short loc_1800549A5
0x18005499a  mov     ebx, 80004005h
0x18005499f  jmp     short loc_1800549A5
0x1800549a1  mov     [rsi+38h], r14
0x1800549a5  mov     rcx, [rbp+380h+pv+8]; pv
0x1800549ac  call    cs:__imp_CoTaskMemFree
0x1800549b2  mov     eax, ebx
0x1800549b4  mov     rcx, [rbp+380h+var_50]
0x1800549bb  xor     rcx, rsp; StackCookie
0x1800549be  call    __security_check_cookie
0x1800549c3  add     rsp, 448h
0x1800549ca  pop     r15
0x1800549cc  pop     r14
0x1800549ce  pop     r13
0x1800549d0  pop     r12
0x1800549d2  pop     rdi
0x1800549d3  pop     rsi
0x1800549d4  pop     rbx
0x1800549d5  pop     rbp
0x1800549d6  retn
```
