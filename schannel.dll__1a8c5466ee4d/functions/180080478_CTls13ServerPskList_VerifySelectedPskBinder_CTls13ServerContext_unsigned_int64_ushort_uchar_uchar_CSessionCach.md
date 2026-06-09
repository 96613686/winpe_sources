# CTls13ServerPskList::VerifySelectedPskBinder(CTls13ServerContext *,unsigned __int64,ushort,uchar,uchar,CSessionCacheItem *,uchar *,_eTlsHashAlgorithm *)

- ea: `0x180080478`
- end: `0x180080984`
- name: `?VerifySelectedPskBinder@CTls13ServerPskList@@QEAAKPEAVCTls13ServerContext@@_KGEEPEAVCSessionCacheItem@@PEAEPEAW4_eTlsHashAlgorithm@@@Z`
- size: `1292`
- prototype: `unsigned int(CTls13ServerPskList *__hidden this, struct CTls13ServerContext *, unsigned __int64, unsigned __int16, unsigned __int8, unsigned __int8, struct CSessionCacheItem *, unsigned __int8 *, enum _eTlsHashAlgorithm *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180081d80`

## callees

- `0x18000d780`
- `0x1800214f0`
- `0x180021da8`
- `0x180021e64`
- `0x18004960c`
- `0x18004d0cc`
- `0x180057c8c`
- `0x1800597b0`
- `0x18005a160`
- `0x18005d450`
- `0x180080478`
- `0x180081628`
- `0x180091010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800808bc`
- `ntdll!RtlReleaseResource` at `0x1800808bc`
- `ntdll!RtlAcquireResourceShared` at `0x1800805d6`
- `ntdll!RtlAcquireResourceShared` at `0x1800805d6`
- `ncrypt!SslFreeObject` at `0x18008089a`
- `ncrypt!SslFreeObject` at `0x18008089a`

## pseudocode

