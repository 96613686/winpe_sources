# CVsmAzureAttestationHelper::AttestSession::Attest(uchar const *,ulong,uchar * *,ulong *)

- ea: `0x10082db70`
- end: `0x10082ddfe`
- name: `?Attest@AttestSession@CVsmAzureAttestationHelper@@QEAA_NPEBEKPEAPEAEPEAK@Z`
- size: `654`
- prototype: `bool __fastcall(CVsmAzureAttestationHelper::AttestSession *__hidden this, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x10082cb80`

## callees

- `0x10045f130`
- `0x10082cad0`
- `0x10082db70`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10082dc2e`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10082dc2e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082dd3c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082dd3c`
- `sqldk!SystemThread_TlsIndex` at `0x10082dbef`
- `sqldk!SystemThread_TlsIndex` at `0x10082dc43`
- `sqldk!SystemThread_TlsOffset` at `0x10082dbf8`
- `sqldk!SystemThread_TlsOffset` at `0x10082dc4c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082dc11`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082dc67`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082dc11`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082dc67`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082dd05`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082ddbf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082dd05`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082ddbf`
- `AzureAttestManager!AttestationAttest` at `0x10082dcd1`
- `AzureAttestManager!AttestationAttest` at `0x10082dd6c`
- `AzureAttestManager!AttestationAttest` at `0x10082dcd1`
- `AzureAttestManager!AttestationAttest` at `0x10082dd6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
_BOOL8 __fastcall CVsmAzureAttestationHelper::AttestSession::Attest(
        CVsmAzureAttestationHelper::AttestSession *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned int *v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rdx
  int v15; // eax
  bool v16; // zf
  bool v17; // bl
  unsigned __int8 *v18; // rax
  int v19; // eax
  const wchar_t *v20; // rax
  int v21; // r9d
  const wchar_t *v23; // [rsp+20h] [rbp-71h]
  __int64 v24; // [rsp+28h] [rbp-69h]
  int v25; // [rsp+50h] [rbp-41h] BYREF
  __int64 v26; // [rsp+58h] [rbp-39h]
  int v27; // [rsp+60h] [rbp-31h] BYREF
  int v28; // [rsp+64h] [rbp-2Dh]
  __int64 v29; // [rsp+68h] [rbp-29h]
  int v30; // [rsp+70h] [rbp-21h] BYREF
  __int64 v31; // [rsp+78h] [rbp-19h]
  __int64 v32; // [rsp+80h] [rbp-11h]
  __int64 v33; // [rsp+88h] [rbp-9h]
  __int64 v34; // [rsp+90h] [rbp-1h]
  bool v35; // [rsp+A0h] [rbp+Fh]
  unsigned int v36; // [rsp+F0h] [rbp+5Fh] BYREF
  int *v37; // [rsp+108h] [rbp+77h]

  v9 = a5;
  *a5 = 0;
  *a4 = 0;
  LODWORD(a5) = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v25, 1);
  v37 = &v27;
  v30 = 536872437;
  v31 = 0;
  v33 = 0;
  v32 = 0;
  v34 = 0;
  v35 = 0;
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v11 = *(_QWORD *)(v10 + 256);
  if ( !v11 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v11 = *(_QWORD *)(v10 + 256);
  }
  v12 = *(_QWORD *)(v11 + 600);
  if ( v12 )
    v35 = (unsigned int)SOS_Task::PushWait(v12, &v30) == 0;
  v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v14 = *(_QWORD *)(v13 + 256);
  if ( !v14 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v14 = *(_QWORD *)(v13 + 256);
  }
  v29 = v14;
  v28 = (*(_DWORD *)(v14 + 800) >> 11) & 1;
  if ( v28 || (*(_BYTE *)(v14 + 800) & 4) == 0 )
  {
    v27 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v14 + 608) + 8LL))(*(_QWORD *)(v14 + 608));
  }
  else
  {
    v27 = 0;
  }
  v15 = AttestationAttest(*((_QWORD *)this + 1), a2, a3, 0, 0, &v36, &a5);
  if ( v15 < 0 )
  {
    if ( v15 == -2147024774 )
    {
      _mm_lfence();
      v18 = (unsigned __int8 *)operator new[](
                                 v36 + 1,
                                 *(struct IMemObj **)this,
                                 "Sql\\Ntdbms\\aetmhost\\VsmAzureAttestationHelper.cpp",
                                 474,
                                 6u);
      *a4 = v18;
      v19 = AttestationAttest(*((_QWORD *)this + 1), a2, a3, v18, v36, &v36, &a5);
      if ( v19 >= 0 )
      {
        *v9 = v36;
        v17 = (_DWORD)a5 != 0;
        goto LABEL_21;
      }
      LODWORD(v24) = v19;
      v20 = L"AttestationAttestData";
      v21 = 61;
    }
    else
    {
      LODWORD(v24) = v15;
      v20 = L"AttestationAttestSizeBuffer";
      v21 = 60;
    }
    v23 = v20;
    _mm_lfence();
    ex_raise(331, 96, 16, v21, v23, v24);
    v17 = 0;
    goto LABEL_21;
  }
  v16 = (_DWORD)a5 == 0;
  if ( !(_DWORD)a5 )
  {
    _mm_lfence();
    LODWORD(v24) = v15;
    ex_raise(331, 96, 16, 59, L"AttestationAttestSize", v24);
    v16 = (_DWORD)a5 == 0;
  }
  v17 = !v16;
LABEL_21:
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v27);
  *(_DWORD *)(v26 + 616) &= ~v25;
  return v17;
}

```

