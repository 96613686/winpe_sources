# CWriteToIStream::Close(void)

- ea: `0x1800e3b00`
- end: `0x1800e3b61`
- name: `?Close@CWriteToIStream@@UEAAJXZ`
- size: `97`
- prototype: `__int64 __fastcall(CWriteToIStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054d28`

## callees

- `0x1800e3b00`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3b28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3b28`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWriteToIStream::Close(CWriteToIStream *this)
{
  int v2; // edi
  void *v3; // rcx
  __int64 v4; // rcx

  v2 = (*(__int64 (__fastcall **)(CWriteToIStream *))(*(_QWORD *)this + 40LL))(this);
  if ( v2 >= 0 )
  {
    v3 = (void *)*((_QWORD *)this + 2);
    if ( v3 )
    {
      CoTaskMemFree(v3);
      *((_QWORD *)this + 2) = 0;
    }
    v4 = *((_QWORD *)this + 1);
    if ( v4 )
    {
      *((_QWORD *)this + 1) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800e3b00  mov     [rsp+arg_0], rbx
0x1800e3b05  push    rdi
0x1800e3b06  sub     rsp, 20h
0x1800e3b0a  mov     rbx, rcx
0x1800e3b0d  mov     rax, [rcx]
0x1800e3b10  mov     rax, [rax+28h]
0x1800e3b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3b19  mov     edi, eax
0x1800e3b1b  test    eax, eax
0x1800e3b1d  js      short loc_1800E3B54
0x1800e3b1f  mov     rcx, [rbx+10h]; pv
0x1800e3b23  test    rcx, rcx
0x1800e3b26  jz      short loc_1800E3B36
0x1800e3b28  call    cs:__imp_CoTaskMemFree
0x1800e3b2e  mov     qword ptr [rbx+10h], 0
0x1800e3b36  mov     rcx, [rbx+8]
0x1800e3b3a  test    rcx, rcx
0x1800e3b3d  jz      short loc_1800E3B54
0x1800e3b3f  mov     qword ptr [rbx+8], 0
0x1800e3b47  mov     rax, [rcx]
0x1800e3b4a  mov     rax, [rax+10h]
0x1800e3b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3b53  nop
0x1800e3b54  mov     eax, edi
0x1800e3b56  mov     rbx, [rsp+28h+arg_0]
0x1800e3b5b  add     rsp, 20h
0x1800e3b5f  pop     rdi
0x1800e3b60  retn
```
