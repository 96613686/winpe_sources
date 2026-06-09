# CWpnIdleTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180006260`
- end: `0x1800062cb`
- name: `?QueryInterface@CWpnIdleTaskHandler@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(CWpnIdleTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180006260`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CWpnIdleTaskHandler::QueryInterface(CWpnIdleTaskHandler *this, const struct _GUID *a2, void **a3)
{
  unsigned int v3; // ebx

  if ( a3 )
  {
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_839d7762_5121_4009_9234_4f0d19394f04.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_839d7762_5121_4009_9234_4f0d19394f04.Data4
      || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
    {
      *a3 = this;
      v3 = 0;
      (*(void (__fastcall **)(CWpnIdleTaskHandler *))(*(_QWORD *)this + 8LL))(this);
    }
    else
    {
      *a3 = 0;
      return (unsigned int)-2147467262;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180006260  push    rbx
0x180006262  sub     rsp, 20h
0x180006266  test    r8, r8
0x180006269  jnz     short loc_180006272
0x18000626b  mov     ebx, 80070057h
0x180006270  jmp     short loc_1800062C3
0x180006272  mov     rax, [rdx]
0x180006275  cmp     rax, qword ptr cs:_GUID_839d7762_5121_4009_9234_4f0d19394f04.Data1
0x18000627c  jnz     short loc_18000628B
0x18000627e  mov     rax, [rdx+8]
0x180006282  cmp     rax, qword ptr cs:_GUID_839d7762_5121_4009_9234_4f0d19394f04.Data4
0x180006289  jz      short loc_1800062A4
0x18000628b  mov     rax, [rdx]
0x18000628e  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180006295  jnz     short loc_1800062B7
0x180006297  mov     rax, [rdx+8]
0x18000629b  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800062a2  jnz     short loc_1800062B7
0x1800062a4  mov     [r8], rcx
0x1800062a7  xor     ebx, ebx
0x1800062a9  mov     rax, [rcx]
0x1800062ac  mov     rax, [rax+8]
0x1800062b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062b5  jmp     short loc_1800062C3
0x1800062b7  mov     qword ptr [r8], 0
0x1800062be  mov     ebx, 80004002h
0x1800062c3  mov     eax, ebx
0x1800062c5  add     rsp, 20h
0x1800062c9  pop     rbx
0x1800062ca  retn
```
