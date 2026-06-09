# ClusApi::Cluster::GetMaximumAccessForToken(void *,ulong *)

- ea: `0x180030b00`
- end: `0x180030b26`
- name: `?GetMaximumAccessForToken@Cluster@ClusApi@@UEAAJPEAXPEAK@Z`
- size: `38`
- prototype: `__int64 __fastcall(ClusApi::Cluster *__hidden this, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180030b00`

## import_xrefs

- `CLUSAPI!ClusterGetMaximumAccessForToken` at `0x180030b08`
- `CLUSAPI!ClusterGetMaximumAccessForToken` at `0x180030b08`

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
0x180030b00  sub     rsp, 28h
0x180030b04  mov     rcx, [rcx+18h]
0x180030b08  call    cs:__imp_ClusterGetMaximumAccessForToken
0x180030b0f  nop     dword ptr [rax+rax+00h]
0x180030b14  test    eax, eax
0x180030b16  jle     short loc_180030B20
0x180030b18  movzx   eax, ax
0x180030b1b  or      eax, 80070000h
0x180030b20  add     rsp, 28h
0x180030b24  retn
```
