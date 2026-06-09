# RQueryServiceConfigW

- ea: `0x140009910`
- end: `0x14000a03b`
- name: `RQueryServiceConfigW`
- size: `1835`
- prototype: `__int64 __fastcall(void *, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140009630`

## callees

- `0x140002890`
- `0x1400083f0`
- `0x140009910`
- `0x14000ab50`
- `0x14000ac50`
- `0x14000b2e4`
- `0x14000bebc`
- `0x14000c310`
- `0x14000ca18`
- `0x14000cee0`
- `0x140019b14`
- `0x14001a230`
- `0x14001e1c0`
- `0x14001f99c`
- `0x140092420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400099e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400099e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140009d5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140009d5c`
- `ntdll!RtlReleaseResource` at `0x140009c9d`
- `ntdll!RtlReleaseResource` at `0x140009e61`
- `ntdll!RtlReleaseResource` at `0x140009f53`
- `ntdll!RtlReleaseResource` at `0x140009f6e`
- `ntdll!RtlReleaseResource` at `0x140009c9d`
- `ntdll!RtlReleaseResource` at `0x140009e61`
- `ntdll!RtlReleaseResource` at `0x140009f53`
- `ntdll!RtlReleaseResource` at `0x140009f6e`
- `ntdll!RtlAcquireResourceShared` at `0x1400099d0`
- `ntdll!RtlAcquireResourceShared` at `0x1400099d0`
- `ntdll!RtlAreAllAccessesGranted` at `0x1400099aa`
- `ntdll!RtlAreAllAccessesGranted` at `0x1400099aa`
- `ntdll!NtClose` at `0x140009cb0`
- `ntdll!NtClose` at `0x140009cb0`
- `ntdll!RtlNtStatusToDosError` at `0x140009cb8`
- `ntdll!RtlNtStatusToDosError` at `0x140009cb8`
- `ntdll!RtlFreeHeap` at `0x140009cd1`
- `ntdll!RtlFreeHeap` at `0x140009ce9`
- `ntdll!RtlFreeHeap` at `0x140009d11`
- `ntdll!RtlFreeHeap` at `0x140009d29`
- `ntdll!RtlFreeHeap` at `0x140009f1a`
- `ntdll!RtlFreeHeap` at `0x140009fb9`
- `ntdll!RtlFreeHeap` at `0x140009cd1`
- `ntdll!RtlFreeHeap` at `0x140009ce9`
- `ntdll!RtlFreeHeap` at `0x140009d11`
- `ntdll!RtlFreeHeap` at `0x140009d29`
- `ntdll!RtlFreeHeap` at `0x140009f1a`
- `ntdll!RtlFreeHeap` at `0x140009fb9`
- `ntdll!RtlAllocateHeap` at `0x140009e0d`
- `ntdll!RtlAllocateHeap` at `0x140009e0d`

## pseudocode

