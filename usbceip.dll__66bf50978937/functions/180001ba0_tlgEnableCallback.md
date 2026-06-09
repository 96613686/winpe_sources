# _tlgEnableCallback

- ea: `0x180001ba0`
- end: `0x180001c16`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001ba0`
- `0x180011010`

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
0x180001ba0  sub     rsp, 48h
0x180001ba4  mov     r11, rcx
0x180001ba7  mov     rcx, [rsp+48h+CallbackContext]
0x180001baf  test    rcx, rcx
0x180001bb2  jz      short loc_180001C11
0x180001bb4  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001bb9  mov     eax, edx
0x180001bbb  test    edx, edx
0x180001bbd  jz      short loc_180001BE2
0x180001bbf  cmp     eax, 1
0x180001bc2  jnz     short loc_180001BE8
0x180001bc4  test    r8b, r8b
0x180001bc7  jz      short loc_180001BD1
0x180001bc9  movzx   eax, r8b
0x180001bcd  inc     eax
0x180001bcf  jmp     short loc_180001BD6
0x180001bd1  mov     eax, 100h
0x180001bd6  mov     [rcx], eax
0x180001bd8  mov     [rcx+10h], r9
0x180001bdc  mov     [rcx+18h], r10
0x180001be0  jmp     short loc_180001BE8
0x180001be2  mov     dword ptr [rcx], 0
0x180001be8  mov     rax, [rcx+28h]
0x180001bec  test    rax, rax
0x180001bef  jz      short loc_180001C11
0x180001bf1  mov     rcx, [rcx+30h]
0x180001bf5  mov     [rsp+48h+var_18], rcx
0x180001bfa  mov     rcx, [rsp+48h+FilterData]
0x180001bff  mov     [rsp+48h+var_20], rcx
0x180001c04  mov     rcx, r11
0x180001c07  mov     [rsp+48h+var_28], r10
0x180001c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c11  add     rsp, 48h
0x180001c15  retn
```
