# _tlgEnableCallback

- ea: `0x180001b50`
- end: `0x180001bc6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001b50`
- `0x18002b010`

## pseudocode

```c
void __fastcall tlgEnableCallback(
        LPCGUID SourceId,
        __int64 IsEnabled,
        __int64 Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        _QWORD *CallbackContext)
{
  int v7; // eax
  void (__fastcall *v8)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rax

  if ( CallbackContext )
  {
    if ( (_DWORD)IsEnabled )
    {
      if ( (_DWORD)IsEnabled == 1 )
      {
        if ( (_BYTE)Level )
          v7 = (unsigned __int8)Level + 1;
        else
          v7 = 256;
        *(_DWORD *)CallbackContext = v7;
        CallbackContext[2] = MatchAnyKeyword;
        CallbackContext[3] = MatchAllKeyword;
      }
    }
    else
    {
      *(_DWORD *)CallbackContext = 0;
    }
    v8 = (void (__fastcall *)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD))CallbackContext[5];
    if ( v8 )
      v8(SourceId, IsEnabled, Level, MatchAnyKeyword, MatchAllKeyword, FilterData, CallbackContext[6]);
  }
}

```

## disassembly

```asm
0x180001b50  sub     rsp, 48h
0x180001b54  mov     r11, rcx
0x180001b57  mov     rcx, [rsp+48h+CallbackContext]
0x180001b5f  test    rcx, rcx
0x180001b62  jz      short loc_180001BC1
0x180001b64  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001b69  mov     eax, edx
0x180001b6b  test    edx, edx
0x180001b6d  jz      short loc_180001B92
0x180001b6f  cmp     eax, 1
0x180001b72  jnz     short loc_180001B98
0x180001b74  test    r8b, r8b
0x180001b77  jz      short loc_180001B81
0x180001b79  movzx   eax, r8b
0x180001b7d  inc     eax
0x180001b7f  jmp     short loc_180001B86
0x180001b81  mov     eax, 100h
0x180001b86  mov     [rcx], eax
0x180001b88  mov     [rcx+10h], r9
0x180001b8c  mov     [rcx+18h], r10
0x180001b90  jmp     short loc_180001B98
0x180001b92  mov     dword ptr [rcx], 0
0x180001b98  mov     rax, [rcx+28h]
0x180001b9c  test    rax, rax
0x180001b9f  jz      short loc_180001BC1
0x180001ba1  mov     rcx, [rcx+30h]
0x180001ba5  mov     [rsp+48h+var_18], rcx
0x180001baa  mov     rcx, [rsp+48h+FilterData]
0x180001baf  mov     [rsp+48h+var_20], rcx
0x180001bb4  mov     rcx, r11
0x180001bb7  mov     [rsp+48h+var_28], r10
0x180001bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bc1  add     rsp, 48h
0x180001bc5  retn
```
