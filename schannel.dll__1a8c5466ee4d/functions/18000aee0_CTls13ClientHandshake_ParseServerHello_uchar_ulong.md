# CTls13ClientHandshake::ParseServerHello(uchar *,ulong)

- ea: `0x18000aee0`
- end: `0x18000b60e`
- name: `?ParseServerHello@CTls13ClientHandshake@@QEAAKPEAEK@Z`
- size: `1838`
- prototype: `unsigned int __fastcall(CTls13ClientHandshake *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050f90`

## callees

- `0x18000a580`
- `0x18000ad90`
- `0x18000aee0`
- `0x18000c610`
- `0x18000d080`
- `0x18000d780`
- `0x18001e7e0`
- `0x1800214f0`
- `0x180025460`
- `0x1800554b4`
- `0x180057c8c`
- `0x18007d658`
- `0x18007e8b4`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000afaf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000b019`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000afaf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000b019`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000b19c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000b1b1`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000b19c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000b1b1`
- `ntdll!RtlReleaseResource` at `0x18000b1da`
- `ntdll!RtlReleaseResource` at `0x18000b223`
- `ntdll!RtlReleaseResource` at `0x18000b3cc`
- `ntdll!RtlReleaseResource` at `0x18000b462`
- `ntdll!RtlReleaseResource` at `0x18000b1da`
- `ntdll!RtlReleaseResource` at `0x18000b223`
- `ntdll!RtlReleaseResource` at `0x18000b3cc`
- `ntdll!RtlReleaseResource` at `0x18000b462`
- `ntdll!RtlAcquireResourceShared` at `0x18000b399`
- `ntdll!RtlAcquireResourceShared` at `0x18000b399`

## pseudocode

