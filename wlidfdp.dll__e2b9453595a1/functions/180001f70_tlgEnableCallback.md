# _tlgEnableCallback

- ea: `0x180001f70`
- end: `0x180001fe6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f70`
- `0x180012010`

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
0x180001f70  sub     rsp, 48h
0x180001f74  mov     r11, rcx
0x180001f77  mov     rcx, [rsp+48h+CallbackContext]
0x180001f7f  test    rcx, rcx
0x180001f82  jz      short loc_180001FE1
0x180001f84  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001f89  mov     eax, edx
0x180001f8b  test    edx, edx
0x180001f8d  jz      short loc_180001FB2
0x180001f8f  cmp     eax, 1
0x180001f92  jnz     short loc_180001FB8
0x180001f94  test    r8b, r8b
0x180001f97  jz      short loc_180001FA1
0x180001f99  movzx   eax, r8b
0x180001f9d  inc     eax
0x180001f9f  jmp     short loc_180001FA6
0x180001fa1  mov     eax, 100h
0x180001fa6  mov     [rcx], eax
0x180001fa8  mov     [rcx+10h], r9
0x180001fac  mov     [rcx+18h], r10
0x180001fb0  jmp     short loc_180001FB8
0x180001fb2  mov     dword ptr [rcx], 0
0x180001fb8  mov     rax, [rcx+28h]
0x180001fbc  test    rax, rax
0x180001fbf  jz      short loc_180001FE1
0x180001fc1  mov     rcx, [rcx+30h]
0x180001fc5  mov     [rsp+48h+var_18], rcx
0x180001fca  mov     rcx, [rsp+48h+FilterData]
0x180001fcf  mov     [rsp+48h+var_20], rcx
0x180001fd4  mov     rcx, r11
0x180001fd7  mov     [rsp+48h+var_28], r10
0x180001fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fe1  add     rsp, 48h
0x180001fe5  retn
```
