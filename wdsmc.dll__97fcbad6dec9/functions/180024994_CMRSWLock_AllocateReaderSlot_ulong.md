# CMRSWLock::AllocateReaderSlot(ulong)

- ea: `0x180024994`
- end: `0x180024a45`
- name: `?AllocateReaderSlot@CMRSWLock@@AEAAKK@Z`
- size: `177`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024c14`

## callees

- `0x1800227d4`
- `0x180024994`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180024a2d`
- `KERNEL32!LeaveCriticalSection` at `0x180024a2d`
- `KERNEL32!EnterCriticalSection` at `0x1800249db`
- `KERNEL32!EnterCriticalSection` at `0x1800249db`
- `KERNEL32!WaitForSingleObject` at `0x1800249b1`
- `KERNEL32!WaitForSingleObject` at `0x1800249b1`

## string_xrefs

- `0x1800249cc`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180024a16`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800249c0`: `WaitForSingleObject(m_hReaderSlots, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

## pseudocode

```c
__int64 __fastcall CMRSWLock::AllocateReaderSlot(LPCRITICAL_SECTION lpCriticalSection, int a2)
{
  unsigned int v4; // edi
  int v5; // r9d
  int v6; // r9d
  __int64 v7; // rax
  _DWORD *OwningThread; // rdx

  v4 = -1;
  if ( WaitForSingleObject(lpCriticalSection[1].LockSemaphore, 0xFFFFFFFF) )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x9Cu,
      "WaitForSingleObject(m_hReaderSlots, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )",
      v5,
      0);
  EnterCriticalSection(lpCriticalSection);
  v7 = 0;
  if ( !HIDWORD(lpCriticalSection[2].DebugInfo) )
    goto LABEL_9;
  OwningThread = lpCriticalSection[2].OwningThread;
  while ( OwningThread[2 * v7] )
  {
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= HIDWORD(lpCriticalSection[2].DebugInfo) )
      goto LABEL_9;
  }
  OwningThread[2 * v7] = a2;
  v4 = v7;
  if ( (_DWORD)v7 == -1 )
LABEL_9:
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0xB3u, "uIndex != 0xffffffffUL", v6, 0);
  if ( v4 > lpCriticalSection[2].LockCount )
    lpCriticalSection[2].LockCount = v4;
  LeaveCriticalSection(lpCriticalSection);
  return v4;
}

```

## disassembly

```asm
0x180024994  mov     [rsp+arg_0], rbx
0x180024999  mov     [rsp+arg_8], rsi
0x18002499e  push    rdi
0x18002499f  sub     rsp, 30h
0x1800249a3  mov     esi, edx
0x1800249a5  mov     rbx, rcx
0x1800249a8  mov     rcx, [rcx+40h]; hHandle
0x1800249ac  or      edi, 0FFFFFFFFh
0x1800249af  or      edx, edi; dwMilliseconds
0x1800249b1  call    cs:__imp_WaitForSingleObject
0x1800249b7  test    eax, eax
0x1800249b9  jz      short loc_1800249D8
0x1800249bb  and     [rsp+38h+var_18], 0
0x1800249c0  lea     r8, aWaitforsingleo_0; "WaitForSingleObject(m_hReaderSlots, 0xF"...
0x1800249c7  mov     edx, 9Ch; unsigned int
0x1800249cc  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800249d3  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800249d8  mov     rcx, rbx; lpCriticalSection
0x1800249db  call    cs:__imp_EnterCriticalSection
0x1800249e1  xor     eax, eax
0x1800249e3  cmp     [rbx+54h], eax
0x1800249e6  jbe     short loc_180024A05
0x1800249e8  mov     rdx, [rbx+60h]
0x1800249ec  cmp     dword ptr [rdx+rax*8], 0
0x1800249f0  jz      short loc_1800249FB
0x1800249f2  inc     eax
0x1800249f4  cmp     eax, [rbx+54h]
0x1800249f7  jb      short loc_1800249EC
0x1800249f9  jmp     short loc_180024A05
0x1800249fb  mov     [rdx+rax*8], esi
0x1800249fe  mov     edi, eax
0x180024a00  cmp     eax, 0FFFFFFFFh
0x180024a03  jnz     short loc_180024A22
0x180024a05  and     [rsp+38h+var_18], 0
0x180024a0a  lea     r8, aUindex0xffffff; "uIndex != 0xffffffffUL"
0x180024a11  mov     edx, 0B3h; unsigned int
0x180024a16  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024a1d  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180024a22  cmp     edi, [rbx+58h]
0x180024a25  jbe     short loc_180024A2A
0x180024a27  mov     [rbx+58h], edi
0x180024a2a  mov     rcx, rbx; lpCriticalSection
0x180024a2d  call    cs:__imp_LeaveCriticalSection
0x180024a33  mov     rbx, [rsp+38h+arg_0]
0x180024a38  mov     eax, edi
0x180024a3a  mov     rsi, [rsp+38h+arg_8]
0x180024a3f  add     rsp, 30h
0x180024a43  pop     rdi
0x180024a44  retn
```
