# CMRSWLock::~CMRSWLock(void)

- ea: `0x180013048`
- end: `0x1800130d5`
- name: `??1CMRSWLock@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003acc`
- `0x180006bec`
- `0x180016070`

## callees

- `0x180012f34`
- `0x180013048`
- `0x1800150b8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800130ce`
- `KERNEL32!CloseHandle` at `0x18001308f`
- `KERNEL32!CloseHandle` at `0x18001309e`
- `KERNEL32!CloseHandle` at `0x1800130ad`
- `KERNEL32!CloseHandle` at `0x18001308f`
- `KERNEL32!CloseHandle` at `0x18001309e`
- `KERNEL32!CloseHandle` at `0x1800130ad`

## string_xrefs

- `0x18001306e`: `m_uActiveReaders == 0 && m_ActiveWriter.m_uThreadId == 0 && m_uWaitingReaders == 0 && m_uWaitingWriters == 0`
- `0x18001307a`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`

## pseudocode

```c
void __fastcall CMRSWLock::~CMRSWLock(CMRSWLock *this, __int64 a2, __int64 a3, int a4)
{
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( *((_DWORD *)this + 26) || *((_DWORD *)this + 18) || *((_DWORD *)this + 27) || *((_DWORD *)this + 28) )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x20u,
      "m_uActiveReaders == 0 && m_ActiveWriter.m_uThreadId == 0 && m_uWaitingReaders == 0 && m_uWaitingWriters == 0",
      a4,
      0);
  v5 = (void *)*((_QWORD *)this + 7);
  if ( v5 )
    CloseHandle(v5);
  v6 = (void *)*((_QWORD *)this + 6);
  if ( v6 )
    CloseHandle(v6);
  v7 = (void *)*((_QWORD *)this + 8);
  if ( v7 )
    CloseHandle(v7);
  v8 = (void *)*((_QWORD *)this + 12);
  if ( v8 )
  {
    operator delete(v8);
    *((_QWORD *)this + 12) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180013048  push    rbx
0x18001304a  sub     rsp, 30h
0x18001304e  cmp     dword ptr [rcx+68h], 0
0x180013052  mov     rbx, rcx
0x180013055  jnz     short loc_180013069
0x180013057  cmp     dword ptr [rcx+48h], 0
0x18001305b  jnz     short loc_180013069
0x18001305d  cmp     dword ptr [rcx+6Ch], 0
0x180013061  jnz     short loc_180013069
0x180013063  cmp     dword ptr [rcx+70h], 0
0x180013067  jz      short loc_180013086
0x180013069  and     [rsp+38h+var_18], 0
0x18001306e  lea     r8, aMUactivereader_0; "m_uActiveReaders == 0 && m_ActiveWriter"...
0x180013075  mov     edx, 20h ; ' '; unsigned int
0x18001307a  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180013081  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180013086  mov     rcx, [rbx+38h]; hObject
0x18001308a  test    rcx, rcx
0x18001308d  jz      short loc_180013095
0x18001308f  call    cs:__imp_CloseHandle
0x180013095  mov     rcx, [rbx+30h]; hObject
0x180013099  test    rcx, rcx
0x18001309c  jz      short loc_1800130A4
0x18001309e  call    cs:__imp_CloseHandle
0x1800130a4  mov     rcx, [rbx+40h]; hObject
0x1800130a8  test    rcx, rcx
0x1800130ab  jz      short loc_1800130B3
0x1800130ad  call    cs:__imp_CloseHandle
0x1800130b3  mov     rcx, [rbx+60h]; Block
0x1800130b7  test    rcx, rcx
0x1800130ba  jz      short loc_1800130C6
0x1800130bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800130c1  and     qword ptr [rbx+60h], 0
0x1800130c6  mov     rcx, rbx
0x1800130c9  add     rsp, 30h
0x1800130cd  pop     rbx
0x1800130ce  jmp     cs:__imp_DeleteCriticalSection
```
