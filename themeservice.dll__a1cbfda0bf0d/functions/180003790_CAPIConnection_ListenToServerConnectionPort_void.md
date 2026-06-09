# CAPIConnection::ListenToServerConnectionPort(void)

- ea: `0x180003790`
- end: `0x180003e14`
- name: `?ListenToServerConnectionPort@CAPIConnection@@AEAAJXZ`
- size: `1668`
- prototype: `__int64 __fastcall(CAPIConnection *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800035e0`

## callees

- `0x180003790`
- `0x180003e1c`
- `0x180003f90`
- `0x180003fd0`
- `0x180004084`
- `0x1800040e0`
- `0x180004130`
- `0x180004a1c`
- `0x180006600`
- `0x1800067e0`
- `0x18000f9ce`
- `0x18000fa00`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003dd4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003dd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003954`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003cab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003954`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003cab`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003ca2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003ca2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000393d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000397b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000393d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000397b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d98`
- `ntdll!NtAlpcAcceptConnectPort` at `0x180003ab5`
- `ntdll!NtAlpcAcceptConnectPort` at `0x180003c40`
- `ntdll!NtAlpcAcceptConnectPort` at `0x180003ab5`
- `ntdll!NtAlpcAcceptConnectPort` at `0x180003c40`
- `ntdll!NtAlpcCancelMessage` at `0x180003d09`
- `ntdll!NtAlpcCancelMessage` at `0x180003d09`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000382f`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000382f`

## pseudocode