```c
__int64 __fastcall RQueryServiceConfigW(void *a1, unsigned int *a2, unsigned int a3, int *a4)
{
  PVOID v7; // r14
  PVOID v8; // r12
  unsigned __int16 *v9; // r13
  unsigned __int16 *v10; // r15
  RTL_SRWLOCK *v11; // rbx
  __int64 v12; // r8
  unsigned int v13; // edi
  int ImageFileName; // eax
  struct CServiceRecord *v15; // r13
  __int64 v16; // rdi
  unsigned int v17; // eax
  unsigned __int16 *v18; // r10
  unsigned __int8 *v19; // r11
  __int64 v20; // rax
  int v21; // ecx
  __int64 v22; // rax
  int v23; // r9d
  unsigned int v24; // r14d
  int v25; // ecx
  int v26; // edx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rdx
  unsigned __int16 *v31; // rax
  __int64 v32; // rdx
  int v33; // eax
  PRPC_ASYNC_STATE v34; // rcx
  __int64 v35; // rdx
  NTSTATUS v36; // eax
  __int64 v38; // rax
  SIZE_T v39; // r15
  unsigned __int16 *Heap; // rax
  size_t v41; // r8
  unsigned __int16 *v42; // r14
  __int64 v43; // rax
  unsigned __int16 *v44; // rcx
  __int64 v45; // rax
  PVOID v46; // [rsp+58h] [rbp-39h] BYREF
  unsigned __int16 *v47; // [rsp+60h] [rbp-31h] BYREF
  char *v48; // [rsp+68h] [rbp-29h] BYREF
  int v49; // [rsp+70h] [rbp-21h]
  PVOID v50; // [rsp+78h] [rbp-19h] BYREF
  PVOID v51; // [rsp+80h] [rbp-11h] BYREF
  PVOID Src; // [rsp+88h] [rbp-9h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp-1h] BYREF
  PVOID P; // [rsp+98h] [rbp+7h]
  unsigned __int16 *v55; // [rsp+A0h] [rbp+Fh] BYREF
  struct CServiceRecord *v56; // [rsp+A8h] [rbp+17h]
  unsigned int v57; // [rsp+F8h] [rbp+67h] BYREF
  unsigned int v58; // [rsp+108h] [rbp+77h]
  int *v59; // [rsp+110h] [rbp+7Fh]

  v59 = a4;
  v58 = a3;
  Handle = 0;
  v7 = 0;
  v57 = 0;
  v8 = 0;
  v46 = 0;
  v9 = 0;
  Src = 0;
  v10 = 0;
  v51 = 0;
  P = 0;
  v55 = 0;
  v50 = 0;
  LODWORD(v47) = 0;
  ScSetTcpKeepalive();
  if ( ScShutdownInProgress )
    return 1115;
  if ( !(unsigned int)ScIsValidServiceHandle(a1) )
    return 6;
  if ( !a2 || !a4 )
    return 87;
  if ( !RtlAreAllAccessesGranted(*((_DWORD *)a1 + 2), 1u) )
    return 5;
  v56 = (struct CServiceRecord *)*((_QWORD *)a1 + 2);
  v49 = 64;
  RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
  v11 = (RTL_SRWLOCK *)((char *)v56 + 312);
  AcquireSRWLockShared((PSRWLOCK)v56 + 39);
  v48 = (char *)v56 + 312;
  v13 = CServiceRecord::OpenServiceConfigKey(v56, 0x20019u, v12, (HKEY *)&Handle);
  if ( v13 )
  {
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v48);
    RtlReleaseResource(&ScServiceRecordLock);
    goto LABEL_54;
  }
  ImageFileName = ScGetImageFileName((HKEY)Handle, 0, (unsigned __int16 **)&v46);
  v7 = v46;
  v15 = v56;
  if ( ImageFileName )
    v7 = 0;
  v46 = v7;
  v13 = ScReadConfigFromReg(
          v56,
          a2,
          a2 + 1,
          &v57,
          a2 + 2,
          (enum _TRI_BOOL *)&v47,
          a2 + 8,
          (unsigned __int16 **)&Src,
          (unsigned __int16 **)&v51,
          (unsigned __int16 **)&v50);
  if ( v13 )
  {
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v48);
    RtlReleaseResource(&ScServiceRecordLock);
    v8 = Src;
    v9 = (unsigned __int16 *)v51;
    v10 = (unsigned __int16 *)v50;
    goto LABEL_54;
  }
  v16 = -1;
  if ( v7 && !v57 && !ScIsArcName((unsigned __int16 *)v7) )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v7 + v38) );
    v39 = (unsigned int)(2 * v38 + 26);
    Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v39);
    v7 = Heap;
    if ( !Heap )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 83, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids);
      v13 = 8;
      Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v48);
      RtlReleaseResource(&ScServiceRecordLock);
      v8 = Src;
      v9 = (unsigned __int16 *)v51;
      v10 = (unsigned __int16 *)v50;
      goto LABEL_53;
    }
    StringCbCopyW(Heap, v39, L"\\SystemRoot\\");
    StringCbCatW((unsigned __int16 *)v7, v39, (const unsigned __int16 *)v46);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v46);
    v46 = v7;
  }
  v17 = ScAllocateAndReadConfigValue((HKEY)Handle, L"ObjectName", &v55, 0);
  v18 = v55;
  v19 = 0;
  if ( v17 )
    v18 = 0;
  P = v18;
  if ( v7 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)v7 + v20) );
    v21 = 2 * v20 + 89;
  }
  else
  {
    v21 = 89;
  }
  v10 = (unsigned __int16 *)v50;
  if ( !v50 )
    v10 = (unsigned __int16 *)*((_QWORD *)v15 + 7);
  v22 = -1;
  do
    ++v22;
  while ( v10[v22] );
  v9 = (unsigned __int16 *)v51;
  v23 = v21 + 2 * v22;
  if ( v51 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_WORD *)v51 + v45) );
    v23 += 2 * v45;
  }
  v8 = Src;
  if ( Src )
  {
    v24 = ScWStrArraySize(Src);
    v25 = v24;
  }
  else
  {
    v24 = 0;
    v25 = 4;
  }
  v26 = v23 + v25 + 16;
  if ( v18 )
  {
    v27 = -1;
    do
      ++v27;
    while ( v18[v27] != (_WORD)v19 );
    v26 += 2 * v27;
  }
  v28 = (v26 + 3) & 0xFFFFFFFE;
  v49 = v28;
  if ( (unsigned int)v28 > v58 )
  {
    *v59 = v28;
LABEL_49:
    v13 = 122;
    goto LABEL_50;
  }
  LODWORD(v29) = (_DWORD)v19;
  v47 = (unsigned __int16 *)((char *)a2 + v28);
  if ( v46 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)v46 + v29) != (_WORD)v19 );
  }
  if ( !(unsigned int)ScCopyStringToBufferW(
                        (const unsigned __int16 *)v46,
                        v29,
                        (const unsigned __int16 *)a2 + 32,
                        &v47,
                        (unsigned __int16 **)a2 + 2,
                        v19) )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 84, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids);
    goto LABEL_49;
  }
  LODWORD(v30) = 0;
  if ( v9 )
  {
    v30 = -1;
    do
      ++v30;
    while ( v9[v30] );
  }
  if ( !(unsigned int)ScCopyStringToBufferW(
                        v9,
                        v30,
                        (const unsigned __int16 *)a2 + 32,
                        &v47,
                        (unsigned __int16 **)a2 + 3,
                        0) )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_47;
    v35 = 85;
    goto LABEL_46;
  }
  if ( v8 && v24 )
  {
    v41 = v24;
    v42 = (unsigned __int16 *)((char *)v47 - v24);
    *((_QWORD *)a2 + 5) = v42;
    v47 = v42;
    memmove(v42, v8, v41);
    v43 = -1;
    do
      ++v43;
    while ( v42[v43] );
    while ( (_DWORD)v43 )
    {
      v44 = &v42[(unsigned int)v43];
      v43 = -1;
      *v44 = 47;
      v42 = v44 + 1;
      do
        ++v43;
      while ( v42[v43] );
    }
  }
  else
  {
    v31 = v47 - 2;
    *((_QWORD *)a2 + 5) = v47 - 2;
    v47 = v31;
    *v31 = 47;
    *(_WORD *)(*((_QWORD *)a2 + 5) + 2LL) = 0;
  }
  LODWORD(v32) = 0;
  if ( P )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)P + v32) );
  }
  if ( !(unsigned int)ScCopyStringToBufferW(
                        (const unsigned __int16 *)P,
                        v32,
                        (const unsigned __int16 *)a2 + 32,
                        &v47,
                        (unsigned __int16 **)a2 + 6,
                        0) )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_47;
    v35 = 86;
    goto LABEL_46;
  }
  do
    ++v16;
  while ( v10[v16] );
  v33 = ScCopyStringToBufferW(v10, v16, (const unsigned __int16 *)a2 + 32, &v47, (unsigned __int16 **)a2 + 7, 0);
  v13 = 0;
  if ( v33 )
  {
LABEL_50:
    if ( v11 )
      ReleaseSRWLockShared(v11);
    goto LABEL_52;
  }
  v34 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
    goto LABEL_47;
  v35 = 87;
LABEL_46:
  WPP_SF_(v34->StubInfo, v35, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids);
LABEL_47:
  v13 = 122;
  Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v48);
LABEL_52:
  RtlReleaseResource(&ScServiceRecordLock);
LABEL_53:
  v7 = v46;
LABEL_54:
  if ( Handle )
  {
    v36 = NtClose(Handle);
    RtlNtStatusToDosError(v36);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( v56 && v10 != *((unsigned __int16 **)v56 + 7) )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  *v59 = v49;
  if ( v13 )
  {
    *((_QWORD *)a2 + 2) = 0;
    *((_QWORD *)a2 + 3) = 0;
    *((_QWORD *)a2 + 5) = 0;
    *((_QWORD *)a2 + 6) = 0;
    *((_QWORD *)a2 + 7) = 0;
  }
  return v13;
}

```

