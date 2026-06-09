# _dynamic_atexit_destructor_for__CShareableObjectManager::m_sharedObjectManager__

- ea: `0x180101000`
- end: `0x180101043`
- name: `_dynamic_atexit_destructor_for__CShareableObjectManager::m_sharedObjectManager__`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800034d4`
- `0x18004c5d8`
- `0x180101000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180101037`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180101037`

## pseudocode

```c
void dynamic_atexit_destructor_for__CShareableObjectManager::m_sharedObjectManager__()
{
  CWideStringHash *v0; // rbx

  v0 = qword_180150CF8;
  if ( qword_180150CF8 )
  {
    CWideStringHash::~CWideStringHash(qword_180150CF8);
    operator delete(v0, 0x10u);
  }
  if ( dword_180150CF0 )
    DeleteCriticalSection(&CShareableObjectManager::m_sharedObjectManager);
}

```

## disassembly

```asm
0x180101000  push    rbx
0x180101002  sub     rsp, 20h
0x180101006  mov     rbx, cs:qword_180150CF8
0x18010100d  test    rbx, rbx
0x180101010  jz      short loc_180101027
0x180101012  mov     rcx, rbx; this
0x180101015  call    ??1CWideStringHash@@QEAA@XZ; CWideStringHash::~CWideStringHash(void)
0x18010101a  mov     edx, 10h; unsigned __int64
0x18010101f  mov     rcx, rbx; void *
0x180101022  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180101027  cmp     cs:dword_180150CF0, 0
0x18010102e  jz      short loc_18010103D
0x180101030  lea     rcx, ?m_sharedObjectManager@CShareableObjectManager@@0V1@A; lpCriticalSection
0x180101037  call    cs:__imp_DeleteCriticalSection
0x18010103d  add     rsp, 20h
0x180101041  pop     rbx
0x180101042  retn
```
