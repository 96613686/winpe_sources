# SpdFdiWrite(__int64,void *,uint)

- ea: `0x1800027b0`
- end: `0x180002810`
- name: `?SpdFdiWrite@@YAI_JPEAXI@Z`
- size: `96`
- prototype: `unsigned int __fastcall(__int64, void *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800027b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027ca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800027e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800027f6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800027e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800027f6`
- `KERNEL32!_lwrite` at `0x1800027bd`
- `KERNEL32!_lwrite` at `0x1800027bd`

## pseudocode

```c
__int64 __fastcall SpdFdiWrite(HFILE a1, const CHAR *a2, UINT a3)
{
  UINT v4; // edi
  int v5; // ebx
  _DWORD *Value; // rax

  v4 = _lwrite(a1, a2, a3);
  if ( v4 == -1 )
  {
    v5 = -4;
    if ( GetLastError() != 112 )
      v5 = -2;
    Value = TlsGetValue(itlsDiamondContext);
    goto LABEL_7;
  }
  if ( v4 != a3 )
  {
    Value = TlsGetValue(itlsDiamondContext);
    v5 = -4;
LABEL_7:
    *Value = v5;
  }
  return v4;
}

```

## disassembly

```asm
0x1800027b0  mov     [rsp+arg_0], rbx
0x1800027b5  push    rdi
0x1800027b6  sub     rsp, 20h
0x1800027ba  mov     ebx, r8d
0x1800027bd  call    cs:__imp__lwrite
0x1800027c3  mov     edi, eax
0x1800027c5  cmp     eax, 0FFFFFFFFh
0x1800027c8  jnz     short loc_1800027EC
0x1800027ca  call    cs:__imp_GetLastError
0x1800027d0  mov     ebx, 0FFFFFFFCh
0x1800027d5  cmp     eax, 70h ; 'p'
0x1800027d8  lea     ecx, [rbx+2]
0x1800027db  cmovnz  ebx, ecx
0x1800027de  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x1800027e4  call    cs:__imp_TlsGetValue
0x1800027ea  jmp     short loc_180002801
0x1800027ec  cmp     edi, ebx
0x1800027ee  jz      short loc_180002803
0x1800027f0  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x1800027f6  call    cs:__imp_TlsGetValue
0x1800027fc  mov     ebx, 0FFFFFFFCh
0x180002801  mov     [rax], ebx
0x180002803  mov     rbx, [rsp+28h+arg_0]
0x180002808  mov     eax, edi
0x18000280a  add     rsp, 20h
0x18000280e  pop     rdi
0x18000280f  retn
```