## disassembly

```asm
0x140009910  mov     rax, rsp
0x140009913  mov     [rax+10h], rbx
0x140009917  mov     [rax+20h], r9
0x14000991b  mov     [rax+18h], r8d
0x14000991f  push    rbp
0x140009920  push    rsi
0x140009921  push    rdi
0x140009922  push    r12
0x140009924  push    r13
0x140009926  push    r14
0x140009928  push    r15
0x14000992a  lea     rbp, [rax-5Fh]
0x14000992e  sub     rsp, 0B0h
0x140009935  mov     rbx, rcx
0x140009938  mov     rdi, r9
0x14000993b  xor     ecx, ecx
0x14000993d  mov     rsi, rdx
0x140009940  mov     [rbp+57h+Handle], rcx
0x140009944  mov     r14d, ecx
0x140009947  mov     [rbp+57h+arg_0], ecx
0x14000994a  mov     r12d, ecx
0x14000994d  mov     [rbp+57h+var_90], rcx
0x140009951  mov     r13d, ecx
0x140009954  mov     [rbp+57h+Src], rcx
0x140009958  mov     r15d, ecx
0x14000995b  mov     [rbp+57h+var_68], rcx
0x14000995f  mov     [rbp+57h+P], rcx
0x140009963  mov     [rbp+57h+var_48], rcx
0x140009967  mov     [rbp+57h+var_70], rcx
0x14000996b  mov     dword ptr [rbp+57h+var_88], ecx
0x14000996e  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x140009973  xor     edx, edx
0x140009975  cmp     cs:?ScShutdownInProgress@@3KA, edx; ulong ScShutdownInProgress
0x14000997b  jnz     loc_140009F25
0x140009981  mov     rcx, rbx; void *
0x140009984  call    ?ScIsValidServiceHandle@@YAHPEAX@Z; ScIsValidServiceHandle(void *)
0x140009989  test    eax, eax
0x14000998b  jz      loc_140009F2F
0x140009991  test    rsi, rsi
0x140009994  jz      loc_14000A031
0x14000999a  test    rdi, rdi
0x14000999d  jz      loc_14000A031
0x1400099a3  mov     ecx, [rbx+8]; GrantedAccess
0x1400099a6  lea     edx, [r15+1]; DesiredAccess
0x1400099aa  call    cs:__imp_RtlAreAllAccessesGranted
0x1400099b0  test    al, al
0x1400099b2  jz      loc_140009F39
0x1400099b8  mov     rdi, [rbx+10h]
0x1400099bc  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x1400099c3  mov     dl, 1; Wait
0x1400099c5  mov     [rbp+57h+var_40], rdi
0x1400099c9  mov     [rbp+57h+var_78], 40h ; '@'
0x1400099d0  call    cs:__imp_RtlAcquireResourceShared
0x1400099d6  lea     rbx, [rdi+138h]
0x1400099dd  mov     rcx, rbx; SRWLock
0x1400099e0  call    cs:__imp_AcquireSRWLockShared
0x1400099e6  lea     r9, [rbp+57h+Handle]; HKEY *
0x1400099ea  mov     [rbp+57h+var_80], rbx
0x1400099ee  mov     edx, 20019h; unsigned int
0x1400099f3  mov     rcx, rdi; this
0x1400099f6  call    ?OpenServiceConfigKey@CServiceRecord@@QEAAKKHPEAPEAUHKEY__@@@Z; CServiceRecord::OpenServiceConfigKey(ulong,int,HKEY__ * *)
0x1400099fb  mov     edi, eax
0x1400099fd  test    eax, eax
0x1400099ff  jnz     loc_140009F43
0x140009a05  mov     rcx, [rbp+57h+Handle]; HKEY
0x140009a09  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x140009a0d  xor     edx, edx; unsigned __int16
0x140009a0f  call    ?ScGetImageFileName@@YAKPEAUHKEY__@@GPEAPEAG@Z; ScGetImageFileName(HKEY__ *,ushort,ushort * *)
0x140009a14  mov     r14, [rbp+57h+var_90]
0x140009a18  lea     rdx, [rbp+57h+var_70]
0x140009a1c  mov     r13, [rbp+57h+var_40]
0x140009a20  lea     rcx, [rsi+8]
0x140009a24  mov     [rsp+48h], rdx; unsigned __int16 **
0x140009a29  lea     r8, [rsi+4]; unsigned int *
0x140009a2d  test    eax, eax
0x140009a2f  lea     rdx, [rbp+57h+var_68]
0x140009a33  mov     [rsp+0E0h+var_A0], rdx; unsigned __int16 **
0x140009a38  lea     rax, [rsi+20h]
0x140009a3c  lea     rdx, [rbp+57h+Src]
0x140009a40  cmovnz  r14, r15
0x140009a44  mov     [rsp+0E0h+var_A8], rdx; unsigned __int16 **
0x140009a49  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x140009a4d  mov     [rsp+0E0h+var_B0], rax; unsigned int *
0x140009a52  mov     rdx, rsi; unsigned int *
0x140009a55  lea     rax, [rbp+57h+var_88]
0x140009a59  mov     [rbp+57h+var_90], r14
0x140009a5d  mov     [rsp+0E0h+var_B8], rax; enum _TRI_BOOL *
0x140009a62  mov     [rsp+0E0h+var_C0], rcx; unsigned int *
0x140009a67  mov     rcx, r13; this
0x140009a6a  call    ?ScReadConfigFromReg@@YAKPEAVCServiceRecord@@PEAK111PEAW4_TRI_BOOL@@1PEAPEAG33@Z; ScReadConfigFromReg(CServiceRecord *,ulong *,ulong *,ulong *,ulong *,_TRI_BOOL *,ulong *,ushort * *,ushort * *,ushort * *)
0x140009a6f  mov     edi, eax
0x140009a71  test    eax, eax
0x140009a73  jnz     loc_140009F5E
0x140009a79  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140009a7d  test    r14, r14
0x140009a80  jnz     loc_140009DCA
0x140009a86  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140009a8a  lea     r8, [rbp+57h+var_48]; unsigned __int16 **
0x140009a8e  xor     r9d, r9d; unsigned int *
0x140009a91  lea     rdx, aObjectname; "ObjectName"
0x140009a98  call    ?ScAllocateAndReadConfigValue@@YAKPEAUHKEY__@@PEBGPEAPEAGPEAK@Z; ScAllocateAndReadConfigValue(HKEY__ *,ushort const *,ushort * *,ulong *)
0x140009a9d  mov     r10, [rbp+57h+var_48]
0x140009aa1  xor     r11d, r11d
0x140009aa4  test    eax, eax
0x140009aa6  cmovnz  r10, r11
0x140009aaa  mov     [rbp+57h+P], r10
0x140009aae  test    r14, r14
0x140009ab1  jz      loc_140009FC8
0x140009ab7  mov     rax, rdi
0x140009aba  inc     rax
0x140009abd  cmp     [r14+rax*2], r11w
0x140009ac2  jnz     short loc_140009ABA
0x140009ac4  lea     ecx, ds:59h[rax*2]
0x140009acb  mov     r15, [rbp+57h+var_70]
0x140009acf  test    r15, r15
0x140009ad2  jz      loc_140009FD2
0x140009ad8  mov     rax, rdi
0x140009adb  inc     rax
0x140009ade  cmp     [r15+rax*2], r11w
0x140009ae3  jnz     short loc_140009ADB
0x140009ae5  mov     r13, [rbp+57h+var_68]
0x140009ae9  lea     r9d, [rcx+rax*2]
0x140009aed  test    r13, r13
0x140009af0  jnz     loc_140009EE7
0x140009af6  mov     r12, [rbp+57h+Src]
0x140009afa  test    r12, r12
0x140009afd  jnz     loc_140009D7D
0x140009b03  mov     r14d, r11d
0x140009b06  lea     ecx, [r12+4]
0x140009b0b  lea     edx, [rcx+10h]
0x140009b0e  add     edx, r9d
0x140009b11  test    r10, r10
0x140009b14  jz      short loc_140009B26
0x140009b16  mov     rax, rdi
0x140009b19  inc     rax
0x140009b1c  cmp     [r10+rax*2], r11w
0x140009b21  jnz     short loc_140009B19
0x140009b23  lea     edx, [rdx+rax*2]
0x140009b26  lea     eax, [rdx+3]
0x140009b29  and     eax, 0FFFFFFFEh
0x140009b2c  mov     [rbp+57h+var_78], eax
0x140009b2f  cmp     eax, [rbp+57h+arg_10]
0x140009b32  ja      loc_140009C82
0x140009b38  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x140009b3c  lea     r8, [rsi+40h]; unsigned __int16 *
0x140009b40  add     rax, rsi
0x140009b43  mov     edx, r11d
0x140009b46  mov     [rbp+57h+var_88], rax
0x140009b4a  test    rcx, rcx
0x140009b4d  jz      short loc_140009B5C
0x140009b4f  mov     rdx, rdi
0x140009b52  inc     rdx; unsigned int
0x140009b55  cmp     [rcx+rdx*2], r11w
0x140009b5a  jnz     short loc_140009B52
0x140009b5c  lea     rax, [rsi+10h]
0x140009b60  mov     [rsp+0E0h+var_B8], r11; unsigned __int8 *
0x140009b65  lea     r9, [rbp+57h+var_88]; unsigned __int16 **
0x140009b69  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 **
0x140009b6e  call    ?ScCopyStringToBufferW@@YAHPEBGK0PEAPEAG1QEAE@Z; ScCopyStringToBufferW(ushort const *,ulong,ushort const *,ushort * *,ushort * *,uchar * const)
0x140009b73  xor     ecx, ecx
0x140009b75  test    eax, eax
0x140009b77  jz      loc_140009D8F
0x140009b7d  mov     edx, ecx; unsigned int
0x140009b7f  test    r13, r13
0x140009b82  jnz     loc_140009ED4
0x140009b88  mov     [rsp+0E0h+var_B8], rcx; unsigned __int8 *
0x140009b8d  lea     rax, [rsi+18h]
0x140009b91  mov     rcx, r13; unsigned __int16 *
0x140009b94  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 **
0x140009b99  lea     r9, [rbp+57h+var_88]; unsigned __int16 **
0x140009b9d  lea     r8, [rsi+40h]; unsigned __int16 *
0x140009ba1  call    ?ScCopyStringToBufferW@@YAHPEBGK0PEAPEAG1QEAE@Z; ScCopyStringToBufferW(ushort const *,ulong,ushort const *,ushort * *,ushort * *,uchar * const)
0x140009ba6  xor     r8d, r8d
0x140009ba9  test    eax, eax
0x140009bab  jz      loc_140009FDB
0x140009bb1  test    r12, r12
0x140009bb4  jnz     loc_140009E78
0x140009bba  mov     rax, [rbp+57h+var_88]
0x140009bbe  add     rax, 0FFFFFFFFFFFFFFFCh
0x140009bc2  mov     [rsi+28h], rax
0x140009bc6  mov     [rbp+57h+var_88], rax
0x140009bca  mov     word ptr [rax], 2Fh ; '/'
0x140009bcf  mov     rcx, [rsi+28h]
0x140009bd3  mov     [rcx+2], r8w
0x140009bd8  mov     rcx, [rbp+57h+P]; unsigned __int16 *
0x140009bdc  mov     edx, r8d
0x140009bdf  test    rcx, rcx
0x140009be2  jz      short loc_140009BF1
0x140009be4  mov     rdx, rdi
0x140009be7  inc     rdx; unsigned int
0x140009bea  cmp     [rcx+rdx*2], r8w
0x140009bef  jnz     short loc_140009BE7
0x140009bf1  mov     [rsp+0E0h+var_B8], r8; unsigned __int8 *
0x140009bf6  lea     rax, [rsi+30h]
0x140009bfa  lea     r8, [rsi+40h]; unsigned __int16 *
0x140009bfe  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 **
0x140009c03  lea     r9, [rbp+57h+var_88]; unsigned __int16 **
0x140009c07  call    ?ScCopyStringToBufferW@@YAHPEBGK0PEAPEAG1QEAE@Z; ScCopyStringToBufferW(ushort const *,ulong,ushort const *,ushort * *,ushort * *,uchar * const)
0x140009c0c  xor     ecx, ecx
0x140009c0e  test    eax, eax
0x140009c10  jz      loc_14000A006
0x140009c16  inc     rdi
0x140009c19  cmp     [r15+rdi*2], cx
0x140009c1e  jnz     short loc_140009C16
0x140009c20  mov     [rsp+0E0h+var_B8], rcx; unsigned __int8 *
0x140009c25  lea     rax, [rsi+38h]
0x140009c29  mov     rcx, r15; unsigned __int16 *
0x140009c2c  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 **
0x140009c31  lea     r9, [rbp+57h+var_88]; unsigned __int16 **
0x140009c35  mov     edx, edi; unsigned int
0x140009c37  lea     r8, [rsi+40h]; unsigned __int16 *
0x140009c3b  call    ?ScCopyStringToBufferW@@YAHPEBGK0PEAPEAG1QEAE@Z; ScCopyStringToBufferW(ushort const *,ulong,ushort const *,ushort * *,ushort * *,uchar * const)
0x140009c40  xor     edi, edi
0x140009c42  test    eax, eax
0x140009c44  jnz     short loc_140009C8D
0x140009c46  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c4d  lea     rax, WPP_GLOBAL_Control
0x140009c54  cmp     rcx, rax
0x140009c57  jz      short loc_140009C72
0x140009c59  test    byte ptr [rcx+1Ch], 1
0x140009c5d  jz      short loc_140009C72
0x140009c5f  lea     edx, [rdi+57h]
0x140009c62  mov     rcx, [rcx+10h]
0x140009c66  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140009c6d  call    WPP_SF_
0x140009c72  lea     rcx, [rbp+57h+var_80]; this
0x140009c76  mov     edi, 7Ah ; 'z'
0x140009c7b  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x140009c80  jmp     short loc_140009C96
0x140009c82  mov     rcx, [rbp+57h+arg_18]
0x140009c86  mov     [rcx], eax
0x140009c88  mov     edi, 7Ah ; 'z'
0x140009c8d  test    rbx, rbx
0x140009c90  jnz     loc_140009D59
0x140009c96  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140009c9d  call    cs:__imp_RtlReleaseResource
0x140009ca3  mov     r14, [rbp+57h+var_90]
0x140009ca7  mov     rcx, [rbp+57h+Handle]; Handle
0x140009cab  test    rcx, rcx
0x140009cae  jz      short loc_140009CBE
0x140009cb0  call    cs:__imp_NtClose
0x140009cb6  mov     ecx, eax; Status
0x140009cb8  call    cs:__imp_RtlNtStatusToDosError
0x140009cbe  mov     rcx, gs:60h
0x140009cc7  xor     edx, edx; Flags
0x140009cc9  mov     r8, [rbp+57h+P]; P
0x140009ccd  mov     rcx, [rcx+30h]; HeapHandle
0x140009cd1  call    cs:__imp_RtlFreeHeap
0x140009cd7  mov     rcx, gs:60h
0x140009ce0  mov     r8, r14; P
0x140009ce3  xor     edx, edx; Flags
0x140009ce5  mov     rcx, [rcx+30h]; HeapHandle
0x140009ce9  call    cs:__imp_RtlFreeHeap
0x140009cef  mov     rax, [rbp+57h+var_40]
0x140009cf3  xor     r14d, r14d
0x140009cf6  test    rax, rax
0x140009cf9  jnz     loc_140009EFE
0x140009cff  mov     rcx, gs:60h
0x140009d08  mov     r8, r13; P
0x140009d0b  xor     edx, edx; Flags
0x140009d0d  mov     rcx, [rcx+30h]; HeapHandle
0x140009d11  call    cs:__imp_RtlFreeHeap
0x140009d17  mov     rcx, gs:60h
0x140009d20  mov     r8, r12; P
0x140009d23  xor     edx, edx; Flags
0x140009d25  mov     rcx, [rcx+30h]; HeapHandle
0x140009d29  call    cs:__imp_RtlFreeHeap
0x140009d2f  mov     rcx, [rbp+57h+arg_18]
0x140009d33  mov     eax, [rbp+57h+var_78]
0x140009d36  mov     [rcx], eax
0x140009d38  test    edi, edi
0x140009d3a  jnz     short loc_140009D67
0x140009d3c  mov     eax, edi
0x140009d3e  mov     rbx, [rsp+0E0h+arg_8]
0x140009d46  add     rsp, 0B0h
0x140009d4d  pop     r15
0x140009d4f  pop     r14
0x140009d51  pop     r13
0x140009d53  pop     r12
0x140009d55  pop     rdi
0x140009d56  pop     rsi
0x140009d57  pop     rbp
0x140009d58  retn
0x140009d59  mov     rcx, rbx; SRWLock
0x140009d5c  call    cs:__imp_ReleaseSRWLockShared
0x140009d62  jmp     loc_140009C96
0x140009d67  mov     [rsi+10h], r14
0x140009d6b  mov     [rsi+18h], r14
0x140009d6f  mov     [rsi+28h], r14
0x140009d73  mov     [rsi+30h], r14
0x140009d77  mov     [rsi+38h], r14
0x140009d7b  jmp     short loc_140009D3C
0x140009d7d  mov     rcx, r12
0x140009d80  call    ScWStrArraySize
0x140009d85  mov     r14d, eax
0x140009d88  mov     ecx, eax
0x140009d8a  jmp     loc_140009B0B
0x140009d8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d96  lea     rax, WPP_GLOBAL_Control
0x140009d9d  cmp     rcx, rax
  ... truncated ...
```
