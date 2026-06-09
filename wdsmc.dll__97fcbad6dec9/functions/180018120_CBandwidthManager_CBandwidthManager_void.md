# CBandwidthManager::~CBandwidthManager(void)

- ea: `0x180018120`
- end: `0x18001816b`
- name: `??1CBandwidthManager@@QEAA@XZ`
- size: `75`
- prototype: `void __fastcall(CBandwidthManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009130`

## callees

- `0x180018120`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180018156`
- `KERNEL32!DeleteCriticalSection` at `0x180018156`
- `KERNEL32!DeleteCriticalSection` at `0x180018164`

## pseudocode

```c
void __fastcall CBandwidthManager::~CBandwidthManager(CBandwidthManager *this, __int64 a2, __int64 a3, int a4)
{
  if ( *((_DWORD *)this + 64) )
    WdsAssert(
      "base\\eco\\wds\\transport\\server\\mc\\bandwidthmanager.cpp",
      0x4Du,
      "m_Interfaces.GetCount() == 0",
      a4,
      0);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180018120  push    rbx
0x180018122  sub     rsp, 30h
0x180018126  cmp     dword ptr [rcx+100h], 0
0x18001812d  mov     rbx, rcx
0x180018130  jz      short loc_18001814F
0x180018132  and     [rsp+38h+var_18], 0
0x180018137  lea     r8, aMInterfacesGet; "m_Interfaces.GetCount() == 0"
0x18001813e  mov     edx, 4Dh ; 'M'; unsigned int
0x180018143  lea     rcx, aBaseEcoWdsTran_20; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18001814a  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001814f  lea     rcx, [rbx+0D8h]; lpCriticalSection
0x180018156  call    cs:__imp_DeleteCriticalSection
0x18001815c  mov     rcx, rbx
0x18001815f  add     rsp, 30h
0x180018163  pop     rbx
0x180018164  jmp     cs:__imp_DeleteCriticalSection
```
