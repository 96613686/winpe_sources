# Microsoft::WRL::SimpleClassFactory<CCreateObjectLocalServer,0>::`scalar deleting destructor'(uint)

- ea: `0x140003b30`
- end: `0x140003b58`
- name: `??_G?$SimpleClassFactory@VCCreateObjectLocalServer@@$0A@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001260`
- `0x140003b30`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::SimpleClassFactory<CCreateObjectLocalServer,0>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[3] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140003b30  push    rbx
0x140003b32  sub     rsp, 20h
0x140003b36  mov     dword ptr [rcx+0Ch], 0C0000001h
0x140003b3d  mov     rbx, rcx
0x140003b40  test    dl, 1
0x140003b43  jz      short loc_140003B4F
0x140003b45  mov     edx, 18h; unsigned __int64
0x140003b4a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003b4f  mov     rax, rbx
0x140003b52  add     rsp, 20h
0x140003b56  pop     rbx
0x140003b57  retn
```
