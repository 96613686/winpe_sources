# ReadWS_IStream(WMPStream *,void *,unsigned __int64)

- ea: `0x18002ea90`
- end: `0x18002eac2`
- name: `?ReadWS_IStream@@YAJPEAUWMPStream@@PEAX_K@Z`
- size: `50`
- prototype: `__int64 __fastcall(struct WMPStream *, void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180045010`

## pseudocode

```c
__int64 __fastcall ReadWS_IStream(struct WMPStream *a1, void *a2, __int64 a3)
{
  __int64 v3; // rcx
  int v4; // eax
  unsigned int v5; // ecx
  int v7; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(_QWORD *)a1;
  v7 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, void *, __int64, int *))(*(_QWORD *)v3 + 24LL))(v3, a2, a3, &v7);
  v5 = 0;
  if ( v4 < 0 )
    return (unsigned int)-102;
  return v5;
}

```

## disassembly

```asm
0x18002ea90  sub     rsp, 38h
0x18002ea94  mov     rcx, [rcx]
0x18002ea97  lea     r9, [rsp+38h+arg_0]
0x18002ea9c  mov     [rsp+38h+arg_0], 0
0x18002eaa4  mov     rax, [rcx]
0x18002eaa7  mov     rax, [rax+18h]
0x18002eaab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eab0  xor     ecx, ecx
0x18002eab2  test    eax, eax
0x18002eab4  lea     edx, [rcx-66h]
0x18002eab7  cmovs   ecx, edx
0x18002eaba  mov     eax, ecx
0x18002eabc  add     rsp, 38h
0x18002eac0  retn
```
