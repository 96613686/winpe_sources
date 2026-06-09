# _tlgEnableCallback

- ea: `0x18000a450`
- end: `0x18000a4d0`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a450`
- `0x180017010`

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
  void (__fastcall *v7)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rax

  if ( CallbackContext )
  {
    if ( (_DWORD)IsEnabled )
    {
      if ( (_DWORD)IsEnabled == 1 )
      {
        if ( (_BYTE)Level )
          *(_DWORD *)CallbackContext = (unsigned __int8)Level + 1;
        else
          *(_DWORD *)CallbackContext = 256;
        CallbackContext[2] = MatchAnyKeyword;
        CallbackContext[3] = MatchAllKeyword;
      }
    }
    else
    {
      *(_DWORD *)CallbackContext = 0;
    }
    v7 = (void (__fastcall *)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD))CallbackContext[5];
    if ( v7 )
      v7(SourceId, IsEnabled, Level, MatchAnyKeyword, MatchAllKeyword, FilterData, CallbackContext[6]);
  }
}

```

## disassembly

```asm
0x18000a450  sub     rsp, 48h
0x18000a454  mov     r11, rcx
0x18000a457  mov     rcx, [rsp+48h+CallbackContext]
0x18000a45f  test    rcx, rcx
0x18000a462  jz      short loc_18000A4CB
0x18000a464  mov     r10, [rsp+48h+MatchAllKeyword]
0x18000a469  mov     eax, edx
0x18000a46b  test    edx, edx
0x18000a46d  jz      short loc_18000A49C
0x18000a46f  cmp     eax, 1
0x18000a472  jnz     short loc_18000A4A2
0x18000a474  test    r8b, r8b
0x18000a477  jz      short loc_18000A48B
0x18000a479  movzx   eax, r8b
0x18000a47d  inc     eax
0x18000a47f  mov     [rcx], eax
0x18000a481  mov     [rcx+10h], r9
0x18000a485  mov     [rcx+18h], r10
0x18000a489  jmp     short loc_18000A4A2
0x18000a48b  mov     eax, 100h
0x18000a490  mov     [rcx], eax
0x18000a492  mov     [rcx+10h], r9
0x18000a496  mov     [rcx+18h], r10
0x18000a49a  jmp     short loc_18000A4A2
0x18000a49c  mov     dword ptr [rcx], 0
0x18000a4a2  mov     rax, [rcx+28h]
0x18000a4a6  test    rax, rax
0x18000a4a9  jz      short loc_18000A4CB
0x18000a4ab  mov     rcx, [rcx+30h]
0x18000a4af  mov     [rsp+48h+var_18], rcx
0x18000a4b4  mov     rcx, [rsp+48h+FilterData]
0x18000a4b9  mov     [rsp+48h+var_20], rcx
0x18000a4be  mov     rcx, r11
0x18000a4c1  mov     [rsp+48h+var_28], r10
0x18000a4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4cb  add     rsp, 48h
0x18000a4cf  retn
```
