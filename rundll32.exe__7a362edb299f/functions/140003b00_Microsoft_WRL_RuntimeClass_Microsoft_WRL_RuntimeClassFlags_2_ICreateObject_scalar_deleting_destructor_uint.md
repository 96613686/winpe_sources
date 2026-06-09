# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICreateObject>::`scalar deleting destructor'(uint)

- ea: `0x140003b00`
- end: `0x140003b28`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICreateObject@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001260`
- `0x140003b00`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICreateObject>::`scalar deleting destructor'(
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
0x140003b00  push    rbx
0x140003b02  sub     rsp, 20h
0x140003b06  mov     dword ptr [rcx+0Ch], 0C0000001h
0x140003b0d  mov     rbx, rcx
0x140003b10  test    dl, 1
0x140003b13  jz      short loc_140003B1F
0x140003b15  mov     edx, 10h; unsigned __int64
0x140003b1a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003b1f  mov     rax, rbx
0x140003b22  add     rsp, 20h
0x140003b26  pop     rbx
0x140003b27  retn
```
