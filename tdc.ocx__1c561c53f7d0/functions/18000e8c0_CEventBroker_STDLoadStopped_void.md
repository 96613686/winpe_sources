# CEventBroker::STDLoadStopped(void)

- ea: `0x18000e8c0`
- end: `0x18000e937`
- name: `?STDLoadStopped@CEventBroker@@UEAAJXZ`
- size: `119`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e8c0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::STDLoadStopped(CEventBroker *this)
{
  __int64 v1; // rax
  unsigned int v2; // edi
  __int64 v4; // rcx
  __int64 v5; // rcx

  v1 = *((_QWORD *)this + 1);
  v2 = 0;
  if ( v1 )
  {
    v4 = *(_QWORD *)(v1 + 56);
    if ( v4 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
      *((_QWORD *)this + 1) = 0;
    }
  }
  v5 = *((_QWORD *)this + 5);
  if ( v5 )
    v2 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 80LL))(v5, 1);
  (*(void (__fastcall **)(CEventBroker *, __int64))(*(_QWORD *)this + 160LL))(this, 4);
  return v2;
}

```

## disassembly

```asm
0x18000e8c0  mov     [rsp+arg_0], rbx
0x18000e8c5  push    rdi
0x18000e8c6  sub     rsp, 20h
0x18000e8ca  mov     rax, [rcx+8]
0x18000e8ce  xor     edi, edi
0x18000e8d0  mov     rbx, rcx
0x18000e8d3  test    rax, rax
0x18000e8d6  jz      short loc_18000E8F7
0x18000e8d8  mov     rcx, [rax+38h]
0x18000e8dc  test    rcx, rcx
0x18000e8df  jz      short loc_18000E8F7
0x18000e8e1  mov     rax, [rcx]
0x18000e8e4  mov     rax, [rax+18h]
0x18000e8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8ed  mov     edi, eax
0x18000e8ef  mov     qword ptr [rbx+8], 0
0x18000e8f7  mov     rcx, [rbx+28h]
0x18000e8fb  test    rcx, rcx
0x18000e8fe  jz      short loc_18000E913
0x18000e900  mov     rax, [rcx]
0x18000e903  mov     edx, 1
0x18000e908  mov     rax, [rax+50h]
0x18000e90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e911  mov     edi, eax
0x18000e913  mov     rax, [rbx]
0x18000e916  mov     edx, 4
0x18000e91b  mov     rcx, rbx
0x18000e91e  mov     rax, [rax+0A0h]
0x18000e925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e92a  mov     rbx, [rsp+28h+arg_0]
0x18000e92f  mov     eax, edi
0x18000e931  add     rsp, 20h
0x18000e935  pop     rdi
0x18000e936  retn
```
