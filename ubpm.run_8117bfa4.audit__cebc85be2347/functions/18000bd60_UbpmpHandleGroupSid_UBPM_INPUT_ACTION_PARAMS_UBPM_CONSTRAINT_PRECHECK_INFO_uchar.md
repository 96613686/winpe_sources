# UbpmpHandleGroupSid(_UBPM_INPUT_ACTION_PARAMS *,_UBPM_CONSTRAINT_PRECHECK_INFO *,uchar *)

- ea: `0x18000bd60`
- end: `0x18000c265`
- name: `?UbpmpHandleGroupSid@@YAKPEAU_UBPM_INPUT_ACTION_PARAMS@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAE@Z`
- size: `1285`
- prototype: `unsigned int __fastcall(struct _UBPM_INPUT_ACTION_PARAMS *, struct _UBPM_CONSTRAINT_PRECHECK_INFO *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000aff0`

## callees

- `0x180007000`
- `0x18000bd60`
- `0x18000c270`
- `0x18000cce0`
- `0x18001af64`
- `0x180032f78`
- `0x180037c0c`
- `0x180038520`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000bef0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000bef0`
- `ntdll!RtlFreeHeap` at `0x18000c063`
- `ntdll!RtlFreeHeap` at `0x18000c092`
- `ntdll!RtlFreeHeap` at `0x18000c063`
- `ntdll!RtlFreeHeap` at `0x18000c092`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c198`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c198`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bfe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c03b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bfe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c03b`
- `RPCRT4!UuidCreate` at `0x18000be84`
- `RPCRT4!UuidCreate` at `0x18000be84`

## pseudocode

