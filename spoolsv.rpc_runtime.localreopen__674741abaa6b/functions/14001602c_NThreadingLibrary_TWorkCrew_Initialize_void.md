# NThreadingLibrary::TWorkCrew::Initialize(void)

- ea: `0x14001602c`
- end: `0x140016119`
- name: `?Initialize@TWorkCrew@NThreadingLibrary@@AEAAJXZ`
- size: `237`
- prototype: `__int64 __fastcall(NThreadingLibrary::TWorkCrew *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140015f18`

## callees

- `0x1400087c8`
- `0x14001602c`

## import_xrefs

- `ntdll!TpSetWait` at `0x1400160fa`
- `ntdll!TpSetWait` at `0x1400160fa`
- `ntdll!TpAllocWait` at `0x1400160c0`
- `ntdll!TpAllocWait` at `0x1400160c0`
- `ntdll!RtlNtStatusToDosError` at `0x1400160ce`
- `ntdll!RtlNtStatusToDosError` at `0x1400160ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140016055`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140016086`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140016055`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140016086`

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
0x14001602c  mov     [rsp+arg_0], rbx
0x140016031  mov     [rsp+arg_8], rsi
0x140016036  push    rdi
0x140016037  sub     rsp, 20h
0x14001603b  mov     ebx, [rcx+58h]
0x14001603e  mov     rdi, rcx
0x140016041  test    ebx, ebx
0x140016043  js      loc_140016106
0x140016049  xor     r9d, r9d; lpName
0x14001604c  xor     r8d, r8d; bInitialState
0x14001604f  xor     ecx, ecx; lpEventAttributes
0x140016051  lea     edx, [r9+1]; bManualReset
0x140016055  call    cs:__imp_CreateEventW
0x14001605c  nop     dword ptr [rax+rax+00h]
0x140016061  mov     [rdi+0D0h], rax
0x140016068  test    rax, rax
0x14001606b  jnz     short loc_14001607C
0x14001606d  call    GetLastErrorAsHResult
0x140016072  mov     ebx, eax
0x140016074  test    eax, eax
0x140016076  js      loc_140016106
0x14001607c  xor     r9d, r9d; lpName
0x14001607f  xor     r8d, r8d; bInitialState
0x140016082  xor     edx, edx; bManualReset
0x140016084  xor     ecx, ecx; lpEventAttributes
0x140016086  call    cs:__imp_CreateEventW
0x14001608d  nop     dword ptr [rax+rax+00h]
0x140016092  mov     [rdi+0B8h], rax
0x140016099  test    rax, rax
0x14001609c  jnz     short loc_1400160A9
0x14001609e  call    GetLastErrorAsHResult
0x1400160a3  mov     ebx, eax
0x1400160a5  test    eax, eax
0x1400160a7  js      short loc_140016106
0x1400160a9  lea     rsi, [rdi+0D8h]
0x1400160b0  xor     r9d, r9d
0x1400160b3  mov     rcx, rsi
0x1400160b6  lea     rdx, ?CancelWorkThread@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; NThreadingLibrary::TWorkCrew::CancelWorkThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x1400160bd  mov     r8, rdi
0x1400160c0  call    cs:__imp_TpAllocWait
0x1400160c7  nop     dword ptr [rax+rax+00h]
0x1400160cc  mov     ecx, eax; Status
0x1400160ce  call    cs:__imp_RtlNtStatusToDosError
0x1400160d5  nop     dword ptr [rax+rax+00h]
0x1400160da  mov     ebx, eax
0x1400160dc  test    eax, eax
0x1400160de  jle     short loc_1400160E9
0x1400160e0  movzx   ebx, ax
0x1400160e3  or      ebx, 80070000h
0x1400160e9  test    ebx, ebx
0x1400160eb  js      short loc_140016106
0x1400160ed  mov     rdx, [rdi+0B8h]
0x1400160f4  xor     r8d, r8d
0x1400160f7  mov     rcx, [rsi]
0x1400160fa  call    cs:__imp_TpSetWait
0x140016101  nop     dword ptr [rax+rax+00h]
0x140016106  mov     rsi, [rsp+28h+arg_8]
0x14001610b  mov     eax, ebx
0x14001610d  mov     rbx, [rsp+28h+arg_0]
0x140016112  add     rsp, 20h
0x140016116  pop     rdi
0x140016117  retn
```
