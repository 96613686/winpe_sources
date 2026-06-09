# _tlgEnableCallback

- ea: `0x1800010f0`
- end: `0x180001166`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800010f0`
- `0x180018010`

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
0x1800010f0  sub     rsp, 48h
0x1800010f4  mov     r11, rcx
0x1800010f7  mov     rcx, [rsp+48h+CallbackContext]
0x1800010ff  test    rcx, rcx
0x180001102  jz      short loc_180001161
0x180001104  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001109  mov     eax, edx
0x18000110b  test    edx, edx
0x18000110d  jz      short loc_180001132
0x18000110f  cmp     eax, 1
0x180001112  jnz     short loc_180001138
0x180001114  test    r8b, r8b
0x180001117  jz      short loc_180001121
0x180001119  movzx   eax, r8b
0x18000111d  inc     eax
0x18000111f  jmp     short loc_180001126
0x180001121  mov     eax, 100h
0x180001126  mov     [rcx], eax
0x180001128  mov     [rcx+10h], r9
0x18000112c  mov     [rcx+18h], r10
0x180001130  jmp     short loc_180001138
0x180001132  mov     dword ptr [rcx], 0
0x180001138  mov     rax, [rcx+28h]
0x18000113c  test    rax, rax
0x18000113f  jz      short loc_180001161
0x180001141  mov     rcx, [rcx+30h]
0x180001145  mov     [rsp+48h+var_18], rcx
0x18000114a  mov     rcx, [rsp+48h+FilterData]
0x18000114f  mov     [rsp+48h+var_20], rcx
0x180001154  mov     rcx, r11
0x180001157  mov     [rsp+48h+var_28], r10
0x18000115c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001161  add     rsp, 48h
0x180001165  retn
```
