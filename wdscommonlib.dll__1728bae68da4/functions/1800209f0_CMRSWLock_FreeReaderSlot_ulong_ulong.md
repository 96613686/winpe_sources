# CMRSWLock::FreeReaderSlot(ulong,ulong)

- ea: `0x1800209f0`
- end: `0x180020ac5`
- name: `?FreeReaderSlot@CMRSWLock@@AEAAXKK@Z`
- size: `213`
- prototype: `void __fastcall(CMRSWLock *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020d00`

## callees

- `0x1800209f0`
- `0x180028a50`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x180020a78`
- `KERNEL32!ReleaseSemaphore` at `0x180020a78`

## string_xrefs

- `0x180020a25`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180020a53`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180020aa7`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180020a18`: `m_pReaderSlots[uIndex].m_uThreadId == uThreadId`
- `0x180020a46`: `m_pReaderSlots[uIndex].m_uNestedReaders == 0`
- `0x180020a88`: `ReleaseSemaphore(m_hReaderSlots, 1, 0)`

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
0x1800209f0  mov     [rsp+arg_0], rbp
0x1800209f5  push    rsi
0x1800209f6  sub     rsp, 30h
0x1800209fa  mov     rsi, rcx
0x1800209fd  cmp     r8d, [rcx+54h]
0x180020a01  jnb     loc_180020A96
0x180020a07  mov     rax, [rcx+60h]
0x180020a0b  mov     ebp, r8d
0x180020a0e  cmp     [rax+rbp*8], edx
0x180020a11  jz      short loc_180020A36
0x180020a13  and     [rsp+38h+var_18], 0
0x180020a18  lea     r8, aMPreaderslotsU; "m_pReaderSlots[uIndex].m_uThreadId == u"...
0x180020a1f  mov     r9d, 1; int
0x180020a25  lea     rcx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180020a2c  mov     edx, 109h; unsigned int
0x180020a31  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020a36  mov     rax, [rsi+60h]
0x180020a3a  cmp     dword ptr [rax+rbp*8+4], 0
0x180020a3f  jz      short loc_180020A64
0x180020a41  and     [rsp+38h+var_18], 0
0x180020a46  lea     r8, aMPreaderslotsU_0; "m_pReaderSlots[uIndex].m_uNestedReaders"...
0x180020a4d  mov     r9d, 1; int
0x180020a53  lea     rcx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180020a5a  mov     edx, 10Eh; unsigned int
0x180020a5f  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020a64  mov     rax, [rsi+60h]
0x180020a68  xor     ecx, ecx
0x180020a6a  xor     r8d, r8d; lpPreviousCount
0x180020a6d  mov     [rax+rbp*8], rcx
0x180020a71  lea     edx, [rcx+1]; lReleaseCount
0x180020a74  mov     rcx, [rsi+40h]; hSemaphore
0x180020a78  call    cs:__imp_ReleaseSemaphore
0x180020a7f  nop     dword ptr [rax+rax+00h]
0x180020a84  test    eax, eax
0x180020a86  jnz     short loc_180020AB9
0x180020a88  lea     r8, aReleasesemapho; "ReleaseSemaphore(m_hReaderSlots, 1, 0)"
0x180020a8f  mov     edx, 11Ah
0x180020a94  jmp     short loc_180020AA2
0x180020a96  lea     r8, a0; "0"
0x180020a9d  mov     edx, 11Eh; unsigned int
0x180020aa2  and     [rsp+38h+var_18], 0
0x180020aa7  lea     rcx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180020aae  mov     r9d, 1; int
0x180020ab4  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020ab9  mov     rbp, [rsp+38h+arg_0]
0x180020abe  add     rsp, 30h
0x180020ac2  pop     rsi
0x180020ac3  retn
```
