# UnionFs::Utils::CheckShareAccess(ulong,ulong,_FILE_OBJECT &,UnionFs::UfsFsContext &,UnionFs::Utils::IoShareAccessFlags,UnionFs::ShareAccessCaller,UnionFs::StackEventTracer &,bool)

- ea: `0x140069eec`
- end: `0x14006a3c5`
- name: `?CheckShareAccess@Utils@UnionFs@@YAJKKAEAU_FILE_OBJECT@@AEAVUfsFsContext@2@W4IoShareAccessFlags@12@W4ShareAccessCaller@2@AEAVStackEventTracer@2@_N@Z`
- size: `1241`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400114c4`
- `0x140058fbc`

## callees

- `0x140003ef4`
- `0x140004080`
- `0x140056a50`
- `0x140057b40`
- `0x14005a2e0`
- `0x14006785c`
- `0x140069eec`
- `0x14006f51c`
- `0x140079a6c`
- `0x140079ab4`

## import_xrefs

- `ntoskrnl!IoCheckLinkShareAccess` at `0x14006a00b`
- `ntoskrnl!IoCheckLinkShareAccess` at `0x14006a00b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069f7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a1f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a360`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a39b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069f7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a1f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a360`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a39b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006a33e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006a379`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006a33e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006a379`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006a34a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006a385`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006a34a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006a385`

## string_xrefs

