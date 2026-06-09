# ThumbnailCacheTelemetry::CheckRecreateFileMapping::StartActivity(void)

- ea: `0x18000ef80`
- end: `0x18000f153`
- name: `?StartActivity@CheckRecreateFileMapping@ThumbnailCacheTelemetry@@QEAAXXZ`
- size: `467`
- prototype: `void __fastcall(ThumbnailCacheTelemetry::CheckRecreateFileMapping *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000ec60`

## callees

- `0x18000ef80`
- `0x18001f1c0`
- `0x180020770`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f052`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f052`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000efda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eff2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f038`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000efda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eff2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f038`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000efc4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000efc4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f120`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f120`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f01b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f01b`

## pseudocode

```c
void __fastcall ThumbnailCacheTelemetry::CheckRecreateFileMapping::StartActivity(
        ThumbnailCacheTelemetry::CheckRecreateFileMapping *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // rbx
  __int64 v6; // r8
  const GUID *v7; // r9
  PSRWLOCK v8; // [rsp+38h] [rbp-31h] BYREF
  __int64 v9; // [rsp+40h] [rbp-29h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-9h] BYREF
  char *v12; // [rsp+70h] [rbp+7h]
  int v13; // [rsp+78h] [rbp+Fh]
  int v14; // [rsp+7Ch] [rbp+13h]
  __int64 *v15; // [rsp+80h] [rbp+17h]
  __int64 v16; // [rsp+88h] [rbp+1Fh]
  PSRWLOCK *v17; // [rsp+90h] [rbp+27h]
  __int64 v18; // [rsp+98h] [rbp+2Fh]

  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v2 )
  {
    v3 = v2 + 33;
    AcquireSRWLockExclusive(v3);
  }
  else
  {
    v8 = 0;
    v3 = 0;
  }
  v4 = *((_QWORD *)this + 34);
  if ( **((_DWORD **)ThumbnailCacheLogging::Instance() + 1) <= 5u )
    *(_OWORD *)(v4 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  *(_DWORD *)v4 = 1;
  if ( v3 )
    ReleaseSRWLockExclusive(v3);
  v5 = *((_QWORD *)ThumbnailCacheLogging::Instance() + 1);
  if ( *(_DWORD *)v5 > 5u )
  {
    LODWORD(v8) = GetCurrentThreadId();
    v9 = 0;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = (const GUID *)(v6 + 24), !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    v17 = &v8;
    v18 = 4;
    v15 = &v9;
    v16 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 261;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = *(_QWORD *)(v5 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v12 = byte_1800575C5;
    v13 = 68;
    v14 = 1;
    EventWriteTransfer(*(_QWORD *)(v5 + 32), &EventDescriptor, (LPCGUID)(v6 + 8), v7, 4u, &UserData);
  }
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000ef80  mov     [rsp-8+arg_8], rbx
0x18000ef85  mov     [rsp-8+arg_10], rsi
0x18000ef8a  push    rbp
0x18000ef8b  push    rdi
0x18000ef8c  push    r14
0x18000ef8e  lea     rbp, [rsp-47h]
0x18000ef93  sub     rsp, 0B0h
0x18000ef9a  mov     rax, cs:__security_cookie
0x18000efa1  xor     rax, rsp
0x18000efa4  mov     [rbp+57h+var_20], rax
0x18000efa8  mov     rdi, rcx
0x18000efab  xor     r14d, r14d
0x18000efae  mov     rbx, [rcx+118h]
0x18000efb5  test    rbx, rbx
0x18000efb8  jz      short loc_18000EFE2
0x18000efba  add     rbx, 108h
0x18000efc1  mov     rcx, rbx; SRWLock
0x18000efc4  call    cs:__imp_AcquireSRWLockExclusive
0x18000efca  lea     rax, [rbp+57h+SRWLock]
0x18000efce  mov     [rax], r14
0x18000efd1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000efd5  test    rcx, rcx
0x18000efd8  jz      short loc_18000EFFB
0x18000efda  call    cs:__imp_ReleaseSRWLockExclusive
0x18000efe0  jmp     short loc_18000EFFB
0x18000efe2  lea     rax, [rbp+57h+var_88]
0x18000efe6  mov     [rax], r14
0x18000efe9  mov     rcx, [rbp+57h+var_88]; SRWLock
0x18000efed  test    rcx, rcx
0x18000eff0  jz      short loc_18000EFF8
0x18000eff2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000eff8  mov     rbx, r14
0x18000effb  mov     rsi, [rdi+110h]
0x18000f002  call    ?Instance@ThumbnailCacheLogging@@KAPEAV1@XZ; ThumbnailCacheLogging::Instance(void)
0x18000f007  mov     rcx, [rax+8]
0x18000f00b  mov     eax, [rcx]
0x18000f00d  cmp     eax, 5
0x18000f010  jbe     short loc_18000F023
0x18000f012  lea     rdx, [rsi+8]; ActivityId
0x18000f016  mov     ecx, 3; ControlCode
0x18000f01b  call    cs:__imp_EventActivityIdControl
0x18000f021  jmp     short loc_18000F02A
0x18000f023  xorps   xmm0, xmm0
0x18000f026  movups  xmmword ptr [rsi+8], xmm0
0x18000f02a  mov     dword ptr [rsi], 1
0x18000f030  test    rbx, rbx
0x18000f033  jz      short loc_18000F03E
0x18000f035  mov     rcx, rbx; SRWLock
0x18000f038  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f03e  call    ?Instance@ThumbnailCacheLogging@@KAPEAV1@XZ; ThumbnailCacheLogging::Instance(void)
0x18000f043  mov     rbx, [rax+8]
0x18000f047  mov     eax, [rbx]
0x18000f049  cmp     eax, 5
0x18000f04c  jbe     loc_18000F126
0x18000f052  call    cs:__imp_GetCurrentThreadId
0x18000f058  mov     dword ptr [rbp+57h+var_88], eax
0x18000f05b  mov     [rbp+57h+var_80], r14
0x18000f05f  mov     r8, [rdi+110h]
0x18000f066  cmp     [r8+4], r14b
0x18000f06a  jz      short loc_18000F087
0x18000f06c  lea     r9, [r8+18h]
0x18000f070  cmp     [r9], r14d
0x18000f073  jnz     short loc_18000F08A
0x18000f075  cmp     [r9+4], r14d
0x18000f079  jnz     short loc_18000F08A
0x18000f07b  cmp     [r9+8], r14d
0x18000f07f  jnz     short loc_18000F08A
0x18000f081  cmp     [r9+0Ch], r14d
0x18000f085  jnz     short loc_18000F08A
0x18000f087  mov     r9, r14; RelatedActivityId
0x18000f08a  lea     rax, [rbp+57h+var_88]
0x18000f08e  mov     [rbp+57h+var_30], rax
0x18000f092  mov     [rbp+57h+var_28], 4
0x18000f09a  lea     rax, [rbp+57h+var_80]
0x18000f09e  mov     [rbp+57h+var_40], rax
0x18000f0a2  mov     [rbp+57h+var_38], 8
0x18000f0aa  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000f0b1  movzx   eax, cs:word_1800575BB
0x18000f0b8  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000f0bb  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x18000f0bf  mov     rax, [rbx+8]
0x18000f0c3  mov     [rbp+57h+var_60.Ptr], rax
0x18000f0c7  movzx   eax, word ptr [rax]
0x18000f0ca  mov     [rbp+57h+var_60.Size], eax
0x18000f0cd  mov     dword ptr [rbp+57h+var_60.0Ch], 2
0x18000f0d4  lea     rax, byte_1800575C5
0x18000f0db  mov     [rbp+57h+var_50], rax
0x18000f0df  mov     [rbp+57h+var_48], 44h ; 'D'
0x18000f0e6  mov     [rbp+57h+var_44], 1
0x18000f0ed  lea     rax, _TraceLoggingMetadataEnd
0x18000f0f4  lea     rcx, _TraceLoggingMetadata
0x18000f0fb  sub     eax, ecx
0x18000f0fd  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000f100  mov     eax, dword ptr [rbp+57h+SRWLock]
0x18000f103  add     r8, 8; ActivityId
0x18000f107  lea     rax, [rbp+57h+var_60]
0x18000f10b  mov     [rsp+0C0h+UserData], rax; UserData
0x18000f110  mov     [rsp+0C0h+UserDataCount], 4; UserDataCount
0x18000f118  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000f11c  mov     rcx, [rbx+20h]; RegHandle
0x18000f120  call    cs:__imp_EventWriteTransfer
0x18000f126  mov     rcx, rdi
0x18000f129  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000f12e  nop
0x18000f12f  mov     rcx, [rbp+57h+var_20]
0x18000f133  xor     rcx, rsp; StackCookie
0x18000f136  call    __security_check_cookie
0x18000f13b  lea     r11, [rsp+0C0h+var_10]
0x18000f143  mov     rbx, [r11+28h]
0x18000f147  mov     rsi, [r11+30h]
0x18000f14b  mov     rsp, r11
0x18000f14e  pop     r14
0x18000f150  pop     rdi
0x18000f151  pop     rbp
0x18000f152  retn
```
