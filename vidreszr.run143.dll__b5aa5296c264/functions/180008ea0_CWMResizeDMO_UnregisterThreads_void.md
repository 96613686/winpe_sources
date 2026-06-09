# CWMResizeDMO::UnregisterThreads(void)

- ea: `0x180008ea0`
- end: `0x180008ec9`
- name: `?UnregisterThreads@CWMResizeDMO@@UEAAJXZ`
- size: `41`
- prototype: `__int64 __fastcall(CWMResizeDMO *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008ea0`

## pseudocode

```c
__int64 __fastcall CWMResizeDMO::UnregisterThreads(CWMResizeDMO *this)
{
  __int64 v1; // rax
  __int64 v2; // rax

  v1 = *((_QWORD *)this + 11);
  *((_DWORD *)this + 194) = 0;
  if ( v1 )
    *(_DWORD *)(v1 + 204) = 0;
  v2 = *((_QWORD *)this + 9);
  if ( v2 )
    *(_DWORD *)(v2 + 204) = 0;
  return 0;
}

```

## disassembly

```asm
0x180008ea0  mov     rax, [rcx+58h]
0x180008ea4  xor     edx, edx
0x180008ea6  mov     [rcx+308h], edx
0x180008eac  test    rax, rax
0x180008eaf  jz      short loc_180008EB7
0x180008eb1  mov     [rax+0CCh], edx
0x180008eb7  mov     rax, [rcx+48h]
0x180008ebb  test    rax, rax
0x180008ebe  jz      short loc_180008EC6
0x180008ec0  mov     [rax+0CCh], edx
0x180008ec6  xor     eax, eax
0x180008ec8  retn
```
