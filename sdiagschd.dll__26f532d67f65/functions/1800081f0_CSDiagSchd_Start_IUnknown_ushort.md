# CSDiagSchd::Start(IUnknown *,ushort *)

- ea: `0x1800081f0`
- end: `0x1800083ca`
- name: `?Start@CSDiagSchd@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `474`
- prototype: `__int64 __fastcall(CSDiagSchd *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800056b4`
- `0x180007810`
- `0x1800081f0`
- `0x18000b13c`
- `0x18000c860`
- `0x18000d010`

## import_xrefs

- `ntdll!WinSqmStartSession` at `0x1800082a2`
- `ntdll!WinSqmStartSession` at `0x1800082a2`
- `ntdll!WinSqmEndSession` at `0x18000837d`
- `ntdll!WinSqmEndSession` at `0x18000837d`
- `KERNEL32!CloseHandle` at `0x180008363`
- `KERNEL32!CloseHandle` at `0x180008363`
- `KERNEL32!GetLastError` at `0x1800082ea`
- `KERNEL32!GetLastError` at `0x1800082ea`
- `KERNEL32!CreateThread` at `0x1800082cb`
- `KERNEL32!CreateThread` at `0x1800082cb`

## pseudocode

```c
__int64 __fastcall CSDiagSchd::Start(CSDiagSchd *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  int ScheduledDiagnosticsExecutionLevel; // eax
  signed int v6; // ebx
  _QWORD *v7; // rsi
  int v8; // r8d
  int v9; // ebp
  HANDLE Thread; // rax
  signed int LastError; // eax
  __int64 v12; // r8
  char *v13; // rcx
  DWORD v15[4]; // [rsp+30h] [rbp-48h] BYREF

  if ( (Microsoft_Windows_Diagnosis_ScheduledEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &SCHEDULED_DIAGNOSTICS_PROVIDER_Context,
      &SCHEDULED_DIAGNOSTICS_EVENT_STARTED,
      a3,
      1,
      v15);
  ScheduledDiagnosticsExecutionLevel = GetScheduledDiagnosticsExecutionLevel((char *)this + 56, a2, a3);
  v6 = ScheduledDiagnosticsExecutionLevel;
  if ( ScheduledDiagnosticsExecutionLevel >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
           (char *)this + 32);
    v9 = v6;
    if ( v6 >= 0 )
    {
      *((_QWORD *)this + 3) = WinSqmStartSession(&unk_180011228, 13959168, 0);
      Thread = CreateThread(0, 0, CSDiagSchd::SchdpExecuteDiagnostics, this, 0, 0);
      *((_QWORD *)this + 2) = Thread;
      if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        return (unsigned int)v6;
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v8 = 177;
      if ( v6 >= 0 )
        v6 = -2147467259;
      v9 = v6;
    }
    else
    {
      v8 = 165;
    }
    v7 = (_QWORD *)((char *)this + 32);
  }
  else
  {
    v7 = (_QWORD *)((char *)this + 32);
    v8 = 162;
    v9 = ScheduledDiagnosticsExecutionLevel;
  }
  SdpDebugTrace(1u, L"CSDiagSchd::Start", v8, v9);
  if ( (Microsoft_Windows_Diagnosis_ScheduledEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &SCHEDULED_DIAGNOSTICS_PROVIDER_Context,
      &SCHEDULED_DIAGNOSTICS_EVENT_COMPLETED,
      v12,
      1,
      v15);
  v13 = (char *)*((_QWORD *)this + 2);
  if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v13);
    *((_QWORD *)this + 2) = 0;
  }
  if ( *((_QWORD *)this + 3) )
  {
    WinSqmEndSession();
    *((_QWORD *)this + 3) = 0;
  }
  if ( *v7 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
    *v7 = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800081f0  mov     [rsp+arg_10], rbx
0x1800081f5  push    rbp
0x1800081f6  push    rsi
0x1800081f7  push    rdi
0x1800081f8  push    r12
0x1800081fa  push    r14
0x1800081fc  sub     rsp, 50h
0x180008200  mov     rax, cs:__security_cookie
0x180008207  xor     rax, rsp
0x18000820a  mov     [rsp+78h+var_38], rax
0x18000820f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScheduledEnableBits, 2
0x180008216  mov     rsi, rdx
0x180008219  mov     rdi, rcx
0x18000821c  mov     r12d, 1
0x180008222  jz      short loc_180008244
0x180008224  lea     rax, [rsp+78h+var_48]
0x180008229  mov     r9d, r12d
0x18000822c  lea     rdx, SCHEDULED_DIAGNOSTICS_EVENT_STARTED
0x180008233  mov     qword ptr [rsp+78h+dwCreationFlags], rax; dwCreationFlags
0x180008238  lea     rcx, SCHEDULED_DIAGNOSTICS_PROVIDER_Context
0x18000823f  call    McGenEventWrite_EventWriteTransfer
0x180008244  lea     rcx, [rdi+38h]
0x180008248  call    GetScheduledDiagnosticsExecutionLevel
0x18000824d  mov     ebx, eax
0x18000824f  test    eax, eax
0x180008251  jns     short loc_180008264
0x180008253  lea     rsi, [rdi+20h]
0x180008257  mov     r8d, 0A2h
0x18000825d  mov     ebp, eax
0x18000825f  jmp     loc_18000831A
0x180008264  mov     rax, [rsi]
0x180008267  lea     r14, [rdi+20h]
0x18000826b  mov     r8, r14
0x18000826e  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180008275  mov     rcx, rsi
0x180008278  mov     rax, [rax]
0x18000827b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008280  mov     ebx, eax
0x180008282  mov     ebp, eax
0x180008284  test    eax, eax
0x180008286  jns     short loc_180008293
0x180008288  mov     r8d, 0A5h
0x18000828e  jmp     loc_180008317
0x180008293  xor     r8d, r8d
0x180008296  lea     rcx, unk_180011228
0x18000829d  mov     edx, 0D50000h
0x1800082a2  call    cs:__imp_WinSqmStartSession
0x1800082a9  nop     dword ptr [rax+rax+00h]
0x1800082ae  and     [rsp+78h+var_50], 0
0x1800082b4  lea     r8, ?SchdpExecuteDiagnostics@CSDiagSchd@@CAKPEAX@Z; lpStartAddress
0x1800082bb  and     [rsp+78h+dwCreationFlags], 0
0x1800082c0  mov     r9, rdi; lpParameter
0x1800082c3  xor     edx, edx; dwStackSize
0x1800082c5  mov     [rdi+18h], rax
0x1800082c9  xor     ecx, ecx; lpThreadAttributes
0x1800082cb  call    cs:__imp_CreateThread
0x1800082d2  nop     dword ptr [rax+rax+00h]
0x1800082d7  mov     [rdi+10h], rax
0x1800082db  inc     rax
0x1800082de  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800082e4  jnz     loc_1800083A6
0x1800082ea  call    cs:__imp_GetLastError
0x1800082f1  nop     dword ptr [rax+rax+00h]
0x1800082f6  mov     ebx, eax
0x1800082f8  test    eax, eax
0x1800082fa  jle     short loc_180008305
0x1800082fc  movzx   ebx, ax
0x1800082ff  or      ebx, 80070000h
0x180008305  test    ebx, ebx
0x180008307  mov     eax, 80004005h
0x18000830c  mov     r8d, 0B1h; int
0x180008312  cmovns  ebx, eax
0x180008315  mov     ebp, ebx
0x180008317  mov     rsi, r14
0x18000831a  mov     ecx, r12d; Level
0x18000831d  lea     rdx, aCsdiagschdStar; "CSDiagSchd::Start"
0x180008324  mov     r9d, ebp; int
0x180008327  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000832c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScheduledEnableBits, 2
0x180008333  jz      short loc_180008355
0x180008335  lea     rax, [rsp+78h+var_48]
0x18000833a  mov     r9d, r12d
0x18000833d  lea     rdx, SCHEDULED_DIAGNOSTICS_EVENT_COMPLETED
0x180008344  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x180008349  lea     rcx, SCHEDULED_DIAGNOSTICS_PROVIDER_Context
0x180008350  call    McGenEventWrite_EventWriteTransfer
0x180008355  mov     rcx, [rdi+10h]; hObject
0x180008359  lea     rax, [rcx-1]
0x18000835d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008361  ja      short loc_180008374
0x180008363  call    cs:__imp_CloseHandle
0x18000836a  nop     dword ptr [rax+rax+00h]
0x18000836f  and     qword ptr [rdi+10h], 0
0x180008374  mov     rcx, [rdi+18h]
0x180008378  test    rcx, rcx
0x18000837b  jz      short loc_18000838E
0x18000837d  call    cs:__imp_WinSqmEndSession
0x180008384  nop     dword ptr [rax+rax+00h]
0x180008389  and     qword ptr [rdi+18h], 0
0x18000838e  mov     rcx, [rsi]
0x180008391  test    rcx, rcx
0x180008394  jz      short loc_1800083A6
0x180008396  mov     rax, [rcx]
0x180008399  mov     rax, [rax+10h]
0x18000839d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083a2  and     qword ptr [rsi], 0
0x1800083a6  mov     eax, ebx
0x1800083a8  mov     rcx, [rsp+78h+var_38]
0x1800083ad  xor     rcx, rsp; StackCookie
0x1800083b0  call    __security_check_cookie
0x1800083b5  mov     rbx, [rsp+78h+arg_10]
0x1800083bd  add     rsp, 50h
0x1800083c1  pop     r14
0x1800083c3  pop     r12
0x1800083c5  pop     rdi
0x1800083c6  pop     rsi
0x1800083c7  pop     rbp
0x1800083c8  retn
```