```c
unsigned int __fastcall CTls13ClientHandshake::ParseServerHello(
        CTls13ClientHandshake *this,
        unsigned __int8 *a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned int v8; // esi
  unsigned int v9; // r8d
  int v10; // eax
  unsigned int v11; // r14d
  bool v12; // zf
  __int64 v13; // r9
  __int64 v14; // rax
  char v15; // r15
  unsigned int v16; // r14d
  __int64 v17; // rbp
  _BYTE *v18; // rcx
  unsigned __int8 *v19; // r12
  char v20; // di
  unsigned int v21; // r14d
  unsigned int v22; // r14d
  unsigned __int8 v23; // r11
  unsigned __int8 *v24; // rdx
  unsigned __int8 v25; // r12
  unsigned int v26; // r14d
  int v27; // r13d
  unsigned int v28; // eax
  unsigned int v29; // ebp
  char v30; // r8
  __int64 v31; // r10
  unsigned int v32; // eax
  __int64 v33; // r9
  __int64 v34; // r10
  unsigned int v35; // edi
  CSessionCacheManager *v36; // r11
  unsigned int v37; // eax
  const unsigned __int16 *v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rdx
  CSessionCacheManager *v41; // r11
  unsigned int v42; // eax
  const unsigned __int16 *v43; // rdx
  __int64 v44; // rcx
  unsigned int result; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  __int64 v48; // r9
  __int64 v49; // r10
  __int64 v50; // rdx
  unsigned int v51; // eax
  unsigned __int16 v52; // ax
  __int64 v53; // r10
  __int64 v54; // rdx
  __int64 v55; // rdi
  __int64 v56; // rax
  __int64 v57; // rcx
  struct _RTL_RESOURCE *v58; // rdx
  struct hsel *HashInfo; // rax
  int v60; // edi
  __int64 v61; // rcx
  struct hsel *v62; // rax
  __int64 v63; // r9
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rax
  int v68; // eax
  __int64 v69; // [rsp+68h] [rbp+10h] BYREF
  int v70; // [rsp+78h] [rbp+20h]

  if ( !a2 || !a3 )
    return 87;
  v6 = *((_QWORD *)this + 1);
  *(_WORD *)(v6 + 3542) = 0;
  *(_QWORD *)(v6 + 3544) = 0;
  *(_WORD *)(v6 + 3552) = 0;
  v7 = *((_QWORD *)this + 1);
  if ( a3 < 2 )
    goto LABEL_81;
  v8 = a2[1] | (*a2 << 8);
  if ( v8 < 0x300 )
    goto LABEL_92;
  if ( !*(_BYTE *)(v7 + 1953) )
  {
    if ( v8 <= 0x303 )
      goto LABEL_7;
LABEL_92:
    LOBYTE(a4) = 70;
    goto LABEL_82;
  }
  if ( v8 < 0xFEFD )
    goto LABEL_92;
LABEL_7:
  v9 = a3 - 2;
  if ( v9 < 0x20 )
  {
LABEL_81:
    LOBYTE(a4) = 50;
LABEL_82:
    CSslContext::SetErrorAndFatalAlert(v7, 100, 2148074248LL, a4);
    return -2146893048;
  }
  v10 = *(_DWORD *)(v7 + 92);
  v11 = v9 - 32;
  *(_OWORD *)(v7 + 2024) = *(_OWORD *)(a2 + 2);
  v70 = v10;
  *(_OWORD *)(v7 + 2040) = *(_OWORD *)(a2 + 18);
  v12 = RtlCompareMemory((const void *)(*((_QWORD *)this + 1) + 2024LL), qword_180098058, 0x20u) == 32;
  v14 = *((_QWORD *)this + 1);
  if ( v12 )
  {
    *(_DWORD *)(v14 + 92) = 100;
    CTls13Handshake<CTls13ClientContext,CTls13ExtClient>::ClearKeyShares(this);
    v15 = 1;
  }
  else
  {
    *(_DWORD *)(v14 + 92) = 70;
    v15 = 0;
  }
  if ( !v11
    || (v16 = v11 - 1, v17 = a2[34], v16 < (unsigned int)v17)
    || (unsigned __int8)v17 > 0x20u
    || ((v18 = (_BYTE *)*((_QWORD *)this + 1), v19 = a2 + 35, (_BYTE)v17 != v18[3369])
     || RtlCompareMemory(v18 + 3337, a2 + 35, a2[34]) != v17
      ? (v20 = 0)
      : (v20 = 1),
        (v21 = v16 - v17, v21 < 2) || (v22 = v21 - 2) == 0) )
  {
    LOBYTE(v13) = 50;
    CSslContext::SetErrorAndFatalAlert(*((_QWORD *)this + 1), 100, 2148074248LL, v13);
    return -2146893048;
  }
  v23 = v19[v17 + 1];
  v24 = &v19[v17];
  v25 = v19[v17 + 2];
  v26 = v22 - 1;
  v27 = *v24;
  LOBYTE(v69) = v23;
  if ( v26 < 2 )
  {
    v30 = 0;
LABEL_23:
    if ( !*(_BYTE *)(*((_QWORD *)this + 2) + 35LL) )
    {
      if ( !*(_QWORD *)(*((_QWORD *)this + 1) + 104LL) )
        return -2146893052;
      v47 = ConvertSslVersionToSchannelProtocol(v8);
      v51 = *(_DWORD *)(v50 + 216) & v47 & 0xA2AA0;
      if ( !v51 )
      {
        LOBYTE(v48) = 70;
        CSslContext::SetErrorAndFatalAlert(v49, 105, 2148074289LL, v48);
        return -2146893007;
      }
      *(_DWORD *)(v49 + 88) = v51;
      v52 = ConvertSchannelProtocolToSsl(v51);
      *(_WORD *)(v53 + 34) = v52;
    }
    v31 = *((_QWORD *)this + 1);
    if ( *(_DWORD *)(v31 + 88) != 0x2000 )
    {
      if ( v70 != 71 )
        return 0;
      LOBYTE(v13) = 70;
      CSslContext::SetErrorAndFatalAlert(v31, 11, 2148074289LL, v13);
      return -2146893007;
    }
    if ( v30 )
    {
      if ( v25 )
      {
        LOBYTE(v13) = 30;
        v54 = 104;
        goto LABEL_59;
      }
      if ( !v20 )
      {
        v54 = 103;
        goto LABEL_58;
      }
      v13 = v23 | (unsigned int)(v27 << 8);
      if ( v70 == 71 )
      {
        if ( v15 )
        {
          LOBYTE(v13) = 10;
          v54 = 109;
          goto LABEL_59;
        }
        if ( (*(_BYTE *)(v31 + 32) & 1) != 0 && (v67 = *(_QWORD *)(v31 + 8)) != 0 )
          v68 = *(_DWORD *)(v67 + 28);
        else
          v68 = 0;
        if ( v68 != (_DWORD)v13 )
          goto LABEL_57;
      }
      else
      {
        if ( v15
          && (unsigned __int8)CTls13Handshake<CTls13ClientContext,CTls13ExtClient>::IsGroupOfferedByClient(
                                this,
                                *(unsigned __int16 *)(v31 + 3540)) )
        {
LABEL_57:
          v54 = 100;
LABEL_58:
          LOBYTE(v13) = 47;
LABEL_59:
          CSslContext::SetErrorAndFatalAlert(v31, v54, 2148074278LL, v13);
          return -2146893018;
        }
        v32 = CCipherMill::SetServerHelloCipher((CCipherMill *)v18, (struct CSsl3TlsClientContext *)v31, v13);
        v34 = *((_QWORD *)this + 1);
        v35 = v32;
        if ( v32 )
        {
          LOBYTE(v33) = 40;
          v64 = v32;
          v65 = 107;
          v66 = *((_QWORD *)this + 1);
          goto LABEL_77;
        }
        if ( (*(_DWORD *)(v34 + 1856) & 0x8000LL) == 0 )
        {
          v55 = *(_QWORD *)(v34 + 112);
          if ( !v55 )
            return -2146893052;
          RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(v55 + 40) + 80LL), 1u);
          v56 = *(_QWORD *)(v55 + 40);
          v57 = *(_QWORD *)(v56 + 184);
          v58 = (struct _RTL_RESOURCE *)(v56 + 80);
          if ( !v57 || (HashInfo = GetHashInfo(*(_DWORD *)(v57 + 44))) == 0 )
          {
            RtlReleaseResource(v58);
            return 1359;
          }
          v60 = *((_DWORD *)HashInfo + 8);
          RtlReleaseResource(v58);
          if ( !v60 )
            return -2146893052;
          v61 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
          if ( !v61 )
            return -2146893052;
          v62 = GetHashInfo(*(_DWORD *)(v61 + 44));
          if ( !v62 )
            return -2146893052;
          if ( v60 != *((_DWORD *)v62 + 8) )
          {
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_ca7b144d2da03908b1ea89985908c21d_Traceguids);
            }
            LOBYTE(v63) = 47;
            CSslContext::SetErrorAndFatalAlert(*((_QWORD *)this + 1), 100, 2148074278LL, v63);
            return -2146893018;
          }
        }
        v69 = 0;
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 240LL))(v34, &v69);
        v36 = CSessionCacheManager::m_pSessionCacheManager;
        if ( CSessionCacheManager::m_pSessionCacheManager )
        {
          v37 = 0;
          v38 = *(const unsigned __int16 **)(*(_QWORD *)(v69 + 160) + 264LL);
          if ( v38 )
            v37 = CSessionCacheManager::ComputeClientCacheIndex(CSessionCacheManager::m_pSessionCacheManager, v38);
          v39 = *((_QWORD *)v36 + 4) + 152LL * (v37 / *((_DWORD *)v36 + 11));
          if ( v39 )
            RtlAcquireResourceExclusive((PRTL_RESOURCE)(v39 + 48), 1u);
        }
        RtlAcquireResourceExclusive((PRTL_RESOURCE)(*(_QWORD *)(v69 + 40) + 80LL), 1u);
        *(_DWORD *)(*(_QWORD *)(v69 + 40) + 176LL) = *(_DWORD *)(*((_QWORD *)this + 1) + 88LL);
        RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(v69 + 40) + 80LL));
        v41 = CSessionCacheManager::m_pSessionCacheManager;
        if ( CSessionCacheManager::m_pSessionCacheManager )
        {
          v42 = 0;
          v43 = *(const unsigned __int16 **)(*(_QWORD *)(v69 + 160) + 264LL);
          if ( v43 )
            v42 = CSessionCacheManager::ComputeClientCacheIndex(CSessionCacheManager::m_pSessionCacheManager, v43);
          v40 = v42 % *((_DWORD *)v41 + 11);
          v44 = *((_QWORD *)v41 + 4) + 152LL * (v42 / *((_DWORD *)v41 + 11));
          if ( v44 )
            RtlReleaseResource((PRTL_RESOURCE)(v44 + 48));
        }
        *(_BYTE *)(*((_QWORD *)this + 1) + 2060LL) = 0;
        if ( v15 )
        {
          result = CTls13ClientContext::HashClientHello1(*((CTls13ClientContext **)this + 1));
          if ( result )
            return result;
        }
        LOBYTE(v40) = 1;
        result = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 560LL))(
                   *((_QWORD *)this + 1),
                   v40);
        v35 = result;
        if ( result )
          return result;
        if ( v15 )
          return v35;
      }
      v46 = CTls13ClientContext::SetServerKeyShare(*((CTls13ClientContext **)this + 1));
      v35 = v46;
      if ( !v46 )
        return v35;
      v66 = *((_QWORD *)this + 1);
      LOBYTE(v33) = 50;
      v64 = v46;
      v65 = 106;
LABEL_77:
      CSslContext::SetErrorAndFatalAlert(v66, v65, v64, v33);
      return v35;
    }
LABEL_65:
    LOBYTE(v13) = 50;
    CSslContext::SetErrorAndFatalAlert(*((_QWORD *)this + 1), 106, 2148074248LL, v13);
    return -2146893048;
  }
  if ( v26 - 2 != (v24[4] | (v24[3] << 8)) )
    goto LABEL_65;
  LOBYTE(v13) = 2;
  v28 = CTlsExt::ParseTlsExtensions(*((__int64 **)this + 2), (unsigned __int16 *)(v24 + 5), v26 - 2, v13);
  v29 = v28;
  if ( !v28 )
  {
    v23 = v69;
    v30 = 1;
    goto LABEL_23;
  }
  if ( v28 != -2146893007 )
  {
    LOBYTE(v13) = 50;
    CSslContext::SetErrorAndFatalAlert(*((_QWORD *)this + 1), 106, v28, v13);
  }
  return v29;
}

```

