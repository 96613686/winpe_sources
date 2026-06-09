# WinHttpEtwSetActivityIdFromHandle(void *,ulong,_WINHTTP_ETW_INFO *)

- ea: `0x18003b230`
- end: `0x18003b9f0`
- name: `?WinHttpEtwSetActivityIdFromHandle@@YAXPEAXKPEAU_WINHTTP_ETW_INFO@@@Z`
- size: `1984`
- prototype: `void __fastcall(void *, unsigned int, struct _WINHTTP_ETW_INFO *)`
- caller_count: `53`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a6a0`
- `0x18000d5c0`
- `0x18001137c`
- `0x180011970`
- `0x18001e610`
- `0x180023250`
- `0x180023de0`
- `0x1800247a0`
- `0x1800258c0`
- `0x180027880`
- `0x180027e00`
- `0x180027f90`
- `0x180028240`
- `0x180028560`
- `0x180028690`
- `0x180028840`
- `0x180028f60`
- `0x180029338`
- `0x1800295a0`
- `0x180029e60`
- `0x1800347e0`
- `0x180040010`
- `0x180042f20`
- `0x180047480`
- `0x18004b010`
- `0x18005af90`
- `0x1800604c0`
- `0x180062570`
- `0x180062ac0`
- `0x180068b40`
- `0x180069920`
- `0x18006f4ec`
- `0x1800741d0`
- `0x18007be60`
- `0x1800816c0`
- `0x18008c350`
- `0x180090330`
- `0x1800a4eb0`
- `0x1800a5a70`
- `0x1800a6190`
- `0x1800ac620`
- `0x1800adaf0`
- `0x1800adc70`
- `0x1800af5f8`
- `0x1800b2f30`
- `0x1800b4a60`
- `0x1800c65b0`
- `0x1800c6690`
- `0x1800c68a0`
- `0x1800c6df0`

## callees

- `0x180033404`
- `0x18003b230`
- `0x18003bc60`
- `0x18009013c`
- `0x1800a1d10`
- `0x1800cdd70`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800db758`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b40b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b605`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b40b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b605`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003b403`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003b5fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003b403`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003b5fd`
- `ntdll!EtwEventActivityIdControl` at `0x18003b3c8`
- `ntdll!EtwEventActivityIdControl` at `0x18003b44e`
- `ntdll!EtwEventActivityIdControl` at `0x18003b5c7`
- `ntdll!EtwEventActivityIdControl` at `0x18003b63b`
- `ntdll!EtwEventActivityIdControl` at `0x18003b6b8`
- `ntdll!EtwEventActivityIdControl` at `0x18003b3c8`
- `ntdll!EtwEventActivityIdControl` at `0x18003b44e`
- `ntdll!EtwEventActivityIdControl` at `0x18003b5c7`
- `ntdll!EtwEventActivityIdControl` at `0x18003b63b`
- `ntdll!EtwEventActivityIdControl` at `0x18003b6b8`

## pseudocode

```c
void __fastcall WinHttpEtwSetActivityIdFromHandle(char *a1, char a2, struct _WINHTTP_ETW_INFO *a3)
{
  struct _GUID *v3; // rsi
  char *v5; // rbx
  unsigned int v6; // edi
  signed __int32 v7; // eax
  char v8; // al
  unsigned int v9; // edi
  struct _GUID *v10; // r13
  struct _GUID *v11; // rbx
  __int64 v12; // rcx
  struct _GUID *v13; // rax
  __int64 v14; // rcx
  struct _GUID *v15; // rax
  __int64 v16; // rcx
  struct _GUID *p_Buf1; // rax
  int v18; // eax
  unsigned __int64 v19; // rcx
  const struct _GUID *v20; // r9
  bool v21; // sf
  signed __int32 v22; // esi
  DWORD TickCount; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v25; // rbx
  unsigned int IsValid; // esi
  __int64 v27; // r8
  __int64 v28; // r9
  _DWORD *v29; // r14
  __int64 v30; // rcx
  struct _WINHTTP_ETW_INFO *v31; // rax
  int v32; // r15d
  __int64 v33; // rcx
  struct _WINHTTP_ETW_INFO *v34; // rax
  __int64 v35; // rcx
  struct _GUID *v36; // rax
  int v37; // eax
  bool v38; // sf
  signed __int32 v39; // esi
  DWORD v40; // ebx
  unsigned __int64 v41; // rcx
  const struct _GUID *v42; // r9
  int v43; // eax
  bool v44; // sf
  int v45; // edx
  int v46; // eax
  bool v47; // sf
  const struct _EVENT_DESCRIPTOR *v48; // rdx
  unsigned __int64 v49; // rcx
  const struct _EVENT_DESCRIPTOR *v50; // rdx
  unsigned __int64 v51; // rcx
  __int64 v52; // [rsp+28h] [rbp-49h]
  const struct _GUID *v53; // [rsp+30h] [rbp-41h]
  unsigned int v54; // [rsp+38h] [rbp-39h]
  char *v56; // [rsp+50h] [rbp-21h] BYREF
  struct _GUID v57; // [rsp+58h] [rbp-19h] BYREF
  struct _GUID Buf1; // [rsp+68h] [rbp-9h] BYREF
  struct _GUID v59; // [rsp+78h] [rbp+7h] BYREF
  _UNKNOWN *retaddr; // [rsp+D0h] [rbp+5Fh]

  v3 = (struct _GUID *)a3;
  v56 = 0;
  v5 = a1;
  if ( !WinHttpEtwInitialized )
    return;
  if ( a1 )
  {
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    {
      LODWORD(v53) = 0;
      WPP_SF_qqD(1041, 10, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, (_DWORD)a1, (__int64)&v56);
    }
    if ( (unsigned int)HANDLE_OBJECT::IsValid(v5, 1684826455) )
    {
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
      {
        v45 = 11;
        goto LABEL_98;
      }
    }
    else
    {
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_q(1032, 19, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
      if ( *((_DWORD *)v5 + 12) )
      {
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_qq(
            1032,
            20,
            (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
            *((_QWORD *)v5 + 4),
            (__int64)v5);
        v6 = 6;
      }
      else
      {
        v6 = 0;
      }
      while ( 1 )
      {
        v7 = *((_DWORD *)v5 + 11);
        if ( v7 <= 0 )
          break;
        if ( v7 == _InterlockedCompareExchange((volatile signed __int32 *)v5 + 11, v7 + 1, v7) )
          goto LABEL_12;
      }
      v6 = 5;
LABEL_12:
      if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
      {
        LODWORD(v53) = *((_DWORD *)v5 + 11);
        WPP_SF_qqD(
          1045,
          21,
          (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
          *((_QWORD *)v5 + 4),
          (__int64)v5);
      }
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_d(1032, 22, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v6, v52);
      v8 = BYTE2(xmmword_180107A50);
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
      {
        WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v6, v52);
        v8 = BYTE2(xmmword_180107A50);
      }
      if ( v6 == 6 || !v6 )
        goto LABEL_19;
      if ( (v8 & 2) != 0 )
      {
        v45 = 13;
LABEL_98:
        WPP_SF_qq(529, v45, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, (_DWORD)v5, (__int64)v5);
      }
    }
    v5 = 0;
    v6 = 6;
LABEL_19:
    v56 = v5;
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    {
      WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v6, v52);
      v5 = v56;
    }
    if ( v5 )
    {
      v9 = 0;
      v10 = v3 + 1;
      if ( v3[1].Data1 )
      {
        *(_DWORD *)&v57.Data2 = 0;
        v46 = EtwEventActivityIdControl(2, v3);
        v47 = v46 < 0;
        if ( v46 > 0 )
          v47 = 1;
        if ( v47 )
          *(_DWORD *)&v57.Data2 = 144;
        v5 = v56;
      }
      v11 = (struct _GUID *)(v5 + 184);
      v12 = 16;
      v13 = v3;
      do
      {
        LOBYTE(v13->Data1) = 0;
        v13 = (struct _GUID *)((char *)v13 + 1);
        --v12;
      }
      while ( v12 );
      if ( v3 != (struct _GUID *)-16LL )
        v10->Data1 = 0;
      v14 = 16;
      if ( (a2 & 0x20) != 0 )
        v11 = 0;
      v15 = v3;
      v59 = 0;
      Buf1 = 0;
      do
      {
        LOBYTE(v15->Data1) = 0;
        v15 = (struct _GUID *)((char *)v15 + 1);
        --v14;
      }
      while ( v14 );
      v57 = 0;
      v16 = 16;
      p_Buf1 = &Buf1;
      do
      {
        LOBYTE(p_Buf1->Data1) = 0;
        p_Buf1 = (struct _GUID *)((char *)p_Buf1 + 1);
        --v16;
      }
      while ( v16 );
      v18 = EtwEventActivityIdControl(1, &v57);
      v21 = v18 < 0;
      if ( v18 > 0 )
        v21 = 1;
      if ( v21 )
        *(_DWORD *)&v57.Data2 = 128;
      else
        Buf1 = v57;
      if ( !v11 )
      {
        v22 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
        TickCount = GetTickCount();
        CurrentProcessId = GetCurrentProcessId();
        v59.Data1 = (unsigned int)retaddr;
        v9 = 0;
        *(_DWORD *)&v59.Data2 = v22;
        v3 = (struct _GUID *)a3;
        *(_DWORD *)v59.Data4 = TickCount;
        v11 = &v59;
        *(_DWORD *)&v59.Data4[4] = CurrentProcessId;
      }
      if ( (a2 & 4) != 0 && g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
        EtwEx_tidActivityInfo(v19, &ActivityStart, v11, v20, v52);
      EtwEventActivityIdControl(2, v11);
      if ( (a2 & 8) != 0
        && g_fEtwCorrelationProviderInitialized
        && memcmp_0(&Buf1, &qword_1800E6318, 0x10u)
        && memcmp_0(v11, &qword_1800E6318, 0x10u)
        && Microsoft_Windows_Networking_CorrelationEnabled )
      {
        EtwEx_tidActivityInfoTransfer(v49, v48, v11, &Buf1, v52, v53, v54);
      }
      v25 = (__int64)v56;
      *v3 = Buf1;
      v10->Data1 = 1;
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
        WPP_SF_q(1041, 15, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids);
      IsValid = HANDLE_OBJECT::IsValid(v25, 1684826455);
      if ( !IsValid )
      {
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_q(1032, 23, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
        v28 = *(_QWORD *)(v25 + 32);
        if ( !_InterlockedDecrement((volatile signed __int32 *)(v25 + 44)) )
          v9 = 1;
        if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
          WPP_SF_qqD(1045, 24, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v28, v25);
        if ( v9 )
          (**(void (__fastcall ***)(__int64, __int64, __int64, __int64))v25)(v25, 1, v27, v28);
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_d(1032, 25, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v9, v52);
      }
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
        WPP_SF_d(1041, 16, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, IsValid, v52);
    }
    return;
  }
  v29 = (_DWORD *)((char *)a3 + 16);
  if ( !*((_DWORD *)a3 + 4) )
  {
    v30 = 16;
    v31 = a3;
    do
    {
      *(_BYTE *)v31 = 0;
      v31 = (struct _WINHTTP_ETW_INFO *)((char *)v31 + 1);
      --v30;
    }
    while ( v30 );
    if ( a3 != (struct _WINHTTP_ETW_INFO *)-16LL )
      *v29 = 0;
    Buf1 = 0;
    v32 = a2 & 8;
    v33 = 16;
    v59 = 0;
    v34 = a3;
    do
    {
      *(_BYTE *)v34 = 0;
      v34 = (struct _WINHTTP_ETW_INFO *)((char *)v34 + 1);
      --v33;
    }
    while ( v33 );
    v57 = 0;
    v35 = 16;
    v36 = &v59;
    do
    {
      LOBYTE(v36->Data1) = 0;
      v36 = (struct _GUID *)((char *)v36 + 1);
      --v35;
    }
    while ( v35 );
    v37 = EtwEventActivityIdControl(1, &v57);
    v38 = v37 < 0;
    if ( v37 > 0 )
      v38 = 1;
    if ( v38 )
      *(_DWORD *)&v57.Data2 = 128;
    else
      v59 = v57;
    v39 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    v40 = GetTickCount();
    *(_DWORD *)&Buf1.Data4[4] = GetCurrentProcessId();
    Buf1.Data1 = (unsigned int)retaddr;
    *(_DWORD *)&Buf1.Data2 = v39;
    *(_DWORD *)Buf1.Data4 = v40;
    if ( g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfo(v41, &ActivityStart, &Buf1, v42, v52);
    *(_DWORD *)&v57.Data2 = 0;
    v43 = EtwEventActivityIdControl(2, &Buf1);
    v44 = v43 < 0;
    if ( v43 > 0 )
      v44 = 1;
    if ( v44 )
      *(_DWORD *)&v57.Data2 = 144;
    if ( v32
      && g_fEtwCorrelationProviderInitialized
      && memcmp_0(&v59, &qword_1800E6318, 0x10u)
      && memcmp_0(&Buf1, &qword_1800E6318, 0x10u)
      && Microsoft_Windows_Networking_CorrelationEnabled )
    {
      EtwEx_tidActivityInfoTransfer(v51, v50, &Buf1, &v59, v52, v53, v54);
    }
    *(struct _GUID *)a3 = v59;
    *v29 = 1;
  }
}

```

## disassembly

```asm
0x18003b230  mov     r11, rsp
0x18003b233  push    rbp
0x18003b234  push    rbx
0x18003b235  push    rsi
0x18003b236  push    r12
0x18003b238  push    r15
0x18003b23a  lea     rbp, [r11-5Fh]
0x18003b23e  sub     rsp, 0A0h
0x18003b245  mov     rax, cs:__security_cookie
0x18003b24c  xor     rax, rsp
0x18003b24f  mov     [rbp+57h+var_40], rax
0x18003b253  xor     r12d, r12d
0x18003b256  mov     [rbp+57h+var_80], r8
0x18003b25a  cmp     cs:?WinHttpEtwInitialized@@3EA, r12b; uchar WinHttpEtwInitialized
0x18003b261  mov     rsi, r8
0x18003b264  mov     r15d, edx
0x18003b267  mov     [rbp+57h+var_78], r12
0x18003b26b  mov     rbx, rcx
0x18003b26e  jz      loc_18003B50F
0x18003b274  mov     [r11+10h], rdi
0x18003b278  mov     [r11-38h], r14
0x18003b27c  test    rcx, rcx
0x18003b27f  jz      loc_18003B544
0x18003b285  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003b28c  jnz     loc_18003B85F
0x18003b292  mov     edx, 646C6957h
0x18003b297  mov     rcx, rbx
0x18003b29a  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003b29f  test    eax, eax
0x18003b2a1  jnz     loc_18003B52A
0x18003b2a7  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003b2ae  jnz     loc_18003B6DB
0x18003b2b4  mov     eax, [rbx+30h]
0x18003b2b7  test    eax, eax
0x18003b2b9  jnz     loc_18003B8E7
0x18003b2bf  mov     edi, r12d
0x18003b2c2  mov     eax, [rbx+2Ch]
0x18003b2c5  test    eax, eax
0x18003b2c7  jle     loc_18003B979
0x18003b2cd  lea     ecx, [rax+1]
0x18003b2d0  lock cmpxchg [rbx+2Ch], ecx
0x18003b2d5  jnz     short loc_18003B2C2
0x18003b2d7  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18003b2de  jnz     loc_18003B912
0x18003b2e4  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003b2eb  jnz     loc_18003B6FA
0x18003b2f1  movzx   eax, byte ptr cs:xmmword_180107A50+2
0x18003b2f8  test    al, 2
0x18003b2fa  jnz     loc_18003B8AD
0x18003b300  cmp     edi, 6
0x18003b303  jnz     loc_18003B675
0x18003b309  mov     [rbp+57h+var_78], rbx
0x18003b30d  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003b314  jnz     loc_18003B88B
0x18003b31a  test    rbx, rbx
0x18003b31d  jz      loc_18003B4FF
0x18003b323  mov     [rsp+98h], r13
0x18003b32b  xor     edi, edi
0x18003b32d  cmp     [rsi+10h], r12d
0x18003b331  lea     r13, [rsi+10h]
0x18003b335  jnz     loc_18003B6AD
0x18003b33b  add     rbx, 0B8h
0x18003b342  mov     ecx, 10h
0x18003b347  mov     rax, rsi
0x18003b34a  nop     word ptr [rax+rax+00h]
0x18003b350  mov     [rax], r12b
0x18003b353  lea     rax, [rax+1]
0x18003b357  sub     rcx, 1
0x18003b35b  jnz     short loc_18003B350
0x18003b35d  test    r13, r13
0x18003b360  jz      short loc_18003B366
0x18003b362  mov     [r13+0], edi
0x18003b366  mov     r14d, r15d
0x18003b369  mov     r12d, r15d
0x18003b36c  and     r14d, 4
0x18003b370  and     r12d, 8
0x18003b374  test    r15b, 20h
0x18003b378  xorps   xmm0, xmm0
0x18003b37b  xorps   xmm1, xmm1
0x18003b37e  mov     ecx, 10h
0x18003b383  cmovnz  rbx, rdi
0x18003b387  mov     rax, rsi
0x18003b38a  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x18003b38e  movups  [rbp+57h+Buf1], xmm1
0x18003b392  mov     byte ptr [rax], 0
0x18003b395  lea     rax, [rax+1]
0x18003b399  sub     rcx, 1
0x18003b39d  jnz     short loc_18003B392
0x18003b39f  xorps   xmm0, xmm0
0x18003b3a2  mov     dword ptr [rbp+57h+var_70+4], edi
0x18003b3a5  movups  xmmword ptr [rbp-19h], xmm0
0x18003b3a9  mov     ecx, 10h
0x18003b3ae  lea     rax, [rbp+57h+Buf1]
0x18003b3b2  mov     byte ptr [rax], 0
0x18003b3b5  lea     rax, [rax+1]
0x18003b3b9  sub     rcx, 1
0x18003b3bd  jnz     short loc_18003B3B2
0x18003b3bf  lea     rdx, [rbp+57h+var_70]
0x18003b3c3  mov     ecx, 1
0x18003b3c8  call    cs:__imp_EtwEventActivityIdControl
0x18003b3ce  test    eax, eax
0x18003b3d0  jle     short loc_18003B3DC
0x18003b3d2  movzx   eax, ax
0x18003b3d5  or      eax, 80070000h
0x18003b3da  test    eax, eax
0x18003b3dc  js      loc_18003B906
0x18003b3e2  movaps  xmm0, [rbp+57h+var_70]
0x18003b3e6  movdqa  [rbp+57h+Buf1], xmm0
0x18003b3eb  test    rbx, rbx
0x18003b3ee  jnz     short loc_18003B427
0x18003b3f0  mov     rdi, [rbp+5Fh]
0x18003b3f4  mov     esi, 1
0x18003b3f9  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x18003b401  inc     esi
0x18003b403  call    cs:__imp_GetTickCount
0x18003b409  mov     ebx, eax
0x18003b40b  call    cs:__imp_GetCurrentProcessId
0x18003b411  mov     [rbp+57h+var_50.Data1], edi
0x18003b414  xor     edi, edi
0x18003b416  mov     dword ptr [rbp+57h+var_50.Data2], esi
0x18003b419  mov     rsi, [rbp+57h+var_80]
0x18003b41d  mov     dword ptr [rbp+57h+var_50.Data4], ebx
0x18003b420  lea     rbx, [rbp+57h+var_50]
0x18003b424  mov     dword ptr [rbp+57h+var_50.Data4+4], eax
0x18003b427  test    r14d, r14d
0x18003b42a  jz      short loc_18003B443
0x18003b42c  cmp     cs:?g_fEtwCorrelationProviderInitialized@@3HA, 0; int g_fEtwCorrelationProviderInitialized
0x18003b433  jz      short loc_18003B443
0x18003b435  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18003b43b  test    eax, eax
0x18003b43d  jnz     loc_18003B7A1
0x18003b443  mov     rdx, rbx
0x18003b446  mov     dword ptr [rbp+57h+var_80+4], edi
0x18003b449  mov     ecx, 2
0x18003b44e  call    cs:__imp_EtwEventActivityIdControl
0x18003b454  test    eax, eax
0x18003b456  jle     short loc_18003B462
0x18003b458  movzx   eax, ax
0x18003b45b  or      eax, 80070000h
0x18003b460  test    eax, eax
0x18003b462  js      loc_18003B8FA
0x18003b468  test    r12d, r12d
0x18003b46b  jnz     loc_18003B73A
0x18003b471  movaps  xmm0, [rbp+57h+Buf1]
0x18003b475  mov     rbx, [rbp+57h+var_78]
0x18003b479  movups  xmmword ptr [rsi], xmm0
0x18003b47c  mov     dword ptr [r13+0], 1
0x18003b484  mov     r13, [rsp+98h]
0x18003b48c  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003b493  jnz     loc_18003B7D8
0x18003b499  mov     edx, 646C6957h
0x18003b49e  mov     rcx, rbx
0x18003b4a1  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003b4a6  mov     esi, eax
0x18003b4a8  test    eax, eax
0x18003b4aa  jnz     short loc_18003B4F2
0x18003b4ac  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003b4b3  jnz     loc_18003B983
0x18003b4b9  mov     r9, [rbx+20h]
0x18003b4bd  mov     eax, 0FFFFFFFFh
0x18003b4c2  lock xadd [rbx+2Ch], eax
0x18003b4c7  sub     eax, 1
0x18003b4ca  jz      loc_18003B718
0x18003b4d0  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18003b4d7  jnz     loc_18003B9C0
0x18003b4dd  test    edi, edi
0x18003b4df  jnz     loc_18003B722
0x18003b4e5  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003b4ec  jnz     loc_18003B9A2
0x18003b4f2  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003b4f9  jnz     loc_18003B68F
0x18003b4ff  mov     rdi, [rsp+0C0h+arg_8]
0x18003b507  mov     r14, [rsp+0C0h+var_30]
0x18003b50f  mov     rcx, [rbp+57h+var_40]
0x18003b513  xor     rcx, rsp; StackCookie
0x18003b516  call    __security_check_cookie
0x18003b51b  add     rsp, 0A0h
0x18003b522  pop     r15
0x18003b524  pop     r12
0x18003b526  pop     rsi
0x18003b527  pop     rbx
0x18003b528  pop     rbp
0x18003b529  retn
0x18003b52a  test    byte ptr cs:xmmword_180107A50+2, 2
0x18003b531  jnz     loc_18003B7B5
0x18003b537  mov     rbx, r12
0x18003b53a  mov     edi, 6
0x18003b53f  jmp     loc_18003B309
0x18003b544  cmp     [r8+10h], r12d
0x18003b548  lea     r14, [r8+10h]
0x18003b54c  jnz     short loc_18003B4FF
0x18003b54e  mov     ecx, 10h
0x18003b553  mov     rax, rsi
0x18003b556  nop     word ptr [rax+rax+00000000h]
0x18003b560  mov     [rax], r12b
0x18003b563  lea     rax, [rax+1]
0x18003b567  sub     rcx, 1
0x18003b56b  jnz     short loc_18003B560
0x18003b56d  test    r14, r14
0x18003b570  jz      short loc_18003B575
0x18003b572  mov     [r14], r12d
0x18003b575  xorps   xmm0, xmm0
0x18003b578  xorps   xmm1, xmm1
0x18003b57b  movups  [rbp+57h+Buf1], xmm0
0x18003b57f  and     r15d, 8
0x18003b583  mov     ecx, 10h
0x18003b588  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm1
0x18003b58c  mov     rax, rsi
0x18003b58f  nop
0x18003b590  mov     [rax], r12b
0x18003b593  lea     rax, [rax+1]
0x18003b597  sub     rcx, 1
0x18003b59b  jnz     short loc_18003B590
0x18003b59d  xorps   xmm0, xmm0
0x18003b5a0  mov     dword ptr [rbp+57h+var_70+4], r12d
0x18003b5a4  movups  [rbp+57h+var_70], xmm0
0x18003b5a8  mov     ecx, 10h
0x18003b5ad  lea     rax, [rbp+57h+var_50]
0x18003b5b1  mov     [rax], r12b
0x18003b5b4  lea     rax, [rax+1]
0x18003b5b8  sub     rcx, 1
0x18003b5bc  jnz     short loc_18003B5B1
0x18003b5be  lea     rdx, [rbp+57h+var_70]
0x18003b5c2  mov     ecx, 1
0x18003b5c7  call    cs:__imp_EtwEventActivityIdControl
0x18003b5cd  test    eax, eax
0x18003b5cf  jle     short loc_18003B5DB
0x18003b5d1  movzx   eax, ax
0x18003b5d4  or      eax, 80070000h
0x18003b5d9  test    eax, eax
0x18003b5db  js      loc_18003B9E4
0x18003b5e1  movaps  xmm0, [rbp+57h+var_70]
0x18003b5e5  movdqa  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x18003b5ea  mov     rdi, [rbp+5Fh]
0x18003b5ee  mov     esi, 1
0x18003b5f3  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x18003b5fb  inc     esi
0x18003b5fd  call    cs:__imp_GetTickCount
0x18003b603  mov     ebx, eax
0x18003b605  call    cs:__imp_GetCurrentProcessId
0x18003b60b  cmp     cs:?g_fEtwCorrelationProviderInitialized@@3HA, r12d; int g_fEtwCorrelationProviderInitialized
0x18003b612  mov     dword ptr [rbp+57h+Buf1+0Ch], eax
0x18003b615  mov     dword ptr [rbp+57h+Buf1], edi
0x18003b618  mov     dword ptr [rbp+57h+Buf1+4], esi
0x18003b61b  mov     dword ptr [rbp+57h+Buf1+8], ebx
0x18003b61e  jz      short loc_18003B62E
0x18003b620  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18003b626  test    eax, eax
0x18003b628  jnz     loc_18003B8D2
0x18003b62e  lea     rdx, [rbp+57h+Buf1]
0x18003b632  mov     dword ptr [rbp+57h+var_70+4], r12d
0x18003b636  mov     ecx, 2
0x18003b63b  call    cs:__imp_EtwEventActivityIdControl
0x18003b641  test    eax, eax
0x18003b643  jle     short loc_18003B64F
0x18003b645  movzx   eax, ax
0x18003b648  or      eax, 80070000h
0x18003b64d  test    eax, eax
0x18003b64f  js      loc_18003B949
0x18003b655  test    r15d, r15d
0x18003b658  jnz     loc_18003B7F6
0x18003b65e  mov     rax, [rbp+57h+var_80]
0x18003b662  movaps  xmm0, xmmword ptr [rbp+57h+var_50.Data1]
0x18003b666  movups  xmmword ptr [rax], xmm0
0x18003b669  mov     dword ptr [r14], 1
0x18003b670  jmp     loc_18003B4FF
0x18003b675  test    edi, edi
0x18003b677  jz      loc_18003B309
0x18003b67d  test    al, 2
0x18003b67f  jz      loc_18003B537
0x18003b685  mov     edx, 0Dh
0x18003b68a  jmp     loc_18003B7BA
0x18003b68f  mov     edx, 10h
0x18003b694  lea     r8, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids
0x18003b69b  mov     ecx, 411h
0x18003b6a0  mov     r9d, esi
0x18003b6a3  call    WPP_SF_d
0x18003b6a8  jmp     loc_18003B4FF
0x18003b6ad  mov     rdx, rsi
0x18003b6b0  mov     dword ptr [rbp+57h+var_70+4], edi
0x18003b6b3  mov     ecx, 2
0x18003b6b8  call    cs:__imp_EtwEventActivityIdControl
0x18003b6be  test    eax, eax
0x18003b6c0  jle     short loc_18003B6CC
0x18003b6c2  movzx   eax, ax
0x18003b6c5  or      eax, 80070000h
0x18003b6ca  test    eax, eax
0x18003b6cc  js      loc_18003B93D
0x18003b6d2  mov     rbx, [rbp+57h+var_78]
0x18003b6d6  jmp     loc_18003B33B
0x18003b6db  mov     r9, [rbx+20h]
0x18003b6df  lea     r8, WPP_989094c1a00a31c88345b82a0793d746_Traceguids
0x18003b6e6  mov     edx, 13h
0x18003b6eb  mov     ecx, 408h
0x18003b6f0  call    WPP_SF_q
0x18003b6f5  jmp     loc_18003B2B4
0x18003b6fa  mov     edx, 16h
0x18003b6ff  lea     r8, WPP_989094c1a00a31c88345b82a0793d746_Traceguids
0x18003b706  mov     ecx, 408h
0x18003b70b  mov     r9d, edi
  ... truncated ...
```
