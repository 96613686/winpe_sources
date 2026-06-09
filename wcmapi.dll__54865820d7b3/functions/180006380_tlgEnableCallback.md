# _tlgEnableCallback

- ea: `0x180006380`
- end: `0x180006401`
- name: `_tlgEnableCallback`
- size: `129`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006380`
- `0x18001e010`

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
0x180006380  sub     rsp, 48h
0x180006384  mov     r11, rcx
0x180006387  mov     rcx, [rsp+48h+CallbackContext]
0x18000638f  test    rcx, rcx
0x180006392  jz      short loc_1800063FB
0x180006394  mov     r10, [rsp+48h+MatchAllKeyword]
0x180006399  mov     eax, edx
0x18000639b  test    edx, edx
0x18000639d  jz      short loc_1800063CC
0x18000639f  cmp     eax, 1
0x1800063a2  jnz     short loc_1800063D2
0x1800063a4  test    r8b, r8b
0x1800063a7  jz      short loc_1800063BB
0x1800063a9  movzx   eax, r8b
0x1800063ad  inc     eax
0x1800063af  mov     [rcx], eax
0x1800063b1  mov     [rcx+10h], r9
0x1800063b5  mov     [rcx+18h], r10
0x1800063b9  jmp     short loc_1800063D2
0x1800063bb  mov     eax, 100h
0x1800063c0  mov     [rcx], eax
0x1800063c2  mov     [rcx+10h], r9
0x1800063c6  mov     [rcx+18h], r10
0x1800063ca  jmp     short loc_1800063D2
0x1800063cc  mov     dword ptr [rcx], 0
0x1800063d2  mov     rax, [rcx+28h]
0x1800063d6  test    rax, rax
0x1800063d9  jz      short loc_1800063FB
0x1800063db  mov     rcx, [rcx+30h]
0x1800063df  mov     [rsp+48h+var_18], rcx
0x1800063e4  mov     rcx, [rsp+48h+FilterData]
0x1800063e9  mov     [rsp+48h+var_20], rcx
0x1800063ee  mov     rcx, r11
0x1800063f1  mov     [rsp+48h+var_28], r10
0x1800063f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063fb  add     rsp, 48h
0x1800063ff  retn
```
