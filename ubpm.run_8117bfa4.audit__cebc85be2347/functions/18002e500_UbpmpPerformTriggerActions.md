# UbpmpPerformTriggerActions

- ea: `0x18002e500`
- end: `0x18002ec28`
- name: `UbpmpPerformTriggerActions`
- size: `1832`
- prototype: `__int64 __usercall@<rax>(struct _UBPM_TRIGGER_CONSUMER_BLOCK *@<rcx>, __int64, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800282b0`

## callees

- `0x1800038d0`
- `0x18000ae00`
- `0x18000cce0`
- `0x18000d928`
- `0x18000e1b0`
- `0x180017110`
- `0x18001af64`
- `0x180026390`
- `0x18002d16c`
- `0x18002e500`
- `0x180030b14`
- `0x180035184`
- `0x180037c0c`
- `0x180040260`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002e7a5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002e7a5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002e7dc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002e7dc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002e950`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002e950`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e7b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e7b1`
- `RPCRT4!UuidEqual` at `0x18002eab9`
- `RPCRT4!UuidEqual` at `0x18002eab9`
- `RPCRT4!UuidCreate` at `0x18002e5b2`
- `RPCRT4!UuidCreate` at `0x18002e5b2`

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
  __int64 *v32; // rcx
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
        v20 = UbpmpMaintenanceTaskCompletedWithinTimePeriod((__int64)a1, &v52);
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
            dword_18004FFE8 = GetCurrentThreadId();
            v30 = UbpmpCheckQueueMaintenanceLauncher();
            dword_18004FFE8 = 0;
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
        if ( (unsigned int)dword_18004F0F0 > 4 )
        {
          LODWORD(v55) = i;
          v31 = *((_QWORD *)a1 + 3);
          LODWORD(v56) = v22;
          v53[0] = v21;
          *((_QWORD *)&v66 + 1) = 4;
          v32 = *(__int64 **)(v31 + 8);
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
            v32 = &qword_1800439C0;
            v34 = 2;
          }
          *((_QWORD *)&v63 + 1) = v34;
          *(_DWORD *)&EventDescriptor.Level = 4;
          UserData.Ptr = (ULONGLONG)off_18004F0F8;
          *(_QWORD *)&v63 = v32;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)off_18004F0F8;
          *(_QWORD *)&v62 = &word_180046326;
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
0x18002e500  push    rbp
0x18002e502  push    rbx
0x18002e503  push    rsi
0x18002e504  push    rdi
0x18002e505  push    r12
0x18002e507  push    r15
0x18002e509  lea     rbp, [rsp-28h]
0x18002e50e  sub     rsp, 128h
0x18002e515  mov     rax, cs:__security_cookie
0x18002e51c  xor     rax, rsp
0x18002e51f  mov     [rbp+50h+var_50], rax
0x18002e523  mov     rdi, [rbp+50h+arg_20]
0x18002e52a  xor     r15d, r15d
0x18002e52d  xorps   xmm0, xmm0
0x18002e530  mov     [rsp+150h+var_110], r15
0x18002e535  movups  xmmword ptr [rsp+150h+Uuid.Data1], xmm0
0x18002e53a  mov     [rsp+150h+var_11F], r15b
0x18002e53f  mov     rbx, rdx
0x18002e542  mov     [rsp+150h+Status], r15d
0x18002e547  mov     rsi, rcx
0x18002e54a  mov     [rsp+150h+var_120], r15b
0x18002e54f  mov     [rsp+150h+var_108], r9
0x18002e554  movzx   r12d, r8w
0x18002e558  mov     qword ptr [rsp+150h+EventDescriptor.Id], rdx
0x18002e55d  call    UbpmpTriggerHandlerPrologue
0x18002e562  test    eax, eax
0x18002e564  jz      short loc_18002E5AD
0x18002e566  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e56d  lea     rbx, WPP_GLOBAL_Control
0x18002e574  cmp     rcx, rbx
0x18002e577  jz      loc_18002EC0B
0x18002e57d  test    byte ptr [rcx+1Ch], 10h
0x18002e581  jz      loc_18002EC0B
0x18002e587  mov     edx, 28h ; '('
0x18002e58c  mov     r9, [rsi+18h]
0x18002e590  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18002e597  mov     rcx, [rcx+10h]
0x18002e59b  mov     [rsp+150h+UserDataCount], eax
0x18002e59f  mov     r9, [r9+8]
0x18002e5a3  call    WPP_SF_Sd
0x18002e5a8  jmp     loc_18002EC0B
0x18002e5ad  lea     rcx, [rsp+150h+Uuid]; Uuid
0x18002e5b2  call    cs:__imp_UuidCreate
0x18002e5b9  nop     dword ptr [rax+rax+00h]
0x18002e5be  test    eax, eax
0x18002e5c0  jz      short loc_18002E5EA
0x18002e5c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e5c9  lea     rbx, WPP_GLOBAL_Control
0x18002e5d0  cmp     rcx, rbx
0x18002e5d3  jz      loc_18002EC0B
0x18002e5d9  test    byte ptr [rcx+1Ch], 1
0x18002e5dd  jz      loc_18002EC0B
0x18002e5e3  mov     edx, 29h ; ')'
0x18002e5e8  jmp     short loc_18002E58C
0x18002e5ea  mov     [rsp+150h+var_30], r13
0x18002e5f2  mov     r13d, 0FFFFh
0x18002e5f8  mov     [rsp+150h+var_38], r14
0x18002e600  cmp     r12w, r13w
0x18002e604  jz      short loc_18002E629
0x18002e606  mov     rdx, [rsi+18h]
0x18002e60a  lea     r14, [r12+r12*2]
0x18002e60e  shl     r14, 4
0x18002e612  lea     rcx, [r12+r12*2]
0x18002e616  add     rcx, rcx
0x18002e619  mov     rax, [rdx+18h]
0x18002e61d  mov     r10d, [rax+r14+24h]
0x18002e622  mov     r8, [rax+rcx*8+28h]
0x18002e627  jmp     short loc_18002E635
0x18002e629  mov     r10d, r15d
0x18002e62c  mov     r14d, 2FFFD0h
0x18002e632  mov     r8, r15; unsigned __int16 **
0x18002e635  lea     r9, [rsp+150h+var_110]; unsigned __int64 *
0x18002e63a  mov     [rsp+150h+var_118], r14
0x18002e63f  mov     edx, r10d; unsigned int
0x18002e642  mov     rcx, rsi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18002e645  call    ?UbpmpGetActionMask@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@KPEAPEAGPEA_K@Z; UbpmpGetActionMask(_UBPM_TRIGGER_CONSUMER_BLOCK *,ulong,ushort * *,unsigned __int64 *)
0x18002e64a  mov     r9, [rsi+18h]
0x18002e64e  mov     rax, [r9+18h]
0x18002e652  mov     ecx, [r14+rax]
0x18002e656  cmp     ecx, 2
0x18002e659  jnz     short loc_18002E674
0x18002e65b  mov     r9b, 1
0x18002e65e  mov     r8d, 1
0x18002e664  mov     rdx, rbx
0x18002e667  mov     rcx, rsi
0x18002e66a  call    ?UbpmpRunConsumerQueuedActions@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@W4_UBPM_QUEUED_ACTION_QUEUE_REASON@@E@Z; UbpmpRunConsumerQueuedActions(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_QUEUED_ACTION_QUEUE_REASON,uchar)
0x18002e66f  jmp     loc_18002EBFB
0x18002e674  cmp     ecx, 3
0x18002e677  jnz     loc_18002E961
0x18002e67d  lea     rdx, [rsp+150h+var_120]
0x18002e682  mov     rcx, rsi
0x18002e685  movzx   edi, r13w
0x18002e689  call    UbpmpMaintenanceTaskCompletedWithinTimePeriod
0x18002e68e  movzx   ecx, [rsp+150h+var_120]
0x18002e693  mov     r14d, eax
0x18002e696  test    eax, eax
0x18002e698  jnz     loc_18002E837
0x18002e69e  test    cl, cl
0x18002e6a0  jnz     loc_18002E837
0x18002e6a6  mov     r13, [rsp+150h+var_110]
0x18002e6ab  lea     rbx, WPP_GLOBAL_Control
0x18002e6b2  mov     edi, r15d
0x18002e6b5  nop     word ptr [rax+rax+00000000h]
0x18002e6c0  mov     rdx, [rsi+18h]
0x18002e6c4  mov     r11d, 0FFFFh
0x18002e6ca  mov     r10, [rsp+150h+var_118]
0x18002e6cf  cmp     r12w, r11w
0x18002e6d3  jz      short loc_18002E6E0
0x18002e6d5  mov     rax, [rdx+18h]
0x18002e6d9  mov     r8d, [r10+rax+24h]
0x18002e6de  jmp     short loc_18002E6E4
0x18002e6e0  mov     r8d, [rdx+20h]
0x18002e6e4  movzx   r15d, di
0x18002e6e8  cmp     r15d, r8d
0x18002e6eb  jnb     loc_18002E82F
0x18002e6f1  xorps   xmm0, xmm0
0x18002e6f4  movzx   r9d, di
0x18002e6f8  xor     eax, eax
0x18002e6fa  mov     [rbp+50h+var_60], rax
0x18002e6fe  movups  xmmword ptr [rbp+50h+var_D0.Ptr], xmm0
0x18002e702  mov     [rbp+50h+var_D0.Ptr], rsi
0x18002e706  lea     rax, [r9+r9*4]
0x18002e70a  lea     r8, ds:0[rax*8]
0x18002e712  movups  [rbp+50h+var_C0], xmm0
0x18002e716  movups  [rbp+50h+var_B0], xmm0
0x18002e71a  movups  [rbp+50h+var_A0], xmm0
0x18002e71e  movups  [rbp+50h+var_90], xmm0
0x18002e722  movups  [rbp+50h+var_80], xmm0
0x18002e726  movups  [rbp+50h+var_70], xmm0
0x18002e72a  cmp     r12w, r11w
0x18002e72e  jz      short loc_18002E743
0x18002e730  mov     rax, [rdx+18h]
0x18002e734  mov     rcx, [rax+r10+28h]
0x18002e739  mov     rax, [rcx+r9*8]
0x18002e73d  mov     qword ptr [rbp+50h+var_C0], rax
0x18002e741  jmp     short loc_18002E74F
0x18002e743  mov     rax, [rdx+28h]
0x18002e747  mov     rcx, [r8+rax]
0x18002e74b  mov     qword ptr [rbp+50h+var_C0], rcx
0x18002e74f  mov     rcx, [rdx+28h]
0x18002e753  lea     rax, [rsp+150h+Uuid]
0x18002e758  add     rcx, r8
0x18002e75b  mov     qword ptr [rbp+50h+var_A0], rax
0x18002e75f  mov     rax, [rsp+150h+var_108]
0x18002e764  mov     qword ptr [rbp+50h+var_80], rax
0x18002e768  mov     qword ptr [rbp+50h+var_90], r13
0x18002e76c  mov     rax, [rcx+20h]
0x18002e770  test    rax, rax
0x18002e773  jz      short loc_18002E781
0x18002e775  test    byte ptr [rax], 10h
0x18002e778  mov     dword ptr [rbp+50h+var_A0+8], 200000h
0x18002e77f  jnz     short loc_18002E788
0x18002e781  mov     dword ptr [rbp+50h+var_A0+8], 0
0x18002e788  mov     qword ptr [rbp+50h+var_D0.Size], rcx
0x18002e78c  lea     rdx, [rbp+50h+var_D0]
0x18002e790  mov     ecx, 3
0x18002e795  mov     dword ptr [rbp+50h+var_70+8], r12d
0x18002e799  call    UbpmpQueueActionInstance
0x18002e79e  lea     rcx, g_MaintenanceLaunchLock
0x18002e7a5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002e7ac  nop     dword ptr [rax+rax+00h]
0x18002e7b1  call    cs:__imp_GetCurrentThreadId
0x18002e7b8  nop     dword ptr [rax+rax+00h]
0x18002e7bd  mov     cs:dword_18004FFE8, eax
0x18002e7c3  call    UbpmpCheckQueueMaintenanceLauncher
0x18002e7c8  lea     rcx, g_MaintenanceLaunchLock
0x18002e7cf  mov     cs:dword_18004FFE8, 0
0x18002e7d9  mov     r14d, eax
0x18002e7dc  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002e7e3  nop     dword ptr [rax+rax+00h]
0x18002e7e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7ef  cmp     rcx, rbx
0x18002e7f2  jz      short loc_18002E827
0x18002e7f4  test    dword ptr [rcx+1Ch], 200h
0x18002e7fb  jz      short loc_18002E827
0x18002e7fd  mov     rax, [rsi+18h]
0x18002e801  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18002e808  mov     rcx, [rcx+10h]
0x18002e80c  mov     edx, 2Ah ; '*'
0x18002e811  mov     dword ptr [rsp+150h+UserData], r14d
0x18002e816  mov     r9d, r15d
0x18002e819  mov     rax, [rax+8]
0x18002e81d  mov     qword ptr [rsp+150h+UserDataCount], rax
0x18002e822  call    WPP_SF_dSd
0x18002e827  inc     di
0x18002e82a  jmp     loc_18002E6C0
0x18002e82f  movzx   ecx, [rsp+150h+var_120]
0x18002e834  xor     r15d, r15d
0x18002e837  mov     eax, cs:dword_18004F0F0
0x18002e83d  cmp     eax, 4
0x18002e840  jbe     loc_18002EBFB
0x18002e846  movzx   eax, di
0x18002e849  mov     dword ptr [rsp+150h+var_110], eax
0x18002e84d  mov     rax, [rsi+18h]
0x18002e851  mov     dword ptr [rsp+150h+var_108], r14d
0x18002e856  mov     [rsp+150h+var_11F], cl
0x18002e85a  mov     qword ptr [rbp+50h+var_80+8], 4
0x18002e862  mov     rcx, [rax+8]
0x18002e866  lea     rax, [rsp+150h+var_108]
0x18002e86b  mov     qword ptr [rbp+50h+var_80], rax
0x18002e86f  lea     rax, [rsp+150h+var_110]
0x18002e874  mov     qword ptr [rbp+50h+var_90], rax
0x18002e878  lea     rax, [rsp+150h+var_11F]
0x18002e87d  mov     qword ptr [rbp+50h+var_A0], rax
0x18002e881  mov     qword ptr [rbp+50h+var_90+8], 4
0x18002e889  mov     qword ptr [rbp+50h+var_A0+8], 1
0x18002e891  test    rcx, rcx
0x18002e894  jz      short loc_18002E8B5
0x18002e896  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002e89d  nop     dword ptr [rax]
0x18002e8a0  cmp     word ptr [rcx+rax*2+2], 0
0x18002e8a6  lea     rax, [rax+1]
0x18002e8aa  jnz     short loc_18002E8A0
0x18002e8ac  lea     eax, ds:2[rax*2]
0x18002e8b3  jmp     short loc_18002E8C1
0x18002e8b5  lea     rcx, qword_1800439C0
0x18002e8bc  mov     eax, 2
0x18002e8c1  mov     dword ptr [rbp+50h+var_B0+8], eax
0x18002e8c4  lea     rdx, [rsp+150h+EventDescriptor]; EventDescriptor
0x18002e8c9  movzx   eax, cs:word_18004631C
0x18002e8d0  xor     r9d, r9d; RelatedActivityId
0x18002e8d3  mov     dword ptr [rsp+150h+EventDescriptor.Level], eax
0x18002e8d7  xor     r8d, r8d; ActivityId
0x18002e8da  mov     rax, cs:off_18004F0F8
0x18002e8e1  mov     [rbp+50h+var_D0.Ptr], rax
0x18002e8e5  mov     qword ptr [rbp+50h+var_B0], rcx
0x18002e8e9  lea     rcx, _TraceLoggingMetadata
0x18002e8f0  mov     dword ptr [rbp+50h+var_B0+0Ch], r15d
0x18002e8f4  mov     dword ptr [rsp+150h+EventDescriptor.Id], 0B000000h
0x18002e8fc  mov     [rsp+150h+EventDescriptor.Keyword], r15
0x18002e901  movzx   eax, word ptr [rax]
0x18002e904  mov     [rbp+50h+var_D0.Size], eax
0x18002e907  lea     rax, word_180046326
0x18002e90e  mov     qword ptr [rbp+50h+var_C0], rax
0x18002e912  lea     rax, _TraceLoggingMetadataEnd
0x18002e919  sub     eax, ecx
0x18002e91b  mov     dword ptr [rbp+50h+var_D0.0Ch], 2
0x18002e922  mov     dword ptr [rbp+50h+var_C0+8], 5Bh ; '['
0x18002e929  mov     dword ptr [rbp+50h+var_C0+0Ch], 1
0x18002e930  mov     dword ptr [rsp+150h+var_118], eax
0x18002e934  mov     eax, dword ptr [rsp+150h+var_118]
0x18002e938  mov     rcx, cs:RegHandle; RegHandle
0x18002e93f  lea     rax, [rbp+50h+var_D0]
0x18002e943  mov     [rsp+150h+UserData], rax; UserData
0x18002e948  mov     [rsp+150h+UserDataCount], 6; UserDataCount
0x18002e950  call    cs:__imp_EventWriteTransfer
0x18002e957  nop     dword ptr [rax+rax+00h]
0x18002e95c  jmp     loc_18002EBFB
0x18002e961  test    rdi, rdi
0x18002e964  jnz     short loc_18002E9A5
0x18002e966  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e96d  lea     rbx, WPP_GLOBAL_Control
0x18002e974  cmp     rcx, rbx
0x18002e977  jz      loc_18002EBFB
0x18002e97d  test    byte ptr [rcx+1Ch], 1
0x18002e981  jz      loc_18002EBFB
0x18002e987  mov     r9, [r9+8]
0x18002e98b  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18002e992  mov     rcx, [rcx+10h]
0x18002e996  mov     edx, 2Bh ; '+'
0x18002e99b  call    WPP_SF_S
0x18002e9a0  jmp     loc_18002EBFB
0x18002e9a5  cmp     [rbp+50h+arg_28], 14h
0x18002e9ac  jnb     short loc_18002E9F0
0x18002e9ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9b5  lea     rbx, WPP_GLOBAL_Control
0x18002e9bc  cmp     rcx, rbx
0x18002e9bf  jz      loc_18002EBFB
0x18002e9c5  test    byte ptr [rcx+1Ch], 1
0x18002e9c9  jz      loc_18002EBFB
0x18002e9cf  mov     r9, [r9+8]
0x18002e9d3  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18002e9da  mov     rcx, [rcx+10h]
0x18002e9de  mov     edx, 2Ch ; ','
0x18002e9e3  call    WPP_SF_S
0x18002e9e8  jmp     loc_18002EBFB
0x18002e9f0  mov     rcx, [rsi+18h]
0x18002e9f4  lea     rdx, [rcx+18h]
0x18002e9f8  cmp     r12w, r13w
0x18002e9fc  jz      short loc_18002EA08
0x18002e9fe  mov     rax, [rdx]
0x18002ea01  mov     r8d, [r14+rax+24h]
0x18002ea06  jmp     short loc_18002EA0C
0x18002ea08  mov     r8d, [rcx+20h]
0x18002ea0c  movzx   r13d, r15w
0x18002ea10  cmp     r13d, r8d
0x18002ea13  jnb     loc_18002EBFB
0x18002ea19  xorps   xmm0, xmm0
0x18002ea1c  movzx   r8d, r15w
0x18002ea20  xor     eax, eax
0x18002ea22  mov     [rbp+50h+var_60], rax
0x18002ea26  movups  xmmword ptr [rbp+50h+var_D0.Ptr], xmm0
0x18002ea2a  lea     rax, [r8+r8*4]
0x18002ea2e  mov     [rbp+50h+var_D0.Ptr], rsi
0x18002ea32  lea     rbx, ds:0[rax*8]
0x18002ea3a  mov     eax, 0FFFFh
0x18002ea3f  movups  [rbp+50h+var_70], xmm0
0x18002ea43  mov     dword ptr [rbp+50h+var_70+8], r12d
0x18002ea47  movups  [rbp+50h+var_C0], xmm0
0x18002ea4b  movups  [rbp+50h+var_B0], xmm0
  ... truncated ...
```
