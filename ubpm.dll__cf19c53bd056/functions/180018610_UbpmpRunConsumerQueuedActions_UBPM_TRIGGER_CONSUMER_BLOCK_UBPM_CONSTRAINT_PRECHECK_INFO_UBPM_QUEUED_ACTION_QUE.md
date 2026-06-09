# UbpmpRunConsumerQueuedActions(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_QUEUED_ACTION_QUEUE_REASON,uchar)

- ea: `0x180018610`
- end: `0x1800189ee`
- name: `?UbpmpRunConsumerQueuedActions@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@W4_UBPM_QUEUED_ACTION_QUEUE_REASON@@E@Z`
- size: `990`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018538`
- `0x18002c480`

## callees

- `0x180003ebc`
- `0x1800049b4`
- `0x180004e10`
- `0x180018610`
- `0x18001c400`
- `0x180032dd8`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800187bc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800187bc`
- `ntdll!RtlFreeHeap` at `0x180018861`
- `ntdll!RtlFreeHeap` at `0x180018882`
- `ntdll!RtlFreeHeap` at `0x1800188a0`
- `ntdll!RtlFreeHeap` at `0x1800188b8`
- `ntdll!RtlFreeHeap` at `0x180018861`
- `ntdll!RtlFreeHeap` at `0x180018882`
- `ntdll!RtlFreeHeap` at `0x1800188a0`
- `ntdll!RtlFreeHeap` at `0x1800188b8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800189c1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800189c1`

## pseudocode

