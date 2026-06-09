# _tlgEnableCallback

- ea: `0x180001010`
- end: `0x180001093`
- name: `_tlgEnableCallback`
- size: `131`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001010`
- `0x1800148e0`

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
  int v8; // ecx
  void (__fastcall *v9)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rax

  if ( CallbackContext )
  {
    if ( (_DWORD)IsEnabled )
    {
      if ( (_DWORD)IsEnabled == 1 )
      {
        v8 = 256;
        CallbackContext[2] = MatchAnyKeyword;
        CallbackContext[3] = MatchAllKeyword;
        if ( (_BYTE)Level )
          v8 = (unsigned __int8)Level + 1;
        *(_DWORD *)CallbackContext = v8;
      }
    }
    else
    {
      *(_DWORD *)CallbackContext = 0;
    }
    v9 = (void (__fastcall *)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD))CallbackContext[5];
    if ( v9 )
      v9(SourceId, IsEnabled, Level, MatchAnyKeyword, MatchAllKeyword, FilterData, CallbackContext[6]);
  }
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_0], rbx
0x180001015  push    rdi
0x180001016  sub     rsp, 40h
0x18000101a  mov     r10, [rsp+48h+CallbackContext]
0x180001022  mov     rdi, rcx
0x180001025  test    r10, r10
0x180001028  jz      short loc_180001088
0x18000102a  mov     r11, [rsp+48h+MatchAllKeyword]
0x18000102f  mov     eax, edx
0x180001031  test    edx, edx
0x180001033  jz      short loc_180001058
0x180001035  cmp     eax, 1
0x180001038  jnz     short loc_18000105F
0x18000103a  movzx   eax, r8b
0x18000103e  mov     ecx, 100h
0x180001043  inc     eax
0x180001045  mov     [r10+10h], r9
0x180001049  test    r8b, r8b
0x18000104c  mov     [r10+18h], r11
0x180001050  cmovnz  ecx, eax
0x180001053  mov     [r10], ecx
0x180001056  jmp     short loc_18000105F
0x180001058  mov     dword ptr [r10], 0
0x18000105f  mov     rax, [r10+28h]
0x180001063  test    rax, rax
0x180001066  jz      short loc_180001088
0x180001068  mov     rcx, [r10+30h]
0x18000106c  mov     [rsp+48h+var_18], rcx
0x180001071  mov     rcx, [rsp+48h+FilterData]
0x180001076  mov     [rsp+48h+var_20], rcx
0x18000107b  mov     rcx, rdi
0x18000107e  mov     [rsp+48h+var_28], r11
0x180001083  call    _guard_dispatch_icall
0x180001088  mov     rbx, [rsp+48h+arg_0]
0x18000108d  add     rsp, 40h
0x180001091  pop     rdi
0x180001092  retn
```
