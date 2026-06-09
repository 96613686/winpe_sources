# CBlkRange::Copy(_WDSMC_BLOCK_RANGE *,ulong,int)

- ea: `0x18001c2ac`
- end: `0x18001c310`
- name: `?Copy@CBlkRange@@QEBAKPEAU_WDSMC_BLOCK_RANGE@@KH@Z`
- size: `100`
- prototype: `unsigned int __fastcall(CBlkRange *__hidden this, struct _WDSMC_BLOCK_RANGE *, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001dd2c`

## callees

- `0x18001c2ac`
- `0x180023b28`

## pseudocode

```c
__int64 __fastcall CBlkRange::Copy(CBlkRange *this, struct _WDSMC_BLOCK_RANGE *a2, unsigned int a3)
{
  _QWORD *v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // rdi

  if ( a3 >= *((_DWORD *)this + 256) )
    a3 = *((_DWORD *)this + 256);
  if ( a3 )
  {
    v3 = (_QWORD *)((char *)a2 + 8);
    v4 = a3;
    v5 = this - a2;
    do
    {
      *(v3 - 1) = CNetworkAddress::HostToNetworkByteOrder(*(_QWORD *)((char *)v3 + v5 - 8));
      *v3 = CNetworkAddress::HostToNetworkByteOrder(*(_QWORD *)((char *)v3 + v5));
      v3 += 2;
      --v4;
    }
    while ( v4 );
  }
  return 0;
}

```

## disassembly

```asm
0x18001c2ac  mov     [rsp+arg_0], rbx
0x18001c2b1  mov     [rsp+arg_8], rsi
0x18001c2b6  push    rdi
0x18001c2b7  sub     rsp, 20h
0x18001c2bb  mov     eax, [rcx+400h]
0x18001c2c1  mov     rdi, rcx
0x18001c2c4  cmp     r8d, eax
0x18001c2c7  cmovnb  r8d, eax
0x18001c2cb  test    r8d, r8d
0x18001c2ce  jz      short loc_18001C2FE
0x18001c2d0  lea     rbx, [rdx+8]
0x18001c2d4  mov     esi, r8d
0x18001c2d7  sub     rdi, rdx
0x18001c2da  mov     rcx, [rdi+rbx-8]; unsigned __int64
0x18001c2df  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001c2e4  mov     [rbx-8], rax
0x18001c2e8  mov     rcx, [rdi+rbx]; unsigned __int64
0x18001c2ec  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001c2f1  mov     [rbx], rax
0x18001c2f4  lea     rbx, [rbx+10h]
0x18001c2f8  sub     rsi, 1
0x18001c2fc  jnz     short loc_18001C2DA
0x18001c2fe  mov     rbx, [rsp+28h+arg_0]
0x18001c303  xor     eax, eax
0x18001c305  mov     rsi, [rsp+28h+arg_8]
0x18001c30a  add     rsp, 20h
0x18001c30e  pop     rdi
0x18001c30f  retn
```
