# VmFindNextDynamicExtension(void *,void *,void * *)

- ea: `0x140003fa0`
- end: `0x140003fe7`
- name: `?VmFindNextDynamicExtension@@YAPEAXPEAX0PEAPEAX@Z`
- size: `71`
- prototype: `void *__fastcall(void *, void *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003fa0`

## pseudocode

```c
__int64 *__fastcall VmFindNextDynamicExtension(char *a1, _QWORD *a2, void **a3)
{
  __int64 **v3; // r9
  __int64 *v4; // rax
  void *v5; // rdx

  *a3 = 0;
  v3 = (__int64 **)(a1 + 208);
  if ( a2 )
    v4 = (__int64 *)a2[4];
  else
    v4 = *v3;
  while ( v4 != (__int64 *)v3 )
  {
    if ( *((_BYTE *)v4 + 394) )
    {
      v5 = (void *)v4[50];
      if ( v5 )
      {
        *a3 = v5;
        return v4 - 4;
      }
    }
    v4 = (__int64 *)*v4;
  }
  return 0;
}

```

## disassembly

```asm
0x140003fa0  mov     qword ptr [r8], 0
0x140003fa7  lea     r9, [rcx+0D0h]
0x140003fae  test    rdx, rdx
0x140003fb1  jnz     short loc_140003FB8
0x140003fb3  mov     rax, [r9]
0x140003fb6  jmp     short loc_140003FBC
0x140003fb8  mov     rax, [rdx+20h]
0x140003fbc  cmp     rax, r9
0x140003fbf  jz      short loc_140003FE4
0x140003fc1  cmp     byte ptr [rax+18Ah], 0
0x140003fc8  jz      short loc_140003FD6
0x140003fca  mov     rdx, [rax+190h]
0x140003fd1  test    rdx, rdx
0x140003fd4  jnz     short loc_140003FDB
0x140003fd6  mov     rax, [rax]
0x140003fd9  jmp     short loc_140003FBC
0x140003fdb  mov     [r8], rdx
0x140003fde  add     rax, 0FFFFFFFFFFFFFFE0h
0x140003fe2  retn
0x140003fe4  xor     eax, eax
0x140003fe6  retn
```
