# CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)

- ea: `0x18001210c`
- end: `0x18001213d`
- name: `?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z`
- size: `49`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180010c24`
- `0x180010c74`
- `0x180012890`
- `0x180013b90`
- `0x180013ca0`
- `0x1800150d0`
- `0x180015134`
- `0x1800151c8`
- `0x1800152b4`

## callees

- `0x180011cb4`
- `0x18001210c`

## pseudocode

```c
__int64 __fastcall CControlPacket::GetULONG(
        CControlPacket *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int *a5)
{
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-28h]
  unsigned int *v7; // [rsp+30h] [rbp-18h] BYREF

  v7 = 0;
  result = CControlPacket::GetVariable<unsigned long>(this, a2, a3, a4, v6, (__int64)&v7);
  if ( !(_DWORD)result )
    *a5 = *v7;
  return result;
}

```

## disassembly

```asm
0x18001210c  sub     rsp, 48h
0x180012110  and     [rsp+48h+var_18], 0
0x180012116  lea     rax, [rsp+48h+var_18]
0x18001211b  mov     [rsp+48h+var_20], rax
0x180012120  call    ??$GetVariable@K@CControlPacket@@QEAAKPEBG0KKPEAPEAK@Z; CControlPacket::GetVariable<ulong>(ushort const *,ushort const *,ulong,ulong,ulong * *)
0x180012125  test    eax, eax
0x180012127  jnz     short loc_180012137
0x180012129  mov     rcx, [rsp+48h+var_18]
0x18001212e  mov     edx, [rcx]
0x180012130  mov     rcx, [rsp+48h+arg_20]
0x180012135  mov     [rcx], edx
0x180012137  add     rsp, 48h
0x18001213b  retn
```
