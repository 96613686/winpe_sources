# EnableCallback

- ea: `0x180002ad0`
- end: `0x180002b46`
- name: `EnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002ad0`
- `0x18002d010`

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
0x180002ad0  sub     rsp, 48h
0x180002ad4  mov     r11, rcx
0x180002ad7  mov     rcx, [rsp+48h+CallbackContext]
0x180002adf  test    rcx, rcx
0x180002ae2  jz      short loc_180002B41
0x180002ae4  mov     r10, [rsp+48h+MatchAllKeyword]
0x180002ae9  mov     eax, edx
0x180002aeb  test    edx, edx
0x180002aed  jz      short loc_180002B12
0x180002aef  cmp     eax, 1
0x180002af2  jnz     short loc_180002B18
0x180002af4  test    r8b, r8b
0x180002af7  jz      short loc_180002B01
0x180002af9  movzx   eax, r8b
0x180002afd  inc     eax
0x180002aff  jmp     short loc_180002B06
0x180002b01  mov     eax, 100h
0x180002b06  mov     [rcx], eax
0x180002b08  mov     [rcx+10h], r9
0x180002b0c  mov     [rcx+18h], r10
0x180002b10  jmp     short loc_180002B18
0x180002b12  mov     dword ptr [rcx], 0
0x180002b18  mov     rax, [rcx+28h]
0x180002b1c  test    rax, rax
0x180002b1f  jz      short loc_180002B41
0x180002b21  mov     rcx, [rcx+30h]
0x180002b25  mov     [rsp+48h+var_18], rcx
0x180002b2a  mov     rcx, [rsp+48h+FilterData]
0x180002b2f  mov     [rsp+48h+var_20], rcx
0x180002b34  mov     rcx, r11
0x180002b37  mov     [rsp+48h+var_28], r10
0x180002b3c  call    j__guard_dispatch_icall
0x180002b41  add     rsp, 48h
0x180002b45  retn
```
