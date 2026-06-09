# CWdsMetadataEntry::Shutdown(void)

- ea: `0x18000a380`
- end: `0x18000a3e9`
- name: `?Shutdown@CWdsMetadataEntry@@QEAAXXZ`
- size: `105`
- prototype: `void __fastcall(CWdsMetadataEntry *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000ac50`
- `0x18000b47c`
- `0x18000ba74`
- `0x18000c4e0`
- `0x18000d40c`
- `0x18001170c`
- `0x1800125c0`

## callees

- `0x180009838`
- `0x18000a380`
- `0x1800150b8`

## pseudocode

```c
void __fastcall CWdsMetadataEntry::Shutdown(CWdsMetadataEntry *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v2 = *(void **)this;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)this = 0;
  }
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 1) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    operator delete(v4);
    *((_QWORD *)this + 2) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
  {
    operator delete(v5);
    *((_QWORD *)this + 3) = 0;
  }
  *((_DWORD *)this + 8) = 0;
  *((_DWORD *)this + 9) = 0;
  CWdsMetadataValue::Shutdown((CWdsMetadataEntry *)((char *)this + 40));
}

```

## disassembly

```asm
0x18000a380  push    rbx
0x18000a382  sub     rsp, 20h
0x18000a386  mov     rbx, rcx
0x18000a389  mov     rcx, [rcx]; Block
0x18000a38c  test    rcx, rcx
0x18000a38f  jz      short loc_18000A39A
0x18000a391  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a396  and     qword ptr [rbx], 0
0x18000a39a  mov     rcx, [rbx+8]; Block
0x18000a39e  test    rcx, rcx
0x18000a3a1  jz      short loc_18000A3AD
0x18000a3a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a3a8  and     qword ptr [rbx+8], 0
0x18000a3ad  mov     rcx, [rbx+10h]; Block
0x18000a3b1  test    rcx, rcx
0x18000a3b4  jz      short loc_18000A3C0
0x18000a3b6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a3bb  and     qword ptr [rbx+10h], 0
0x18000a3c0  mov     rcx, [rbx+18h]; Block
0x18000a3c4  test    rcx, rcx
0x18000a3c7  jz      short loc_18000A3D3
0x18000a3c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a3ce  and     qword ptr [rbx+18h], 0
0x18000a3d3  and     dword ptr [rbx+20h], 0
0x18000a3d7  lea     rcx, [rbx+28h]; this
0x18000a3db  and     dword ptr [rbx+24h], 0
0x18000a3df  add     rsp, 20h
0x18000a3e3  pop     rbx
0x18000a3e4  jmp     ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
```
