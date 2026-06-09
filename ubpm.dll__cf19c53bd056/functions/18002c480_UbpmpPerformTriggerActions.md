# UbpmpPerformTriggerActions

- ea: `0x18002c480`
- end: `0x18002cb81`
- name: `UbpmpPerformTriggerActions`
- size: `1793`
- prototype: `void __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, __int64, unsigned __int16, __int64, _DWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180026650`

## callees

- `0x180003890`
- `0x180014db0`
- `0x180018610`
- `0x180019dc0`
- `0x18001c000`
- `0x18001cc44`
- `0x18001cd78`
- `0x18001e9f4`
- `0x180024bb0`
- `0x18002c480`
- `0x18002e964`
- `0x180032dd8`
- `0x1800356cc`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c715`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c715`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c740`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c740`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002c8b0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002c8b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c71b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c71b`
- `RPCRT4!UuidEqual` at `0x18002ca19`
- `RPCRT4!UuidEqual` at `0x18002ca19`
- `RPCRT4!UuidCreate` at `0x18002c532`
- `RPCRT4!UuidCreate` at `0x18002c532`

## pseudocode

```c
void __fastcall UbpmpPerformTriggerActions(
        struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1,
        __int64 a2,
        unsigned __int16 a3,
        __int64 a4,
        _DWORD *a5,
        unsigned int a6)
{
  unsigned __int16 v6; // r15
  __int64 v9; // r12
  RPC_STATUS v10; // eax
  _QWORD *v11; // rcx
  int v12; // edx
  __int64 v13; // r14
  __int64 v14; // rax
  unsigned int v15; // r10d
  unsigned __int16 **v16; // r8
  __int64 v17; // r9
  int v18; // ecx
  unsigned __int16 i; // di
  int v20; // eax
  unsigned __int8 v21; // cl
  int v22; // r14d
  unsigned __int64 v23; // r13
  __int64 v24; // rdx
  unsigned int v25; // r8d
  __int64 v26; // r8
  __int64 v27; // rcx
  _BYTE *v28; // rax
  bool v29; // zf
  int v30; // eax
  __int64 v31; // rax
  int *v32; // rcx
  __int64 v33; // rax
  unsigned int v34; // eax
  __int64 v35; // rcx
  _QWORD *v36; // rdx
  unsigned int v37; // r8d
  __int64 v38; // rbx
  __int64 v39; // rcx
  unsigned int v40; // r14d
  __int64 v41; // rcx
  int v42; // eax
  int v43; // edx
  int v44; // eax
  __int64 v45; // rcx
  _BYTE *v46; // rax
  int v47; // eax
  int v48; // edx
  __int64 v49; // rax
  __int64 v50; // rax
  int v51; // r8d
  unsigned __int8 v52; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v53[7]; // [rsp+31h] [rbp-CFh] BYREF
  __int64 v54; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v55; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v56; // [rsp+48h] [rbp-B8h] BYREF
  RPC_STATUS Status; // [rsp+50h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v59; // [rsp+68h] [rbp-98h] BYREF
  UUID Uuid; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-80h] BYREF
  __int128 v62; // [rsp+90h] [rbp-70h]
  __int128 v63; // [rsp+A0h] [rbp-60h]
  __int128 v64; // [rsp+B0h] [rbp-50h]
  __int128 v65; // [rsp+C0h] [rbp-40h]
  __int128 v66; // [rsp+D0h] [rbp-30h]
  __int128 v67; // [rsp+E0h] [rbp-20h]
  __int64 v68; // [rsp+F0h] [rbp-10h]

  v6 = 0;
  v55 = 0;
  Uuid = 0;
  v53[0] = 0;
  Status = 0;
  v52 = 0;
  v56 = a4;
  v9 = a3;
  *(_QWORD *)&EventDescriptor.Id = a2;
  v10 = UbpmpTriggerHandlerPrologue();
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v12 = 40;
LABEL_5:
      WPP_SF_Sd(
        v11[2],
        v12,
        (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
        *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
        v10);
    }
  }
  else
  {
    v10 = UuidCreate(&Uuid);
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 41;
        goto LABEL_5;
      }
    }
    else
    {
      if ( (_WORD)v9 == 0xFFFF )
      {
        v15 = 0;
        v13 = 3145680;
        v16 = 0;
      }
      else
      {
        v13 = 48 * v9;
        v14 = *(_QWORD *)(*((_QWORD *)a1 + 3) + 24LL);
        v15 = *(_DWORD *)(v14 + 48 * v9 + 36);
        v16 = *(unsigned __int16 ***)(v14 + 48 * v9 + 40);
      }
      v54 = v13;
      UbpmpGetActionMask(a1, v15, v16, &v55);
      v17 = *((_QWORD *)a1 + 3);
      v18 = *(_DWORD *)(v13 + *(_QWORD *)(v17 + 24));
      if ( v18 == 2 )
      {
        LOBYTE(v17) = 1;
        UbpmpRunConsumerQueuedActions(a1, a2, 1, v17);
      }
      else if ( v18 == 3 )
      {
        i = -1;
        v20 = UbpmpMaintenanceTaskCompletedWithinTimePeriod(a1, &v52);
        v21 = v52;
        v22 = v20;
        if ( !v20 && !v52 )
        {
          v23 = v55;
          for ( i = 0; ; ++i )
          {
            v24 = *((_QWORD *)a1 + 3);
            v25 = (_WORD)v9 == 0xFFFF ? *(_DWORD *)(v24 + 32) : *(_DWORD *)(v54 + *(_QWORD *)(v24 + 24) + 36);
            if ( i >= v25 )
              break;
            v68 = 0;
            *(_QWORD *)&UserData.Size = 0;
            UserData.Ptr = (ULONGLONG)a1;
            v26 = 40LL * i;
            v62 = 0;
            v63 = 0;
            v64 = 0;
            v65 = 0;
            v66 = 0;
            v67 = 0;
            if ( (_WORD)v9 == 0xFFFF )
              *(_QWORD *)&v62 = *(_QWORD *)(v26 + *(_QWORD *)(v24 + 40));
            else
              *(_QWORD *)&v62 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v24 + 24) + v54 + 40) + 8LL * i);
            v27 = v26 + *(_QWORD *)(v24 + 40);
            *(_QWORD *)&v64 = &Uuid;
            *(_QWORD *)&v66 = v56;
            *(_QWORD *)&v65 = v23;
            v28 = *(_BYTE **)(v27 + 32);
            if ( !v28 || (v29 = (*v28 & 0x10) == 0, DWORD2(v64) = 0x200000, v29) )
              DWORD2(v64) = 0;
            *(_QWORD *)&UserData.Size = v27;
            DWORD2(v67) = v9;
            UbpmpQueueActionInstance(3, &UserData);
            RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
            dword_18004CEE8 = GetCurrentThreadId();
            v30 = UbpmpCheckQueueMaintenanceLauncher();
            dword_18004CEE8 = 0;
            v22 = v30;
            RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              WPP_SF_dSd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                42,
                (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                i,
                *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
                v22);
          }
          v21 = v52;
        }
        if ( (unsigned int)dword_18004C0F0 > 4 )
        {
          LODWORD(v55) = i;
          v31 = *((_QWORD *)a1 + 3);
          LODWORD(v56) = v22;
          v53[0] = v21;
          *((_QWORD *)&v66 + 1) = 4;
          v32 = *(int **)(v31 + 8);
          *(_QWORD *)&v66 = &v56;
          *(_QWORD *)&v65 = &v55;
          *(_QWORD *)&v64 = v53;
          *((_QWORD *)&v65 + 1) = 4;
          *((_QWORD *)&v64 + 1) = 1;
          if ( v32 )
          {
            v33 = -1;
            do
              v29 = *((_WORD *)v32 + ++v33) == 0;
            while ( !v29 );
            v34 = 2 * v33 + 2;
          }
          else
          {
            v32 = &dword_1800405F4;
            v34 = 2;
          }
          *((_QWORD *)&v63 + 1) = v34;
          *(_DWORD *)&EventDescriptor.Level = 4;
          UserData.Ptr = (ULONGLONG)off_18004C0F8;
          *(_QWORD *)&v63 = v32;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)off_18004C0F8;
          *(_QWORD *)&v62 = &word_1800432BE;
          UserData.Reserved = 2;
          *((_QWORD *)&v62 + 1) = 0x10000005BLL;
          LODWORD(v54) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
        }
      }
      else if ( a5 )
      {
        if ( a6 >= 0x14 )
        {
          while ( 1 )
          {
            v35 = *((_QWORD *)a1 + 3);
            v36 = (_QWORD *)(v35 + 24);
            v37 = (_WORD)v9 == 0xFFFF ? *(_DWORD *)(v35 + 32) : *(_DWORD *)(v13 + *v36 + 36);
            if ( v6 >= v37 )
              break;
            v68 = 0;
            *(_QWORD *)&UserData.Size = 0;
            UserData.Ptr = (ULONGLONG)a1;
            v38 = 40LL * v6;
            v67 = 0;
            DWORD2(v67) = v9;
            v62 = 0;
            v63 = 0;
            v64 = 0;
            v65 = 0;
            v66 = 0;
            if ( (_WORD)v9 == 0xFFFF )
            {
              v40 = v9;
              v43 = DWORD2(v64);
              v45 = *(_QWORD *)(v38 + *(_QWORD *)(v35 + 40));
              *(_QWORD *)&v64 = &Uuid;
              *(_QWORD *)&v65 = v55;
              *(_QWORD *)&v66 = v56;
              *(_QWORD *)&v62 = v45;
            }
            else
            {
              v39 = *(_QWORD *)(*v36 + v13 + 40);
              v40 = v9;
              *(_QWORD *)&v62 = *(_QWORD *)(v39 + 8LL * v6);
              *(_QWORD *)&v64 = &Uuid;
              *(_QWORD *)&v65 = v55;
              *(_QWORD *)&v66 = v56;
              v41 = *(_QWORD *)(*v36 + v54 + 8);
              if ( *(_DWORD *)(v41 + 56) == 1 )
              {
                v42 = UuidEqual(**(UUID ***)(v41 + 64), (UUID *)&IDLE_TRIGGER_PROVIDER_GUID, &Status);
                v43 = DWORD2(v64);
                if ( v42 )
                  v43 = 0x100000;
              }
              else
              {
                v43 = DWORD2(v64);
              }
              v44 = a5[2];
              if ( (v44 & 8) != 0 )
                v43 |= 0x20000u;
              if ( (v44 & 0x10) != 0 )
                v43 |= 0x80000u;
              if ( (v44 & 4) != 0 )
                v43 |= 0x20u;
            }
            v46 = *(_BYTE **)(*(_QWORD *)(*((_QWORD *)a1 + 3) + 40LL) + v38 + 32);
            if ( v46 && (*v46 & 0x10) != 0 )
              v47 = 0x200000;
            else
              v47 = 0;
            v48 = v47 | v43;
            v49 = (unsigned int)a5[1];
            DWORD2(v64) = v48;
            if ( (_DWORD)v49 )
            {
              *((_QWORD *)&v62 + 1) = (char *)a5 + v49;
              LODWORD(v63) = *a5;
            }
            DWORD1(v63) = a5[3];
            v50 = (unsigned int)a5[6];
            if ( (_DWORD)v50 )
              *((_QWORD *)&v63 + 1) = (char *)a5 + v50;
            v59 = 0;
            UbpmpTakeActions(
              (struct _UBPM_INPUT_ACTION_PARAMS *)&UserData,
              *(struct _UBPM_CONSTRAINT_PRECHECK_INFO **)&EventDescriptor.Id,
              &v59,
              v53,
              v9);
            if ( v53[0] == 1 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, v51, v6, *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL));
              return;
            }
            UbpmpExecutionTimeLimitCheckSet(a1, v64, DWORD2(v64), v40);
            v13 = v54;
            ++v6;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            44,
            WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
            *(_QWORD *)(v17 + 8));
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *(_QWORD *)(v17 + 8));
      }
    }
  }
}

