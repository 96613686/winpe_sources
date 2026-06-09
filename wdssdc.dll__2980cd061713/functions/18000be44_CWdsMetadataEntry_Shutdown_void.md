# CWdsMetadataEntry::Shutdown(void)

- ea: `0x18000be44`
- end: `0x18000beb9`
- name: `?Shutdown@CWdsMetadataEntry@@QEAAXXZ`
- size: `117`
- prototype: `void __fastcall(CWdsMetadataEntry *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180009194`
- `0x180009300`
- `0x18000b960`

## callees

- `0x1800015d4`
- `0x18000be44`
- `0x18000bec0`

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
  *((_QWORD *)this + 4) = 0;
  CWdsMetadataValue::Shutdown((CWdsMetadataEntry *)((char *)this + 40));
}

```

## disassembly

```asm
0x18000be44  push    rbx
0x18000be46  sub     rsp, 20h
0x18000be4a  mov     rbx, rcx
0x18000be4d  mov     rcx, [rcx]; Block
0x18000be50  test    rcx, rcx
0x18000be53  jz      short loc_18000BE61
0x18000be55  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000be5a  mov     qword ptr [rbx], 0
0x18000be61  mov     rcx, [rbx+8]; Block
0x18000be65  test    rcx, rcx
0x18000be68  jz      short loc_18000BE77
0x18000be6a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000be6f  mov     qword ptr [rbx+8], 0
0x18000be77  mov     rcx, [rbx+10h]; Block
0x18000be7b  test    rcx, rcx
0x18000be7e  jz      short loc_18000BE8D
0x18000be80  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000be85  mov     qword ptr [rbx+10h], 0
0x18000be8d  mov     rcx, [rbx+18h]; Block
0x18000be91  test    rcx, rcx
0x18000be94  jz      short loc_18000BEA3
0x18000be96  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000be9b  mov     qword ptr [rbx+18h], 0
0x18000bea3  lea     rcx, [rbx+28h]; this
0x18000bea7  mov     qword ptr [rbx+20h], 0
0x18000beaf  add     rsp, 20h
0x18000beb3  pop     rbx
0x18000beb4  jmp     ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
```
