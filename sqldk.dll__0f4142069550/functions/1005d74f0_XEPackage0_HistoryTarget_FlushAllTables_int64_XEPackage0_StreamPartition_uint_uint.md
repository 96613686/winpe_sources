# XEPackage0::HistoryTarget::FlushAllTables(__int64,XEPackage0::StreamPartition *,uint,uint &)

- ea: `0x1005d74f0`
- end: `0x1005d78a6`
- name: `?FlushAllTables@HistoryTarget@XEPackage0@@AEAAH_JPEAUStreamPartition@2@IAEAI@Z`
- size: `950`
- prototype: `__int64 __usercall@<rax>(XEPackage0::HistoryTarget *__hidden this@<rcx>, __int64@<rdx>, struct XEPackage0::StreamPartition *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1005d2e50`
- `0x1005d72d0`

## callees

- `0x100403070`
- `0x100443110`
- `0x10044c9b0`
- `0x100450f10`
- `0x100451110`
- `0x100451260`
- `0x100451370`
- `0x1005d5a40`
- `0x1005d69b0`
- `0x1005d74f0`
- `0x1005d8ec0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1005d754c`
- `KERNEL32!GetCurrentThreadId` at `0x1005d7572`
- `KERNEL32!GetCurrentThreadId` at `0x1005d758d`
- `KERNEL32!GetCurrentThreadId` at `0x1005d754c`
- `KERNEL32!GetCurrentThreadId` at `0x1005d7572`
- `KERNEL32!GetCurrentThreadId` at `0x1005d758d`

## pseudocode

```c
__int64 __fastcall XEPackage0::HistoryTarget::FlushAllTables(
        XEPackage0::HistoryTarget *this,
        __int64 a2,
        struct XEPackage0::StreamPartition *a3,
        unsigned int a4,
        unsigned int *a5)
{
  unsigned int v5; // r12d
  unsigned int v6; // edi
  int **v9; // rax
  unsigned int i; // r13d
  int *v11; // r14
  int v12; // ecx
  int v13; // esi
  unsigned __int64 *v14; // rbx
  CXFixedTable *v15; // rdi
  __int64 v16; // rax
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  double v19; // xmm0_8
  unsigned __int64 v20; // rax
  int v21; // eax
  __int64 result; // rax
  int v23; // ecx
  __int64 v24; // rbx
  int started; // eax
  unsigned __int64 v26; // [rsp+28h] [rbp-B0h]
  int **v28; // [rsp+38h] [rbp-A0h]
  unsigned int v29; // [rsp+40h] [rbp-98h] BYREF
  int v30; // [rsp+44h] [rbp-94h]
  int v31; // [rsp+48h] [rbp-90h] BYREF
  __int64 v32; // [rsp+50h] [rbp-88h]
  unsigned int *v33; // [rsp+58h] [rbp-80h]
  _QWORD v34[2]; // [rsp+60h] [rbp-78h] BYREF
  __int16 v35; // [rsp+70h] [rbp-68h] BYREF
  __int64 v36; // [rsp+78h] [rbp-60h]
  __int64 v37; // [rsp+80h] [rbp-58h]

  v5 = 1;
  v33 = a5;
  v6 = a4;
  v30 = 1;
  v32 = a2;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)a3 + 4, GetCurrentThreadId(), 0) )
  {
    while ( 1 )
    {
      qword_100714F50(*((_QWORD *)a3 + 3), 0xFFFFFFFFLL, 0);
      if ( !_InterlockedCompareExchange((volatile signed __int32 *)a3 + 4, GetCurrentThreadId(), 0) )
        break;
      qword_100714F58(*((_QWORD *)a3 + 3));
      if ( !_InterlockedCompareExchange((volatile signed __int32 *)a3 + 4, GetCurrentThreadId(), 0) )
        goto LABEL_4;
    }
  }
  else
  {
LABEL_4:
    qword_100714F50(*((_QWORD *)a3 + 3), 0xFFFFFFFFLL, 0);
  }
  v9 = (int **)((char *)this + 32);
  v28 = (int **)((char *)this + 32);
  for ( i = 0; i < 0x400; ++i )
  {
    v11 = *v9;
    if ( *v9 )
    {
      v12 = *v11;
      v13 = 0;
      if ( *v11 )
      {
        while ( 1 )
        {
          v14 = (unsigned __int64 *)(*((_QWORD *)v11 + 1) + 24LL * (v13 + v12 * v6));
          if ( v14 )
          {
            v15 = (CXFixedTable *)v14[2];
            if ( v15 && *(_DWORD *)(**((_QWORD **)v15 + 3) + 8LL) )
            {
              v16 = *((_QWORD *)this + 1030);
              v34[0] = &XE_ILiveSessionMetadata::`vftable';
              v34[1] = v16;
              XE_ILiveSessionMetadata::GetTicksConfig((XE_ILiveSessionMetadata *)v34, (struct XETicksConfig *)&v35);
              v17 = *v14;
              v18 = 0;
              if ( v35 == 1 )
              {
                if ( v37 )
                {
                  if ( v37 < 0 )
                    v19 = (double)(int)(v37 & 1 | ((unsigned __int64)v37 >> 1))
                        + (double)(int)(v37 & 1 | ((unsigned __int64)v37 >> 1));
                  else
                    v19 = (double)(int)v37;
                  v18 = v36 + (unsigned int)(int)(10000000.0 / v19 * (double)(int)v17);
LABEL_19:
                  if ( v18 > v32 )
                  {
                    v6 = a4;
                  }
                  else
                  {
                    v29 = -1;
                    ++*v33;
                    if ( !(unsigned int)CXFixedTable::FlushTable(v15, *((struct XE_CXFileWriter **)a3 + 1), 0, &v29) )
                      return 0;
                    v6 = a4;
                    v26 = v14[1];
                    v20 = *v14;
                    v31 = i & 0x3FF | ((v13 & 0x3FFFF) << 10);
                    v21 = XEPackage0::HistoryTarget::WriteEventTableFrame(
                            this,
                            v29,
                            a4,
                            (const struct XERelativeObjectId *)&v31,
                            v20,
                            v26);
                    v30 = v21;
                    *v14 = -1;
                    v14[1] = 0;
                    if ( !v21 )
                      return 0;
                  }
                  goto LABEL_25;
                }
              }
              else if ( v35 )
              {
                goto LABEL_19;
              }
              v18 = v17 + v36;
              goto LABEL_19;
            }
            v6 = a4;
          }
