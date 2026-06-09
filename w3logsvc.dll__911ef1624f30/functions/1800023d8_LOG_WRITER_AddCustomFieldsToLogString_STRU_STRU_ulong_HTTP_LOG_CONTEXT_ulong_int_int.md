# LOG_WRITER::AddCustomFieldsToLogString(STRU *,STRU *,ulong *,HTTP_LOG_CONTEXT *,ulong *,int,int)

- ea: `0x1800023d8`
- end: `0x1800026fc`
- name: `?AddCustomFieldsToLogString@LOG_WRITER@@AEAAJPEAVSTRU@@0PEAKPEAVHTTP_LOG_CONTEXT@@1HH@Z`
- size: `804`
- prototype: `__int64 __fastcall(LOG_WRITER *this, struct STRU *, struct STRU *, unsigned int *, struct HTTP_LOG_CONTEXT *, unsigned int *, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003718`

## callees

- `0x1800023d8`
- `0x1800029c0`
- `0x180002eb8`
- `0x18000e97a`
- `0x18000e9a0`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18000255f`
- `msvcrt!wcsnlen` at `0x18000255f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800026d1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800026d1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002456`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002456`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000251e`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800025f4`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002645`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000251e`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800025f4`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002645`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800025a4`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18000262e`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800025a4`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18000262e`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::AddCustomFieldsToLogString(
        LOG_WRITER *this,
        struct STRU *a2,
        struct STRU *a3,
        unsigned int *a4,
        struct HTTP_LOG_CONTEXT *a5,
        unsigned int *a6,
        int a7,
        int a8)
{
  int appended; // ebx
  __int64 v12; // rdi
  unsigned __int64 v13; // rcx
  const unsigned __int16 *v14; // rsi
  const unsigned __int16 *v15; // rdi
  __int64 v16; // r9
  const unsigned __int16 *v17; // rax
  int v18; // edx
  __int64 v19; // rax
  const wchar_t *v20; // rdi
  unsigned int v21; // r8d
  LOG_WRITER *v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  unsigned __int64 v25; // r9
  unsigned int v26; // r9d
  __int64 v27; // rax
  __int64 v28; // rax
  struct MULTISZ *v30; // [rsp+20h] [rbp-E0h]
  unsigned int v31; // [rsp+40h] [rbp-C0h]
  _BYTE v34[32]; // [rsp+60h] [rbp-A0h] BYREF
  LOG_WRITER *v35; // [rsp+80h] [rbp-80h]
  int v36; // [rsp+88h] [rbp-78h]
  int v37; // [rsp+90h] [rbp-70h]
  unsigned __int16 v38[128]; // [rsp+A0h] [rbp-60h] BYREF

  appended = 0;
  v12 = *((_QWORD *)a5 + 102);
  memset_0(v38, 0, sizeof(v38));
  STRU::STRU((STRU *)v34, v38, 0x80u);
  v13 = *(_QWORD *)(*((_QWORD *)this + 1) + 192LL);
  v14 = (const unsigned __int16 *)(v13 & -(__int64)(*(_WORD *)v13 != 0));
  if ( v12
    && (v31 = 0,
        v13 = *(_QWORD *)(v12 + 32),
        (v15 = (const unsigned __int16 *)(v13 & -(__int64)(*(_WORD *)v13 != 0))) != 0) )
  {
    v16 = -1;
    while ( v14 )
    {
      v17 = v15;
      do
      {
        v13 = *(const unsigned __int16 *)((char *)v17 + (char *)v14 - (char *)v15);
        v18 = *v17 - (_DWORD)v13;
        if ( v18 )
          break;
        ++v17;
      }
      while ( (_DWORD)v13 );
      if ( v18 )
        goto LABEL_38;
      *(_WORD *)v35 = 0;
      v37 = 0;
      do
        ++v16;
      while ( v15[v16] );
      appended = LOG_WRITER::AppendStringReplaceSpaces((LOG_WRITER *)v13, (struct STRU *)v34, v15, v16, 0x2Du);
      if ( appended < 0 )
        break;
      if ( a7 )
      {
        appended = STRU::Append(a3, (const struct STRU *)v34);
        if ( appended < 0 )
          break;
        *a4 |= 0x80000000;
      }
      v19 = -1;
      do
        ++v19;
      while ( v15[v19] );
      v20 = &v15[v19 + 1];
      if ( !*v20 )
        goto LABEL_38;
      v21 = wcsnlen(v20, 0x1000u);
      v31 += 2 * v21;
      v22 = v35;
      *(_WORD *)v35 = 0;
      v37 = 0;
      v23 = *((_QWORD *)this + 1);
      if ( v31 <= *(_DWORD *)(v23 + 220) )
      {
        v25 = *(unsigned int *)(v23 + 216);
        if ( 2 * (unsigned __int64)v21 <= v25 )
          v26 = v21;
        else
          v26 = (unsigned int)v25 >> 1;
        v24 = LOG_WRITER::AppendStringReplaceSpaces(v22, (struct STRU *)v34, v20, v26, 0x2Bu);
      }
      else
      {
        v24 = STRU::Append((STRU *)v34, L"- ", 2u);
      }
      appended = v24;
      if ( v24 < 0 )
        break;
      if ( a8 )
      {
        appended = STRU::Append(a2, (const struct STRU *)v34);
        if ( appended < 0 )
          break;
      }
      if ( a7 )
      {
        if ( v36 + *a6 <= 0xF618 )
        {
          appended = STRU::Append(a3, (const struct STRU *)v34);
          *a6 += v36;
        }
        else
        {
          appended = STRU::Append(a3, L"- ", 2u);
          *a6 += 2;
        }
        if ( appended < 0 )
          break;
      }
      v16 = -1;
      v27 = -1;
      do
        ++v27;
      while ( v20[v27] );
      v15 = (const unsigned __int16 *)((unsigned __int64)&v20[v27 + 1] & -(__int64)(v20[v27 + 1] != 0));
      v28 = -1;
      do
        ++v28;
      while ( v14[v28] );
      v13 = (unsigned __int64)&v14[v28 + 1];
      v14 = (const unsigned __int16 *)(v13 & -(__int64)(*(_WORD *)v13 != 0));
      if ( !v15 )
        goto LABEL_37;
    }
  }
  else
  {
LABEL_37:
    if ( v14 )
LABEL_38:
      appended = LOG_WRITER::AppendHyphensForRemainingCustomHeaders((LOG_WRITER *)v13, a2, a3, v14, v30, a8, a7);
  }
  STRU::~STRU((STRU *)v34);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800023d8  push    rbp
0x1800023da  push    rbx
0x1800023db  push    rsi
0x1800023dc  push    rdi
0x1800023dd  push    r12
0x1800023df  push    r13
0x1800023e1  push    r14
0x1800023e3  push    r15
0x1800023e5  lea     rbp, [rsp-0B8h]
0x1800023ed  sub     rsp, 1B8h
0x1800023f4  mov     rax, cs:__security_cookie
0x1800023fb  xor     rax, rsp
0x1800023fe  mov     [rbp+0F0h+var_50], rax
0x180002405  mov     [rsp+1F0h+var_1A0], r9
0x18000240a  mov     r14, r8
0x18000240d  mov     r13, rdx
0x180002410  mov     rsi, rcx
0x180002413  mov     [rsp+1F0h+var_198], rcx
0x180002418  mov     rax, [rbp+0F0h+arg_20]
0x18000241f  mov     rcx, [rbp+0F0h+arg_28]
0x180002426  mov     [rsp+1F0h+var_1A8], rcx
0x18000242b  xor     ecx, ecx
0x18000242d  mov     ebx, ecx
0x18000242f  mov     rdi, [rax+330h]
0x180002436  xor     edx, edx; Val
0x180002438  mov     r8d, 100h; Size
0x18000243e  lea     rcx, [rbp+0F0h+var_150]; void *
0x180002442  call    memset_0
0x180002447  mov     r8d, 80h
0x18000244d  lea     rdx, [rbp+0F0h+var_150]
0x180002451  lea     rcx, [rsp+1F0h+var_190]
0x180002456  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000245c  nop
0x18000245d  mov     rax, [rsi+8]
0x180002461  mov     rcx, [rax+0C0h]
0x180002468  movzx   eax, word ptr [rcx]
0x18000246b  neg     ax
0x18000246e  sbb     rsi, rsi
0x180002471  and     rsi, rcx
0x180002474  mov     r12d, [rbp+0F0h+arg_38]
0x18000247b  mov     r15d, [rbp+0F0h+arg_30]
0x180002482  xor     r10d, r10d
0x180002485  test    rdi, rdi
0x180002488  jz      loc_1800026AD
0x18000248e  mov     [rsp+1F0h+var_1B0], r10d
0x180002493  mov     rcx, [rdi+20h]
0x180002497  movzx   eax, word ptr [rcx]
0x18000249a  neg     ax
0x18000249d  sbb     rdi, rdi
0x1800024a0  and     rdi, rcx
0x1800024a3  jz      loc_1800026AD
0x1800024a9  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800024ad  test    rsi, rsi
0x1800024b0  jz      loc_1800026CC
0x1800024b6  mov     rax, rdi
0x1800024b9  mov     r8, rsi
0x1800024bc  sub     r8, rdi
0x1800024bf  movzx   edx, word ptr [rax]
0x1800024c2  movzx   ecx, word ptr [rax+r8]; this
0x1800024c7  sub     edx, ecx
0x1800024c9  jnz     short loc_1800024D3
0x1800024cb  add     rax, 2
0x1800024cf  test    ecx, ecx
0x1800024d1  jnz     short loc_1800024BF
0x1800024d3  test    edx, edx
0x1800024d5  jnz     loc_1800026B2
0x1800024db  mov     rax, [rbp+0F0h+var_170]
0x1800024df  mov     [rax], r10w
0x1800024e3  mov     [rbp+0F0h+var_160], r10d
0x1800024e7  inc     r9; unsigned int
0x1800024ea  cmp     [rdi+r9*2], r10w
0x1800024ef  jnz     short loc_1800024E7
0x1800024f1  mov     word ptr [rsp+1F0h+var_1D0], 2Dh ; '-'; unsigned __int16
0x1800024f8  mov     r8, rdi; unsigned __int16 *
0x1800024fb  lea     rdx, [rsp+1F0h+var_190]; struct STRU *
0x180002500  call    ?AppendStringReplaceSpaces@LOG_WRITER@@AEAAJPEAVSTRU@@PEBGKG@Z; LOG_WRITER::AppendStringReplaceSpaces(STRU *,ushort const *,ulong,ushort)
0x180002505  mov     ebx, eax
0x180002507  test    eax, eax
0x180002509  js      loc_1800026CC
0x18000250f  xor     ebx, ebx
0x180002511  test    r15d, r15d
0x180002514  jz      short loc_180002539
0x180002516  lea     rdx, [rsp+1F0h+var_190]
0x18000251b  mov     rcx, r14
0x18000251e  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180002524  mov     ebx, eax
0x180002526  test    eax, eax
0x180002528  js      loc_1800026CC
0x18000252e  mov     rax, [rsp+1F0h+var_1A0]
0x180002533  bts     dword ptr [rax], 1Fh
0x180002537  xor     ebx, ebx
0x180002539  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000253d  inc     rax
0x180002540  cmp     [rdi+rax*2], bx
0x180002544  jnz     short loc_18000253D
0x180002546  lea     rdi, [rdi+rax*2]
0x18000254a  add     rdi, 2
0x18000254e  cmp     [rdi], bx
0x180002551  jz      loc_1800026B2
0x180002557  mov     edx, 1000h; MaxCount
0x18000255c  mov     rcx, rdi; Source
0x18000255f  call    cs:__imp_wcsnlen
0x180002565  mov     r8, rax
0x180002568  mov     r9d, [rsp+1F0h+var_1B0]
0x18000256d  lea     r9d, [r9+rax*2]
0x180002571  mov     [rsp+1F0h+var_1B0], r9d
0x180002576  mov     rcx, [rbp+0F0h+var_170]; this
0x18000257a  mov     [rcx], bx
0x18000257d  mov     [rbp+0F0h+var_160], ebx
0x180002580  mov     rax, [rsp+1F0h+var_198]
0x180002585  mov     rax, [rax+8]
0x180002589  cmp     r9d, [rax+0DCh]
0x180002590  jbe     short loc_1800025AC
0x180002592  mov     r8d, 2
0x180002598  lea     rdx, asc_180012130; "- "
0x18000259f  lea     rcx, [rsp+1F0h+var_190]
0x1800025a4  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x1800025aa  jmp     short loc_1800025DA
0x1800025ac  mov     r9d, [rax+0D8h]
0x1800025b3  mov     eax, r8d
0x1800025b6  add     rax, rax
0x1800025b9  mov     word ptr [rsp+1F0h+var_1D0], 2Bh ; '+'; struct MULTISZ *
0x1800025c0  lea     rdx, [rsp+1F0h+var_190]; struct STRU *
0x1800025c5  cmp     rax, r9
0x1800025c8  jbe     short loc_1800025CF
0x1800025ca  shr     r9d, 1
0x1800025cd  jmp     short loc_1800025D2
0x1800025cf  mov     r9d, r8d; unsigned int
0x1800025d2  mov     r8, rdi; unsigned __int16 *
0x1800025d5  call    ?AppendStringReplaceSpaces@LOG_WRITER@@AEAAJPEAVSTRU@@PEBGKG@Z; LOG_WRITER::AppendStringReplaceSpaces(STRU *,ushort const *,ulong,ushort)
0x1800025da  mov     ebx, eax
0x1800025dc  xor     r10d, r10d
0x1800025df  test    eax, eax
0x1800025e1  js      loc_1800026CC
0x1800025e7  test    r12d, r12d
0x1800025ea  jz      short loc_180002607
0x1800025ec  lea     rdx, [rsp+1F0h+var_190]
0x1800025f1  mov     rcx, r13
0x1800025f4  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x1800025fa  mov     ebx, eax
0x1800025fc  xor     r10d, r10d
0x1800025ff  test    eax, eax
0x180002601  js      loc_1800026CC
0x180002607  test    r15d, r15d
0x18000260a  jz      short loc_18000265E
0x18000260c  mov     rcx, [rsp+1F0h+var_1A8]
0x180002611  mov     ecx, [rcx]
0x180002613  add     ecx, [rbp+0F0h+var_168]
0x180002616  cmp     ecx, 0F618h
0x18000261c  mov     rcx, r14
0x18000261f  jbe     short loc_180002640
0x180002621  mov     r8d, 2
0x180002627  lea     rdx, asc_180012130; "- "
0x18000262e  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180002634  mov     ebx, eax
0x180002636  mov     rcx, [rsp+1F0h+var_1A8]
0x18000263b  add     dword ptr [rcx], 2
0x18000263e  jmp     short loc_180002657
0x180002640  lea     rdx, [rsp+1F0h+var_190]
0x180002645  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18000264b  mov     ebx, eax
0x18000264d  mov     eax, [rbp+0F0h+var_168]
0x180002650  mov     rcx, [rsp+1F0h+var_1A8]
0x180002655  add     [rcx], eax
0x180002657  xor     r10d, r10d
0x18000265a  test    ebx, ebx
0x18000265c  js      short loc_1800026CC
0x18000265e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180002662  mov     rax, r9
0x180002665  inc     rax
0x180002668  cmp     [rdi+rax*2], r10w
0x18000266d  jnz     short loc_180002665
0x18000266f  lea     rcx, [rdi+2]
0x180002673  lea     rcx, [rcx+rax*2]
0x180002677  movzx   eax, word ptr [rcx]
0x18000267a  neg     ax
0x18000267d  sbb     rdi, rdi
0x180002680  and     rdi, rcx
0x180002683  mov     rax, r9
0x180002686  inc     rax
0x180002689  cmp     [rsi+rax*2], r10w
0x18000268e  jnz     short loc_180002686
0x180002690  lea     rcx, [rsi+2]
0x180002694  lea     rcx, [rcx+rax*2]; this
0x180002698  movzx   eax, word ptr [rcx]
0x18000269b  neg     ax
0x18000269e  sbb     rsi, rsi
0x1800026a1  and     rsi, rcx
0x1800026a4  test    rdi, rdi
0x1800026a7  jnz     loc_1800024AD
0x1800026ad  test    rsi, rsi
0x1800026b0  jz      short loc_1800026CC
0x1800026b2  mov     [rsp+1F0h+var_1C0], r15d; int
0x1800026b7  mov     [rsp+1F0h+var_1C8], r12d; int
0x1800026bc  mov     r9, rsi; unsigned __int16 *
0x1800026bf  mov     r8, r14; struct STRU *
0x1800026c2  mov     rdx, r13; struct STRU *
0x1800026c5  call    ?AppendHyphensForRemainingCustomHeaders@LOG_WRITER@@AEAAJPEAVSTRU@@0PEBGPEAVMULTISZ@@HH@Z; LOG_WRITER::AppendHyphensForRemainingCustomHeaders(STRU *,STRU *,ushort const *,MULTISZ *,int,int)
0x1800026ca  mov     ebx, eax
0x1800026cc  lea     rcx, [rsp+1F0h+var_190]
0x1800026d1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800026d7  mov     eax, ebx
0x1800026d9  mov     rcx, [rbp+0F0h+var_50]
0x1800026e0  xor     rcx, rsp; StackCookie
0x1800026e3  call    __security_check_cookie
0x1800026e8  add     rsp, 1B8h
0x1800026ef  pop     r15
0x1800026f1  pop     r14
0x1800026f3  pop     r13
0x1800026f5  pop     r12
0x1800026f7  pop     rdi
0x1800026f8  pop     rsi
0x1800026f9  pop     rbx
0x1800026fa  pop     rbp
0x1800026fb  retn
```
