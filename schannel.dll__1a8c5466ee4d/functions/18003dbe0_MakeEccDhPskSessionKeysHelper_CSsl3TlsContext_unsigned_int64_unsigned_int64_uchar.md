# MakeEccDhPskSessionKeysHelper(CSsl3TlsContext *,unsigned __int64,unsigned __int64,uchar)

- ea: `0x18003dbe0`
- end: `0x18003e1a0`
- name: `?MakeEccDhPskSessionKeysHelper@@YAKPEAVCSsl3TlsContext@@_K1E@Z`
- size: `1472`
- prototype: `unsigned int __fastcall(struct CSsl3TlsContext *, unsigned __int64, unsigned __int64, unsigned __int8)`
- caller_count: `6`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001aecc`
- `0x180020450`
- `0x18003d8d8`
- `0x18004eae8`
- `0x180057358`
- `0x180085474`

## callees

- `0x180011054`
- `0x1800165a4`
- `0x1800214f0`
- `0x18003dbe0`
- `0x18004bca4`
- `0x1800597b0`
- `0x18005a160`
- `0x18005f1e4`
- `0x180091010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18003de7b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003de7b`
- `ntdll!RtlReleaseResource` at `0x18003de9a`
- `ntdll!RtlReleaseResource` at `0x18003de9a`
- `ntdll!RtlInitUnicodeString` at `0x18008f4f8`
- `ntdll!RtlInitUnicodeString` at `0x18008f506`
- `ntdll!RtlInitUnicodeString` at `0x18008f4f8`
- `ntdll!RtlInitUnicodeString` at `0x18008f506`
- `ncrypt!SslGenerateSessionKeys` at `0x18003de5d`
- `ncrypt!SslGenerateSessionKeys` at `0x18003de5d`
- `ncrypt!SslComputeSessionHash` at `0x18003df3a`
- `ncrypt!SslComputeSessionHash` at `0x18003df3a`
- `ncrypt!SslFreeObject` at `0x18003e055`
- `ncrypt!SslFreeObject` at `0x18003e170`
- `ncrypt!SslFreeObject` at `0x18003e184`
- `ncrypt!SslFreeObject` at `0x18003e055`
- `ncrypt!SslFreeObject` at `0x18003e170`
- `ncrypt!SslFreeObject` at `0x18003e184`
- `ncrypt!SslGenerateMasterKey` at `0x18003dd72`
- `ncrypt!SslGenerateMasterKey` at `0x18003dd72`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18003deb5`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18003deb5`

## pseudocode

```c
__int64 __fastcall MakeEccDhPskSessionKeysHelper(struct CSsl3TlsContext *a1, __int64 a2, __int64 a3, char a4)
{
  unsigned int v4; // r12d
  __int64 v9; // rcx
  _WORD *v10; // r9
  int v11; // eax
  unsigned int v12; // edx
  __int64 v13; // r8
  __int64 *v14; // rax
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned int v19; // esi
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // r12
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned int v27; // esi
  __int64 v28; // r9
  __int64 *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  unsigned int v33; // esi
  __int64 v34; // rax
  __int64 *v35; // rcx
  __int64 v36; // rcx
  unsigned int v37; // eax
  unsigned int v38; // esi
  __int64 v39; // rax
  __int64 v40; // rcx
  const WCHAR *v41; // rdx
  const WCHAR *v42; // r14
  __int64 v43; // rax
  __int64 v44; // rdx
  int v45; // r14d
  __int64 v46; // r12
  int v47; // edi
  __int64 v48; // rdx
  __int64 v49; // r8
  PEVENT_DATA_DESCRIPTOR v50; // [rsp+20h] [rbp-E0h]
  __int64 v51; // [rsp+28h] [rbp-D8h]
  int v52; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v53; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v54; // [rsp+70h] [rbp-90h] BYREF
  int v55; // [rsp+80h] [rbp-80h] BYREF
  int v56; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v57; // [rsp+8Ch] [rbp-74h]
  int *v58; // [rsp+90h] [rbp-70h]
  _BYTE v59[8]; // [rsp+A0h] [rbp-60h] BYREF
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  int v62; // [rsp+720h] [rbp+620h] BYREF
  _BYTE v63[44]; // [rsp+724h] [rbp+624h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+750h] [rbp+650h] BYREF
  char v65; // [rsp+760h] [rbp+660h] BYREF
  _BYTE v66[64]; // [rsp+7A0h] [rbp+6A0h] BYREF

  v4 = 0;
  v53 = 0;
  v57 = 0;
  v62 = 0;
  memset(v63, 0, sizeof(v63));
  memset_0(v66, 0, sizeof(v66));
  v52 = 0;
  if ( !a1 )
    return 87;
  v58 = &v62;
  v11 = *((_DWORD *)a1 + 464);
  v56 = 0;
  if ( (v11 & 0x8000000) != 0 )
  {
    v33 = *((unsigned __int16 *)a1 + 17);
    v34 = (*(__int64 (__fastcall **)(struct CSsl3TlsContext *, _QWORD))(*(_QWORD *)a1 + 576LL))(a1, 0);
    v35 = (__int64 *)*((_QWORD *)a1 + 1);
    if ( v35 )
      v36 = *v35;
    else
      v36 = 0;
    v37 = SslComputeSessionHash(v36, v34, v33, v66, 64, &v52, 0);
    v38 = v37;
    if ( v37 )
    {
      LOBYTE(v10) = 51;
      CSslContext::SetErrorAndFatalAlert(a1, 604, v37, v10);
      return v38;
    }
    v12 = 1;
    v62 = v52;
    *(_QWORD *)&v63[4] = v66;
    *(_DWORD *)v63 = 25;
  }
  else
  {
    *(_DWORD *)v63 = 20;
    *(_QWORD *)&v63[4] = (char *)a1 + 1992;
    v12 = 2;
    v62 = 32;
    *(_QWORD *)&v63[20] = (char *)a1 + 2024;
    *(_DWORD *)&v63[16] = 21;
    *(_DWORD *)&v63[12] = 32;
  }
  v13 = *((_QWORD *)a1 + 1);
  v57 = v12;
  if ( *(_DWORD *)(v13 + 48) == 4 )
  {
    v10 = (_WORD *)*((_QWORD *)a1 + 321);
    if ( !v10 )
      return 590624;
    if ( !*v10 )
    {
      LOBYTE(v10) = 115;
      CSslContext::SetErrorAndFatalAlert(a1, 602, 87, v10);
      return 87;
    }
    v9 = 2LL * v12;
    *(_DWORD *)&v63[8 * v9] = 23;
    *(_DWORD *)&v63[8 * v9 - 4] = (unsigned __int16)*v10;
    *(_QWORD *)&v63[8 * v9 + 4] = v10 + 1;
    v57 = v12 + 1;
  }
  if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(
      v9,
      (const EVENT_DESCRIPTOR *)&GenerateMasterKeyStart,
      v13,
      (__int64)v10,
      (PEVENT_DATA_DESCRIPTOR)&DestinationString);
    v13 = *((_QWORD *)a1 + 1);
  }
  v14 = (__int64 *)v13;
  if ( (*((_BYTE *)a1 + 32) & 1) != 0 )
  {
    if ( v13 )
    {
      v15 = *(_DWORD *)(v13 + 28);
      v16 = *((unsigned __int16 *)a1 + 17);
LABEL_12:
      v17 = *v14;
      goto LABEL_13;
    }
    v14 = 0;
  }
  else
  {
    v14 = (__int64 *)v13;
  }
  v16 = *((unsigned __int16 *)a1 + 17);
  v15 = 0;
  if ( v14 )
    goto LABEL_12;
  v17 = 0;
