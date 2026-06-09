# UbpmpTriggerConsumerUpdate

- ea: `0x18000e090`
- end: `0x18000e657`
- name: `UbpmpTriggerConsumerUpdate`
- size: `1479`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d5c0`

## callees

- `0x18000aba0`
- `0x18000ad3c`
- `0x18000ada4`
- `0x18000c37c`
- `0x18000c3d4`
- `0x18000c4f0`
- `0x18000d200`
- `0x18000d5c0`
- `0x18000e090`
- `0x180016eb0`
- `0x18001e9f4`
- `0x1800358a0`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000e419`
- `ntdll!RtlFreeHeap` at `0x18000e419`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e133`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e199`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e133`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e199`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000e18b`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000e18b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e178`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e1af`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e474`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e178`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e1af`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e474`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e270`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e298`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e37d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e3e3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e4ed`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e270`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e298`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e37d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e3e3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e4ed`
- `ntdll!NtDeleteWnfStateName` at `0x18000e64c`
- `ntdll!NtDeleteWnfStateName` at `0x18000e64c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000e10c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000e3b5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000e10c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000e3b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e17e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e1b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e47a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e17e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e1b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e47a`

## pseudocode

```c
__int64 __fastcall UbpmpTriggerConsumerUpdate(
        struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *a1,
        char a2,
        __int64 a3,
        _QWORD *a4)
{
  void *v4; // r12
  __int64 *Value; // rax
  __int64 v8; // rdx
  bool v9; // zf
  unsigned int v10; // ebx
  __int64 v11; // rsi
  int v12; // ebx
  struct _UBPM_TRIGGER_CONSUMER_BLOCK **v13; // rax
  struct _UBPM_TRIGGER_CONSUMER_BLOCK ***v14; // rcx
  struct _UBPM_TRIGGER_CONSUMER_BLOCK **v15; // rdx
  struct _UBPM_TRIGGER_CONSUMER_BLOCK **v16; // rax
  int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // edi
  __int64 v20; // rdx
  __int64 v21; // rcx
  _QWORD *v22; // rax
  _QWORD *v23; // rdx
  unsigned int i; // edx
  __int64 v25; // rax
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  int v28; // edx
  __int64 *v29; // rax
  __int64 v30; // r8
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v32; // rbx
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v33; // rcx
  int v34; // ecx
  char *v35; // rcx
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v36; // rdx
  struct _UBPM_TRIGGER_CONSUMER_BLOCK **v37; // rax
  char *v38; // rax
  struct _UBPM_TRIGGER_CONSUMER_BLOCK **v39; // r8
  char v40; // [rsp+30h] [rbp-29h]
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v41; // [rsp+38h] [rbp-21h] BYREF
  __int64 v42; // [rsp+40h] [rbp-19h] BYREF
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v43; // [rsp+48h] [rbp-11h] BYREF
  struct _UBPM_TRIGGER_CONSUMER_BLOCK **v44; // [rsp+50h] [rbp-9h]
  int v45; // [rsp+58h] [rbp-1h] BYREF
  int v46; // [rsp+60h] [rbp+7h]
  __int64 v47; // [rsp+68h] [rbp+Fh] BYREF

  v4 = 0;
  v43 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)&v43;
  v44 = &v43;
  v42 = 0;
  v41 = 0;
  v47 = 0;
  v45 = 0;
  if ( !a1 || (*((_DWORD *)a1 + 4) & 0x100) == 0 || !a2 )
    return 183;
  if ( UbpmpLockTrackerId != -1 )
  {
    Value = (__int64 *)TlsGetValue(UbpmpLockTrackerId);
    v8 = *Value;
    if ( (*Value & 1) == 0 )
      __int2c();
    v9 = Value[1]-- == 1;
    if ( v9 )
      *Value = v8 & 0xFFFFFFFFFFFFFFFEuLL;
  }
  RtlReleaseSRWLockShared(&g_ConsumerUpdateLock);
  v10 = UbpmpOpenTriggerConsumer(*(UUID **)a1, *((wchar_t **)a1 + 1), &v42);
  if ( !v10 )
  {
    UbpmpAcquireUpdateLockExclusive();
    v11 = v42;
    RtlAcquireSRWLockExclusive(v42 + 48);
    *(_DWORD *)(v11 + 56) = GetCurrentThreadId();
    RtlAcquireSRWLockShared(v11 + 72);
    v12 = *(unsigned __int8 *)(v11 + 92);
    RtlReleaseSRWLockShared(v11 + 72);
    if ( (v12 & 1) != 0 )
    {
      *(_DWORD *)(v11 + 56) = 0;
      RtlReleaseSRWLockExclusive(v11 + 48);
      v19 = 4320;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_30;
      v28 = 159;
      goto LABEL_28;
    }
    RtlAcquireSRWLockExclusive(v11 + 208);
    *(_DWORD *)(v11 + 216) = GetCurrentThreadId();
    v13 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK **)(v11 + 224);
    v14 = *(struct _UBPM_TRIGGER_CONSUMER_BLOCK ****)(v11 + 224);
    if ( v14 != (struct _UBPM_TRIGGER_CONSUMER_BLOCK ***)(v11 + 224) )
    {
      if ( v14[1] != v13 )
        goto LABEL_50;
      v15 = *(struct _UBPM_TRIGGER_CONSUMER_BLOCK ***)(v11 + 232);
      if ( *v15 != (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v13 )
        goto LABEL_50;
      *v15 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v14;
      v14[1] = v15;
      *(_QWORD *)(v11 + 232) = v11 + 224;
      *v13 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v13;
      v16 = *v14;
      if ( (*v14)[1] != (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v14 )
        goto LABEL_50;
      v43 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)*v14;
      v44 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK **)v14;
      v16[1] = (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)&v43;
      *v14 = &v43;
    }
    v40 = *(_BYTE *)(v11 + 304);
    v47 = *(_QWORD *)(v11 + 336);
    *(_QWORD *)(v11 + 336) = 0;
    v17 = *(_DWORD *)(v11 + 344);
    *(_DWORD *)(v11 + 344) = 0;
    v4 = *(void **)(v11 + 352);
    *(_QWORD *)(v11 + 352) = 0;
    v46 = v17;
    LODWORD(v42) = *(_DWORD *)(v11 + 44);
    *(_DWORD *)(v11 + 216) = 0;
    RtlReleaseSRWLockExclusive(v11 + 208);
    v18 = UbpmpTriggerConsumerUnregister(v11, &v45, 0, 0, 1);
    *(_DWORD *)(v11 + 56) = 0;
    v19 = v18;
    RtlReleaseSRWLockExclusive(v11 + 48);
    if ( v19 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_30;
      v28 = 160;
      goto LABEL_28;
    }
    UbpmpAcquireListLockExclusive();
    v21 = *(_QWORD *)(v11 + 8);
    v22 = (_QWORD *)(v11 + 8);
    if ( *(_QWORD *)(v21 + 8) == v11 + 8 )
    {
      v23 = *(_QWORD **)(v11 + 16);
      if ( (_QWORD *)*v23 == v22 )
      {
        --g_cTotalConsumers;
        *v23 = v21;
        *(_QWORD *)(v21 + 8) = v23;
        *(_QWORD *)(v11 + 16) = v11 + 8;
        *v22 = v22;
        UbpmpReleaseListLockExclusive();
        for ( i = 0; i < *((_DWORD *)a1 + 8); ++i )
        {
          v25 = *((_QWORD *)a1 + 5);
          if ( *(_DWORD *)(v25 + 40LL * i + 16) == 1 )
          {
            v26 = *(_QWORD *)(*(_QWORD *)(v25 + 40LL * i + 24) + 32LL);
            if ( v26 )
              *(_QWORD *)(v26 + 40) &= ~0x8000000000000000uLL;
          }
        }
        v19 = UbpmpTriggerConsumerRegister(a1, 1, &v41);
        if ( v19 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_30;
          v28 = 161;
LABEL_28:
          WPP_SF_Sd(
            v27[2],
            v28,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            *(_QWORD *)(*(_QWORD *)(v11 + 24) + 8LL),
            v19);
LABEL_30:
          UbpmTelemConsumerUpdated(a1, v20, v19);
          if ( UbpmpLockTrackerId != -1 )
          {
            v29 = (__int64 *)TlsGetValue(UbpmpLockTrackerId);
            v30 = *v29;
            if ( (*v29 & 1) == 0 )
              __int2c();
            v9 = v29[1]-- == 1;
            if ( v9 )
              *v29 = v30 & 0xFFFFFFFFFFFFFFFEuLL;
          }
          dword_18004CEC8 = 0;
          RtlReleaseSRWLockExclusive(&g_ConsumerUpdateLock);
          UbpmpAcquireUpdateLockShared();
          if ( v47 )
            NtDeleteWnfStateName(&v47);
          if ( v4 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
          if ( v11 )
            UbpmpCloseTriggerConsumer(v11);
          return v19;
        }
        v32 = v41;
        RtlAcquireSRWLockExclusive((char *)v41 + 208);
        *((_DWORD *)v32 + 54) = GetCurrentThreadId();
        v33 = v43;
        if ( v43 == (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)&v43 )
        {
LABEL_43:
          *((_BYTE *)v41 + 304) = v40;
          *((_QWORD *)v41 + 42) = v47;
          v47 = 0;
          *((_DWORD *)v41 + 86) = v46;
          v34 = v42;
          *((_QWORD *)v41 + 44) = v4;
          v4 = 0;
          *((_DWORD *)v41 + 11) = v34;
          v35 = (char *)v41 + 208;
          *((_DWORD *)v41 + 54) = 0;
          RtlReleaseSRWLockExclusive(v35);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_qqS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              *(_QWORD *)(*((_QWORD *)v41 + 3) + 8LL),
              (_DWORD)v41,
              v11,
              (char)v41,
              *(_QWORD *)(*((_QWORD *)v41 + 3) + 8LL));
          *a4 = v41;
          goto LABEL_30;
        }
        while ( 1 )
        {
          v36 = *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)v33;
          if ( *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)(*(_QWORD *)v33 + 8LL) != v33 )
            break;
          v37 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK **)*((_QWORD *)v33 + 1);
          if ( *v37 != v33 )
            break;
          *v37 = v36;
          *((_QWORD *)v36 + 1) = v37;
          *((_QWORD *)v33 + 1) = v33;
          *(_QWORD *)v33 = v33;
          v38 = (char *)v41 + 224;
          v39 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK **)*((_QWORD *)v41 + 29);
          if ( *v39 != (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)v41 + 224) )
            break;
          *(_QWORD *)v33 = v38;
          *((_QWORD *)v33 + 1) = v39;
          *v39 = v33;
          *((_QWORD *)v38 + 1) = v33;
          v33 = v36;
          if ( v36 == (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)&v43 )
            goto LABEL_43;
        }
      }
    }
