# CMRSWLock::FreeReaderSlot(ulong,ulong)

- ea: `0x18001f9f0`
- end: `0x18001fac5`
- name: `?FreeReaderSlot@CMRSWLock@@AEAAXKK@Z`
- size: `213`
- prototype: `void __fastcall(CMRSWLock *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001fd00`

## callees

- `0x18001f9f0`
- `0x180027900`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x18001fa78`
- `KERNEL32!ReleaseSemaphore` at `0x18001fa78`

## string_xrefs

- `0x18001fa25`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001fa53`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001faa7`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001fa18`: `m_pReaderSlots[uIndex].m_uThreadId == uThreadId`
- `0x18001fa46`: `m_pReaderSlots[uIndex].m_uNestedReaders == 0`
- `0x18001fa88`: `ReleaseSemaphore(m_hReaderSlots, 1, 0)`

## pseudocode

```c
void __fastcall CMRSWLock::FreeReaderSlot(CMRSWLock *this, int a2, unsigned int a3)
{
  __int64 v4; // rbp
  const char *v5; // r8
  unsigned int v6; // edx

  if ( a3 >= *((_DWORD *)this + 21) )
  {
    v5 = "0";
    v6 = 286;
    goto LABEL_9;
  }
  v4 = a3;
  if ( *(_DWORD *)(*((_QWORD *)this + 12) + 8LL * a3) != a2 )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x109u,
      "m_pReaderSlots[uIndex].m_uThreadId == uThreadId",
      1,
      0);
  if ( *(_DWORD *)(*((_QWORD *)this + 12) + 8 * v4 + 4) )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x10Eu,
      "m_pReaderSlots[uIndex].m_uNestedReaders == 0",
      1,
      0);
  *(_QWORD *)(*((_QWORD *)this + 12) + 8 * v4) = 0;
  if ( !ReleaseSemaphore(*((HANDLE *)this + 8), 1, 0) )
  {
    v5 = "ReleaseSemaphore(m_hReaderSlots, 1, 0)";
    v6 = 282;
LABEL_9:
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v6, v5, 1, 0);
  }
}

```

## disassembly

```asm
0x18001f9f0  mov     [rsp+arg_0], rbp
0x18001f9f5  push    rsi
0x18001f9f6  sub     rsp, 30h
0x18001f9fa  mov     rsi, rcx
0x18001f9fd  cmp     r8d, [rcx+54h]
0x18001fa01  jnb     loc_18001FA96
0x18001fa07  mov     rax, [rcx+60h]
0x18001fa0b  mov     ebp, r8d
0x18001fa0e  cmp     [rax+rbp*8], edx
0x18001fa11  jz      short loc_18001FA36
0x18001fa13  and     [rsp+38h+var_18], 0
0x18001fa18  lea     r8, aMPreaderslotsU; "m_pReaderSlots[uIndex].m_uThreadId == u"...
0x18001fa1f  mov     r9d, 1; int
0x18001fa25  lea     rcx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001fa2c  mov     edx, 109h; unsigned int
0x18001fa31  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001fa36  mov     rax, [rsi+60h]
0x18001fa3a  cmp     dword ptr [rax+rbp*8+4], 0
0x18001fa3f  jz      short loc_18001FA64
0x18001fa41  and     [rsp+38h+var_18], 0
0x18001fa46  lea     r8, aMPreaderslotsU_0; "m_pReaderSlots[uIndex].m_uNestedReaders"...
0x18001fa4d  mov     r9d, 1; int
0x18001fa53  lea     rcx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001fa5a  mov     edx, 10Eh; unsigned int
0x18001fa5f  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001fa64  mov     rax, [rsi+60h]
0x18001fa68  xor     ecx, ecx
0x18001fa6a  xor     r8d, r8d; lpPreviousCount
0x18001fa6d  mov     [rax+rbp*8], rcx
0x18001fa71  lea     edx, [rcx+1]; lReleaseCount
0x18001fa74  mov     rcx, [rsi+40h]; hSemaphore
0x18001fa78  call    cs:__imp_ReleaseSemaphore
0x18001fa7f  nop     dword ptr [rax+rax+00h]
0x18001fa84  test    eax, eax
0x18001fa86  jnz     short loc_18001FAB9
0x18001fa88  lea     r8, aReleasesemapho; "ReleaseSemaphore(m_hReaderSlots, 1, 0)"
0x18001fa8f  mov     edx, 11Ah
0x18001fa94  jmp     short loc_18001FAA2
0x18001fa96  lea     r8, a0; "0"
0x18001fa9d  mov     edx, 11Eh; unsigned int
0x18001faa2  and     [rsp+38h+var_18], 0
0x18001faa7  lea     rcx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001faae  mov     r9d, 1; int
0x18001fab4  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001fab9  mov     rbp, [rsp+38h+arg_0]
0x18001fabe  add     rsp, 30h
0x18001fac2  pop     rsi
0x18001fac3  retn
```
