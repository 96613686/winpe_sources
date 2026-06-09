# CContainerProps::CreateMoreDirectoriesAsCaller(void)

- ea: `0x1800ed5e8`
- end: `0x1800ed96a`
- name: `?CreateMoreDirectoriesAsCaller@CContainerProps@@AEAAJXZ`
- size: `898`
- prototype: `__int64 __fastcall(CContainerProps *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800f125c`

## callees

- `0x180021360`
- `0x18007ec9c`
- `0x180083dc4`
- `0x180086300`
- `0x1800ed5e8`
- `0x1800ee168`
- `0x1800eed94`
- `0x1800eee94`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801aad40`
- `0x1801e1790`
- `0x1801e3c24`

## import_xrefs

- `ESENT!JetCommitTransaction` at `0x1800ed941`
- `ESENT!JetCommitTransaction` at `0x1800ed941`
- `ESENT!JetUpdate` at `0x1800ed920`
- `ESENT!JetUpdate` at `0x1800ed920`
- `ESENT!JetPrepareUpdate` at `0x1800ed820`
- `ESENT!JetPrepareUpdate` at `0x1800ed868`
- `ESENT!JetPrepareUpdate` at `0x1800ed820`
- `ESENT!JetPrepareUpdate` at `0x1800ed868`
- `ESENT!JetRollback` at `0x1800ed874`
- `ESENT!JetRollback` at `0x1800ed874`
- `ESENT!JetBeginTransaction` at `0x1800ed7cb`
- `ESENT!JetBeginTransaction` at `0x1800ed7cb`

## pseudocode

```c
__int64 __fastcall CContainerProps::CreateMoreDirectoriesAsCaller(CContainerProps *this)
{
  unsigned int v2; // edi
  unsigned int v3; // r14d
  signed int SecureSubDirectory; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  unsigned __int16 *v8; // r8
  unsigned __int16 *v9; // rax
  __int64 v10; // rdx
  unsigned __int16 *v11; // rcx
  unsigned int v12; // r9d
  JET_SESID *v13; // rdi
  JET_ERR v14; // eax
  int v15; // eax
  JET_ERR v16; // eax
  JET_ERR v18; // eax
  JET_ERR v19; // eax
  struct CJetContext *v20; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v21[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v22; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v23[264]; // [rsp+60h] [rbp-A0h] BYREF

  v22 = 0;
  *(_OWORD *)v21 = 0;
  memset_0(v23, 0, 0x202u);
  v20 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_q(1036, 20, WPP_b5c7e844a87d3fa49b467b888bebb474_Traceguids, this);
  v2 = **((_DWORD **)this + 20);
  v3 = v2 + 4;
  if ( v2 + 4 > 0x20 )
    v3 = 32;
  while ( v2 < v3 )
  {
    SecureSubDirectory = CreateSecureSubDirectory(*((const unsigned __int16 **)this + 13), v21, (unsigned __int16 *)1);
    if ( SecureSubDirectory < 0 )
      goto LABEL_28;
    v5 = 2LL * v2;
    v6 = v2++;
    *(_OWORD *)(*((_QWORD *)this + 20) + 8 * v5 + 4) = *(_OWORD *)v21;
    *(_DWORD *)(*((_QWORD *)this + 20) + 4 * v6 + 516) = 0;
  }
  v7 = 8 * v3;
  if ( v7 > 0x7FFFFFFE )
  {
    v23[0] = 0;
    SecureSubDirectory = -2147024809;
    goto LABEL_28;
  }
  v8 = v23;
  v9 = (unsigned __int16 *)(*((_QWORD *)this + 20) + 4LL);
  v10 = 257;
  do
  {
    if ( !v7 )
      break;
    if ( !*v9 )
      break;
    *v8++ = *v9++;
    --v7;
    --v10;
  }
  while ( v10 );
  v11 = v8 - 1;
  if ( v10 )
    v11 = v8;
  SecureSubDirectory = v10 == 0 ? 0x8007007A : 0;
  *v11 = 0;
  if ( v10 )
  {
    SecureSubDirectory = CJetContextList::AcquireContext(*(CJetContextList **)(*((_QWORD *)this + 3) + 320LL), &v20, 0);
    if ( SecureSubDirectory >= 0 )
    {
      v13 = (JET_SESID *)v20;
      SecureSubDirectory = CJetContext::SetCurrentIndex(v20, 0, L"ContainerIdIndex", v12);
      if ( SecureSubDirectory >= 0 )
      {
        v14 = JetBeginTransaction(v13[2]);
        SecureSubDirectory = HRESULTFromJET_ERR(v14, 1);
        if ( SecureSubDirectory >= 0 )
        {
          v15 = SeekToContainer((struct CJetContext *)v13, *((_QWORD *)this + 1));
          SecureSubDirectory = v15;
          if ( v15 < 0 )
          {
LABEL_27:
            JetRollback(v13[2], 0);
            goto LABEL_28;
          }
          if ( v15 )
          {
            SecureSubDirectory = -2147418113;
            goto LABEL_27;
          }
          v16 = JetPrepareUpdate(v13[2], v13[4], 2u);
          SecureSubDirectory = HRESULTFromJET_ERR(v16, 1);
          if ( SecureSubDirectory < 0 )
            goto LABEL_27;
          SecureSubDirectory = CJetContext::SetStringColumn((CJetContext *)v13, 8u, v23);
          if ( SecureSubDirectory < 0
            || (SecureSubDirectory = CJetContext::SetBinaryColumn(
                                       (CJetContext *)v13,
                                       9u,
                                       (const unsigned __int8 *)(*((_QWORD *)this + 20) + 516LL),
                                       4 * v3),
                SecureSubDirectory < 0)
            || (v18 = JetUpdate(v13[2], v13[4], 0, 0, 0),
                SecureSubDirectory = HRESULTFromJET_ERR(v18, 1),
                SecureSubDirectory < 0) )
          {
            JetPrepareUpdate(v13[2], v13[4], 3u);
            goto LABEL_27;
          }
          v19 = JetCommitTransaction(v13[2], 1u);
          SecureSubDirectory = HRESULTFromJET_ERR(v19, 1);
          if ( SecureSubDirectory < 0 )
            goto LABEL_27;
          **((_DWORD **)this + 20) = v3;
        }
      }
    }
  }
LABEL_28:
  CCacheStore::ReleaseContainerContext(*((CCacheStore **)this + 3), &v20);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 21, WPP_b5c7e844a87d3fa49b467b888bebb474_Traceguids, (unsigned int)SecureSubDirectory);
  return (unsigned int)SecureSubDirectory;
}

