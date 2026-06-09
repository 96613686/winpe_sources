# CMRSWLock::~CMRSWLock(void)

- ea: `0x180024840`
- end: `0x1800248cd`
- name: `??1CMRSWLock@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009130`
- `0x18000a97c`

## callees

- `0x18001a9a8`
- `0x1800227d4`
- `0x180024840`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180024887`
- `KERNEL32!CloseHandle` at `0x180024896`
- `KERNEL32!CloseHandle` at `0x1800248a5`
- `KERNEL32!CloseHandle` at `0x180024887`
- `KERNEL32!CloseHandle` at `0x180024896`
- `KERNEL32!CloseHandle` at `0x1800248a5`
- `KERNEL32!DeleteCriticalSection` at `0x1800248c6`

## string_xrefs

- `0x180024866`: `m_uActiveReaders == 0 && m_ActiveWriter.m_uThreadId == 0 && m_uWaitingReaders == 0 && m_uWaitingWriters == 0`
- `0x180024872`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`

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
0x180024840  push    rbx
0x180024842  sub     rsp, 30h
0x180024846  cmp     dword ptr [rcx+68h], 0
0x18002484a  mov     rbx, rcx
0x18002484d  jnz     short loc_180024861
0x18002484f  cmp     dword ptr [rcx+48h], 0
0x180024853  jnz     short loc_180024861
0x180024855  cmp     dword ptr [rcx+6Ch], 0
0x180024859  jnz     short loc_180024861
0x18002485b  cmp     dword ptr [rcx+70h], 0
0x18002485f  jz      short loc_18002487E
0x180024861  and     [rsp+38h+var_18], 0
0x180024866  lea     r8, aMUactivereader_0; "m_uActiveReaders == 0 && m_ActiveWriter"...
0x18002486d  mov     edx, 20h ; ' '; unsigned int
0x180024872  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024879  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18002487e  mov     rcx, [rbx+38h]; hObject
0x180024882  test    rcx, rcx
0x180024885  jz      short loc_18002488D
0x180024887  call    cs:__imp_CloseHandle
0x18002488d  mov     rcx, [rbx+30h]; hObject
0x180024891  test    rcx, rcx
0x180024894  jz      short loc_18002489C
0x180024896  call    cs:__imp_CloseHandle
0x18002489c  mov     rcx, [rbx+40h]; hObject
0x1800248a0  test    rcx, rcx
0x1800248a3  jz      short loc_1800248AB
0x1800248a5  call    cs:__imp_CloseHandle
0x1800248ab  mov     rcx, [rbx+60h]; void *
0x1800248af  test    rcx, rcx
0x1800248b2  jz      short loc_1800248BE
0x1800248b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800248b9  and     qword ptr [rbx+60h], 0
0x1800248be  mov     rcx, rbx
0x1800248c1  add     rsp, 30h
0x1800248c5  pop     rbx
0x1800248c6  jmp     cs:__imp_DeleteCriticalSection
```
