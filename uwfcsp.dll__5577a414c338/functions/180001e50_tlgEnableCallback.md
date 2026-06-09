# _tlgEnableCallback

- ea: `0x180001e50`
- end: `0x180001ec6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001e50`
- `0x18001b010`

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
0x180001e50  sub     rsp, 48h
0x180001e54  mov     r11, rcx
0x180001e57  mov     rcx, [rsp+48h+CallbackContext]
0x180001e5f  test    rcx, rcx
0x180001e62  jz      short loc_180001EC1
0x180001e64  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001e69  mov     eax, edx
0x180001e6b  test    edx, edx
0x180001e6d  jz      short loc_180001E92
0x180001e6f  cmp     eax, 1
0x180001e72  jnz     short loc_180001E98
0x180001e74  test    r8b, r8b
0x180001e77  jz      short loc_180001E81
0x180001e79  movzx   eax, r8b
0x180001e7d  inc     eax
0x180001e7f  jmp     short loc_180001E86
0x180001e81  mov     eax, 100h
0x180001e86  mov     [rcx], eax
0x180001e88  mov     [rcx+10h], r9
0x180001e8c  mov     [rcx+18h], r10
0x180001e90  jmp     short loc_180001E98
0x180001e92  mov     dword ptr [rcx], 0
0x180001e98  mov     rax, [rcx+28h]
0x180001e9c  test    rax, rax
0x180001e9f  jz      short loc_180001EC1
0x180001ea1  mov     rcx, [rcx+30h]
0x180001ea5  mov     [rsp+48h+var_18], rcx
0x180001eaa  mov     rcx, [rsp+48h+FilterData]
0x180001eaf  mov     [rsp+48h+var_20], rcx
0x180001eb4  mov     rcx, r11
0x180001eb7  mov     [rsp+48h+var_28], r10
0x180001ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ec1  add     rsp, 48h
0x180001ec5  retn
```
