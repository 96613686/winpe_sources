# CMRSWLock::FreeReaderSlot(ulong,ulong)

- ea: `0x180024a4c`
- end: `0x180024b04`
- name: `?FreeReaderSlot@CMRSWLock@@AEAAXKK@Z`
- size: `184`
- prototype: `void __fastcall(CMRSWLock *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024ce0`

## callees

- `0x1800227d4`
- `0x180024a4c`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x180024ac4`
- `KERNEL32!ReleaseSemaphore` at `0x180024ac4`

## string_xrefs

- `0x180024a7c`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180024aa4`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180024aed`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180024a70`: `m_pReaderSlots[uIndex].m_uThreadId == uThreadId`
- `0x180024a98`: `m_pReaderSlots[uIndex].m_uNestedReaders == 0`
- `0x180024ace`: `ReleaseSemaphore(m_hReaderSlots, 1, 0)`

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
0x180024a4c  mov     [rsp+arg_0], rsi
0x180024a51  push    rdi
0x180024a52  sub     rsp, 30h
0x180024a56  mov     rdi, rcx
0x180024a59  cmp     r8d, [rcx+54h]
0x180024a5d  jnb     short loc_180024ADC
0x180024a5f  mov     rax, [rcx+60h]
0x180024a63  mov     esi, r8d
0x180024a66  cmp     [rax+rsi*8], edx
0x180024a69  jz      short loc_180024A8C
0x180024a6b  and     [rsp+38h+var_18], 0
0x180024a70  lea     r8, aMPreaderslotsU; "m_pReaderSlots[uIndex].m_uThreadId == u"...
0x180024a77  mov     edx, 109h; unsigned int
0x180024a7c  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024a83  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180024a88  mov     rax, [rdi+60h]
0x180024a8c  cmp     dword ptr [rax+rsi*8+4], 0
0x180024a91  jz      short loc_180024AB4
0x180024a93  and     [rsp+38h+var_18], 0
0x180024a98  lea     r8, aMPreaderslotsU_0; "m_pReaderSlots[uIndex].m_uNestedReaders"...
0x180024a9f  mov     edx, 10Eh; unsigned int
0x180024aa4  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024aab  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180024ab0  mov     rax, [rdi+60h]
0x180024ab4  xor     ecx, ecx
0x180024ab6  xor     r8d, r8d; lpPreviousCount
0x180024ab9  mov     [rax+rsi*8], rcx
0x180024abd  lea     edx, [rcx+1]; lReleaseCount
0x180024ac0  mov     rcx, [rdi+40h]; hSemaphore
0x180024ac4  call    cs:__imp_ReleaseSemaphore
0x180024aca  test    eax, eax
0x180024acc  jnz     short loc_180024AF9
0x180024ace  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderSlots, 1, 0)"
0x180024ad5  mov     edx, 11Ah
0x180024ada  jmp     short loc_180024AE8
0x180024adc  lea     r8, a0; "0"
0x180024ae3  mov     edx, 11Eh; unsigned int
0x180024ae8  and     [rsp+38h+var_18], 0
0x180024aed  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024af4  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180024af9  mov     rsi, [rsp+38h+arg_0]
0x180024afe  add     rsp, 30h
0x180024b02  pop     rdi
0x180024b03  retn
```
