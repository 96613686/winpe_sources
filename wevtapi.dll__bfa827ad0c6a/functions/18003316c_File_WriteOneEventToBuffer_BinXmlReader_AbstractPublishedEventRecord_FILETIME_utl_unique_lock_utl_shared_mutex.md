# File::WriteOneEventToBuffer(BinXmlReader &,AbstractPublishedEventRecord *,_FILETIME,utl::unique_lock<utl::shared_mutex> &)

- ea: `0x18003316c`
- end: `0x1800335ed`
- name: `?WriteOneEventToBuffer@File@@AEAAKAEAVBinXmlReader@@PEAVAbstractPublishedEventRecord@@U_FILETIME@@AEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `1153`
- prototype: `__int64 __usercall@<rax>(File *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x1800335f4`

## callees

- `0x180007180`
- `0x18000a0d0`
- `0x1800223c8`
- `0x180023548`
- `0x1800310d4`
- `0x180032704`
- `0x180032b4c`
- `0x18003316c`
- `0x1800355c8`
- `0x180038fa4`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800334f0`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800334f0`

## pseudocode

```c
__int64 __fastcall File::WriteOneEventToBuffer(
        LPCWSTR *this,
        struct BinXmlReader *a2,
        void (__fastcall ***a3)(_QWORD, LPCWSTR, __int64),
        __int64 a4,
        const char *a5)
{
  __int64 result; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // rcx
  unsigned __int64 v12; // rdx
  char v13; // r8
  __int64 v14; // rsi
  _OWORD *v15; // rbx
  const WCHAR *v16; // rdx
  _OWORD *v17; // rcx
  __int64 v18; // rdx
  _OWORD *v19; // rax
  __int128 v20; // xmm1
  _OWORD *v21; // rax
  LPCWSTR v22; // r14
  void (__fastcall **v23)(_QWORD, LPCWSTR, __int64); // rax
  LPCWSTR v24; // r9
  unsigned int v25; // r15d
  LPCWSTR v26; // rdx
  __int64 v27; // rax
  LPCWSTR v28; // rcx
  WCHAR *v29; // rax
  __int128 v30; // xmm1
  WCHAR *v31; // rax
  unsigned __int64 UnbiasedTime; // [rsp+30h] [rbp-38h] BYREF
  __int128 pExceptionObject; // [rsp+38h] [rbp-30h] BYREF
  __int64 v34; // [rsp+48h] [rbp-20h]
  int v35; // [rsp+50h] [rbp-18h]
  int v36; // [rsp+54h] [rbp-14h]
  int v37; // [rsp+58h] [rbp-10h]

  result = File::EnsureFileIsCreated(this);
  if ( !(_DWORD)result )
  {
    *((_DWORD *)this + 204) = 0;
    if ( *((_BYTE *)this + 829) && *((_BYTE *)this + 830) )
    {
      if ( !*((_BYTE *)this + 828) )
      {
        *((_DWORD *)this + 34) |= 1u;
        v10 = (WCHAR *)MIDL_user_allocate(0x80u);
        if ( v10 )
        {
          *(_OWORD *)v10 = *((_OWORD *)this + 1);
          *((_OWORD *)v10 + 1) = *((_OWORD *)this + 2);
          *((_OWORD *)v10 + 2) = *((_OWORD *)this + 3);
          *((_OWORD *)v10 + 3) = *((_OWORD *)this + 4);
          *((_OWORD *)v10 + 4) = *((_OWORD *)this + 5);
          *((_OWORD *)v10 + 5) = *((_OWORD *)this + 6);
          *((_OWORD *)v10 + 6) = *((_OWORD *)this + 7);
          *((_OWORD *)v10 + 7) = *((_OWORD *)this + 8);
        }
        else
        {
          v10 = 0;
        }
        v11 = (WCHAR *)this[18];
        UnbiasedTime = 0;
        this[18] = v10;
        if ( v11 )
          operator delete(v11);
        utl::unique_ptr<FileHeader,utl::default_delete<FileHeader>>::~unique_ptr<FileHeader,utl::default_delete<FileHeader>>(&UnbiasedTime);
        if ( !this[18] )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 14);
          }
          v34 = 0;
          v35 = 14;
          v36 = -1;
          pExceptionObject = 0;
          v37 = 912;
          throw (EvtException *)&pExceptionObject;
        }
        *((_BYTE *)this + 828) = 1;
      }
      v12 = (unsigned __int64)this[4];
      *(_QWORD *)&pExceptionObject = 10794;
      v34 = a4;
      File::MapInWriteChunk((File *)this, v12, a5);
      if ( !*((_BYTE *)this + 834) || (*((_BYTE *)this + 825) & 3) == 0 || (v13 = 1, *((_BYTE *)this + 835)) )
        v13 = 0;
      v14 = 2;
      v15 = this + 29;
      v16 = (LPCWSTR)((char *)this[22] + *((unsigned int *)this + 48));
      v17 = this + 29;
      if ( v13 )
        v16 -= 1024;
      this[23] = v16;
      v18 = 2;
      *((_BYTE *)this + 836) = 1;
      v19 = this[28];
      do
      {
        *v17 = *v19;
        v17[1] = v19[1];
        v17[2] = v19[2];
        v17[3] = v19[3];
        v17[4] = v19[4];
        v17[5] = v19[5];
        v17[6] = v19[6];
        v20 = v19[7];
        v19 += 8;
        v17[7] = v20;
        v17 += 8;
        --v18;
      }
      while ( v18 );
      v21 = this[63];
      *((_OWORD *)this + 32) = *v21;
      *((_OWORD *)this + 33) = v21[1];
      *((_OWORD *)this + 34) = v21[2];
      *((_OWORD *)this + 35) = v21[3];
      *((_OWORD *)this + 36) = v21[4];
      *((_OWORD *)this + 37) = v21[5];
      *((_OWORD *)this + 38) = v21[6];
      *((_OWORD *)this + 39) = v21[7];
      if ( !*((_BYTE *)this + 827) )
      {
        *((_BYTE *)this + 827) = 1;
        *((_DWORD *)this + 203) = 0;
      }
      v22 = this[5];
      v23 = *a3;
      *((_QWORD *)&pExceptionObject + 1) = v22;
      (*v23)(a3, v22, 128);
      v24 = this[20];
      LODWORD(UnbiasedTime) = 0;
      v25 = WriteFileView::SerializeBlob(
              (WriteFileView *)(this + 19),
              a2,
              (struct ObjectBlobStart *)&pExceptionObject,
              *((_DWORD *)v24 + 12),
              (unsigned int *)&UnbiasedTime);
      if ( v25 )
      {
        v29 = (WCHAR *)this[28];
        do
        {
          *(_OWORD *)v29 = *v15;
          *((_OWORD *)v29 + 1) = v15[1];
          *((_OWORD *)v29 + 2) = v15[2];
          *((_OWORD *)v29 + 3) = v15[3];
          *((_OWORD *)v29 + 4) = v15[4];
          *((_OWORD *)v29 + 5) = v15[5];
          *((_OWORD *)v29 + 6) = v15[6];
          v30 = v15[7];
          v15 += 8;
          *((_OWORD *)v29 + 7) = v30;
          v29 += 64;
          --v14;
        }
        while ( v14 );
        v31 = (WCHAR *)this[63];
        *(_OWORD *)v31 = *((_OWORD *)this + 32);
        *((_OWORD *)v31 + 1) = *((_OWORD *)this + 33);
        *((_OWORD *)v31 + 2) = *((_OWORD *)this + 34);
        *((_OWORD *)v31 + 3) = *((_OWORD *)this + 35);
        *((_OWORD *)v31 + 4) = *((_OWORD *)this + 36);
        *((_OWORD *)v31 + 5) = *((_OWORD *)this + 37);
        *((_OWORD *)v31 + 6) = *((_OWORD *)this + 38);
        *((_OWORD *)v31 + 7) = *((_OWORD *)this + 39);
      }
      else
      {
        v26 = this[20];
        v27 = *((_QWORD *)v26 + 2);
        if ( v27 == -1 )
        {
          *((_QWORD *)v26 + 2) = *((_QWORD *)v26 + 1);
          *((_QWORD *)this[20] + 3) = v22;
        }
        else
        {
          *((_QWORD *)v26 + 2) = v27 + 1;
        }
        *((_DWORD *)this[20] + 11) = *((_DWORD *)this[20] + 12);
        *((_DWORD *)this[20] + 12) += UnbiasedTime;
        *((_QWORD *)this[20] + 4) = v22;
        this[5] = (LPCWSTR)((char *)v22 + 1);
        this[98] = (LPCWSTR)*((_QWORD *)this[20] + 2);
        *((_DWORD *)this + 34) &= ~2u;
        *((_BYTE *)this + 826) = 1;
        File::PossiblyScheduleTimer(this);
        UnbiasedTime = 0;
        QueryUnbiasedInterruptTime(&UnbiasedTime);
        v28 = this[96];
        this[96] = (LPCWSTR)UnbiasedTime;
        if ( v28 == (LPCWSTR)-1LL )
          _InterlockedIncrement(&g_ActiveChannels);
      }
      return v25;
    }
    else
    {
      return 110;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003316c  push    rbp
0x18003316e  push    rbx
0x18003316f  push    rsi
0x180033170  push    rdi
0x180033171  push    r12
0x180033173  push    r13
0x180033175  push    r14
0x180033177  push    r15
0x180033179  mov     rbp, rsp
0x18003317c  sub     rsp, 68h
0x180033180  mov     r13, rdx
0x180033183  mov     rbx, r9
0x180033186  mov     rdx, [rbp+arg_20]
0x18003318a  mov     r12, r8
0x18003318d  mov     rdi, rcx
0x180033190  call    ?EnsureFileIsCreated@File@@AEAAKAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::EnsureFileIsCreated(utl::unique_lock<utl::shared_mutex> &)
0x180033195  xor     r14d, r14d
0x180033198  test    eax, eax
0x18003319a  jnz     loc_1800335DC
0x1800331a0  mov     [rdi+330h], r14d
0x1800331a7  cmp     [rdi+33Dh], r14b
0x1800331ae  jz      loc_1800335D7
0x1800331b4  cmp     [rdi+33Eh], r14b
0x1800331bb  jz      loc_1800335D7
0x1800331c1  mov     esi, 80h
0x1800331c6  cmp     [rdi+33Ch], r14b
0x1800331cd  jnz     loc_1800332D3
0x1800331d3  or      dword ptr [rdi+88h], 1
0x1800331da  mov     ecx, esi; size
0x1800331dc  call    MIDL_user_allocate
0x1800331e1  test    rax, rax
0x1800331e4  jz      short loc_18003322A
0x1800331e6  movups  xmm0, xmmword ptr [rdi+10h]
0x1800331ea  movups  xmmword ptr [rax], xmm0
0x1800331ed  movups  xmm1, xmmword ptr [rdi+20h]
0x1800331f1  movups  xmmword ptr [rax+10h], xmm1
0x1800331f5  movups  xmm0, xmmword ptr [rdi+30h]
0x1800331f9  movups  xmmword ptr [rax+20h], xmm0
0x1800331fd  movups  xmm1, xmmword ptr [rdi+40h]
0x180033201  movups  xmmword ptr [rax+30h], xmm1
0x180033205  movups  xmm0, xmmword ptr [rdi+50h]
0x180033209  movups  xmmword ptr [rax+40h], xmm0
0x18003320d  movups  xmm1, xmmword ptr [rdi+60h]
0x180033211  movups  xmmword ptr [rax+50h], xmm1
0x180033215  movups  xmm0, xmmword ptr [rdi+70h]
0x180033219  movups  xmmword ptr [rax+60h], xmm0
0x18003321d  movups  xmm1, xmmword ptr [rdi+80h]
0x180033224  movups  xmmword ptr [rax+70h], xmm1
0x180033228  jmp     short loc_18003322D
0x18003322a  mov     rax, r14
0x18003322d  mov     rcx, [rdi+90h]; void *
0x180033234  mov     [rbp+UnbiasedTime], r14
0x180033238  mov     [rdi+90h], rax
0x18003323f  test    rcx, rcx
0x180033242  jz      short loc_18003324C
0x180033244  mov     rdx, rsi; unsigned __int64
0x180033247  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003324c  lea     rcx, [rbp+UnbiasedTime]
0x180033250  call    ??1?$unique_ptr@UFileHeader@@U?$default_delete@UFileHeader@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<FileHeader,utl::default_delete<FileHeader>>::~unique_ptr<FileHeader,utl::default_delete<FileHeader>>(void)
0x180033255  cmp     [rdi+90h], r14
0x18003325c  jnz     short loc_1800332CC
0x18003325e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033265  lea     rax, WPP_GLOBAL_Control
0x18003326c  mov     ebx, 0Eh
0x180033271  cmp     rcx, rax
0x180033274  jz      short loc_18003329E
0x180033276  test    dword ptr [rcx+1Ch], 8000h
0x18003327d  jz      short loc_18003329E
0x18003327f  lea     esi, [rbx-0Ch]
0x180033282  cmp     [rcx+19h], sil
0x180033286  jb      short loc_18003329E
0x180033288  mov     rcx, [rcx+10h]
0x18003328c  lea     edx, [rbx+1Eh]
0x18003328f  mov     r9d, ebx
0x180033292  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180033299  call    WPP_SF_D
0x18003329e  xorps   xmm0, xmm0
0x1800332a1  mov     [rbp+var_20], r14
0x1800332a5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800332ac  mov     [rbp+var_18], ebx
0x1800332af  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800332b3  mov     [rbp+var_14], 0FFFFFFFFh
0x1800332ba  movdqu  [rbp+pExceptionObject], xmm0
0x1800332bf  mov     [rbp+var_10], 390h
0x1800332c6  call    _CxxThrowException_0
0x1800332cc  mov     byte ptr [rdi+33Ch], 1
0x1800332d3  mov     r8, [rbp+arg_20]
0x1800332d7  mov     rcx, rdi; this
0x1800332da  mov     rdx, [rdi+20h]; unsigned __int64
0x1800332de  mov     qword ptr [rbp+pExceptionObject], 2A2Ah
0x1800332e6  mov     [rbp+var_20], rbx
0x1800332ea  call    ?MapInWriteChunk@File@@AEAAX_KAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::MapInWriteChunk(unsigned __int64,utl::unique_lock<utl::shared_mutex> &)
0x1800332ef  cmp     [rdi+342h], r14b
0x1800332f6  jz      short loc_18003330D
0x1800332f8  test    byte ptr [rdi+339h], 3
0x1800332ff  jz      short loc_18003330D
0x180033301  mov     r8b, 1
0x180033304  cmp     [rdi+343h], r14b
0x18003330b  jz      short loc_180033310
0x18003330d  mov     r8b, r14b
0x180033310  lea     r15, [rdi+98h]
0x180033317  mov     esi, 2
0x18003331c  mov     edx, [r15+28h]
0x180033320  lea     rbx, [rdi+0E8h]
0x180033327  add     rdx, [r15+18h]
0x18003332b  mov     rcx, rbx
0x18003332e  test    r8b, r8b
0x180033331  lea     r8d, [rsi+7Eh]
0x180033335  lea     rax, [rdx-800h]
0x18003333c  cmovnz  rdx, rax
0x180033340  mov     [r15+20h], rdx
0x180033344  mov     edx, esi
0x180033346  mov     byte ptr [rdi+344h], 1
0x18003334d  mov     rax, [rdi+0E0h]
0x180033354  movups  xmm0, xmmword ptr [rax]
0x180033357  movups  xmmword ptr [rcx], xmm0
0x18003335a  movups  xmm1, xmmword ptr [rax+10h]
0x18003335e  movups  xmmword ptr [rcx+10h], xmm1
0x180033362  movups  xmm0, xmmword ptr [rax+20h]
0x180033366  movups  xmmword ptr [rcx+20h], xmm0
0x18003336a  movups  xmm1, xmmword ptr [rax+30h]
0x18003336e  movups  xmmword ptr [rcx+30h], xmm1
0x180033372  movups  xmm0, xmmword ptr [rax+40h]
0x180033376  movups  xmmword ptr [rcx+40h], xmm0
0x18003337a  movups  xmm1, xmmword ptr [rax+50h]
0x18003337e  movups  xmmword ptr [rcx+50h], xmm1
0x180033382  movups  xmm0, xmmword ptr [rax+60h]
0x180033386  movups  xmmword ptr [rcx+60h], xmm0
0x18003338a  movups  xmm1, xmmword ptr [rax+70h]
0x18003338e  add     rax, r8
0x180033391  movups  xmmword ptr [rcx+70h], xmm1
0x180033395  add     rcx, r8
0x180033398  sub     rdx, 1
0x18003339c  jnz     short loc_180033354
0x18003339e  mov     rax, [rdi+1F8h]
0x1800333a5  movups  xmm0, xmmword ptr [rax]
0x1800333a8  movups  xmmword ptr [rdi+200h], xmm0
0x1800333af  movups  xmm1, xmmword ptr [rax+10h]
0x1800333b3  movups  xmmword ptr [rdi+210h], xmm1
0x1800333ba  movups  xmm0, xmmword ptr [rax+20h]
0x1800333be  movups  xmmword ptr [rdi+220h], xmm0
0x1800333c5  movups  xmm1, xmmword ptr [rax+30h]
0x1800333c9  movups  xmmword ptr [rdi+230h], xmm1
0x1800333d0  movups  xmm0, xmmword ptr [rax+40h]
0x1800333d4  movups  xmmword ptr [rdi+240h], xmm0
0x1800333db  movups  xmm1, xmmword ptr [rax+50h]
0x1800333df  movups  xmmword ptr [rdi+250h], xmm1
0x1800333e6  movups  xmm0, xmmword ptr [rax+60h]
0x1800333ea  movups  xmmword ptr [rdi+260h], xmm0
0x1800333f1  movups  xmm1, xmmword ptr [rax+70h]
0x1800333f5  movups  xmmword ptr [rdi+270h], xmm1
0x1800333fc  cmp     [rdi+33Bh], r14b
0x180033403  jnz     short loc_180033413
0x180033405  mov     byte ptr [rdi+33Bh], 1
0x18003340c  mov     [rdi+32Ch], r14d
0x180033413  mov     r14, [rdi+28h]
0x180033417  mov     rcx, r12
0x18003341a  mov     rax, [r12]
0x18003341e  mov     rdx, r14
0x180033421  mov     qword ptr [rbp+pExceptionObject+8], r14
0x180033425  mov     rax, [rax]
0x180033428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003342d  mov     r9, [rdi+0A0h]
0x180033434  lea     rax, [rbp+UnbiasedTime]
0x180033438  lea     r8, [rbp+pExceptionObject]; struct ObjectBlobStart *
0x18003343c  mov     dword ptr [rbp+UnbiasedTime], 0
0x180033443  mov     rdx, r13; struct BinXmlReader *
0x180033446  mov     [rsp+68h+var_48], rax; unsigned int *
0x18003344b  mov     rcx, r15; this
0x18003344e  mov     r9d, [r9+30h]; unsigned int
0x180033452  call    ?SerializeBlob@WriteFileView@@QEAAKAEAVBinXmlReader@@PEAUObjectBlobStart@@KAEAK@Z; WriteFileView::SerializeBlob(BinXmlReader &,ObjectBlobStart *,ulong,ulong &)
0x180033457  mov     r15d, eax
0x18003345a  test    eax, eax
0x18003345c  jnz     loc_18003351E
0x180033462  mov     rdx, [rdi+0A0h]
0x180033469  mov     rax, [rdx+10h]
0x18003346d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033471  jnz     short loc_180033488
0x180033473  mov     rcx, [rdx+8]
0x180033477  mov     [rdx+10h], rcx
0x18003347b  mov     rcx, [rdi+0A0h]
0x180033482  mov     [rcx+18h], r14
0x180033486  jmp     short loc_18003348F
0x180033488  inc     rax
0x18003348b  mov     [rdx+10h], rax
0x18003348f  mov     rcx, [rdi+0A0h]
0x180033496  mov     eax, [rcx+30h]
0x180033499  mov     [rcx+2Ch], eax
0x18003349c  mov     rcx, [rdi+0A0h]
0x1800334a3  mov     eax, dword ptr [rbp+UnbiasedTime]
0x1800334a6  add     [rcx+30h], eax
0x1800334a9  mov     rax, [rdi+0A0h]
0x1800334b0  mov     [rax+20h], r14
0x1800334b4  lea     rax, [r14+1]
0x1800334b8  mov     [rdi+28h], rax
0x1800334bc  mov     rax, [rdi+0A0h]
0x1800334c3  mov     rcx, [rax+10h]
0x1800334c7  mov     [rdi+310h], rcx
0x1800334ce  mov     rcx, rdi; pv
0x1800334d1  and     dword ptr [rdi+88h], 0FFFFFFFDh
0x1800334d8  mov     byte ptr [rdi+33Ah], 1
0x1800334df  call    ?PossiblyScheduleTimer@File@@AEAAXXZ; File::PossiblyScheduleTimer(void)
0x1800334e4  lea     rcx, [rbp+UnbiasedTime]; UnbiasedTime
0x1800334e8  mov     [rbp+UnbiasedTime], 0
0x1800334f0  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800334f6  mov     rcx, [rdi+300h]
0x1800334fd  mov     rax, [rbp+UnbiasedTime]
0x180033501  mov     [rdi+300h], rax
0x180033508  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003350c  jnz     loc_1800335D2
0x180033512  lock inc cs:?g_ActiveChannels@@3JA; long g_ActiveChannels
0x180033519  jmp     loc_1800335D2
0x18003351e  mov     rax, [rdi+0E0h]
0x180033525  mov     ecx, 80h
0x18003352a  movups  xmm0, xmmword ptr [rbx]
0x18003352d  movups  xmmword ptr [rax], xmm0
0x180033530  movups  xmm1, xmmword ptr [rbx+10h]
0x180033534  movups  xmmword ptr [rax+10h], xmm1
0x180033538  movups  xmm0, xmmword ptr [rbx+20h]
0x18003353c  movups  xmmword ptr [rax+20h], xmm0
0x180033540  movups  xmm1, xmmword ptr [rbx+30h]
0x180033544  movups  xmmword ptr [rax+30h], xmm1
0x180033548  movups  xmm0, xmmword ptr [rbx+40h]
0x18003354c  movups  xmmword ptr [rax+40h], xmm0
0x180033550  movups  xmm1, xmmword ptr [rbx+50h]
0x180033554  movups  xmmword ptr [rax+50h], xmm1
0x180033558  movups  xmm0, xmmword ptr [rbx+60h]
0x18003355c  movups  xmmword ptr [rax+60h], xmm0
0x180033560  movups  xmm1, xmmword ptr [rbx+70h]
0x180033564  add     rbx, rcx
0x180033567  movups  xmmword ptr [rax+70h], xmm1
0x18003356b  add     rax, rcx
0x18003356e  sub     rsi, 1
0x180033572  jnz     short loc_18003352A
0x180033574  movups  xmm0, xmmword ptr [rdi+200h]
0x18003357b  mov     rax, [rdi+1F8h]
0x180033582  movups  xmmword ptr [rax], xmm0
0x180033585  movups  xmm1, xmmword ptr [rdi+210h]
0x18003358c  movups  xmmword ptr [rax+10h], xmm1
0x180033590  movups  xmm0, xmmword ptr [rdi+220h]
0x180033597  movups  xmmword ptr [rax+20h], xmm0
0x18003359b  movups  xmm1, xmmword ptr [rdi+230h]
0x1800335a2  movups  xmmword ptr [rax+30h], xmm1
0x1800335a6  movups  xmm0, xmmword ptr [rdi+240h]
0x1800335ad  movups  xmmword ptr [rax+40h], xmm0
0x1800335b1  movups  xmm1, xmmword ptr [rdi+250h]
0x1800335b8  movups  xmmword ptr [rax+50h], xmm1
0x1800335bc  movups  xmm0, xmmword ptr [rdi+260h]
0x1800335c3  movups  xmmword ptr [rax+60h], xmm0
0x1800335c7  movups  xmm1, xmmword ptr [rdi+270h]
0x1800335ce  movups  xmmword ptr [rax+70h], xmm1
0x1800335d2  mov     eax, r15d
0x1800335d5  jmp     short loc_1800335DC
0x1800335d7  mov     eax, 6Eh ; 'n'
0x1800335dc  add     rsp, 68h
0x1800335e0  pop     r15
0x1800335e2  pop     r14
0x1800335e4  pop     r13
0x1800335e6  pop     r12
0x1800335e8  pop     rdi
0x1800335e9  pop     rsi
0x1800335ea  pop     rbx
0x1800335eb  pop     rbp
0x1800335ec  retn
```