```

## disassembly

```asm
0x1800ed5e8  mov     [rsp-8+arg_8], rbx
0x1800ed5ed  mov     [rsp-8+arg_10], rsi
0x1800ed5f2  push    rbp
0x1800ed5f3  push    rdi
0x1800ed5f4  push    r12
0x1800ed5f6  push    r14
0x1800ed5f8  push    r15
0x1800ed5fa  lea     rbp, [rsp-180h]
0x1800ed602  sub     rsp, 280h
0x1800ed609  mov     rax, cs:__security_cookie
0x1800ed610  xor     rax, rsp
0x1800ed613  mov     [rbp+1A0h+var_30], rax
0x1800ed61a  mov     rsi, rcx
0x1800ed61d  xor     r15d, r15d
0x1800ed620  xorps   xmm0, xmm0
0x1800ed623  mov     [rsp+2A0h+var_26C], r15d
0x1800ed628  xor     eax, eax
0x1800ed62a  lea     rcx, [rsp+2A0h+var_240]; void *
0x1800ed62f  xor     edx, edx; Val
0x1800ed631  mov     [rsp+2A0h+var_250], ax
0x1800ed636  mov     r8d, 202h; Size
0x1800ed63c  movups  xmmword ptr [rsp+2A0h+var_260], xmm0
0x1800ed641  call    memset_0
0x1800ed646  mov     [rsp+2A0h+var_268], r15
0x1800ed64b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ed652  jz      short loc_1800ED66C
0x1800ed654  lea     edx, [r15+14h]
0x1800ed658  mov     ecx, 40Ch
0x1800ed65d  mov     r9, rsi
0x1800ed660  lea     r8, WPP_b5c7e844a87d3fa49b467b888bebb474_Traceguids
0x1800ed667  call    WPP_SF_q
0x1800ed66c  mov     rax, [rsi+0A0h]
0x1800ed673  mov     edi, [rax]
0x1800ed675  mov     eax, 20h ; ' '
0x1800ed67a  lea     r14d, [rdi+4]
0x1800ed67e  cmp     r14d, eax
0x1800ed681  lea     r12d, [rax-1Fh]
0x1800ed685  cmova   r14d, eax
0x1800ed689  cmp     edi, r14d
0x1800ed68c  jnb     short loc_1800ED6EC
0x1800ed68e  mov     rcx, [rsi+68h]; unsigned __int16 *
0x1800ed692  lea     rdx, [rsp+2A0h+var_260]; unsigned __int16 *
0x1800ed697  mov     r8d, r12d; unsigned __int16 *
0x1800ed69a  mov     [rsp+2A0h+var_26C], r15d
0x1800ed69f  call    ?CreateSecureSubDirectory@@YAJPEBGPEAGH@Z; CreateSecureSubDirectory(ushort const *,ushort *,int)
0x1800ed6a4  mov     ebx, eax
0x1800ed6a6  test    eax, eax
0x1800ed6a8  js      short loc_1800ED6D7
0x1800ed6aa  mov     rax, [rsi+0A0h]
0x1800ed6b1  movups  xmm0, xmmword ptr [rsp+2A0h+var_260]
0x1800ed6b6  mov     ecx, edi
0x1800ed6b8  add     rcx, rcx
0x1800ed6bb  mov     edx, edi
0x1800ed6bd  add     edi, r12d
0x1800ed6c0  movdqu  xmmword ptr [rax+rcx*8+4], xmm0
0x1800ed6c6  mov     rax, [rsi+0A0h]
0x1800ed6cd  mov     [rax+rdx*4+204h], r15d
0x1800ed6d5  jmp     short loc_1800ED689
0x1800ed6d7  mov     [rsp+2A0h+var_26C], 181h
0x1800ed6df  mov     [rsp+2A0h+var_26C], 1A4h
0x1800ed6e7  jmp     loc_1800ED87A
0x1800ed6ec  lea     ecx, ds:0[r14*8]
0x1800ed6f4  cmp     rcx, 7FFFFFFEh
0x1800ed6fb  jbe     short loc_1800ED70A
0x1800ed6fd  mov     [rsp+2A0h+var_240], r15w
0x1800ed703  mov     ebx, 80070057h
0x1800ed708  jmp     short loc_1800ED766
0x1800ed70a  mov     rax, [rsi+0A0h]
0x1800ed711  lea     r8, [rsp+2A0h+var_240]
0x1800ed716  add     rax, 4
0x1800ed71a  mov     edx, 101h
0x1800ed71f  test    rcx, rcx
0x1800ed722  jz      short loc_1800ED742
0x1800ed724  movzx   r9d, word ptr [rax]
0x1800ed728  test    r9w, r9w
0x1800ed72c  jz      short loc_1800ED742
0x1800ed72e  mov     [r8], r9w
0x1800ed732  add     rax, 2
0x1800ed736  add     r8, 2
0x1800ed73a  sub     rcx, r12
0x1800ed73d  sub     rdx, r12
0x1800ed740  jnz     short loc_1800ED71F
0x1800ed742  test    rdx, rdx
0x1800ed745  lea     rcx, [r8-2]
0x1800ed749  mov     rax, rdx
0x1800ed74c  cmovnz  rcx, r8
0x1800ed750  neg     rax
0x1800ed753  sbb     ebx, ebx
0x1800ed755  not     ebx
0x1800ed757  and     ebx, 8007007Ah
0x1800ed75d  mov     [rcx], r15w
0x1800ed761  test    rdx, rdx
0x1800ed764  jnz     short loc_1800ED773
0x1800ed766  mov     [rsp+2A0h+var_26C], 1B2h
0x1800ed76e  jmp     loc_1800ED87A
0x1800ed773  mov     rcx, [rsi+18h]
0x1800ed777  lea     rdx, [rsp+2A0h+var_268]; struct CJetContext **
0x1800ed77c  xor     r8d, r8d; int *
0x1800ed77f  mov     rcx, [rcx+140h]; this
0x1800ed786  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800ed78b  mov     ebx, eax
0x1800ed78d  test    eax, eax
0x1800ed78f  jns     short loc_1800ED79E
0x1800ed791  mov     [rsp+2A0h+var_26C], 1B6h
0x1800ed799  jmp     loc_1800ED87A
0x1800ed79e  mov     rdi, [rsp+2A0h+var_268]
0x1800ed7a3  lea     r8, aContaineridind; "ContainerIdIndex"
0x1800ed7aa  mov     rcx, rdi; this
0x1800ed7ad  xor     edx, edx; unsigned int
0x1800ed7af  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1800ed7b4  mov     ebx, eax
0x1800ed7b6  test    eax, eax
0x1800ed7b8  jns     short loc_1800ED7C7
0x1800ed7ba  mov     [rsp+2A0h+var_26C], 1B8h
0x1800ed7c2  jmp     loc_1800ED87A
0x1800ed7c7  mov     rcx, [rdi+10h]; sesid
0x1800ed7cb  call    cs:__imp_JetBeginTransaction
0x1800ed7d1  mov     ecx, eax; int
0x1800ed7d3  mov     edx, r12d; int
0x1800ed7d6  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ed7db  mov     ebx, eax
0x1800ed7dd  test    eax, eax
0x1800ed7df  js      loc_1800ED87A
0x1800ed7e5  mov     rdx, [rsi+8]; unsigned __int64
0x1800ed7e9  mov     rcx, rdi; struct CJetContext *
0x1800ed7ec  call    ?SeekToContainer@@YAJPEAVCJetContext@@_K@Z; SeekToContainer(CJetContext *,unsigned __int64)
0x1800ed7f1  mov     ebx, eax
0x1800ed7f3  test    eax, eax
0x1800ed7f5  jns     short loc_1800ED801
0x1800ed7f7  mov     [rsp+2A0h+var_26C], 1C2h
0x1800ed7ff  jmp     short loc_1800ED86E
0x1800ed801  jz      short loc_1800ED812
0x1800ed803  mov     ebx, 8000FFFFh
0x1800ed808  mov     [rsp+2A0h+var_26C], 1C4h
0x1800ed810  jmp     short loc_1800ED86E
0x1800ed812  mov     rdx, [rdi+20h]; tableid
0x1800ed816  mov     r8d, 2; prep
0x1800ed81c  mov     rcx, [rdi+10h]; sesid
0x1800ed820  call    cs:__imp_JetPrepareUpdate
0x1800ed826  mov     ecx, eax; int
0x1800ed828  mov     edx, r12d; int
0x1800ed82b  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ed830  mov     ebx, eax
0x1800ed832  test    eax, eax
0x1800ed834  js      short loc_1800ED86E
0x1800ed836  lea     r8, [rsp+2A0h+var_240]; unsigned __int16 *
0x1800ed83b  mov     edx, 8; unsigned int
0x1800ed840  mov     rcx, rdi; this
0x1800ed843  call    ?SetStringColumn@CJetContext@@QEAAJKPEBG@Z; CJetContext::SetStringColumn(ulong,ushort const *)
0x1800ed848  mov     ebx, eax
0x1800ed84a  test    eax, eax
0x1800ed84c  jns     loc_1800ED8D7
0x1800ed852  mov     [rsp+2A0h+var_26C], 1C9h
0x1800ed85a  mov     rdx, [rdi+20h]; tableid
0x1800ed85e  mov     r8d, 3; prep
0x1800ed864  mov     rcx, [rdi+10h]; sesid
0x1800ed868  call    cs:__imp_JetPrepareUpdate
0x1800ed86e  mov     rcx, [rdi+10h]; sesid
0x1800ed872  xor     edx, edx; grbit
0x1800ed874  call    cs:__imp_JetRollback
0x1800ed87a  mov     rcx, [rsi+18h]; this
0x1800ed87e  lea     rdx, [rsp+2A0h+var_268]; struct CJetContext **
0x1800ed883  call    ?ReleaseContainerContext@CCacheStore@@QEAAXPEAPEAVCJetContext@@@Z; CCacheStore::ReleaseContainerContext(CJetContext * *)
0x1800ed888  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ed88f  jz      short loc_1800ED8AA
0x1800ed891  mov     edx, 15h
0x1800ed896  lea     r8, WPP_b5c7e844a87d3fa49b467b888bebb474_Traceguids
0x1800ed89d  mov     ecx, 40Ch
0x1800ed8a2  mov     r9d, ebx
0x1800ed8a5  call    WPP_SF_d
0x1800ed8aa  mov     eax, ebx
0x1800ed8ac  mov     rcx, [rbp+1A0h+var_30]
0x1800ed8b3  xor     rcx, rsp; StackCookie
0x1800ed8b6  call    __security_check_cookie
0x1800ed8bb  lea     r11, [rsp+2A0h+var_20]
0x1800ed8c3  mov     rbx, [r11+38h]
0x1800ed8c7  mov     rsi, [r11+40h]
0x1800ed8cb  mov     rsp, r11
0x1800ed8ce  pop     r15
0x1800ed8d0  pop     r14
0x1800ed8d2  pop     r12
0x1800ed8d4  pop     rdi
0x1800ed8d5  pop     rbp
0x1800ed8d6  retn
0x1800ed8d7  mov     r8, [rsi+0A0h]
0x1800ed8de  lea     r9d, ds:0[r14*4]; unsigned int
0x1800ed8e6  add     r8, 204h; unsigned __int8 *
0x1800ed8ed  mov     edx, 9; unsigned int
0x1800ed8f2  mov     rcx, rdi; this
0x1800ed8f5  call    ?SetBinaryColumn@CJetContext@@QEAAJKPEBEK@Z; CJetContext::SetBinaryColumn(ulong,uchar const *,ulong)
0x1800ed8fa  mov     ebx, eax
0x1800ed8fc  test    eax, eax
0x1800ed8fe  jns     short loc_1800ED90D
0x1800ed900  mov     [rsp+2A0h+var_26C], 1CAh
0x1800ed908  jmp     loc_1800ED85A
0x1800ed90d  mov     rdx, [rdi+20h]; tableid
0x1800ed911  xor     r9d, r9d; cbBookmark
0x1800ed914  mov     rcx, [rdi+10h]; sesid
0x1800ed918  xor     r8d, r8d; pvBookmark
0x1800ed91b  mov     [rsp+2A0h+pcbActual], r15; pcbActual
0x1800ed920  call    cs:__imp_JetUpdate
0x1800ed926  mov     ecx, eax; int
0x1800ed928  mov     edx, r12d; int
0x1800ed92b  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ed930  mov     ebx, eax
0x1800ed932  test    eax, eax
0x1800ed934  js      loc_1800ED85A
0x1800ed93a  mov     rcx, [rdi+10h]; sesid
0x1800ed93e  mov     edx, r12d; grbit
0x1800ed941  call    cs:__imp_JetCommitTransaction
0x1800ed947  mov     ecx, eax; int
0x1800ed949  mov     edx, r12d; int
0x1800ed94c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ed951  mov     ebx, eax
0x1800ed953  test    eax, eax
0x1800ed955  js      loc_1800ED86E
0x1800ed95b  mov     rax, [rsi+0A0h]
0x1800ed962  mov     [rax], r14d
0x1800ed965  jmp     loc_1800ED87A
```
