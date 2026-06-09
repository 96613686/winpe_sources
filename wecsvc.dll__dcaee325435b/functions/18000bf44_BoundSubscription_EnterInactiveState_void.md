# BoundSubscription::EnterInactiveState(void)

- ea: `0x18000bf44`
- end: `0x18000c0e0`
- name: `?EnterInactiveState@BoundSubscription@@AEAAXXZ`
- size: `412`
- prototype: `void __fastcall(BoundSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000c2d8`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18000bf44`
- `0x18000d480`
- `0x180011a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c03c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c03c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000bfe6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000bfe6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000c02e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000c02e`

## string_xrefs

- `0x18000c07e`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall BoundSubscription::EnterInactiveState(BoundSubscription *this)
{
  _QWORD *v2; // r8
  _QWORD *v3; // rax
  bool v4; // zf
  void *v5; // rdx
  unsigned int DueTime; // ebx
  DWORD LastError; // ebx
  void **pExceptionObject; // [rsp+40h] [rbp-68h] BYREF
  char v9; // [rsp+48h] [rbp-60h]
  const char *v10; // [rsp+50h] [rbp-58h]
  __int64 v11; // [rsp+58h] [rbp-50h]
  __int64 v12; // [rsp+60h] [rbp-48h]
  DWORD v13; // [rsp+68h] [rbp-40h]
  int v14; // [rsp+6Ch] [rbp-3Ch]
  int v15; // [rsp+70h] [rbp-38h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v2 = (_QWORD *)((char *)this + 72);
    if ( *((_QWORD *)this + 12) >= 8u )
      v2 = (_QWORD *)*v2;
    v3 = (_QWORD *)(*((_QWORD *)this + 8) + 56LL);
    if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
      v3 = (_QWORD *)*v3;
    WPP_SF_dSSq(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v3, (__int64)v2, (char)this);
  }
  v4 = *((_DWORD *)this + 70) == 0;
  *((_DWORD *)this + 62) = 0;
  *((_DWORD *)this + 14) = 0;
  if ( !v4 )
  {
    v5 = (void *)*((_QWORD *)this + 30);
    if ( v5 )
    {
      DeleteTimerQueueTimer(0, v5, 0);
      *((_QWORD *)this + 30) = 0;
    }
    DueTime = 60000 * *((_DWORD *)this + 70);
    *((_QWORD *)this + 34) = GetNextRetryTime(DueTime);
    if ( !CreateTimerQueueTimer(
            (PHANDLE)this + 30,
            0,
            (WAITORTIMERCALLBACK)BoundSubscription::CleanupInativeEventresourceCallback,
            this,
            DueTime,
            0,
            0) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, LastError);
      }
      v9 = 0;
      v10 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
      v11 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v12 = 0;
      v13 = LastError;
      v14 = -1;
      v15 = 1779;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x18000bf44  push    rbx
0x18000bf46  push    rsi
0x18000bf47  push    rdi
0x18000bf48  push    r14
0x18000bf4a  sub     rsp, 88h
0x18000bf51  mov     rdi, rcx
0x18000bf54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf5b  lea     r14, WPP_GLOBAL_Control
0x18000bf62  cmp     rcx, r14
0x18000bf65  jz      short loc_18000BFB4
0x18000bf67  test    byte ptr [rcx+1Ch], 10h
0x18000bf6b  jz      short loc_18000BFB4
0x18000bf6d  cmp     byte ptr [rcx+19h], 5
0x18000bf71  jb      short loc_18000BFB4
0x18000bf73  lea     r8, [rdi+48h]
0x18000bf77  cmp     qword ptr [r8+18h], 8
0x18000bf7c  jb      short loc_18000BF81
0x18000bf7e  mov     r8, [r8]
0x18000bf81  mov     rax, [rdi+40h]
0x18000bf85  add     rax, 38h ; '8'
0x18000bf89  cmp     qword ptr [rax+18h], 8
0x18000bf8e  jb      short loc_18000BF93
0x18000bf90  mov     rax, [rax]
0x18000bf93  mov     r9d, [rdi+38h]
0x18000bf97  mov     edx, 2Eh ; '.'
0x18000bf9c  mov     rcx, [rcx+10h]; LoggerHandle
0x18000bfa0  mov     qword ptr [rsp+0A8h+Flags], rdi; char
0x18000bfa5  mov     qword ptr [rsp+0A8h+Period], r8; __int64
0x18000bfaa  mov     qword ptr [rsp+0A8h+DueTime], rax; __int64
0x18000bfaf  call    WPP_SF_dSSq
0x18000bfb4  cmp     dword ptr [rdi+118h], 0
0x18000bfbb  mov     dword ptr [rdi+0F8h], 0
0x18000bfc5  mov     dword ptr [rdi+38h], 0
0x18000bfcc  jz      loc_18000C0D3
0x18000bfd2  lea     rsi, [rdi+0F0h]
0x18000bfd9  mov     rdx, [rsi]; Timer
0x18000bfdc  test    rdx, rdx
0x18000bfdf  jz      short loc_18000BFF3
0x18000bfe1  xor     r8d, r8d; CompletionEvent
0x18000bfe4  xor     ecx, ecx; TimerQueue
0x18000bfe6  call    cs:__imp_DeleteTimerQueueTimer
0x18000bfec  mov     qword ptr [rsi], 0
0x18000bff3  imul    ebx, [rdi+118h], 0EA60h
0x18000bffd  mov     ecx, ebx; unsigned int
0x18000bfff  call    ?GetNextRetryTime@@YA_KK@Z; GetNextRetryTime(ulong)
0x18000c004  mov     [rsp+0A8h+Flags], 0; Flags
0x18000c00c  lea     r8, ?CleanupInativeEventresourceCallback@BoundSubscription@@CAXPEAXE@Z; Callback
0x18000c013  mov     [rsp+0A8h+Period], 0; Period
0x18000c01b  mov     r9, rdi; Parameter
0x18000c01e  xor     edx, edx; TimerQueue
0x18000c020  mov     [rsp+0A8h+DueTime], ebx; DueTime
0x18000c024  mov     rcx, rsi; phNewTimer
0x18000c027  mov     [rdi+110h], rax
0x18000c02e  call    cs:__imp_CreateTimerQueueTimer
0x18000c034  test    eax, eax
0x18000c036  jnz     loc_18000C0D3
0x18000c03c  call    cs:__imp_GetLastError
0x18000c042  mov     ebx, eax
0x18000c044  mov     eax, 507h
0x18000c049  test    ebx, ebx
0x18000c04b  cmovz   ebx, eax
0x18000c04e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c055  cmp     rcx, r14
0x18000c058  jz      short loc_18000C07E
0x18000c05a  test    byte ptr [rcx+1Ch], 10h
0x18000c05e  jz      short loc_18000C07E
0x18000c060  cmp     byte ptr [rcx+19h], 2
0x18000c064  jb      short loc_18000C07E
0x18000c066  mov     rcx, [rcx+10h]
0x18000c06a  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000c071  mov     edx, 2Fh ; '/'
0x18000c076  mov     r9d, ebx
0x18000c079  call    WPP_SF_D
0x18000c07e  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000c085  mov     [rsp+0A8h+var_60], 0
0x18000c08a  mov     [rsp+0A8h+var_58], rax
0x18000c08f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000c096  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000c09d  mov     [rsp+0A8h+var_50], 0
0x18000c0a6  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18000c0ab  mov     [rsp+0A8h+pExceptionObject], rax
0x18000c0b0  mov     [rsp+0A8h+var_48], 0
0x18000c0b9  mov     [rsp+0A8h+var_40], ebx
0x18000c0bd  mov     [rsp+0A8h+var_3C], 0FFFFFFFFh
0x18000c0c5  mov     [rsp+0A8h+var_38], 6F3h
0x18000c0cd  call    _CxxThrowException_0
0x18000c0d3  add     rsp, 88h
0x18000c0da  pop     r14
0x18000c0dc  pop     rdi
0x18000c0dd  pop     rsi
0x18000c0de  pop     rbx
0x18000c0df  retn
```
