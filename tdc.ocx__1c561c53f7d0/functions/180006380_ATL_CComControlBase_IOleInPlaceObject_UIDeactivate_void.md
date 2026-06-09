# ATL::CComControlBase::IOleInPlaceObject_UIDeactivate(void)

- ea: `0x180006380`
- end: `0x1800064d9`
- name: `?IOleInPlaceObject_UIDeactivate@CComControlBase@ATL@@QEAAJXZ`
- size: `345`
- prototype: `__int64 __fastcall(ATL::CComControlBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007c00`
- `0x180009700`

## callees

- `0x180006380`
- `0x180014270`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComControlBase::IOleInPlaceObject_UIDeactivate(ATL::CComControlBase *this)
{
  int v1; // eax
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v8; // [rsp+40h] [rbp-9h] BYREF
  __int64 v9; // [rsp+48h] [rbp-1h] BYREF
  __int64 v10; // [rsp+50h] [rbp+7h] BYREF
  _OWORD v11[2]; // [rsp+58h] [rbp+Fh] BYREF
  __int128 v12; // [rsp+78h] [rbp+2Fh] BYREF
  __int128 v13; // [rsp+88h] [rbp+3Fh] BYREF

  v1 = *((_DWORD *)this + 25);
  if ( (v1 & 8) != 0 )
  {
    v10 = 0;
    *((_DWORD *)this + 25) = v1 & 0xFFFFFFF7;
    v3 = *((_QWORD *)this + 1);
    if ( v3 )
    {
      if ( !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 24LL))(v3, &v10) )
      {
        v4 = *((_QWORD *)this + 1);
        memset(v11, 0, sizeof(v11));
        v9 = 0;
        v8 = 0;
        LODWORD(v11[0]) = 32;
        v13 = 0;
        v12 = 0;
        (*(void (__fastcall **)(__int64, __int64 *, __int64 *, __int128 *, __int128 *, _OWORD *))(*(_QWORD *)v4 + 64LL))(
          v4,
          &v9,
          &v8,
          &v13,
          &v12,
          v11);
        v5 = v8;
        if ( v8 )
        {
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v8 + 64LL))(v8, 0, 0);
          v5 = v8;
        }
        v6 = v9;
        if ( v9 )
        {
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 64LL))(v9, 0, 0);
          v6 = v9;
          v5 = v8;
        }
        if ( v5 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          v6 = v9;
        }
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1), 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006380  mov     [rsp-8+arg_8], rbx
0x180006385  push    rbp
0x180006386  lea     rbp, [rsp-57h]
0x18000638b  sub     rsp, 0A0h
0x180006392  mov     rax, cs:__security_cookie
0x180006399  xor     rax, rsp
0x18000639c  mov     [rbp+57h+var_8], rax
0x1800063a0  mov     eax, [rcx+64h]
0x1800063a3  mov     rbx, rcx
0x1800063a6  test    al, 8
0x1800063a8  jz      loc_1800064BA
0x1800063ae  and     eax, 0FFFFFFF7h
0x1800063b1  mov     [rbp+57h+var_50], 0
0x1800063b9  mov     [rcx+64h], eax
0x1800063bc  mov     rcx, [rcx+8]
0x1800063c0  test    rcx, rcx
0x1800063c3  jz      loc_1800064BA
0x1800063c9  mov     rax, [rcx]
0x1800063cc  lea     rdx, [rbp+57h+var_50]
0x1800063d0  mov     rax, [rax+18h]
0x1800063d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d9  test    eax, eax
0x1800063db  jnz     loc_1800064A8
0x1800063e1  mov     rcx, [rbx+8]
0x1800063e5  lea     rdx, [rbp+57h+var_48]
0x1800063e9  xorps   xmm0, xmm0
0x1800063ec  mov     [rsp+0A0h+var_78], rdx
0x1800063f1  movups  [rbp+57h+var_48], xmm0
0x1800063f5  mov     [rbp+57h+var_58], 0
0x1800063fd  lea     rdx, [rbp+57h+var_28]
0x180006401  xorps   xmm1, xmm1
0x180006404  mov     [rbp+57h+var_60], 0
0x18000640c  movups  [rbp+57h+var_38], xmm0
0x180006410  mov     dword ptr [rbp+57h+var_48], 20h ; ' '
0x180006417  lea     r9, [rbp+57h+var_18]
0x18000641b  movups  [rbp+57h+var_18], xmm0
0x18000641f  mov     [rsp+0A0h+var_80], rdx
0x180006424  lea     r8, [rbp+57h+var_60]
0x180006428  movups  [rbp+57h+var_28], xmm1
0x18000642c  mov     rax, [rcx]
0x18000642f  lea     rdx, [rbp+57h+var_58]
0x180006433  mov     rax, [rax+40h]
0x180006437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000643c  mov     r9, [rbp+57h+var_60]
0x180006440  test    r9, r9
0x180006443  jz      short loc_18000645D
0x180006445  mov     rax, [r9]
0x180006448  xor     r8d, r8d
0x18000644b  xor     edx, edx
0x18000644d  mov     rcx, r9
0x180006450  mov     rax, [rax+40h]
0x180006454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006459  mov     r9, [rbp+57h+var_60]
0x18000645d  mov     rcx, [rbp+57h+var_58]
0x180006461  test    rcx, rcx
0x180006464  jz      short loc_18000647F
0x180006466  mov     rax, [rcx]
0x180006469  xor     r8d, r8d
0x18000646c  xor     edx, edx
0x18000646e  mov     rax, [rax+40h]
0x180006472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006477  mov     rcx, [rbp+57h+var_58]
0x18000647b  mov     r9, [rbp+57h+var_60]
0x18000647f  test    r9, r9
0x180006482  jz      short loc_180006497
0x180006484  mov     rax, [r9]
0x180006487  mov     rcx, r9
0x18000648a  mov     rax, [rax+10h]
0x18000648e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006493  mov     rcx, [rbp+57h+var_58]
0x180006497  test    rcx, rcx
0x18000649a  jz      short loc_1800064A8
0x18000649c  mov     rax, [rcx]
0x18000649f  mov     rax, [rax+10h]
0x1800064a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064a8  mov     rcx, [rbx+8]
0x1800064ac  xor     edx, edx
0x1800064ae  mov     rax, [rcx]
0x1800064b1  mov     rax, [rax+50h]
0x1800064b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ba  xor     eax, eax
0x1800064bc  mov     rcx, [rbp+57h+var_8]
0x1800064c0  xor     rcx, rsp; StackCookie
0x1800064c3  call    __security_check_cookie
0x1800064c8  mov     rbx, [rsp+0A0h+arg_8]
0x1800064d0  add     rsp, 0A0h
0x1800064d7  pop     rbp
0x1800064d8  retn
```
