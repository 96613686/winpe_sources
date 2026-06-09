# ProcessChangedDestLists

- ea: `0x180002dd0`
- end: `0x180003726`
- name: `ProcessChangedDestLists`
- size: `2390`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003730`

## callees

- `0x180002cb0`
- `0x180002dd0`
- `0x180009d14`
- `0x18000a1bc`
- `0x18000dc60`
- `0x180014d2c`
- `0x180015178`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180003161`
- `ntdll!RtlReleaseResource` at `0x180003161`
- `ntdll!RtlIpv6AddressToStringA` at `0x180003343`
- `ntdll!RtlIpv6AddressToStringA` at `0x180003343`
- `ntdll!RtlAcquireResourceShared` at `0x180002edd`
- `ntdll!RtlAcquireResourceShared` at `0x180002edd`
- `KERNEL32!EnterCriticalSection` at `0x180002fa4`
- `KERNEL32!EnterCriticalSection` at `0x180003003`
- `KERNEL32!EnterCriticalSection` at `0x18000306e`
- `KERNEL32!EnterCriticalSection` at `0x1800030b5`
- `KERNEL32!EnterCriticalSection` at `0x1800034e6`
- `KERNEL32!EnterCriticalSection` at `0x180002fa4`
- `KERNEL32!EnterCriticalSection` at `0x180003003`
- `KERNEL32!EnterCriticalSection` at `0x18000306e`
- `KERNEL32!EnterCriticalSection` at `0x1800030b5`
- `KERNEL32!EnterCriticalSection` at `0x1800034e6`
- `KERNEL32!LeaveCriticalSection` at `0x180002fca`
- `KERNEL32!LeaveCriticalSection` at `0x18000302d`
- `KERNEL32!LeaveCriticalSection` at `0x1800030a5`
- `KERNEL32!LeaveCriticalSection` at `0x180003154`
- `KERNEL32!LeaveCriticalSection` at `0x18000352b`
- `KERNEL32!LeaveCriticalSection` at `0x180002fca`
- `KERNEL32!LeaveCriticalSection` at `0x18000302d`
- `KERNEL32!LeaveCriticalSection` at `0x1800030a5`
- `KERNEL32!LeaveCriticalSection` at `0x180003154`
- `KERNEL32!LeaveCriticalSection` at `0x18000352b`
- `KERNEL32!GetLastError` at `0x1800030fb`
- `KERNEL32!GetLastError` at `0x1800030fb`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180003095`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180003095`
- `KERNEL32!ChangeTimerQueueTimer` at `0x1800030de`
- `KERNEL32!ChangeTimerQueueTimer` at `0x1800030de`
- `WS2_32!__imp_htonl` at `0x1800033b2`
- `WS2_32!__imp_htonl` at `0x1800033b2`

## string_xrefs

- `0x180003181`: `ProcessChangedDestLists: Dests Removed: %ld`

## pseudocode

