# ATL::CComControlBase::OnSetFocus(uint,unsigned __int64,__int64,int &)

- ea: `0x18000802c`
- end: `0x18000814e`
- name: `?OnSetFocus@CComControlBase@ATL@@QEAA_JI_K_JAEAH@Z`
- size: `290`
- prototype: `__int64 __fastcall(ATL::CComControlBase *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008360`

## callees

- `0x18000802c`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComControlBase::OnSetFocus(
        ATL::CComControlBase *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5)
{
  __int64 v6; // rax
  __int64 v7; // rax
  void (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // r9
  __int64 v9; // rcx
  __int64 result; // rax
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = a4;
  v11 = a3;
  if ( (*((_BYTE *)this + 100) & 4) == 0 )
    goto LABEL_13;
  v6 = *(_QWORD *)this;
  v12 = 0;
  (*(void (__fastcall **)(ATL::CComControlBase *, GUID *, __int64 *))(v6 + 16))(
    this,
    &GUID_00000112_0000_0000_c000_000000000046,
    &v12);
  v7 = v12;
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD, _QWORD, char *))(*(_QWORD *)v12 + 88LL))(
      v12,
      4294967292LL,
      0,
      *((_QWORD *)this + 4),
      0,
      **((_QWORD **)this + 11),
      (char *)this + 72);
    v7 = v12;
  }
  v8 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 4);
  v9 = 0;
  v11 = 0;
  if ( v8 )
  {
    (**v8)(v8, &GUID_b196b289_bab4_101a_b69c_00aa00341d07, &v11);
    v7 = v12;
    v9 = v11;
  }
  if ( (*((_BYTE *)this + 100) & 4) == 0 )
    goto LABEL_9;
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 64LL))(v9, 1);
    v7 = v12;
    v9 = v11;
LABEL_9:
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      v7 = v12;
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
LABEL_13:
  result = 1;
  *a5 = 0;
  return result;
}

```

## disassembly

```asm
0x18000802c  mov     r11, rsp
0x18000802f  mov     [r11+20h], r9
0x180008033  mov     [r11+18h], r8
0x180008037  push    rbx
0x180008038  sub     rsp, 40h
0x18000803c  test    byte ptr [rcx+64h], 4
0x180008040  mov     rbx, rcx
0x180008043  jz      loc_180008138
0x180008049  mov     rax, [rcx]
0x18000804c  lea     r8, [r11+20h]
0x180008050  lea     rdx, _GUID_00000112_0000_0000_c000_000000000046
0x180008057  mov     qword ptr [r11+20h], 0
0x18000805f  mov     rax, [rax+10h]
0x180008063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008068  mov     rax, [rsp+48h+arg_18]
0x18000806d  test    rax, rax
0x180008070  jz      short loc_1800080B1
0x180008072  mov     rcx, [rax]
0x180008075  lea     rdx, [rbx+48h]
0x180008079  mov     r8, [rbx+58h]
0x18000807d  mov     r9, [rbx+20h]
0x180008081  mov     [rsp+48h+var_18], rdx
0x180008086  mov     r10, [rcx+58h]
0x18000808a  mov     rcx, [r8]
0x18000808d  xor     r8d, r8d
0x180008090  mov     [rsp+48h+var_20], rcx
0x180008095  mov     rcx, rax
0x180008098  mov     rax, r10
0x18000809b  mov     [rsp+48h+var_28], 0
0x1800080a3  lea     edx, [r8-4]
0x1800080a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080ac  mov     rax, [rsp+48h+arg_18]
0x1800080b1  mov     r9, [rbx+20h]
0x1800080b5  xor     ecx, ecx
0x1800080b7  mov     [rsp+48h+arg_10], rcx
0x1800080bc  test    r9, r9
0x1800080bf  jz      short loc_1800080E5
0x1800080c1  mov     rax, [r9]
0x1800080c4  lea     r8, [rsp+48h+arg_10]
0x1800080c9  lea     rdx, _GUID_b196b289_bab4_101a_b69c_00aa00341d07
0x1800080d0  mov     rcx, r9
0x1800080d3  mov     rax, [rax]
0x1800080d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080db  mov     rax, [rsp+48h+arg_18]
0x1800080e0  mov     rcx, [rsp+48h+arg_10]
0x1800080e5  test    byte ptr [rbx+64h], 4
0x1800080e9  jz      short loc_18000810B
0x1800080eb  test    rcx, rcx
0x1800080ee  jz      short loc_180008121
0x1800080f0  mov     rax, [rcx]
0x1800080f3  mov     edx, 1
0x1800080f8  mov     rax, [rax+40h]
0x1800080fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008101  mov     rax, [rsp+48h+arg_18]
0x180008106  mov     rcx, [rsp+48h+arg_10]
0x18000810b  test    rcx, rcx
0x18000810e  jz      short loc_180008121
0x180008110  mov     rax, [rcx]
0x180008113  mov     rax, [rax+10h]
0x180008117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000811c  mov     rax, [rsp+48h+arg_18]
0x180008121  test    rax, rax
0x180008124  jz      short loc_180008138
0x180008126  mov     rcx, [rax]
0x180008129  mov     rdx, [rcx+10h]
0x18000812d  mov     rcx, rax
0x180008130  mov     rax, rdx
0x180008133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008138  mov     rcx, [rsp+48h+arg_20]
0x18000813d  mov     eax, 1
0x180008142  mov     dword ptr [rcx], 0
0x180008148  add     rsp, 40h
0x18000814c  pop     rbx
0x18000814d  retn
```
