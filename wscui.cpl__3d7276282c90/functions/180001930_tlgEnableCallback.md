# _tlgEnableCallback

- ea: `0x180001930`
- end: `0x1800019b0`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001930`
- `0x18000c010`

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
0x180001930  sub     rsp, 48h
0x180001934  mov     r11, rcx
0x180001937  mov     rcx, [rsp+48h+CallbackContext]
0x18000193f  test    rcx, rcx
0x180001942  jz      short loc_1800019AB
0x180001944  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001949  mov     eax, edx
0x18000194b  test    edx, edx
0x18000194d  jz      short loc_18000197C
0x18000194f  cmp     eax, 1
0x180001952  jnz     short loc_180001982
0x180001954  test    r8b, r8b
0x180001957  jz      short loc_18000196B
0x180001959  movzx   eax, r8b
0x18000195d  inc     eax
0x18000195f  mov     [rcx], eax
0x180001961  mov     [rcx+10h], r9
0x180001965  mov     [rcx+18h], r10
0x180001969  jmp     short loc_180001982
0x18000196b  mov     eax, 100h
0x180001970  mov     [rcx], eax
0x180001972  mov     [rcx+10h], r9
0x180001976  mov     [rcx+18h], r10
0x18000197a  jmp     short loc_180001982
0x18000197c  mov     dword ptr [rcx], 0
0x180001982  mov     rax, [rcx+28h]
0x180001986  test    rax, rax
0x180001989  jz      short loc_1800019AB
0x18000198b  mov     rcx, [rcx+30h]
0x18000198f  mov     [rsp+48h+var_18], rcx
0x180001994  mov     rcx, [rsp+48h+FilterData]
0x180001999  mov     [rsp+48h+var_20], rcx
0x18000199e  mov     rcx, r11
0x1800019a1  mov     [rsp+48h+var_28], r10
0x1800019a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019ab  add     rsp, 48h
0x1800019af  retn
```
