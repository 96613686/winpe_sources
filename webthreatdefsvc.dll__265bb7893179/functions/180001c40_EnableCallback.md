# EnableCallback

- ea: `0x180001c40`
- end: `0x180001cb6`
- name: `EnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001c40`
- `0x18001c010`

## pseudocode

```c
void __fastcall EnableCallback(
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
0x180001c40  sub     rsp, 48h
0x180001c44  mov     r11, rcx
0x180001c47  mov     rcx, [rsp+48h+CallbackContext]
0x180001c4f  test    rcx, rcx
0x180001c52  jz      short loc_180001CB1
0x180001c54  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001c59  mov     eax, edx
0x180001c5b  test    edx, edx
0x180001c5d  jz      short loc_180001C82
0x180001c5f  cmp     eax, 1
0x180001c62  jnz     short loc_180001C88
0x180001c64  test    r8b, r8b
0x180001c67  jz      short loc_180001C71
0x180001c69  movzx   eax, r8b
0x180001c6d  inc     eax
0x180001c6f  jmp     short loc_180001C76
0x180001c71  mov     eax, 100h
0x180001c76  mov     [rcx], eax
0x180001c78  mov     [rcx+10h], r9
0x180001c7c  mov     [rcx+18h], r10
0x180001c80  jmp     short loc_180001C88
0x180001c82  mov     dword ptr [rcx], 0
0x180001c88  mov     rax, [rcx+28h]
0x180001c8c  test    rax, rax
0x180001c8f  jz      short loc_180001CB1
0x180001c91  mov     rcx, [rcx+30h]
0x180001c95  mov     [rsp+48h+var_18], rcx
0x180001c9a  mov     rcx, [rsp+48h+FilterData]
0x180001c9f  mov     [rsp+48h+var_20], rcx
0x180001ca4  mov     rcx, r11
0x180001ca7  mov     [rsp+48h+var_28], r10
0x180001cac  call    j__guard_dispatch_icall
0x180001cb1  add     rsp, 48h
0x180001cb5  retn
```