```c
__int64 __fastcall CAPIConnection::ListenToServerConnectionPort(CAPIConnection *this)
{
  __int64 v2; // rcx
  __int64 result; // rax
  __int64 v4; // r8
  unsigned int v5; // r14d
  __int64 v6; // rsi
  int v7; // eax
  __int64 v8; // r14
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // r9d
  int v13; // edx
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // r11
  __int64 v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // rax
  volatile signed __int32 *v20; // rbx
  int v21; // r15d
  int *v22; // rsi
  __int64 v23; // rcx
  int v24; // r10d
  int v25; // r12d
  __int64 v26; // r8
  __int64 v27; // r9
  void (__fastcall **v28)(__int64, __int64); // rax
  __int64 v29; // rcx
  __int64 v30; // r8
  void (__fastcall **v31)(__int64, __int64); // rax
  __int64 v32; // r8
  __int64 i; // r15
  struct _RTL_CRITICAL_SECTION *v34; // rdi
  HANDLE LockSemaphore; // rcx
  __int64 v36; // r13
  CAPIDispatcher *v37; // r13
  int v38; // ebx
  __int64 v39; // rcx
  void *v40; // rcx
  int v41; // [rsp+40h] [rbp-C0h]
  unsigned int ClientSessionID; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A0h] BYREF
  int v45; // [rsp+68h] [rbp-98h] BYREF
  CAPIDispatcher *v46[2]; // [rsp+6Ch] [rbp-94h] BYREF
  __int128 v47; // [rsp+7Ch] [rbp-84h]
  int v48; // [rsp+8Ch] [rbp-74h]
  void **v49; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v50[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v51; // [rsp+B8h] [rbp-48h]
  __int128 v52; // [rsp+C8h] [rbp-38h]
  __int128 v53; // [rsp+D8h] [rbp-28h]
  __int128 v54; // [rsp+E8h] [rbp-18h]
  __int128 v55; // [rsp+F8h] [rbp-8h]
  _QWORD v56[2]; // [rsp+110h] [rbp+10h] BYREF
  char v57[16]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v58; // [rsp+130h] [rbp+30h]
  __int64 v59; // [rsp+138h] [rbp+38h]
  unsigned int *p_ClientSessionID; // [rsp+140h] [rbp+40h]
  __int64 v61; // [rsp+148h] [rbp+48h]
  __int64 *v62; // [rsp+150h] [rbp+50h]
  __int64 v63; // [rsp+158h] [rbp+58h]

  v45 = 0x20000000;
  v44 = 112;
  v49 = &CPortMessage::`vftable';
  v2 = *((_QWORD *)this + 4);
  v48 = 0;
  memset(v50, 0, sizeof(v50));
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  result = NtAlpcSendWaitReceivePort(v2, 0, 0, 0, v50, &v44, &v45, 0);
  v5 = result;
  if ( (int)result < 0 )
    return result;
  v6 = 0;
  if ( ((__int64)v46[0] & 0x20000000) != 0 )
    v6 = *(__int64 *)((char *)v46 + 4);
  if ( BYTE4(v50[0]) == 1 )
  {
    v7 = DWORD2(v51);
    v8 = DWORD2(v51);
    if ( (Microsoft_Windows_UxThemeEnableBits & 1) != 0 )
    {
      McGenEventWrite_EventWriteTransfer(BYTE4(v50[0]), ShellTraceId_ThemeService_HandleServerRequest_Start, v4, 1, v56);
      v7 = DWORD2(v51);
    }
    if ( (v8 & 0xFF0000) != 0 )
    {
      if ( (v7 & 0xFF0000) == 0x10000 )
      {
        v38 = DWORD2(v50[0]);
        if ( v38 == GetCurrentProcessId() )
        {
          *((_BYTE *)this + 20) = 1;
          CAPIDispatcher::RejectRequest((CAPIDispatcher *)v6, (const struct CPortMessage *)&v49, 0);
          v39 = *((_QWORD *)this + 5);
          if ( v39 && (v40 = *(void **)(v39 + 56)) != 0 && (v11 = 258, WaitForSingleObject(v40, 0xEA60u) == 258) )
          {
            *((_BYTE *)this + 20) = 0;
          }
          else
          {
            if ( *((int *)this + 12) >= 0 )
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
            v11 = 0;
            for ( i = (unsigned int)(*((_DWORD *)this + 24) - 1); (int)i >= 0; i = (unsigned int)(i - 1) )
            {
              v36 = *((_QWORD *)this + 13);
              if ( v36 )
              {
                if ( (unsigned int)i < *((_DWORD *)this + 24) )
                {
                  v37 = *(CAPIDispatcher **)(v36 + 8 * i);
                  if ( v37 )
                  {
                    CAPIDispatcher::CloseConnection(v37);
                    CCountedObject::Release(v37);
                  }
                }
              }
              CDynamicPointerArrayBase<CCountedObject,CTOwnershipPolicy_CountedObject<CCountedObject>>::Remove(
                (char *)this + 96,
                (unsigned int)i,
                v32);
            }
            if ( *((int *)this + 12) >= 0 )
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
            v34 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 5);
            if ( v34 )
            {
              EnterCriticalSection(v34);
              LockSemaphore = v34[1].LockSemaphore;
              if ( LockSemaphore )
                SetEvent(LockSemaphore);
              LeaveCriticalSection(v34);
            }
          }
        }
        else
        {
          v11 = -1073741790;
          CAPIDispatcher::RejectRequest((CAPIDispatcher *)v6, (const struct CPortMessage *)&v49, -1073741790);
        }
        goto LABEL_13;
      }
    }
    else
    {
      v9 = v7 & 0xFF000000;
      if ( !v9 )
      {
        v10 = CAPIDispatcher::QueueRequest(
                (CAPIDispatcher *)v6,
                (const struct CPortMessage *)&v49,
                *((LPCRITICAL_SECTION *)this + 5));
LABEL_12:
        v11 = v10;
LABEL_13:
        if ( (Microsoft_Windows_UxThemeEnableBits & 1) != 0 )
        {
          LODWORD(v43) = v11;
          ClientSessionID = CAPIDispatcher::GetClientSessionID((CAPIDispatcher *)v6);
          v56[0] = v8;
          v58 = v56;
          v59 = 8;
          p_ClientSessionID = &ClientSessionID;
          v62 = &v43;
          v61 = 4;
          v63 = 4;
          McGenEventWrite_EventWriteTransfer(v29, ShellTraceId_ThemeService_HandleServerRequest_Stop, v30, 4, v57);
        }
        return v11;
      }
      if ( v9 == 0x80000000 )
      {
        if ( *(_BYTE *)(v6 + 113) )
          v10 = CAPIDispatcher::RejectRequest((CAPIDispatcher *)v6, (const struct CPortMessage *)&v49, -1073741769);
        else
          v10 = (*(__int64 (__fastcall **)(__int64, void ***))(*(_QWORD *)v6 + 24LL))(v6, &v49);
        goto LABEL_12;
      }
    }
    v11 = -1073741822;
    CAPIDispatcher::RejectRequest((CAPIDispatcher *)v6, (const struct CPortMessage *)&v49, -1073741822);
    goto LABEL_13;
  }
  if ( BYTE4(v50[0]) != 5 )
  {
    if ( BYTE4(v50[0]) != 10 )
    {
      if ( (WORD2(v50[0]) & 0x2000) != 0 )
      {
        NtAlpcCancelMessage(*((_QWORD *)this + 4), 0, (char *)v46 + 4);
        return v5;
      }
      return result;
    }
    if ( (Microsoft_Windows_UxThemeEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        BYTE4(v50[0]),
        ShellTraceId_ThemeService_HandleServerConnectionRequest_Start,
        v4,
        1,
        v56);
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, void ***))(**((_QWORD **)this + 3) + 32LL))(
           *((_QWORD *)this + 3),
           &v49) )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD, void ***))(**((_QWORD **)this + 3) + 40LL))(*((_QWORD *)this + 3), &v49);
      v20 = (volatile signed __int32 *)v19;
      if ( !v19 )
      {
LABEL_48:
        v21 = 0;
        v22 = (int *)((char *)this + 96);
        goto LABEL_49;
      }
      v22 = (int *)((char *)this + 96);
      v43 = v19;
      if ( (int)CDynamicArray<_ACCESS_ALLOWED_ACE *>::Add((char *)this + 96, &v43) >= 0 )
      {
        _InterlockedIncrement(v20 + 2);
        v21 = NtAlpcAcceptConnectPort(v20 + 26, *((_QWORD *)this + 4), 0, 0, 0, v20, v50, 0, 1);
        if ( v21 >= 0 )
        {
LABEL_59:
          if ( (Microsoft_Windows_UxThemeEnableBits & 1) != 0 )
            McTemplateU0t_EventWriteTransfer(
              v23,
              ShellTraceId_ThemeService_HandleServerConnectionRequest_Stop,
              (unsigned int)v21);
          return v5;
        }
LABEL_49:
        LOBYTE(v41) = 0;
        NtAlpcAcceptConnectPort(0, *((_QWORD *)this + 4), 0, 0, 0, 0, v50, 0, v41);
        if ( v20 )
        {
          v24 = *v22;
          v25 = -1;
          LODWORD(v26) = 0;
          while ( (int)v26 < v24 )
          {
            v27 = *((_QWORD *)this + 13);
            if ( v27 && (unsigned int)v26 < v24 && v20 == *(volatile signed __int32 **)(v27 + 8LL * (unsigned int)v26) )
              v25 = v26;
            v26 = (unsigned int)(v26 + 1);
            if ( v25 >= 0 )
            {
              CDynamicPointerArrayBase<CCountedObject,CTOwnershipPolicy_CountedObject<CCountedObject>>::Remove(
                v22,
                (unsigned int)v25,
                v26);
              break;
            }
          }
          CAPIDispatcher::CloseConnection((CAPIDispatcher *)v20);
          CCountedObject::Release((CCountedObject *)v20);
        }
        goto LABEL_59;
      }
      CCountedObject::Release((CCountedObject *)v20);
    }
    v20 = 0;
    goto LABEL_48;
  }
  if ( v6 )
  {
    if ( *(int *)(v6 + 120) >= 0 )
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 128));
    *(_BYTE *)(v6 + 113) = 1;
    if ( *(int *)(v6 + 120) >= 0 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 128));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 8), 0xFFFFFFFF) == 1 )
    {
      v28 = *(void (__fastcall ***)(__int64, __int64))v6;
      *(_BYTE *)(v6 + 12) = 1;
      (*v28)(v6, 1);
    }
    if ( *((int *)this + 12) >= 0 )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    v12 = *((_DWORD *)this + 24);
    v13 = -1;
    v14 = 0;
    while ( (int)v14 < (int)v12 )
    {
      v15 = *((_QWORD *)this + 13);
      if ( v15 && v14 < v12 && v6 == *(_QWORD *)(v15 + 8LL * v14) )
        v13 = v14;
      ++v14;
      if ( v13 >= 0 )
      {
        if ( v15 && v13 < v12 )
        {
          _mm_lfence();
          v16 = 8LL * (unsigned int)v13;
          v17 = *(_QWORD *)(v16 + *((_QWORD *)this + 13));
          v18 = 8 * (v12 + ~v13);
          if ( v18 )
            memmove_0(
              (void *)(v16 + *((_QWORD *)this + 13)),
              (const void *)(*((_QWORD *)this + 13) + 8LL * (unsigned int)(v13 + 1)),
              v18);
          *(_QWORD *)(*((_QWORD *)this + 13) + 8LL * (unsigned int)--*((_DWORD *)this + 24)) = 0;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 + 8), 0xFFFFFFFF) == 1 )
          {
            v31 = *(void (__fastcall ***)(__int64, __int64))v17;
            *(_BYTE *)(v17 + 12) = 1;
            (*v31)(v17, 1);
          }
        }
        break;
      }
    }
    if ( *((int *)this + 12) >= 0 )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  }
  return 0;
}

