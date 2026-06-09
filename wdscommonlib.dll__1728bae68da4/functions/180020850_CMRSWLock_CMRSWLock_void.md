# CMRSWLock::~CMRSWLock(void)

- ea: `0x180020850`
- end: `0x180020900`
- name: `??1CMRSWLock@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(CMRSWLock *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180020850`
- `0x180028a50`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800208db`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800208db`
- `KERNEL32!DeleteCriticalSection` at `0x1800208f4`
- `KERNEL32!CloseHandle` at `0x18002089c`
- `KERNEL32!CloseHandle` at `0x1800208b1`
- `KERNEL32!CloseHandle` at `0x1800208c6`
- `KERNEL32!CloseHandle` at `0x18002089c`
- `KERNEL32!CloseHandle` at `0x1800208b1`
- `KERNEL32!CloseHandle` at `0x1800208c6`

## string_xrefs

- `0x180020876`: `m_uActiveReaders == 0 && m_ActiveWriter.m_uThreadId == 0 && m_uWaitingReaders == 0 && m_uWaitingWriters == 0`
- `0x180020883`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`

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
0x180020850  push    rbx
0x180020852  sub     rsp, 30h
0x180020856  cmp     dword ptr [rcx+68h], 0
0x18002085a  mov     rbx, rcx
0x18002085d  jnz     short loc_180020871
0x18002085f  cmp     dword ptr [rcx+48h], 0
0x180020863  jnz     short loc_180020871
0x180020865  cmp     dword ptr [rcx+6Ch], 0
0x180020869  jnz     short loc_180020871
0x18002086b  cmp     dword ptr [rcx+70h], 0
0x18002086f  jz      short loc_180020893
0x180020871  and     [rsp+38h+var_18], 0
0x180020876  lea     r8, aMUactivereader; "m_uActiveReaders == 0 && m_ActiveWriter"...
0x18002087d  mov     r9d, 1; int
0x180020883  lea     rcx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002088a  lea     edx, [r9+1Fh]; unsigned int
0x18002088e  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020893  mov     rcx, [rbx+38h]; hObject
0x180020897  test    rcx, rcx
0x18002089a  jz      short loc_1800208A8
0x18002089c  call    cs:__imp_CloseHandle
0x1800208a3  nop     dword ptr [rax+rax+00h]
0x1800208a8  mov     rcx, [rbx+30h]; hObject
0x1800208ac  test    rcx, rcx
0x1800208af  jz      short loc_1800208BD
0x1800208b1  call    cs:__imp_CloseHandle
0x1800208b8  nop     dword ptr [rax+rax+00h]
0x1800208bd  mov     rcx, [rbx+40h]; hObject
0x1800208c1  test    rcx, rcx
0x1800208c4  jz      short loc_1800208D2
0x1800208c6  call    cs:__imp_CloseHandle
0x1800208cd  nop     dword ptr [rax+rax+00h]
0x1800208d2  mov     rcx, [rbx+60h]
0x1800208d6  test    rcx, rcx
0x1800208d9  jz      short loc_1800208EC
0x1800208db  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800208e2  nop     dword ptr [rax+rax+00h]
0x1800208e7  and     qword ptr [rbx+60h], 0
0x1800208ec  mov     rcx, rbx
0x1800208ef  add     rsp, 30h
0x1800208f3  pop     rbx
0x1800208f4  jmp     cs:__imp_DeleteCriticalSection
```
