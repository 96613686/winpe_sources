# CMRSWLock::~CMRSWLock(void)

- ea: `0x18003a628`
- end: `0x18003a6cc`
- name: `??1CMRSWLock@@QEAA@XZ`
- size: `164`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000362c`
- `0x180005c50`
- `0x18000d66c`

## callees

- `0x18000a960`
- `0x18003a628`
- `0x18003c514`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18003a6c0`
- `KERNEL32!CloseHandle` at `0x18003a66f`
- `KERNEL32!CloseHandle` at `0x18003a684`
- `KERNEL32!CloseHandle` at `0x18003a699`
- `KERNEL32!CloseHandle` at `0x18003a66f`
- `KERNEL32!CloseHandle` at `0x18003a684`
- `KERNEL32!CloseHandle` at `0x18003a699`

## string_xrefs

- `0x18003a64e`: `m_uActiveReaders == 0 && m_ActiveWriter.m_uThreadId == 0 && m_uWaitingReaders == 0 && m_uWaitingWriters == 0`
- `0x18003a65a`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`

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
0x18003a628  push    rbx
0x18003a62a  sub     rsp, 30h
0x18003a62e  cmp     dword ptr [rcx+68h], 0
0x18003a632  mov     rbx, rcx
0x18003a635  jnz     short loc_18003A649
0x18003a637  cmp     dword ptr [rcx+48h], 0
0x18003a63b  jnz     short loc_18003A649
0x18003a63d  cmp     dword ptr [rcx+6Ch], 0
0x18003a641  jnz     short loc_18003A649
0x18003a643  cmp     dword ptr [rcx+70h], 0
0x18003a647  jz      short loc_18003A666
0x18003a649  and     [rsp+38h+var_18], 0
0x18003a64e  lea     r8, aMUactivereader; "m_uActiveReaders == 0 && m_ActiveWriter"...
0x18003a655  mov     edx, 20h ; ' '; unsigned int
0x18003a65a  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003a661  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18003a666  mov     rcx, [rbx+38h]; hObject
0x18003a66a  test    rcx, rcx
0x18003a66d  jz      short loc_18003A67B
0x18003a66f  call    cs:__imp_CloseHandle
0x18003a676  nop     dword ptr [rax+rax+00h]
0x18003a67b  mov     rcx, [rbx+30h]; hObject
0x18003a67f  test    rcx, rcx
0x18003a682  jz      short loc_18003A690
0x18003a684  call    cs:__imp_CloseHandle
0x18003a68b  nop     dword ptr [rax+rax+00h]
0x18003a690  mov     rcx, [rbx+40h]; hObject
0x18003a694  test    rcx, rcx
0x18003a697  jz      short loc_18003A6A5
0x18003a699  call    cs:__imp_CloseHandle
0x18003a6a0  nop     dword ptr [rax+rax+00h]
0x18003a6a5  mov     rcx, [rbx+60h]; void *
0x18003a6a9  test    rcx, rcx
0x18003a6ac  jz      short loc_18003A6B8
0x18003a6ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a6b3  and     qword ptr [rbx+60h], 0
0x18003a6b8  mov     rcx, rbx
0x18003a6bb  add     rsp, 30h
0x18003a6bf  pop     rbx
0x18003a6c0  jmp     cs:__imp_DeleteCriticalSection
```
