# NThreadingLibrary::TWorkCrew::CancelWorkThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x14000af80`
- end: `0x14000b1fd`
- name: `?CancelWorkThread@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `637`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400511b0`
- `0x140051974`

## callees

- `0x14000af80`
- `0x1400516e8`
- `0x140051738`
- `0x140051788`
- `0x1400517e8`
- `0x14007a010`

## import_xrefs

- `ntdll!TpSetWait` at `0x14000b14a`
- `ntdll!TpSetWait` at `0x14000b14a`
- `ntdll!TpCallbackMayRunLong` at `0x14000b133`
- `ntdll!TpCallbackMayRunLong` at `0x14000b133`
- `ntdll!TpWaitForAlpcCompletion` at `0x14000b1a7`
- `ntdll!TpWaitForAlpcCompletion` at `0x14000b1a7`
- `ntdll!TpReleaseAlpcCompletion` at `0x14000b1b1`
- `ntdll!TpReleaseAlpcCompletion` at `0x14000b1b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000b049`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000b10e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000b049`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000b10e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000afb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000b0aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000afb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000b0aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000afc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b0b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000afc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b0b3`

## pseudocode

```c
void __fastcall NThreadingLibrary::TWorkCrew::CancelWorkThread(
        struct _TP_CALLBACK_INSTANCE *a1,
        struct _RTL_CRITICAL_SECTION *a2,
        struct _TP_WAIT *a3)
{
  _QWORD *p_Type; // rdx
  _QWORD *v6; // r14
  signed __int32 i; // edx
  _QWORD *v8; // rdx

  if ( a2 && LODWORD(a2->SpinCount) == 2003985271 )
  {
    EnterCriticalSection(a2 + 1);
    ++HIDWORD(a2[2].DebugInfo);
    LODWORD(a2[2].DebugInfo) = GetCurrentThreadId();
    if ( !LODWORD(a2[4].SpinCount) )
    {
      LODWORD(a2[4].SpinCount) = 1;
      p_Type = &a2[4].DebugInfo->Type;
      *(_QWORD *)(p_Type[2] + 24LL) = p_Type[3];
      *(_QWORD *)(p_Type[3] + 16LL) = p_Type[2];
      p_Type[2] = p_Type;
      p_Type[3] = p_Type;
      if ( p_Type != &a2[3].LockSemaphore )
      {
        v6 = p_Type - 4;
        if ( !p_Type )
          v6 = 0;
        while ( v6 )
        {
          if ( !--HIDWORD(a2[2].DebugInfo) )
            LODWORD(a2[2].DebugInfo) = 0;
          LeaveCriticalSection(a2 + 1);
          switch ( *((_DWORD *)v6 + 22) )
          {
            case 1:
              NThreadingLibrary::TWorkCrew::CancelQueuedItem(
                (NThreadingLibrary::TWorkCrew *)(unsigned int)(*((_DWORD *)v6 + 22) - 1),
                (struct NThreadingLibrary::TQueuedItem *)v6);
              break;
            case 2:
              NThreadingLibrary::TWorkCrew::CancelWaitItem(
                (NThreadingLibrary::TWorkCrew *)(unsigned int)(*((_DWORD *)v6 + 22) - 2),
                (struct NThreadingLibrary::TWaitItem *)v6);
              break;
            case 3:
              NThreadingLibrary::TWorkCrew::CancelTimerItem(
                (NThreadingLibrary::TWorkCrew *)(unsigned int)(*((_DWORD *)v6 + 22) - 3),
                (struct NThreadingLibrary::TTimerItem *)v6);
              break;
            case 4:
              NThreadingLibrary::TWorkCrew::CancelIOItem(
                (NThreadingLibrary::TWorkCrew *)(unsigned int)(*((_DWORD *)v6 + 22) - 4),
                (struct NThreadingLibrary::TIOItem *)v6);
              break;
            default:
              if ( *((_DWORD *)v6 + 22) == 5 && v6[12] )
              {
                TpWaitForAlpcCompletion();
                TpReleaseAlpcCompletion(v6[12]);
                v6[12] = 0;
              }
              break;
          }
          for ( i = *((_DWORD *)v6 + 2); i != 0x7FFFFFFF; i = *((_DWORD *)v6 + 2) )
          {
            if ( i == _InterlockedCompareExchange((volatile signed __int32 *)v6 + 2, i - 1, i) )
              break;
          }
          if ( i == 1 )
            (*(void (__fastcall **)(_QWORD *))(*v6 + 8LL))(v6);
          EnterCriticalSection(a2 + 1);
          ++HIDWORD(a2[2].DebugInfo);
          LODWORD(a2[2].DebugInfo) = GetCurrentThreadId();
          v8 = &a2[4].DebugInfo->Type;
          *(_QWORD *)(v8[2] + 24LL) = v8[3];
          *(_QWORD *)(v8[3] + 16LL) = v8[2];
          v8[2] = v8;
          v8[3] = v8;
          if ( v8 == &a2[3].LockSemaphore )
            break;
          v6 = v8 - 4;
          if ( !v8 )
            v6 = 0;
        }
      }
      LODWORD(a2[4].SpinCount) = 0;
    }
    if ( HIDWORD(a2[2].DebugInfo)-- == 1 )
      LODWORD(a2[2].DebugInfo) = 0;
    LeaveCriticalSection(a2 + 1);
  }
  if ( a1 )
  {
    if ( !LODWORD(a2[4].OwningThread) )
    {
      TpCallbackMayRunLong(a1, a2, a3);
      TpSetWait(a2[5].OwningThread, a2[4].LockSemaphore, 0);
    }
  }
}

```

