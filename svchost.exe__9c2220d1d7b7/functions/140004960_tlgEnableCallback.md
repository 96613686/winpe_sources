# _tlgEnableCallback

- ea: `0x140004960`
- end: `0x1400049e1`
- name: `_tlgEnableCallback`
- size: `129`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140004960`
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
0x140004960  sub     rsp, 48h
0x140004964  mov     r11, rcx
0x140004967  mov     rcx, [rsp+48h+CallbackContext]
0x14000496f  test    rcx, rcx
0x140004972  jz      short loc_1400049DB
0x140004974  mov     r10, [rsp+48h+MatchAllKeyword]
0x140004979  mov     eax, edx
0x14000497b  test    edx, edx
0x14000497d  jz      short loc_1400049AC
0x14000497f  cmp     eax, 1
0x140004982  jnz     short loc_1400049B2
0x140004984  test    r8b, r8b
0x140004987  jz      short loc_14000499B
0x140004989  movzx   eax, r8b
0x14000498d  inc     eax
0x14000498f  mov     [rcx], eax
0x140004991  mov     [rcx+10h], r9
0x140004995  mov     [rcx+18h], r10
0x140004999  jmp     short loc_1400049B2
0x14000499b  mov     eax, 100h
0x1400049a0  mov     [rcx], eax
0x1400049a2  mov     [rcx+10h], r9
0x1400049a6  mov     [rcx+18h], r10
0x1400049aa  jmp     short loc_1400049B2
0x1400049ac  mov     dword ptr [rcx], 0
0x1400049b2  mov     rax, [rcx+28h]
0x1400049b6  test    rax, rax
0x1400049b9  jz      short loc_1400049DB
0x1400049bb  mov     rcx, [rcx+30h]
0x1400049bf  mov     [rsp+48h+var_18], rcx
0x1400049c4  mov     rcx, [rsp+48h+FilterData]
0x1400049c9  mov     [rsp+48h+var_20], rcx
0x1400049ce  mov     rcx, r11
0x1400049d1  mov     [rsp+48h+var_28], r10
0x1400049d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049db  add     rsp, 48h
0x1400049df  retn
```
