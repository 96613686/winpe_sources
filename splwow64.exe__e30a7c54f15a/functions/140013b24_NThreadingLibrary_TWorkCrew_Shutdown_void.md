# NThreadingLibrary::TWorkCrew::Shutdown(void * *)

- ea: `0x140013b24`
- end: `0x140013c35`
- name: `?Shutdown@TWorkCrew@NThreadingLibrary@@QEAAJPEAPEAX@Z`
- size: `273`
- prototype: `__int64 __fastcall(NThreadingLibrary::TWorkCrew *__hidden this, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400108dc`
- `0x1400131c4`

## callees

- `0x140012bd4`
- `0x140013640`
- `0x140013870`
- `0x140013adc`
- `0x140013b24`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140013bc4`
- `KERNEL32!WaitForSingleObject` at `0x140013bc4`
- `KERNEL32!GetCurrentThreadId` at `0x140013b4b`
- `KERNEL32!GetCurrentThreadId` at `0x140013b4b`
- `KERNEL32!SetEvent` at `0x140013b99`
- `KERNEL32!SetEvent` at `0x140013b99`
- `KERNEL32!EnterCriticalSection` at `0x140013b42`
- `KERNEL32!EnterCriticalSection` at `0x140013b42`
- `KERNEL32!LeaveCriticalSection` at `0x140013bb5`
- `KERNEL32!LeaveCriticalSection` at `0x140013bb5`
- `ntdll!TpSetWait` at `0x140013bea`
- `ntdll!TpSetWait` at `0x140013bea`
- `ntdll!TpWaitForWait` at `0x140013bfc`
- `ntdll!TpWaitForWait` at `0x140013bfc`
- `ntdll!TpReleaseWait` at `0x140013c09`
- `ntdll!TpReleaseWait` at `0x140013c09`

## pseudocode

```c
__int64 __fastcall NThreadingLibrary::TWorkCrew::Shutdown(NThreadingLibrary::TWorkCrew *this, void **a2)
{
  int LastErrorAsHResult; // ebx
  NThreadingLibrary::TWorkCrew *v4; // rcx
  struct NThreadingLibrary::TWorkItem *v5; // rax
  struct NThreadingLibrary::TWorkItem *v6; // rsi
  NCoreLibrary *v8; // rcx
  __int64 v9; // rcx

  LastErrorAsHResult = *((_DWORD *)this + 49);
  if ( LastErrorAsHResult >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
    ++*((_DWORD *)this + 21);
    *((_DWORD *)this + 20) = GetCurrentThreadId();
    *((_DWORD *)this + 44) = 1;
    while ( 1 )
    {
      v5 = (struct NThreadingLibrary::TWorkItem *)NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::RemoveAtHead((char *)this + 96);
      v6 = v5;
      if ( !v5 )
        break;
      v4 = (NThreadingLibrary::TWorkCrew *)*((_QWORD *)v5 + 10);
      if ( v4 )
        NThreadingLibrary::TWorkCrew::DeleteItem(v4, v5);
      *((_DWORD *)v6 + 17) = 1;
    }
    if ( !*((_DWORD *)this + 50) )
      SetEvent(*((HANDLE *)this + 26));
    if ( (*((_DWORD *)this + 21))-- == 1 )
      *((_DWORD *)this + 20) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
    if ( WaitForSingleObject(*((HANDLE *)this + 26), 0xFFFFFFFF) == -1 )
      LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v8);
    else
      LastErrorAsHResult = 0;
    v9 = *((_QWORD *)this + 27);
    if ( v9 )
    {
      TpSetWait(v9, 0, 0);
      TpWaitForWait(*((_QWORD *)this + 27), 1);
      TpReleaseWait(*((_QWORD *)this + 27));
      *((_QWORD *)this + 27) = 0;
    }
    NThreadingLibrary::TWorkCrew::CancelWorkThread(0, (struct _RTL_CRITICAL_SECTION *)this, 0);
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x140013b24  push    rbx
0x140013b26  push    rbp
0x140013b27  push    rsi
0x140013b28  push    rdi
0x140013b29  sub     rsp, 28h
0x140013b2d  mov     ebx, [rcx+0C4h]
0x140013b33  mov     rdi, rcx
0x140013b36  test    ebx, ebx
0x140013b38  js      loc_140013C2A
0x140013b3e  add     rcx, 28h ; '('; lpCriticalSection
0x140013b42  call    cs:__imp_EnterCriticalSection
0x140013b48  inc     dword ptr [rdi+54h]
0x140013b4b  call    cs:__imp_GetCurrentThreadId
0x140013b51  mov     [rdi+50h], eax
0x140013b54  mov     dword ptr [rdi+0B0h], 1
0x140013b5e  jmp     short loc_140013B78
0x140013b60  mov     rcx, [rsi+50h]; this
0x140013b64  test    rcx, rcx
0x140013b67  jz      short loc_140013B71
0x140013b69  mov     rdx, rsi; struct NThreadingLibrary::TWorkItem *
0x140013b6c  call    ?DeleteItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::DeleteItem(NThreadingLibrary::TWorkItem *)
0x140013b71  mov     dword ptr [rsi+44h], 1
0x140013b78  lea     rcx, [rdi+60h]
0x140013b7c  call    ?RemoveAtHead@?$TList@VTWorkItem@NThreadingLibrary@@@NCoreLibrary@@QEAAPEAVTWorkItem@NThreadingLibrary@@XZ; NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::RemoveAtHead(void)
0x140013b81  mov     rsi, rax
0x140013b84  test    rax, rax
0x140013b87  jnz     short loc_140013B60
0x140013b89  cmp     dword ptr [rdi+0C8h], 0
0x140013b90  jnz     short loc_140013B9F
0x140013b92  mov     rcx, [rdi+0D0h]; hEvent
0x140013b99  call    cs:__imp_SetEvent
0x140013b9f  or      esi, 0FFFFFFFFh
0x140013ba2  add     [rdi+54h], esi
0x140013ba5  mov     eax, [rdi+54h]
0x140013ba8  jnz     short loc_140013BB1
0x140013baa  mov     dword ptr [rdi+50h], 0
0x140013bb1  lea     rcx, [rdi+28h]; lpCriticalSection
0x140013bb5  call    cs:__imp_LeaveCriticalSection
0x140013bbb  mov     rcx, [rdi+0D0h]; hHandle
0x140013bc2  mov     edx, esi; dwMilliseconds
0x140013bc4  call    cs:__imp_WaitForSingleObject
0x140013bca  cmp     eax, esi
0x140013bcc  jz      short loc_140013BD2
0x140013bce  xor     ebx, ebx
0x140013bd0  jmp     short loc_140013BD9
0x140013bd2  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140013bd7  mov     ebx, eax
0x140013bd9  mov     rcx, [rdi+0D8h]
0x140013be0  test    rcx, rcx
0x140013be3  jz      short loc_140013C1A
0x140013be5  xor     r8d, r8d
0x140013be8  xor     edx, edx
0x140013bea  call    cs:__imp_TpSetWait
0x140013bf0  mov     rcx, [rdi+0D8h]
0x140013bf7  mov     edx, 1
0x140013bfc  call    cs:__imp_TpWaitForWait
0x140013c02  mov     rcx, [rdi+0D8h]
0x140013c09  call    cs:__imp_TpReleaseWait
0x140013c0f  mov     qword ptr [rdi+0D8h], 0
0x140013c1a  xor     r9d, r9d; int
0x140013c1d  xor     r8d, r8d; struct _TP_WAIT *
0x140013c20  mov     rdx, rdi; void *
0x140013c23  xor     ecx, ecx; struct _TP_CALLBACK_INSTANCE *
0x140013c25  call    ?CancelWorkThread@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; NThreadingLibrary::TWorkCrew::CancelWorkThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x140013c2a  mov     eax, ebx
0x140013c2c  add     rsp, 28h
0x140013c30  pop     rdi
0x140013c31  pop     rsi
0x140013c32  pop     rbp
0x140013c33  pop     rbx
0x140013c34  retn
```
