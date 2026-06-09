# CVsmAzureAttestationHelper::AttestSession::GetReport(uchar * *,ulong *)

- ea: `0x10082de10`
- end: `0x10082e02c`
- name: `?GetReport@AttestSession@CVsmAzureAttestationHelper@@QEAAXPEAPEAEPEAK@Z`
- size: `540`
- prototype: `void __fastcall(CVsmAzureAttestationHelper::AttestSession *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x10082cb80`

## callees

- `0x10045f130`
- `0x10082cad0`
- `0x10082de10`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10082debd`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10082debd`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082dff5`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082dff5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082df96`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082df96`
- `sqldk!SystemThread_TlsIndex` at `0x10082de7e`
- `sqldk!SystemThread_TlsIndex` at `0x10082ded2`
- `sqldk!SystemThread_TlsOffset` at `0x10082de87`
- `sqldk!SystemThread_TlsOffset` at `0x10082dedb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082dea0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082def6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082dea0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082def6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082df78`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082dfe1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082df78`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082dfe1`
- `AzureAttestManager!AttestationGetReport` at `0x10082df49`
- `AzureAttestManager!AttestationGetReport` at `0x10082dfb2`
- `AzureAttestManager!AttestationGetReport` at `0x10082df49`
- `AzureAttestManager!AttestationGetReport` at `0x10082dfb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CVsmAzureAttestationHelper::AttestSession::GetReport(
        CVsmAzureAttestationHelper::AttestSession *this,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rdx
  int Report; // eax
  unsigned __int8 *v12; // rbx
  int v13; // eax
  __int64 v14; // [rsp+28h] [rbp-41h]
  int v15; // [rsp+40h] [rbp-29h] BYREF
  __int64 v16; // [rsp+48h] [rbp-21h]
  int v17; // [rsp+50h] [rbp-19h] BYREF
  int v18; // [rsp+54h] [rbp-15h]
  __int64 v19; // [rsp+58h] [rbp-11h]
  int v20; // [rsp+60h] [rbp-9h] BYREF
  __int64 v21; // [rsp+68h] [rbp-1h]
  __int64 v22; // [rsp+70h] [rbp+7h]
  __int64 v23; // [rsp+78h] [rbp+Fh]
  __int64 v24; // [rsp+80h] [rbp+17h]
  bool v25; // [rsp+90h] [rbp+27h]
  unsigned int v26; // [rsp+D0h] [rbp+67h] BYREF
  unsigned __int8 *v27; // [rsp+D8h] [rbp+6Fh]
  int *v28; // [rsp+E0h] [rbp+77h]

  v26 = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v15, 1);
  v28 = &v17;
  v20 = 536872437;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  v24 = 0;
  v25 = 0;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(_QWORD *)(v7 + 600);
  if ( v8 )
    v25 = (unsigned int)SOS_Task::PushWait(v8, &v20) == 0;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v19 = v10;
  v18 = (*(_DWORD *)(v10 + 800) >> 11) & 1;
  if ( v18 || (*(_BYTE *)(v10 + 800) & 4) == 0 )
  {
    v17 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 608) + 8LL))(*(_QWORD *)(v10 + 608));
  }
  else
  {
    v17 = 0;
  }
  Report = AttestationGetReport(*((_QWORD *)this + 1), 0, 0, &v26);
  if ( Report != -2147024774 )
    ex_raise(331, 96, 16, 62, L"AttestationGetReportSize", Report, -2);
  v12 = (unsigned __int8 *)operator new[](
                             v26,
                             *(struct IMemObj **)this,
                             "Sql\\Ntdbms\\aetmhost\\VsmAzureAttestationHelper.cpp",
                             517,
                             6u);
  v27 = v12;
  v13 = AttestationGetReport(*((_QWORD *)this + 1), v12, v26, &v26);
  if ( v13 < 0 )
  {
    _mm_lfence();
    LODWORD(v14) = v13;
    ex_raise(331, 96, 16, 63, L"AttestationGetReportData", v14);
  }
  v27 = 0;
  *a2 = v12;
  *a3 = v26;
  operator delete[](0);
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v17);
  *(_DWORD *)(v16 + 616) &= ~v15;
}

