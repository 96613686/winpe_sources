# _tlgEnableCallback

- ea: `0x180001770`
- end: `0x1800017e6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001770`
- `0x18000d010`

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
0x180001770  sub     rsp, 48h
0x180001774  mov     r11, rcx
0x180001777  mov     rcx, [rsp+48h+CallbackContext]
0x18000177f  test    rcx, rcx
0x180001782  jz      short loc_1800017E1
0x180001784  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001789  mov     eax, edx
0x18000178b  test    edx, edx
0x18000178d  jz      short loc_1800017B2
0x18000178f  cmp     eax, 1
0x180001792  jnz     short loc_1800017B8
0x180001794  test    r8b, r8b
0x180001797  jz      short loc_1800017A1
0x180001799  movzx   eax, r8b
0x18000179d  inc     eax
0x18000179f  jmp     short loc_1800017A6
0x1800017a1  mov     eax, 100h
0x1800017a6  mov     [rcx], eax
0x1800017a8  mov     [rcx+10h], r9
0x1800017ac  mov     [rcx+18h], r10
0x1800017b0  jmp     short loc_1800017B8
0x1800017b2  mov     dword ptr [rcx], 0
0x1800017b8  mov     rax, [rcx+28h]
0x1800017bc  test    rax, rax
0x1800017bf  jz      short loc_1800017E1
0x1800017c1  mov     rcx, [rcx+30h]
0x1800017c5  mov     [rsp+48h+var_18], rcx
0x1800017ca  mov     rcx, [rsp+48h+FilterData]
0x1800017cf  mov     [rsp+48h+var_20], rcx
0x1800017d4  mov     rcx, r11
0x1800017d7  mov     [rsp+48h+var_28], r10
0x1800017dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017e1  add     rsp, 48h
0x1800017e5  retn
```
