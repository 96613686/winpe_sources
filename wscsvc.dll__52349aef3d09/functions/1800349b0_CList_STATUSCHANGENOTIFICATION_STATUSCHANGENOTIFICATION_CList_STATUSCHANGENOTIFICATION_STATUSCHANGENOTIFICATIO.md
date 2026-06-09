# CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::~CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>(void)

- ea: `0x1800349b0`
- end: `0x1800349f9`
- name: `??1?$CList@PEAUSTATUSCHANGENOTIFICATION@@PEAU1@@@QEAA@XZ`
- size: `73`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180034a84`

## callees

- `0x1800221e8`
- `0x180023a90`
- `0x1800349b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800349e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800349e7`

## pseudocode

```c
void __fastcall CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::~CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>(
        _DWORD *a1)
{
  _DWORD *v1; // rbx
  __int64 HeadPosition; // rax

  v1 = a1;
  if ( *a1 )
  {
    while ( 1 )
    {
      HeadPosition = CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::GetHeadPosition(a1);
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
0x1800349b0  push    rbx
0x1800349b2  sub     rsp, 20h
0x1800349b6  cmp     dword ptr [rcx], 0
0x1800349b9  mov     rbx, rcx
0x1800349bc  jz      short loc_1800349F3
0x1800349be  jmp     short loc_1800349CE
0x1800349c0  mov     rdx, rax
0x1800349c3  mov     rcx, rbx
0x1800349c6  call    ?RemoveAt@?$CList@PEAVCExternalBase@@PEAV1@@@QEAAXPEAU_CListElement@@@Z; CList<CExternalBase *,CExternalBase *>::RemoveAt(_CListElement *)
0x1800349cb  mov     rcx, rbx
0x1800349ce  call    ?GetHeadPosition@?$CList@PEAUSTATUSCHANGENOTIFICATION@@PEAU1@@@QEBAPEAU_CListElement@@XZ; CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::GetHeadPosition(void)
0x1800349d3  test    rax, rax
0x1800349d6  jnz     short loc_1800349C0
0x1800349d8  lea     rax, [rbx+38h]
0x1800349dc  lea     rcx, [rbx+8]; lpCriticalSection
0x1800349e0  mov     [rax], rax
0x1800349e3  mov     [rbx+40h], rax
0x1800349e7  call    cs:__imp_DeleteCriticalSection
0x1800349ed  mov     dword ptr [rbx], 0
0x1800349f3  add     rsp, 20h
0x1800349f7  pop     rbx
0x1800349f8  retn
```
