# std::_Uninitialized_move<std::shared_ptr<WcmConnectionSelection> *,std::allocator<std::shared_ptr<WcmConnectionSelection>>>(std::shared_ptr<WcmConnectionSelection> * const,std::shared_ptr<WcmConnectionSelection> * const,std::shared_ptr<WcmConnectionSelection> *,std::allocator<std::shared_ptr<WcmConnectionSelection>> &)

- ea: `0x180019580`
- end: `0x1800195d3`
- name: `??$_Uninitialized_move@PEAV?$shared_ptr@VWcmConnectionSelection@@@std@@V?$allocator@V?$shared_ptr@VWcmConnectionSelection@@@std@@@2@@std@@YAPEAV?$shared_ptr@VWcmConnectionSelection@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@VWcmConnectionSelection@@@std@@@0@@Z`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001932c`
- `0x18001944c`

## callees

- `0x1800192c8`
- `0x180019308`
- `0x180019580`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<std::shared_ptr<WcmConnectionSelection> *,std::allocator<std::shared_ptr<WcmConnectionSelection>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rbx
  __int64 v5; // r10
  __int64 v6; // r10
  __int64 v7; // r11
  __int64 v9; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+28h] [rbp-20h]
  __int64 v11; // [rsp+30h] [rbp-18h]

  v11 = a4;
  v4 = a3;
  v9 = a3;
  v10 = a3;
  v5 = a1;
  if ( a1 != a2 )
  {
    do
    {
      std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<WcmConnectionSelection>>>::_Emplace_back<std::shared_ptr<WcmConnectionSelection>>(
        &v9,
        v5);
      v5 = v6 + 16;
    }
    while ( v5 != v7 );
    v4 = v10;
  }
  std::_Destroy_range<std::allocator<std::shared_ptr<WcmConnectionSelection>>>(v4, v4);
  return v4;
}

```

## disassembly

```asm
0x180019580  push    rbx
0x180019582  sub     rsp, 40h
0x180019586  mov     [rsp+48h+var_18], r9
0x18001958b  mov     rbx, r8
0x18001958e  mov     [rsp+48h+var_28], rbx
0x180019593  mov     r11, rdx
0x180019596  mov     [rsp+48h+var_20], rbx
0x18001959b  mov     r10, rcx
0x18001959e  cmp     rcx, rdx
0x1800195a1  jz      short loc_1800195BE
0x1800195a3  mov     rdx, r10
0x1800195a6  lea     rcx, [rsp+48h+var_28]
0x1800195ab  call    ??$_Emplace_back@V?$shared_ptr@VWcmConnectionSelection@@@std@@@?$_Uninitialized_backout_al@V?$allocator@V?$shared_ptr@VWcmConnectionSelection@@@std@@@std@@@std@@QEAAX$$QEAV?$shared_ptr@VWcmConnectionSelection@@@1@@Z; std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<WcmConnectionSelection>>>::_Emplace_back<std::shared_ptr<WcmConnectionSelection>>(std::shared_ptr<WcmConnectionSelection> &&)
0x1800195b0  add     r10, 10h
0x1800195b4  cmp     r10, r11
0x1800195b7  jnz     short loc_1800195A3
0x1800195b9  mov     rbx, [rsp+48h+var_20]
0x1800195be  mov     rdx, rbx
0x1800195c1  mov     rcx, rbx
0x1800195c4  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VWcmConnectionSelection@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VWcmConnectionSelection@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VWcmConnectionSelection@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<WcmConnectionSelection>>>(std::shared_ptr<WcmConnectionSelection> *,std::shared_ptr<WcmConnectionSelection> * const,std::allocator<std::shared_ptr<WcmConnectionSelection>> &)
0x1800195c9  mov     rax, rbx
0x1800195cc  add     rsp, 40h
0x1800195d0  pop     rbx
0x1800195d1  retn
```