LABEL_13:
  v19 = SslGenerateMasterKey(v17, a2, a3, &v53, v16, v15, &v56, 0, 0, &v52, (unsigned int)(a4 != 0) + 1);
  if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v18,
      (const EVENT_DESCRIPTOR *)&GenerateMasterKeyStop,
      v20,
      v21,
      (PEVENT_DATA_DESCRIPTOR)&DestinationString);
  if ( !v19 )
  {
    v22 = *((_QWORD *)a1 + 235);
    v23 = v53;
    v55 = 0;
    v54 = 0;
    if ( v22 )
    {
      SslFreeObject(v22, 0);
      *((_QWORD *)a1 + 235) = 0;
    }
    v24 = *((_QWORD *)a1 + 236);
    if ( v24 )
    {
      SslFreeObject(v24, 0);
      *((_QWORD *)a1 + 236) = 0;
    }
    if ( (*((_BYTE *)a1 + 32) & 1) == 0 )
      goto LABEL_27;
    v25 = *((_QWORD *)a1 + 1);
    if ( !v25 || !*(_DWORD *)(v25 + 28) )
      goto LABEL_27;
    v54.Buffer = (PWSTR)&v65;
    v26 = *(_QWORD *)a1;
    *(_DWORD *)&v54.Length = 0;
    *(_DWORD *)(&v54.MaximumLength + 1) = 4;
    v27 = (*(__int64 (__fastcall **)(struct CSsl3TlsContext *, _QWORD, int *, struct _UNICODE_STRING *, _QWORD, _QWORD))(v26 + 144))(
            a1,
            0,
            &v55,
            &v54,
            0,
            0);
    if ( v27 )
    {
      v48 = 601;
    }
    else
    {
      v29 = (__int64 *)*((_QWORD *)a1 + 1);
      if ( v29 )
        v30 = *v29;
      else
        v30 = 0;
      v27 = SslGenerateSessionKeys(v30, v23, (char *)a1 + 1880, (char *)a1 + 1888, &v54, 0);
      if ( !v27 )
      {
LABEL_27:
        RtlAcquireResourceExclusive((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 40LL) + 80LL), 1u);
        *(_QWORD *)(*((_QWORD *)a1 + 14) + 32LL) = v53;
        RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 40LL) + 80LL));
        v31 = 8;
        if ( !a4 )
          v31 = 6;
        LsaIModifyPerformanceCounter(v31, 0, 0);
        return 0;
      }
      v48 = 600;
    }
    LOBYTE(v28) = 51;
    CSslContext::SetErrorAndFatalAlert(a1, v48, v27, v28);
    SslFreeObject(v53, 0);
    return v27;
  }
  v39 = (*(__int64 (__fastcall **)(struct CSsl3TlsContext *))(*(_QWORD *)a1 + 352LL))(a1);
  v40 = *((_QWORD *)a1 + 231);
  if ( !*(_WORD *)(v40 + 34) )
  {
    *(_WORD *)(v40 + 34) = 602;
    *(_DWORD *)(v40 + 36) = v19;
  }
  *((_WORD *)a1 + 60) = 13058;
  v41 = &Class;
  v42 = &Class;
  if ( v39 )
    v42 = (const WCHAR *)v39;
  v43 = *((_QWORD *)a1 + 13);
  if ( v43 )
  {
    v4 = *(_DWORD *)(v43 + 276);
    v41 = (const WCHAR *)(v43 + 280);
  }
  if ( (g_dwEventLogging & 4) != 0 )
  {
    DestinationString = 0;
    v54 = 0;
    RtlInitUnicodeString(&DestinationString, v41);
    RtlInitUnicodeString(&v54, v42);
    LODWORD(v51) = 602;
    LODWORD(v50) = 51;
    SchEventWrite(&SSLEVENT_GENERATE_FATAL_ALERT, L"duddu", v4, &DestinationString, v50, v51, &v54);
  }
  memset_0(v59, 0, 0x680u);
  v44 = *((_QWORD *)a1 + 1);
  v45 = *((unsigned __int16 *)a1 + 17);
  v46 = *((_QWORD *)a1 + 232);
  v61 = *((_DWORD *)a1 + 4);
  if ( v44 )
  {
    v49 = *((_QWORD *)a1 + 14);
    v47 = *(_DWORD *)(v44 + 28);
    v60 = v47;
    if ( v49 )
      CSchannelTelemetryContext::LogKeyExchange(
        (struct CSsl3TlsContext *)((char *)a1 + 144),
        *(_DWORD *)(v44 + 32),
        *(_DWORD *)(*(_QWORD *)(v49 + 40) + 8LL));
  }
  else
  {
    v47 = 0;
    v60 = 0;
  }
  if ( CTelemetryContext::s_IsTelemetryGloballyInitialized )
  {
    *((_DWORD *)a1 + 47) = v61;
    *((_BYTE *)a1 + 260) = 51;
    *((_DWORD *)a1 + 64) = v19;
    *((_DWORD *)a1 + 66) = 602;
    *((_DWORD *)a1 + 46) = v47;
    *((_DWORD *)a1 + 48) = v45;
    *((_QWORD *)a1 + 35) = v46;
    *((_BYTE *)a1 + 169) = 1;
  }
  CSchannelTelemetryContext::LogDebugTraceHandshakeInfo((struct CSsl3TlsContext *)((char *)a1 + 144), L"Fatal Error");
  return v19;
}

