# CASFExtendedContentDescObject::DeleteDesc(CASFExtendedContentDescObject::ECD_DESCRIPTOR *)

- ea: `0x18001aac0`
- end: `0x18001ab01`
- name: `?DeleteDesc@CASFExtendedContentDescObject@@IEAAXPEAUECD_DESCRIPTOR@1@@Z`
- size: `65`
- prototype: `void __fastcall(CASFExtendedContentDescObject *__hidden this, struct CASFExtendedContentDescObject::ECD_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180015d90`
- `0x180021f80`

## callees

- `0x180001194`
- `0x18001aac0`

## pseudocode

```c
void __fastcall CASFExtendedContentDescObject::DeleteDesc(
        CASFExtendedContentDescObject *this,
        struct CASFExtendedContentDescObject::ECD_DESCRIPTOR *a2)
{
  void *v2; // rcx
  void *v4; // rcx

  v2 = *(void **)((char *)a2 + 2);
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)((char *)a2 + 2) = 0;
  }
  v4 = *(void **)((char *)a2 + 14);
  if ( v4 )
  {
    operator delete(v4);
    *(_QWORD *)((char *)a2 + 14) = 0;
  }
  *((_WORD *)a2 + 6) = 0;
}

```

## disassembly

```asm
0x18001aac0  push    rbx
0x18001aac2  sub     rsp, 20h
0x18001aac6  mov     rcx, [rdx+2]; void *
0x18001aaca  mov     rbx, rdx
0x18001aacd  test    rcx, rcx
0x18001aad0  jz      short loc_18001AADF
0x18001aad2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001aad7  mov     qword ptr [rbx+2], 0
0x18001aadf  mov     rcx, [rbx+0Eh]; void *
0x18001aae3  test    rcx, rcx
0x18001aae6  jz      short loc_18001AAF5
0x18001aae8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001aaed  mov     qword ptr [rbx+0Eh], 0
0x18001aaf5  xor     eax, eax
0x18001aaf7  mov     [rbx+0Ch], ax
0x18001aafb  add     rsp, 20h
0x18001aaff  pop     rbx
0x18001ab00  retn
```
