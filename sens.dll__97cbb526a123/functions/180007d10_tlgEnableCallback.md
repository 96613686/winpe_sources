# _tlgEnableCallback

- ea: `0x180007d10`
- end: `0x180007d90`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007d10`
- `0x18000b010`

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
0x180007d10  sub     rsp, 48h
0x180007d14  mov     r11, rcx
0x180007d17  mov     rcx, [rsp+48h+CallbackContext]
0x180007d1f  test    rcx, rcx
0x180007d22  jz      short loc_180007D8B
0x180007d24  mov     r10, [rsp+48h+MatchAllKeyword]
0x180007d29  mov     eax, edx
0x180007d2b  test    edx, edx
0x180007d2d  jz      short loc_180007D5C
0x180007d2f  cmp     eax, 1
0x180007d32  jnz     short loc_180007D62
0x180007d34  test    r8b, r8b
0x180007d37  jz      short loc_180007D4B
0x180007d39  movzx   eax, r8b
0x180007d3d  inc     eax
0x180007d3f  mov     [rcx], eax
0x180007d41  mov     [rcx+10h], r9
0x180007d45  mov     [rcx+18h], r10
0x180007d49  jmp     short loc_180007D62
0x180007d4b  mov     eax, 100h
0x180007d50  mov     [rcx], eax
0x180007d52  mov     [rcx+10h], r9
0x180007d56  mov     [rcx+18h], r10
0x180007d5a  jmp     short loc_180007D62
0x180007d5c  mov     dword ptr [rcx], 0
0x180007d62  mov     rax, [rcx+28h]
0x180007d66  test    rax, rax
0x180007d69  jz      short loc_180007D8B
0x180007d6b  mov     rcx, [rcx+30h]
0x180007d6f  mov     [rsp+48h+var_18], rcx
0x180007d74  mov     rcx, [rsp+48h+FilterData]
0x180007d79  mov     [rsp+48h+var_20], rcx
0x180007d7e  mov     rcx, r11
0x180007d81  mov     [rsp+48h+var_28], r10
0x180007d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d8b  add     rsp, 48h
0x180007d8f  retn
```
