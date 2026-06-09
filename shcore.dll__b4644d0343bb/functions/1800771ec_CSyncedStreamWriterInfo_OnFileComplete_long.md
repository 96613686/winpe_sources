# CSyncedStreamWriterInfo::OnFileComplete(long)

- ea: `0x1800771ec`
- end: `0x1800772b3`
- name: `?OnFileComplete@CSyncedStreamWriterInfo@@QEAAJJ@Z`
- size: `199`
- prototype: `__int64 __fastcall(CSyncedStreamWriterInfo *__hidden this, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180012f60`
- `0x1800772bc`

## callees

- `0x180013578`
- `0x180047594`
- `0x180066910`
- `0x1800771ec`
- `0x1800791c4`
- `0x18007a2ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180077234`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180077234`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077268`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077268`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077217`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077217`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180077256`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180077256`

## pseudocode

```c
__int64 __fastcall CSyncedStreamWriterInfo::OnFileComplete(CSyncedStreamWriterInfo *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  CStreamWriterTimeoutManager *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // r8
  _BYTE v9[16]; // [rsp+30h] [rbp-38h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 152);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  CSyncedStreamWriterInfo::_OnDataWritten(this, 0, a2, 1);
  SetEvent(*((HANDLE *)this + 1));
  CStreamWriterTimeoutManager::RevokeWriter(v5, *((_DWORD *)this + 48), this);
  if ( a2 < 0 && *((_BYTE *)this + 76) )
    DeleteFileW(*((LPCWSTR *)this + 6));
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release((char *)this + 8);
  LeaveCriticalSection(v2);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v6, FileAccessAPI_StreamedFile_WriteStream_Stop, v7, 1, v9);
  return 0;
}

```

## disassembly

```asm
0x1800771ec  mov     [rsp+arg_10], rbx
0x1800771f1  push    rsi
0x1800771f2  push    rdi
0x1800771f3  push    r14
0x1800771f5  sub     rsp, 50h
0x1800771f9  mov     rax, cs:__security_cookie
0x180077200  xor     rax, rsp
0x180077203  mov     [rsp+68h+var_28], rax
0x180077208  lea     rsi, [rcx+98h]
0x18007720f  mov     rdi, rcx
0x180077212  mov     rcx, rsi; lpCriticalSection
0x180077215  mov     ebx, edx
0x180077217  call    cs:__imp_EnterCriticalSection
0x18007721d  mov     r9d, 1; int
0x180077223  mov     r8d, ebx; int
0x180077226  xor     edx, edx; unsigned __int64
0x180077228  mov     rcx, rdi; this
0x18007722b  call    ?_OnDataWritten@CSyncedStreamWriterInfo@@AEAAJ_KJH@Z; CSyncedStreamWriterInfo::_OnDataWritten(unsigned __int64,long,int)
0x180077230  mov     rcx, [rdi+8]; hEvent
0x180077234  call    cs:__imp_SetEvent
0x18007723a  mov     edx, [rdi+0C0h]; unsigned int
0x180077240  mov     r8, rdi; struct CSyncedStreamWriterInfo *
0x180077243  call    ?RevokeWriter@CStreamWriterTimeoutManager@@QEAAXKPEAVCSyncedStreamWriterInfo@@@Z; CStreamWriterTimeoutManager::RevokeWriter(ulong,CSyncedStreamWriterInfo *)
0x180077248  test    ebx, ebx
0x18007724a  jns     short loc_18007725C
0x18007724c  cmp     byte ptr [rdi+4Ch], 0
0x180077250  jz      short loc_18007725C
0x180077252  mov     rcx, [rdi+30h]; lpFileName
0x180077256  call    cs:__imp_DeleteFileW
0x18007725c  lea     rcx, [rdi+8]
0x180077260  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180077265  mov     rcx, rsi; lpCriticalSection
0x180077268  call    cs:__imp_LeaveCriticalSection
0x18007726e  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180077275  jz      short loc_180077293
0x180077277  lea     rax, [rsp+68h+var_38]
0x18007727c  mov     r9d, 1
0x180077282  lea     rdx, FileAccessAPI_StreamedFile_WriteStream_Stop
0x180077289  mov     [rsp+68h+var_48], rax
0x18007728e  call    McGenEventWrite_EventWriteTransfer
0x180077293  xor     eax, eax
0x180077295  mov     rcx, [rsp+68h+var_28]
0x18007729a  xor     rcx, rsp; StackCookie
0x18007729d  call    __security_check_cookie
0x1800772a2  mov     rbx, [rsp+68h+arg_10]
0x1800772aa  add     rsp, 50h
0x1800772ae  pop     r14
0x1800772b0  pop     rdi
0x1800772b1  pop     rsi
0x1800772b2  retn
```
