# NThreadingLibrary::TWorkCrew::Initialize(void)

- ea: `0x140014d44`
- end: `0x140014e0e`
- name: `?Initialize@TWorkCrew@NThreadingLibrary@@AEAAJXZ`
- size: `202`
- prototype: `__int64 __fastcall(NThreadingLibrary::TWorkCrew *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140014c34`

## callees

- `0x140007bdc`
- `0x140014d44`

## import_xrefs

- `ntdll!TpSetWait` at `0x140014df6`
- `ntdll!TpSetWait` at `0x140014df6`
- `ntdll!TpAllocWait` at `0x140014dc8`
- `ntdll!TpAllocWait` at `0x140014dc8`
- `ntdll!RtlNtStatusToDosError` at `0x140014dd0`
- `ntdll!RtlNtStatusToDosError` at `0x140014dd0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140014d6d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140014d94`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140014d6d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140014d94`

## pseudocode

```c
__int64 __fastcall NThreadingLibrary::TWorkCrew::Initialize(NThreadingLibrary::TWorkCrew *this)
{
  signed int LastErrorAsHResult; // ebx
  HANDLE EventW; // rax
  __int64 v4; // rcx
  HANDLE v5; // rax
  __int64 v6; // rcx
  NTSTATUS v7; // eax
  signed int v8; // eax

  LastErrorAsHResult = *((_DWORD *)this + 22);
  if ( LastErrorAsHResult >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 26) = EventW;
    if ( EventW || (LastErrorAsHResult = GetLastErrorAsHResult(v4), LastErrorAsHResult >= 0) )
    {
      v5 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 23) = v5;
      if ( v5 || (LastErrorAsHResult = GetLastErrorAsHResult(v6), LastErrorAsHResult >= 0) )
      {
        v7 = TpAllocWait((char *)this + 216, NThreadingLibrary::TWorkCrew::CancelWorkThread, this, 0);
        v8 = RtlNtStatusToDosError(v7);
        LastErrorAsHResult = v8;
        if ( v8 > 0 )
          LastErrorAsHResult = (unsigned __int16)v8 | 0x80070000;
        if ( LastErrorAsHResult >= 0 )
          TpSetWait(*((_QWORD *)this + 27), *((_QWORD *)this + 23), 0);
      }
    }
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x140014d44  mov     [rsp+arg_0], rbx
0x140014d49  mov     [rsp+arg_8], rsi
0x140014d4e  push    rdi
0x140014d4f  sub     rsp, 20h
0x140014d53  mov     ebx, [rcx+58h]
0x140014d56  mov     rdi, rcx
0x140014d59  test    ebx, ebx
0x140014d5b  js      loc_140014DFC
0x140014d61  xor     r9d, r9d; lpName
0x140014d64  xor     r8d, r8d; bInitialState
0x140014d67  xor     ecx, ecx; lpEventAttributes
0x140014d69  lea     edx, [r9+1]; bManualReset
0x140014d6d  call    cs:__imp_CreateEventW
0x140014d73  mov     [rdi+0D0h], rax
0x140014d7a  test    rax, rax
0x140014d7d  jnz     short loc_140014D8A
0x140014d7f  call    GetLastErrorAsHResult
0x140014d84  mov     ebx, eax
0x140014d86  test    eax, eax
0x140014d88  js      short loc_140014DFC
0x140014d8a  xor     r9d, r9d; lpName
0x140014d8d  xor     r8d, r8d; bInitialState
0x140014d90  xor     edx, edx; bManualReset
0x140014d92  xor     ecx, ecx; lpEventAttributes
0x140014d94  call    cs:__imp_CreateEventW
0x140014d9a  mov     [rdi+0B8h], rax
0x140014da1  test    rax, rax
0x140014da4  jnz     short loc_140014DB1
0x140014da6  call    GetLastErrorAsHResult
0x140014dab  mov     ebx, eax
0x140014dad  test    eax, eax
0x140014daf  js      short loc_140014DFC
0x140014db1  lea     rsi, [rdi+0D8h]
0x140014db8  xor     r9d, r9d
0x140014dbb  mov     rcx, rsi
0x140014dbe  lea     rdx, ?CancelWorkThread@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; NThreadingLibrary::TWorkCrew::CancelWorkThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x140014dc5  mov     r8, rdi
0x140014dc8  call    cs:__imp_TpAllocWait
0x140014dce  mov     ecx, eax; Status
0x140014dd0  call    cs:__imp_RtlNtStatusToDosError
0x140014dd6  mov     ebx, eax
0x140014dd8  test    eax, eax
0x140014dda  jle     short loc_140014DE5
0x140014ddc  movzx   ebx, ax
0x140014ddf  or      ebx, 80070000h
0x140014de5  test    ebx, ebx
0x140014de7  js      short loc_140014DFC
0x140014de9  mov     rdx, [rdi+0B8h]
0x140014df0  xor     r8d, r8d
0x140014df3  mov     rcx, [rsi]
0x140014df6  call    cs:__imp_TpSetWait
0x140014dfc  mov     rsi, [rsp+28h+arg_8]
0x140014e01  mov     eax, ebx
0x140014e03  mov     rbx, [rsp+28h+arg_0]
0x140014e08  add     rsp, 20h
0x140014e0c  pop     rdi
0x140014e0d  retn
```