## disassembly

```asm
0x18000aee0  push    rbx
0x18000aee2  push    rdi
0x18000aee3  sub     rsp, 48h
0x18000aee7  mov     rdi, rdx
0x18000aeea  mov     rbx, rcx
0x18000aeed  test    rdx, rdx
0x18000aef0  jz      loc_18000B376
0x18000aef6  test    r8d, r8d
0x18000aef9  jz      loc_18000B376
0x18000aeff  mov     rcx, [rcx+8]
0x18000af03  xor     eax, eax
0x18000af05  mov     [rsp+58h+var_18], rsi
0x18000af0a  mov     [rcx+0DD6h], ax
0x18000af11  mov     [rcx+0DD8h], rax
0x18000af18  mov     [rcx+0DE0h], ax
0x18000af1f  mov     rcx, [rbx+8]
0x18000af23  cmp     r8d, 2
0x18000af27  jb      loc_18000B503
0x18000af2d  movzx   esi, byte ptr [rdx]
0x18000af30  movzx   eax, byte ptr [rdx+1]
0x18000af34  shl     esi, 8
0x18000af37  or      esi, eax
0x18000af39  cmp     esi, 300h
0x18000af3f  jb      loc_18000B56F
0x18000af45  cmp     byte ptr [rcx+7A1h], 0
0x18000af4c  jnz     loc_18000B563
0x18000af52  cmp     esi, 303h
0x18000af58  ja      loc_18000B56F
0x18000af5e  add     r8d, 0FFFFFFFEh
0x18000af62  cmp     r8d, 20h ; ' '
0x18000af66  jb      loc_18000B503
0x18000af6c  mov     eax, [rcx+5Ch]
0x18000af6f  movups  xmm0, xmmword ptr [rdx+2]
0x18000af73  mov     [rsp+58h+var_30], r14
0x18000af78  lea     r14d, [r8-20h]
0x18000af7c  mov     r8d, 20h ; ' '; Length
0x18000af82  mov     [rsp+58h+var_38], r15
0x18000af87  movups  xmmword ptr [rcx+7E8h], xmm0
0x18000af8e  mov     [rsp+58h+arg_18], eax
0x18000af92  movups  xmm1, xmmword ptr [rdx+12h]
0x18000af96  lea     rdx, qword_180098058; Source2
0x18000af9d  movups  xmmword ptr [rcx+7F8h], xmm1
0x18000afa4  mov     rcx, [rbx+8]
0x18000afa8  add     rcx, 7E8h; Source1
0x18000afaf  call    cs:__imp_RtlCompareMemory
0x18000afb5  cmp     rax, 20h ; ' '
0x18000afb9  mov     rax, [rbx+8]
0x18000afbd  jz      loc_18000B297
0x18000afc3  mov     dword ptr [rax+5Ch], 46h ; 'F'
0x18000afca  xor     r15b, r15b
0x18000afcd  cmp     r14d, 1
0x18000afd1  jb      loc_18000B43B
0x18000afd7  mov     [rsp+58h+arg_0], rbp
0x18000afdc  dec     r14d
0x18000afdf  movzx   ebp, byte ptr [rdi+22h]
0x18000afe3  cmp     r14d, ebp
0x18000afe6  jb      loc_18000B2FB
0x18000afec  cmp     bpl, 20h ; ' '
0x18000aff0  ja      loc_18000B2FB
0x18000aff6  mov     rcx, [rbx+8]
0x18000affa  mov     [rsp+58h+var_20], r12
0x18000afff  lea     r12, [rdi+23h]
0x18000b003  cmp     bpl, [rcx+0D29h]
0x18000b00a  jnz     short loc_18000B029
0x18000b00c  add     rcx, 0D09h; Source1
0x18000b013  mov     r8d, ebp; Length
0x18000b016  mov     rdx, r12; Source2
0x18000b019  call    cs:__imp_RtlCompareMemory
0x18000b01f  cmp     rax, rbp
0x18000b022  jnz     short loc_18000B029
0x18000b024  mov     dil, 1
0x18000b027  jmp     short loc_18000B02C
0x18000b029  xor     dil, dil
0x18000b02c  sub     r14d, ebp
0x18000b02f  cmp     r14d, 2
0x18000b033  jb      loc_18000B3FA
0x18000b039  add     r14d, 0FFFFFFFEh
0x18000b03d  cmp     r14d, 1
0x18000b041  jb      loc_18000B3FA
0x18000b047  movzx   r11d, byte ptr [r12+rbp+1]
0x18000b04d  lea     rdx, [r12+rbp]
0x18000b051  movzx   r12d, byte ptr [r12+rbp+2]
0x18000b057  dec     r14d
0x18000b05a  mov     [rsp+58h+var_28], r13
0x18000b05f  movzx   r13d, byte ptr [rdx]
0x18000b063  mov     byte ptr [rsp+58h+arg_8], r11b
0x18000b068  cmp     r14d, 2
0x18000b06c  jb      loc_18000B31C
0x18000b072  movzx   ecx, byte ptr [rdx+3]
0x18000b076  lea     r8d, [r14-2]
0x18000b07a  movzx   eax, byte ptr [rdx+4]
0x18000b07e  shl     ecx, 8
0x18000b081  or      ecx, eax
0x18000b083  cmp     r8d, ecx
0x18000b086  jnz     loc_18000B3D9
0x18000b08c  mov     rcx, [rbx+10h]
0x18000b090  add     rdx, 5
0x18000b094  mov     r9b, 2
0x18000b097  call    ?ParseTlsExtensions@CTlsExt@@QEAAKPEAEKW4eTlsHandshakeType@@@Z; CTlsExt::ParseTlsExtensions(uchar *,ulong,eTlsHandshakeType)
0x18000b09c  mov     ebp, eax
0x18000b09e  test    eax, eax
0x18000b0a0  jnz     loc_18000B574
0x18000b0a6  movzx   r11d, byte ptr [rsp+58h+arg_8]
0x18000b0ac  mov     r8b, 1
0x18000b0af  mov     rax, [rbx+10h]
0x18000b0b3  cmp     byte ptr [rax+23h], 0
0x18000b0b7  jz      loc_18000B2BD
0x18000b0bd  mov     r10, [rbx+8]
0x18000b0c1  cmp     dword ptr [r10+58h], 2000h
0x18000b0c9  jnz     loc_18000B2AE
0x18000b0cf  test    r8b, r8b
0x18000b0d2  jz      loc_18000B5BA
0x18000b0d8  test    r12b, r12b
0x18000b0db  jnz     loc_18000B527
0x18000b0e1  test    dil, dil
0x18000b0e4  jz      loc_18000B5DA
0x18000b0ea  mov     r9d, r13d
0x18000b0ed  movzx   eax, r11b
0x18000b0f1  shl     r9d, 8
0x18000b0f5  or      r9d, eax
0x18000b0f8  cmp     [rsp+58h+arg_18], 47h ; 'G'
0x18000b0fd  jz      loc_18000B5E4
0x18000b103  test    r15b, r15b
0x18000b106  jnz     loc_18000B33E
0x18000b10c  mov     r8d, r9d; unsigned int
0x18000b10f  mov     rdx, r10; struct CSsl3TlsClientContext *
0x18000b112  call    ?SetServerHelloCipher@CCipherMill@@QEAAKPEAVCSsl3TlsClientContext@@K@Z; CCipherMill::SetServerHelloCipher(CSsl3TlsClientContext *,ulong)
0x18000b117  mov     r10, [rbx+8]
0x18000b11b  mov     edi, eax
0x18000b11d  test    eax, eax
0x18000b11f  jnz     loc_18000B4CB
0x18000b125  mov     eax, [r10+740h]
0x18000b12c  bt      rax, 0Fh
0x18000b131  jnb     loc_18000B382
0x18000b137  mov     [rsp+58h+arg_8], 0
0x18000b140  lea     rdx, [rsp+58h+arg_8]
0x18000b145  mov     rax, [r10]
0x18000b148  mov     rcx, r10
0x18000b14b  mov     rax, [rax+0F0h]
0x18000b152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b157  mov     r11, cs:?m_pSessionCacheManager@CSessionCacheManager@@0PEAV1@EA; CSessionCacheManager * CSessionCacheManager::m_pSessionCacheManager
0x18000b15e  test    r11, r11
0x18000b161  jz      short loc_18000B1A2
0x18000b163  mov     rax, [rsp+58h+arg_8]
0x18000b168  mov     rcx, [rax+0A0h]
0x18000b16f  xor     eax, eax
0x18000b171  mov     rdx, [rcx+108h]; unsigned __int16 *
0x18000b178  test    rdx, rdx
0x18000b17b  jnz     loc_18000B331
0x18000b181  xor     edx, edx
0x18000b183  div     dword ptr [r11+2Ch]
0x18000b187  mov     ecx, eax
0x18000b189  imul    rcx, 98h
0x18000b190  add     rcx, [r11+20h]
0x18000b194  jz      short loc_18000B1A2
0x18000b196  add     rcx, 30h ; '0'; Resource
0x18000b19a  mov     dl, 1; Wait
0x18000b19c  call    cs:__imp_RtlAcquireResourceExclusive
0x18000b1a2  mov     rax, [rsp+58h+arg_8]
0x18000b1a7  mov     dl, 1; Wait
0x18000b1a9  mov     rcx, [rax+28h]
0x18000b1ad  add     rcx, 50h ; 'P'; Resource
0x18000b1b1  call    cs:__imp_RtlAcquireResourceExclusive
0x18000b1b7  mov     rax, [rsp+58h+arg_8]
0x18000b1bc  mov     rdx, [rbx+8]
0x18000b1c0  mov     rcx, [rax+28h]
0x18000b1c4  mov     eax, [rdx+58h]
0x18000b1c7  mov     [rcx+0B0h], eax
0x18000b1cd  mov     rax, [rsp+58h+arg_8]
0x18000b1d2  mov     rcx, [rax+28h]
0x18000b1d6  add     rcx, 50h ; 'P'; Resource
0x18000b1da  call    cs:__imp_RtlReleaseResource
0x18000b1e0  mov     r11, cs:?m_pSessionCacheManager@CSessionCacheManager@@0PEAV1@EA; CSessionCacheManager * CSessionCacheManager::m_pSessionCacheManager
0x18000b1e7  test    r11, r11
0x18000b1ea  jz      short loc_18000B229
0x18000b1ec  mov     rax, [rsp+58h+arg_8]
0x18000b1f1  mov     rcx, [rax+0A0h]
0x18000b1f8  xor     eax, eax
0x18000b1fa  mov     rdx, [rcx+108h]; unsigned __int16 *
0x18000b201  test    rdx, rdx
0x18000b204  jnz     loc_18000B324
0x18000b20a  xor     edx, edx
0x18000b20c  div     dword ptr [r11+2Ch]
0x18000b210  mov     ecx, eax
0x18000b212  imul    rcx, 98h
0x18000b219  add     rcx, [r11+20h]
0x18000b21d  jz      short loc_18000B229
0x18000b21f  add     rcx, 30h ; '0'; Resource
0x18000b223  call    cs:__imp_RtlReleaseResource
0x18000b229  mov     rax, [rbx+8]
0x18000b22d  mov     byte ptr [rax+80Ch], 0
0x18000b234  test    r15b, r15b
0x18000b237  jnz     loc_18000B4ED
0x18000b23d  mov     rcx, [rbx+8]
0x18000b241  mov     dl, 1
0x18000b243  mov     rax, [rcx]
0x18000b246  mov     rax, [rax+230h]
0x18000b24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b252  mov     edi, eax
0x18000b254  test    eax, eax
0x18000b256  jnz     short loc_18000B272
0x18000b258  test    r15b, r15b
0x18000b25b  jnz     short loc_18000B270
0x18000b25d  mov     rcx, [rbx+8]; this
0x18000b261  call    ?SetServerKeyShare@CTls13ClientContext@@QEAAKXZ; CTls13ClientContext::SetServerKeyShare(void)
0x18000b266  mov     edi, eax
0x18000b268  test    eax, eax
0x18000b26a  jnz     loc_18000B5FA
0x18000b270  mov     eax, edi
0x18000b272  mov     r13, [rsp+58h+var_28]
0x18000b277  mov     r12, [rsp+58h+var_20]
0x18000b27c  mov     rbp, [rsp+58h+arg_0]
0x18000b281  mov     r15, [rsp+58h+var_38]
0x18000b286  mov     r14, [rsp+58h+var_30]
0x18000b28b  mov     rsi, [rsp+58h+var_18]
0x18000b290  add     rsp, 48h
0x18000b294  pop     rdi
0x18000b295  pop     rbx
0x18000b296  retn
0x18000b297  mov     rcx, rbx
0x18000b29a  mov     dword ptr [rax+5Ch], 64h ; 'd'
0x18000b2a1  call    ?ClearKeyShares@?$CTls13Handshake@VCTls13ClientContext@@VCTls13ExtClient@@@@QEAAXXZ; CTls13Handshake<CTls13ClientContext,CTls13ExtClient>::ClearKeyShares(void)
0x18000b2a6  mov     r15b, 1
0x18000b2a9  jmp     loc_18000AFCD
0x18000b2ae  cmp     [rsp+58h+arg_18], 47h ; 'G'
0x18000b2b3  jz      loc_18000B59A
0x18000b2b9  xor     eax, eax
0x18000b2bb  jmp     short loc_18000B272
0x18000b2bd  mov     r10, [rbx+8]
0x18000b2c1  mov     rdx, [r10+68h]
0x18000b2c5  test    rdx, rdx
0x18000b2c8  jz      loc_18000B534
0x18000b2ce  mov     ecx, esi; unsigned int
0x18000b2d0  call    ?ConvertSslVersionToSchannelProtocol@@YAKK@Z; ConvertSslVersionToSchannelProtocol(ulong)
0x18000b2d5  and     eax, [rdx+0D8h]
0x18000b2db  and     eax, 0A2AA0h
0x18000b2e0  jz      loc_18000B41B
0x18000b2e6  mov     ecx, eax; unsigned int
0x18000b2e8  mov     [r10+58h], eax
0x18000b2ec  call    ?ConvertSchannelProtocolToSsl@@YAGK@Z; ConvertSchannelProtocolToSsl(ulong)
0x18000b2f1  mov     [r10+22h], ax
0x18000b2f6  jmp     loc_18000B0BD
0x18000b2fb  mov     rcx, [rbx+8]
0x18000b2ff  mov     r9b, 32h ; '2'
0x18000b302  mov     edx, 64h ; 'd'
0x18000b307  mov     r8d, 80090308h
0x18000b30d  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18000b312  mov     eax, 80090308h
0x18000b317  jmp     loc_18000B27C
0x18000b31c  xor     r8b, r8b
0x18000b31f  jmp     loc_18000B0AF
0x18000b324  mov     rcx, r11; this
0x18000b327  call    ?ComputeClientCacheIndex@CSessionCacheManager@@AEAAKPEBG@Z; CSessionCacheManager::ComputeClientCacheIndex(ushort const *)
0x18000b32c  jmp     loc_18000B20A
0x18000b331  mov     rcx, r11; this
0x18000b334  call    ?ComputeClientCacheIndex@CSessionCacheManager@@AEAAKPEBG@Z; CSessionCacheManager::ComputeClientCacheIndex(ushort const *)
0x18000b339  jmp     loc_18000B181
0x18000b33e  movzx   edx, word ptr [r10+0DD4h]
0x18000b346  mov     rcx, rbx
0x18000b349  call    ?IsGroupOfferedByClient@?$CTls13Handshake@VCTls13ClientContext@@VCTls13ExtClient@@@@QEBAEG@Z; CTls13Handshake<CTls13ClientContext,CTls13ExtClient>::IsGroupOfferedByClient(ushort)
0x18000b34e  test    al, al
0x18000b350  jz      loc_18000B10C
0x18000b356  mov     edx, 64h ; 'd'
0x18000b35b  mov     r9b, 2Fh ; '/'
0x18000b35e  mov     r8d, 80090326h
0x18000b364  mov     rcx, r10
0x18000b367  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18000b36c  mov     eax, 80090326h
0x18000b371  jmp     loc_18000B272
0x18000b376  mov     eax, 57h ; 'W'
0x18000b37b  add     rsp, 48h
0x18000b37f  pop     rdi
0x18000b380  pop     rbx
0x18000b381  retn
0x18000b382  mov     rdi, [r10+70h]
0x18000b386  test    rdi, rdi
0x18000b389  jz      loc_18000B4E3
0x18000b38f  mov     rcx, [rdi+28h]
0x18000b393  mov     dl, 1; Wait
0x18000b395  add     rcx, 50h ; 'P'; Resource
0x18000b399  call    cs:__imp_RtlAcquireResourceShared
0x18000b39f  mov     rax, [rdi+28h]
0x18000b3a3  mov     rcx, [rax+0B8h]
0x18000b3aa  lea     rdx, [rax+50h]
0x18000b3ae  test    rcx, rcx
0x18000b3b1  jz      short loc_18000B3C4
0x18000b3b3  mov     ecx, [rcx+2Ch]; unsigned int
0x18000b3b6  call    ?GetHashInfo@@YAPEAUhsel@@I@Z; GetHashInfo(uint)
0x18000b3bb  test    rax, rax
0x18000b3be  jnz     loc_18000B45C
0x18000b3c4  mov     rcx, rdx; Resource
0x18000b3c7  mov     ebx, 54Fh
0x18000b3cc  call    cs:__imp_RtlReleaseResource
0x18000b3d2  mov     eax, ebx
0x18000b3d4  jmp     loc_18000B272
0x18000b3d9  mov     rcx, [rbx+8]
0x18000b3dd  mov     r9b, 32h ; '2'
0x18000b3e0  mov     edx, 6Ah ; 'j'
0x18000b3e5  mov     r8d, 80090308h
0x18000b3eb  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
  ... truncated ...
```