- `0x14006a0a9`: `UnionFs::Utils::CheckShareAccess`
- `0x14006a318`: `UnionFs::Utils::CheckShareAccess`
- `0x14006a09e`: `API: CheckShareAccess`
- `0x14006a311`: `API: IoCheckLinkShareAccess`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CheckShareAccess(
        unsigned int a1,
        unsigned int a2,
        struct _ERESOURCE *a3,
        __int64 a4,
        char *a5,
        char a6,
        int a7,
        __int16 a8)
{
  char *v8; // rdi
  int IsEnabledDeviceUsageNoInline; // eax
  int v13; // r14d
  PVOID *v14; // rax
  struct _ERESOURCE *v15; // rbx
  __int64 v16; // rdx
  _OWORD *v17; // rsi
  __int128 v18; // xmm1
  int v19; // r14d
  __int128 v20; // xmm1
  struct _UNICODE_STRING *v21; // r12
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  const struct _UNICODE_STRING *v25; // rax
  bool v26; // zf
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  char *v31; // [rsp+30h] [rbp-F8h]
  struct _ERESOURCE *v32; // [rsp+A8h] [rbp-80h] BYREF
  int v33; // [rsp+B0h] [rbp-78h] BYREF
  unsigned int v34; // [rsp+B4h] [rbp-74h] BYREF
  unsigned int v35; // [rsp+B8h] [rbp-70h] BYREF
  int v36; // [rsp+BCh] [rbp-6Ch] BYREF
  int v37; // [rsp+C0h] [rbp-68h] BYREF
  int v38; // [rsp+C4h] [rbp-64h] BYREF
  int v39; // [rsp+C8h] [rbp-60h] BYREF
  unsigned int v40; // [rsp+CCh] [rbp-5Ch] BYREF
  PVOID P; // [rsp+D0h] [rbp-58h] BYREF
  const char *v42; // [rsp+D8h] [rbp-50h] BYREF
  const char *v43; // [rsp+E0h] [rbp-48h] BYREF
  const struct _UNICODE_STRING *v44; // [rsp+E8h] [rbp-40h] BYREF
  _OWORD v45[5]; // [rsp+F0h] [rbp-38h]
  unsigned int v46; // [rsp+158h] [rbp+30h] BYREF
  unsigned int v47; // [rsp+160h] [rbp+38h] BYREF
  PVOID v48; // [rsp+170h] [rbp+48h] BYREF

  v47 = a2;
  v46 = a1;
  v8 = 0;
  v48 = 0;
  IsEnabledDeviceUsageNoInline = Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline();
  v13 = (int)a5;
  if ( IsEnabledDeviceUsageNoInline )
  {
    v32 = a3;
    LODWORD(v48) = ((unsigned __int8)a5 & 1) + 1;
    v14 = (PVOID *)utl::make_unique<UnionFs::ShareAccessDbg,_FILE_OBJECT *,enum UnionFs::ShareAccessCaller &,enum UnionFs::ShareAccessOperation,unsigned long &,unsigned long &,0>(
                     (unsigned int)&P,
                     (unsigned int)&v32,
                     (unsigned int)&a6,
                     (unsigned int)&v48,
                     (__int64)&v46,
                     (__int64)&v47);
    v8 = (char *)*v14;
    *v14 = 0;
    v48 = v8;
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( !v8 )
      _InterlockedIncrement((volatile signed __int32 *)(a4 + 204));
  }
  v15 = 0;
  if ( (_BYTE)a8 )
  {
    v16 = *(_QWORD *)(a4 + 120) + 56LL;
    if ( (v13 & 3) == 2 )
      FsFltWil::AcquireResourceShared(&v32, v16);
    else
      FsFltWil::AcquireResourceExclusive(&v32, v16);
    v15 = v32;
  }
  v17 = (_OWORD *)(a4 + 152);
  if ( (unsigned int)Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline() && v8 )
  {
    v18 = *(_OWORD *)(a4 + 164);
    v45[0] = *v17;
    *(_OWORD *)((char *)v45 + 12) = v18;
    *(_OWORD *)(v8 + 24) = v45[0];
    *(_OWORD *)(v8 + 36) = v18;
  }
  LODWORD(v31) = v13;
  v19 = IoCheckLinkShareAccess(v46, a2, a3, a4 + 152, 0);
  if ( (unsigned int)Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v8 )
    {
      *((_DWORD *)v8 + 70) = v19;
      v20 = *(_OWORD *)(a4 + 164);
      v45[0] = *v17;
      *(_OWORD *)((char *)v45 + 12) = v20;
      *((_OWORD *)v8 + 4) = v45[0];
      *(_OWORD *)(v8 + 76) = v20;
      v8[104] = BYTE2(a3->NumberOfSharedWaiters);
      v8[105] = HIBYTE(a3->NumberOfSharedWaiters);
      v8[106] = a3->NumberOfExclusiveWaiters;
      v8[107] = BYTE1(a3->NumberOfExclusiveWaiters);
      v8[108] = BYTE2(a3->NumberOfExclusiveWaiters);
      v8[109] = HIBYTE(a3->NumberOfExclusiveWaiters);
      UnionFs::UfsFsContext::AddShareAccessDbgEntry(a4, &v48);
      v8 = (char *)v48;
    }
    if ( v19 < 0 )
    {
      UnionFs::Utils::GetProcessImageFileName(&v48);
      v21 = (struct _UNICODE_STRING *)v48;
      if ( v48 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v19,
          a7,
          (struct UnionFs::StackEventTracer *)0x61B00210AC6LL,
          (unsigned __int64)"UnionFs::Utils::CheckShareAccess",
          "API: CheckShareAccess",
          v31);
        if ( (unsigned int)dword_14009E178 > 2 )
        {
          LODWORD(v48) = *(_DWORD *)(a4 + 176);
          v33 = *(_DWORD *)(a4 + 172);
          v34 = *(_DWORD *)(a4 + 168);
          v35 = *(_DWORD *)(a4 + 164);
          v36 = *(_DWORD *)(a4 + 160);
          v37 = *(_DWORD *)(a4 + 156);
          v38 = *(_DWORD *)v17;
          v39 = (int)a5;
          v40 = v47;
          LODWORD(P) = v46;
          v25 = &FsTlEmptyUnicodeString;
          v26 = v21->Buffer == 0;
          v42 = (const char *)a4;
          if ( !v26 )
            v25 = v21;
          LODWORD(v32) = 1563;
          v44 = v25;
          a8 = 2758;
          v43 = "UnionFs::Utils::CheckShareAccess";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)&word_14009A42E,
            v23,
            v24,
            (__int64)&v43,
            (__int64)&v32,
            (__int64)&a8,
            (__int64)&v42,
            (__int64)&v44,
            (__int64)&P,
            (__int64)&v40,
            (__int64)&v39,
            (__int64)&v38,
            (__int64)&v37,
            (__int64)&v36,
            (__int64)&v35,
            (__int64)&v34,
            (__int64)&v33,
            (__int64)&v48);
        }
        if ( v21 )
          ExFreePoolWithTag(v21, 0);
      }
      else
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v19,
          a7,
          (struct UnionFs::StackEventTracer *)0x61E00210ADBLL,
          (unsigned __int64)"UnionFs::Utils::CheckShareAccess",
          "API: CheckShareAccess",
          v31);
        if ( (unsigned int)dword_14009E178 > 2 )
        {
          LODWORD(v48) = *(_DWORD *)(a4 + 176);
          LODWORD(v32) = *(_DWORD *)(a4 + 172);
          LODWORD(P) = *(_DWORD *)(a4 + 168);
          v40 = *(_DWORD *)(a4 + 164);
          v39 = *(_DWORD *)(a4 + 160);
          v38 = *(_DWORD *)(a4 + 156);
          v37 = *(_DWORD *)v17;
          v36 = (int)a5;
          v35 = v47;
          v34 = v46;
          a8 = 2779;
          v43 = (const char *)a4;
          v33 = 1566;
          v42 = "UnionFs::Utils::CheckShareAccess";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v27,
            (unsigned int)&dword_140099D0C,
            v28,
            v29,
            (__int64)&v42,
            (__int64)&v33,
            (__int64)&a8,
            (__int64)&v43,
            (__int64)&v34,
            (__int64)&v35,
            (__int64)&v36,
            (__int64)&v37,
            (__int64)&v38,
            (__int64)&v39,
            (__int64)&v40,
            (__int64)&P,
            (__int64)&v32,
            (__int64)&v48);
        }
      }
      goto LABEL_29;
    }
  }
  else if ( v19 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v19,
      a7,
      (struct UnionFs::StackEventTracer *)0x22D00210AE1LL,
      (unsigned __int64)"UnionFs::Utils::CheckShareAccess",
      "API: IoCheckLinkShareAccess",
      v31);
