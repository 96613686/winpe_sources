# CMRSWLock::FreeReaderSlot(ulong,ulong)

- ea: `0x180013254`
- end: `0x18001330c`
- name: `?FreeReaderSlot@CMRSWLock@@AEAAXKK@Z`
- size: `184`
- prototype: `void __fastcall(CMRSWLock *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800051e8`
- `0x1800134f4`

## callees

- `0x180012f34`
- `0x180013254`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x1800132cc`
- `KERNEL32!ReleaseSemaphore` at `0x1800132cc`

## string_xrefs

- `0x180013284`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800132ac`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800132f5`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180013278`: `m_pReaderSlots[uIndex].m_uThreadId == uThreadId`
- `0x1800132a0`: `m_pReaderSlots[uIndex].m_uNestedReaders == 0`
- `0x1800132d6`: `ReleaseSemaphore(m_hReaderSlots, 1, 0)`

## pseudocode

```c
void __fastcall CMRSWLock::FreeReaderSlot(CMRSWLock *this, int a2, unsigned int a3, int a4)
{
  __int64 v5; // rax
  __int64 v6; // rsi
  const char *v7; // r8
  unsigned int v8; // edx

  if ( a3 >= *((_DWORD *)this + 21) )
  {
    v7 = "0";
    v8 = 286;
    goto LABEL_9;
  }
  v5 = *((_QWORD *)this + 12);
  v6 = a3;
  if ( *(_DWORD *)(v5 + 8LL * a3) != a2 )
  {
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x109u,
      "m_pReaderSlots[uIndex].m_uThreadId == uThreadId",
      a4,
      0);
    v5 = *((_QWORD *)this + 12);
  }
  if ( *(_DWORD *)(v5 + 8 * v6 + 4) )
  {
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x10Eu,
      "m_pReaderSlots[uIndex].m_uNestedReaders == 0",
      a4,
      0);
    v5 = *((_QWORD *)this + 12);
  }
  *(_QWORD *)(v5 + 8 * v6) = 0;
  if ( !ReleaseSemaphore(*((HANDLE *)this + 8), 1, 0) )
  {
    v7 = "ReleaseSemaphore(m_hReaderSlots, 1, 0)";
    v8 = 282;
LABEL_9:
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v8, v7, a4, 0);
  }
}

```

## disassembly

```asm
0x180013254  mov     [rsp+arg_0], rsi
0x180013259  push    rdi
0x18001325a  sub     rsp, 30h
0x18001325e  mov     rdi, rcx
0x180013261  cmp     r8d, [rcx+54h]
0x180013265  jnb     short loc_1800132E4
0x180013267  mov     rax, [rcx+60h]
0x18001326b  mov     esi, r8d
0x18001326e  cmp     [rax+rsi*8], edx
0x180013271  jz      short loc_180013294
0x180013273  and     [rsp+38h+var_18], 0
0x180013278  lea     r8, aMPreaderslotsU; "m_pReaderSlots[uIndex].m_uThreadId == u"...
0x18001327f  mov     edx, 109h; unsigned int
0x180013284  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001328b  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180013290  mov     rax, [rdi+60h]
0x180013294  cmp     dword ptr [rax+rsi*8+4], 0
0x180013299  jz      short loc_1800132BC
0x18001329b  and     [rsp+38h+var_18], 0
0x1800132a0  lea     r8, aMPreaderslotsU_0; "m_pReaderSlots[uIndex].m_uNestedReaders"...
0x1800132a7  mov     edx, 10Eh; unsigned int
0x1800132ac  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800132b3  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800132b8  mov     rax, [rdi+60h]
0x1800132bc  xor     ecx, ecx
0x1800132be  xor     r8d, r8d; lpPreviousCount
0x1800132c1  mov     [rax+rsi*8], rcx
0x1800132c5  lea     edx, [rcx+1]; lReleaseCount
0x1800132c8  mov     rcx, [rdi+40h]; hSemaphore
0x1800132cc  call    cs:__imp_ReleaseSemaphore
0x1800132d2  test    eax, eax
0x1800132d4  jnz     short loc_180013301
0x1800132d6  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderSlots, 1, 0)"
0x1800132dd  mov     edx, 11Ah
0x1800132e2  jmp     short loc_1800132F0
0x1800132e4  lea     r8, a0; "0"
0x1800132eb  mov     edx, 11Eh; unsigned int
0x1800132f0  and     [rsp+38h+var_18], 0
0x1800132f5  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800132fc  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180013301  mov     rsi, [rsp+38h+arg_0]
0x180013306  add     rsp, 30h
0x18001330a  pop     rdi
0x18001330b  retn
```