```c
void __fastcall ProcessChangedDestLists(char *a1)
{
  unsigned int UniqueThread; // ebx
  struct _SPropValue *v3; // rcx
  __int64 v4; // r13
  __int128 *v5; // r9
  __int64 v6; // r8
  __int128 *v7; // r9
  unsigned int v8; // ecx
  __int64 v9; // rax
  __int64 v10; // rbx
  char *v11; // r12
  char *v12; // rax
  char *v13; // r15
  char **v14; // rdi
  __int64 v15; // r14
  char *v16; // r15
  char *v17; // rax
  unsigned int v18; // edi
  void *v19; // rdx
  DWORD LastError; // eax
  __int128 *v21; // r9
  __int128 *v22; // r9
  __int128 *v23; // r9
  char *v24; // r14
  char v25; // bl
  __int128 *v26; // r9
  __int128 *v27; // r9
  __int16 v28; // ax
  DWORD v29; // r8d
  u_long v30; // eax
  DWORD v31; // ecx
  _QWORD *v32; // rbx
  int v33; // eax
  unsigned int v34; // r13d
  int v35; // edi
  int v36; // edi
  int v37; // ebx
  __int64 v38; // rcx
  int v39; // r8d
  int v40; // r9d
  __int64 v41; // rdx
  int v42; // ebx
  char *v43; // rax
  unsigned int v44; // ecx
  unsigned int v45; // ebx
  __int64 v46; // r13
  __int64 v47; // rdi
  __int128 *v48; // r9
  __int128 *v49; // r9
  __int64 v50; // [rsp+20h] [rbp-E0h]
  __int64 v51; // [rsp+28h] [rbp-D8h]
  __int64 v52; // [rsp+30h] [rbp-D0h]
  __int64 v53; // [rsp+38h] [rbp-C8h]
  __int64 v54; // [rsp+40h] [rbp-C0h]
  __int64 v55; // [rsp+48h] [rbp-B8h]
  unsigned int v56; // [rsp+50h] [rbp-B0h]
  DWORD pLength; // [rsp+54h] [rbp-ACh] BYREF
  ULONG uliInst[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v59; // [rsp+60h] [rbp-A0h]
  int v60; // [rsp+64h] [rbp-9Ch]
  unsigned int v61; // [rsp+68h] [rbp-98h]
  char **v62; // [rsp+70h] [rbp-90h]
  char *v63; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v64; // [rsp+80h] [rbp-80h]
  __int64 v65; // [rsp+88h] [rbp-78h]
  __int64 v66; // [rsp+90h] [rbp-70h]
  char *v67; // [rsp+98h] [rbp-68h]
  __int64 v68; // [rsp+A0h] [rbp-60h]
  __int128 v69; // [rsp+A8h] [rbp-58h] BYREF
  in6_addr pAddress; // [rsp+C0h] [rbp-40h] BYREF
  int v71; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v72; // [rsp+D4h] [rbp-2Ch]
  __int128 v73; // [rsp+E4h] [rbp-1Ch]
  int v74; // [rsp+F4h] [rbp-Ch]
  CHAR S[80]; // [rsp+100h] [rbp+0h] BYREF
  int v76; // [rsp+150h] [rbp+50h] BYREF
  char v77[2044]; // [rsp+154h] [rbp+54h] BYREF

  v63 = 0;
  *(_QWORD *)uliInst = 0;
  pLength = 0;
  v76 = 0;
  memset_0(v77, 0, sizeof(v77));
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v69 = 0;
  UniqueThread = (unsigned int)NtCurrentTeb()->ClientId.UniqueThread;
  v3 = (struct _SPropValue *)*(unsigned __int16 *)(*((_QWORD *)a1 + 2) + 4LL);
  v64 = UniqueThread;
  GetInstance(v3, 0, (ULONG)uliInst);
  if ( (byte_18002BD1A & 8) != 0 )
  {
    LOWORD(v76) = 0;
    LOWORD(v71) = 0;
    FormatRRASErrorString(&v76, L"Entering ProcessChangedDestLists: %lu", UniqueThread);
    v4 = *(_QWORD *)uliInst;
    if ( (byte_18002BD1A & 8) != 0 )
    {
      v5 = &v69;
      if ( *(_QWORD *)uliInst != -48 )
        LODWORD(v5) = uliInst[0] + 48;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
        (unsigned int)&v76,
        (_DWORD)v5,
        0,
        (__int64)&v71);
    }
  }
  else
  {
    v4 = *(_QWORD *)uliInst;
  }
  RtlAcquireResourceShared((PRTL_RESOURCE)(a1 + 744), 1u);
  if ( (byte_18002BD1A & 8) != 0 )
  {
    v6 = *((unsigned int *)a1 + 268);
    LOWORD(v76) = 0;
    LOWORD(v71) = 0;
    FormatRRASErrorString(&v76, L"ProcessChangedDestLists: Number of changed dests: %ld", v6);
    if ( (byte_18002BD1A & 8) != 0 )
    {
      v7 = &v69;
      if ( v4 != -48 )
        LODWORD(v7) = v4 + 48;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
        (unsigned int)&v76,
        (_DWORD)v7,
        0,
        (__int64)&v71);
    }
  }
  v8 = 0;
  v56 = 0;
  v9 = 0;
  v59 = 0;
  v66 = 0;
  v61 = 0;
  while ( 2 )
  {
    v10 = 9 * v9;
    v68 = 9 * v9;
    if ( _InterlockedIncrement((volatile signed __int32 *)&a1[72 * v9 + 1080]) != 1 )
    {
      v15 = *(_QWORD *)uliInst;
      goto LABEL_22;
    }
    v11 = &a1[72 * v9 + 1136];
    v67 = v11;
    EnterCriticalSection((LPCRITICAL_SECTION)&a1[72 * v9 + 1088]);
    v12 = *(char **)v11;
    *(_QWORD *)v11 = v11;
    v63 = v12;
    *(_QWORD *)&a1[8 * v10 + 1144] = v11;
    LeaveCriticalSection((LPCRITICAL_SECTION)&a1[8 * v10 + 1088]);
    v13 = v63;
    v14 = &v63;
    v62 = &v63;
    v60 = 0;
    if ( v63 == v11 )
    {
      v15 = *(_QWORD *)uliInst;
      goto LABEL_17;
    }
    while ( 1 )
    {
      do
      {
        v24 = v13 - 8;
        LOBYTE(v65) = byte_18002BD1A & 8;
        if ( (byte_18002BD1A & 8) == 0 )
          goto LABEL_64;
        LOWORD(v76) = 0;
        LOWORD(v71) = 0;
        FormatRRASErrorString(&v76, L"Adding dest %p to change list %d: ", v13 - 8, v59);
        v25 = byte_18002BD1A;
        if ( (byte_18002BD1A & 8) != 0 )
        {
          v26 = &v69;
          if ( v4 != -48 )
            LODWORD(v26) = v4 + 48;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
            (unsigned int)&v76,
            (_DWORD)v26,
            0,
            (__int64)&v71);
          v25 = byte_18002BD1A;
        }
        if ( *((_WORD *)v24 + 40) == 23 )
        {
          pAddress = 0;
          memset_0(S, 0, 0x41u);
          RtmConvertNetAddressToIpv6AddressAndLength((PRTM_NET_ADDRESS)v24 + 4, &pAddress, &pLength, 0x10u);
          if ( (v25 & 8) != 0 )
          {
            LOWORD(v76) = 0;
            LOWORD(v71) = 0;
            RtlIpv6AddressToStringA(&pAddress, S);
            FormatRRASErrorString(&v76, L"address is %S  mask %d", S, pLength);
            if ( (byte_18002BD1A & 8) != 0 )
            {
              v27 = &v69;
              if ( v4 != -48 )
                LODWORD(v27) = v4 + 48;
LABEL_63:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
                (unsigned int)&v76,
                (_DWORD)v27,
                0,
                (__int64)&v71);
            }
          }
        }
        else
        {
          v28 = *((_WORD *)v24 + 41);
          v29 = *((_DWORD *)v24 + 21);
          pLength = v29;
          if ( v28 )
          {
            v30 = htonl(-1 << (32 - v28));
            v25 = byte_18002BD1A;
            v29 = pLength;
            v31 = v30;
          }
          else
          {
            v31 = 0;
          }
          pLength = v31;
          if ( (v25 & 8) != 0 )
          {
            LOWORD(v76) = 0;
            LOWORD(v71) = 0;
            LODWORD(v55) = HIBYTE(v31);
            LODWORD(v54) = BYTE2(v31);
            LODWORD(v53) = BYTE1(v31);
            LODWORD(v52) = (unsigned __int8)v31;
            LODWORD(v51) = HIBYTE(v29);
            LODWORD(v50) = BYTE2(v29);
            FormatRRASErrorString(
              &v76,
              L"Dest: %d.%d.%d.%d Mask: %d.%d.%d.%d",
              (unsigned __int8)v29,
              BYTE1(v29),
              v50,
              v51,
              v52,
              v53,
              v54,
              v55);
            if ( (byte_18002BD1A & 8) != 0 )
            {
              v27 = &v69;
              if ( v4 != -48 )
                LODWORD(v27) = v4 + 48;
              goto LABEL_63;
            }
          }
        }
LABEL_64:
        v32 = v24 + 32;
        AcquireWriteLock(v24 + 32);
        v33 = *((_DWORD *)v24 + 11) & *((_DWORD *)a1 + 216);
        v34 = 0;
        v35 = ~*((_DWORD *)v24 + 12);
        *((_DWORD *)v24 + 11) = v33;
        v36 = v33 & v35;
        if ( *((_DWORD *)a1 + 211) )
        {
          while ( v36 )
          {
            v37 = 1 << v34;
            if ( ((1 << v34) & v36) != 0 )
            {
              v65 = *(_QWORD *)(*((_QWORD *)a1 + 107) + 8LL * v34);
              *(_QWORD *)pAddress.u.Byte = v65 + 32;
              EnterCriticalSection((LPCRITICAL_SECTION)(v65 + 32));
              v38 = v65;
              HIDWORD(v41) = 0;
              v39 = *(_DWORD *)(v65 + 84);
              v40 = *(_DWORD *)(v65 + 80);
              LODWORD(v41) = (unsigned int)(v39 + 1) % *(_DWORD *)(v65 + 88);
              if ( v40 != (_DWORD)v41 )
              {
                *(_DWORD *)(v65 + 84) = v41;
                *(_QWORD *)(v38 + 8 * v41 + 96) = v24;
                if ( v40 == v39 )
                  v56 |= v37;
                *((_DWORD *)v24 + 12) |= v37;
                v42 = ~v37;
                *((_DWORD *)v24 + 11) &= v42;
                v36 &= v42;
                _InterlockedIncrement((volatile signed __int32 *)v24);
              }
              LeaveCriticalSection(*(LPCRITICAL_SECTION *)pAddress.u.Byte);
            }
            if ( ++v34 >= *((_DWORD *)a1 + 211) )
            {
              v32 = v24 + 32;
              goto LABEL_74;
            }
          }
          v32 = v24 + 32;
        }
        else
        {
LABEL_74:
          if ( v36 )
            goto LABEL_78;
        }
        v43 = *(char **)v13;
        ++v61;
        *v62 = v43;
        *(_QWORD *)v13 = 0;
LABEL_78:
        ReleaseWriteLock(v32);
        if ( v36 )
        {
          v14 = (char **)v13;
          v62 = (char **)v13;
        }
        else
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24, 0xFFFFFFFF) == 1 )
            DestroyDest(v13 - 8);
          v14 = v62;
        }
        v13 = *v14;
        if ( ++v60 == 16 )
          break;
        v4 = *(_QWORD *)uliInst;
      }
      while ( v13 != v11 );
      v44 = v56;
      v45 = 0;
      v15 = *(_QWORD *)uliInst;
      if ( v56 )
      {
        do
        {
          if ( (v44 & 1) != 0 )
          {
            v46 = *(_QWORD *)(*((_QWORD *)a1 + 107) + 8LL * v45);
            v47 = *(_QWORD *)(v46 + 8);
            *(_QWORD *)pAddress.u.Byte = *(_QWORD *)(v47 + 448);
            if ( (byte_18002BD1A & 8) != 0 )
            {
              LOWORD(v76) = 0;
              LOWORD(v71) = 0;
              FormatRRASErrorString(&v76, L"Notifying CN %d BEGIN", v45);
              if ( (byte_18002BD1A & 8) != 0 )
              {
                v48 = &v69;
                if ( v15 != -48 )
                  LODWORD(v48) = v15 + 48;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
                  (unsigned int)&v76,
                  (_DWORD)v48,
                  0,
                  (__int64)&v71);
              }
            }
            (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD))pAddress.u.Byte)(
              v47 ^ 0x7754DF32,
              3,
              v46 ^ 0x7754DF32,
              *(_QWORD *)(v46 + 72));
            if ( (byte_18002BD1A & 8) != 0 )
            {
              LOWORD(v76) = 0;
              LOWORD(v71) = 0;
              FormatRRASErrorString(&v76, L"Notifying CN %d END\n", v45);
              if ( (byte_18002BD1A & 8) != 0 )
              {
                v49 = &v69;
                if ( v15 != -48 )
                  LODWORD(v49) = v15 + 48;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
                  (unsigned int)&v76,
                  (_DWORD)v49,
                  0,
                  (__int64)&v71);
              }
            }
            v44 = v56;
          }
          v44 >>= 1;
          ++v45;
          v56 = v44;
        }
        while ( v44 );
        v11 = v67;
        v14 = v62;
      }
      v60 = 0;
      if ( v13 == v11 )
        break;
      v4 = *(_QWORD *)uliInst;
    }
    v13 = v63;
    v10 = v68;
LABEL_17:
    if ( v13 != v11 )
    {
      v16 = &a1[8 * v10];
      EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 1088));
      v17 = *(char **)v11;
      if ( *(char **)v11 == v11 )
        *(_QWORD *)&a1[8 * v10 + 1144] = v14;
      *v14 = v17;
      *(_QWORD *)v11 = v63;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 1088));
    }
    v8 = v59;
LABEL_22:
    _InterlockedDecrement((volatile signed __int32 *)&a1[8 * v10 + 1080]);
    ++v8;
    v9 = v66 + 1;
    v59 = v8;
    ++v66;
    if ( v8 < 0x10 )
    {
      v4 = *(_QWORD *)uliInst;
      continue;
    }
    break;
  }
  v18 = v61;
  if ( v61 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1016));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 268, -v18) == v18 )
    {
      DeleteTimerQueueTimer(*((HANDLE *)a1 + 92), *((HANDLE *)a1 + 133), 0);
      *((_QWORD *)a1 + 133) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1016));
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1016));
  v19 = (void *)*((_QWORD *)a1 + 133);
  if ( v19 )
  {
    if ( !ChangeTimerQueueTimer(*((HANDLE *)a1 + 92), v19, 0xFAu, 0xF4240u) && (byte_18002BD1A & 0x10) != 0 )
    {
      LOWORD(v76) = 0;
      LOWORD(v71) = 0;
      LastError = GetLastError();
      FormatRRASErrorString(&v76, L"Unable to ChangeTimerQueueTimer. Error: %d", LastError);
      if ( (byte_18002BD1A & 0x10) != 0 )
      {
        v21 = &v69;
        if ( v15 != -48 )
          LODWORD(v21) = v15 + 48;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RRAS_RTM_PARAM_TRACE_ERROR,
          (unsigned int)&v76,
          (_DWORD)v21,
          0,
          (__int64)&v71);
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1016));
  RtlReleaseResource((PRTL_RESOURCE)(a1 + 744));
  if ( (byte_18002BD1A & 8) != 0 )
  {
    LOWORD(v76) = 0;
    LOWORD(v71) = 0;
    FormatRRASErrorString(&v76, L"ProcessChangedDestLists: Dests Removed: %ld", v18);
    if ( (byte_18002BD1A & 8) != 0 )
    {
      v22 = &v69;
      if ( v15 != -48 )
        LODWORD(v22) = v15 + 48;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
        (unsigned int)&v76,
        (_DWORD)v22,
        0,
        (__int64)&v71);
      if ( (byte_18002BD1A & 8) != 0 )
      {
        LOWORD(v76) = 0;
        LOWORD(v71) = 0;
        FormatRRASErrorString(&v76, L"Leaving  ProcessChangedDestLists: %lu", v64);
        if ( (byte_18002BD1A & 8) != 0 )
        {
          v23 = &v69;
          if ( v15 != -48 )
            LODWORD(v23) = v15 + 48;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
            (unsigned int)&v76,
            (_DWORD)v23,
            0,
            (__int64)&v71);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180002dd0  push    rbp
0x180002dd2  push    rbx
0x180002dd3  push    rsi
0x180002dd4  push    rdi
0x180002dd5  push    r12
0x180002dd7  push    r13
0x180002dd9  push    r14
0x180002ddb  push    r15
0x180002ddd  lea     rbp, [rsp-868h]
0x180002de5  sub     rsp, 968h
0x180002dec  mov     rax, cs:__security_cookie
0x180002df3  xor     rax, rsp
0x180002df6  mov     [rbp+8A0h+var_50], rax
0x180002dfd  xor     r15d, r15d
0x180002e00  mov     rsi, rcx
0x180002e03  lea     rcx, [rbp+8A0h+var_84C]; void *
0x180002e07  mov     [rsp+9A0h+var_928], r15
0x180002e0c  xor     edx, edx; Val
0x180002e0e  mov     qword ptr [rsp+9A0h+uliInst], r15
0x180002e13  mov     r8d, 7FCh; Size
0x180002e19  mov     [rsp+9A0h+pLength], r15d
0x180002e1e  mov     [rbp+8A0h+var_850], r15d
0x180002e22  call    memset_0
0x180002e27  xorps   xmm0, xmm0
0x180002e2a  mov     [rbp+8A0h+var_8D0], r15d
0x180002e2e  movups  [rbp+8A0h+var_8CC], xmm0
0x180002e32  xor     eax, eax
0x180002e34  lea     r8, [rsp+9A0h+uliInst]; uliInst
0x180002e39  movups  [rbp+8A0h+var_8BC], xmm0
0x180002e3d  mov     [rbp+8A0h+var_8AC], eax
0x180002e40  xor     edx, edx; lpPropSv
0x180002e42  movups  [rbp+8A0h+var_8F8], xmm0
0x180002e46  mov     rax, gs:30h
0x180002e4f  mov     rcx, [rsi+10h]
0x180002e53  mov     ebx, [rax+48h]
0x180002e56  movzx   ecx, word ptr [rcx+4]; lpPropMv
0x180002e5a  mov     [rbp+8A0h+var_920], ebx
0x180002e5d  call    GetInstance
0x180002e62  mov     r12b, 8
0x180002e65  test    cs:byte_18002BD1A, r12b
0x180002e6c  jz      short loc_180002ECF
0x180002e6e  mov     r8d, ebx
0x180002e71  mov     word ptr [rbp+8A0h+var_850], r15w
0x180002e76  lea     rdx, aEnteringProces; "Entering ProcessChangedDestLists: %lu"
0x180002e7d  mov     word ptr [rbp+8A0h+var_8D0], r15w
0x180002e82  lea     rcx, [rbp+8A0h+var_850]
0x180002e86  call    FormatRRASErrorString
0x180002e8b  test    cs:byte_18002BD1A, r12b
0x180002e92  mov     r13, qword ptr [rsp+9A0h+uliInst]
0x180002e97  jz      short loc_180002ED4
0x180002e99  lea     rax, [r13+30h]
0x180002e9d  test    rax, rax
0x180002ea0  lea     r9, [rbp+8A0h+var_8F8]
0x180002ea4  lea     r8, [rbp+8A0h+var_850]
0x180002ea8  cmovnz  r9, rax
0x180002eac  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x180002eb3  lea     rax, [rbp+8A0h+var_8D0]
0x180002eb7  mov     [rsp+9A0h+var_978], rax
0x180002ebc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002ec3  mov     [rsp+9A0h+var_980], r15
0x180002ec8  call    McTemplateU0zjzz_EventWriteTransfer
0x180002ecd  jmp     short loc_180002ED4
0x180002ecf  mov     r13, qword ptr [rsp+9A0h+uliInst]
0x180002ed4  lea     rcx, [rsi+2E8h]; Resource
0x180002edb  mov     dl, 1; Wait
0x180002edd  call    cs:__imp_RtlAcquireResourceShared
0x180002ee3  test    cs:byte_18002BD1A, r12b
0x180002eea  jz      short loc_180002F4A
0x180002eec  mov     r8d, [rsi+430h]
0x180002ef3  lea     rdx, aProcesschanged_0; "ProcessChangedDestLists: Number of chan"...
0x180002efa  lea     rcx, [rbp+8A0h+var_850]
0x180002efe  mov     word ptr [rbp+8A0h+var_850], r15w
0x180002f03  mov     word ptr [rbp+8A0h+var_8D0], r15w
0x180002f08  call    FormatRRASErrorString
0x180002f0d  test    cs:byte_18002BD1A, r12b
0x180002f14  jz      short loc_180002F4A
0x180002f16  lea     rax, [r13+30h]
0x180002f1a  test    rax, rax
0x180002f1d  lea     r9, [rbp+8A0h+var_8F8]
0x180002f21  lea     r8, [rbp+8A0h+var_850]
0x180002f25  cmovnz  r9, rax
0x180002f29  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x180002f30  lea     rax, [rbp+8A0h+var_8D0]
0x180002f34  mov     [rsp+9A0h+var_978], rax
0x180002f39  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002f40  mov     [rsp+9A0h+var_980], r15
0x180002f45  call    McTemplateU0zjzz_EventWriteTransfer
0x180002f4a  mov     ecx, r15d
0x180002f4d  mov     [rsp+9A0h+var_950], r15d
0x180002f52  mov     rax, r15
0x180002f55  mov     [rsp+9A0h+var_940], ecx
0x180002f59  mov     [rbp+8A0h+var_910], rax
0x180002f5d  mov     [rsp+9A0h+var_938], r15d
0x180002f62  jmp     short loc_180002F69
0x180002f64  mov     r13, qword ptr [rsp+9A0h+uliInst]
0x180002f69  lea     rbx, [rax+rax*8]
0x180002f6d  mov     eax, 1
0x180002f72  mov     [rbp+8A0h+var_900], rbx
0x180002f76  lock xadd [rsi+rbx*8+438h], eax
0x180002f7f  inc     eax
0x180002f81  cmp     eax, 1
0x180002f84  jnz     loc_18000371C
0x180002f8a  lea     r12, [rsi+470h]
0x180002f91  lea     rcx, [rsi+440h]
0x180002f98  lea     r12, [r12+rbx*8]
0x180002f9c  lea     rcx, [rcx+rbx*8]; lpCriticalSection
0x180002fa0  mov     [rbp+8A0h+var_908], r12
0x180002fa4  call    cs:__imp_EnterCriticalSection
0x180002faa  mov     rax, [r12]
0x180002fae  lea     rcx, [rsi+440h]
0x180002fb5  mov     [r12], r12
0x180002fb9  lea     rcx, [rcx+rbx*8]; lpCriticalSection
0x180002fbd  mov     [rsp+9A0h+var_928], rax
0x180002fc2  mov     [rsi+rbx*8+478h], r12
0x180002fca  call    cs:__imp_LeaveCriticalSection
0x180002fd0  mov     r15, [rsp+9A0h+var_928]
0x180002fd5  lea     rdi, [rsp+9A0h+var_928]
0x180002fda  xor     edx, edx
0x180002fdc  mov     [rsp+9A0h+var_930], rdi
0x180002fe1  mov     [rsp+9A0h+var_93C], edx
0x180002fe5  cmp     r15, r12
0x180002fe8  jnz     loc_180003267
0x180002fee  mov     r14, qword ptr [rsp+9A0h+uliInst]
0x180002ff3  cmp     r15, r12
0x180002ff6  jz      short loc_180003033
0x180002ff8  lea     r15, [rsi+rbx*8]
0x180002ffc  lea     rcx, [r15+440h]; lpCriticalSection
0x180003003  call    cs:__imp_EnterCriticalSection
0x180003009  mov     rax, [r12]
0x18000300d  cmp     rax, r12
0x180003010  jnz     short loc_18000301A
0x180003012  mov     [rsi+rbx*8+478h], rdi
0x18000301a  mov     [rdi], rax
0x18000301d  lea     rcx, [r15+440h]; lpCriticalSection
0x180003024  mov     rax, [rsp+9A0h+var_928]
0x180003029  mov     [r12], rax
0x18000302d  call    cs:__imp_LeaveCriticalSection
0x180003033  mov     ecx, [rsp+9A0h+var_940]
0x180003037  lock dec dword ptr [rsi+rbx*8+438h]
0x18000303f  inc     ecx
0x180003041  mov     rax, [rbp+8A0h+var_910]
0x180003045  inc     rax
0x180003048  mov     [rsp+9A0h+var_940], ecx
0x18000304c  mov     [rbp+8A0h+var_910], rax
0x180003050  cmp     ecx, 10h
0x180003053  jb      loc_180002F64
0x180003059  mov     edi, [rsp+9A0h+var_938]
0x18000305d  xor     r15d, r15d
0x180003060  test    edi, edi
0x180003062  jz      short loc_1800030AB
0x180003064  lea     rbx, [rsi+3F8h]
0x18000306b  mov     rcx, rbx; lpCriticalSection
0x18000306e  call    cs:__imp_EnterCriticalSection
0x180003074  mov     eax, edi
0x180003076  neg     eax
0x180003078  lock xadd [rsi+430h], eax
0x180003080  cmp     eax, edi
0x180003082  jnz     short loc_1800030A2
0x180003084  mov     rdx, [rsi+428h]; Timer
0x18000308b  xor     r8d, r8d; CompletionEvent
0x18000308e  mov     rcx, [rsi+2E0h]; TimerQueue
0x180003095  call    cs:__imp_DeleteTimerQueueTimer
0x18000309b  mov     [rsi+428h], r15
0x1800030a2  mov     rcx, rbx; lpCriticalSection
0x1800030a5  call    cs:__imp_LeaveCriticalSection
0x1800030ab  lea     rbx, [rsi+3F8h]
0x1800030b2  mov     rcx, rbx; lpCriticalSection
0x1800030b5  call    cs:__imp_EnterCriticalSection
0x1800030bb  mov     rdx, [rsi+428h]; Timer
0x1800030c2  test    rdx, rdx
0x1800030c5  jz      loc_180003151
0x1800030cb  mov     rcx, [rsi+2E0h]; TimerQueue
0x1800030d2  mov     r9d, 0F4240h; Period
0x1800030d8  mov     r8d, 0FAh; DueTime
0x1800030de  call    cs:__imp_ChangeTimerQueueTimer
0x1800030e4  test    eax, eax
0x1800030e6  jnz     short loc_180003151
0x1800030e8  test    cs:byte_18002BD1A, 10h
0x1800030ef  jz      short loc_180003151
0x1800030f1  mov     word ptr [rbp+8A0h+var_850], r15w
0x1800030f6  mov     word ptr [rbp+8A0h+var_8D0], r15w
0x1800030fb  call    cs:__imp_GetLastError
0x180003101  mov     r8d, eax
0x180003104  lea     rdx, aUnableToChange; "Unable to ChangeTimerQueueTimer. Error:"...
0x18000310b  lea     rcx, [rbp+8A0h+var_850]
0x18000310f  call    FormatRRASErrorString
0x180003114  test    cs:byte_18002BD1A, 10h
0x18000311b  jz      short loc_180003151
0x18000311d  lea     rax, [r14+30h]
0x180003121  test    rax, rax
0x180003124  lea     r9, [rbp+8A0h+var_8F8]
0x180003128  lea     r8, [rbp+8A0h+var_850]
0x18000312c  cmovnz  r9, rax
0x180003130  lea     rdx, RRAS_RTM_PARAM_TRACE_ERROR
0x180003137  lea     rax, [rbp+8A0h+var_8D0]
0x18000313b  mov     [rsp+9A0h+var_978], rax
0x180003140  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003147  mov     [rsp+9A0h+var_980], r15
0x18000314c  call    McTemplateU0zjzz_EventWriteTransfer
0x180003151  mov     rcx, rbx; lpCriticalSection
0x180003154  call    cs:__imp_LeaveCriticalSection
0x18000315a  lea     rcx, [rsi+2E8h]; Resource
0x180003161  call    cs:__imp_RtlReleaseResource
0x180003167  mov     al, cs:byte_18002BD1A
0x18000316d  mov     r12b, 8
0x180003170  test    r12b, al
0x180003173  jz      loc_18000323F
0x180003179  mov     r8d, edi
0x18000317c  mov     word ptr [rbp+8A0h+var_850], r15w
0x180003181  lea     rdx, aProcesschanged; "ProcessChangedDestLists: Dests Removed:"...
0x180003188  mov     word ptr [rbp+8A0h+var_8D0], r15w
0x18000318d  lea     rcx, [rbp+8A0h+var_850]
0x180003191  call    FormatRRASErrorString
0x180003196  mov     al, cs:byte_18002BD1A
0x18000319c  test    r12b, al
0x18000319f  jz      loc_18000323F
0x1800031a5  lea     rax, [r14+30h]
0x1800031a9  test    rax, rax
0x1800031ac  lea     r9, [rbp+8A0h+var_8F8]
0x1800031b0  lea     r8, [rbp+8A0h+var_850]
0x1800031b4  cmovnz  r9, rax
0x1800031b8  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x1800031bf  lea     rax, [rbp+8A0h+var_8D0]
0x1800031c3  mov     [rsp+9A0h+var_978], rax
0x1800031c8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800031cf  mov     [rsp+9A0h+var_980], r15
0x1800031d4  call    McTemplateU0zjzz_EventWriteTransfer
0x1800031d9  mov     al, cs:byte_18002BD1A
0x1800031df  test    r12b, al
0x1800031e2  jz      short loc_18000323F
0x1800031e4  mov     r8d, [rbp+8A0h+var_920]
0x1800031e8  lea     rdx, aLeavingProcess; "Leaving  ProcessChangedDestLists: %lu"
0x1800031ef  lea     rcx, [rbp+8A0h+var_850]
0x1800031f3  mov     word ptr [rbp+8A0h+var_850], r15w
0x1800031f8  mov     word ptr [rbp+8A0h+var_8D0], r15w
0x1800031fd  call    FormatRRASErrorString
0x180003202  test    cs:byte_18002BD1A, r12b
0x180003209  jz      short loc_18000323F
0x18000320b  lea     rax, [r14+30h]
0x18000320f  test    rax, rax
0x180003212  lea     r9, [rbp+8A0h+var_8F8]
0x180003216  lea     r8, [rbp+8A0h+var_850]
0x18000321a  cmovnz  r9, rax
0x18000321e  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x180003225  lea     rax, [rbp+8A0h+var_8D0]
0x180003229  mov     [rsp+9A0h+var_978], rax
0x18000322e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003235  mov     [rsp+9A0h+var_980], r15
0x18000323a  call    McTemplateU0zjzz_EventWriteTransfer
0x18000323f  mov     rcx, [rbp+8A0h+var_50]
0x180003246  xor     rcx, rsp; StackCookie
0x180003249  call    __security_check_cookie
0x18000324e  add     rsp, 968h
0x180003255  pop     r15
0x180003257  pop     r14
0x180003259  pop     r13
0x18000325b  pop     r12
0x18000325d  pop     rdi
0x18000325e  pop     rsi
0x18000325f  pop     rbx
0x180003260  pop     rbp
0x180003261  retn
0x180003262  mov     r13, qword ptr [rsp+9A0h+uliInst]
0x180003267  mov     al, cs:byte_18002BD1A
0x18000326d  lea     r14, [r15-8]
0x180003271  and     al, 8
0x180003273  mov     byte ptr [rbp+8A0h+var_918], al
0x180003276  jz      loc_180003480
0x18000327c  mov     r9d, [rsp+9A0h+var_940]
0x180003281  lea     rcx, [rbp+8A0h+var_850]
0x180003285  mov     word ptr [rbp+8A0h+var_850], dx
0x180003289  mov     eax, edx
0x18000328b  mov     word ptr [rbp+8A0h+var_8D0], dx
0x18000328f  mov     r8, r14
0x180003292  lea     rdx, aAddingDestPToC; "Adding dest %p to change list %d: "
0x180003299  call    FormatRRASErrorString
0x18000329e  mov     bl, cs:byte_18002BD1A
0x1800032a4  test    bl, 8
0x1800032a7  jz      short loc_1800032E5
0x1800032a9  xor     ecx, ecx
0x1800032ab  lea     rax, [r13+30h]
0x1800032af  test    rax, rax
0x1800032b2  lea     r9, [rbp+8A0h+var_8F8]
0x1800032b6  lea     r8, [rbp+8A0h+var_850]
0x1800032ba  cmovnz  r9, rax
0x1800032be  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x1800032c5  lea     rax, [rbp+8A0h+var_8D0]
0x1800032c9  mov     [rsp+9A0h+var_978], rax
0x1800032ce  mov     [rsp+9A0h+var_980], rcx
0x1800032d3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800032da  call    McTemplateU0zjzz_EventWriteTransfer
0x1800032df  mov     bl, cs:byte_18002BD1A
0x1800032e5  cmp     word ptr [r14+50h], 17h
0x1800032eb  jnz     loc_180003391
0x1800032f1  xor     edx, edx; Val
0x1800032f3  lea     rcx, [rbp+8A0h+S]; void *
0x1800032f7  xorps   xmm0, xmm0
0x1800032fa  movups  xmmword ptr [rbp+8A0h+pAddress.u], xmm0
0x1800032fe  lea     r8d, [rdx+41h]; Size
0x180003302  call    memset_0
  ... truncated ...
```