LABEL_25:
          v12 = *v11;
          if ( ++v13 >= (unsigned int)*v11 )
          {
            v9 = v28;
            break;
          }
        }
      }
    }
    v28 = ++v9;
  }
  v23 = v30;
  if ( !v30 || *((_DWORD *)this + 6) )
  {
    *(_DWORD *)(*((_QWORD *)a3 + 1) + 832LL) = 1;
    if ( !v23 )
      goto LABEL_38;
  }
  v24 = *((_QWORD *)a3 + 1);
  if ( *(_DWORD *)(v24 + 680) )
  {
    if ( !(unsigned int)XE_CXFileWriter::FlushWriterSync((XE_CXFileWriter *)v24, 0) )
      goto LABEL_38;
    XE_CXFileWriter::CloseWriter(*((XE_CXFileWriter **)a3 + 1));
    ++*((_DWORD *)this + v6 + 2658);
    ++*((_QWORD *)this + 3851);
    if ( !(unsigned int)XEPackage0::HistoryTarget::AddMetadataFrame<MasterMetadataRecord>(
                          this,
                          12345677,
                          (char *)this + 10616,
                          (char *)this + 14216) )
      goto LABEL_38;
    started = XEPackage0::HistoryTarget::OpenWriter(
                this,
                *((struct XE_CXFileWriter **)a3 + 1),
                0,
                (wchar_t *)L"eventstream",
                v6,
                *((_DWORD *)this + v6 + 2658));
  }
  else
  {
    ++*(_QWORD *)(v24 + 728);
    if ( !(unsigned int)XE_CXFileWriter::FlushDirectory((XE_CXFileWriter *)v24, 1) )
    {
LABEL_38:
      v5 = 0;
      goto LABEL_39;
    }
    started = XE_CXFileWriter::StartIO(
                (XE_CXFileWriter *)v24,
                (struct CXFilePage *)(*(_QWORD *)(v24 + 600) + 80LL * *(unsigned int *)(v24 + 612)),
                0);
  }
  if ( !started )
    goto LABEL_38;