```

## disassembly

```asm
0x18003dbe0  push    rbp
0x18003dbe2  push    rbx
0x18003dbe3  push    r12
0x18003dbe5  push    r13
0x18003dbe7  push    r14
0x18003dbe9  push    r15
0x18003dbeb  lea     rbp, [rsp-6F8h]
0x18003dbf3  sub     rsp, 7F8h
0x18003dbfa  mov     rax, cs:__security_cookie
0x18003dc01  xor     rax, rsp
0x18003dc04  mov     [rbp+720h+var_40], rax
0x18003dc0b  xorps   xmm0, xmm0
0x18003dc0e  xor     r12d, r12d
0x18003dc11  mov     r15, r8
0x18003dc14  mov     [rsp+820h+var_7B8], r12
0x18003dc19  mov     r14, rdx
0x18003dc1c  mov     [rbp+720h+var_794], r12d
0x18003dc20  mov     rbx, rcx
0x18003dc23  mov     [rbp+720h+var_100], r12d
0x18003dc2a  movups  xmmword ptr [rbp+720h+var_EC], xmm0
0x18003dc31  xor     edx, edx; Val
0x18003dc33  lea     rcx, [rbp+720h+var_80]; void *
0x18003dc3a  mov     r8d, 40h ; '@'; Size
0x18003dc40  movzx   r13d, r9b
0x18003dc44  movups  xmmword ptr [rbp+720h+var_EC+0Ch], xmm0
0x18003dc4b  movups  [rbp+720h+var_FC], xmm0
0x18003dc52  call    memset_0
0x18003dc57  mov     [rsp+820h+var_7C0], r12d
0x18003dc5c  test    rbx, rbx
0x18003dc5f  jz      loc_18003E093
0x18003dc65  lea     rax, [rbp+720h+var_100]
0x18003dc6c  mov     [rsp+820h+arg_18], rsi
0x18003dc74  mov     [rbp+720h+var_790], rax
0x18003dc78  mov     eax, [rbx+740h]
0x18003dc7e  mov     [rsp+820h+var_30], rdi
0x18003dc86  mov     [rbp+720h+var_798], r12d
0x18003dc8a  bt      rax, 1Bh
0x18003dc8f  jb      loc_18003DEEE
0x18003dc95  lea     rax, [rbx+7C8h]
0x18003dc9c  mov     dword ptr [rbp+720h+var_FC], 14h
0x18003dca6  mov     qword ptr [rbp+720h+var_FC+4], rax
0x18003dcad  mov     edx, 2
0x18003dcb2  lea     rax, [rbx+7E8h]
0x18003dcb9  mov     [rbp+720h+var_100], 20h ; ' '
0x18003dcc3  mov     qword ptr [rbp+720h+var_EC+4], rax
0x18003dcca  mov     dword ptr [rbp+720h+var_EC], 15h
0x18003dcd4  mov     dword ptr [rbp+720h+var_FC+0Ch], 20h ; ' '
0x18003dcde  mov     r8, [rbx+8]; int
0x18003dce2  mov     [rbp+720h+var_794], edx
0x18003dce5  cmp     dword ptr [r8+30h], 4
0x18003dcea  jz      loc_18003E0DB
0x18003dcf0  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x18003dcf7  jnz     loc_18003E09D
0x18003dcfd  test    r13b, r13b
0x18003dd00  mov     edx, r12d
0x18003dd03  mov     rax, r8
0x18003dd06  setnz   dl
0x18003dd09  inc     edx
0x18003dd0b  test    byte ptr [rbx+20h], 1
0x18003dd0f  jz      short loc_18003DD25
0x18003dd11  test    rax, rax
0x18003dd14  jz      loc_18003E0F5
0x18003dd1a  mov     r8d, [rax+1Ch]
0x18003dd1e  movzx   r9d, word ptr [rbx+22h]
0x18003dd23  jmp     short loc_18003DD39
0x18003dd25  mov     rax, r8
0x18003dd28  movzx   r9d, word ptr [rbx+22h]
0x18003dd2d  mov     r8d, r12d
0x18003dd30  test    rax, rax
0x18003dd33  jz      loc_18003E062
0x18003dd39  mov     rcx, [rax]
0x18003dd3c  mov     [rsp+820h+var_7D0], edx
0x18003dd40  lea     rax, [rsp+820h+var_7C0]
0x18003dd45  mov     [rsp+820h+var_7D8], rax
0x18003dd4a  mov     rdx, r14
0x18003dd4d  mov     [rsp+820h+var_7E0], r12d
0x18003dd52  lea     rax, [rbp+720h+var_798]
0x18003dd56  mov     [rsp+820h+var_7E8], r12
0x18003dd5b  mov     [rsp+820h+var_7F0], rax
0x18003dd60  mov     dword ptr [rsp+820h+var_7F8], r8d
0x18003dd65  mov     r8, r15
0x18003dd68  mov     dword ptr [rsp+820h+var_800], r9d
0x18003dd6d  lea     r9, [rsp+820h+var_7B8]
0x18003dd72  call    cs:__imp_SslGenerateMasterKey
0x18003dd78  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x18003dd7f  mov     esi, eax
0x18003dd81  jnz     loc_18003E0BE
0x18003dd87  test    esi, esi
0x18003dd89  jnz     loc_18003DF76
0x18003dd8f  mov     rcx, [rbx+758h]
0x18003dd96  xor     esi, esi
0x18003dd98  mov     r12, [rsp+820h+var_7B8]
0x18003dd9d  xorps   xmm0, xmm0
0x18003dda0  mov     [rbp+720h+var_7A0], esi
0x18003dda3  movups  xmmword ptr [rsp+820h+var_7B0.Length], xmm0
0x18003dda8  test    rcx, rcx
0x18003ddab  jnz     loc_18003E16E
0x18003ddb1  mov     rcx, [rbx+760h]
0x18003ddb8  test    rcx, rcx
0x18003ddbb  jnz     loc_18003E182
0x18003ddc1  test    byte ptr [rbx+20h], 1
0x18003ddc5  jz      loc_18003DE6D
0x18003ddcb  mov     rax, [rbx+8]
0x18003ddcf  test    rax, rax
0x18003ddd2  jz      loc_18003DE6D
0x18003ddd8  cmp     [rax+1Ch], esi
0x18003dddb  jz      loc_18003DE6D
0x18003dde1  lea     rax, [rbp+720h+var_C0]
0x18003dde8  mov     [rsp+820h+var_7F8], rsi
0x18003dded  mov     [rsp+820h+var_7B0.Buffer], rax
0x18003ddf2  lea     r9, [rsp+820h+var_7B0]
0x18003ddf7  mov     rax, [rbx]
0x18003ddfa  lea     r8, [rbp+720h+var_7A0]
0x18003ddfe  xor     edx, edx
0x18003de00  mov     dword ptr [rsp+820h+var_7B0.Length], esi
0x18003de04  mov     rcx, rbx
0x18003de07  mov     dword ptr [rsp+820h+var_7B0+4], 4
0x18003de0f  mov     [rsp+820h+var_800], rsi
0x18003de14  mov     rax, [rax+90h]
0x18003de1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de20  mov     esi, eax
0x18003de22  test    eax, eax
0x18003de24  jnz     loc_18003E03B
0x18003de2a  mov     rax, [rbx+8]
0x18003de2e  test    rax, rax
0x18003de31  jz      loc_18003E06A
0x18003de37  mov     rcx, [rax]
0x18003de3a  lea     rax, [rsp+820h+var_7B0]
0x18003de3f  mov     dword ptr [rsp+820h+var_7F8], 0
0x18003de47  lea     r9, [rbx+760h]
0x18003de4e  mov     [rsp+820h+var_800], rax
0x18003de53  lea     r8, [rbx+758h]
0x18003de5a  mov     rdx, r12
0x18003de5d  call    cs:__imp_SslGenerateSessionKeys
0x18003de63  mov     esi, eax
0x18003de65  test    eax, eax
0x18003de67  jnz     loc_18003E196
0x18003de6d  mov     rax, [rbx+70h]
0x18003de71  mov     dl, 1; Wait
0x18003de73  mov     rcx, [rax+28h]
0x18003de77  add     rcx, 50h ; 'P'; Resource
0x18003de7b  call    cs:__imp_RtlAcquireResourceExclusive
0x18003de81  mov     rcx, [rbx+70h]
0x18003de85  mov     rax, [rsp+820h+var_7B8]
0x18003de8a  mov     [rcx+20h], rax
0x18003de8e  mov     rax, [rbx+70h]
0x18003de92  mov     rcx, [rax+28h]
0x18003de96  add     rcx, 50h ; 'P'; Resource
0x18003de9a  call    cs:__imp_RtlReleaseResource
0x18003dea0  mov     ecx, 8
0x18003dea5  mov     eax, 6
0x18003deaa  test    r13b, r13b
0x18003dead  cmovz   ecx, eax
0x18003deb0  xor     r8d, r8d
0x18003deb3  xor     edx, edx
0x18003deb5  call    cs:__imp_LsaIModifyPerformanceCounter
0x18003debb  xor     eax, eax
0x18003debd  mov     rsi, [rsp+820h+arg_18]
0x18003dec5  mov     rdi, [rsp+820h+var_30]
0x18003decd  mov     rcx, [rbp+720h+var_40]
0x18003ded4  xor     rcx, rsp; StackCookie
0x18003ded7  call    __security_check_cookie
0x18003dedc  add     rsp, 7F8h
0x18003dee3  pop     r15
0x18003dee5  pop     r14
0x18003dee7  pop     r13
0x18003dee9  pop     r12
0x18003deeb  pop     rbx
0x18003deec  pop     rbp
0x18003deed  retn
0x18003deee  mov     rax, [rbx]
0x18003def1  xor     edx, edx
0x18003def3  movzx   esi, word ptr [rbx+22h]
0x18003def7  mov     rcx, rbx
0x18003defa  mov     rax, [rax+240h]
0x18003df01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df06  mov     rcx, [rbx+8]
0x18003df0a  test    rcx, rcx
0x18003df0d  jz      loc_18003E071
0x18003df13  mov     rcx, [rcx]
0x18003df16  lea     rdx, [rsp+820h+var_7C0]
0x18003df1b  mov     dword ptr [rsp+820h+var_7F0], r12d
0x18003df20  mov     [rsp+820h+var_7F8], rdx
0x18003df25  lea     r9, [rbp+720h+var_80]
0x18003df2c  mov     rdx, rax
0x18003df2f  mov     dword ptr [rsp+820h+var_800], 40h ; '@'
0x18003df37  mov     r8d, esi
0x18003df3a  call    cs:__imp_SslComputeSessionHash
0x18003df40  mov     esi, eax
0x18003df42  test    eax, eax
0x18003df44  jnz     loc_18003E079
0x18003df4a  mov     eax, [rsp+820h+var_7C0]
0x18003df4e  mov     edx, 1
0x18003df53  mov     [rbp+720h+var_100], eax
0x18003df59  lea     rax, [rbp+720h+var_80]
0x18003df60  mov     qword ptr [rbp+720h+var_FC+4], rax
0x18003df67  mov     dword ptr [rbp+720h+var_FC], 19h
0x18003df71  jmp     loc_18003DCDE
0x18003df76  mov     rax, [rbx]
0x18003df79  mov     rcx, rbx
0x18003df7c  mov     rax, [rax+160h]
0x18003df83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df88  mov     rcx, [rbx+738h]
0x18003df8f  mov     r15d, 25Ah
0x18003df95  cmp     [rcx+22h], r12w
0x18003df9a  jnz     short loc_18003DFA4
0x18003df9c  mov     [rcx+22h], r15w
0x18003dfa1  mov     [rcx+24h], esi
0x18003dfa4  test    rax, rax
0x18003dfa7  mov     word ptr [rbx+78h], 3302h
0x18003dfad  lea     rdx, Class
0x18003dfb4  mov     r14, rdx
0x18003dfb7  cmovnz  r14, rax
0x18003dfbb  mov     rax, [rbx+68h]
0x18003dfbf  test    rax, rax
0x18003dfc2  jz      short loc_18003DFD2
0x18003dfc4  mov     r12d, [rax+114h]
0x18003dfcb  lea     rdx, [rax+118h]; SourceString
0x18003dfd2  test    cs:?g_dwEventLogging@@3KA, 4; ulong g_dwEventLogging
0x18003dfd9  jnz     loc_18008F4DF
0x18003dfdf  xor     edx, edx; Val
0x18003dfe1  lea     rcx, [rbp+720h+var_780]; void *
0x18003dfe5  mov     r8d, 680h; Size
0x18003dfeb  call    memset_0
0x18003dff0  mov     rdx, [rbx+8]
0x18003dff4  mov     eax, [rbx+10h]
0x18003dff7  movzx   r14d, word ptr [rbx+22h]
0x18003dffc  mov     r12, [rbx+740h]
0x18003e003  mov     [rbp+720h+var_778+4], eax
0x18003e006  test    rdx, rdx
0x18003e009  jnz     loc_18003E0FD
0x18003e00f  xor     edi, edi
0x18003e011  mov     [rbp+720h+var_778], edi
0x18003e014  cmp     cs:?s_IsTelemetryGloballyInitialized@CTelemetryContext@@1_NA, 0; bool CTelemetryContext::s_IsTelemetryGloballyInitialized
0x18003e01b  lea     rcx, [rbx+90h]; this
0x18003e022  jnz     loc_18003E12C
0x18003e028  lea     rdx, aFatalError; "Fatal Error"
0x18003e02f  call    ?LogDebugTraceHandshakeInfo@CSchannelTelemetryContext@@QEAAXQEAG@Z; CSchannelTelemetryContext::LogDebugTraceHandshakeInfo(ushort * const)
0x18003e034  mov     eax, esi
0x18003e036  jmp     loc_18003DEBD
0x18003e03b  mov     edx, 259h
0x18003e040  mov     r9b, 33h ; '3'
0x18003e043  mov     r8d, esi
0x18003e046  mov     rcx, rbx
0x18003e049  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18003e04e  mov     rcx, [rsp+820h+var_7B8]
0x18003e053  xor     edx, edx
0x18003e055  call    cs:__imp_SslFreeObject
0x18003e05b  mov     eax, esi
0x18003e05d  jmp     loc_18003DEBD
0x18003e062  mov     rcx, r12
0x18003e065  jmp     loc_18003DD3C
0x18003e06a  xor     ecx, ecx
0x18003e06c  jmp     loc_18003DE3A
0x18003e071  mov     rcx, r12
0x18003e074  jmp     loc_18003DF16
0x18003e079  mov     r9b, 33h ; '3'
0x18003e07c  mov     r8d, esi
0x18003e07f  mov     edx, 25Ch
0x18003e084  mov     rcx, rbx
0x18003e087  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18003e08c  mov     eax, esi
0x18003e08e  jmp     loc_18003DEBD
0x18003e093  mov     eax, 57h ; 'W'
0x18003e098  jmp     loc_18003DECD
0x18003e09d  lea     rax, [rbp+720h+DestinationString]
0x18003e0a4  lea     rdx, GenerateMasterKeyStart; int
0x18003e0ab  mov     [rsp+820h+var_800], rax; PEVENT_DATA_DESCRIPTOR
0x18003e0b0  call    McGenEventWrite_EventWriteTransfer
0x18003e0b5  mov     r8, [rbx+8]
0x18003e0b9  jmp     loc_18003DCFD
0x18003e0be  lea     rax, [rbp+720h+DestinationString]
0x18003e0c5  lea     rdx, GenerateMasterKeyStop; int
0x18003e0cc  mov     [rsp+820h+var_800], rax; PEVENT_DATA_DESCRIPTOR
0x18003e0d1  call    McGenEventWrite_EventWriteTransfer
0x18003e0d6  jmp     loc_18003DD87
0x18003e0db  mov     r9, [rbx+0A08h]
0x18003e0e2  test    r9, r9
0x18003e0e5  jnz     loc_18008F488
0x18003e0eb  mov     eax, 90320h
0x18003e0f0  jmp     loc_18003DEBD
0x18003e0f5  mov     rax, r12
0x18003e0f8  jmp     loc_18003DD28
0x18003e0fd  mov     r8, [rbx+70h]
0x18003e101  mov     edi, [rdx+1Ch]
0x18003e104  mov     [rbp+720h+var_778], edi
0x18003e107  test    r8, r8
0x18003e10a  jz      loc_18003E014
0x18003e110  mov     r8, [r8+28h]
0x18003e114  lea     rcx, [rbx+90h]; this
0x18003e11b  mov     edx, [rdx+20h]; unsigned int
0x18003e11e  mov     r8d, [r8+8]; unsigned int
0x18003e122  call    ?LogKeyExchange@CSchannelTelemetryContext@@QEAAXIK@Z; CSchannelTelemetryContext::LogKeyExchange(uint,ulong)
0x18003e127  jmp     loc_18003E014
0x18003e12c  mov     rax, qword ptr [rbp+720h+var_778]
0x18003e130  shr     rax, 20h
0x18003e134  mov     [rbx+0BCh], eax
0x18003e13a  mov     byte ptr [rbx+104h], 33h ; '3'
0x18003e141  mov     [rbx+100h], esi
0x18003e147  mov     [rbx+108h], r15d
  ... truncated ...
```
