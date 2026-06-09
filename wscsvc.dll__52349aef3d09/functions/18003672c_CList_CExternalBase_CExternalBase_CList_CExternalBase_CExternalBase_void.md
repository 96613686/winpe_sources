# CList<CExternalBase *,CExternalBase *>::~CList<CExternalBase *,CExternalBase *>(void)

- ea: `0x18003672c`
- end: `0x180036775`
- name: `??1?$CList@PEAVCExternalBase@@PEAV1@@@QEAA@XZ`
- size: `73`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003680c`

## callees

- `0x180009f40`
- `0x180023a90`
- `0x18003672c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036763`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036763`

## pseudocode

```c
void __fastcall CList<CExternalBase *,CExternalBase *>::~CList<CExternalBase *,CExternalBase *>(_DWORD *a1)
{
  _DWORD *v1; // rbx
  __int64 HeadPosition; // rax

  v1 = a1;
  if ( *a1 )
  {
    while ( 1 )
    {
      HeadPosition = CList<unsigned short *,unsigned short *>::GetHeadPosition(a1);
      if ( !HeadPosition )
        break;
      CList<CExternalBase *,CExternalBase *>::RemoveAt(v1, HeadPosition);
      a1 = v1;
    }
    *((_QWORD *)v1 + 7) = v1 + 14;
    *((_QWORD *)v1 + 8) = v1 + 14;
    DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 2));
    *v1 = 0;
  }
}

```

## disassembly

```asm
0x18003672c  push    rbx
0x18003672e  sub     rsp, 20h
0x180036732  cmp     dword ptr [rcx], 0
0x180036735  mov     rbx, rcx
0x180036738  jz      short loc_18003676F
0x18003673a  jmp     short loc_18003674A
0x18003673c  mov     rdx, rax
0x18003673f  mov     rcx, rbx
0x180036742  call    ?RemoveAt@?$CList@PEAVCExternalBase@@PEAV1@@@QEAAXPEAU_CListElement@@@Z; CList<CExternalBase *,CExternalBase *>::RemoveAt(_CListElement *)
0x180036747  mov     rcx, rbx
0x18003674a  call    ?GetHeadPosition@?$CList@PEAGPEAG@@QEBAPEAU_CListElement@@XZ; CList<ushort *,ushort *>::GetHeadPosition(void)
0x18003674f  test    rax, rax
0x180036752  jnz     short loc_18003673C
0x180036754  lea     rax, [rbx+38h]
0x180036758  lea     rcx, [rbx+8]; lpCriticalSection
0x18003675c  mov     [rax], rax
0x18003675f  mov     [rbx+40h], rax
0x180036763  call    cs:__imp_DeleteCriticalSection
0x180036769  mov     dword ptr [rbx], 0
0x18003676f  add     rsp, 20h
0x180036773  pop     rbx
0x180036774  retn
```