LABEL_39:
  qword_100714F58(*((_QWORD *)a3 + 3));
  result = v5;
  *((_DWORD *)a3 + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x1005d74f0  mov     [rsp+arg_8], rbx
0x1005d74f5  push    rbp
0x1005d74f6  push    rsi
0x1005d74f7  push    rdi
0x1005d74f8  push    r12
0x1005d74fa  push    r13
0x1005d74fc  push    r14
0x1005d74fe  push    r15
0x1005d7500  sub     rsp, 0A0h
0x1005d7507  movaps  [rsp+0D8h+var_48], xmm6
0x1005d750f  mov     rax, cs:__security_cookie
0x1005d7516  xor     rax, rsp
0x1005d7519  mov     [rsp+0D8h+var_50], rax
0x1005d7521  mov     rax, [rsp+0D8h+arg_20]
0x1005d7529  mov     r12d, 1
0x1005d752f  mov     [rsp+0D8h+var_80], rax
0x1005d7534  mov     edi, r9d
0x1005d7537  mov     [rsp+0D8h+var_94], r12d
0x1005d753c  mov     rbp, r8
0x1005d753f  mov     [rsp+0D8h+var_A8], r9d
0x1005d7544  mov     r15, rcx
0x1005d7547  mov     [rsp+0D8h+var_88], rdx
0x1005d754c  call    cs:__imp_GetCurrentThreadId
0x1005d7552  mov     ecx, eax
0x1005d7554  xor     eax, eax
0x1005d7556  lock cmpxchg [rbp+10h], ecx
0x1005d755b  jz      short loc_1005D759E
0x1005d755d  nop     dword ptr [rax]
0x1005d7560  mov     rcx, [rbp+18h]
0x1005d7564  xor     r8d, r8d
0x1005d7567  mov     edx, 0FFFFFFFFh
0x1005d756c  call    cs:qword_100714F50
0x1005d7572  call    cs:__imp_GetCurrentThreadId
0x1005d7578  mov     ecx, eax
0x1005d757a  xor     eax, eax
0x1005d757c  lock cmpxchg [rbp+10h], ecx
0x1005d7581  jz      short loc_1005D75B0
0x1005d7583  mov     rcx, [rbp+18h]
0x1005d7587  call    cs:qword_100714F58
0x1005d758d  call    cs:__imp_GetCurrentThreadId
0x1005d7593  mov     ecx, eax
0x1005d7595  xor     eax, eax
0x1005d7597  lock cmpxchg [rbp+10h], ecx
0x1005d759c  jnz     short loc_1005D7560
0x1005d759e  mov     rcx, [rbp+18h]
0x1005d75a2  xor     r8d, r8d
0x1005d75a5  mov     edx, 0FFFFFFFFh
0x1005d75aa  call    cs:qword_100714F50
0x1005d75b0  movsd   xmm6, cs:__real@416312d000000000
0x1005d75b8  lea     rax, [r15+20h]
0x1005d75bc  xor     r8d, r8d
0x1005d75bf  mov     [rsp+0D8h+var_A0], rax
0x1005d75c4  mov     r13d, r8d
0x1005d75c7  lea     rdx, ??_7XE_ILiveSessionMetadata@@6B@; const XE_ILiveSessionMetadata::`vftable'
0x1005d75ce  xchg    ax, ax
0x1005d75d0  mov     r14, [rax]
0x1005d75d3  test    r14, r14
0x1005d75d6  jz      loc_1005D776A
0x1005d75dc  mov     ecx, [r14]
0x1005d75df  mov     esi, r8d
0x1005d75e2  test    ecx, ecx
0x1005d75e4  jz      loc_1005D776A
0x1005d75ea  nop     word ptr [rax+rax]
0x1005d75ef  nop
0x1005d75f0  mov     eax, edi
0x1005d75f2  imul    eax, ecx
0x1005d75f5  add     eax, esi
0x1005d75f7  lea     rcx, [rax+rax*2]
0x1005d75fb  mov     rax, [r14+8]
0x1005d75ff  lea     rbx, [rax+rcx*8]
0x1005d7603  test    rbx, rbx
0x1005d7606  jz      loc_1005D7758
0x1005d760c  mov     rdi, [rbx+10h]
0x1005d7610  test    rdi, rdi
0x1005d7613  jz      loc_1005D7747
0x1005d7619  mov     rax, [rdi+18h]
0x1005d761d  mov     rcx, [rax]
0x1005d7620  cmp     dword ptr [rcx+8], 0
0x1005d7624  jbe     loc_1005D7747
0x1005d762a  mov     rax, [r15+2030h]
0x1005d7631  lea     rcx, [rsp+0D8h+var_78]; this
0x1005d7636  mov     [rsp+0D8h+var_78], rdx
0x1005d763b  lea     rdx, [rsp+0D8h+var_68]; struct XETicksConfig *
0x1005d7640  mov     [rsp+0D8h+var_70], rax
0x1005d7645  call    ?GetTicksConfig@XE_ILiveSessionMetadata@@UEBAXPEAUXETicksConfig@@@Z; XE_ILiveSessionMetadata::GetTicksConfig(XETicksConfig *)
0x1005d764a  movzx   ecx, [rsp+0D8h+var_68]
0x1005d764f  xor     r8d, r8d; struct XPRESS9_ENCODER_T *
0x1005d7652  mov     rdx, [rbx]
0x1005d7655  mov     eax, r8d
0x1005d7658  cmp     r12w, cx
0x1005d765c  jnz     short loc_1005D76AB
0x1005d765e  mov     rcx, [rsp+0D8h+var_58]
0x1005d7666  test    rcx, rcx
0x1005d7669  jz      short loc_1005D76B1
0x1005d766b  xorps   xmm0, xmm0
0x1005d766e  js      short loc_1005D7677
0x1005d7670  cvtsi2sd xmm0, rcx
0x1005d7675  jmp     short loc_1005D768C
0x1005d7677  mov     rax, rcx
0x1005d767a  and     ecx, r12d
0x1005d767d  shr     rax, 1
0x1005d7680  or      rax, rcx
0x1005d7683  cvtsi2sd xmm0, rax
0x1005d7688  addsd   xmm0, xmm0
0x1005d768c  movaps  xmm1, xmm6
0x1005d768f  divsd   xmm1, xmm0
0x1005d7693  xorps   xmm0, xmm0
0x1005d7696  cvtsi2sd xmm0, rdx
0x1005d769b  mulsd   xmm1, xmm0
0x1005d769f  cvttsd2si rax, xmm1
0x1005d76a4  add     rax, [rsp+0D8h+var_60]
0x1005d76a9  jmp     short loc_1005D76B9
0x1005d76ab  cmp     r8w, cx
0x1005d76af  jnz     short loc_1005D76B9
0x1005d76b1  mov     rax, [rsp+0D8h+var_60]
0x1005d76b6  add     rax, rdx
0x1005d76b9  cmp     rax, [rsp+0D8h+var_88]
0x1005d76be  jg      loc_1005D774D
0x1005d76c4  mov     rax, [rsp+0D8h+var_80]
0x1005d76c9  lea     r9, [rsp+0D8h+var_98]; unsigned int *
0x1005d76ce  mov     rcx, rdi; this
0x1005d76d1  mov     [rsp+0D8h+var_98], 0FFFFFFFFh
0x1005d76d9  inc     dword ptr [rax]
0x1005d76db  mov     rdx, [rbp+8]; struct XE_CXFileWriter *
0x1005d76df  call    ?FlushTable@CXFixedTable@@QEAAHPEAVXE_CXFileWriter@@PEBUXPRESS9_ENCODER_T@@AEAK@Z; CXFixedTable::FlushTable(XE_CXFileWriter *,XPRESS9_ENCODER_T const *,ulong &)
0x1005d76e4  test    eax, eax
0x1005d76e6  jz      short loc_1005D7740
0x1005d76e8  mov     edi, [rsp+0D8h+var_A8]
0x1005d76ec  lea     r9, [rsp+0D8h+var_90]; struct XERelativeObjectId *
0x1005d76f1  mov     edx, [rsp+0D8h+var_98]; unsigned int
0x1005d76f5  mov     ecx, esi
0x1005d76f7  and     ecx, 3FFFFh
0x1005d76fd  mov     eax, r13d
0x1005d7700  and     eax, 3FFh
0x1005d7705  shl     ecx, 0Ah
0x1005d7708  or      ecx, eax
0x1005d770a  mov     r8d, edi; unsigned int
0x1005d770d  mov     rax, [rbx+8]
0x1005d7711  mov     qword ptr [rsp+0D8h+var_B0], rax; unsigned __int64
0x1005d7716  mov     rax, [rbx]
0x1005d7719  mov     [rsp+0D8h+var_90], ecx
0x1005d771d  mov     rcx, r15; this
0x1005d7720  mov     qword ptr [rsp+0D8h+var_B8], rax; unsigned __int64
0x1005d7725  call    ?WriteEventTableFrame@HistoryTarget@XEPackage0@@AEAAHKIPEBUXERelativeObjectId@@_K1@Z; XEPackage0::HistoryTarget::WriteEventTableFrame(ulong,uint,XERelativeObjectId const *,unsigned __int64,unsigned __int64)
0x1005d772a  xor     r8d, r8d
0x1005d772d  mov     [rsp+0D8h+var_94], eax
0x1005d7731  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1005d7738  mov     [rbx+8], r8
0x1005d773c  test    eax, eax
0x1005d773e  jnz     short loc_1005D7751
0x1005d7740  xor     eax, eax
0x1005d7742  jmp     loc_1005D7873
0x1005d7747  mov     edi, [rsp+0D8h+var_A8]
0x1005d774b  jmp     short loc_1005D7758
0x1005d774d  mov     edi, [rsp+0D8h+var_A8]
0x1005d7751  lea     rdx, ??_7XE_ILiveSessionMetadata@@6B@; const XE_ILiveSessionMetadata::`vftable'
0x1005d7758  mov     ecx, [r14]
0x1005d775b  inc     esi
0x1005d775d  cmp     esi, ecx
0x1005d775f  jb      loc_1005D75F0
0x1005d7765  mov     rax, [rsp+0D8h+var_A0]
0x1005d776a  add     rax, 8
0x1005d776e  inc     r13d
0x1005d7771  mov     [rsp+0D8h+var_A0], rax
0x1005d7776  cmp     r13d, 400h
0x1005d777d  jb      loc_1005D75D0
0x1005d7783  mov     ecx, [rsp+0D8h+var_94]
0x1005d7787  test    ecx, ecx
0x1005d7789  jz      short loc_1005D7792
0x1005d778b  cmp     dword ptr [r15+18h], 0
0x1005d7790  jz      short loc_1005D77A5
0x1005d7792  mov     rax, [rbp+8]
0x1005d7796  mov     [rax+340h], r12d
0x1005d779d  test    ecx, ecx
0x1005d779f  jz      loc_1005D785C
0x1005d77a5  mov     rbx, [rbp+8]
0x1005d77a9  mov     rcx, rbx; this
0x1005d77ac  cmp     dword ptr [rbx+2A8h], 0
0x1005d77b3  jz      short loc_1005D7825
0x1005d77b5  xor     edx, edx; int
0x1005d77b7  call    ?FlushWriterSync@XE_CXFileWriter@@QEAAHH@Z; XE_CXFileWriter::FlushWriterSync(int)
0x1005d77bc  test    eax, eax
0x1005d77be  jz      loc_1005D785C
0x1005d77c4  mov     rcx, [rbp+8]; this
0x1005d77c8  call    ?CloseWriter@XE_CXFileWriter@@QEAAHXZ; XE_CXFileWriter::CloseWriter(void)
0x1005d77cd  mov     ebx, edi
0x1005d77cf  lea     r9, [r15+3788h]
0x1005d77d6  lea     r8, [r15+2978h]
0x1005d77dd  mov     edx, 0BC614Dh
0x1005d77e2  mov     rcx, r15
0x1005d77e5  inc     dword ptr [r15+rbx*4+2988h]
0x1005d77ed  inc     qword ptr [r15+7858h]
0x1005d77f4  call    ??$AddMetadataFrame@UMasterMetadataRecord@@@HistoryTarget@XEPackage0@@AEAAHW4MetadataRecordType@@PEAUMasterMetadataRecord@@AEAK@Z; XEPackage0::HistoryTarget::AddMetadataFrame<MasterMetadataRecord>(MetadataRecordType,MasterMetadataRecord *,ulong &)
0x1005d77f9  test    eax, eax
0x1005d77fb  jz      short loc_1005D785C
0x1005d77fd  mov     eax, [r15+rbx*4+2988h]
0x1005d7805  lea     r9, aEventstream; "eventstream"
0x1005d780c  mov     rdx, [rbp+8]; struct XE_CXFileWriter *
0x1005d7810  xor     r8d, r8d; struct XE_ErrorContext *
0x1005d7813  mov     [rsp+0D8h+var_B0], eax; unsigned int
0x1005d7817  mov     rcx, r15; this
0x1005d781a  mov     [rsp+0D8h+var_B8], edi; unsigned int
0x1005d781e  call    ?OpenWriter@HistoryTarget@XEPackage0@@AEAAHPEAVXE_CXFileWriter@@PEAVXE_ErrorContext@@PEA_WII@Z; XEPackage0::HistoryTarget::OpenWriter(XE_CXFileWriter *,XE_ErrorContext *,wchar_t *,uint,uint)
0x1005d7823  jmp     short loc_1005D7858
0x1005d7825  inc     qword ptr [rbx+2D8h]
0x1005d782c  mov     edx, r12d; int
0x1005d782f  call    ?FlushDirectory@XE_CXFileWriter@@AEAAHH@Z; XE_CXFileWriter::FlushDirectory(int)
0x1005d7834  test    eax, eax
0x1005d7836  jz      short loc_1005D785C
0x1005d7838  mov     eax, [rbx+264h]
0x1005d783e  xor     r8d, r8d; int
0x1005d7841  mov     rcx, rbx; this
0x1005d7844  lea     rdx, [rax+rax*4]
0x1005d7848  shl     rdx, 4
0x1005d784c  add     rdx, [rbx+258h]; struct CXFilePage *
0x1005d7853  call    ?StartIO@XE_CXFileWriter@@AEAAHPEAUCXFilePage@@H@Z; XE_CXFileWriter::StartIO(CXFilePage *,int)
0x1005d7858  test    eax, eax
0x1005d785a  jnz     short loc_1005D785F
0x1005d785c  xor     r12d, r12d
0x1005d785f  mov     rcx, [rbp+18h]
0x1005d7863  call    cs:qword_100714F58
0x1005d7869  mov     eax, r12d
0x1005d786c  mov     dword ptr [rbp+10h], 0
0x1005d7873  mov     rcx, [rsp+0D8h+var_50]
0x1005d787b  xor     rcx, rsp; StackCookie
0x1005d787e  call    __security_check_cookie
0x1005d7883  mov     rbx, [rsp+0D8h+arg_8]
0x1005d788b  movaps  xmm6, [rsp+0D8h+var_48]
0x1005d7893  add     rsp, 0A0h
0x1005d789a  pop     r15
0x1005d789c  pop     r14
0x1005d789e  pop     r13
0x1005d78a0  pop     r12
0x1005d78a2  pop     rdi
0x1005d78a3  pop     rsi
0x1005d78a4  pop     rbp
0x1005d78a5  retn
```