```

## disassembly

```asm
0x180003790  push    rbp
0x180003792  push    rdi
0x180003793  push    r13
0x180003795  push    r14
0x180003797  lea     rbp, [rsp-78h]
0x18000379c  sub     rsp, 178h
0x1800037a3  mov     rax, cs:__security_cookie
0x1800037aa  xor     rax, rsp
0x1800037ad  mov     [rbp+90h+var_30], rax
0x1800037b1  xorps   xmm0, xmm0
0x1800037b4  mov     [rsp+190h+var_128], 20000000h
0x1800037bc  lea     rax, ??_7CPortMessage@@6B@; const CPortMessage::`vftable'
0x1800037c3  mov     [rsp+190h+var_130], 70h ; 'p'
0x1800037cc  mov     [rbp+90h+var_100], rax
0x1800037d0  mov     rdi, rcx
0x1800037d3  mov     rcx, [rcx+20h]
0x1800037d7  xor     eax, eax
0x1800037d9  mov     [rbp+90h+var_104], eax
0x1800037dc  xor     r13d, r13d
0x1800037df  mov     [rsp+190h+var_158], r13
0x1800037e4  lea     rax, [rsp+190h+var_128]
0x1800037e9  mov     [rsp+190h+var_160], rax
0x1800037ee  xor     r9d, r9d
0x1800037f1  lea     rax, [rsp+190h+var_130]
0x1800037f6  xor     r8d, r8d
0x1800037f9  mov     [rsp+190h+var_168], rax
0x1800037fe  xor     edx, edx
0x180003800  lea     rax, [rbp+90h+var_F8]
0x180003804  mov     [rsp+190h+var_170], rax
0x180003809  movups  [rbp+90h+var_F8], xmm0
0x18000380d  movups  [rbp+90h+var_E8], xmm0
0x180003811  movups  [rbp+90h+var_D8], xmm0
0x180003815  movups  [rbp+90h+var_C8], xmm0
0x180003819  movups  [rbp+90h+var_B8], xmm0
0x18000381d  movups  [rbp+90h+var_A8], xmm0
0x180003821  movups  [rbp+90h+var_98], xmm0
0x180003825  movups  xmmword ptr [rsp+190h+var_124], xmm0
0x18000382a  movups  [rsp+190h+var_114], xmm0
0x18000382f  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180003835  mov     r14d, eax
0x180003838  test    eax, eax
0x18000383a  js      loc_180003904
0x180003840  test    dword ptr [rsp+190h+var_124], 20000000h
0x180003848  movzx   edx, word ptr [rbp+90h+var_F8+4]
0x18000384c  mov     [rsp+190h+arg_10], rsi
0x180003854  mov     esi, r13d
0x180003857  cmovnz  rsi, [rsp+190h+var_124+4]
0x18000385d  mov     [rsp+190h+arg_8], rbx
0x180003865  movzx   ecx, dl
0x180003868  mov     [rsp+190h+arg_18], r12
0x180003870  mov     [rsp+190h+var_20], r15
0x180003878  cmp     ecx, 1
0x18000387b  jnz     loc_18000391E
0x180003881  test    byte ptr cs:Microsoft_Windows_UxThemeEnableBits, cl
0x180003887  mov     rax, qword ptr [rbp+90h+var_D8+8]
0x18000388b  mov     r14d, eax
0x18000388e  jnz     loc_180003D4B
0x180003894  test    r14d, 0FF0000h
0x18000389b  jnz     loc_180003D6F
0x1800038a1  lea     rdx, [rbp+90h+var_100]; struct CPortMessage *
0x1800038a5  mov     rcx, rsi; this
0x1800038a8  and     eax, 0FF000000h
0x1800038ad  jz      loc_180003B37
0x1800038b3  cmp     eax, 80000000h
0x1800038b8  jnz     loc_180003E02
0x1800038be  cmp     [rsi+71h], r13b
0x1800038c2  jz      loc_180003B26
0x1800038c8  mov     r8d, 0C0000037h; int
0x1800038ce  call    ?RejectRequest@CAPIDispatcher@@QEBAJAEBVCPortMessage@@J@Z; CAPIDispatcher::RejectRequest(CPortMessage const &,long)
0x1800038d3  mov     ebx, eax
0x1800038d5  test    byte ptr cs:Microsoft_Windows_UxThemeEnableBits, 1
0x1800038dc  jnz     loc_180003B8F
0x1800038e2  mov     eax, ebx
0x1800038e4  mov     r12, [rsp+190h+arg_18]
0x1800038ec  mov     rbx, [rsp+190h+arg_8]
0x1800038f4  mov     r15, [rsp+190h+var_20]
0x1800038fc  mov     rsi, [rsp+190h+arg_10]
0x180003904  mov     rcx, [rbp+90h+var_30]
0x180003908  xor     rcx, rsp; StackCookie
0x18000390b  call    __security_check_cookie
0x180003910  add     rsp, 178h
0x180003917  pop     r14
0x180003919  pop     r13
0x18000391b  pop     rdi
0x18000391c  pop     rbp
0x18000391d  retn
0x18000391e  cmp     ecx, 5
0x180003921  jnz     loc_180003A33
0x180003927  test    rsi, rsi
0x18000392a  jz      loc_180003A2B
0x180003930  cmp     [rsi+78h], r13d
0x180003934  jl      short loc_180003943
0x180003936  lea     rcx, [rsi+80h]; lpCriticalSection
0x18000393d  call    cs:__imp_EnterCriticalSection
0x180003943  mov     byte ptr [rsi+71h], 1
0x180003947  cmp     [rsi+78h], r13d
0x18000394b  jl      short loc_18000395A
0x18000394d  lea     rcx, [rsi+80h]; lpCriticalSection
0x180003954  call    cs:__imp_LeaveCriticalSection
0x18000395a  mov     r12d, 0FFFFFFFFh
0x180003960  mov     eax, r12d
0x180003963  lock xadd [rsi+8], eax
0x180003968  cmp     eax, 1
0x18000396b  jz      loc_180003B73
0x180003971  cmp     [rdi+30h], r13d
0x180003975  jl      short loc_180003981
0x180003977  lea     rcx, [rdi+38h]; lpCriticalSection
0x18000397b  call    cs:__imp_EnterCriticalSection
0x180003981  mov     r9d, [rdi+60h]
0x180003985  mov     edx, r12d
0x180003988  mov     eax, r13d
0x18000398b  nop     dword ptr [rax+rax+00h]
0x180003990  cmp     eax, r9d
0x180003993  jge     loc_180003A1B
0x180003999  mov     r8, [rdi+68h]
0x18000399d  test    r8, r8
0x1800039a0  jz      short loc_1800039B0
0x1800039a2  cmp     eax, r9d
0x1800039a5  jnb     short loc_1800039B0
0x1800039a7  mov     ecx, eax
0x1800039a9  cmp     rsi, [r8+rcx*8]
0x1800039ad  cmovz   edx, eax
0x1800039b0  inc     eax
0x1800039b2  test    edx, edx
0x1800039b4  js      short loc_180003990
0x1800039b6  mov     r10, r8
0x1800039b9  test    r8, r8
0x1800039bc  jz      short loc_180003A1B
0x1800039be  cmp     edx, r9d
0x1800039c1  jnb     short loc_180003A1B
0x1800039c3  lfence
0x1800039c6  mov     eax, edx
0x1800039c8  lea     r11, ds:0[rax*8]
0x1800039d0  mov     rax, [rdi+68h]
0x1800039d4  mov     rbx, [r11+rax]
0x1800039d8  mov     eax, edx
0x1800039da  not     eax
0x1800039dc  add     eax, r9d
0x1800039df  shl     eax, 3
0x1800039e2  test    eax, eax
0x1800039e4  jz      short loc_1800039F9
0x1800039e6  mov     r8d, eax; Size
0x1800039e9  lea     rcx, [r11+r10]; void *
0x1800039ed  lea     eax, [rdx+1]
0x1800039f0  lea     rdx, [r10+rax*8]; Src
0x1800039f4  call    memmove_0
0x1800039f9  mov     ecx, [rdi+60h]
0x1800039fc  xor     edx, edx
0x1800039fe  mov     rax, [rdi+68h]
0x180003a02  dec     ecx
0x180003a04  mov     [rax+rcx*8], rdx
0x180003a08  dec     dword ptr [rdi+60h]
0x180003a0b  lock xadd [rbx+8], r12d
0x180003a11  cmp     r12d, 1
0x180003a15  jz      loc_180003BF5
0x180003a1b  cmp     [rdi+30h], r13d
0x180003a1f  jl      short loc_180003A2B
0x180003a21  lea     rcx, [rdi+38h]; lpCriticalSection
0x180003a25  call    cs:__imp_LeaveCriticalSection
0x180003a2b  mov     eax, r13d
0x180003a2e  jmp     loc_1800038E4
0x180003a33  cmp     ecx, 0Ah
0x180003a36  jnz     loc_180003CF3
0x180003a3c  test    byte ptr cs:Microsoft_Windows_UxThemeEnableBits, 1
0x180003a43  jnz     loc_180003D17
0x180003a49  mov     rcx, [rdi+18h]
0x180003a4d  lea     rdx, [rbp+90h+var_100]
0x180003a51  mov     rax, [rcx]
0x180003a54  mov     rax, [rax+20h]
0x180003a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a5d  test    al, al
0x180003a5f  jz      loc_180003B6B
0x180003a65  mov     rcx, [rdi+18h]
0x180003a69  lea     rdx, [rbp+90h+var_100]
0x180003a6d  mov     rax, [rcx]
0x180003a70  mov     rax, [rax+28h]
0x180003a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a79  mov     rbx, rax
0x180003a7c  test    rax, rax
0x180003a7f  jnz     loc_180003B45
0x180003a85  mov     r15d, r13d
0x180003a88  lea     rsi, [rdi+60h]
0x180003a8c  mov     rdx, [rdi+20h]
0x180003a90  lea     rax, [rbp+90h+var_F8]
0x180003a94  mov     byte ptr [rsp+190h+var_150], r13b
0x180003a99  xor     r9d, r9d
0x180003a9c  mov     [rsp+190h+var_158], r13
0x180003aa1  xor     r8d, r8d
0x180003aa4  mov     [rsp+190h+var_160], rax
0x180003aa9  xor     ecx, ecx
0x180003aab  mov     [rsp+190h+var_168], r13
0x180003ab0  mov     [rsp+190h+var_170], r13
0x180003ab5  call    cs:__imp_NtAlpcAcceptConnectPort
0x180003abb  test    rbx, rbx
0x180003abe  jz      short loc_180003B11
0x180003ac0  mov     r10d, [rsi]
0x180003ac3  mov     r12d, 0FFFFFFFFh
0x180003ac9  mov     r8d, r13d
0x180003acc  nop     dword ptr [rax+00h]
0x180003ad0  cmp     r8d, r10d
0x180003ad3  jge     short loc_180003B01
0x180003ad5  mov     r9, [rdi+68h]
0x180003ad9  test    r9, r9
0x180003adc  jz      short loc_180003AEE
0x180003ade  cmp     r8d, r10d
0x180003ae1  jnb     short loc_180003AEE
0x180003ae3  mov     eax, r8d
0x180003ae6  cmp     rbx, [r9+rax*8]
0x180003aea  cmovz   r12d, r8d
0x180003aee  inc     r8d
0x180003af1  test    r12d, r12d
0x180003af4  js      short loc_180003AD0
0x180003af6  mov     edx, r12d
0x180003af9  mov     rcx, rsi
0x180003afc  call    ?Remove@?$CDynamicPointerArrayBase@VCCountedObject@@V?$CTOwnershipPolicy_CountedObject@VCCountedObject@@@@@@QEAAJI@Z; CDynamicPointerArrayBase<CCountedObject,CTOwnershipPolicy_CountedObject<CCountedObject>>::Remove(uint)
0x180003b01  mov     rcx, rbx; this
0x180003b04  call    ?CloseConnection@CAPIDispatcher@@QEAAJXZ; CAPIDispatcher::CloseConnection(void)
0x180003b09  mov     rcx, rbx; this
0x180003b0c  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180003b11  test    byte ptr cs:Microsoft_Windows_UxThemeEnableBits, 1
0x180003b18  jnz     loc_180003D37
0x180003b1e  mov     eax, r14d
0x180003b21  jmp     loc_1800038E4
0x180003b26  mov     rax, [rsi]
0x180003b29  mov     rax, [rax+18h]
0x180003b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b32  jmp     loc_1800038D3
0x180003b37  mov     r8, [rdi+28h]; lpCriticalSection
0x180003b3b  call    ?QueueRequest@CAPIDispatcher@@QEAAJAEBVCPortMessage@@PEAVCAPIDispatchSync@@@Z; CAPIDispatcher::QueueRequest(CPortMessage const &,CAPIDispatchSync *)
0x180003b40  jmp     loc_1800038D3
0x180003b45  lea     rsi, [rdi+60h]
0x180003b49  mov     [rsp+190h+var_138], rbx
0x180003b4e  mov     rcx, rsi
0x180003b51  lea     rdx, [rsp+190h+var_138]
0x180003b56  call    ?Add@?$CDynamicArray@PEAU_ACCESS_ALLOWED_ACE@@@@QEAAJAEBQEAU_ACCESS_ALLOWED_ACE@@@Z; CDynamicArray<_ACCESS_ALLOWED_ACE *>::Add(_ACCESS_ALLOWED_ACE * const &)
0x180003b5b  test    eax, eax
0x180003b5d  jns     loc_180003C11
0x180003b63  mov     rcx, rbx; this
0x180003b66  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180003b6b  mov     rbx, r13
0x180003b6e  jmp     loc_180003A85
0x180003b73  mov     rax, [rsi]
0x180003b76  mov     edx, 1
0x180003b7b  mov     rcx, rsi
0x180003b7e  mov     byte ptr [rsi+0Ch], 1
0x180003b82  mov     rax, [rax]
0x180003b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b8a  jmp     loc_180003971
0x180003b8f  mov     rcx, rsi; this
0x180003b92  mov     dword ptr [rsp+190h+var_138], ebx
0x180003b96  call    ?GetClientSessionID@CAPIDispatcher@@QEBAKXZ; CAPIDispatcher::GetClientSessionID(void)
0x180003b9b  mov     [rsp+190h+var_140], eax
0x180003b9f  lea     rdx, ShellTraceId_ThemeService_HandleServerRequest_Stop
0x180003ba6  lea     rax, [rbp+90h+var_80]
0x180003baa  mov     [rbp+90h+var_80], r14
0x180003bae  mov     [rbp+90h+var_60], rax
0x180003bb2  mov     r9d, 4
0x180003bb8  lea     rax, [rsp+190h+var_140]
0x180003bbd  mov     [rbp+90h+var_58], 8
0x180003bc5  mov     [rbp+90h+var_50], rax
0x180003bc9  lea     rax, [rsp+190h+var_138]
0x180003bce  mov     [rbp+90h+var_40], rax
0x180003bd2  lea     rax, [rbp+90h+var_70]
0x180003bd6  mov     [rsp+190h+var_170], rax
0x180003bdb  mov     [rbp+90h+var_48], 4
0x180003be3  mov     [rbp+90h+var_38], 4
0x180003beb  call    McGenEventWrite_EventWriteTransfer
0x180003bf0  jmp     loc_1800038E2
0x180003bf5  mov     rax, [rbx]
0x180003bf8  mov     edx, 1
0x180003bfd  mov     rcx, rbx
0x180003c00  mov     byte ptr [rbx+0Ch], 1
0x180003c04  mov     rax, [rax]
0x180003c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c0c  jmp     loc_180003A1B
0x180003c11  lock inc dword ptr [rbx+8]
0x180003c15  mov     rdx, [rdi+20h]
0x180003c19  lea     rax, [rbp+90h+var_F8]
0x180003c1d  mov     byte ptr [rsp+190h+var_150], 1
0x180003c22  lea     rcx, [rbx+68h]
0x180003c26  mov     [rsp+190h+var_158], r13
0x180003c2b  xor     r9d, r9d
0x180003c2e  mov     [rsp+190h+var_160], rax
0x180003c33  xor     r8d, r8d
0x180003c36  mov     [rsp+190h+var_168], rbx
0x180003c3b  mov     [rsp+190h+var_170], r13
0x180003c40  call    cs:__imp_NtAlpcAcceptConnectPort
0x180003c46  mov     r15d, eax
0x180003c49  test    eax, eax
0x180003c4b  jns     loc_180003B11
0x180003c51  jmp     loc_180003A8C
0x180003c56  cmp     [rdi+30h], r13d
0x180003c5a  jl      short loc_180003C66
0x180003c5c  lea     rcx, [rdi+38h]; lpCriticalSection
0x180003c60  call    cs:__imp_EnterCriticalSection
0x180003c66  mov     r15d, [rdi+60h]
0x180003c6a  mov     ebx, r13d
0x180003c6d  sub     r15d, 1
0x180003c71  jns     short loc_180003CB6
0x180003c73  cmp     dword ptr [rdi+30h], 0
  ... truncated ...
```
