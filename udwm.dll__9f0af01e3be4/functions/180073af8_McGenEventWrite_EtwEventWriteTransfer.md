# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180073af8`
- end: `0x180073b45`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `53`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005d80`
- `0x180007368`
- `0x180007e64`
- `0x180012018`
- `0x18001d710`
- `0x18001dec0`
- `0x18001e100`
- `0x18001f680`
- `0x18002e7ac`
- `0x180037ac8`
- `0x180037e98`
- `0x18003adc0`
- `0x18003dd18`
- `0x18003deb8`
- `0x18003e410`
- `0x180047524`
- `0x180074088`
- `0x1800744b0`
- `0x180080a98`
- `0x1800884a0`
- `0x180088af0`
- `0x180088c1c`
- `0x180089e80`
- `0x18008a06c`
- `0x18008a8b4`
- `0x18008a910`
- `0x18009d228`
- `0x18009d3d8`
- `0x18009db84`
- `0x18009dbd8`
- `0x18009dc40`
- `0x18009e0ac`
- `0x18009ecb4`
- `0x18009f014`
- `0x18009f308`
- `0x1800afdd8`
- `0x1800b0230`
- `0x1800b12b4`
- `0x1800bb35c`
- `0x1800be64c`
- `0x1800be9c0`
- `0x1800c1ad4`
- `0x1800c1e04`
- `0x1800c3ed0`
- `0x1800c8ed4`
- `0x1800c9380`
- `0x1800c9430`
- `0x1800cc8a0`
- `0x1800cf99c`
- `0x1800cfa80`

## callees

- `0x180073af8`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180073b3a`
- `ntdll!EtwEventWriteTransfer` at `0x180073b3a`

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
0x180073af8  sub     rsp, 38h
0x180073afc  mov     r8, [rcx+8]
0x180073b00  mov     rax, [rsp+38h+arg_20]
0x180073b05  test    r8, r8
0x180073b08  jnz     short loc_180073B12
0x180073b0a  mov     [rax], r8
0x180073b0d  xor     r10d, r10d
0x180073b10  jmp     short loc_180073B1F
0x180073b12  mov     [rax], r8
0x180073b15  mov     r10d, 2
0x180073b1b  movzx   r8d, word ptr [r8]
0x180073b1f  mov     [rax+8], r8d
0x180073b23  xor     r8d, r8d
0x180073b26  mov     [rsp+38h+var_10], rax
0x180073b2b  mov     [rax+0Ch], r10d
0x180073b2f  mov     rcx, [rcx]
0x180073b32  mov     [rsp+38h+var_18], r9d
0x180073b37  xor     r9d, r9d
0x180073b3a  call    cs:__imp_EtwEventWriteTransfer
0x180073b40  add     rsp, 38h
0x180073b44  retn
```