LABEL_50:
    __fastfail(3u);
  }
  UbpmpAcquireUpdateLockShared();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      158,
      (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
      *((_QWORD *)a1 + 1),
      v10);
  return v10;
}

```

## disassembly

```asm
0x18000e090  push    rbp
0x18000e092  push    r12
0x18000e094  push    r13
0x18000e096  push    r14
0x18000e098  lea     rbp, [rsp-3Fh]
0x18000e09d  sub     rsp, 98h
0x18000e0a4  mov     rax, cs:__security_cookie
0x18000e0ab  xor     rax, rsp
0x18000e0ae  mov     [rbp+57h+var_40], rax
0x18000e0b2  xor     r12d, r12d
0x18000e0b5  lea     rax, [rbp+57h+var_68]
0x18000e0b9  mov     [rbp+57h+var_68], rax
0x18000e0bd  lea     rax, [rbp+57h+var_68]
0x18000e0c1  mov     [rbp+57h+var_60], rax
0x18000e0c5  mov     r13, r9
0x18000e0c8  mov     [rbp+57h+var_70], r12
0x18000e0cc  mov     r14, rcx
0x18000e0cf  mov     [rbp+57h+var_78], r12
0x18000e0d3  mov     [rbp+57h+var_48], r12
0x18000e0d7  mov     [rbp+57h+var_58], r12d
0x18000e0db  test    rcx, rcx
0x18000e0de  jz      loc_18000E5B3
0x18000e0e4  test    dword ptr [rcx+10h], 100h
0x18000e0eb  jz      loc_18000E5B3
0x18000e0f1  test    dl, dl
0x18000e0f3  jz      loc_18000E5B3
0x18000e0f9  mov     ecx, cs:UbpmpLockTrackerId; dwTlsIndex
0x18000e0ff  mov     [rsp+0B0h+arg_8], rbx
0x18000e107  cmp     ecx, 0FFFFFFFFh
0x18000e10a  jz      short loc_18000E12C
0x18000e10c  call    cs:__imp_TlsGetValue
0x18000e112  mov     rdx, [rax]
0x18000e115  test    dl, 1
0x18000e118  jz      loc_18000E613
0x18000e11e  sub     qword ptr [rax+8], 1
0x18000e123  jnz     short loc_18000E12C
0x18000e125  and     rdx, 0FFFFFFFFFFFFFFFEh
0x18000e129  mov     [rax], rdx
0x18000e12c  lea     rcx, ?g_ConsumerUpdateLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerUpdateLock
0x18000e133  call    cs:__imp_RtlReleaseSRWLockShared
0x18000e139  mov     rdx, [r14+8]; String2
0x18000e13d  lea     r8, [rbp+57h+var_70]
0x18000e141  mov     rcx, [r14]; Uuid2
0x18000e144  call    UbpmpOpenTriggerConsumer
0x18000e149  mov     ebx, eax
0x18000e14b  test    eax, eax
0x18000e14d  jnz     loc_18000E5BD
0x18000e153  mov     [rsp+0B0h+var_20], rsi
0x18000e15b  mov     [rsp+0B0h+var_28], rdi
0x18000e163  mov     [rsp+0B0h+var_30], r15
0x18000e16b  call    UbpmpAcquireUpdateLockExclusive
0x18000e170  mov     rsi, [rbp+57h+var_70]
0x18000e174  lea     rcx, [rsi+30h]
0x18000e178  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e17e  call    cs:__imp_GetCurrentThreadId
0x18000e184  lea     rcx, [rsi+48h]
0x18000e188  mov     [rsi+38h], eax
0x18000e18b  call    cs:__imp_RtlAcquireSRWLockShared
0x18000e191  movzx   ebx, byte ptr [rsi+5Ch]
0x18000e195  lea     rcx, [rsi+48h]
0x18000e199  call    cs:__imp_RtlReleaseSRWLockShared
0x18000e19f  test    bl, 1
0x18000e1a2  jnz     loc_18000E374
0x18000e1a8  lea     rcx, [rsi+0D0h]
0x18000e1af  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e1b5  call    cs:__imp_GetCurrentThreadId
0x18000e1bb  mov     [rsi+0D8h], eax
0x18000e1c1  lea     rax, [rsi+0E0h]
0x18000e1c8  mov     rcx, [rax]
0x18000e1cb  cmp     rcx, rax
0x18000e1ce  jz      short loc_18000E219
0x18000e1d0  cmp     [rcx+8], rax
0x18000e1d4  jnz     loc_18000E551
0x18000e1da  mov     rdx, [rax+8]
0x18000e1de  cmp     [rdx], rax
0x18000e1e1  jnz     loc_18000E551
0x18000e1e7  mov     [rdx], rcx
0x18000e1ea  mov     [rcx+8], rdx
0x18000e1ee  mov     [rax+8], rax
0x18000e1f2  mov     [rax], rax
0x18000e1f5  mov     rax, [rcx]
0x18000e1f8  cmp     [rax+8], rcx
0x18000e1fc  jnz     loc_18000E551
0x18000e202  mov     [rbp+57h+var_68], rax
0x18000e206  lea     rdx, [rbp+57h+var_68]
0x18000e20a  mov     [rbp+57h+var_60], rcx
0x18000e20e  mov     [rax+8], rdx
0x18000e212  lea     rax, [rbp+57h+var_68]
0x18000e216  mov     [rcx], rax
0x18000e219  movzx   eax, byte ptr [rsi+130h]
0x18000e220  lea     rcx, [rsi+0D0h]
0x18000e227  mov     [rbp+57h+var_80], al
0x18000e22a  mov     rax, [rsi+150h]
0x18000e231  mov     [rbp+57h+var_48], rax
0x18000e235  xor     eax, eax
0x18000e237  mov     [rsi+150h], rax
0x18000e23e  mov     eax, [rsi+158h]
0x18000e244  mov     [rsi+158h], r12d
0x18000e24b  mov     r12, [rsi+160h]
0x18000e252  mov     qword ptr [rsi+160h], 0
0x18000e25d  mov     [rbp+57h+var_50], eax
0x18000e260  mov     eax, [rsi+2Ch]
0x18000e263  mov     dword ptr [rbp+57h+var_70], eax
0x18000e266  mov     dword ptr [rsi+0D8h], 0
0x18000e270  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e276  xor     r9d, r9d
0x18000e279  mov     byte ptr [rsp+0B0h+var_90], 1
0x18000e27e  xor     r8d, r8d
0x18000e281  lea     rdx, [rbp+57h+var_58]
0x18000e285  mov     rcx, rsi
0x18000e288  call    UbpmpTriggerConsumerUnregister
0x18000e28d  xor     ebx, ebx
0x18000e28f  lea     rcx, [rsi+30h]
0x18000e293  mov     [rsi+38h], ebx
0x18000e296  mov     edi, eax
0x18000e298  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e29e  test    edi, edi
0x18000e2a0  jnz     loc_18000E526
0x18000e2a6  call    UbpmpAcquireListLockExclusive
0x18000e2ab  mov     rcx, [rsi+8]
0x18000e2af  lea     rax, [rsi+8]
0x18000e2b3  cmp     [rcx+8], rax
0x18000e2b7  jnz     loc_18000E551
0x18000e2bd  mov     rdx, [rax+8]
0x18000e2c1  cmp     [rdx], rax
0x18000e2c4  jnz     loc_18000E551
0x18000e2ca  dec     cs:g_cTotalConsumers
0x18000e2d0  mov     [rdx], rcx
0x18000e2d3  mov     [rcx+8], rdx
0x18000e2d7  mov     [rax+8], rax
0x18000e2db  mov     [rax], rax
0x18000e2de  call    UbpmpReleaseListLockExclusive
0x18000e2e3  mov     edx, ebx
0x18000e2e5  cmp     [r14+20h], ebx
0x18000e2e9  jbe     short loc_18000E320
0x18000e2eb  mov     r8, 7FFFFFFFFFFFFFFFh
0x18000e2f5  mov     eax, edx
0x18000e2f7  lea     rcx, [rax+rax*4]
0x18000e2fb  mov     rax, [r14+28h]
0x18000e2ff  cmp     dword ptr [rax+rcx*8+10h], 1
0x18000e304  jnz     short loc_18000E318
0x18000e306  mov     rax, [rax+rcx*8+18h]
0x18000e30b  mov     rcx, [rax+20h]
0x18000e30f  test    rcx, rcx
0x18000e312  jnz     loc_18000E51D
0x18000e318  inc     edx
0x18000e31a  cmp     edx, [r14+20h]
0x18000e31e  jb      short loc_18000E2F5
0x18000e320  lea     r8, [rbp+57h+var_78]
0x18000e324  mov     dl, 1
0x18000e326  mov     rcx, r14; struct _UBPM_TRIGGER_CONSUMER_PARAMS_1 *
0x18000e329  call    UbpmpTriggerConsumerRegister
0x18000e32e  mov     edi, eax
0x18000e330  test    eax, eax
0x18000e332  jz      loc_18000E469
0x18000e338  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e33f  lea     rax, WPP_GLOBAL_Control
0x18000e346  cmp     rcx, rax
0x18000e349  jz      short loc_18000E39F
0x18000e34b  test    byte ptr [rcx+1Ch], 1
0x18000e34f  jz      short loc_18000E39F
0x18000e351  mov     edx, 0A1h
0x18000e356  mov     r9, [rsi+18h]
0x18000e35a  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18000e361  mov     rcx, [rcx+10h]
0x18000e365  mov     dword ptr [rsp+0B0h+var_90], edi
0x18000e369  mov     r9, [r9+8]
0x18000e36d  call    WPP_SF_Sd
0x18000e372  jmp     short loc_18000E39F
0x18000e374  xor     ebx, ebx
0x18000e376  lea     rcx, [rsi+30h]
0x18000e37a  mov     [rsi+38h], ebx
0x18000e37d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e383  mov     edi, 10E0h
0x18000e388  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e38f  lea     rax, WPP_GLOBAL_Control
0x18000e396  cmp     rcx, rax
0x18000e399  jnz     loc_18000E5FF
0x18000e39f  mov     r8d, edi
0x18000e3a2  mov     rcx, r14
0x18000e3a5  call    UbpmTelemConsumerUpdated
0x18000e3aa  mov     ecx, cs:UbpmpLockTrackerId; dwTlsIndex
0x18000e3b0  cmp     ecx, 0FFFFFFFFh
0x18000e3b3  jz      short loc_18000E3D6
0x18000e3b5  call    cs:__imp_TlsGetValue
0x18000e3bb  mov     r8, [rax]
0x18000e3be  test    r8b, 1
0x18000e3c2  jz      loc_18000E61A
0x18000e3c8  sub     qword ptr [rax+8], 1
0x18000e3cd  jnz     short loc_18000E3D6
0x18000e3cf  and     r8, 0FFFFFFFFFFFFFFFEh
0x18000e3d3  mov     [rax], r8
0x18000e3d6  lea     rcx, ?g_ConsumerUpdateLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerUpdateLock
0x18000e3dd  mov     cs:dword_18004CEC8, ebx
0x18000e3e3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e3e9  call    UbpmpAcquireUpdateLockShared
0x18000e3ee  cmp     dword ptr [rbp+57h+var_48], 0
0x18000e3f2  jnz     loc_18000E648
0x18000e3f8  cmp     dword ptr [rbp+57h+var_48+4], 0
0x18000e3fc  jnz     loc_18000E648
0x18000e402  test    r12, r12
0x18000e405  jz      short loc_18000E41F
0x18000e407  mov     rcx, gs:60h
0x18000e410  mov     r8, r12; P
0x18000e413  xor     edx, edx; Flags
0x18000e415  mov     rcx, [rcx+30h]; HeapHandle
0x18000e419  call    cs:__imp_RtlFreeHeap
0x18000e41f  test    rsi, rsi
0x18000e422  jz      short loc_18000E42C
0x18000e424  mov     rcx, rsi
0x18000e427  call    UbpmpCloseTriggerConsumer
0x18000e42c  mov     rsi, [rsp+0B0h+var_20]
0x18000e434  mov     eax, edi
0x18000e436  mov     rdi, [rsp+0B0h+var_28]
0x18000e43e  mov     r15, [rsp+0B0h+var_30]
0x18000e446  mov     rbx, [rsp+0B0h+arg_8]
0x18000e44e  mov     rcx, [rbp+57h+var_40]
0x18000e452  xor     rcx, rsp; StackCookie
0x18000e455  call    __security_check_cookie
0x18000e45a  add     rsp, 98h
0x18000e461  pop     r14
0x18000e463  pop     r13
0x18000e465  pop     r12
0x18000e467  pop     rbp
0x18000e468  retn
0x18000e469  mov     rbx, [rbp+57h+var_78]
0x18000e46d  lea     rcx, [rbx+0D0h]
0x18000e474  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e47a  call    cs:__imp_GetCurrentThreadId
0x18000e480  mov     [rbx+0D8h], eax
0x18000e486  lea     rax, [rbp+57h+var_68]
0x18000e48a  mov     rcx, [rbp+57h+var_68]
0x18000e48e  cmp     rcx, rax
0x18000e491  jnz     loc_18000E560
0x18000e497  mov     rax, [rbp+57h+var_78]
0x18000e49b  xor     ebx, ebx
0x18000e49d  movzx   ecx, [rbp+57h+var_80]
0x18000e4a1  mov     [rax+130h], cl
0x18000e4a7  mov     rcx, [rbp+57h+var_78]
0x18000e4ab  mov     rax, [rbp+57h+var_48]
0x18000e4af  mov     [rcx+150h], rax
0x18000e4b6  mov     rax, [rbp+57h+var_78]
0x18000e4ba  mov     ecx, [rbp+57h+var_50]
0x18000e4bd  mov     [rbp+57h+var_48], rbx
0x18000e4c1  mov     [rax+158h], ecx
0x18000e4c7  mov     rax, [rbp+57h+var_78]
0x18000e4cb  mov     ecx, dword ptr [rbp+57h+var_70]
0x18000e4ce  mov     [rax+160h], r12
0x18000e4d5  mov     r12d, ebx
0x18000e4d8  mov     rax, [rbp+57h+var_78]
0x18000e4dc  mov     [rax+2Ch], ecx
0x18000e4df  mov     rcx, [rbp+57h+var_78]
0x18000e4e3  add     rcx, 0D0h
0x18000e4ea  mov     [rcx+8], ebx
0x18000e4ed  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e4f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4fa  lea     rax, WPP_GLOBAL_Control
0x18000e501  cmp     rcx, rax
0x18000e504  jz      short loc_18000E510
0x18000e506  test    byte ptr [rcx+1Ch], 4
0x18000e50a  jnz     loc_18000E621
0x18000e510  mov     rax, [rbp+57h+var_78]
0x18000e514  mov     [r13+0], rax
0x18000e518  jmp     loc_18000E39F
0x18000e51d  and     [rcx+28h], r8
0x18000e521  jmp     loc_18000E318
0x18000e526  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e52d  lea     rax, WPP_GLOBAL_Control
0x18000e534  cmp     rcx, rax
0x18000e537  jz      loc_18000E39F
0x18000e53d  test    byte ptr [rcx+1Ch], 1
0x18000e541  jz      loc_18000E39F
0x18000e547  mov     edx, 0A0h
0x18000e54c  jmp     loc_18000E356
0x18000e551  mov     ecx, 3
0x18000e556  int     29h; Win8: RtlFailFast(ecx)
0x18000e560  mov     rdx, [rcx]
0x18000e563  cmp     [rdx+8], rcx
0x18000e567  jnz     short loc_18000E551
0x18000e569  mov     rax, [rcx+8]
0x18000e56d  cmp     [rax], rcx
0x18000e570  jnz     short loc_18000E551
0x18000e572  mov     [rax], rdx
0x18000e575  mov     [rdx+8], rax
0x18000e579  mov     [rcx+8], rcx
0x18000e57d  mov     [rcx], rcx
0x18000e580  mov     rax, [rbp+57h+var_78]
0x18000e584  add     rax, 0E0h
0x18000e58a  mov     r8, [rax+8]
0x18000e58e  cmp     [r8], rax
0x18000e591  jnz     short loc_18000E551
0x18000e593  mov     [rcx], rax
0x18000e596  mov     [rcx+8], r8
0x18000e59a  mov     [r8], rcx
0x18000e59d  mov     [rax+8], rcx
0x18000e5a1  lea     rax, [rbp+57h+var_68]
0x18000e5a5  mov     rcx, rdx
0x18000e5a8  cmp     rdx, rax
0x18000e5ab  jz      loc_18000E497
0x18000e5b1  jmp     short loc_18000E560
  ... truncated ...
```