```

## disassembly

```asm
0x10082de10  push    rbp
0x10082de12  push    rsi
0x10082de13  push    rdi
0x10082de14  push    r14
0x10082de16  push    r15
0x10082de18  lea     rbp, [rsp-37h]
0x10082de1d  sub     rsp, 0A0h
0x10082de24  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x10082de2c  mov     [rsp+0C0h+arg_18], rbx
0x10082de34  mov     rsi, r8
0x10082de37  mov     r14, rdx
0x10082de3a  mov     rdi, rcx
0x10082de3d  xor     r15d, r15d
0x10082de40  mov     [rbp+57h+arg_0], r15d
0x10082de44  lea     edx, [r15+1]
0x10082de48  lea     rcx, [rbp+57h+var_80]
0x10082de4c  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10082de51  nop
0x10082de52  lea     rax, [rbp+57h+var_70]
0x10082de56  mov     [rbp+57h+arg_10], rax
0x10082de5a  mov     [rbp+57h+var_60], 200005F5h
0x10082de61  mov     [rbp+57h+var_58], r15
0x10082de65  mov     [rbp+57h+var_48], r15
0x10082de69  mov     [rbp+57h+var_50], r15
0x10082de6d  mov     [rbp+57h+var_40], r15
0x10082de71  mov     [rbp+57h+var_30], r15b
0x10082de75  mov     rdx, gs:58h
0x10082de7e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082de85  mov     ecx, [rax]
0x10082de87  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082de8e  mov     ebx, [rax]
0x10082de90  add     rbx, [rdx+rcx*8]
0x10082de94  mov     rcx, [rbx+100h]
0x10082de9b  test    rcx, rcx
0x10082de9e  jnz     short loc_10082DEAD
0x10082dea0  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082dea6  mov     rcx, [rbx+100h]
0x10082dead  mov     rcx, [rcx+258h]
0x10082deb4  test    rcx, rcx
0x10082deb7  jz      short loc_10082DEC9
0x10082deb9  lea     rdx, [rbp+57h+var_60]
0x10082debd  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10082dec3  test    eax, eax
0x10082dec5  setz    [rbp+57h+var_30]
0x10082dec9  mov     rdx, gs:58h
0x10082ded2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082ded9  mov     ecx, [rax]
0x10082dedb  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082dee2  mov     ebx, [rax]
0x10082dee4  add     rbx, [rdx+rcx*8]
0x10082dee8  mov     rdx, [rbx+100h]
0x10082deef  test    rdx, rdx
0x10082def2  jnz     short loc_10082DF03
0x10082def4  xor     ecx, ecx
0x10082def6  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082defc  mov     rdx, [rbx+100h]
0x10082df03  mov     [rbp+57h+var_68], rdx
0x10082df07  mov     eax, [rdx+320h]
0x10082df0d  shr     eax, 0Bh
0x10082df10  and     eax, 1
0x10082df13  mov     [rbp+57h+var_6C], eax
0x10082df16  jnz     short loc_10082DF27
0x10082df18  test    byte ptr [rdx+320h], 4
0x10082df1f  jz      short loc_10082DF27
0x10082df21  mov     [rbp+57h+var_70], r15d
0x10082df25  jmp     short loc_10082DF3C
0x10082df27  mov     [rbp+57h+var_70], 1
0x10082df2e  mov     rcx, [rdx+260h]
0x10082df35  mov     rax, [rcx]
0x10082df38  call    qword ptr [rax+8]
0x10082df3b  nop
0x10082df3c  lea     r9, [rbp+57h+arg_0]
0x10082df40  xor     r8d, r8d
0x10082df43  xor     edx, edx
0x10082df45  mov     rcx, [rdi+8]
0x10082df49  call    cs:__imp_AttestationGetReport
0x10082df4f  cmp     eax, 8007007Ah
0x10082df54  jz      short loc_10082DF7E
0x10082df56  mov     dword ptr [rsp+0C0h+var_98], eax
0x10082df5a  lea     rax, aAttestationget_0; "AttestationGetReportSize"
0x10082df61  mov     [rsp+0C0h+var_A0], rax
0x10082df66  mov     edx, 60h ; '`'
0x10082df6b  mov     ecx, 14Bh
0x10082df70  lea     r9d, [rdx-22h]
0x10082df74  lea     r8d, [rdx-50h]
0x10082df78  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082df7e  mov     ecx, [rbp+57h+arg_0]
0x10082df81  mov     byte ptr [rsp+0C0h+var_A0], 6
0x10082df86  mov     r9d, 205h
0x10082df8c  lea     r8, aSqlNtdbmsAetmh_4; "Sql\\Ntdbms\\aetmhost\\VsmAzureAttestat"...
0x10082df93  mov     rdx, [rdi]
0x10082df96  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10082df9c  mov     rbx, rax
0x10082df9f  mov     [rbp+57h+arg_8], rax
0x10082dfa3  lea     r9, [rbp+57h+arg_0]
0x10082dfa7  mov     r8d, [rbp+57h+arg_0]
0x10082dfab  mov     rdx, rax
0x10082dfae  mov     rcx, [rdi+8]
0x10082dfb2  call    cs:__imp_AttestationGetReport
0x10082dfb8  test    eax, eax
0x10082dfba  jns     short loc_10082DFE7
0x10082dfbc  lfence
0x10082dfbf  mov     dword ptr [rsp+0C0h+var_98], eax
0x10082dfc3  lea     rax, aAttestationget_1; "AttestationGetReportData"
0x10082dfca  mov     [rsp+0C0h+var_A0], rax
0x10082dfcf  mov     edx, 60h ; '`'
0x10082dfd4  mov     ecx, 14Bh
0x10082dfd9  lea     r9d, [rdx-21h]
0x10082dfdd  lea     r8d, [rdx-50h]
0x10082dfe1  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082dfe7  mov     [rbp+57h+arg_8], r15
0x10082dfeb  mov     [r14], rbx
0x10082dfee  mov     eax, [rbp+57h+arg_0]
0x10082dff1  mov     [rsi], eax
0x10082dff3  xor     ecx, ecx
0x10082dff5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082dffb  nop
0x10082dffc  lea     rcx, [rbp+57h+var_70]; this
0x10082e000  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10082e005  nop
0x10082e006  mov     rcx, [rbp+57h+var_78]
0x10082e00a  mov     eax, [rbp+57h+var_80]
0x10082e00d  not     eax
0x10082e00f  and     [rcx+268h], eax
0x10082e015  mov     rbx, [rsp+0C0h+arg_18]
0x10082e01d  add     rsp, 0A0h
0x10082e024  pop     r15
0x10082e026  pop     r14
0x10082e028  pop     rdi
0x10082e029  pop     rsi
0x10082e02a  pop     rbp
0x10082e02b  retn
```
