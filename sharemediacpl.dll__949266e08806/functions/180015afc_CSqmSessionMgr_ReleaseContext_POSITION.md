# CSqmSessionMgr::ReleaseContext(__POSITION *)

- ea: `0x180015afc`
- end: `0x180015cd6`
- name: `?ReleaseContext@CSqmSessionMgr@@QEAAXPEAU__POSITION@@@Z`
- size: `474`
- prototype: `void __fastcall(CSqmSessionMgr *__hidden this, struct __POSITION *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007e5c`

## callees

- `0x180003860`
- `0x180003888`
- `0x180015afc`
- `0x180016108`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180015c72`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180015c72`
- `KERNEL32!LeaveCriticalSection` at `0x180015cbd`
- `KERNEL32!LeaveCriticalSection` at `0x180015cbd`
- `KERNEL32!EnterCriticalSection` at `0x180015b24`
- `KERNEL32!EnterCriticalSection` at `0x180015b24`
- `KERNEL32!CreateTimerQueue` at `0x180015bb7`
- `KERNEL32!CreateTimerQueue` at `0x180015bb7`
- `KERNEL32!CreateTimerQueueTimer` at `0x180015c66`
- `KERNEL32!CreateTimerQueueTimer` at `0x180015c66`
- `KERNEL32!GetLastError` at `0x180015bc6`
- `KERNEL32!GetLastError` at `0x180015c7e`
- `KERNEL32!GetLastError` at `0x180015bc6`
- `KERNEL32!GetLastError` at `0x180015c7e`

## pseudocode

```c
void __fastcall CSqmSessionMgr::ReleaseContext(CSqmSessionMgr *this, struct __POSITION *a2)
{
  LPCRITICAL_SECTION v2; // rsi
  __int64 v4; // r8
  __int64 v5; // rbx
  _QWORD *v6; // rcx
  bool v7; // zf
  HANDLE TimerQueue; // rax
  signed int LastError; // eax
  unsigned int v10; // edi
  _QWORD *v11; // rcx
  signed int v12; // eax

  if ( a2 )
  {
    v2 = _pSqmSessionMgr;
    EnterCriticalSection(_pSqmSessionMgr);
    v5 = *((_QWORD *)a2 + 1);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids,
        *(unsigned int *)a2);
      v6 = WPP_GLOBAL_Control;
    }
    if ( !*(_DWORD *)(v5 + 8) || !*(_QWORD *)(v5 + 24) )
      goto LABEL_32;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      WPP_SF_(v6[2], 32, &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids);
    v7 = (*(_DWORD *)(v5 + 8))-- == 1;
    if ( !v7 || *(_QWORD *)(v5 + 16) )
      goto LABEL_32;
    if ( *(_QWORD *)&v2[1].LockCount
      || (TimerQueue = CreateTimerQueue(), (*(_QWORD *)&v2[1].LockCount = TimerQueue) != 0) )
    {
      v11 = WPP_GLOBAL_Control;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids, v10);
        v11 = WPP_GLOBAL_Control;
      }
      if ( v10 )
        goto LABEL_32;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
      WPP_SF_q(v11[2], 34, v4, *(_QWORD *)(v5 + 24));
    if ( CreateTimerQueueTimer(
           (PHANDLE)(v5 + 16),
           *(HANDLE *)&v2[1].LockCount,
           CSqmSessionMgr::TimerCallback,
           (PVOID)v5,
           HIDWORD(v2[4].OwningThread),
           0,
           0x100u) )
    {
      *(_QWORD *)(v5 + 32) = _time64(0);
    }
    else
    {
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids,
          (unsigned int)v12);
    }
LABEL_32:
    LeaveCriticalSection(v2);
  }
}

```

## disassembly

