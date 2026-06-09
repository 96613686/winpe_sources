# EnableCallback

- ea: `0x1800023f0`
- end: `0x180002495`
- name: `EnableCallback`
- size: `165`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800023f0`
- `0x1800313f0`

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
0x1800023f0  push    rbx
0x1800023f2  push    rbp
0x1800023f3  push    rsi
0x1800023f4  push    rdi
0x1800023f5  push    r12
0x1800023f7  push    r14
0x1800023f9  push    r15
0x1800023fb  sub     rsp, 40h
0x1800023ff  mov     rbx, [rsp+78h+CallbackContext]
0x180002407  mov     r14, r9
0x18000240a  movzx   edi, r8b
0x18000240e  mov     r15d, edx
0x180002411  mov     r12, rcx
0x180002414  test    rbx, rbx
0x180002417  jz      short loc_180002486
0x180002419  mov     rbp, [rsp+78h+MatchAllKeyword]
0x180002421  mov     eax, edx
0x180002423  test    edx, edx
0x180002425  jz      short loc_180002445
0x180002427  cmp     eax, 1
0x18000242a  jnz     short loc_18000244B
0x18000242c  lea     eax, [rdi+1]
0x18000242f  test    r8b, r8b
0x180002432  jnz     short loc_180002439
0x180002434  mov     eax, 100h
0x180002439  mov     [rbx], eax
0x18000243b  mov     [rbx+10h], r14
0x18000243f  mov     [rbx+18h], rbp
0x180002443  jmp     short loc_18000244B
0x180002445  mov     dword ptr [rbx], 0
0x18000244b  mov     rsi, [rbx+28h]
0x18000244f  test    rsi, rsi
0x180002452  jz      short loc_180002486
0x180002454  mov     rcx, rsi
0x180002457  call    cs:__guard_check_icall_fptr
0x18000245d  mov     rax, [rbx+30h]
0x180002461  mov     r9, r14
0x180002464  mov     [rsp+78h+var_48], rax
0x180002469  mov     r8b, dil
0x18000246c  mov     rax, [rsp+78h+FilterData]
0x180002474  mov     edx, r15d
0x180002477  mov     [rsp+78h+var_50], rax
0x18000247c  mov     rcx, r12
0x18000247f  mov     [rsp+78h+var_58], rbp
0x180002484  call    rsi
0x180002486  add     rsp, 40h
0x18000248a  pop     r15
0x18000248c  pop     r14
0x18000248e  pop     r12
0x180002490  pop     rdi
0x180002491  pop     rsi
0x180002492  pop     rbp
0x180002493  pop     rbx
0x180002494  retn
```
