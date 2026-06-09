# _tlgEnableCallback

- ea: `0x1400045c0`
- end: `0x140004640`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400045c0`
- `0x140009010`

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
0x1400045c0  sub     rsp, 48h
0x1400045c4  mov     r11, rcx
0x1400045c7  mov     rcx, [rsp+48h+CallbackContext]
0x1400045cf  test    rcx, rcx
0x1400045d2  jz      short loc_14000463B
0x1400045d4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1400045d9  mov     eax, edx
0x1400045db  test    edx, edx
0x1400045dd  jz      short loc_14000460C
0x1400045df  cmp     eax, 1
0x1400045e2  jnz     short loc_140004612
0x1400045e4  test    r8b, r8b
0x1400045e7  jz      short loc_1400045FB
0x1400045e9  movzx   eax, r8b
0x1400045ed  inc     eax
0x1400045ef  mov     [rcx], eax
0x1400045f1  mov     [rcx+10h], r9
0x1400045f5  mov     [rcx+18h], r10
0x1400045f9  jmp     short loc_140004612
0x1400045fb  mov     eax, 100h
0x140004600  mov     [rcx], eax
0x140004602  mov     [rcx+10h], r9
0x140004606  mov     [rcx+18h], r10
0x14000460a  jmp     short loc_140004612
0x14000460c  mov     dword ptr [rcx], 0
0x140004612  mov     rax, [rcx+28h]
0x140004616  test    rax, rax
0x140004619  jz      short loc_14000463B
0x14000461b  mov     rcx, [rcx+30h]
0x14000461f  mov     [rsp+48h+var_18], rcx
0x140004624  mov     rcx, [rsp+48h+FilterData]
0x140004629  mov     [rsp+48h+var_20], rcx
0x14000462e  mov     rcx, r11
0x140004631  mov     [rsp+48h+var_28], r10
0x140004636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000463b  add     rsp, 48h
0x14000463f  retn
```