```

## disassembly

```asm
0x18002c480  push    rbp
0x18002c482  push    rbx
0x18002c483  push    rsi
0x18002c484  push    rdi
0x18002c485  push    r12
0x18002c487  push    r15
0x18002c489  lea     rbp, [rsp-28h]
0x18002c48e  sub     rsp, 128h
0x18002c495  mov     rax, cs:__security_cookie
0x18002c49c  xor     rax, rsp
0x18002c49f  mov     [rbp+50h+var_50], rax
0x18002c4a3  mov     rdi, [rbp+50h+arg_20]
0x18002c4aa  xor     r15d, r15d
0x18002c4ad  xorps   xmm0, xmm0
0x18002c4b0  mov     [rsp+150h+var_110], r15
0x18002c4b5  movups  xmmword ptr [rsp+150h+Uuid.Data1], xmm0
0x18002c4ba  mov     [rsp+150h+var_11F], r15b
0x18002c4bf  mov     rbx, rdx
0x18002c4c2  mov     [rsp+150h+Status], r15d
0x18002c4c7  mov     rsi, rcx
0x18002c4ca  mov     [rsp+150h+var_120], r15b
0x18002c4cf  mov     [rsp+150h+var_108], r9
0x18002c4d4  movzx   r12d, r8w
0x18002c4d8  mov     qword ptr [rsp+150h+EventDescriptor.Id], rdx
0x18002c4dd  call    UbpmpTriggerHandlerPrologue
0x18002c4e2  test    eax, eax
0x18002c4e4  jz      short loc_18002C52D
0x18002c4e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4ed  lea     rbx, WPP_GLOBAL_Control
0x18002c4f4  cmp     rcx, rbx
0x18002c4f7  jz      loc_18002CB65
0x18002c4fd  test    byte ptr [rcx+1Ch], 10h
0x18002c501  jz      loc_18002CB65
0x18002c507  mov     edx, 28h ; '('
0x18002c50c  mov     r9, [rsi+18h]
0x18002c510  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18002c517  mov     rcx, [rcx+10h]
0x18002c51b  mov     [rsp+150h+UserDataCount], eax
0x18002c51f  mov     r9, [r9+8]
0x18002c523  call    WPP_SF_Sd
0x18002c528  jmp     loc_18002CB65
0x18002c52d  lea     rcx, [rsp+150h+Uuid]; Uuid
0x18002c532  call    cs:__imp_UuidCreate
0x18002c538  test    eax, eax
0x18002c53a  jz      short loc_18002C564
0x18002c53c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c543  lea     rbx, WPP_GLOBAL_Control
0x18002c54a  cmp     rcx, rbx
0x18002c54d  jz      loc_18002CB65
0x18002c553  test    byte ptr [rcx+1Ch], 1
0x18002c557  jz      loc_18002CB65
0x18002c55d  mov     edx, 29h ; ')'
0x18002c562  jmp     short loc_18002C50C
0x18002c564  mov     [rsp+150h+var_30], r13
0x18002c56c  mov     r13d, 0FFFFh
0x18002c572  mov     [rsp+150h+var_38], r14
0x18002c57a  cmp     r12w, r13w
0x18002c57e  jz      short loc_18002C5A3
0x18002c580  mov     rdx, [rsi+18h]
0x18002c584  lea     r14, [r12+r12*2]
0x18002c588  shl     r14, 4
0x18002c58c  lea     rcx, [r12+r12*2]
0x18002c590  add     rcx, rcx
0x18002c593  mov     rax, [rdx+18h]
0x18002c597  mov     r10d, [rax+r14+24h]
0x18002c59c  mov     r8, [rax+rcx*8+28h]
0x18002c5a1  jmp     short loc_18002C5AF
0x18002c5a3  mov     r10d, r15d
0x18002c5a6  mov     r14d, 2FFFD0h
0x18002c5ac  mov     r8, r15; unsigned __int16 **
0x18002c5af  lea     r9, [rsp+150h+var_110]; unsigned __int64 *
0x18002c5b4  mov     [rsp+150h+var_118], r14
0x18002c5b9  mov     edx, r10d; unsigned int
0x18002c5bc  mov     rcx, rsi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18002c5bf  call    ?UbpmpGetActionMask@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@KPEAPEAGPEA_K@Z; UbpmpGetActionMask(_UBPM_TRIGGER_CONSUMER_BLOCK *,ulong,ushort * *,unsigned __int64 *)
0x18002c5c4  mov     r9, [rsi+18h]
0x18002c5c8  mov     rax, [r9+18h]
0x18002c5cc  mov     ecx, [r14+rax]
0x18002c5d0  cmp     ecx, 2
0x18002c5d3  jnz     short loc_18002C5EE
0x18002c5d5  mov     r9b, 1
0x18002c5d8  mov     r8d, 1
0x18002c5de  mov     rdx, rbx
0x18002c5e1  mov     rcx, rsi
0x18002c5e4  call    ?UbpmpRunConsumerQueuedActions@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@W4_UBPM_QUEUED_ACTION_QUEUE_REASON@@E@Z; UbpmpRunConsumerQueuedActions(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_QUEUED_ACTION_QUEUE_REASON,uchar)
0x18002c5e9  jmp     loc_18002CB55
0x18002c5ee  cmp     ecx, 3
0x18002c5f1  jnz     loc_18002C8BB
0x18002c5f7  lea     rdx, [rsp+150h+var_120]
0x18002c5fc  mov     rcx, rsi
0x18002c5ff  movzx   edi, r13w
0x18002c603  call    UbpmpMaintenanceTaskCompletedWithinTimePeriod
0x18002c608  movzx   ecx, [rsp+150h+var_120]
0x18002c60d  mov     r14d, eax
0x18002c610  test    eax, eax
0x18002c612  jnz     loc_18002C795
0x18002c618  test    cl, cl
0x18002c61a  jnz     loc_18002C795
0x18002c620  mov     r13, [rsp+150h+var_110]
0x18002c625  lea     rbx, WPP_GLOBAL_Control
0x18002c62c  mov     edi, r15d
0x18002c62f  nop
0x18002c630  mov     rdx, [rsi+18h]
0x18002c634  mov     r11d, 0FFFFh
0x18002c63a  mov     r10, [rsp+150h+var_118]
0x18002c63f  cmp     r12w, r11w
0x18002c643  jz      short loc_18002C650
0x18002c645  mov     rax, [rdx+18h]
0x18002c649  mov     r8d, [r10+rax+24h]
0x18002c64e  jmp     short loc_18002C654
0x18002c650  mov     r8d, [rdx+20h]
0x18002c654  movzx   r15d, di
0x18002c658  cmp     r15d, r8d
0x18002c65b  jnb     loc_18002C78D
0x18002c661  xorps   xmm0, xmm0
0x18002c664  movzx   r9d, di
0x18002c668  xor     eax, eax
0x18002c66a  mov     [rbp+50h+var_60], rax
0x18002c66e  movups  xmmword ptr [rbp+50h+var_D0.Ptr], xmm0
0x18002c672  mov     [rbp+50h+var_D0.Ptr], rsi
0x18002c676  lea     rax, [r9+r9*4]
0x18002c67a  lea     r8, ds:0[rax*8]
0x18002c682  movups  [rbp+50h+var_C0], xmm0
0x18002c686  movups  [rbp+50h+var_B0], xmm0
0x18002c68a  movups  [rbp+50h+var_A0], xmm0
0x18002c68e  movups  [rbp+50h+var_90], xmm0
0x18002c692  movups  [rbp+50h+var_80], xmm0
0x18002c696  movups  [rbp+50h+var_70], xmm0
0x18002c69a  cmp     r12w, r11w
0x18002c69e  jz      short loc_18002C6B3
0x18002c6a0  mov     rax, [rdx+18h]
0x18002c6a4  mov     rcx, [rax+r10+28h]
0x18002c6a9  mov     rax, [rcx+r9*8]
0x18002c6ad  mov     qword ptr [rbp+50h+var_C0], rax
0x18002c6b1  jmp     short loc_18002C6BF
0x18002c6b3  mov     rax, [rdx+28h]
0x18002c6b7  mov     rcx, [r8+rax]
0x18002c6bb  mov     qword ptr [rbp+50h+var_C0], rcx
0x18002c6bf  mov     rcx, [rdx+28h]
0x18002c6c3  lea     rax, [rsp+150h+Uuid]
0x18002c6c8  add     rcx, r8
0x18002c6cb  mov     qword ptr [rbp+50h+var_A0], rax
0x18002c6cf  mov     rax, [rsp+150h+var_108]
0x18002c6d4  mov     qword ptr [rbp+50h+var_80], rax
0x18002c6d8  mov     qword ptr [rbp+50h+var_90], r13
0x18002c6dc  mov     rax, [rcx+20h]
0x18002c6e0  test    rax, rax
0x18002c6e3  jz      short loc_18002C6F1
0x18002c6e5  test    byte ptr [rax], 10h
0x18002c6e8  mov     dword ptr [rbp+50h+var_A0+8], 200000h
0x18002c6ef  jnz     short loc_18002C6F8
0x18002c6f1  mov     dword ptr [rbp+50h+var_A0+8], 0
0x18002c6f8  mov     qword ptr [rbp+50h+var_D0.Size], rcx
0x18002c6fc  lea     rdx, [rbp+50h+var_D0]
0x18002c700  mov     ecx, 3
0x18002c705  mov     dword ptr [rbp+50h+var_70+8], r12d
0x18002c709  call    UbpmpQueueActionInstance
0x18002c70e  lea     rcx, g_MaintenanceLaunchLock
0x18002c715  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002c71b  call    cs:__imp_GetCurrentThreadId
0x18002c721  mov     cs:dword_18004CEE8, eax
0x18002c727  call    UbpmpCheckQueueMaintenanceLauncher
0x18002c72c  lea     rcx, g_MaintenanceLaunchLock
0x18002c733  mov     cs:dword_18004CEE8, 0
0x18002c73d  mov     r14d, eax
0x18002c740  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002c746  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c74d  cmp     rcx, rbx
0x18002c750  jz      short loc_18002C785
0x18002c752  test    dword ptr [rcx+1Ch], 200h
0x18002c759  jz      short loc_18002C785
0x18002c75b  mov     rax, [rsi+18h]
0x18002c75f  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18002c766  mov     rcx, [rcx+10h]
0x18002c76a  mov     edx, 2Ah ; '*'
0x18002c76f  mov     dword ptr [rsp+150h+UserData], r14d
0x18002c774  mov     r9d, r15d
0x18002c777  mov     rax, [rax+8]
0x18002c77b  mov     qword ptr [rsp+150h+UserDataCount], rax
0x18002c780  call    WPP_SF_dSd
0x18002c785  inc     di
0x18002c788  jmp     loc_18002C630
0x18002c78d  movzx   ecx, [rsp+150h+var_120]
0x18002c792  xor     r15d, r15d
0x18002c795  mov     eax, cs:dword_18004C0F0
0x18002c79b  cmp     eax, 4
0x18002c79e  jbe     loc_18002CB55
0x18002c7a4  movzx   eax, di
0x18002c7a7  mov     dword ptr [rsp+150h+var_110], eax
0x18002c7ab  mov     rax, [rsi+18h]
0x18002c7af  mov     dword ptr [rsp+150h+var_108], r14d
0x18002c7b4  mov     [rsp+150h+var_11F], cl
0x18002c7b8  mov     qword ptr [rbp+50h+var_80+8], 4
0x18002c7c0  mov     rcx, [rax+8]
0x18002c7c4  lea     rax, [rsp+150h+var_108]
0x18002c7c9  mov     qword ptr [rbp+50h+var_80], rax
0x18002c7cd  lea     rax, [rsp+150h+var_110]
0x18002c7d2  mov     qword ptr [rbp+50h+var_90], rax
0x18002c7d6  lea     rax, [rsp+150h+var_11F]
0x18002c7db  mov     qword ptr [rbp+50h+var_A0], rax
0x18002c7df  mov     qword ptr [rbp+50h+var_90+8], 4
0x18002c7e7  mov     qword ptr [rbp+50h+var_A0+8], 1
0x18002c7ef  test    rcx, rcx
0x18002c7f2  jz      short loc_18002C815
0x18002c7f4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002c7fb  nop     dword ptr [rax+rax+00h]
0x18002c800  cmp     word ptr [rcx+rax*2+2], 0
0x18002c806  lea     rax, [rax+1]
0x18002c80a  jnz     short loc_18002C800
0x18002c80c  lea     eax, ds:2[rax*2]
0x18002c813  jmp     short loc_18002C821
0x18002c815  lea     rcx, dword_1800405F4
0x18002c81c  mov     eax, 2
0x18002c821  mov     dword ptr [rbp+50h+var_B0+8], eax
0x18002c824  lea     rdx, [rsp+150h+EventDescriptor]; EventDescriptor
0x18002c829  movzx   eax, cs:word_1800432B4
0x18002c830  xor     r9d, r9d; RelatedActivityId
0x18002c833  mov     dword ptr [rsp+150h+EventDescriptor.Level], eax
0x18002c837  xor     r8d, r8d; ActivityId
0x18002c83a  mov     rax, cs:off_18004C0F8
0x18002c841  mov     [rbp+50h+var_D0.Ptr], rax
0x18002c845  mov     qword ptr [rbp+50h+var_B0], rcx
0x18002c849  lea     rcx, _TraceLoggingMetadata
0x18002c850  mov     dword ptr [rbp+50h+var_B0+0Ch], r15d
0x18002c854  mov     dword ptr [rsp+150h+EventDescriptor.Id], 0B000000h
0x18002c85c  mov     [rsp+150h+EventDescriptor.Keyword], r15
0x18002c861  movzx   eax, word ptr [rax]
0x18002c864  mov     [rbp+50h+var_D0.Size], eax
0x18002c867  lea     rax, word_1800432BE
0x18002c86e  mov     qword ptr [rbp+50h+var_C0], rax
0x18002c872  lea     rax, _TraceLoggingMetadataEnd
0x18002c879  sub     eax, ecx
0x18002c87b  mov     dword ptr [rbp+50h+var_D0.0Ch], 2
0x18002c882  mov     dword ptr [rbp+50h+var_C0+8], 5Bh ; '['
0x18002c889  mov     dword ptr [rbp+50h+var_C0+0Ch], 1
0x18002c890  mov     dword ptr [rsp+150h+var_118], eax
0x18002c894  mov     eax, dword ptr [rsp+150h+var_118]
0x18002c898  mov     rcx, cs:RegHandle; RegHandle
0x18002c89f  lea     rax, [rbp+50h+var_D0]
0x18002c8a3  mov     [rsp+150h+UserData], rax; UserData
0x18002c8a8  mov     [rsp+150h+UserDataCount], 6; UserDataCount
0x18002c8b0  call    cs:__imp_EventWriteTransfer
0x18002c8b6  jmp     loc_18002CB55
0x18002c8bb  test    rdi, rdi
0x18002c8be  jnz     short loc_18002C8FF
0x18002c8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8c7  lea     rbx, WPP_GLOBAL_Control
0x18002c8ce  cmp     rcx, rbx
0x18002c8d1  jz      loc_18002CB55
0x18002c8d7  test    byte ptr [rcx+1Ch], 1
0x18002c8db  jz      loc_18002CB55
0x18002c8e1  mov     r9, [r9+8]
0x18002c8e5  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18002c8ec  mov     rcx, [rcx+10h]
0x18002c8f0  mov     edx, 2Bh ; '+'
0x18002c8f5  call    WPP_SF_S
0x18002c8fa  jmp     loc_18002CB55
0x18002c8ff  cmp     [rbp+50h+arg_28], 14h
0x18002c906  jnb     short loc_18002C950
0x18002c908  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c90f  lea     rbx, WPP_GLOBAL_Control
0x18002c916  cmp     rcx, rbx
0x18002c919  jz      loc_18002CB55
0x18002c91f  test    byte ptr [rcx+1Ch], 1
0x18002c923  jz      loc_18002CB55
0x18002c929  mov     r9, [r9+8]
0x18002c92d  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18002c934  mov     rcx, [rcx+10h]
0x18002c938  mov     edx, 2Ch ; ','
0x18002c93d  call    WPP_SF_S
0x18002c942  jmp     loc_18002CB55
0x18002c950  mov     rcx, [rsi+18h]
0x18002c954  lea     rdx, [rcx+18h]
0x18002c958  cmp     r12w, r13w
0x18002c95c  jz      short loc_18002C968
0x18002c95e  mov     rax, [rdx]
0x18002c961  mov     r8d, [r14+rax+24h]
0x18002c966  jmp     short loc_18002C96C
0x18002c968  mov     r8d, [rcx+20h]
0x18002c96c  movzx   r13d, r15w
0x18002c970  cmp     r13d, r8d
0x18002c973  jnb     loc_18002CB55
0x18002c979  xorps   xmm0, xmm0
0x18002c97c  movzx   r8d, r15w
0x18002c980  xor     eax, eax
0x18002c982  mov     [rbp+50h+var_60], rax
0x18002c986  movups  xmmword ptr [rbp+50h+var_D0.Ptr], xmm0
0x18002c98a  lea     rax, [r8+r8*4]
0x18002c98e  mov     [rbp+50h+var_D0.Ptr], rsi
0x18002c992  lea     rbx, ds:0[rax*8]
0x18002c99a  mov     eax, 0FFFFh
0x18002c99f  movups  [rbp+50h+var_70], xmm0
0x18002c9a3  mov     dword ptr [rbp+50h+var_70+8], r12d
0x18002c9a7  movups  [rbp+50h+var_C0], xmm0
0x18002c9ab  movups  [rbp+50h+var_B0], xmm0
0x18002c9af  movups  [rbp+50h+var_A0], xmm0
0x18002c9b3  movups  [rbp+50h+var_90], xmm0
0x18002c9b7  movups  [rbp+50h+var_80], xmm0
0x18002c9bb  cmp     r12w, ax
0x18002c9bf  jz      loc_18002CA4D
  ... truncated ...
```
