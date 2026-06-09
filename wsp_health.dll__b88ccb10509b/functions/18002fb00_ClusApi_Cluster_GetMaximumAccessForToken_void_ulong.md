# ClusApi::Cluster::GetMaximumAccessForToken(void *,ulong *)

- ea: `0x18002fb00`
- end: `0x18002fb1f`
- name: `?GetMaximumAccessForToken@Cluster@ClusApi@@UEAAJPEAXPEAK@Z`
- size: `31`
- prototype: `__int64 __fastcall(ClusApi::Cluster *__hidden this, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002fb00`

## import_xrefs

- `CLUSAPI!ClusterGetMaximumAccessForToken` at `0x18002fb08`
- `CLUSAPI!ClusterGetMaximumAccessForToken` at `0x18002fb08`

## pseudocode

```c
__int64 __fastcall ClusApi::Cluster::GetMaximumAccessForToken(ClusApi::Cluster *this, void *a2, unsigned int *a3)
{
  __int64 result; // rax

  result = ClusterGetMaximumAccessForToken(*((_QWORD *)this + 3), a2, a3);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002fb00  sub     rsp, 28h
0x18002fb04  mov     rcx, [rcx+18h]
0x18002fb08  call    cs:__imp_ClusterGetMaximumAccessForToken
0x18002fb0e  test    eax, eax
0x18002fb10  jle     short loc_18002FB1A
0x18002fb12  movzx   eax, ax
0x18002fb15  or      eax, 80070000h
0x18002fb1a  add     rsp, 28h
0x18002fb1e  retn
```
