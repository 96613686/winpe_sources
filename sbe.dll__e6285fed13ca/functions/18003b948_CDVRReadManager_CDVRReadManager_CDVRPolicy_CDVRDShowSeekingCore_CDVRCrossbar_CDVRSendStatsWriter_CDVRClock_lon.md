# CDVRReadManager::CDVRReadManager(CDVRPolicy *,CDVRDShowSeekingCore *,CDVRCrossbar *,CDVRSendStatsWriter *,CDVRClock *,long *)

- ea: `0x18003b948`
- end: `0x18003bb2e`
- name: `??0CDVRReadManager@@QEAA@PEAVCDVRPolicy@@PEAVCDVRDShowSeekingCore@@PEAVCDVRCrossbar@@PEAVCDVRSendStatsWriter@@PEAVCDVRClock@@PEAJ@Z`
- size: `486`
- prototype: `CDVRReadManager *__fastcall(CDVRReadManager *__hidden this, struct CDVRPolicy *, struct CDVRDShowSeekingCore *, struct CDVRCrossbar *, struct CDVRSendStatsWriter *, struct CDVRClock *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003bb34`

## callees

- `0x180007120`
- `0x18003b948`
- `0x18003eec8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18003bab6`
- `KERNEL32!CreateEventW` at `0x18003bab6`
- `KERNEL32!InitializeCriticalSection` at `0x18003b98c`
- `KERNEL32!InitializeCriticalSection` at `0x18003b996`
- `KERNEL32!InitializeCriticalSection` at `0x18003baa4`
- `KERNEL32!InitializeCriticalSection` at `0x18003b98c`
- `KERNEL32!InitializeCriticalSection` at `0x18003b996`
- `KERNEL32!InitializeCriticalSection` at `0x18003baa4`
- `KERNEL32!GetLastError` at `0x18003bac8`
- `KERNEL32!GetLastError` at `0x18003bac8`

## pseudocode

```c
CDVRReadManager *__fastcall CDVRReadManager::CDVRReadManager(
        CDVRReadManager *this,
        struct CDVRPolicy *a2,
        struct CDVRDShowSeekingCore *a3,
        struct CDVRCrossbar *a4,
        struct CDVRSendStatsWriter *a5,
        struct CDVRClock *a6,
        int *a7)
{
  __int64 v11; // rax
  HANDLE EventW; // rax
  signed int DVRReadController; // eax

  *(_QWORD *)this = &CDVRReadManager::`vftable';
  CAMEvent::CAMEvent((CDVRReadManager *)((char *)this + 16), 1, 0);
  CAMEvent::CAMEvent((CDVRReadManager *)((char *)this + 24), 0, 0);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  *((_QWORD *)this + 16) = this;
  *((_QWORD *)this + 1) = &CDVRDReaderThread::`vftable';
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 30) = a5;
  *((_QWORD *)this + 32) = a6;
  *((_QWORD *)this + 33) = 0x3FF0000000000000LL;
  *((_QWORD *)this + 29) = a2;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = -1;
  *((_DWORD *)this + 46) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_DWORD *)this + 52) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = a4;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 34) = a3;
  *((_DWORD *)this + 70) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 36) = -1;
  *((_QWORD *)this + 37) = -1;
  v11 = *((_QWORD *)this + 29);
  *((_DWORD *)this + 90) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_DWORD *)this + 98) = 1;
  _InterlockedIncrement((volatile signed __int32 *)(v11 + 272));
  *(_OWORD *)((char *)this + 152) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 46) = EventW;
  if ( EventW )
  {
    DVRReadController = CDVRReadManager::GetDVRReadController_(
                          *((int *)this + 46),
                          this,
                          *((_QWORD *)this + 28),
                          *((_QWORD *)this + 29),
                          *((_QWORD *)this + 30),
                          (char *)this + 8 * *((int *)this + 46) + 152);
  }
  else
  {
    DVRReadController = GetLastError();
    if ( DVRReadController > 0 )
      DVRReadController = (unsigned __int16)DVRReadController | 0x80070000;
  }
  *a7 = DVRReadController;
  return this;
}

```

## disassembly

