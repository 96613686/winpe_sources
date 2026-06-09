# CControlProtocol::GetTypeTotalLength(ulong,ulong,ulong,ulong *,ulong *)

- ea: `0x18000c834`
- end: `0x18000c8b5`
- name: `?GetTypeTotalLength@CControlProtocol@@AEAAHKKKPEAK0@Z`
- size: `129`
- prototype: `__int64 __fastcall(CControlProtocol *this, int, unsigned int, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c190`
- `0x18000c8bc`

## callees

- `0x18000c834`

## pseudocode

```c
__int64 __fastcall CControlProtocol::GetTypeTotalLength(
        CControlProtocol *this,
        int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int *a6)
{
  unsigned int v6; // ecx
  unsigned __int64 v7; // rdx

  v6 = 0;
  switch ( a2 & 0xEFFFFFFF )
  {
    case 1u:
      a3 = 1;
      break;
    case 2u:
      a3 = 2;
      break;
    case 4u:
      a3 = 4;
      break;
    case 8u:
      a3 = 8;
      break;
    default:
      if ( !a3 )
        return v6;
      break;
  }
  if ( (a2 & 0x10000000) == 0 )
  {
    *a6 = a3;
    goto LABEL_17;
  }
  if ( a4 )
  {
    v7 = a4 * (unsigned __int64)a3;
    if ( v7 <= 0xFFFFFFFF )
    {
      *a6 = v7;
LABEL_17:
      v6 = 1;
      *a5 = a3;
      return v6;
    }
    *a6 = -1;
  }
  return v6;
}

```

## disassembly

```asm
0x18000c834  mov     r10, [rsp+arg_28]
0x18000c839  xor     ecx, ecx
0x18000c83b  mov     eax, edx
0x18000c83d  btr     eax, 1Ch
0x18000c841  lea     r11d, [rcx+1]
0x18000c845  sub     eax, r11d
0x18000c848  jz      short loc_18000C878
0x18000c84a  sub     eax, r11d
0x18000c84d  jz      short loc_18000C870
0x18000c84f  sub     eax, 2
0x18000c852  jz      short loc_18000C868
0x18000c854  cmp     eax, 4
0x18000c857  jz      short loc_18000C860
0x18000c859  test    r8d, r8d
0x18000c85c  jz      short loc_18000C8B2
0x18000c85e  jmp     short loc_18000C87B
0x18000c860  mov     r8d, 8
0x18000c866  jmp     short loc_18000C87B
0x18000c868  mov     r8d, 4
0x18000c86e  jmp     short loc_18000C87B
0x18000c870  mov     r8d, 2
0x18000c876  jmp     short loc_18000C87B
0x18000c878  mov     r8d, r11d
0x18000c87b  bt      edx, 1Ch
0x18000c87f  jnb     short loc_18000C8A4
0x18000c881  test    r9d, r9d
0x18000c884  jz      short loc_18000C8B2
0x18000c886  mov     eax, r9d
0x18000c889  mov     edx, r8d
0x18000c88c  imul    rdx, rax
0x18000c890  mov     eax, 0FFFFFFFFh
0x18000c895  cmp     rdx, rax
0x18000c898  ja      short loc_18000C89F
0x18000c89a  mov     [r10], edx
0x18000c89d  jmp     short loc_18000C8A7
0x18000c89f  mov     [r10], eax
0x18000c8a2  jmp     short loc_18000C8B2
0x18000c8a4  mov     [r10], r8d
0x18000c8a7  mov     rax, [rsp+arg_20]
0x18000c8ac  mov     ecx, r11d
0x18000c8af  mov     [rax], r8d
0x18000c8b2  mov     eax, ecx
0x18000c8b4  retn
```
