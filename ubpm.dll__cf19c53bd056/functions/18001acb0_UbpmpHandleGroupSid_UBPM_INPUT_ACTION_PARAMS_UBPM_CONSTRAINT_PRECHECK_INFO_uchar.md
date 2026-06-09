# UbpmpHandleGroupSid(_UBPM_INPUT_ACTION_PARAMS *,_UBPM_CONSTRAINT_PRECHECK_INFO *,uchar *)

- ea: `0x18001acb0`
- end: `0x18001b18a`
- name: `?UbpmpHandleGroupSid@@YAKPEAU_UBPM_INPUT_ACTION_PARAMS@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAE@Z`
- size: `1242`
- prototype: `unsigned int __fastcall(struct _UBPM_INPUT_ACTION_PARAMS *, struct _UBPM_CONSTRAINT_PRECHECK_INFO *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019fb0`

## callees

- `0x180006650`
- `0x18001acb0`
- `0x18001b190`
- `0x18001c000`
- `0x18001e9f4`
- `0x180030cec`
- `0x1800356cc`
- `0x180035f88`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001ae39`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001ae39`
- `ntdll!RtlFreeHeap` at `0x18001af9a`
- `ntdll!RtlFreeHeap` at `0x18001afc3`
- `ntdll!RtlFreeHeap` at `0x18001af9a`
- `ntdll!RtlFreeHeap` at `0x18001afc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af78`
- `RPCRT4!UuidCreate` at `0x18001add3`
- `RPCRT4!UuidCreate` at `0x18001add3`

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
  DWORD LastError; // eax
  unsigned __int8 v23[4]; // [rsp+B8h] [rbp-80h] BYREF
  unsigned int v24[3]; // [rsp+BCh] [rbp-7Ch] BYREF
  __int64 v25; // [rsp+C8h] [rbp-70h]
  HANDLE hObject; // [rsp+D0h] [rbp-68h] BYREF
  struct _UBPM_CONSTRAINT_PRECHECK_INFO *v27; // [rsp+D8h] [rbp-60h]
  UUID Uuid; // [rsp+E0h] [rbp-58h] BYREF

  v3 = 0;
  v4 = (*((_DWORD *)a1 + 14) & 0x20000) == 0;
  v27 = a2;
  *(_QWORD *)&v24[1] = 0;
  hObject = 0;
  if ( v4 )
    v7 = -1;
  else
    v7 = *((_DWORD *)a1 + 9);
  v8 = *((_QWORD *)a1 + 1);
  v24[0] = 0;
  Uuid = 0;
  v23[0] = 0;
  InteractiveUserSidAndToken = UbpmGetInteractiveUserSidAndToken(
                                 0,
                                 *(PSID *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 24) + 32LL) + 8LL) + 8LL),
                                 v7,
                                 &v24[1],
                                 v24);
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
        v24[0]);
    for ( i = 0; ; ++i )
    {
      if ( i >= v24[0] )
      {
        *a3 = 1;
        goto LABEL_10;
      }
      if ( v7 == -1 || *(_DWORD *)(32LL * i + *(_QWORD *)&v24[1] + 16) == v7 )
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
        v23[0] = 0;
        while ( v3 < *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 32LL) )
        {
          v12 = *((_QWORD *)a1 + 8);
          if ( _bittest64(&v12, v3) )
          {
            v25 = 32LL * i;
            if ( DuplicateTokenEx(
                   *(HANDLE *)(v25 + *(_QWORD *)&v24[1] + 8),
                   0x2000000u,
                   0,
                   SecurityImpersonation,
                   TokenPrimary,
                   &hObject) )
            {
              LODWORD(v25) = UbpmpLaunchOneTask(
                               *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)a1,
                               v27,
                               (struct _UBPM_ACTION_PARAMS *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 40LL)
                                                            + 40LL * v3),
                               *(_DWORD *)(*(_QWORD *)&v24[1] + v25 + 16),
                               *(PSID *)(*(_QWORD *)&v24[1] + v25),
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
                               v23);
              if ( hObject )
                CloseHandle(hObject);
              v13 = *((unsigned int *)a1 + 26);
              v14 = *((unsigned int *)a1 + 14);
              v15 = *(_QWORD *)a1;
              if ( v23[0] == 1 )
              {
                UbpmpExecutionTimeLimitCheckSet(v15, &Uuid, v14, v13);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  WPP_SF_dSd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    65,
                    (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                    v3,
                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL),
                    v25);
                break;
              }
              UbpmpExecutionTimeLimitCheckSet(v15, &Uuid, v14, v13);
              if ( (_DWORD)v25 )
              {
                InteractiveUserSidAndToken = v25;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    66,
                    (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL),
                    v25);
              }
            }
            else
            {
              LastError = GetLastError();
              InteractiveUserSidAndToken = LastError;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  64,
                  WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                  *(unsigned int *)(v25 + *(_QWORD *)&v24[1] + 16),
                  LastError);
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
  if ( *(_QWORD *)&v24[1] )
  {
    for ( j = 0; j < v24[0]; ++j )
    {
      v17 = 32LL * j;
      v18 = *(void **)(v17 + *(_QWORD *)&v24[1] + 8);
      if ( v18 )
        CloseHandle(v18);
      v19 = *(void **)(v17 + *(_QWORD *)&v24[1]);
      if ( v19 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
    }
    if ( *(_QWORD *)&v24[1] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)&v24[1]);
  }
  return InteractiveUserSidAndToken;
}

