# WriteWS_IStream(WMPStream *,void const *,unsigned __int64)

- ea: `0x18002eed0`
- end: `0x18002ef0b`
- name: `?WriteWS_IStream@@YAJPEAUWMPStream@@PEBX_K@Z`
- size: `59`
- prototype: `__int64 __fastcall(struct WMPStream *, const void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180045010`

## pseudocode

```c
__int64 __fastcall WriteWS_IStream(struct WMPStream *a1, const void *a2, __int64 a3)
{
  __int64 v3; // rcx
  int v6; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(_QWORD *)a1;
  v6 = 0;
  (*(void (__fastcall **)(__int64, const void *, __int64, int *))(*(_QWORD *)v3 + 32LL))(v3, a2, a3, &v6);
  return v6 != a3 ? 0xFFFFFF9A : 0;
}

```

## disassembly

```asm
0x18002eed0  push    rbx
0x18002eed2  sub     rsp, 30h
0x18002eed6  mov     rcx, [rcx]
0x18002eed9  lea     r9, [rsp+38h+arg_0]
0x18002eede  mov     [rsp+38h+arg_0], 0
0x18002eee6  mov     rbx, r8
0x18002eee9  mov     rax, [rcx]
0x18002eeec  mov     rax, [rax+20h]
0x18002eef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eef5  mov     eax, [rsp+38h+arg_0]
0x18002eef9  sub     rbx, rax
0x18002eefc  neg     rbx
0x18002eeff  sbb     eax, eax
0x18002ef01  and     eax, 0FFFFFF9Ah
0x18002ef04  add     rsp, 30h
0x18002ef08  pop     rbx
0x18002ef09  retn
```
