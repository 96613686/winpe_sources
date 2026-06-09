# _tlgEnableCallback

- ea: `0x180001950`
- end: `0x1800019c6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001950`
- `0x18000f010`

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
0x180001950  sub     rsp, 48h
0x180001954  mov     r11, rcx
0x180001957  mov     rcx, [rsp+48h+CallbackContext]
0x18000195f  test    rcx, rcx
0x180001962  jz      short loc_1800019C1
0x180001964  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001969  mov     eax, edx
0x18000196b  test    edx, edx
0x18000196d  jz      short loc_180001992
0x18000196f  cmp     eax, 1
0x180001972  jnz     short loc_180001998
0x180001974  test    r8b, r8b
0x180001977  jz      short loc_180001981
0x180001979  movzx   eax, r8b
0x18000197d  inc     eax
0x18000197f  jmp     short loc_180001986
0x180001981  mov     eax, 100h
0x180001986  mov     [rcx], eax
0x180001988  mov     [rcx+10h], r9
0x18000198c  mov     [rcx+18h], r10
0x180001990  jmp     short loc_180001998
0x180001992  mov     dword ptr [rcx], 0
0x180001998  mov     rax, [rcx+28h]
0x18000199c  test    rax, rax
0x18000199f  jz      short loc_1800019C1
0x1800019a1  mov     rcx, [rcx+30h]
0x1800019a5  mov     [rsp+48h+var_18], rcx
0x1800019aa  mov     rcx, [rsp+48h+FilterData]
0x1800019af  mov     [rsp+48h+var_20], rcx
0x1800019b4  mov     rcx, r11
0x1800019b7  mov     [rsp+48h+var_28], r10
0x1800019bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019c1  add     rsp, 48h
0x1800019c5  retn
```