```

## disassembly

```asm
0x18001acb0  mov     r11, rsp
0x18001acb3  push    rbp
0x18001acb4  push    rbx
0x18001acb5  push    rsi
0x18001acb6  push    rdi
0x18001acb7  lea     rbp, [r11+8]
0x18001acbb  sub     rsp, 108h
0x18001acc2  mov     rax, cs:__security_cookie
0x18001acc9  xor     rax, rsp
0x18001accc  mov     [rbp-10h+var_38], rax
0x18001acd0  xor     esi, esi
0x18001acd2  mov     [r11+20h], r12
0x18001acd6  test    dword ptr [rcx+38h], 20000h
0x18001acdd  mov     r12, r8
0x18001ace0  mov     [r11-38h], r15
0x18001ace4  mov     rbx, rcx
0x18001ace7  mov     [rbp-10h+var_50], rdx
0x18001aceb  mov     qword ptr [rbp-10h+var_6C+4], rsi
0x18001acef  mov     [rbp-10h+hObject], rsi
0x18001acf3  jnz     loc_18001B018
0x18001acf9  mov     r15d, 0FFFFFFFFh
0x18001acff  mov     rax, [rcx+8]
0x18001ad03  lea     r9, [rbp-10h+var_6C+4]
0x18001ad07  mov     dword ptr [rbp-10h+var_6C], esi
0x18001ad0a  xorps   xmm0, xmm0
0x18001ad0d  movups  xmmword ptr [rbp-10h+Uuid.Data1], xmm0
0x18001ad11  mov     [rbp-10h+var_70], sil
0x18001ad15  mov     r8d, r15d
0x18001ad18  mov     rcx, [rax+18h]
0x18001ad1c  mov     [rsp+100h], r13
0x18001ad24  mov     [rsp+120h+var_28], r14
0x18001ad2c  mov     rax, [rcx+20h]
0x18001ad30  xor     ecx, ecx; pSid2
0x18001ad32  mov     rdx, [rax+8]
0x18001ad36  lea     rax, [rbp-10h+var_6C]
0x18001ad3a  mov     qword ptr [rsp+120h+TokenType], rax; __int64
0x18001ad3f  mov     rdx, [rdx+8]; SidToCheck
0x18001ad43  call    UbpmGetInteractiveUserSidAndToken
0x18001ad48  mov     edi, eax
0x18001ad4a  test    eax, eax
0x18001ad4c  jnz     loc_18001AFCE
0x18001ad52  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad59  lea     r13, WPP_GLOBAL_Control
0x18001ad60  cmp     rcx, r13
0x18001ad63  jz      short loc_18001AD72
0x18001ad65  test    dword ptr [rcx+1Ch], 200h
0x18001ad6c  jnz     loc_18001B150
0x18001ad72  mov     r14d, esi
0x18001ad75  cmp     r14d, dword ptr [rbp-10h+var_6C]
0x18001ad79  jb      short loc_18001ADC5
0x18001ad7b  mov     byte ptr [r12], 1
0x18001ad80  cmp     qword ptr [rbp-10h+var_6C+4], 0
0x18001ad85  mov     r15, [rsp+120h+var_30]
0x18001ad8d  mov     r14, [rsp+120h+var_28]
0x18001ad95  mov     r13, [rsp+100h]
0x18001ad9d  mov     r12, [rsp+120h+arg_18]
0x18001ada5  jnz     loc_18001AF5C
0x18001adab  mov     eax, edi
0x18001adad  mov     rcx, [rbp-10h+var_38]
0x18001adb1  xor     rcx, rsp; StackCookie
0x18001adb4  call    __security_check_cookie
0x18001adb9  add     rsp, 108h
0x18001adc0  pop     rdi
0x18001adc1  pop     rsi
0x18001adc2  pop     rbx
0x18001adc3  pop     rbp
0x18001adc4  retn
0x18001adc5  cmp     r15d, 0FFFFFFFFh
0x18001adc9  jnz     loc_18001B021
0x18001adcf  lea     rcx, [rbp-10h+Uuid]; Uuid
0x18001add3  call    cs:__imp_UuidCreate
0x18001add9  mov     edi, eax
0x18001addb  test    eax, eax
0x18001addd  jnz     loc_18001B080
0x18001ade3  mov     [rbp-10h+var_70], al
0x18001ade6  mov     rax, [rbx]
0x18001ade9  mov     rcx, [rax+18h]
0x18001aded  cmp     esi, [rcx+20h]
0x18001adf0  jnb     loc_18001B00E
0x18001adf6  mov     rax, [rbx+40h]
0x18001adfa  mov     ecx, esi
0x18001adfc  bt      rax, rcx
0x18001ae00  jnb     loc_18001AF55
0x18001ae06  lea     rcx, [rbp-10h+hObject]
0x18001ae0a  mov     eax, r14d
0x18001ae0d  mov     [rsp+120h+phNewToken], rcx; phNewToken
0x18001ae12  mov     r9d, 2; ImpersonationLevel
0x18001ae18  mov     rcx, qword ptr [rbp-10h+var_6C+4]
0x18001ae1c  xor     r8d, r8d; lpTokenAttributes
0x18001ae1f  shl     rax, 5
0x18001ae23  mov     edx, 2000000h; dwDesiredAccess
0x18001ae28  mov     [rbp-10h+var_60], rax
0x18001ae2c  mov     [rsp+120h+TokenType], 1; TokenType
0x18001ae34  mov     rcx, [rax+rcx+8]; hExistingToken
0x18001ae39  call    cs:__imp_DuplicateTokenEx
0x18001ae3f  test    eax, eax
0x18001ae41  jz      loc_18001B0C3
0x18001ae47  mov     r11, [rbx]
0x18001ae4a  mov     r10d, [rbx+38h]
0x18001ae4e  mov     r9, [rbp-10h+var_60]
0x18001ae52  bts     r10d, 11h
0x18001ae57  add     r9, qword ptr [rbp-10h+var_6C+4]
0x18001ae5b  mov     rdx, [r11+18h]
0x18001ae5f  mov     eax, esi
0x18001ae61  lea     rcx, [rax+rax*4]
0x18001ae65  mov     rax, [rdx+28h]
0x18001ae69  mov     rdx, [rbp-10h+var_50]; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18001ae6d  lea     r8, [rax+rcx*8]; struct _UBPM_ACTION_PARAMS *
0x18001ae71  mov     rcx, r11; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18001ae74  lea     rax, [rbp-10h+var_70]
0x18001ae78  mov     [rsp+0A0h], rax; unsigned __int8 *
0x18001ae80  mov     rax, [rbx+70h]
0x18001ae84  mov     [rsp+120h+var_88], rax; unsigned __int16 **
0x18001ae8c  movzx   eax, byte ptr [rbx+6Ch]
0x18001ae90  mov     [rsp+120h+var_90], al; unsigned __int8
0x18001ae97  mov     rax, [rbx+28h]
0x18001ae9b  mov     [rsp+120h+var_98], rax; void *
0x18001aea3  mov     eax, [rbx+68h]
0x18001aea6  mov     [rsp+120h+var_A0], eax; unsigned int
0x18001aead  mov     rax, [rbx+18h]
0x18001aeb1  mov     [rsp+120h+var_A8], rax; unsigned __int8 *
0x18001aeb6  mov     eax, [rbx+20h]
0x18001aeb9  mov     [rsp+120h+var_B0], eax; unsigned int
0x18001aebd  mov     rax, [rbx+60h]
0x18001aec1  mov     [rsp+120h+var_B8], rax; unsigned __int16 **
0x18001aec6  movzx   eax, byte ptr [rbx+58h]
0x18001aeca  mov     [rsp+120h+var_C0], al; char
0x18001aece  mov     rax, [rbx+50h]
0x18001aed2  mov     [rsp+120h+var_C8], rax; unsigned __int64
0x18001aed7  mov     eax, [rbx+48h]
0x18001aeda  mov     [rsp+120h+var_D0], eax; unsigned int
0x18001aede  mov     rax, [rbx+40h]
0x18001aee2  mov     [rsp+120h+var_D8], rax; unsigned __int64
0x18001aee7  lea     rax, [rbp-10h+Uuid]
0x18001aeeb  mov     [rsp+120h+var_E0], r10d; unsigned int
0x18001aef0  mov     [rsp+120h+var_E8], rax; struct _GUID *
0x18001aef5  lea     rax, [rbp-10h+hObject]
0x18001aef9  mov     [rsp+120h+var_F0], 0; void *
0x18001af02  mov     [rsp+120h+phNewToken], rax; void **
0x18001af07  mov     rax, [r9]
0x18001af0a  mov     r9d, [r9+10h]; unsigned int
0x18001af0e  mov     qword ptr [rsp+120h+TokenType], rax; pSid
0x18001af13  call    ?UbpmpLaunchOneTask@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAU_UBPM_ACTION_PARAMS@@KPEAXPEAPEAX3PEAU_GUID@@K_KK6EPEAPEBGKPEAEK3E78@Z; UbpmpLaunchOneTask(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_ACTION_PARAMS *,ulong,void *,void * *,void *,_GUID *,ulong,unsigned __int64,ulong,unsigned __int64,uchar,ushort const * *,ulong,uchar *,ulong,void *,uchar,ushort const * *,uchar *)
0x18001af18  mov     rcx, [rbp-10h+hObject]; hObject
0x18001af1c  mov     dword ptr [rbp-10h+var_60], eax
0x18001af1f  test    rcx, rcx
0x18001af22  jz      short loc_18001AF2A
0x18001af24  call    cs:__imp_CloseHandle
0x18001af2a  cmp     [rbp-10h+var_70], 1
0x18001af2e  lea     rdx, [rbp-10h+Uuid]
0x18001af32  mov     r9d, [rbx+68h]
0x18001af36  mov     r8d, [rbx+38h]
0x18001af3a  mov     rcx, [rbx]
0x18001af3d  jz      loc_18001AFF9
0x18001af43  call    UbpmpExecutionTimeLimitCheckSet
0x18001af48  mov     r8d, dword ptr [rbp-10h+var_60]
0x18001af4c  test    r8d, r8d
0x18001af4f  jnz     loc_18001B039
0x18001af55  inc     esi
0x18001af57  jmp     loc_18001ADE6
0x18001af5c  cmp     dword ptr [rbp-10h+var_6C], 0
0x18001af60  mov     ebx, esi
0x18001af62  jbe     short loc_18001AFA7
0x18001af64  mov     rax, qword ptr [rbp-10h+var_6C+4]
0x18001af68  mov     esi, ebx
0x18001af6a  shl     rsi, 5
0x18001af6e  mov     rcx, [rsi+rax+8]; hObject
0x18001af73  test    rcx, rcx
0x18001af76  jz      short loc_18001AF7E
0x18001af78  call    cs:__imp_CloseHandle
0x18001af7e  mov     rax, qword ptr [rbp-10h+var_6C+4]
0x18001af82  mov     r8, [rsi+rax]; P
0x18001af86  test    r8, r8
0x18001af89  jz      short loc_18001AFA0
0x18001af8b  mov     rcx, gs:60h
0x18001af94  xor     edx, edx; Flags
0x18001af96  mov     rcx, [rcx+30h]; HeapHandle
0x18001af9a  call    cs:__imp_RtlFreeHeap
0x18001afa0  inc     ebx
0x18001afa2  cmp     ebx, dword ptr [rbp-10h+var_6C]
0x18001afa5  jb      short loc_18001AF64
0x18001afa7  mov     r8, qword ptr [rbp-10h+var_6C+4]; P
0x18001afab  test    r8, r8
0x18001afae  jz      loc_18001ADAB
0x18001afb4  mov     rcx, gs:60h
0x18001afbd  xor     edx, edx; Flags
0x18001afbf  mov     rcx, [rcx+30h]; HeapHandle
0x18001afc3  call    cs:__imp_RtlFreeHeap
0x18001afc9  jmp     loc_18001ADAB
0x18001afce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afd5  lea     r13, WPP_GLOBAL_Control
0x18001afdc  cmp     rcx, r13
0x18001afdf  jz      loc_18001AD80
0x18001afe5  test    byte ptr [rcx+1Ch], 1
0x18001afe9  jz      loc_18001AD80
0x18001afef  mov     edx, 3Dh ; '='
0x18001aff4  jmp     loc_18001B09F
0x18001aff9  call    UbpmpExecutionTimeLimitCheckSet
0x18001affe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b005  cmp     rcx, r13
0x18001b008  jnz     loc_18001B110
0x18001b00e  xor     esi, esi
0x18001b010  inc     r14d
0x18001b013  jmp     loc_18001AD75
0x18001b018  mov     r15d, [rcx+24h]
0x18001b01c  jmp     loc_18001ACFF
0x18001b021  mov     rax, qword ptr [rbp-10h+var_6C+4]
0x18001b025  mov     ecx, r14d
0x18001b028  shl     rcx, 5
0x18001b02c  cmp     [rcx+rax+10h], r15d
0x18001b031  jz      loc_18001ADCF
0x18001b037  jmp     short loc_18001B010
0x18001b039  mov     edi, r8d
0x18001b03c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b043  cmp     rcx, r13
0x18001b046  jz      loc_18001AF55
0x18001b04c  test    byte ptr [rcx+1Ch], 1
0x18001b050  jz      loc_18001AF55
0x18001b056  mov     rax, [rbx]
0x18001b059  mov     edx, 42h ; 'B'
0x18001b05e  mov     rcx, [rcx+10h]
0x18001b062  mov     [rsp+120h+TokenType], r8d
0x18001b067  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18001b06e  mov     r9, [rax+18h]
0x18001b072  mov     r9, [r9+8]
0x18001b076  call    WPP_SF_Sd
0x18001b07b  jmp     loc_18001AF55
0x18001b080  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b087  cmp     rcx, r13
0x18001b08a  jz      loc_18001AD80
0x18001b090  test    byte ptr [rcx+1Ch], 1
0x18001b094  jz      loc_18001AD80
0x18001b09a  mov     edx, 3Fh ; '?'
0x18001b09f  mov     rax, [rbx]
0x18001b0a2  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18001b0a9  mov     rcx, [rcx+10h]
0x18001b0ad  mov     [rsp+120h+TokenType], edi
0x18001b0b1  mov     r9, [rax+18h]
0x18001b0b5  mov     r9, [r9+8]
0x18001b0b9  call    WPP_SF_Sd
0x18001b0be  jmp     loc_18001AD80
0x18001b0c3  call    cs:__imp_GetLastError
0x18001b0c9  mov     edi, eax
0x18001b0cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0d2  cmp     rcx, r13
0x18001b0d5  jz      loc_18001AF55
0x18001b0db  test    byte ptr [rcx+1Ch], 1
0x18001b0df  jz      loc_18001AF55
0x18001b0e5  mov     r9, qword ptr [rbp-10h+var_6C+4]
0x18001b0e9  mov     edx, 40h ; '@'
0x18001b0ee  mov     r8, [rbp-10h+var_60]
0x18001b0f2  mov     rcx, [rcx+10h]
0x18001b0f6  mov     [rsp+120h+TokenType], eax
0x18001b0fa  mov     r9d, [r8+r9+10h]
0x18001b0ff  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18001b106  call    WPP_SF_dd
0x18001b10b  jmp     loc_18001AF55
0x18001b110  test    byte ptr [rcx+1Ch], 4
0x18001b114  jz      loc_18001B00E
0x18001b11a  mov     rax, [rbx]
0x18001b11d  mov     edx, 41h ; 'A'
0x18001b122  mov     r8d, dword ptr [rbp-10h+var_60]
0x18001b126  mov     r9d, esi
0x18001b129  mov     rcx, [rcx+10h]
0x18001b12d  mov     dword ptr [rsp+120h+phNewToken], r8d
0x18001b132  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18001b139  mov     rax, [rax+18h]
0x18001b13d  mov     rax, [rax+8]
0x18001b141  mov     qword ptr [rsp+120h+TokenType], rax
0x18001b146  call    WPP_SF_dSd
0x18001b14b  jmp     loc_18001B00E
0x18001b150  mov     rax, [rbx]
0x18001b153  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18001b15a  mov     rcx, [rcx+10h]
0x18001b15e  mov     edx, 3Eh ; '>'
0x18001b163  mov     r9, [rax+18h]
0x18001b167  mov     eax, dword ptr [rbp-10h+var_6C]
0x18001b16a  mov     dword ptr [rsp+120h+var_F0], eax
0x18001b16e  mov     rax, [rbx+40h]
0x18001b172  mov     r9, [r9+8]
0x18001b176  mov     dword ptr [rsp+120h+phNewToken], r15d
0x18001b17b  mov     qword ptr [rsp+120h+TokenType], rax
0x18001b180  call    WPP_SF_Sidd
0x18001b185  jmp     loc_18001AD72
```
