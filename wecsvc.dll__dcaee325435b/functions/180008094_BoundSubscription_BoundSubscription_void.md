# BoundSubscription::~BoundSubscription(void)

- ea: `0x180008094`
- end: `0x180008157`
- name: `??1BoundSubscription@@UEAA@XZ`
- size: `195`
- prototype: `void __fastcall(BoundSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800086b0`

## callees

- `0x1800062d4`
- `0x180008094`
- `0x18000dda4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008141`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080c6`

## pseudocode

```c
void __fastcall BoundSubscription::~BoundSubscription(BoundSubscription *this)
{
  __int64 v2; // rdx
  void *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx

  *(_QWORD *)this = &BoundSubscription::`vftable';
  BoundSubscription::InternalDeactivate(this, 1);
  v3 = (void *)*((_QWORD *)this + 29);
  if ( v3 )
    CloseHandle(v3);
  LOBYTE(v2) = 1;
  std::wstring::_Tidy((char *)this + 464, v2, 0);
  LOBYTE(v4) = 1;
  std::wstring::_Tidy((char *)this + 432, v4, 0);
  LOBYTE(v5) = 1;
  std::wstring::_Tidy((char *)this + 400, v5, 0);
  LOBYTE(v6) = 1;
  std::wstring::_Tidy((char *)this + 184, v6, 0);
  LOBYTE(v7) = 1;
  std::wstring::_Tidy((char *)this + 136, v7, 0);
  LOBYTE(v8) = 1;
  std::wstring::_Tidy((char *)this + 104, v8, 0);
  LOBYTE(v9) = 1;
  std::wstring::_Tidy((char *)this + 72, v9, 0);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &wmi::RefBase::`vftable';
}

```

## disassembly

```asm
0x180008094  mov     [rsp+arg_0], rcx
0x180008099  push    rbx
0x18000809a  sub     rsp, 20h
0x18000809e  mov     rbx, rcx
0x1800080a1  lea     rax, ??_7BoundSubscription@@6B@; const BoundSubscription::`vftable'
0x1800080a8  mov     [rcx], rax
0x1800080ab  mov     dl, 1; bool
0x1800080ad  call    ?InternalDeactivate@BoundSubscription@@QEAAX_N@Z; BoundSubscription::InternalDeactivate(bool)
0x1800080b2  nop
0x1800080b3  jmp     short loc_1800080BA
0x1800080b5  mov     rbx, [rsp+28h+arg_0]
0x1800080ba  mov     rcx, [rbx+0E8h]; hObject
0x1800080c1  test    rcx, rcx
0x1800080c4  jz      short loc_1800080CC
0x1800080c6  call    cs:__imp_CloseHandle
0x1800080cc  lea     rcx, [rbx+1D0h]
0x1800080d3  xor     r8d, r8d
0x1800080d6  mov     dl, 1
0x1800080d8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800080dd  lea     rcx, [rbx+1B0h]
0x1800080e4  xor     r8d, r8d
0x1800080e7  mov     dl, 1
0x1800080e9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800080ee  lea     rcx, [rbx+190h]
0x1800080f5  xor     r8d, r8d
0x1800080f8  mov     dl, 1
0x1800080fa  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800080ff  lea     rcx, [rbx+0B8h]
0x180008106  xor     r8d, r8d
0x180008109  mov     dl, 1
0x18000810b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180008110  lea     rcx, [rbx+88h]
0x180008117  xor     r8d, r8d
0x18000811a  mov     dl, 1
0x18000811c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180008121  lea     rcx, [rbx+68h]
0x180008125  xor     r8d, r8d
0x180008128  mov     dl, 1
0x18000812a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000812f  lea     rcx, [rbx+48h]
0x180008133  xor     r8d, r8d
0x180008136  mov     dl, 1
0x180008138  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000813d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180008141  call    cs:__imp_DeleteCriticalSection
0x180008147  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x18000814e  mov     [rbx], rax
0x180008151  add     rsp, 20h
0x180008155  pop     rbx
0x180008156  retn
```