LABEL_29:
    if ( v15 )
    {
      ExReleaseResourceLite(v15);
      KeLeaveCriticalRegion();
    }
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
    return (unsigned int)v19;
  }
  if ( v15 )
  {
    ExReleaseResourceLite(v15);
    KeLeaveCriticalRegion();
  }
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  return 0;
}

```

## disassembly

```asm
0x140069eec  mov     rax, rsp
0x140069eef  mov     [rax+18h], rbx
0x140069ef3  mov     [rax+10h], edx
0x140069ef6  mov     [rax+8], ecx
0x140069ef9  push    rbp
0x140069efa  push    rsi
0x140069efb  push    rdi
0x140069efc  push    r12
0x140069efe  push    r13
0x140069f00  push    r14
0x140069f02  push    r15
0x140069f04  lea     rbp, [rax-28h]
0x140069f08  sub     rsp, 110h
0x140069f0f  xor     edi, edi
0x140069f11  mov     r13, r9
0x140069f14  mov     [rbp+20h+arg_18], rdi
0x140069f18  mov     r15, r8
0x140069f1b  mov     r12d, edx
0x140069f1e  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x140069f23  mov     r14d, dword ptr [rbp+20h+arg_20]
0x140069f27  test    eax, eax
0x140069f29  jz      short loc_140069F95
0x140069f2b  mov     eax, r14d
0x140069f2e  mov     [rbp+20h+var_A0], r15
0x140069f32  and     eax, 1
0x140069f35  lea     r9, [rbp+20h+arg_18]
0x140069f39  inc     eax
0x140069f3b  lea     r8, [rbp+20h+arg_28]
0x140069f3f  mov     dword ptr [rbp+20h+arg_18], eax
0x140069f42  lea     rdx, [rbp+20h+var_A0]
0x140069f46  lea     rax, [rbp+20h+arg_8]
0x140069f4a  mov     [rsp+140h+var_118], rax
0x140069f4f  lea     rcx, [rbp+20h+P]
0x140069f53  lea     rax, [rbp+20h+arg_0]
0x140069f57  mov     [rsp+140h+var_120], rax
0x140069f5c  call    ??$make_unique@UShareAccessDbg@UnionFs@@PEAU_FILE_OBJECT@@AEAW4ShareAccessCaller@2@W4ShareAccessOperation@2@AEAKAEAK$0A@@utl@@YA?AV?$unique_ptr@UShareAccessDbg@UnionFs@@U?$default_delete@UShareAccessDbg@UnionFs@@@utl@@@0@$$QEAPEAU_FILE_OBJECT@@AEAW4ShareAccessCaller@UnionFs@@$$QEAW4ShareAccessOperation@4@AEAK3@Z; utl::make_unique<UnionFs::ShareAccessDbg,_FILE_OBJECT *,UnionFs::ShareAccessCaller &,UnionFs::ShareAccessOperation,ulong &,ulong &,0>(_FILE_OBJECT * &&,UnionFs::ShareAccessCaller &,UnionFs::ShareAccessOperation &&,ulong &,ulong &)
0x140069f61  mov     rdi, [rax]
0x140069f64  mov     qword ptr [rax], 0
0x140069f6b  mov     rcx, [rbp+20h+P]; P
0x140069f6f  mov     [rbp+20h+arg_18], rdi
0x140069f73  test    rcx, rcx
0x140069f76  jz      short loc_140069F86
0x140069f78  xor     edx, edx; Tag
0x140069f7a  call    cs:__imp_ExFreePoolWithTag
0x140069f81  nop     dword ptr [rax+rax+00h]
0x140069f86  test    rdi, rdi
0x140069f89  jnz     short loc_140069F95
0x140069f8b  nop
0x140069f8c  lock inc dword ptr [r13+0CCh]
0x140069f94  nop
0x140069f95  xor     ebx, ebx
0x140069f97  cmp     byte ptr [rbp+20h+arg_38], bl
0x140069f9a  jz      short loc_140069FC1
0x140069f9c  mov     rdx, [r13+78h]
0x140069fa0  lea     rcx, [rbp+20h+var_A0]
0x140069fa4  mov     eax, r14d
0x140069fa7  add     rdx, 38h ; '8'
0x140069fab  and     al, 3
0x140069fad  cmp     al, 2
0x140069faf  jnz     short loc_140069FB8
0x140069fb1  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x140069fb6  jmp     short loc_140069FBD
0x140069fb8  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140069fbd  mov     rbx, [rbp+20h+var_A0]
0x140069fc1  lea     rsi, [r13+98h]
0x140069fc8  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x140069fcd  test    eax, eax
0x140069fcf  jz      short loc_140069FF1
0x140069fd1  test    rdi, rdi
0x140069fd4  jz      short loc_140069FF1
0x140069fd6  movups  xmm0, xmmword ptr [rsi]
0x140069fd9  movups  xmm1, xmmword ptr [rsi+0Ch]
0x140069fdd  movups  [rbp+20h+var_58], xmm0
0x140069fe1  movups  [rbp+20h+var_58+0Ch], xmm1
0x140069fe5  movups  xmm0, [rbp+20h+var_58]
0x140069fe9  movups  xmmword ptr [rdi+18h], xmm0
0x140069fed  movups  xmmword ptr [rdi+24h], xmm1
0x140069ff1  mov     ecx, [rbp+20h+arg_0]
0x140069ff4  mov     r9, rsi
0x140069ff7  mov     dword ptr [rsp+140h+var_118], r14d; char *
0x140069ffc  mov     r8, r15
0x140069fff  mov     edx, r12d
0x14006a002  mov     [rsp+140h+var_120], 0
0x14006a00b  call    cs:__imp_IoCheckLinkShareAccess
0x14006a012  nop     dword ptr [rax+rax+00h]
0x14006a017  mov     r14d, eax
0x14006a01a  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x14006a01f  test    eax, eax
0x14006a021  jz      loc_14006A308
0x14006a027  test    rdi, rdi
0x14006a02a  jz      short loc_14006A088
0x14006a02c  mov     [rdi+118h], r14d
0x14006a033  lea     rdx, [rbp+20h+arg_18]
0x14006a037  movups  xmm0, xmmword ptr [rsi]
0x14006a03a  mov     rcx, r13
0x14006a03d  movups  xmm1, xmmword ptr [rsi+0Ch]
0x14006a041  movups  [rbp+20h+var_58], xmm0
0x14006a045  movups  [rbp+20h+var_58+0Ch], xmm1
0x14006a049  movups  xmm0, [rbp+20h+var_58]
0x14006a04d  movups  xmmword ptr [rdi+40h], xmm0
0x14006a051  movups  xmmword ptr [rdi+4Ch], xmm1
0x14006a055  mov     al, [r15+4Ah]
0x14006a059  mov     [rdi+68h], al
0x14006a05c  mov     al, [r15+4Bh]
0x14006a060  mov     [rdi+69h], al
0x14006a063  mov     al, [r15+4Ch]
0x14006a067  mov     [rdi+6Ah], al
0x14006a06a  mov     al, [r15+4Dh]
0x14006a06e  mov     [rdi+6Bh], al
0x14006a071  mov     al, [r15+4Eh]
0x14006a075  mov     [rdi+6Ch], al
0x14006a078  mov     al, [r15+4Fh]
0x14006a07c  mov     [rdi+6Dh], al
0x14006a07f  call    ?AddShareAccessDbgEntry@UfsFsContext@UnionFs@@QEAAX$$QEAV?$unique_ptr@UShareAccessDbg@UnionFs@@U?$default_delete@UShareAccessDbg@UnionFs@@@utl@@@utl@@@Z; UnionFs::UfsFsContext::AddShareAccessDbgEntry(utl::unique_ptr<UnionFs::ShareAccessDbg,utl::default_delete<UnionFs::ShareAccessDbg>> &&)
0x14006a084  mov     rdi, [rbp+20h+arg_18]
0x14006a088  test    r14d, r14d
0x14006a08b  jns     loc_14006A371
0x14006a091  lea     rcx, [rbp+20h+arg_18]
0x14006a095  call    ?GetProcessImageFileName@Utils@UnionFs@@YA?AV?$unique_ptr@U_UNICODE_STRING@@U?$default_delete@U_UNICODE_STRING@@@utl@@@utl@@PEAU_KPROCESS@@@Z; UnionFs::Utils::GetProcessImageFileName(_KPROCESS *)
0x14006a09a  mov     r12, [rbp+20h+arg_18]
0x14006a09e  lea     rax, aApiChecksharea; "API: CheckShareAccess"
0x14006a0a5  mov     rdx, qword ptr [rbp+20h+arg_30]; int
0x14006a0a9  lea     r15, aUnionfsUtilsCh_0; "UnionFs::Utils::CheckShareAccess"
0x14006a0b0  mov     [rsp+140h+var_120], rax; char *
0x14006a0b5  mov     ecx, r14d; this
0x14006a0b8  mov     r9, r15; unsigned __int64
0x14006a0bb  test    r12, r12
0x14006a0be  jz      loc_14006A205
0x14006a0c4  mov     r8, 61B00210AC6h; struct UnionFs::StackEventTracer *
0x14006a0ce  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a0d3  mov     eax, cs:dword_14009E178
0x14006a0d9  cmp     eax, 2
0x14006a0dc  jbe     loc_14006A1E6
0x14006a0e2  mov     eax, [rsi+18h]
0x14006a0e5  lea     rdx, word_14009A42E
0x14006a0ec  mov     dword ptr [rbp+20h+arg_18], eax
0x14006a0ef  mov     eax, [rsi+14h]
0x14006a0f2  mov     [rbp+20h+var_98], eax
0x14006a0f5  mov     eax, [rsi+10h]
0x14006a0f8  mov     [rbp+20h+var_94], eax
0x14006a0fb  mov     eax, [rsi+0Ch]
0x14006a0fe  mov     [rbp+20h+var_90], eax
0x14006a101  mov     eax, [rsi+8]
0x14006a104  mov     [rbp+20h+var_8C], eax
0x14006a107  mov     eax, [rsi+4]
0x14006a10a  mov     [rbp+20h+var_88], eax
0x14006a10d  mov     eax, [rsi]
0x14006a10f  mov     [rbp+20h+var_84], eax
0x14006a112  mov     eax, dword ptr [rbp+20h+arg_20]
0x14006a115  mov     [rbp+20h+var_80], eax
0x14006a118  mov     eax, [rbp+20h+arg_8]
0x14006a11b  mov     [rbp+20h+var_7C], eax
0x14006a11e  mov     eax, [rbp+20h+arg_0]
0x14006a121  mov     dword ptr [rbp+20h+P], eax
0x14006a124  lea     rax, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x14006a12b  cmp     qword ptr [r12+8], 0
0x14006a131  mov     [rbp+20h+var_70], r13
0x14006a135  cmovnz  rax, r12
0x14006a139  mov     dword ptr [rbp+20h+var_A0], 61Bh
0x14006a140  mov     [rbp+20h+var_60], rax
0x14006a144  mov     eax, 0AC6h
0x14006a149  mov     [rbp+20h+arg_38], ax
0x14006a14d  lea     rax, [rbp+20h+arg_18]
0x14006a151  mov     [rsp+90h], rax
0x14006a159  lea     rax, [rbp+20h+var_98]
0x14006a15d  mov     [rsp+140h+var_B8], rax
0x14006a165  lea     rax, [rbp+20h+var_94]
0x14006a169  mov     [rsp+140h+var_C0], rax
0x14006a171  lea     rax, [rbp+20h+var_90]
0x14006a175  mov     [rsp+140h+var_C8], rax
0x14006a17a  lea     rax, [rbp+20h+var_8C]
0x14006a17e  mov     [rsp+140h+var_D0], rax
0x14006a183  lea     rax, [rbp+20h+var_88]
0x14006a187  mov     [rsp+140h+var_D8], rax
0x14006a18c  lea     rax, [rbp+20h+var_84]
0x14006a190  mov     [rsp+140h+var_E0], rax
0x14006a195  lea     rax, [rbp+20h+var_80]
0x14006a199  mov     [rsp+140h+var_E8], rax
0x14006a19e  lea     rax, [rbp+20h+var_7C]
0x14006a1a2  mov     [rsp+140h+var_F0], rax
0x14006a1a7  lea     rax, [rbp+20h+P]
0x14006a1ab  mov     [rsp+140h+var_F8], rax
0x14006a1b0  lea     rax, [rbp+20h+var_60]
0x14006a1b4  mov     [rsp+140h+var_100], rax
0x14006a1b9  lea     rax, [rbp+20h+var_70]
0x14006a1bd  mov     [rsp+140h+var_108], rax
0x14006a1c2  lea     rax, [rbp+20h+arg_38]
0x14006a1c6  mov     [rsp+140h+var_110], rax
0x14006a1cb  lea     rax, [rbp+20h+var_A0]
0x14006a1cf  mov     [rsp+140h+var_118], rax
0x14006a1d4  lea     rax, [rbp+20h+var_68]
0x14006a1d8  mov     [rsp+140h+var_120], rax
0x14006a1dd  mov     [rbp+20h+var_68], r15
0x14006a1e1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@4444444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14006a1e6  test    r12, r12
0x14006a1e9  jz      loc_14006A336
0x14006a1ef  xor     edx, edx; Tag
0x14006a1f1  mov     rcx, r12; P
0x14006a1f4  call    cs:__imp_ExFreePoolWithTag
0x14006a1fb  nop     dword ptr [rax+rax+00h]
0x14006a200  jmp     loc_14006A336
0x14006a205  mov     r8, 61E00210ADBh; struct UnionFs::StackEventTracer *
0x14006a20f  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a214  mov     eax, cs:dword_14009E178
0x14006a21a  cmp     eax, 2
0x14006a21d  jbe     loc_14006A336
0x14006a223  mov     eax, [rsi+18h]
0x14006a226  lea     rdx, dword_140099D0C
0x14006a22d  mov     dword ptr [rbp+20h+arg_18], eax
0x14006a230  mov     eax, [rsi+14h]
0x14006a233  mov     dword ptr [rbp+20h+var_A0], eax
0x14006a236  mov     eax, [rsi+10h]
0x14006a239  mov     dword ptr [rbp+20h+P], eax
0x14006a23c  mov     eax, [rsi+0Ch]
0x14006a23f  mov     [rbp+20h+var_7C], eax
0x14006a242  mov     eax, [rsi+8]
0x14006a245  mov     [rbp+20h+var_80], eax
0x14006a248  mov     eax, [rsi+4]
0x14006a24b  mov     [rbp+20h+var_84], eax
0x14006a24e  mov     eax, [rsi]
0x14006a250  mov     [rbp+20h+var_88], eax
0x14006a253  mov     eax, dword ptr [rbp+20h+arg_20]
0x14006a256  mov     [rbp+20h+var_8C], eax
0x14006a259  mov     eax, [rbp+20h+arg_8]
0x14006a25c  mov     [rbp+20h+var_90], eax
0x14006a25f  mov     eax, [rbp+20h+arg_0]
0x14006a262  mov     [rbp+20h+var_94], eax
0x14006a265  mov     eax, 0ADBh
0x14006a26a  mov     [rbp+20h+arg_38], ax
0x14006a26e  lea     rax, [rbp+20h+arg_18]
0x14006a272  mov     [rsp+140h+var_B8], rax
0x14006a27a  lea     rax, [rbp+20h+var_A0]
0x14006a27e  mov     [rsp+140h+var_C0], rax
0x14006a286  lea     rax, [rbp+20h+P]
0x14006a28a  mov     [rsp+140h+var_C8], rax
0x14006a28f  lea     rax, [rbp+20h+var_7C]
0x14006a293  mov     [rsp+140h+var_D0], rax
0x14006a298  lea     rax, [rbp+20h+var_80]
0x14006a29c  mov     [rsp+140h+var_D8], rax
0x14006a2a1  lea     rax, [rbp+20h+var_84]
0x14006a2a5  mov     [rsp+140h+var_E0], rax
0x14006a2aa  lea     rax, [rbp+20h+var_88]
0x14006a2ae  mov     [rsp+140h+var_E8], rax
0x14006a2b3  lea     rax, [rbp+20h+var_8C]
0x14006a2b7  mov     [rsp+140h+var_F0], rax
0x14006a2bc  lea     rax, [rbp+20h+var_90]
0x14006a2c0  mov     [rsp+140h+var_F8], rax
0x14006a2c5  lea     rax, [rbp+20h+var_94]
0x14006a2c9  mov     [rsp+140h+var_100], rax
0x14006a2ce  lea     rax, [rbp+20h+var_68]
0x14006a2d2  mov     [rsp+140h+var_108], rax
0x14006a2d7  lea     rax, [rbp+20h+arg_38]
0x14006a2db  mov     [rsp+140h+var_110], rax
0x14006a2e0  lea     rax, [rbp+20h+var_98]
0x14006a2e4  mov     [rsp+140h+var_118], rax
0x14006a2e9  lea     rax, [rbp+20h+var_70]
0x14006a2ed  mov     [rsp+140h+var_120], rax
0x14006a2f2  mov     [rbp+20h+var_68], r13
0x14006a2f6  mov     [rbp+20h+var_98], 61Eh
0x14006a2fd  mov     [rbp+20h+var_70], r15
0x14006a301  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$07@@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$07@@4444444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14006a306  jmp     short loc_14006A336
0x14006a308  test    r14d, r14d
0x14006a30b  jns     short loc_14006A371
0x14006a30d  mov     rdx, qword ptr [rbp+20h+arg_30]; int
0x14006a311  lea     rax, aApiIochecklink; "API: IoCheckLinkShareAccess"
0x14006a318  lea     r9, aUnionfsUtilsCh_0; "UnionFs::Utils::CheckShareAccess"
0x14006a31f  mov     [rsp+140h+var_120], rax; char *
0x14006a324  mov     r8, 22D00210AE1h; struct UnionFs::StackEventTracer *
0x14006a32e  mov     ecx, r14d; this
0x14006a331  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a336  test    rbx, rbx
0x14006a339  jz      short loc_14006A356
0x14006a33b  mov     rcx, rbx; Resource
0x14006a33e  call    cs:__imp_ExReleaseResourceLite
0x14006a345  nop     dword ptr [rax+rax+00h]
0x14006a34a  call    cs:__imp_KeLeaveCriticalRegion
0x14006a351  nop     dword ptr [rax+rax+00h]
0x14006a356  test    rdi, rdi
0x14006a359  jz      short loc_14006A36C
0x14006a35b  xor     edx, edx; Tag
0x14006a35d  mov     rcx, rdi; P
0x14006a360  call    cs:__imp_ExFreePoolWithTag
0x14006a367  nop     dword ptr [rax+rax+00h]
0x14006a36c  mov     eax, r14d
0x14006a36f  jmp     short loc_14006A3A9
0x14006a371  test    rbx, rbx
0x14006a374  jz      short loc_14006A391
0x14006a376  mov     rcx, rbx; Resource
0x14006a379  call    cs:__imp_ExReleaseResourceLite
0x14006a380  nop     dword ptr [rax+rax+00h]
0x14006a385  call    cs:__imp_KeLeaveCriticalRegion
0x14006a38c  nop     dword ptr [rax+rax+00h]
0x14006a391  test    rdi, rdi
0x14006a394  jz      short loc_14006A3A7
0x14006a396  xor     edx, edx; Tag
0x14006a398  mov     rcx, rdi; P
0x14006a39b  call    cs:__imp_ExFreePoolWithTag
0x14006a3a2  nop     dword ptr [rax+rax+00h]
0x14006a3a7  xor     eax, eax
  ... truncated ...
```
