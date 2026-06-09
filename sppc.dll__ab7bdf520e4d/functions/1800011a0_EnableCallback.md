# EnableCallback

- ea: `0x1800011a0`
- end: `0x180001245`
- name: `EnableCallback`
- size: `165`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800011a0`
- `0x18000eeb0`

## pseudocode

```c
void __fastcall EnableCallback(
        LPCGUID SourceId,
        ULONG IsEnabled,
        __int64 Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        _QWORD *CallbackContext)
{
  int v7; // eax
  void (__fastcall *v8)(LPCGUID, _QWORD, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rsi

  if ( CallbackContext )
  {
    if ( IsEnabled )
    {
      if ( IsEnabled == 1 )
      {
        v7 = (unsigned __int8)Level + 1;
        if ( !(_BYTE)Level )
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
    v8 = (void (__fastcall *)(LPCGUID, _QWORD, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD))CallbackContext[5];
    if ( v8 )
      v8(SourceId, IsEnabled, Level, MatchAnyKeyword, MatchAllKeyword, FilterData, CallbackContext[6]);
  }
}

```

## disassembly

```asm
0x1800011a0  push    rbx
0x1800011a2  push    rbp
0x1800011a3  push    rsi
0x1800011a4  push    rdi
0x1800011a5  push    r12
0x1800011a7  push    r14
0x1800011a9  push    r15
0x1800011ab  sub     rsp, 40h
0x1800011af  mov     rbx, [rsp+78h+CallbackContext]
0x1800011b7  mov     r14, r9
0x1800011ba  movzx   edi, r8b
0x1800011be  mov     r15d, edx
0x1800011c1  mov     r12, rcx
0x1800011c4  test    rbx, rbx
0x1800011c7  jz      short loc_180001236
0x1800011c9  mov     rbp, [rsp+78h+MatchAllKeyword]
0x1800011d1  mov     eax, edx
0x1800011d3  test    edx, edx
0x1800011d5  jz      short loc_1800011F5
0x1800011d7  cmp     eax, 1
0x1800011da  jnz     short loc_1800011FB
0x1800011dc  lea     eax, [rdi+1]
0x1800011df  test    r8b, r8b
0x1800011e2  jnz     short loc_1800011E9
0x1800011e4  mov     eax, 100h
0x1800011e9  mov     [rbx], eax
0x1800011eb  mov     [rbx+10h], r14
0x1800011ef  mov     [rbx+18h], rbp
0x1800011f3  jmp     short loc_1800011FB
0x1800011f5  mov     dword ptr [rbx], 0
0x1800011fb  mov     rsi, [rbx+28h]
0x1800011ff  test    rsi, rsi
0x180001202  jz      short loc_180001236
0x180001204  mov     rcx, rsi
0x180001207  call    cs:__guard_check_icall_fptr
0x18000120d  mov     rax, [rbx+30h]
0x180001211  mov     r9, r14
0x180001214  mov     [rsp+78h+var_48], rax
0x180001219  mov     r8b, dil
0x18000121c  mov     rax, [rsp+78h+FilterData]
0x180001224  mov     edx, r15d
0x180001227  mov     [rsp+78h+var_50], rax
0x18000122c  mov     rcx, r12
0x18000122f  mov     [rsp+78h+var_58], rbp
0x180001234  call    rsi
0x180001236  add     rsp, 40h
0x18000123a  pop     r15
0x18000123c  pop     r14
0x18000123e  pop     r12
0x180001240  pop     rdi
0x180001241  pop     rsi
0x180001242  pop     rbp
0x180001243  pop     rbx
0x180001244  retn
```