```asm
0x18003b948  push    rbx
0x18003b94a  push    rsi
0x18003b94b  push    rdi
0x18003b94c  push    r14
0x18003b94e  push    r15
0x18003b950  sub     rsp, 30h
0x18003b954  mov     rsi, r8
0x18003b957  lea     rax, ??_7CDVRReadManager@@6B@; const CDVRReadManager::`vftable'
0x18003b95e  xor     r8d, r8d; int *
0x18003b961  mov     [rcx], rax
0x18003b964  mov     rdi, rdx
0x18003b967  mov     r14, rcx
0x18003b96a  add     rcx, 10h; this
0x18003b96e  mov     rbx, r9
0x18003b971  lea     edx, [r8+1]; int
0x18003b975  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x18003b97a  lea     rcx, [r14+18h]; this
0x18003b97e  xor     r8d, r8d; int *
0x18003b981  xor     edx, edx; int
0x18003b983  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x18003b988  lea     rcx, [r14+30h]; lpCriticalSection
0x18003b98c  call    cs:__imp_InitializeCriticalSection
0x18003b992  lea     rcx, [r14+58h]; lpCriticalSection
0x18003b996  call    cs:__imp_InitializeCriticalSection
0x18003b99c  mov     [r14+80h], r14
0x18003b9a3  lea     rax, ??_7CDVRDReaderThread@@6B@; const CDVRDReaderThread::`vftable'
0x18003b9aa  mov     [r14+8], rax
0x18003b9ae  xor     r15d, r15d
0x18003b9b1  mov     rax, [rsp+58h+arg_20]
0x18003b9b9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003b9bd  mov     [r14+28h], r15
0x18003b9c1  mov     [r14+20h], r15d
0x18003b9c5  mov     [r14+0F0h], rax
0x18003b9cc  mov     rax, [rsp+58h+arg_28]
0x18003b9d4  mov     [r14+100h], rax
0x18003b9db  mov     rax, 3FF0000000000000h
0x18003b9e5  mov     [r14+108h], rax
0x18003b9ec  mov     [r14+0E8h], rdi
0x18003b9f3  mov     [r14+88h], r15
0x18003b9fa  mov     [r14+90h], rcx
0x18003ba01  mov     [r14+0B8h], r15d
0x18003ba08  mov     [r14+0C0h], r15
0x18003ba0f  mov     [r14+0C8h], r15
0x18003ba16  mov     [r14+0D0h], r15d
0x18003ba1d  mov     [r14+0D8h], r15
0x18003ba24  mov     [r14+0E0h], rbx
0x18003ba2b  mov     [r14+0F8h], r15
0x18003ba32  mov     [r14+110h], rsi
0x18003ba39  mov     [r14+118h], r15d
0x18003ba40  mov     [r14+130h], r15
0x18003ba47  mov     [r14+120h], rcx
0x18003ba4e  mov     [r14+128h], rcx
0x18003ba55  mov     rax, [r14+0E8h]
0x18003ba5c  mov     [r14+168h], r15d
0x18003ba63  mov     [r14+170h], r15
0x18003ba6a  mov     [r14+178h], r15
0x18003ba71  mov     [r14+180h], r15
0x18003ba78  mov     dword ptr [r14+188h], 1
0x18003ba83  lock inc dword ptr [rax+110h]
0x18003ba8a  xorps   xmm0, xmm0
0x18003ba8d  lea     rcx, [r14+138h]; lpCriticalSection
0x18003ba94  movups  xmmword ptr [r14+98h], xmm0
0x18003ba9c  movups  xmmword ptr [r14+0A8h], xmm0
0x18003baa4  call    cs:__imp_InitializeCriticalSection
0x18003baaa  xor     r9d, r9d; lpName
0x18003baad  lea     edx, [r15+1]; bManualReset
0x18003bab1  xor     r8d, r8d; bInitialState
0x18003bab4  xor     ecx, ecx; lpEventAttributes
0x18003bab6  call    cs:__imp_CreateEventW
0x18003babc  mov     [r14+170h], rax
0x18003bac3  test    rax, rax
0x18003bac6  jnz     short loc_18003BADC
0x18003bac8  call    cs:__imp_GetLastError
0x18003bace  test    eax, eax
0x18003bad0  jle     short loc_18003BB15
0x18003bad2  movzx   eax, ax
0x18003bad5  or      eax, 80070000h
0x18003bada  jmp     short loc_18003BB15
0x18003badc  movsxd  rcx, dword ptr [r14+0B8h]
0x18003bae3  lea     rax, [r14+98h]
0x18003baea  mov     r9, [r14+0E8h]
0x18003baf1  mov     r8, [r14+0E0h]
0x18003baf8  lea     rdx, [rax+rcx*8]
0x18003bafc  mov     rax, [r14+0F0h]
0x18003bb03  mov     [rsp+58h+var_30], rdx
0x18003bb08  mov     rdx, r14
0x18003bb0b  mov     [rsp+58h+var_38], rax
0x18003bb10  call    ?GetDVRReadController_@CDVRReadManager@@CAJW4CONTROLLER_CATEGORY@1@PEAV1@PEAVCDVRCrossbar@@PEAVCDVRPolicy@@PEAVCDVRSendStatsWriter@@PEAPEAVCDVRReadController@@@Z; CDVRReadManager::GetDVRReadController_(CDVRReadManager::CONTROLLER_CATEGORY,CDVRReadManager *,CDVRCrossbar *,CDVRPolicy *,CDVRSendStatsWriter *,CDVRReadController * *)
0x18003bb15  mov     rcx, [rsp+58h+arg_30]
0x18003bb1d  mov     [rcx], eax
0x18003bb1f  mov     rax, r14
0x18003bb22  add     rsp, 30h
0x18003bb26  pop     r15
0x18003bb28  pop     r14
0x18003bb2a  pop     rdi
0x18003bb2b  pop     rsi
0x18003bb2c  pop     rbx
0x18003bb2d  retn
```
