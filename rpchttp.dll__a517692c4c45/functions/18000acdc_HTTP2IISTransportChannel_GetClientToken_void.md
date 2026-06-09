# HTTP2IISTransportChannel::GetClientToken(void)

- ea: `0x18000acdc`
- end: `0x18000ad2a`
- name: `?GetClientToken@HTTP2IISTransportChannel@@QEAAPEAXXZ`
- size: `78`
- prototype: `void *__fastcall(HTTP2IISTransportChannel *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002770`
- `0x180002874`

## callees

- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2IISTransportChannel::GetClientToken(HTTP2IISTransportChannel *this)
{
  __int64 v1; // rcx
  int v2; // eax
  __int64 v3; // rcx
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 8);
  v5 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, _QWORD, _QWORD))(v1 + 184))(
         *(_QWORD *)(v1 + 8),
         1011,
         &v5,
         0,
         0);
  v3 = v5;
  if ( !v2 )
    return -1;
  return v3;
}

```

## disassembly

```asm
0x18000acdc  sub     rsp, 38h
0x18000ace0  mov     rcx, [rcx+40h]
0x18000ace4  lea     r8, [rsp+38h+arg_0]
0x18000ace9  mov     [rsp+38h+arg_0], 0
0x18000acf2  xor     r9d, r9d
0x18000acf5  mov     edx, 3F3h
0x18000acfa  mov     [rsp+38h+var_18], 0
0x18000ad03  mov     rax, [rcx+0B8h]
0x18000ad0a  mov     rcx, [rcx+8]
0x18000ad0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad13  mov     rcx, [rsp+38h+arg_0]
0x18000ad18  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ad1c  test    eax, eax
0x18000ad1e  cmovz   rcx, rdx
0x18000ad22  mov     rax, rcx
0x18000ad25  add     rsp, 38h
0x18000ad29  retn
```