```c
__int64 __fastcall CTls13ServerPskList::VerifySelectedPskBinder(
        CTls13ServerPskList *this,
        struct CTls13ServerContext *a2,
        unsigned __int64 a3,
        unsigned __int16 a4,
        unsigned __int8 a5,
        unsigned __int8 a6,
        struct CSessionCacheItem *a7,
        unsigned __int8 *a8,
        enum _eTlsHashAlgorithm *a9)
{
  char v14; // bl
  CTls13PskList *v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rax
  unsigned __int64 v18; // r14
  __int64 v19; // rsi
  __int64 v20; // rcx
  struct hsel *HashInfo; // rax
  CTls13PskList *v22; // rcx
  __int64 v23; // r9
  int v24; // r14d
  unsigned int EarlySecretForEntry; // ebx
  CCipherMill *v26; // rcx
  __int64 v27; // rdx
  unsigned int BinderTranscriptHash; // eax
  unsigned int v29; // r13d
  unsigned int BinderData; // eax
  __int64 v31; // r9
  char v32; // r8
  __int64 v33; // rdx
  unsigned __int8 v34; // cl
  char v35; // al
  __int64 v36; // r9
  __int64 v37; // rax
  __int64 v38; // rcx
  const char *v39; // r9
  unsigned __int64 v40; // [rsp+40h] [rbp-B8h] BYREF
  CTls13ServerPskList *v41; // [rsp+48h] [rbp-B0h]
  struct CSessionCacheItem *v42; // [rsp+50h] [rbp-A8h]
  enum _eTlsHashAlgorithm *v43; // [rsp+58h] [rbp-A0h]
  unsigned __int8 *v44; // [rsp+60h] [rbp-98h]
  unsigned __int8 v45[64]; // [rsp+70h] [rbp-88h] BYREF

  v41 = this;
  v42 = a7;
  v43 = a9;
  v44 = a8;
  if ( !a2 || !a3 || !a8 || !a9 )
    return 87;
  if ( (unsigned __int8)(*((_BYTE *)this + 24) - 3) > 1u )
  {
    if ( !a5 )
      return 0;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_81c4835239bd3f7852303592565886e3_Traceguids);
    return 315;
  }
  v14 = *((_BYTE *)this + 25);
  if ( !v14 || a7 )
  {
    memset_0(v45, 0, sizeof(v45));
    v17 = *((_QWORD *)this + 4);
    v18 = 0;
    v40 = 0;
    v19 = *((_QWORD *)this + 2) + 80 * v17;
    if ( v14 )
    {
      RtlAcquireResourceShared((PRTL_RESOURCE)(*((_QWORD *)v42 + 5) + 80LL), 1u);
      v20 = *(_QWORD *)(*((_QWORD *)v42 + 5) + 184LL);
      if ( !v20 || (HashInfo = GetHashInfo(*(_DWORD *)(v20 + 44))) == 0 || *((_DWORD *)HashInfo + 7) > 0x40u )
      {
        EarlySecretForEntry = 1359;
        goto LABEL_54;
      }
      v24 = *((unsigned __int8 *)HashInfo + 28);
      if ( (unsigned __int8)v24 > 0x40u )
      {
        EarlySecretForEntry = 1359;
LABEL_57:
        v26 = WPP_GLOBAL_Control;
        goto LABEL_58;
      }
      if ( (_WORD)v24 != *(_WORD *)(v19 + 40) )
      {
        EarlySecretForEntry = -2146893048;
        LOBYTE(v23) = 47;
        CSslContext::SetErrorAndFatalAlert(a2, 1210, 2148074248LL, v23);
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v27 = 27;
LABEL_28:
          WPP_SF_dd(
            *((_QWORD *)v26 + 2),
            v27,
            WPP_81c4835239bd3f7852303592565886e3_Traceguids,
            *(unsigned __int16 *)(v19 + 40),
            v24);
          goto LABEL_57;
        }
        goto LABEL_58;
      }
      if ( !*(_QWORD *)(v19 + 64) )
      {
        EarlySecretForEntry = CTls13PskList::GenerateEarlySecretForEntry(
                                v22,
                                a3,
                                a4,
                                a6,
                                v42,
                                (struct CTls13PskList::_PskInfo *)v19);
        if ( EarlySecretForEntry )
          goto LABEL_57;
      }
    }
    else
    {
      if ( !*(_QWORD *)(v19 + 64) )
      {
        EarlySecretForEntry = CTls13PskList::GenerateEarlySecretForEntry(
                                v15,
                                a3,
                                a4,
                                a6,
                                0,
                                (struct CTls13PskList::_PskInfo *)v19);
        if ( EarlySecretForEntry )
          goto LABEL_57;
      }
      v24 = *(unsigned __int8 *)(v19 + 8);
      if ( (_WORD)v24 != *(_WORD *)(v19 + 40) )
      {
        EarlySecretForEntry = -2146893048;
        LOBYTE(v16) = 47;
        CSslContext::SetErrorAndFatalAlert(a2, 1210, 2148074248LL, v16);
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v27 = 28;
          goto LABEL_28;
        }
LABEL_58:
        if ( v42 )
        {
          RtlReleaseResource((PRTL_RESOURCE)(*((_QWORD *)v42 + 5) + 80LL));
          if ( EarlySecretForEntry )
          {
            v37 = *((_QWORD *)a2 + 339);
            if ( v37 )
            {
              *(_BYTE *)(v37 + 76) = 0;
              (*(void (__fastcall **)(struct CTls13ServerContext *))(*(_QWORD *)a2 + 256LL))(a2);
            }
            *((_QWORD *)a2 + 14) = 0;
            if ( EarlySecretForEntry == 315 )
            {
              EarlySecretForEntry = -2146893048;
              LOBYTE(v36) = 50;
              CSslContext::SetErrorAndFatalAlert(a2, 1202, 2148074248LL, v36);
            }
            v26 = WPP_GLOBAL_Control;
            goto LABEL_66;
          }
        }
        else if ( EarlySecretForEntry )
        {
LABEL_66:
          if ( v26 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 1) != 0 )
          {
            v38 = *((_QWORD *)v26 + 2);
            v39 = "resumption";
            if ( !*((_BYTE *)v41 + 25) )
              v39 = "external";
            WPP_SF_s(v38, 33, WPP_81c4835239bd3f7852303592565886e3_Traceguids, v39);
          }
        }
        return EarlySecretForEntry;
      }
    }
    BinderTranscriptHash = CTls13ServerContext::GetBinderTranscriptHash(a2, a3, *(_DWORD *)(v19 + 72), &v40);
    EarlySecretForEntry = BinderTranscriptHash;
    if ( BinderTranscriptHash )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        v18 = v40;
LABEL_55:
        if ( !v18 )
          goto LABEL_58;
        SslFreeObject(v18, 0);
        goto LABEL_57;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_81c4835239bd3f7852303592565886e3_Traceguids,
        BinderTranscriptHash);
      v18 = v40;
    }
    else
    {
      v29 = (unsigned __int8)v24;
      v18 = v40;
      BinderData = CTls13Context::GenerateBinderData(
                     (CTls13Context *)v45,
                     a3,
                     *(_QWORD *)(v19 + 64),
                     v40,
                     *((_BYTE *)v41 + 25) == 0,
                     v45,
                     v29);
      EarlySecretForEntry = BinderData;
      if ( BinderData )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_55;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_81c4835239bd3f7852303592565886e3_Traceguids, BinderData);
      }
      else
      {
        v31 = *(_QWORD *)(v19 + 48);
        v32 = 0;
        v33 = 0;
        if ( !v29 )
          goto LABEL_53;
        do
        {
          v34 = v45[v33];
          v35 = *(_BYTE *)(v33 + v31);
          v33 = (unsigned int)(v33 + 1);
          v32 |= v35 ^ v34;
        }
        while ( (unsigned int)v33 < v29 );
        if ( v32 )
        {
          EarlySecretForEntry = -2146893048;
          LOBYTE(v31) = 47;
          CSslContext::SetErrorAndFatalAlert(a2, 1210, 2148074248LL, v31);
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_55;
          }
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_81c4835239bd3f7852303592565886e3_Traceguids);
        }
        else
        {
LABEL_53:
          *v43 = *(enum _eTlsHashAlgorithm *)(v19 + 4);
          *v44 = *((_BYTE *)v41 + 25);
        }
      }
    }
LABEL_54:
    v26 = WPP_GLOBAL_Control;
    goto LABEL_55;
  }
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_81c4835239bd3f7852303592565886e3_Traceguids);
  return 1359;
}

```