```asm
0x180015afc  test    rdx, rdx
0x180015aff  jz      locret_180015CD5
0x180015b05  mov     [rsp+arg_8], rbx
0x180015b0a  mov     [rsp+arg_10], rbp
0x180015b0f  push    rsi
0x180015b10  push    rdi
0x180015b11  push    r12
0x180015b13  sub     rsp, 40h
0x180015b17  mov     rsi, cs:?_pSqmSessionMgr@@3PEAVCSqmSessionMgr@@EA; CSqmSessionMgr * _pSqmSessionMgr
0x180015b1e  mov     rdi, rdx
0x180015b21  mov     rcx, rsi; lpCriticalSection
0x180015b24  call    cs:__imp_EnterCriticalSection
0x180015b2a  mov     rbx, [rdi+8]
0x180015b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b35  lea     r12, WPP_GLOBAL_Control
0x180015b3c  cmp     rcx, r12
0x180015b3f  jz      short loc_180015B66
0x180015b41  test    byte ptr [rcx+1Ch], 8
0x180015b45  jz      short loc_180015B66
0x180015b47  mov     r9d, [rdi]
0x180015b4a  lea     r8, WPP_ea0197bca44a35f25f9875116037e43b_Traceguids
0x180015b51  mov     rcx, [rcx+10h]
0x180015b55  mov     edx, 1Fh
0x180015b5a  call    WPP_SF_d
0x180015b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b66  cmp     dword ptr [rbx+8], 0
0x180015b6a  jz      loc_180015CBA
0x180015b70  cmp     qword ptr [rbx+18h], 0
0x180015b75  jz      loc_180015CBA
0x180015b7b  cmp     rcx, r12
0x180015b7e  jz      short loc_180015B9B
0x180015b80  test    byte ptr [rcx+1Ch], 8
0x180015b84  jz      short loc_180015B9B
0x180015b86  mov     rcx, [rcx+10h]
0x180015b8a  lea     r8, WPP_ea0197bca44a35f25f9875116037e43b_Traceguids
0x180015b91  mov     edx, 20h ; ' '
0x180015b96  call    WPP_SF_
0x180015b9b  add     dword ptr [rbx+8], 0FFFFFFFFh
0x180015b9f  jnz     loc_180015CBA
0x180015ba5  cmp     qword ptr [rbx+10h], 0
0x180015baa  jnz     loc_180015CBA
0x180015bb0  cmp     qword ptr [rsi+30h], 0
0x180015bb5  jnz     short loc_180015C16
0x180015bb7  call    cs:__imp_CreateTimerQueue
0x180015bbd  mov     [rsi+30h], rax
0x180015bc1  test    rax, rax
0x180015bc4  jnz     short loc_180015C16
0x180015bc6  call    cs:__imp_GetLastError
0x180015bcc  mov     edi, eax
0x180015bce  test    eax, eax
0x180015bd0  jle     short loc_180015BDB
0x180015bd2  movzx   edi, ax
0x180015bd5  or      edi, 80070000h
0x180015bdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180015be2  cmp     rcx, r12
0x180015be5  jz      short loc_180015C0C
0x180015be7  test    byte ptr [rcx+1Ch], 8
0x180015beb  jz      short loc_180015C0C
0x180015bed  mov     rcx, [rcx+10h]
0x180015bf1  lea     r8, WPP_ea0197bca44a35f25f9875116037e43b_Traceguids
0x180015bf8  mov     edx, 21h ; '!'
0x180015bfd  mov     r9d, edi
0x180015c00  call    WPP_SF_d
0x180015c05  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c0c  test    edi, edi
0x180015c0e  jnz     loc_180015CBA
0x180015c14  jmp     short loc_180015C1D
0x180015c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c1d  cmp     rcx, r12
0x180015c20  jz      short loc_180015C3A
0x180015c22  test    byte ptr [rcx+1Ch], 8
0x180015c26  jz      short loc_180015C3A
0x180015c28  mov     r9, [rbx+18h]
0x180015c2c  mov     edx, 22h ; '"'
0x180015c31  mov     rcx, [rcx+10h]
0x180015c35  call    WPP_SF_q
0x180015c3a  mov     eax, [rsi+0B4h]
0x180015c40  lea     r8, ?TimerCallback@CSqmSessionMgr@@CAXPEAXE@Z; Callback
0x180015c47  mov     rdx, [rsi+30h]; TimerQueue
0x180015c4b  lea     rcx, [rbx+10h]; phNewTimer
0x180015c4f  mov     [rsp+58h+Flags], 100h; Flags
0x180015c57  mov     r9, rbx; Parameter
0x180015c5a  mov     [rsp+58h+Period], 0; Period
0x180015c62  mov     [rsp+58h+DueTime], eax; DueTime
0x180015c66  call    cs:__imp_CreateTimerQueueTimer
0x180015c6c  test    eax, eax
0x180015c6e  jz      short loc_180015C7E
0x180015c70  xor     ecx, ecx; Time
0x180015c72  call    cs:__imp__time64
0x180015c78  mov     [rbx+20h], rax
0x180015c7c  jmp     short loc_180015CBA
0x180015c7e  call    cs:__imp_GetLastError
0x180015c84  test    eax, eax
0x180015c86  jle     short loc_180015C90
0x180015c88  movzx   eax, ax
0x180015c8b  or      eax, 80070000h
0x180015c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c97  cmp     rcx, r12
0x180015c9a  jz      short loc_180015CBA
0x180015c9c  test    byte ptr [rcx+1Ch], 8
0x180015ca0  jz      short loc_180015CBA
0x180015ca2  mov     rcx, [rcx+10h]
0x180015ca6  lea     r8, WPP_ea0197bca44a35f25f9875116037e43b_Traceguids
0x180015cad  mov     edx, 23h ; '#'
0x180015cb2  mov     r9d, eax
0x180015cb5  call    WPP_SF_d
0x180015cba  mov     rcx, rsi; lpCriticalSection
0x180015cbd  call    cs:__imp_LeaveCriticalSection
0x180015cc3  mov     rbx, [rsp+58h+arg_8]
0x180015cc8  mov     rbp, [rsp+58h+arg_10]
0x180015ccd  add     rsp, 40h
0x180015cd1  pop     r12
0x180015cd3  pop     rdi
0x180015cd4  pop     rsi
0x180015cd5  retn
```
