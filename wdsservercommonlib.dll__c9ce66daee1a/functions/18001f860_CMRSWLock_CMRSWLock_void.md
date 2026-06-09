# CMRSWLock::~CMRSWLock(void)

- ea: `0x18001f860`
- end: `0x18001f909`
- name: `??1CMRSWLock@@QEAA@XZ`
- size: `169`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001f860`
- `0x180027900`
- `0x18002e468`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001f8fd`
- `KERNEL32!CloseHandle` at `0x18001f8ac`
- `KERNEL32!CloseHandle` at `0x18001f8c1`
- `KERNEL32!CloseHandle` at `0x18001f8d6`
- `KERNEL32!CloseHandle` at `0x18001f8ac`
- `KERNEL32!CloseHandle` at `0x18001f8c1`
- `KERNEL32!CloseHandle` at `0x18001f8d6`

## string_xrefs

- `0x18001f886`: `m_uActiveReaders == 0 && m_ActiveWriter.m_uThreadId == 0 && m_uWaitingReaders == 0 && m_uWaitingWriters == 0`
- `0x18001f893`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`

## pseudocode

```c
void __fastcall CMRSWLock::~CMRSWLock(CMRSWLock *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  if ( *((_DWORD *)this + 26) || *((_DWORD *)this + 18) || *((_DWORD *)this + 27) || *((_DWORD *)this + 28) )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x20u,
      "m_uActiveReaders == 0 && m_ActiveWriter.m_uThreadId == 0 && m_uWaitingReaders == 0 && m_uWaitingWriters == 0",
      1,
      0);
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 6);
  if ( v3 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 8);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 12);
  if ( v5 )
  {
    operator delete(v5);
    *((_QWORD *)this + 12) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18001f860  push    rbx
0x18001f862  sub     rsp, 30h
0x18001f866  cmp     dword ptr [rcx+68h], 0
0x18001f86a  mov     rbx, rcx
0x18001f86d  jnz     short loc_18001F881
0x18001f86f  cmp     dword ptr [rcx+48h], 0
0x18001f873  jnz     short loc_18001F881
0x18001f875  cmp     dword ptr [rcx+6Ch], 0
0x18001f879  jnz     short loc_18001F881
0x18001f87b  cmp     dword ptr [rcx+70h], 0
0x18001f87f  jz      short loc_18001F8A3
0x18001f881  and     [rsp+38h+var_18], 0
0x18001f886  lea     r8, aMUactivereader; "m_uActiveReaders == 0 && m_ActiveWriter"...
0x18001f88d  mov     r9d, 1; int
0x18001f893  lea     rcx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001f89a  lea     edx, [r9+1Fh]; unsigned int
0x18001f89e  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001f8a3  mov     rcx, [rbx+38h]; hObject
0x18001f8a7  test    rcx, rcx
0x18001f8aa  jz      short loc_18001F8B8
0x18001f8ac  call    cs:__imp_CloseHandle
0x18001f8b3  nop     dword ptr [rax+rax+00h]
0x18001f8b8  mov     rcx, [rbx+30h]; hObject
0x18001f8bc  test    rcx, rcx
0x18001f8bf  jz      short loc_18001F8CD
0x18001f8c1  call    cs:__imp_CloseHandle
0x18001f8c8  nop     dword ptr [rax+rax+00h]
0x18001f8cd  mov     rcx, [rbx+40h]; hObject
0x18001f8d1  test    rcx, rcx
0x18001f8d4  jz      short loc_18001F8E2
0x18001f8d6  call    cs:__imp_CloseHandle
0x18001f8dd  nop     dword ptr [rax+rax+00h]
0x18001f8e2  mov     rcx, [rbx+60h]; lpMem
0x18001f8e6  test    rcx, rcx
0x18001f8e9  jz      short loc_18001F8F5
0x18001f8eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f8f0  and     qword ptr [rbx+60h], 0
0x18001f8f5  mov     rcx, rbx
0x18001f8f8  add     rsp, 30h
0x18001f8fc  pop     rbx
0x18001f8fd  jmp     cs:__imp_DeleteCriticalSection
```
