# _tlgEnableCallback

- ea: `0x140001670`
- end: `0x1400016f3`
- name: `_tlgEnableCallback`
- size: `131`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001670`
- `0x1400206e0`

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
0x140001670  mov     [rsp+arg_0], rbx
0x140001675  push    rdi
0x140001676  sub     rsp, 40h
0x14000167a  mov     r10, [rsp+48h+CallbackContext]
0x140001682  mov     rdi, rcx
0x140001685  test    r10, r10
0x140001688  jz      short loc_1400016E8
0x14000168a  mov     r11, [rsp+48h+MatchAllKeyword]
0x14000168f  mov     eax, edx
0x140001691  test    edx, edx
0x140001693  jz      short loc_1400016B8
0x140001695  cmp     eax, 1
0x140001698  jnz     short loc_1400016BF
0x14000169a  movzx   eax, r8b
0x14000169e  mov     ecx, 100h
0x1400016a3  inc     eax
0x1400016a5  mov     [r10+10h], r9
0x1400016a9  test    r8b, r8b
0x1400016ac  mov     [r10+18h], r11
0x1400016b0  cmovnz  ecx, eax
0x1400016b3  mov     [r10], ecx
0x1400016b6  jmp     short loc_1400016BF
0x1400016b8  mov     dword ptr [r10], 0
0x1400016bf  mov     rax, [r10+28h]
0x1400016c3  test    rax, rax
0x1400016c6  jz      short loc_1400016E8
0x1400016c8  mov     rcx, [r10+30h]
0x1400016cc  mov     [rsp+48h+var_18], rcx
0x1400016d1  mov     rcx, [rsp+48h+FilterData]
0x1400016d6  mov     [rsp+48h+var_20], rcx
0x1400016db  mov     rcx, rdi
0x1400016de  mov     [rsp+48h+var_28], r11
0x1400016e3  call    _guard_dispatch_icall
0x1400016e8  mov     rbx, [rsp+48h+arg_0]
0x1400016ed  add     rsp, 40h
0x1400016f1  pop     rdi
0x1400016f2  retn
```
