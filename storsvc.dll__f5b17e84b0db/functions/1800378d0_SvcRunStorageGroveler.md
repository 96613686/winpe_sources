# SvcRunStorageGroveler

- ea: `0x1800378d0`
- end: `0x180037942`
- name: `SvcRunStorageGroveler`
- size: `114`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180012734`
- `0x18001a70c`
- `0x1800378d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800378e8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800378e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003792d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003792d`
- `storageusage!GetStorageUsageInfo` at `0x180037924`
- `storageusage!GetStorageUsageInfo` at `0x180037924`

## string_xrefs

- `0x180037906`: `onecore\drivers\storage\storsvc\service\storageusageclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SvcRunStorageGroveler(__int64 a1, unsigned int a2)
{
  HANDLE EventW; // rax
  void *v4; // rbx
  int LastHr; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  EventW = CreateEventW(0, 1, 0, 0);
  v4 = EventW;
  if ( EventW )
  {
    GetStorageUsageInfo(EventW, a2, 0);
    CloseHandle(v4);
    return 0;
  }
  else
  {
    LastHr = GetLastHr();
    v6 = LastHr;
    if ( LastHr < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x493,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageusageclient.cpp",
        (const char *)(unsigned int)LastHr,
        v8);
  }
  return v6;
}

```

## disassembly

```asm
0x1800378d0  mov     [rsp+arg_0], rbx
0x1800378d5  push    rdi; int
0x1800378d6  sub     rsp, 20h
0x1800378da  xor     r9d, r9d; lpName
0x1800378dd  mov     edi, edx
0x1800378df  xor     r8d, r8d; bInitialState
0x1800378e2  xor     ecx, ecx; lpEventAttributes
0x1800378e4  lea     edx, [r9+1]; bManualReset
0x1800378e8  call    cs:__imp_CreateEventW
0x1800378ee  mov     rbx, rax
0x1800378f1  test    rax, rax
0x1800378f4  jnz     short loc_18003791C
0x1800378f6  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x1800378fb  mov     ebx, eax
0x1800378fd  test    eax, eax
0x1800378ff  jns     short loc_180037935
0x180037901  mov     rcx, [rsp+28h]; this
0x180037906  lea     r8, aOnecoreDrivers_11; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003790d  mov     r9d, eax; char *
0x180037910  mov     edx, 493h; void *
0x180037915  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003791a  jmp     short loc_180037935
0x18003791c  xor     r8d, r8d
0x18003791f  mov     edx, edi
0x180037921  mov     rcx, rbx
0x180037924  call    cs:__imp_?GetStorageUsageInfo@@YAXPEAXW4_GROVELER_SCAN_LEVEL@@W4GROVELER_TRIGGER_TYPE@@@Z; GetStorageUsageInfo(void *,_GROVELER_SCAN_LEVEL,GROVELER_TRIGGER_TYPE)
0x18003792a  mov     rcx, rbx; hObject
0x18003792d  call    cs:__imp_CloseHandle
0x180037933  xor     ebx, ebx
0x180037935  mov     eax, ebx
0x180037937  mov     rbx, [rsp+28h+arg_0]
0x18003793c  add     rsp, 20h
0x180037940  pop     rdi
0x180037941  retn
```