```c
ULONG __fastcall UbpmpRunConsumerQueuedActions(
        __int64 a1,
        struct _UBPM_CONSTRAINT_PRECHECK_INFO *a2,
        unsigned int a3,
        char a4)
{
  PVOID v8; // rbx
  PVOID *v9; // rax
  _QWORD *v10; // rax
  PVOID *v11; // rcx
  PVOID *v12; // rbx
  int v13; // r14d
  PVOID *v14; // rax
  PVOID **v15; // rcx
  PVOID *v16; // rsi
  PVOID *v17; // rdi
  PVOID v18; // rcx
  ULONG v19; // eax
  unsigned __int64 v20; // r8
  PVOID v21; // r8
  PVOID v22; // r8
  PVOID v23; // r8
  ULONG result; // eax
  __int64 v25; // rax
  int *v26; // rcx
  __int64 v27; // rax
  unsigned int v29; // eax
  void *v30; // [rsp+60h] [rbp-69h] BYREF
  PVOID P; // [rsp+68h] [rbp-61h] BYREF
  PVOID *p_P; // [rsp+70h] [rbp-59h]
  int v33; // [rsp+78h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-39h] BYREF
  __int128 v36; // [rsp+A0h] [rbp-29h]
  __int128 v37; // [rsp+B0h] [rbp-19h]
  __int128 v38; // [rsp+C0h] [rbp-9h]
  PVOID v39; // [rsp+D0h] [rbp+7h]

  p_P = &P;
  P = &P;
  v30 = 0;
  UbpmpDequeueActionInstance(a3, a1, &v30);
  v8 = v30;
  if ( v30 )
  {
    while ( 1 )
    {
      v9 = p_P;
      if ( *p_P != &P )
        goto LABEL_33;
      *((_QWORD *)v8 + 1) = p_P;
      *(_QWORD *)v8 = &P;
      *v9 = v8;
      p_P = (PVOID *)v8;
      if ( !a4 )
        goto LABEL_15;
      v8 = *(PVOID *)(a1 + 256);
      if ( v8 == (PVOID)(a1 + 256) )
        break;
      while ( *((_DWORD *)v8 + 4) != a3 )
      {
        v8 = *(PVOID *)v8;
        if ( v8 == (PVOID)(a1 + 256) )
          goto LABEL_15;
      }
      UbpmQueueConsumerClose(*((void **)v8 + 17));
      v10 = *(_QWORD **)v8;
      if ( *(PVOID *)(*(_QWORD *)v8 + 8LL) != v8 )
        goto LABEL_33;
      v11 = (PVOID *)*((_QWORD *)v8 + 1);
      if ( *v11 != v8 )
        goto LABEL_33;
      *v11 = v10;
      v10[1] = v11;
      *((_QWORD *)v8 + 1) = v8;
      *(_QWORD *)v8 = v8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          94,
          WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 17) + 24LL) + 8LL));
      UbpmTriggerConsumerPublishStateChange(a1);
    }
    v30 = 0;
  }
LABEL_15:
  v12 = (PVOID *)P;
  v13 = 0;
  if ( P != &P )
  {
    while ( 1 )
    {
      v14 = (PVOID *)*v12;
      if ( *((PVOID **)*v12 + 1) != v12 )
        break;
      v15 = (PVOID **)v12[1];
      if ( *v15 != v12 )
        break;
      *v15 = v14;
      v16 = v12;
      v14[1] = v15;
      v12[1] = v12;
      v17 = v12;
      v12 = v14;
      *v16 = v16;
      v18 = v16[7];
      v39 = 0;
      v19 = *((_DWORD *)v16 + 12);
      UserData = 0;
      UserData.Size = v19;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      if ( v18 )
        LODWORD(v36) = GetLengthSid(v18);
      else
        LODWORD(v36) = 0;
      v20 = (unsigned __int64)v17[5];
      *((_QWORD *)&v36 + 1) = v17[7];
      HIDWORD(UserData.Ptr) = *((_DWORD *)v17 + 30);
      BYTE8(v37) = *((_BYTE *)v17 + 104);
      *(_QWORD *)&v38 = v17[14];
      BYTE8(v38) = *((_BYTE *)v17 + 124);
      v39 = v17[16];
      UbpmpRunConsumerActions(
        (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v17[17],
        a2,
        v20,
        v20,
        (struct _GUID *)((char *)v16 + 20),
        *((_DWORD *)v17 + 18),
        (unsigned __int64)v17[10],
        *((_DWORD *)v17 + 22),
        *((_DWORD *)v17 + 23),
        (unsigned __int8 *)v17[12],
        (struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *)&UserData);
      v21 = v17[14];
      if ( v21 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
      v22 = v17[16];
      if ( v22 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
      v23 = v17[12];
      if ( v23 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
      ++v13;
      if ( v12 == &P )
        goto LABEL_28;
    }
LABEL_33:
    __fastfail(3u);
  }
LABEL_28:
  result = dword_18004C0F0;
  if ( (unsigned int)dword_18004C0F0 > 4 )
  {
    v25 = *(_QWORD *)(a1 + 24);
    v33 = v13;
    *((_QWORD *)&v38 + 1) = 4;
    v26 = *(int **)(v25 + 8);
    *(_QWORD *)&v38 = &v33;
    if ( v26 )
    {
      v27 = -1;
      while ( *((_WORD *)v26 + ++v27) != 0 )
        ;
      v29 = 2 * v27 + 2;
    }
    else
    {
      v26 = &dword_1800405F4;
      v29 = 2;
    }
    *((_QWORD *)&v37 + 1) = v29;
    *(_DWORD *)&EventDescriptor.Level = 4;
    UserData.Ptr = (ULONGLONG)off_18004C0F8;
    *(_QWORD *)&v37 = v26;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_18004C0F8;
    *(_QWORD *)&v36 = byte_180043289;
    UserData.Reserved = 2;
    *((_QWORD *)&v36 + 1) = 0x100000029LL;
    LODWORD(v30) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x180018610  mov     [rsp-8+arg_10], rbx
0x180018615  push    rbp
0x180018616  push    rsi
0x180018617  push    rdi
0x180018618  push    r12
0x18001861a  push    r13
0x18001861c  push    r14
0x18001861e  push    r15
0x180018620  lea     rbp, [rsp-27h]
0x180018625  sub     rsp, 0F0h
0x18001862c  mov     rax, cs:__security_cookie
0x180018633  xor     rax, rsp
0x180018636  mov     [rbp+57h+var_40], rax
0x18001863a  mov     edi, r8d
0x18001863d  lea     rax, [rbp+57h+P]
0x180018641  mov     [rbp+57h+var_B0], rax
0x180018645  lea     r8, [rbp+57h+var_C0]
0x180018649  mov     r12, rdx
0x18001864c  lea     rax, [rbp+57h+P]
0x180018650  mov     r15, rcx
0x180018653  mov     [rbp+57h+P], rax
0x180018657  mov     rdx, rcx
0x18001865a  xor     r13d, r13d
0x18001865d  mov     ecx, edi
0x18001865f  mov     [rbp+57h+var_C0], r13
0x180018663  movzx   esi, r9b
0x180018667  call    ?UbpmpDequeueActionInstance@@YAXW4_UBPM_QUEUED_ACTION_QUEUE_REASON@@PEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAPEAU_UBPM_QUEUED_ACTION_INSTANCE@@@Z; UbpmpDequeueActionInstance(_UBPM_QUEUED_ACTION_QUEUE_REASON,_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_QUEUED_ACTION_INSTANCE * *)
0x18001866c  mov     rbx, [rbp+57h+var_C0]
0x180018670  test    rbx, rbx
0x180018673  jz      loc_18001874A
0x180018679  lea     r14, WPP_GLOBAL_Control
0x180018680  mov     rax, [rbp+57h+var_B0]
0x180018684  lea     rcx, [rbp+57h+P]
0x180018688  cmp     [rax], rcx
0x18001868b  jnz     loc_180018925
0x180018691  mov     [rbx+8], rax
0x180018695  lea     rcx, [rbp+57h+P]
0x180018699  mov     [rbx], rcx
0x18001869c  mov     [rax], rbx
0x18001869f  mov     [rbp+57h+var_B0], rbx
0x1800186a3  test    sil, sil
0x1800186a6  jz      loc_18001874A
0x1800186ac  lea     rax, [r15+100h]
0x1800186b3  mov     rbx, [rax]
0x1800186b6  cmp     rbx, rax
0x1800186b9  jz      loc_180018746
0x1800186bf  nop
0x1800186c0  cmp     [rbx+10h], edi
0x1800186c3  jz      short loc_1800186CF
0x1800186c5  mov     rbx, [rbx]
0x1800186c8  cmp     rbx, rax
0x1800186cb  jnz     short loc_1800186C0
0x1800186cd  jmp     short loc_18001874A
0x1800186cf  mov     rcx, [rbx+88h]; void *
0x1800186d6  call    UbpmQueueConsumerClose
0x1800186db  mov     rax, [rbx]
0x1800186de  cmp     [rax+8], rbx
0x1800186e2  jnz     loc_180018925
0x1800186e8  mov     rcx, [rbx+8]
0x1800186ec  cmp     [rcx], rbx
0x1800186ef  jnz     loc_180018925
0x1800186f5  mov     [rcx], rax
0x1800186f8  mov     [rax+8], rcx
0x1800186fc  mov     [rbx+8], rbx
0x180018700  mov     [rbx], rbx
0x180018703  mov     rcx, cs:WPP_GLOBAL_Control
0x18001870a  cmp     rcx, r14
0x18001870d  jz      short loc_180018739
0x18001870f  test    byte ptr [rcx+1Ch], 20h
0x180018713  jz      short loc_180018739
0x180018715  mov     rax, [rbx+88h]
0x18001871c  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180018723  mov     rcx, [rcx+10h]
0x180018727  mov     edx, 5Eh ; '^'
0x18001872c  mov     r9, [rax+18h]
0x180018730  mov     r9, [r9+8]
0x180018734  call    WPP_SF_S
0x180018739  mov     rcx, r15
0x18001873c  call    UbpmTriggerConsumerPublishStateChange
0x180018741  jmp     loc_180018680
0x180018746  mov     [rbp+57h+var_C0], r13
0x18001874a  mov     rbx, [rbp+57h+P]
0x18001874e  lea     rax, [rbp+57h+P]
0x180018752  mov     r14d, r13d
0x180018755  cmp     rbx, rax
0x180018758  jz      loc_1800188CE
0x18001875e  xchg    ax, ax
0x180018760  mov     rax, [rbx]
0x180018763  cmp     [rax+8], rbx
0x180018767  jnz     loc_180018925
0x18001876d  mov     rcx, [rbx+8]
0x180018771  lea     rdx, [rbx+8]
0x180018775  cmp     [rcx], rbx
0x180018778  jnz     loc_180018925
0x18001877e  mov     [rcx], rax
0x180018781  mov     rsi, rbx
0x180018784  mov     [rax+8], rcx
0x180018788  xorps   xmm0, xmm0
0x18001878b  mov     [rdx], rsi
0x18001878e  mov     rdi, rbx
0x180018791  mov     rbx, rax
0x180018794  xor     eax, eax
0x180018796  mov     [rsi], rsi
0x180018799  mov     rcx, [rsi+38h]; pSid
0x18001879d  mov     [rbp+57h+var_50], rax
0x1800187a1  mov     eax, [rsi+30h]
0x1800187a4  movups  xmmword ptr [rbp+57h+var_90.Ptr], xmm0
0x1800187a8  mov     [rbp+57h+var_90.Size], eax
0x1800187ab  movups  [rbp+57h+var_80], xmm0
0x1800187af  movups  [rbp+57h+var_70], xmm0
0x1800187b3  movups  [rbp+57h+var_60], xmm0
0x1800187b7  test    rcx, rcx
0x1800187ba  jz      short loc_1800187C7
0x1800187bc  call    cs:__imp_GetLengthSid
0x1800187c2  mov     dword ptr [rbp+57h+var_80], eax
0x1800187c5  jmp     short loc_1800187CB
0x1800187c7  mov     dword ptr [rbp+57h+var_80], r13d
0x1800187cb  mov     rax, [rdi+38h]
0x1800187cf  lea     rcx, [rsi+14h]
0x1800187d3  mov     r8, [rdi+28h]; unsigned __int64
0x1800187d7  mov     rdx, r12; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x1800187da  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800187de  mov     r9, r8; unsigned __int64
0x1800187e1  mov     eax, [rdi+78h]
0x1800187e4  mov     dword ptr [rbp+57h+var_90.Ptr+4], eax
0x1800187e7  movzx   eax, byte ptr [rdi+68h]
0x1800187eb  mov     byte ptr [rbp+57h+var_70+8], al
0x1800187ee  mov     rax, [rdi+70h]
0x1800187f2  mov     qword ptr [rbp+57h+var_60], rax
0x1800187f6  movzx   eax, byte ptr [rdi+7Ch]
0x1800187fa  mov     byte ptr [rbp+57h+var_60+8], al
0x1800187fd  mov     rax, [rdi+80h]
0x180018804  mov     [rbp+57h+var_50], rax
0x180018808  lea     rax, [rbp+57h+var_90]
0x18001880c  mov     [rsp+120h+var_D0], rax; struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *
0x180018811  mov     rax, [rdi+60h]
0x180018815  mov     [rsp+120h+var_D8], rax; unsigned __int8 *
0x18001881a  mov     eax, [rdi+5Ch]
0x18001881d  mov     [rsp+120h+var_E0], eax; unsigned int
0x180018821  mov     eax, [rdi+58h]
0x180018824  mov     [rsp+120h+var_E8], eax; unsigned int
0x180018828  mov     rax, [rdi+50h]
0x18001882c  mov     [rsp+120h+var_F0], rax; unsigned __int64
0x180018831  mov     eax, [rdi+48h]
0x180018834  mov     dword ptr [rsp+120h+UserData], eax; unsigned int
0x180018838  mov     qword ptr [rsp+120h+UserDataCount], rcx; struct _GUID *
0x18001883d  mov     rcx, [rdi+88h]; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x180018844  call    ?UbpmpRunConsumerActions@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@_K2PEAU_GUID@@K2KKPEAEPEAU_UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1@@@Z; UbpmpRunConsumerActions(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,unsigned __int64,unsigned __int64,_GUID *,ulong,unsigned __int64,ulong,ulong,uchar *,_UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *)
0x180018849  mov     r8, [rdi+70h]; P
0x18001884d  test    r8, r8
0x180018850  jz      short loc_180018867
0x180018852  mov     rcx, gs:60h
0x18001885b  xor     edx, edx; Flags
0x18001885d  mov     rcx, [rcx+30h]; HeapHandle
0x180018861  call    cs:__imp_RtlFreeHeap
0x180018867  mov     r8, [rdi+80h]; P
0x18001886e  test    r8, r8
0x180018871  jz      short loc_180018888
0x180018873  mov     rcx, gs:60h
0x18001887c  xor     edx, edx; Flags
0x18001887e  mov     rcx, [rcx+30h]; HeapHandle
0x180018882  call    cs:__imp_RtlFreeHeap
0x180018888  mov     r8, [rdi+60h]; P
0x18001888c  test    r8, r8
0x18001888f  jz      short loc_1800188A6
0x180018891  mov     rcx, gs:60h
0x18001889a  xor     edx, edx; Flags
0x18001889c  mov     rcx, [rcx+30h]; HeapHandle
0x1800188a0  call    cs:__imp_RtlFreeHeap
0x1800188a6  mov     rcx, gs:60h
0x1800188af  mov     r8, rsi; P
0x1800188b2  xor     edx, edx; Flags
0x1800188b4  mov     rcx, [rcx+30h]; HeapHandle
0x1800188b8  call    cs:__imp_RtlFreeHeap
0x1800188be  lea     rax, [rbp+57h+P]
0x1800188c2  inc     r14d
0x1800188c5  cmp     rbx, rax
0x1800188c8  jnz     loc_180018760
0x1800188ce  mov     eax, cs:dword_18004C0F0
0x1800188d4  cmp     eax, 4
0x1800188d7  jbe     loc_1800189C7
0x1800188dd  mov     rax, [r15+18h]
0x1800188e1  mov     [rbp+57h+var_A8], r14d
0x1800188e5  mov     qword ptr [rbp+57h+var_60+8], 4
0x1800188ed  mov     rcx, [rax+8]
0x1800188f1  lea     rax, [rbp+57h+var_A8]
0x1800188f5  mov     qword ptr [rbp+57h+var_60], rax
0x1800188f9  test    rcx, rcx
0x1800188fc  jz      short loc_18001892C
0x1800188fe  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180018905  nop     word ptr [rax+rax+00000000h]
0x180018910  cmp     [rcx+rax*2+2], r13w
0x180018916  lea     rax, [rax+1]
0x18001891a  jnz     short loc_180018910
0x18001891c  lea     eax, ds:2[rax*2]
0x180018923  jmp     short loc_180018938
0x180018925  mov     ecx, 3
0x18001892a  int     29h; Win8: RtlFailFast(ecx)
0x18001892c  lea     rcx, dword_1800405F4
0x180018933  mov     eax, 2
0x180018938  mov     dword ptr [rbp+57h+var_70+8], eax
0x18001893b  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18001893f  movzx   eax, cs:word_18004327F
0x180018946  xor     r9d, r9d; RelatedActivityId
0x180018949  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18001894c  xor     r8d, r8d; ActivityId
0x18001894f  mov     rax, cs:off_18004C0F8
0x180018956  mov     [rbp+57h+var_90.Ptr], rax
0x18001895a  mov     qword ptr [rbp+57h+var_70], rcx
0x18001895e  lea     rcx, _TraceLoggingMetadata
0x180018965  mov     dword ptr [rbp+57h+var_70+0Ch], r13d
0x180018969  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180018970  mov     [rbp+57h+EventDescriptor.Keyword], r13
0x180018974  movzx   eax, word ptr [rax]
0x180018977  mov     [rbp+57h+var_90.Size], eax
0x18001897a  lea     rax, byte_180043289
0x180018981  mov     qword ptr [rbp+57h+var_80], rax
0x180018985  lea     rax, _TraceLoggingMetadataEnd
0x18001898c  sub     eax, ecx
0x18001898e  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x180018995  mov     dword ptr [rbp+57h+var_80+8], 29h ; ')'
0x18001899c  mov     dword ptr [rbp+57h+var_80+0Ch], 1
0x1800189a3  mov     dword ptr [rbp+57h+var_C0], eax
0x1800189a6  mov     eax, dword ptr [rbp+57h+var_C0]
0x1800189a9  mov     rcx, cs:RegHandle; RegHandle
0x1800189b0  lea     rax, [rbp+57h+var_90]
0x1800189b4  mov     [rsp+120h+UserData], rax; UserData
0x1800189b9  mov     [rsp+120h+UserDataCount], 4; UserDataCount
0x1800189c1  call    cs:__imp_EventWriteTransfer
0x1800189c7  mov     rcx, [rbp+57h+var_40]
0x1800189cb  xor     rcx, rsp; StackCookie
0x1800189ce  call    __security_check_cookie
0x1800189d3  mov     rbx, [rsp+120h+arg_10]
0x1800189db  add     rsp, 0F0h
0x1800189e2  pop     r15
0x1800189e4  pop     r14
0x1800189e6  pop     r13
0x1800189e8  pop     r12
0x1800189ea  pop     rdi
0x1800189eb  pop     rsi
0x1800189ec  pop     rbp
0x1800189ed  retn
```
