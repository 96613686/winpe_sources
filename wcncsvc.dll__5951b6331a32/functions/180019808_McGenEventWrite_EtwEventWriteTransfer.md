# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180019808`
- end: `0x180019855`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800157bc`
- `0x180017054`
- `0x180018204`
- `0x180018804`
- `0x18003eb28`
- `0x1800441f4`
- `0x1800535b8`
- `0x18005379c`

## callees

- `0x180019808`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18001984a`
- `ntdll!EtwEventWriteTransfer` at `0x18001984a`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(_QWORD *a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    *(_QWORD *)a5 = v5;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    *(_QWORD *)a5 = 0;
    v6 = 0;
  }
  *(_DWORD *)(a5 + 8) = (_DWORD)v5;
  *(_DWORD *)(a5 + 12) = v6;
  return EtwEventWriteTransfer(*a1, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x180019808  sub     rsp, 38h
0x18001980c  mov     r8, [rcx+8]
0x180019810  mov     rax, [rsp+38h+arg_20]
0x180019815  test    r8, r8
0x180019818  jnz     short loc_180019822
0x18001981a  mov     [rax], r8
0x18001981d  xor     r10d, r10d
0x180019820  jmp     short loc_18001982F
0x180019822  mov     [rax], r8
0x180019825  mov     r10d, 2
0x18001982b  movzx   r8d, word ptr [r8]
0x18001982f  mov     [rax+8], r8d
0x180019833  xor     r8d, r8d
0x180019836  mov     [rsp+38h+var_10], rax
0x18001983b  mov     [rax+0Ch], r10d
0x18001983f  mov     rcx, [rcx]
0x180019842  mov     [rsp+38h+var_18], r9d
0x180019847  xor     r9d, r9d
0x18001984a  call    cs:__imp_EtwEventWriteTransfer
0x180019850  add     rsp, 38h
0x180019854  retn
```
