# _tlgEnableCallback

- ea: `0x18000d650`
- end: `0x18000d6c6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d650`
- `0x180019010`

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
0x18000d650  sub     rsp, 48h
0x18000d654  mov     r11, rcx
0x18000d657  mov     rcx, [rsp+48h+CallbackContext]
0x18000d65f  test    rcx, rcx
0x18000d662  jz      short loc_18000D6C1
0x18000d664  mov     r10, [rsp+48h+MatchAllKeyword]
0x18000d669  mov     eax, edx
0x18000d66b  test    edx, edx
0x18000d66d  jz      short loc_18000D692
0x18000d66f  cmp     eax, 1
0x18000d672  jnz     short loc_18000D698
0x18000d674  test    r8b, r8b
0x18000d677  jz      short loc_18000D681
0x18000d679  movzx   eax, r8b
0x18000d67d  inc     eax
0x18000d67f  jmp     short loc_18000D686
0x18000d681  mov     eax, 100h
0x18000d686  mov     [rcx], eax
0x18000d688  mov     [rcx+10h], r9
0x18000d68c  mov     [rcx+18h], r10
0x18000d690  jmp     short loc_18000D698
0x18000d692  mov     dword ptr [rcx], 0
0x18000d698  mov     rax, [rcx+28h]
0x18000d69c  test    rax, rax
0x18000d69f  jz      short loc_18000D6C1
0x18000d6a1  mov     rcx, [rcx+30h]
0x18000d6a5  mov     [rsp+48h+var_18], rcx
0x18000d6aa  mov     rcx, [rsp+48h+FilterData]
0x18000d6af  mov     [rsp+48h+var_20], rcx
0x18000d6b4  mov     rcx, r11
0x18000d6b7  mov     [rsp+48h+var_28], r10
0x18000d6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6c1  add     rsp, 48h
0x18000d6c5  retn
```
