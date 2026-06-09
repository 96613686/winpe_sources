# ATL::CComControl<CTDCCtl,ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>>::FireOnChanged(long)

- ea: `0x180005504`
- end: `0x180005669`
- name: `?FireOnChanged@?$CComControl@VCTDCCtl@@V?$CWindowImpl@VCTDCCtl@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@ATL@@@ATL@@QEAAJJ@Z`
- size: `357`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800097d4`
- `0x18000ad30`
- `0x18000ea80`

## callees

- `0x180005504`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComControl<CTDCCtl,ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>>::FireOnChanged(
        __int64 a1)
{
  void (__fastcall ***v1)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v3; // [rsp+30h] [rbp-20h] BYREF
  __int128 v4; // [rsp+38h] [rbp-18h] BYREF
  __int64 v5; // [rsp+60h] [rbp+10h] BYREF
  __int64 v6; // [rsp+70h] [rbp+20h] BYREF
  __int64 v7; // [rsp+78h] [rbp+28h] BYREF

  v5 = 0;
  v1 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))(a1 + 176);
  if ( v1 )
  {
    (**v1)(v1, &GUID_b196b284_bab4_101a_b69c_00aa00341d07, &v5);
    if ( v5 )
    {
      v7 = 0;
      (*(void (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v5 + 32LL))(
        v5,
        &GUID_9bfbbc02_eff1_101a_84ed_00aa00341d07,
        &v7);
      if ( v7 )
      {
        v6 = 0;
        if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 56LL))(v7, &v6) >= 0 )
        {
          v4 = 0;
          while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v6 + 24LL))(v6, 1, &v4) )
          {
            if ( (_QWORD)v4 )
            {
              v3 = 0;
              (**(void (__fastcall ***)(_QWORD, GUID *, __int64 *))v4)(
                v4,
                &GUID_9bfbbc02_eff1_101a_84ed_00aa00341d07,
                &v3);
              if ( v3 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 24LL))(v3, 4294966771LL);
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4 + 16LL))(v4);
              if ( v3 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
            }
          }
        }
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005504  push    rbp
0x180005506  mov     rbp, rsp
0x180005509  sub     rsp, 50h
0x18000550d  mov     [rbp+arg_0], 0
0x180005515  add     rcx, 0B0h
0x18000551c  jz      loc_180005661
0x180005522  mov     rax, [rcx]
0x180005525  lea     r8, [rbp+arg_0]
0x180005529  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x180005530  mov     rax, [rax]
0x180005533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005538  mov     rcx, [rbp+arg_0]
0x18000553c  test    rcx, rcx
0x18000553f  jz      loc_180005661
0x180005545  mov     [rbp+arg_18], 0
0x18000554d  lea     r8, [rbp+arg_18]
0x180005551  mov     rax, [rcx]
0x180005554  lea     rdx, _GUID_9bfbbc02_eff1_101a_84ed_00aa00341d07
0x18000555b  mov     rax, [rax+20h]
0x18000555f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005564  mov     rcx, [rbp+arg_18]
0x180005568  test    rcx, rcx
0x18000556b  jz      loc_18000564C
0x180005571  mov     [rbp+arg_10], 0
0x180005579  lea     rdx, [rbp+arg_10]
0x18000557d  mov     rax, [rcx]
0x180005580  mov     rax, [rax+38h]
0x180005584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005589  test    eax, eax
0x18000558b  js      loc_180005622
0x180005591  xorps   xmm0, xmm0
0x180005594  movups  [rbp+var_18], xmm0
0x180005598  mov     rcx, [rbp+arg_10]
0x18000559c  lea     r8, [rbp+var_18]
0x1800055a0  xor     r9d, r9d
0x1800055a3  mov     rax, [rcx]
0x1800055a6  lea     edx, [r9+1]
0x1800055aa  mov     rax, [rax+18h]
0x1800055ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055b3  test    eax, eax
0x1800055b5  jnz     short loc_180005622
0x1800055b7  mov     rcx, qword ptr [rbp+var_18]
0x1800055bb  test    rcx, rcx
0x1800055be  jz      short loc_180005598
0x1800055c0  mov     [rbp+var_20], 0
0x1800055c8  lea     r8, [rbp+var_20]
0x1800055cc  mov     rax, [rcx]
0x1800055cf  lea     rdx, _GUID_9bfbbc02_eff1_101a_84ed_00aa00341d07
0x1800055d6  mov     rax, [rax]
0x1800055d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055de  mov     rcx, [rbp+var_20]
0x1800055e2  test    rcx, rcx
0x1800055e5  jz      short loc_1800055F8
0x1800055e7  mov     rax, [rcx]
0x1800055ea  mov     edx, 0FFFFFDF3h
0x1800055ef  mov     rax, [rax+18h]
0x1800055f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055f8  mov     rcx, qword ptr [rbp+var_18]
0x1800055fc  mov     rax, [rcx]
0x1800055ff  mov     rax, [rax+10h]
0x180005603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005608  mov     rcx, [rbp+var_20]
0x18000560c  test    rcx, rcx
0x18000560f  jz      short loc_180005598
0x180005611  mov     rax, [rcx]
0x180005614  mov     rax, [rax+10h]
0x180005618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000561d  jmp     loc_180005598
0x180005622  mov     rcx, [rbp+arg_10]
0x180005626  test    rcx, rcx
0x180005629  jz      short loc_180005637
0x18000562b  mov     rax, [rcx]
0x18000562e  mov     rax, [rax+10h]
0x180005632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005637  mov     rcx, [rbp+arg_18]
0x18000563b  test    rcx, rcx
0x18000563e  jz      short loc_18000564C
0x180005640  mov     rax, [rcx]
0x180005643  mov     rax, [rax+10h]
0x180005647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000564c  mov     rcx, [rbp+arg_0]
0x180005650  test    rcx, rcx
0x180005653  jz      short loc_180005661
0x180005655  mov     rax, [rcx]
0x180005658  mov     rax, [rax+10h]
0x18000565c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005661  xor     eax, eax
0x180005663  add     rsp, 50h
0x180005667  pop     rbp
0x180005668  retn
```