```c
__int64 __fastcall UbpmpHandleGroupSid(
        struct _UBPM_INPUT_ACTION_PARAMS *a1,
        struct _UBPM_CONSTRAINT_PRECHECK_INFO *a2,
        unsigned __int8 *a3)
{
  unsigned int v3; // esi
  bool v4; // zf
  int v7; // r15d
  __int64 v8; // rax
  unsigned int InteractiveUserSidAndToken; // edi
  unsigned int i; // r14d
  __int64 v12; // rax
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // rcx
  unsigned int j; // ebx
  __int64 v17; // rsi
  void *v18; // rcx
  void *v19; // r8
  _QWORD *v20; // rcx
  int v21; // edx
  unsigned __int8 v22[4]; // [rsp+B8h] [rbp-80h] BYREF
  unsigned int v23[3]; // [rsp+BCh] [rbp-7Ch] BYREF
  __int64 v24; // [rsp+C8h] [rbp-70h]
  HANDLE hObject; // [rsp+D0h] [rbp-68h] BYREF
  struct _UBPM_CONSTRAINT_PRECHECK_INFO *v26; // [rsp+D8h] [rbp-60h]
  UUID Uuid; // [rsp+E0h] [rbp-58h] BYREF

  v3 = 0;
  v4 = (*((_DWORD *)a1 + 14) & 0x20000) == 0;
  v26 = a2;
  *(_QWORD *)&v23[1] = 0;
  hObject = 0;
  if ( v4 )
    v7 = -1;
  else
    v7 = *((_DWORD *)a1 + 9);
  v8 = *((_QWORD *)a1 + 1);
  v23[0] = 0;
  Uuid = 0;
  v22[0] = 0;
  InteractiveUserSidAndToken = UbpmGetInteractiveUserSidAndToken(
                                 0,
                                 *(PSID *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 24) + 32LL) + 8LL) + 8LL),
                                 v7,
                                 &v23[1],
                                 v23);
  if ( !InteractiveUserSidAndToken )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_Sidd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL),
        *((_QWORD *)a1 + 8),
        v7,
        v23[0]);
    for ( i = 0; ; ++i )
    {
      if ( i >= v23[0] )
      {
        *a3 = 1;
        goto LABEL_10;
      }
      if ( v7 == -1 || *(_DWORD *)(32LL * i + *(_QWORD *)&v23[1] + 16) == v7 )
      {
        InteractiveUserSidAndToken = UuidCreate(&Uuid);
        if ( InteractiveUserSidAndToken )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v21 = 63;
LABEL_46:
            WPP_SF_Sd(
              v20[2],
              v21,
              (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL),
              InteractiveUserSidAndToken);
          }
          goto LABEL_10;
        }
        v22[0] = 0;
        while ( v3 < *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 32LL) )
        {
          v12 = *((_QWORD *)a1 + 8);
          if ( _bittest64(&v12, v3) )
          {
            v24 = 32LL * i;
            if ( DuplicateTokenEx(
                   *(HANDLE *)(v24 + *(_QWORD *)&v23[1] + 8),
                   0x2000000u,
                   0,
                   SecurityImpersonation,
                   TokenPrimary,
                   &hObject) )
            {
              LODWORD(v24) = UbpmpLaunchOneTask(
                               *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)a1,
                               v26,
                               (struct _UBPM_ACTION_PARAMS *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 40LL)
                                                            + 40LL * v3),
                               *(_DWORD *)(*(_QWORD *)&v23[1] + v24 + 16),
                               *(PSID *)(*(_QWORD *)&v23[1] + v24),
                               &hObject,
                               0,
                               &Uuid,
                               *((_DWORD *)a1 + 14) | 0x20000u,
                               *((_QWORD *)a1 + 8),
                               *((_DWORD *)a1 + 18),
                               *((_QWORD *)a1 + 10),
                               *((_BYTE *)a1 + 88),
                               *((const unsigned __int16 ***)a1 + 12),
                               *((_DWORD *)a1 + 8),
                               *((unsigned __int8 **)a1 + 3),
                               *((_DWORD *)a1 + 26),
                               *((void **)a1 + 5),
                               *((_BYTE *)a1 + 108),
                               *((const unsigned __int16 ***)a1 + 14),
                               v22);
              if ( hObject )
                CloseHandle(hObject);
              v13 = *((unsigned int *)a1 + 26);
              v14 = *((unsigned int *)a1 + 14);
              v15 = *(_QWORD *)a1;
              if ( v22[0] == 1 )
              {
                UbpmpExecutionTimeLimitCheckSet(v15, &Uuid, v14, v13);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  WPP_SF_dSd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    65,
                    (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                    v3,
                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL),
                    v24);
                break;
              }
              UbpmpExecutionTimeLimitCheckSet(v15, &Uuid, v14, v13);
              if ( (_DWORD)v24 )
              {
                InteractiveUserSidAndToken = v24;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    66,
                    (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL),
                    v24);
              }
            }
            else
            {
              InteractiveUserSidAndToken = GetLastError();
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  64,
                  WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                  *(unsigned int *)(v24 + *(_QWORD *)&v23[1] + 16));
            }
          }
          ++v3;
        }
        v3 = 0;
      }
    }
  }
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v21 = 61;
    goto LABEL_46;
  }
LABEL_10:
  if ( *(_QWORD *)&v23[1] )
  {
    for ( j = 0; j < v23[0]; ++j )
    {
      v17 = 32LL * j;
      v18 = *(void **)(v17 + *(_QWORD *)&v23[1] + 8);
      if ( v18 )
        CloseHandle(v18);
      v19 = *(void **)(v17 + *(_QWORD *)&v23[1]);
      if ( v19 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
    }
    if ( *(_QWORD *)&v23[1] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)&v23[1]);
  }
  return InteractiveUserSidAndToken;
}

```

## disassembly

