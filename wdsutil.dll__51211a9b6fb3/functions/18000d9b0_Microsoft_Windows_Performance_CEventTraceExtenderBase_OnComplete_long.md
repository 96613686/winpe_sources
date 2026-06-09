# Microsoft::Windows::Performance::CEventTraceExtenderBase::OnComplete(long)

- ea: `0x18000d9b0`
- end: `0x18000da2a`
- name: `?OnComplete@CEventTraceExtenderBase@Performance@Windows@Microsoft@@UEAAJJ@Z`
- size: `122`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000d9b0`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceExtenderBase::OnComplete(
        Microsoft::Windows::Performance::CEventTraceExtenderBase *this,
        unsigned int a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 104LL))(v4);
    v5 = *((_QWORD *)this + 1);
    if ( v5 )
    {
      *((_QWORD *)this + 1) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  v6 = *((_QWORD *)this + 2);
  if ( v6 )
  {
    *((_QWORD *)this + 2) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return a2;
}

```

## disassembly

```asm
0x18000d9b0  push    rdi
0x18000d9b2  sub     rsp, 30h
0x18000d9b6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000d9bf  mov     [rsp+38h+arg_0], rbx
0x18000d9c4  mov     edi, edx
0x18000d9c6  mov     rbx, rcx
0x18000d9c9  mov     rcx, [rcx+8]
0x18000d9cd  test    rcx, rcx
0x18000d9d0  jz      short loc_18000D9FE
0x18000d9d2  mov     rax, [rcx]
0x18000d9d5  mov     rax, [rax+68h]
0x18000d9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9de  mov     edi, eax
0x18000d9e0  mov     rcx, [rbx+8]
0x18000d9e4  test    rcx, rcx
0x18000d9e7  jz      short loc_18000D9FE
0x18000d9e9  mov     qword ptr [rbx+8], 0
0x18000d9f1  mov     rax, [rcx]
0x18000d9f4  mov     rax, [rax+10h]
0x18000d9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9fd  nop
0x18000d9fe  mov     rcx, [rbx+10h]
0x18000da02  test    rcx, rcx
0x18000da05  jz      short loc_18000DA1C
0x18000da07  mov     qword ptr [rbx+10h], 0
0x18000da0f  mov     rax, [rcx]
0x18000da12  mov     rax, [rax+10h]
0x18000da16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da1b  nop
0x18000da1c  mov     eax, edi
0x18000da1e  mov     rbx, [rsp+38h+arg_0]
0x18000da23  add     rsp, 30h
0x18000da27  pop     rdi
0x18000da28  retn
```