## disassembly

```asm
0x14000af80  push    rsi
0x14000af82  push    rdi
0x14000af83  sub     rsp, 28h
0x14000af87  mov     rdi, rdx
0x14000af8a  mov     rsi, rcx
0x14000af8d  test    rdx, rdx
0x14000af90  jz      short loc_14000AF9B
0x14000af92  cmp     dword ptr [rdx+20h], 77726377h
0x14000af99  jz      short loc_14000AFAB
0x14000af9b  test    rsi, rsi
0x14000af9e  jnz     loc_14000B123
0x14000afa4  add     rsp, 28h
0x14000afa8  pop     rdi
0x14000afa9  pop     rsi
0x14000afaa  retn
0x14000afab  mov     [rsp+38h+arg_0], rbx
0x14000afb0  lea     rcx, [rdx+28h]; lpCriticalSection
0x14000afb4  mov     [rsp+38h+var_18], r15
0x14000afb9  call    cs:__imp_EnterCriticalSection
0x14000afbf  inc     dword ptr [rdi+54h]
0x14000afc2  call    cs:__imp_GetCurrentThreadId
0x14000afc8  xor     r15d, r15d
0x14000afcb  mov     [rdi+50h], eax
0x14000afce  cmp     [rdi+0C0h], r15d
0x14000afd5  jnz     loc_14000B0FD
0x14000afdb  mov     dword ptr [rdi+0C0h], 1
0x14000afe5  mov     [rsp+38h+arg_8], rbp
0x14000afea  lea     rbp, [rdi+90h]
0x14000aff1  mov     rdx, [rbp+10h]
0x14000aff5  mov     rcx, [rdx+10h]
0x14000aff9  mov     rax, [rdx+18h]
0x14000affd  mov     [rcx+18h], rax
0x14000b001  mov     rcx, [rdx+18h]
0x14000b005  mov     rax, [rdx+10h]
0x14000b009  mov     [rcx+10h], rax
0x14000b00d  mov     [rdx+10h], rdx
0x14000b011  mov     [rdx+18h], rdx
0x14000b015  cmp     rdx, rbp
0x14000b018  jz      loc_14000B0F1
0x14000b01e  mov     [rsp+38h+arg_10], r14
0x14000b023  test    rdx, rdx
0x14000b026  lea     r14, [rdx-20h]
0x14000b02a  cmovz   r14, r15
0x14000b02e  test    r14, r14
0x14000b031  jz      loc_14000B0EC
0x14000b037  dec     dword ptr [rdi+54h]
0x14000b03a  mov     eax, [rdi+54h]
0x14000b03d  test    eax, eax
0x14000b03f  jz      loc_14000B191
0x14000b045  lea     rcx, [rdi+28h]; lpCriticalSection
0x14000b049  call    cs:__imp_LeaveCriticalSection
0x14000b04f  mov     ecx, [r14+58h]
0x14000b053  sub     ecx, 1; this
0x14000b056  jz      loc_14000B1E7
0x14000b05c  sub     ecx, 1; this
0x14000b05f  jz      loc_14000B1DA
0x14000b065  sub     ecx, 1; this
0x14000b068  jz      loc_14000B1CD
0x14000b06e  sub     ecx, 1; this
0x14000b071  jz      loc_14000B1C0
0x14000b077  cmp     ecx, 1
0x14000b07a  jz      loc_14000B19A
0x14000b080  mov     edx, [r14+8]
0x14000b084  cmp     edx, 7FFFFFFFh
0x14000b08a  jnz     loc_14000B155
0x14000b090  lea     eax, [rdx-1]
0x14000b093  test    eax, eax
0x14000b095  jnz     short loc_14000B0A6
0x14000b097  mov     rax, [r14]
0x14000b09a  mov     rcx, r14
0x14000b09d  mov     rax, [rax+8]
0x14000b0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b0a6  lea     rcx, [rdi+28h]; lpCriticalSection
0x14000b0aa  call    cs:__imp_EnterCriticalSection
0x14000b0b0  inc     dword ptr [rdi+54h]
0x14000b0b3  call    cs:__imp_GetCurrentThreadId
0x14000b0b9  mov     [rdi+50h], eax
0x14000b0bc  mov     rdx, [rdi+0A0h]
0x14000b0c3  mov     rcx, [rdx+10h]
0x14000b0c7  mov     rax, [rdx+18h]
0x14000b0cb  mov     [rcx+18h], rax
0x14000b0cf  mov     rcx, [rdx+18h]
0x14000b0d3  mov     rax, [rdx+10h]
0x14000b0d7  mov     [rcx+10h], rax
0x14000b0db  mov     [rdx+10h], rdx
0x14000b0df  mov     [rdx+18h], rdx
0x14000b0e3  cmp     rdx, rbp
0x14000b0e6  jnz     loc_14000B178
0x14000b0ec  mov     r14, [rsp+38h+arg_10]
0x14000b0f1  mov     rbp, [rsp+38h+arg_8]
0x14000b0f6  mov     [rdi+0C0h], r15d
0x14000b0fd  add     dword ptr [rdi+54h], 0FFFFFFFFh
0x14000b101  mov     eax, [rdi+54h]
0x14000b104  jz      loc_14000B1F4
0x14000b10a  lea     rcx, [rdi+28h]; lpCriticalSection
0x14000b10e  call    cs:__imp_LeaveCriticalSection
0x14000b114  mov     r15, [rsp+38h+var_18]
0x14000b119  mov     rbx, [rsp+38h+arg_0]
0x14000b11e  jmp     loc_14000AF9B
0x14000b123  cmp     dword ptr [rdi+0B0h], 0
0x14000b12a  jnz     loc_14000AFA4
0x14000b130  mov     rcx, rsi
0x14000b133  call    cs:__imp_TpCallbackMayRunLong
0x14000b139  mov     rdx, [rdi+0B8h]
0x14000b140  xor     r8d, r8d
0x14000b143  mov     rcx, [rdi+0D8h]
0x14000b14a  call    cs:__imp_TpSetWait
0x14000b150  jmp     loc_14000AFA4
0x14000b155  lea     ecx, [rdx-1]
0x14000b158  mov     eax, edx
0x14000b15a  lock cmpxchg [r14+8], ecx
0x14000b160  jz      loc_14000B090
0x14000b166  mov     edx, [r14+8]
0x14000b16a  cmp     edx, 7FFFFFFFh
0x14000b170  jz      loc_14000B090
0x14000b176  jmp     short loc_14000B155
0x14000b178  test    rdx, rdx
0x14000b17b  lea     r14, [rdx-20h]
0x14000b17f  cmovz   r14, r15
0x14000b183  test    r14, r14
0x14000b186  jz      loc_14000B0EC
0x14000b18c  jmp     loc_14000B037
0x14000b191  mov     [rdi+50h], r15d
0x14000b195  jmp     loc_14000B045
0x14000b19a  mov     rcx, [r14+60h]
0x14000b19e  test    rcx, rcx
0x14000b1a1  jz      loc_14000B080
0x14000b1a7  call    cs:__imp_TpWaitForAlpcCompletion
0x14000b1ad  mov     rcx, [r14+60h]
0x14000b1b1  call    cs:__imp_TpReleaseAlpcCompletion
0x14000b1b7  mov     [r14+60h], r15
0x14000b1bb  jmp     loc_14000B080
0x14000b1c0  mov     rdx, r14; struct NThreadingLibrary::TIOItem *
0x14000b1c3  call    ?CancelIOItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTIOItem@2@@Z; NThreadingLibrary::TWorkCrew::CancelIOItem(NThreadingLibrary::TIOItem *)
0x14000b1c8  jmp     loc_14000B080
0x14000b1cd  mov     rdx, r14; struct NThreadingLibrary::TTimerItem *
0x14000b1d0  call    ?CancelTimerItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTTimerItem@2@@Z; NThreadingLibrary::TWorkCrew::CancelTimerItem(NThreadingLibrary::TTimerItem *)
0x14000b1d5  jmp     loc_14000B080
0x14000b1da  mov     rdx, r14; struct NThreadingLibrary::TWaitItem *
0x14000b1dd  call    ?CancelWaitItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWaitItem@2@@Z; NThreadingLibrary::TWorkCrew::CancelWaitItem(NThreadingLibrary::TWaitItem *)
0x14000b1e2  jmp     loc_14000B080
0x14000b1e7  mov     rdx, r14; struct NThreadingLibrary::TQueuedItem *
0x14000b1ea  call    ?CancelQueuedItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTQueuedItem@2@@Z; NThreadingLibrary::TWorkCrew::CancelQueuedItem(NThreadingLibrary::TQueuedItem *)
0x14000b1ef  jmp     loc_14000B080
0x14000b1f4  mov     [rdi+50h], r15d
0x14000b1f8  jmp     loc_14000B10A
```