```asm
0x18000bd60  mov     r11, rsp
0x18000bd63  push    rbp
0x18000bd64  push    rbx
0x18000bd65  push    rsi
0x18000bd66  push    rdi
0x18000bd67  lea     rbp, [r11+8]
0x18000bd6b  sub     rsp, 108h
0x18000bd72  mov     rax, cs:__security_cookie
0x18000bd79  xor     rax, rsp
0x18000bd7c  mov     [rbp-10h+var_38], rax
0x18000bd80  xor     esi, esi
0x18000bd82  mov     [r11+20h], r12
0x18000bd86  test    dword ptr [rcx+38h], 20000h
0x18000bd8d  mov     r12, r8
0x18000bd90  mov     [r11-38h], r15
0x18000bd94  mov     rbx, rcx
0x18000bd97  mov     [rbp-10h+var_50], rdx
0x18000bd9b  mov     qword ptr [rbp-10h+var_6C+4], rsi
0x18000bd9f  mov     [rbp-10h+hObject], rsi
0x18000bda3  jnz     loc_18000C0ED
0x18000bda9  mov     r15d, 0FFFFFFFFh
0x18000bdaf  mov     rax, [rcx+8]
0x18000bdb3  lea     r9, [rbp-10h+var_6C+4]
0x18000bdb7  mov     dword ptr [rbp-10h+var_6C], esi
0x18000bdba  xorps   xmm0, xmm0
0x18000bdbd  movups  xmmword ptr [rbp-10h+Uuid.Data1], xmm0
0x18000bdc1  mov     [rbp-10h+var_70], sil
0x18000bdc5  mov     r8d, r15d
0x18000bdc8  mov     rcx, [rax+18h]
0x18000bdcc  mov     [rsp+100h], r13
0x18000bdd4  mov     [rsp+120h+var_28], r14
0x18000bddc  mov     rax, [rcx+20h]
0x18000bde0  xor     ecx, ecx; pSid2
0x18000bde2  mov     rdx, [rax+8]
0x18000bde6  lea     rax, [rbp-10h+var_6C]
0x18000bdea  mov     qword ptr [rsp+120h+TokenType], rax; __int64
0x18000bdef  mov     rdx, [rdx+8]; SidToCheck
0x18000bdf3  call    UbpmGetInteractiveUserSidAndToken
0x18000bdf8  mov     edi, eax
0x18000bdfa  test    eax, eax
0x18000bdfc  jnz     loc_18000C0A3
0x18000be02  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be09  lea     r13, WPP_GLOBAL_Control
0x18000be10  cmp     rcx, r13
0x18000be13  jz      short loc_18000BE22
0x18000be15  test    dword ptr [rcx+1Ch], 200h
0x18000be1c  jnz     loc_18000C22B
0x18000be22  mov     r14d, esi
0x18000be25  cmp     r14d, dword ptr [rbp-10h+var_6C]
0x18000be29  jb      short loc_18000BE76
0x18000be2b  mov     byte ptr [r12], 1
0x18000be30  cmp     qword ptr [rbp-10h+var_6C+4], 0
0x18000be35  mov     r15, [rsp+120h+var_30]
0x18000be3d  mov     r14, [rsp+120h+var_28]
0x18000be45  mov     r13, [rsp+100h]
0x18000be4d  mov     r12, [rsp+120h+arg_18]
0x18000be55  jnz     loc_18000C01F
0x18000be5b  mov     eax, edi
0x18000be5d  mov     rcx, [rbp-10h+var_38]
0x18000be61  xor     rcx, rsp; StackCookie
0x18000be64  call    __security_check_cookie
0x18000be69  add     rsp, 108h
0x18000be70  pop     rdi
0x18000be71  pop     rsi
0x18000be72  pop     rbx
0x18000be73  pop     rbp
0x18000be74  retn
0x18000be76  cmp     r15d, 0FFFFFFFFh
0x18000be7a  jnz     loc_18000C0F6
0x18000be80  lea     rcx, [rbp-10h+Uuid]; Uuid
0x18000be84  call    cs:__imp_UuidCreate
0x18000be8b  nop     dword ptr [rax+rax+00h]
0x18000be90  mov     edi, eax
0x18000be92  test    eax, eax
0x18000be94  jnz     loc_18000C155
0x18000be9a  mov     [rbp-10h+var_70], al
0x18000be9d  mov     rax, [rbx]
0x18000bea0  mov     rcx, [rax+18h]
0x18000bea4  cmp     esi, [rcx+20h]
0x18000bea7  jnb     loc_18000C0E3
0x18000bead  mov     rax, [rbx+40h]
0x18000beb1  mov     ecx, esi
0x18000beb3  bt      rax, rcx
0x18000beb7  jnb     loc_18000C018
0x18000bebd  lea     rcx, [rbp-10h+hObject]
0x18000bec1  mov     eax, r14d
0x18000bec4  mov     [rsp+120h+phNewToken], rcx; phNewToken
0x18000bec9  mov     r9d, 2; ImpersonationLevel
0x18000becf  mov     rcx, qword ptr [rbp-10h+var_6C+4]
0x18000bed3  xor     r8d, r8d; lpTokenAttributes
0x18000bed6  shl     rax, 5
0x18000beda  mov     edx, 2000000h; dwDesiredAccess
0x18000bedf  mov     [rbp-10h+var_60], rax
0x18000bee3  mov     [rsp+120h+TokenType], 1; TokenType
0x18000beeb  mov     rcx, [rax+rcx+8]; hExistingToken
0x18000bef0  call    cs:__imp_DuplicateTokenEx
0x18000bef7  nop     dword ptr [rax+rax+00h]
0x18000befc  test    eax, eax
0x18000befe  jz      loc_18000C198
0x18000bf04  mov     r11, [rbx]
0x18000bf07  mov     r10d, [rbx+38h]
0x18000bf0b  mov     r9, [rbp-10h+var_60]
0x18000bf0f  bts     r10d, 11h
0x18000bf14  add     r9, qword ptr [rbp-10h+var_6C+4]
0x18000bf18  mov     rdx, [r11+18h]
0x18000bf1c  mov     eax, esi
0x18000bf1e  lea     rcx, [rax+rax*4]
0x18000bf22  mov     rax, [rdx+28h]
0x18000bf26  mov     rdx, [rbp-10h+var_50]; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18000bf2a  lea     r8, [rax+rcx*8]; struct _UBPM_ACTION_PARAMS *
0x18000bf2e  mov     rcx, r11; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18000bf31  lea     rax, [rbp-10h+var_70]
0x18000bf35  mov     [rsp+0A0h], rax; unsigned __int8 *
0x18000bf3d  mov     rax, [rbx+70h]
0x18000bf41  mov     [rsp+120h+var_88], rax; unsigned __int16 **
0x18000bf49  movzx   eax, byte ptr [rbx+6Ch]
0x18000bf4d  mov     [rsp+120h+var_90], al; unsigned __int8
0x18000bf54  mov     rax, [rbx+28h]
0x18000bf58  mov     [rsp+120h+var_98], rax; void *
0x18000bf60  mov     eax, [rbx+68h]
0x18000bf63  mov     [rsp+120h+var_A0], eax; unsigned int
0x18000bf6a  mov     rax, [rbx+18h]
0x18000bf6e  mov     [rsp+120h+var_A8], rax; unsigned __int8 *
0x18000bf73  mov     eax, [rbx+20h]
0x18000bf76  mov     [rsp+120h+var_B0], eax; unsigned int
0x18000bf7a  mov     rax, [rbx+60h]
0x18000bf7e  mov     [rsp+120h+var_B8], rax; unsigned __int16 **
0x18000bf83  movzx   eax, byte ptr [rbx+58h]
0x18000bf87  mov     [rsp+120h+var_C0], al; char
0x18000bf8b  mov     rax, [rbx+50h]
0x18000bf8f  mov     [rsp+120h+var_C8], rax; unsigned __int64
0x18000bf94  mov     eax, [rbx+48h]
0x18000bf97  mov     [rsp+120h+var_D0], eax; unsigned int
0x18000bf9b  mov     rax, [rbx+40h]
0x18000bf9f  mov     [rsp+120h+var_D8], rax; unsigned __int64
0x18000bfa4  lea     rax, [rbp-10h+Uuid]
0x18000bfa8  mov     [rsp+120h+var_E0], r10d; unsigned int
0x18000bfad  mov     [rsp+120h+var_E8], rax; struct _GUID *
0x18000bfb2  lea     rax, [rbp-10h+hObject]
0x18000bfb6  mov     [rsp+120h+var_F0], 0; void *
0x18000bfbf  mov     [rsp+120h+phNewToken], rax; void **
0x18000bfc4  mov     rax, [r9]
0x18000bfc7  mov     r9d, [r9+10h]; unsigned int
0x18000bfcb  mov     qword ptr [rsp+120h+TokenType], rax; pSid
0x18000bfd0  call    ?UbpmpLaunchOneTask@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAU_UBPM_ACTION_PARAMS@@KPEAXPEAPEAX3PEAU_GUID@@K_KK6EPEAPEBGKPEAEK3E78@Z; UbpmpLaunchOneTask(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_ACTION_PARAMS *,ulong,void *,void * *,void *,_GUID *,ulong,unsigned __int64,ulong,unsigned __int64,uchar,ushort const * *,ulong,uchar *,ulong,void *,uchar,ushort const * *,uchar *)
0x18000bfd5  mov     rcx, [rbp-10h+hObject]; hObject
0x18000bfd9  mov     dword ptr [rbp-10h+var_60], eax
0x18000bfdc  test    rcx, rcx
0x18000bfdf  jz      short loc_18000BFED
0x18000bfe1  call    cs:__imp_CloseHandle
0x18000bfe8  nop     dword ptr [rax+rax+00h]
0x18000bfed  cmp     [rbp-10h+var_70], 1
0x18000bff1  lea     rdx, [rbp-10h+Uuid]
0x18000bff5  mov     r9d, [rbx+68h]
0x18000bff9  mov     r8d, [rbx+38h]
0x18000bffd  mov     rcx, [rbx]
0x18000c000  jz      loc_18000C0CE
0x18000c006  call    UbpmpExecutionTimeLimitCheckSet
0x18000c00b  mov     r8d, dword ptr [rbp-10h+var_60]
0x18000c00f  test    r8d, r8d
0x18000c012  jnz     loc_18000C10E
0x18000c018  inc     esi
0x18000c01a  jmp     loc_18000BE9D
0x18000c01f  cmp     dword ptr [rbp-10h+var_6C], 0
0x18000c023  mov     ebx, esi
0x18000c025  jbe     short loc_18000C076
0x18000c027  mov     rax, qword ptr [rbp-10h+var_6C+4]
0x18000c02b  mov     esi, ebx
0x18000c02d  shl     rsi, 5
0x18000c031  mov     rcx, [rsi+rax+8]; hObject
0x18000c036  test    rcx, rcx
0x18000c039  jz      short loc_18000C047
0x18000c03b  call    cs:__imp_CloseHandle
0x18000c042  nop     dword ptr [rax+rax+00h]
0x18000c047  mov     rax, qword ptr [rbp-10h+var_6C+4]
0x18000c04b  mov     r8, [rsi+rax]; P
0x18000c04f  test    r8, r8
0x18000c052  jz      short loc_18000C06F
0x18000c054  mov     rcx, gs:60h
0x18000c05d  xor     edx, edx; Flags
0x18000c05f  mov     rcx, [rcx+30h]; HeapHandle
0x18000c063  call    cs:__imp_RtlFreeHeap
0x18000c06a  nop     dword ptr [rax+rax+00h]
0x18000c06f  inc     ebx
0x18000c071  cmp     ebx, dword ptr [rbp-10h+var_6C]
0x18000c074  jb      short loc_18000C027
0x18000c076  mov     r8, qword ptr [rbp-10h+var_6C+4]; P
0x18000c07a  test    r8, r8
0x18000c07d  jz      loc_18000BE5B
0x18000c083  mov     rcx, gs:60h
0x18000c08c  xor     edx, edx; Flags
0x18000c08e  mov     rcx, [rcx+30h]; HeapHandle
0x18000c092  call    cs:__imp_RtlFreeHeap
0x18000c099  nop     dword ptr [rax+rax+00h]
0x18000c09e  jmp     loc_18000BE5B
0x18000c0a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0aa  lea     r13, WPP_GLOBAL_Control
0x18000c0b1  cmp     rcx, r13
0x18000c0b4  jz      loc_18000BE30
0x18000c0ba  test    byte ptr [rcx+1Ch], 1
0x18000c0be  jz      loc_18000BE30
0x18000c0c4  mov     edx, 3Dh ; '='
0x18000c0c9  jmp     loc_18000C174
0x18000c0ce  call    UbpmpExecutionTimeLimitCheckSet
0x18000c0d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0da  cmp     rcx, r13
0x18000c0dd  jnz     loc_18000C1EB
0x18000c0e3  xor     esi, esi
0x18000c0e5  inc     r14d
0x18000c0e8  jmp     loc_18000BE25
0x18000c0ed  mov     r15d, [rcx+24h]
0x18000c0f1  jmp     loc_18000BDAF
0x18000c0f6  mov     rax, qword ptr [rbp-10h+var_6C+4]
0x18000c0fa  mov     ecx, r14d
0x18000c0fd  shl     rcx, 5
0x18000c101  cmp     [rcx+rax+10h], r15d
0x18000c106  jz      loc_18000BE80
0x18000c10c  jmp     short loc_18000C0E5
0x18000c10e  mov     edi, r8d
0x18000c111  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c118  cmp     rcx, r13
0x18000c11b  jz      loc_18000C018
0x18000c121  test    byte ptr [rcx+1Ch], 1
0x18000c125  jz      loc_18000C018
0x18000c12b  mov     rax, [rbx]
0x18000c12e  mov     edx, 42h ; 'B'
0x18000c133  mov     rcx, [rcx+10h]
0x18000c137  mov     [rsp+120h+TokenType], r8d
0x18000c13c  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000c143  mov     r9, [rax+18h]
0x18000c147  mov     r9, [r9+8]
0x18000c14b  call    WPP_SF_Sd
0x18000c150  jmp     loc_18000C018
0x18000c155  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c15c  cmp     rcx, r13
0x18000c15f  jz      loc_18000BE30
0x18000c165  test    byte ptr [rcx+1Ch], 1
0x18000c169  jz      loc_18000BE30
0x18000c16f  mov     edx, 3Fh ; '?'
0x18000c174  mov     rax, [rbx]
0x18000c177  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000c17e  mov     rcx, [rcx+10h]
0x18000c182  mov     [rsp+120h+TokenType], edi
0x18000c186  mov     r9, [rax+18h]
0x18000c18a  mov     r9, [r9+8]
0x18000c18e  call    WPP_SF_Sd
0x18000c193  jmp     loc_18000BE30
0x18000c198  call    cs:__imp_GetLastError
0x18000c19f  nop     dword ptr [rax+rax+00h]
0x18000c1a4  mov     edi, eax
0x18000c1a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1ad  cmp     rcx, r13
0x18000c1b0  jz      loc_18000C018
0x18000c1b6  test    byte ptr [rcx+1Ch], 1
0x18000c1ba  jz      loc_18000C018
0x18000c1c0  mov     r9, qword ptr [rbp-10h+var_6C+4]
0x18000c1c4  mov     edx, 40h ; '@'
0x18000c1c9  mov     r8, [rbp-10h+var_60]
0x18000c1cd  mov     rcx, [rcx+10h]
0x18000c1d1  mov     [rsp+120h+TokenType], eax
0x18000c1d5  mov     r9d, [r8+r9+10h]
0x18000c1da  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000c1e1  call    WPP_SF_dd
0x18000c1e6  jmp     loc_18000C018
0x18000c1eb  test    byte ptr [rcx+1Ch], 4
0x18000c1ef  jz      loc_18000C0E3
0x18000c1f5  mov     rax, [rbx]
0x18000c1f8  mov     edx, 41h ; 'A'
0x18000c1fd  mov     r8d, dword ptr [rbp-10h+var_60]
0x18000c201  mov     r9d, esi
0x18000c204  mov     rcx, [rcx+10h]
0x18000c208  mov     dword ptr [rsp+120h+phNewToken], r8d
0x18000c20d  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000c214  mov     rax, [rax+18h]
0x18000c218  mov     rax, [rax+8]
0x18000c21c  mov     qword ptr [rsp+120h+TokenType], rax
0x18000c221  call    WPP_SF_dSd
0x18000c226  jmp     loc_18000C0E3
0x18000c22b  mov     rax, [rbx]
0x18000c22e  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000c235  mov     rcx, [rcx+10h]
0x18000c239  mov     edx, 3Eh ; '>'
0x18000c23e  mov     r9, [rax+18h]
0x18000c242  mov     eax, dword ptr [rbp-10h+var_6C]
0x18000c245  mov     dword ptr [rsp+120h+var_F0], eax
0x18000c249  mov     rax, [rbx+40h]
0x18000c24d  mov     r9, [r9+8]
0x18000c251  mov     dword ptr [rsp+120h+phNewToken], r15d
0x18000c256  mov     qword ptr [rsp+120h+TokenType], rax
0x18000c25b  call    WPP_SF_Sidd
0x18000c260  jmp     loc_18000BE22
```