## disassembly

```asm
0x180080478  push    rbx
0x18008047a  push    rsi
0x18008047b  push    rdi
0x18008047c  push    r12
0x18008047e  push    r13
0x180080480  push    r14
0x180080482  push    r15
0x180080484  sub     rsp, 0C0h
0x18008048b  mov     rax, cs:__security_cookie
0x180080492  xor     rax, rsp
0x180080495  mov     [rsp+0F8h+var_48], rax
0x18008049d  mov     rax, [rsp+0F8h+arg_38]
0x1800804a5  mov     r15, rdx
0x1800804a8  mov     rdx, [rsp+0F8h+arg_40]
0x1800804b0  mov     rdi, rcx
0x1800804b3  mov     [rsp+0F8h+var_B0], rcx
0x1800804b8  movzx   r13d, r9w
0x1800804bc  mov     rcx, [rsp+0F8h+arg_30]
0x1800804c4  mov     r12, r8
0x1800804c7  mov     [rsp+0F8h+var_A8], rcx
0x1800804cc  mov     [rsp+0F8h+var_A0], rdx
0x1800804d1  mov     [rsp+0F8h+var_98], rax
0x1800804d6  test    r15, r15
0x1800804d9  jz      loc_18008095C
0x1800804df  test    r8, r8
0x1800804e2  jz      loc_18008095C
0x1800804e8  test    rax, rax
0x1800804eb  jz      loc_18008095C
0x1800804f1  test    rdx, rdx
0x1800804f4  jz      loc_18008095C
0x1800804fa  mov     al, [rdi+18h]
0x1800804fd  sub     al, 3
0x1800804ff  cmp     al, 1
0x180080501  jbe     short loc_18008054C
0x180080503  cmp     [rsp+0F8h+arg_20], 0
0x18008050b  jz      short loc_180080545
0x18008050d  mov     rcx, cs:WPP_GLOBAL_Control
0x180080514  lea     rdi, WPP_GLOBAL_Control
0x18008051b  cmp     rcx, rdi
0x18008051e  jz      short loc_18008053B
0x180080520  test    byte ptr [rcx+1Ch], 1
0x180080524  jz      short loc_18008053B
0x180080526  mov     rcx, [rcx+10h]
0x18008052a  lea     r8, WPP_81c4835239bd3f7852303592565886e3_Traceguids
0x180080531  mov     edx, 19h
0x180080536  call    WPP_SF_
0x18008053b  mov     eax, 13Bh
0x180080540  jmp     loc_180080961
0x180080545  xor     eax, eax
0x180080547  jmp     loc_180080961
0x18008054c  mov     bl, [rdi+19h]
0x18008054f  test    bl, bl
0x180080551  jz      short loc_180080590
0x180080553  test    rcx, rcx
0x180080556  jnz     short loc_180080590
0x180080558  mov     rcx, cs:WPP_GLOBAL_Control
0x18008055f  lea     rdi, WPP_GLOBAL_Control
0x180080566  cmp     rcx, rdi
0x180080569  jz      short loc_180080586
0x18008056b  test    byte ptr [rcx+1Ch], 1
0x18008056f  jz      short loc_180080586
0x180080571  mov     rcx, [rcx+10h]
0x180080575  lea     r8, WPP_81c4835239bd3f7852303592565886e3_Traceguids
0x18008057c  mov     edx, 1Ah
0x180080581  call    WPP_SF_
0x180080586  mov     eax, 54Fh
0x18008058b  jmp     loc_180080961
0x180080590  xor     edx, edx; Val
0x180080592  lea     rcx, [rsp+0F8h+var_88]; void *
0x180080597  lea     r8d, [rdx+40h]; Size
0x18008059b  call    memset_0
0x1800805a0  mov     rax, [rdi+20h]
0x1800805a4  xor     r14d, r14d
0x1800805a7  mov     [rsp+0F8h+var_B8], r14
0x1800805ac  lea     rsi, [rax+rax*4]
0x1800805b0  shl     rsi, 4
0x1800805b4  add     rsi, [rdi+10h]
0x1800805b8  lea     rdi, WPP_GLOBAL_Control
0x1800805bf  test    bl, bl
0x1800805c1  jz      loc_180080710
0x1800805c7  mov     rbx, [rsp+0F8h+var_A8]
0x1800805cc  mov     dl, 1; Wait
0x1800805ce  mov     rcx, [rbx+28h]
0x1800805d2  add     rcx, 50h ; 'P'; Resource
0x1800805d6  call    cs:__imp_RtlAcquireResourceShared
0x1800805dc  mov     rax, [rbx+28h]
0x1800805e0  mov     rcx, [rax+0B8h]
0x1800805e7  test    rcx, rcx
0x1800805ea  jz      loc_180080706
0x1800805f0  mov     ecx, [rcx+2Ch]; unsigned int
0x1800805f3  call    ?GetHashInfo@@YAPEAUhsel@@I@Z; GetHashInfo(uint)
0x1800805f8  test    rax, rax
0x1800805fb  jz      loc_180080706
0x180080601  cmp     dword ptr [rax+1Ch], 40h ; '@'
0x180080605  ja      loc_180080706
0x18008060b  movzx   r14d, byte ptr [rax+1Ch]
0x180080610  cmp     r14b, 40h ; '@'
0x180080614  jbe     short loc_180080620
0x180080616  mov     ebx, 54Fh
0x18008061b  jmp     loc_1800808A0
0x180080620  cmp     r14w, [rsi+28h]
0x180080625  jz      short loc_18008067D
0x180080627  mov     ebx, 80090308h
0x18008062c  mov     r9b, 2Fh ; '/'
0x18008062f  mov     r8d, ebx
0x180080632  mov     edx, 4BAh
0x180080637  mov     rcx, r15
0x18008063a  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18008063f  mov     rcx, cs:WPP_GLOBAL_Control
0x180080646  cmp     rcx, rdi
0x180080649  jz      loc_1800808A7
0x18008064f  test    byte ptr [rcx+1Ch], 1
0x180080653  jz      loc_1800808A7
0x180080659  mov     edx, 1Bh
0x18008065e  movzx   r9d, word ptr [rsi+28h]
0x180080663  lea     r8, WPP_81c4835239bd3f7852303592565886e3_Traceguids
0x18008066a  mov     rcx, [rcx+10h]
0x18008066e  mov     dword ptr [rsp+0F8h+var_D8], r14d
0x180080673  call    WPP_SF_dd
0x180080678  jmp     loc_1800808A0
0x18008067d  cmp     qword ptr [rsi+40h], 0
0x180080682  jnz     short loc_1800806AC
0x180080684  mov     r9b, [rsp+0F8h+arg_28]; unsigned __int8
0x18008068c  movzx   r8d, r13w; unsigned __int16
0x180080690  mov     [rsp+0F8h+var_D0], rsi; struct CTls13PskList::_PskInfo *
0x180080695  mov     rdx, r12; unsigned __int64
0x180080698  mov     [rsp+0F8h+var_D8], rbx; struct CSessionCacheItem *
0x18008069d  call    ?GenerateEarlySecretForEntry@CTls13PskList@@IEAAK_KGEPEAVCSessionCacheItem@@PEAU_PskInfo@1@@Z; CTls13PskList::GenerateEarlySecretForEntry(unsigned __int64,ushort,uchar,CSessionCacheItem *,CTls13PskList::_PskInfo *)
0x1800806a2  mov     ebx, eax
0x1800806a4  test    eax, eax
0x1800806a6  jnz     loc_1800808A0
0x1800806ac  mov     r8d, [rsi+48h]; unsigned int
0x1800806b0  lea     r9, [rsp+0F8h+var_B8]; unsigned __int64 *
0x1800806b5  mov     rdx, r12; unsigned __int64
0x1800806b8  mov     rcx, r15; this
0x1800806bb  call    ?GetBinderTranscriptHash@CTls13ServerContext@@QEAAK_KKPEA_K@Z; CTls13ServerContext::GetBinderTranscriptHash(unsigned __int64,ulong,unsigned __int64 *)
0x1800806c0  mov     ebx, eax
0x1800806c2  test    eax, eax
0x1800806c4  jz      loc_180080794
0x1800806ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800806d1  cmp     rcx, rdi
0x1800806d4  jz      loc_18008078A
0x1800806da  test    byte ptr [rcx+1Ch], 1
0x1800806de  jz      loc_18008078A
0x1800806e4  mov     rcx, [rcx+10h]
0x1800806e8  lea     r8, WPP_81c4835239bd3f7852303592565886e3_Traceguids
0x1800806ef  mov     edx, 1Dh
0x1800806f4  mov     r9d, eax
0x1800806f7  call    WPP_SF_d
0x1800806fc  mov     r14, [rsp+0F8h+var_B8]
0x180080701  jmp     loc_180080889
0x180080706  mov     ebx, 54Fh
0x18008070b  jmp     loc_180080889
0x180080710  cmp     [rsi+40h], r14
0x180080714  jnz     short loc_18008073E
0x180080716  mov     r9b, [rsp+0F8h+arg_28]; unsigned __int8
0x18008071e  movzx   r8d, r13w; unsigned __int16
0x180080722  mov     [rsp+0F8h+var_D0], rsi; struct CTls13PskList::_PskInfo *
0x180080727  mov     rdx, r12; unsigned __int64
0x18008072a  mov     [rsp+0F8h+var_D8], r14; struct CSessionCacheItem *
0x18008072f  call    ?GenerateEarlySecretForEntry@CTls13PskList@@IEAAK_KGEPEAVCSessionCacheItem@@PEAU_PskInfo@1@@Z; CTls13PskList::GenerateEarlySecretForEntry(unsigned __int64,ushort,uchar,CSessionCacheItem *,CTls13PskList::_PskInfo *)
0x180080734  mov     ebx, eax
0x180080736  test    eax, eax
0x180080738  jnz     loc_1800808A0
0x18008073e  movzx   r14d, byte ptr [rsi+8]
0x180080743  cmp     r14w, [rsi+28h]
0x180080748  jz      loc_1800806AC
0x18008074e  mov     ebx, 80090308h
0x180080753  mov     r9b, 2Fh ; '/'
0x180080756  mov     r8d, ebx
0x180080759  mov     edx, 4BAh
0x18008075e  mov     rcx, r15
0x180080761  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x180080766  mov     rcx, cs:WPP_GLOBAL_Control
0x18008076d  cmp     rcx, rdi
0x180080770  jz      loc_1800808A7
0x180080776  test    byte ptr [rcx+1Ch], 1
0x18008077a  jz      loc_1800808A7
0x180080780  mov     edx, 1Ch
0x180080785  jmp     loc_18008065E
0x18008078a  mov     r14, [rsp+0F8h+var_B8]
0x18008078f  jmp     loc_180080890
0x180080794  mov     rax, [rsp+0F8h+var_B0]
0x180080799  lea     rcx, [rsp+0F8h+var_88]; this
0x18008079e  mov     r8, [rsi+40h]; unsigned __int64
0x1800807a2  mov     rdx, r12; unsigned __int64
0x1800807a5  movzx   r13d, r14b
0x1800807a9  mov     r14, [rsp+0F8h+var_B8]
0x1800807ae  cmp     byte ptr [rax+19h], 0
0x1800807b2  mov     r9, r14; unsigned __int64
0x1800807b5  mov     [rsp+0F8h+var_C8], r13d; unsigned int
0x1800807ba  setz    al
0x1800807bd  mov     [rsp+0F8h+var_D0], rcx; unsigned __int8 *
0x1800807c2  mov     byte ptr [rsp+0F8h+var_D8], al; char
0x1800807c6  call    ?GenerateBinderData@CTls13Context@@QEAAK_K00EPEAEK@Z; CTls13Context::GenerateBinderData(unsigned __int64,unsigned __int64,unsigned __int64,uchar,uchar *,ulong)
0x1800807cb  mov     ebx, eax
0x1800807cd  test    eax, eax
0x1800807cf  jz      short loc_180080808
0x1800807d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800807d8  cmp     rcx, rdi
0x1800807db  jz      loc_180080890
0x1800807e1  test    byte ptr [rcx+1Ch], 1
0x1800807e5  jz      loc_180080890
0x1800807eb  mov     rcx, [rcx+10h]
0x1800807ef  lea     r8, WPP_81c4835239bd3f7852303592565886e3_Traceguids
0x1800807f6  mov     edx, 1Eh
0x1800807fb  mov     r9d, eax
0x1800807fe  call    WPP_SF_d
0x180080803  jmp     loc_180080889
0x180080808  mov     r9, [rsi+30h]
0x18008080c  xor     r8b, r8b
0x18008080f  xor     edx, edx
0x180080811  test    r13d, r13d
0x180080814  jz      short loc_180080870
0x180080816  mov     cl, [rsp+rdx+0F8h+var_88]
0x18008081a  mov     al, [rdx+r9]
0x18008081e  inc     edx
0x180080820  xor     cl, al
0x180080822  or      r8b, cl
0x180080825  cmp     edx, r13d
0x180080828  jb      short loc_180080816
0x18008082a  test    r8b, r8b
0x18008082d  jz      short loc_180080870
0x18008082f  mov     ebx, 80090308h
0x180080834  mov     r9b, 2Fh ; '/'
0x180080837  mov     r8d, ebx
0x18008083a  mov     edx, 4BAh
0x18008083f  mov     rcx, r15
0x180080842  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x180080847  mov     rcx, cs:WPP_GLOBAL_Control
0x18008084e  cmp     rcx, rdi
0x180080851  jz      short loc_180080890
0x180080853  test    byte ptr [rcx+1Ch], 1
0x180080857  jz      short loc_180080890
0x180080859  mov     rcx, [rcx+10h]
0x18008085d  lea     r8, WPP_81c4835239bd3f7852303592565886e3_Traceguids
0x180080864  mov     edx, 1Fh
0x180080869  call    WPP_SF_
0x18008086e  jmp     short loc_180080889
0x180080870  mov     eax, [rsi+4]
0x180080873  mov     rcx, [rsp+0F8h+var_A0]
0x180080878  mov     [rcx], eax
0x18008087a  mov     rax, [rsp+0F8h+var_B0]
0x18008087f  mov     rcx, [rsp+0F8h+var_98]
0x180080884  mov     al, [rax+19h]
0x180080887  mov     [rcx], al
0x180080889  mov     rcx, cs:WPP_GLOBAL_Control
0x180080890  test    r14, r14
0x180080893  jz      short loc_1800808A7
0x180080895  xor     edx, edx
0x180080897  mov     rcx, r14
0x18008089a  call    cs:__imp_SslFreeObject
0x1800808a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800808a7  mov     rax, [rsp+0F8h+var_A8]
0x1800808ac  xor     r14d, r14d
0x1800808af  test    rax, rax
0x1800808b2  jz      short loc_180080919
0x1800808b4  mov     rcx, [rax+28h]
0x1800808b8  add     rcx, 50h ; 'P'; Resource
0x1800808bc  call    cs:__imp_RtlReleaseResource
0x1800808c2  test    ebx, ebx
0x1800808c4  jz      loc_180080958
0x1800808ca  mov     rax, [r15+0A98h]
0x1800808d1  test    rax, rax
0x1800808d4  jz      short loc_1800808EC
0x1800808d6  mov     [rax+4Ch], r14b
0x1800808da  mov     rcx, r15
0x1800808dd  mov     rax, [r15]
0x1800808e0  mov     rax, [rax+100h]
0x1800808e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800808ec  mov     [r15+70h], r14
0x1800808f0  cmp     ebx, 13Bh
0x1800808f6  jnz     short loc_180080910
0x1800808f8  mov     ebx, 80090308h
0x1800808fd  mov     r9b, 32h ; '2'
0x180080900  mov     r8d, ebx
0x180080903  mov     edx, 4B2h
0x180080908  mov     rcx, r15
0x18008090b  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x180080910  mov     rcx, cs:WPP_GLOBAL_Control
0x180080917  jmp     short loc_18008091D
0x180080919  test    ebx, ebx
0x18008091b  jz      short loc_180080958
0x18008091d  cmp     rcx, rdi
0x180080920  jz      short loc_180080958
0x180080922  test    byte ptr [rcx+1Ch], 1
0x180080926  jz      short loc_180080958
0x180080928  mov     rax, [rsp+0F8h+var_B0]
0x18008092d  lea     rdx, aExternal; "external"
0x180080934  mov     rcx, [rcx+10h]
0x180080938  lea     r9, aResumption; "resumption"
0x18008093f  lea     r8, WPP_81c4835239bd3f7852303592565886e3_Traceguids
0x180080946  cmp     [rax+19h], r14b
0x18008094a  cmovz   r9, rdx
0x18008094e  mov     edx, 21h ; '!'
0x180080953  call    WPP_SF_s
0x180080958  mov     eax, ebx
0x18008095a  jmp     short loc_180080961
0x18008095c  mov     eax, 57h ; 'W'
0x180080961  mov     rcx, [rsp+0F8h+var_48]
  ... truncated ...
```