## disassembly

```asm
0x10082db70  push    rbp
0x10082db72  push    rsi
0x10082db73  push    rdi
0x10082db74  push    r12
0x10082db76  push    r13
0x10082db78  push    r14
0x10082db7a  push    r15
0x10082db7c  lea     rbp, [rsp-1Fh]
0x10082db81  sub     rsp, 0B0h
0x10082db88  mov     [rbp+4Fh+var_A0], 0FFFFFFFFFFFFFFFEh
0x10082db90  mov     [rsp+0E0h+arg_8], rbx
0x10082db98  mov     r12, r9
0x10082db9b  mov     r14d, r8d
0x10082db9e  mov     r15, rdx
0x10082dba1  mov     rsi, rcx
0x10082dba4  xor     r13d, r13d
0x10082dba7  mov     rdi, [rbp+4Fh+arg_20]
0x10082dbab  mov     [rdi], r13d
0x10082dbae  mov     [r9], r13
0x10082dbb1  mov     dword ptr [rbp+4Fh+arg_20], r13d
0x10082dbb5  lea     edx, [r13+1]
0x10082dbb9  lea     rcx, [rbp+4Fh+var_90]
0x10082dbbd  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10082dbc2  nop
0x10082dbc3  lea     rax, [rbp+4Fh+var_80]
0x10082dbc7  mov     [rbp+4Fh+arg_18], rax
0x10082dbcb  mov     [rbp+4Fh+var_70], 200005F5h
0x10082dbd2  mov     [rbp+4Fh+var_68], r13
0x10082dbd6  mov     [rbp+4Fh+var_58], r13
0x10082dbda  mov     [rbp+4Fh+var_60], r13
0x10082dbde  mov     [rbp+4Fh+var_50], r13
0x10082dbe2  mov     [rbp+4Fh+var_40], r13b
0x10082dbe6  mov     rdx, gs:58h
0x10082dbef  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082dbf6  mov     ecx, [rax]
0x10082dbf8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082dbff  mov     ebx, [rax]
0x10082dc01  add     rbx, [rdx+rcx*8]
0x10082dc05  mov     rcx, [rbx+100h]
0x10082dc0c  test    rcx, rcx
0x10082dc0f  jnz     short loc_10082DC1E
0x10082dc11  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082dc17  mov     rcx, [rbx+100h]
0x10082dc1e  mov     rcx, [rcx+258h]
0x10082dc25  test    rcx, rcx
0x10082dc28  jz      short loc_10082DC3A
0x10082dc2a  lea     rdx, [rbp+4Fh+var_70]
0x10082dc2e  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10082dc34  test    eax, eax
0x10082dc36  setz    [rbp+4Fh+var_40]
0x10082dc3a  mov     rdx, gs:58h
0x10082dc43  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082dc4a  mov     ecx, [rax]
0x10082dc4c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082dc53  mov     ebx, [rax]
0x10082dc55  add     rbx, [rdx+rcx*8]
0x10082dc59  mov     rdx, [rbx+100h]
0x10082dc60  test    rdx, rdx
0x10082dc63  jnz     short loc_10082DC74
0x10082dc65  xor     ecx, ecx
0x10082dc67  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082dc6d  mov     rdx, [rbx+100h]
0x10082dc74  mov     [rbp+4Fh+var_78], rdx
0x10082dc78  mov     eax, [rdx+320h]
0x10082dc7e  shr     eax, 0Bh
0x10082dc81  and     eax, 1
0x10082dc84  mov     [rbp+4Fh+var_7C], eax
0x10082dc87  jnz     short loc_10082DC98
0x10082dc89  test    byte ptr [rdx+320h], 4
0x10082dc90  jz      short loc_10082DC98
0x10082dc92  mov     [rbp+4Fh+var_80], r13d
0x10082dc96  jmp     short loc_10082DCAD
0x10082dc98  mov     [rbp+4Fh+var_80], 1
0x10082dc9f  mov     rcx, [rdx+260h]
0x10082dca6  mov     rax, [rcx]
0x10082dca9  call    qword ptr [rax+8]
0x10082dcac  nop
0x10082dcad  lea     rax, [rbp+4Fh+arg_20]
0x10082dcb1  mov     [rsp+0E0h+var_B0], rax
0x10082dcb6  lea     rax, [rbp+4Fh+arg_0]
0x10082dcba  mov     [rsp+0E0h+var_B8], rax
0x10082dcbf  mov     dword ptr [rsp+0E0h+var_C0], r13d
0x10082dcc4  xor     r9d, r9d
0x10082dcc7  mov     r8d, r14d
0x10082dcca  mov     rdx, r15
0x10082dccd  mov     rcx, [rsi+8]
0x10082dcd1  call    cs:__imp_AttestationAttest
0x10082dcd7  test    eax, eax
0x10082dcd9  js      short loc_10082DD18
0x10082dcdb  mov     ecx, dword ptr [rbp+4Fh+arg_20]
0x10082dcde  test    ecx, ecx
0x10082dce0  jnz     short loc_10082DD10
0x10082dce2  lfence
0x10082dce5  mov     dword ptr [rsp+0E0h+var_B8], eax
0x10082dce9  lea     rax, aAttestationatt_1; "AttestationAttestSize"
0x10082dcf0  mov     [rsp+0E0h+var_C0], rax
0x10082dcf5  lea     edx, [rcx+60h]
0x10082dcf8  mov     ecx, 14Bh
0x10082dcfd  lea     r9d, [rdx-25h]
0x10082dd01  lea     r8d, [rdx-50h]
0x10082dd05  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082dd0b  mov     ecx, dword ptr [rbp+4Fh+arg_20]
0x10082dd0e  test    ecx, ecx
0x10082dd10  setnz   bl
0x10082dd13  jmp     loc_10082DDC7
0x10082dd18  cmp     eax, 8007007Ah
0x10082dd1d  jnz     short loc_10082DD97
0x10082dd1f  lfence
0x10082dd22  mov     ecx, [rbp+4Fh+arg_0]
0x10082dd25  inc     ecx
0x10082dd27  mov     byte ptr [rsp+0E0h+var_C0], 6
0x10082dd2c  mov     r9d, 1DAh
0x10082dd32  lea     r8, aSqlNtdbmsAetmh_4; "Sql\\Ntdbms\\aetmhost\\VsmAzureAttestat"...
0x10082dd39  mov     rdx, [rsi]
0x10082dd3c  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10082dd42  mov     [r12], rax
0x10082dd46  lea     rcx, [rbp+4Fh+arg_20]
0x10082dd4a  mov     [rsp+0E0h+var_B0], rcx
0x10082dd4f  lea     rcx, [rbp+4Fh+arg_0]
0x10082dd53  mov     [rsp+0E0h+var_B8], rcx
0x10082dd58  mov     ecx, [rbp+4Fh+arg_0]
0x10082dd5b  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x10082dd5f  mov     r9, rax
0x10082dd62  mov     r8d, r14d
0x10082dd65  mov     rdx, r15
0x10082dd68  mov     rcx, [rsi+8]
0x10082dd6c  call    cs:__imp_AttestationAttest
0x10082dd72  test    eax, eax
0x10082dd74  jns     short loc_10082DD89
0x10082dd76  mov     dword ptr [rsp+0E0h+var_B8], eax
0x10082dd7a  lea     rax, aAttestationatt_2; "AttestationAttestData"
0x10082dd81  mov     r9d, 3Dh ; '='
0x10082dd87  jmp     short loc_10082DDA8
0x10082dd89  mov     eax, [rbp+4Fh+arg_0]
0x10082dd8c  mov     [rdi], eax
0x10082dd8e  cmp     dword ptr [rbp+4Fh+arg_20], 0
0x10082dd92  setnz   bl
0x10082dd95  jmp     short loc_10082DDC7
0x10082dd97  mov     dword ptr [rsp+0E0h+var_B8], eax
0x10082dd9b  lea     rax, aAttestationatt_0; "AttestationAttestSizeBuffer"
0x10082dda2  mov     r9d, 3Ch ; '<'
0x10082dda8  mov     [rsp+0E0h+var_C0], rax
0x10082ddad  lfence
0x10082ddb0  mov     r8d, 10h
0x10082ddb6  lea     edx, [r8+50h]
0x10082ddba  mov     ecx, 14Bh
0x10082ddbf  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082ddc5  xor     bl, bl
0x10082ddc7  lea     rcx, [rbp+4Fh+var_80]; this
0x10082ddcb  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10082ddd0  nop
0x10082ddd1  mov     rdx, [rbp+4Fh+var_88]
0x10082ddd5  mov     ecx, [rbp+4Fh+var_90]
0x10082ddd8  not     ecx
0x10082ddda  and     [rdx+268h], ecx
0x10082dde0  movzx   eax, bl
0x10082dde3  mov     rbx, [rsp+0E0h+arg_8]
0x10082ddeb  add     rsp, 0B0h
0x10082ddf2  pop     r15
0x10082ddf4  pop     r14
0x10082ddf6  pop     r13
0x10082ddf8  pop     r12
0x10082ddfa  pop     rdi
0x10082ddfb  pop     rsi
0x10082ddfc  pop     rbp
0x10082ddfd  retn
```
