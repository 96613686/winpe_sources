# CControlPacket::GetHANDLE(ushort const *,ushort const *,ulong,void * *)

- ea: `0x180020b98`
- end: `0x180020bca`
- name: `?GetHANDLE@CControlPacket@@QEAAKPEBG0KPEAPEAX@Z`
- size: `50`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800067f0`
- `0x180006f84`
- `0x1800071a0`
- `0x180007278`
- `0x180007358`
- `0x1800074bc`
- `0x180007668`
- `0x1800077b0`
- `0x1800078a8`
- `0x180021d80`

## callees

- `0x180020ab0`
- `0x180020b98`

## pseudocode

```c
unsigned int __fastcall CControlPacket::GetHANDLE(
        CControlPacket *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  unsigned int result; // eax
  unsigned __int64 v6[3]; // [rsp+30h] [rbp-18h] BYREF

  v6[0] = 0;
  result = CControlPacket::GetULONG64(this, a2, a3, 0, v6);
  if ( !result )
    *a5 = (void *)v6[0];
  return result;
}

```

## disassembly

```asm
0x180020b98  sub     rsp, 48h
0x180020b9c  and     [rsp+48h+var_18], 0
0x180020ba2  lea     rax, [rsp+48h+var_18]
0x180020ba7  xor     r9d, r9d; unsigned int
0x180020baa  mov     [rsp+48h+var_28], rax; unsigned __int64 *
0x180020baf  call    ?GetULONG64@CControlPacket@@QEAAKPEBG0KPEA_K@Z; CControlPacket::GetULONG64(ushort const *,ushort const *,ulong,unsigned __int64 *)
0x180020bb4  test    eax, eax
0x180020bb6  jnz     short loc_180020BC5
0x180020bb8  mov     rdx, [rsp+48h+arg_20]
0x180020bbd  mov     rcx, [rsp+48h+var_18]
0x180020bc2  mov     [rdx], rcx
0x180020bc5  add     rsp, 48h
0x180020bc9  retn
```
