# CWdsDeviceQuery::Shutdown(void)

- ea: `0x18000c3c4`
- end: `0x18000c3fe`
- name: `?Shutdown@CWdsDeviceQuery@@QEAAXXZ`
- size: `58`
- prototype: `void __fastcall(CWdsDeviceQuery *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006210`
- `0x180006320`
- `0x180006460`
- `0x180006598`
- `0x18000c344`

## callees

- `0x1800015d4`
- `0x180009390`
- `0x18000c3c4`

## pseudocode

```c
void __fastcall CWdsDeviceQuery::Shutdown(CWdsDeviceQuery *this)
{
  void *v2; // rcx

  if ( *((_DWORD *)this + 20) == 2 )
  {
    v2 = *(void **)this;
    if ( v2 )
    {
      operator delete(v2);
      *(_QWORD *)this = 0;
    }
  }
  CWdsMetadata::Clear((CWdsDeviceQuery *)((char *)this + 8));
  *((_DWORD *)this + 20) = 0;
}

```

## disassembly

```asm
0x18000c3c4  push    rbx
0x18000c3c6  sub     rsp, 20h
0x18000c3ca  cmp     dword ptr [rcx+50h], 2
0x18000c3ce  mov     rbx, rcx
0x18000c3d1  jnz     short loc_18000C3E7
0x18000c3d3  mov     rcx, [rcx]; Block
0x18000c3d6  test    rcx, rcx
0x18000c3d9  jz      short loc_18000C3E7
0x18000c3db  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c3e0  mov     qword ptr [rbx], 0
0x18000c3e7  lea     rcx, [rbx+8]; this
0x18000c3eb  call    ?Clear@CWdsMetadata@@QEAAKXZ; CWdsMetadata::Clear(void)
0x18000c3f0  mov     dword ptr [rbx+50h], 0
0x18000c3f7  add     rsp, 20h
0x18000c3fb  pop     rbx
0x18000c3fc  retn
```
