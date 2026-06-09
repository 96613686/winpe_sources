# _tlgEnableCallback

- ea: `0x180001360`
- end: `0x1800013d6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001360`
- `0x180037010`

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
0x180001360  sub     rsp, 48h
0x180001364  mov     r11, rcx
0x180001367  mov     rcx, [rsp+48h+CallbackContext]
0x18000136f  test    rcx, rcx
0x180001372  jz      short loc_1800013D1
0x180001374  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001379  mov     eax, edx
0x18000137b  test    edx, edx
0x18000137d  jz      short loc_1800013A2
0x18000137f  cmp     eax, 1
0x180001382  jnz     short loc_1800013A8
0x180001384  test    r8b, r8b
0x180001387  jz      short loc_180001391
0x180001389  movzx   eax, r8b
0x18000138d  inc     eax
0x18000138f  jmp     short loc_180001396
0x180001391  mov     eax, 100h
0x180001396  mov     [rcx], eax
0x180001398  mov     [rcx+10h], r9
0x18000139c  mov     [rcx+18h], r10
0x1800013a0  jmp     short loc_1800013A8
0x1800013a2  mov     dword ptr [rcx], 0
0x1800013a8  mov     rax, [rcx+28h]
0x1800013ac  test    rax, rax
0x1800013af  jz      short loc_1800013D1
0x1800013b1  mov     rcx, [rcx+30h]
0x1800013b5  mov     [rsp+48h+var_18], rcx
0x1800013ba  mov     rcx, [rsp+48h+FilterData]
0x1800013bf  mov     [rsp+48h+var_20], rcx
0x1800013c4  mov     rcx, r11
0x1800013c7  mov     [rsp+48h+var_28], r10
0x1800013cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013d1  add     rsp, 48h
0x1800013d5  retn
```
