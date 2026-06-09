# CWSHRemote::CError::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x140001750`
- end: `0x1400017b4`
- name: `?GetTypeInfo@CError@CWSHRemote@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `100`
- prototype: `__int64 __fastcall(CWSHRemote::CError *__hidden this, unsigned int, unsigned int, struct ITypeInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001750`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000177a`
- `KERNEL32!GetCurrentThreadId` at `0x14000177a`

## pseudocode

```c
__int64 __fastcall CWSHRemote::CError::GetTypeInfo(CWSHRemote::CError *this, int a2, __int64 a3, struct ITypeInfo **a4)
{
  int v7; // ebx

  *a4 = 0;
  if ( a2 )
    return 2147614731LL;
  v7 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v7 )
    return 2147549183LL;
  *a4 = (struct ITypeInfo *)*((_QWORD *)this + 7);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
  return 0;
}

```

## disassembly

```asm
0x140001750  mov     [rsp+arg_0], rbx
0x140001755  mov     [rsp+arg_8], rsi
0x14000175a  push    rdi
0x14000175b  sub     rsp, 20h
0x14000175f  mov     qword ptr [r9], 0
0x140001766  mov     rsi, r9
0x140001769  mov     rdi, rcx
0x14000176c  test    edx, edx
0x14000176e  jz      short loc_140001777
0x140001770  mov     eax, 8002000Bh
0x140001775  jmp     short loc_1400017A4
0x140001777  mov     ebx, [rcx+0Ch]
0x14000177a  call    cs:__imp_GetCurrentThreadId
0x140001780  cmp     eax, ebx
0x140001782  jz      short loc_14000178B
0x140001784  mov     eax, 8000FFFFh
0x140001789  jmp     short loc_1400017A4
0x14000178b  mov     rax, [rdi+38h]
0x14000178f  mov     [rsi], rax
0x140001792  mov     rcx, [rdi+38h]
0x140001796  mov     rax, [rcx]
0x140001799  mov     rax, [rax+8]
0x14000179d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400017a2  xor     eax, eax
0x1400017a4  mov     rbx, [rsp+28h+arg_0]
0x1400017a9  mov     rsi, [rsp+28h+arg_8]
0x1400017ae  add     rsp, 20h
0x1400017b2  pop     rdi
0x1400017b3  retn
```
