# EventSession::ProcessEventsThread(void *)

- ea: `0x1800ace80`
- end: `0x1800acfe5`
- name: `?ProcessEventsThread@EventSession@@CAKPEAX@Z`
- size: `357`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18002b3e8`
- `0x180077ad0`
- `0x18009aee0`
- `0x1800ace80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800acf05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800acf42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800acf05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800acf42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aced3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800acf98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aced3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800acf98`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x1800acf5a`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x1800acf5a`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1800acf11`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1800acf11`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x1800acf6d`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x1800acf6d`

## pseudocode

```c
__int64 __fastcall EventSession::ProcessEventsThread(ULONG64 *Parameter)
{
  __int64 v2; // rbx
  DWORD CurrentThreadId; // eax
  const WCHAR *v4; // rbx
  HANDLE CurrentThread; // rax
  HANDLE v6; // rax
  ULONG v7; // esi
  __int64 v8; // rbx
  DWORD v9; // eax
  ULONG64 HandleArray; // [rsp+30h] [rbp-58h] BYREF
  ULONG64 *v12; // [rsp+38h] [rbp-50h] BYREF
  _DWORD v13[4]; // [rsp+40h] [rbp-48h] BYREF

  HandleArray = *Parameter;
  v12 = Parameter;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v2 = *(_QWORD *)(Parameter[1] + 16);
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)&WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids,
      CurrentThreadId,
      v2);
  }
  v4 = *(const WCHAR **)(Parameter[1] + 16);
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, v4);
  if ( !*(_BYTE *)(Parameter[1] + 100) || !BYTE5(g_service[60].Ptr) )
  {
    v13[0] = 1;
    v13[1] = 1;
    v13[2] = 1;
    v6 = GetCurrentThread();
    SetThreadInformation(v6, 3, v13);
  }
  v7 = ProcessTrace(&HandleArray, 1u, 0, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v8 = *(_QWORD *)(Parameter[1] + 16);
    v9 = GetCurrentThreadId();
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)&WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids,
      v9,
      v8);
  }
  utl::unique_ptr<ProcessEventsThreadArgs,utl::default_delete<ProcessEventsThreadArgs>>::~unique_ptr<ProcessEventsThreadArgs,utl::default_delete<ProcessEventsThreadArgs>>(&v12);
  return v7;
}

```

## disassembly

```asm
0x1800ace80  push    rbx
0x1800ace82  push    rsi
0x1800ace83  push    rdi
0x1800ace84  push    r14
0x1800ace86  sub     rsp, 68h
0x1800ace8a  mov     rax, cs:__security_cookie
0x1800ace91  xor     rax, rsp
0x1800ace94  mov     [rsp+88h+var_38], rax
0x1800ace99  mov     rax, [rcx]
0x1800ace9c  mov     rdi, rcx
0x1800ace9f  mov     [rsp+88h+HandleArray], rax
0x1800acea4  mov     [rsp+88h+var_50], rcx
0x1800acea9  mov     rax, cs:WPP_GLOBAL_Control
0x1800aceb0  lea     r14, WPP_GLOBAL_Control
0x1800aceb7  cmp     rax, r14
0x1800aceba  jz      short loc_1800ACEFD
0x1800acebc  test    dword ptr [rax+1Ch], 4000000h
0x1800acec3  jz      short loc_1800ACEFD
0x1800acec5  cmp     byte ptr [rax+19h], 4
0x1800acec9  jb      short loc_1800ACEFD
0x1800acecb  mov     rax, [rcx+8]
0x1800acecf  mov     rbx, [rax+10h]
0x1800aced3  call    cs:__imp_GetCurrentThreadId
0x1800aced9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acee0  lea     r8, WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids
0x1800acee7  mov     edx, 0Eh
0x1800aceec  mov     [rsp+88h+var_68], rbx
0x1800acef1  mov     r9d, eax
0x1800acef4  mov     rcx, [rcx+10h]
0x1800acef8  call    WPP_SF_dS
0x1800acefd  mov     rax, [rdi+8]
0x1800acf01  mov     rbx, [rax+10h]
0x1800acf05  call    cs:__imp_GetCurrentThread
0x1800acf0b  mov     rcx, rax; hThread
0x1800acf0e  mov     rdx, rbx; lpThreadDescription
0x1800acf11  call    cs:__imp_SetThreadDescription
0x1800acf17  mov     rax, [rdi+8]
0x1800acf1b  mov     ebx, 1
0x1800acf20  cmp     byte ptr [rax+64h], 0
0x1800acf24  jz      short loc_1800ACF36
0x1800acf26  mov     rax, cs:?g_service@@3PEAVEventService@@EA; EventService * g_service
0x1800acf2d  cmp     byte ptr [rax+1E5h], 0
0x1800acf34  jnz     short loc_1800ACF60
0x1800acf36  mov     [rsp+88h+var_48], ebx
0x1800acf3a  mov     [rsp+88h+var_44], ebx
0x1800acf3e  mov     [rsp+88h+var_40], ebx
0x1800acf42  call    cs:__imp_GetCurrentThread
0x1800acf48  mov     r9d, 0Ch
0x1800acf4e  lea     r8, [rsp+88h+var_48]
0x1800acf53  mov     rcx, rax
0x1800acf56  lea     edx, [r9-9]
0x1800acf5a  call    cs:__imp_SetThreadInformation
0x1800acf60  xor     r9d, r9d; EndTime
0x1800acf63  lea     rcx, [rsp+88h+HandleArray]; HandleArray
0x1800acf68  xor     r8d, r8d; StartTime
0x1800acf6b  mov     edx, ebx; HandleCount
0x1800acf6d  call    cs:__imp_ProcessTrace
0x1800acf73  mov     esi, eax
0x1800acf75  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acf7c  cmp     rcx, r14
0x1800acf7f  jz      short loc_1800ACFC2
0x1800acf81  test    dword ptr [rcx+1Ch], 4000000h
0x1800acf88  jz      short loc_1800ACFC2
0x1800acf8a  cmp     byte ptr [rcx+19h], 4
0x1800acf8e  jb      short loc_1800ACFC2
0x1800acf90  mov     rcx, [rdi+8]
0x1800acf94  mov     rbx, [rcx+10h]
0x1800acf98  call    cs:__imp_GetCurrentThreadId
0x1800acf9e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acfa5  lea     r8, WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids
0x1800acfac  mov     edx, 0Fh
0x1800acfb1  mov     [rsp+88h+var_68], rbx
0x1800acfb6  mov     r9d, eax
0x1800acfb9  mov     rcx, [rcx+10h]
0x1800acfbd  call    WPP_SF_dS
0x1800acfc2  lea     rcx, [rsp+88h+var_50]
0x1800acfc7  call    ??1?$unique_ptr@UProcessEventsThreadArgs@@U?$default_delete@UProcessEventsThreadArgs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ProcessEventsThreadArgs,utl::default_delete<ProcessEventsThreadArgs>>::~unique_ptr<ProcessEventsThreadArgs,utl::default_delete<ProcessEventsThreadArgs>>(void)
0x1800acfcc  mov     eax, esi
0x1800acfce  mov     rcx, [rsp+88h+var_38]
0x1800acfd3  xor     rcx, rsp; StackCookie
0x1800acfd6  call    __security_check_cookie
0x1800acfdb  add     rsp, 68h
0x1800acfdf  pop     r14
0x1800acfe1  pop     rdi
0x1800acfe2  pop     rsi
0x1800acfe3  pop     rbx
0x1800acfe4  retn
```
