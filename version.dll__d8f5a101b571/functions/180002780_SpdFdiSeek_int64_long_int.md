# SpdFdiSeek(__int64,long,int)

- ea: `0x180002780`
- end: `0x1800027a9`
- name: `?SpdFdiSeek@@YAJ_JJH@Z`
- size: `41`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002780`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002795`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002795`
- `KERNEL32!_llseek` at `0x180002784`
- `KERNEL32!_llseek` at `0x180002784`

## pseudocode

```c
LONG __fastcall SpdFdiSeek(HFILE a1, LONG a2, int a3)
{
  LONG result; // eax

  result = _llseek(a1, a2, a3);
  if ( result == -1 )
  {
    *(_DWORD *)TlsGetValue(itlsDiamondContext) = -1;
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x180002780  sub     rsp, 28h
0x180002784  call    cs:__imp__llseek
0x18000278a  cmp     eax, 0FFFFFFFFh
0x18000278d  jnz     short loc_1800027A4
0x18000278f  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002795  call    cs:__imp_TlsGetValue
0x18000279b  mov     dword ptr [rax], 0FFFFFFFFh
0x1800027a1  or      eax, 0FFFFFFFFh
0x1800027a4  add     rsp, 28h
0x1800027a8  retn
```
