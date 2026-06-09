# WinHvpSetProximityDomain

- ea: `0x140004408`
- end: `0x140004456`
- name: `WinHvpSetProximityDomain`
- size: `78`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140008ef0`
- `0x14001d900`
- `0x14001ffd0`
- `0x1400231a4`
- `0x140023820`
- `0x1400243d0`
- `0x140024570`
- `0x140026070`
- `0x1400261c0`

## callees

- `0x140004408`

## pseudocode

```c
int __fastcall WinHvpSetProximityDomain(__int64 a1, int a2)
{
  __int64 v2; // rax
  unsigned int v3; // edx

  *(_QWORD *)a1 = 0;
  v2 = (unsigned int)a2;
  LODWORD(v2) = a2 & 0x7FFFFFFF;
  if ( (a2 & 0x7FFFFFFFu) < WinHvpNodeCount )
  {
    v2 = WinHvpNodeInfo + 40 * v2;
    if ( *(_BYTE *)(v2 + 4) )
    {
      if ( v2 )
      {
        if ( a2 >= 0 )
        {
          v3 = 0x80000000;
        }
        else
        {
          *(_DWORD *)(a1 + 4) = 1;
          v3 = -2147483647;
        }
        LODWORD(v2) = *(_DWORD *)v2;
        *(_DWORD *)a1 = v2;
        *(_DWORD *)(a1 + 4) = v3;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140004408  xor     eax, eax
0x14000440a  mov     [rcx], rax
0x14000440d  mov     eax, edx
0x14000440f  btr     eax, 1Fh
0x140004413  cmp     eax, cs:WinHvpNodeCount
0x140004419  jnb     short locret_140004435
0x14000441b  lea     r8, [rax+rax*4]
0x14000441f  mov     rax, cs:WinHvpNodeInfo
0x140004426  lea     rax, [rax+r8*8]
0x14000442a  cmp     byte ptr [rax+4], 0
0x14000442e  jz      short locret_140004435
0x140004430  test    rax, rax
0x140004433  jnz     short loc_140004437
0x140004435  retn
0x140004437  test    edx, edx
0x140004439  jns     short loc_140004449
0x14000443b  mov     dword ptr [rcx+4], 1
0x140004442  mov     edx, 80000001h
0x140004447  jmp     short loc_14000444E
0x140004449  mov     edx, 80000000h
0x14000444e  mov     eax, [rax]
0x140004450  mov     [rcx], eax
0x140004452  mov     [rcx+4], edx
0x140004455  retn
```
