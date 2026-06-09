# CAutoWriterLock::Lock(void)

- ea: `0x180008dcc`
- end: `0x180008eb0`
- name: `?Lock@CAutoWriterLock@@QEAAXXZ`
- size: `228`
- prototype: `void __fastcall(CAutoWriterLock *__hidden this)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800053a0`
- `0x180005a4c`
- `0x180005e28`
- `0x180005f18`
- `0x180006488`
- `0x1800067f0`
- `0x180006bc4`
- `0x180006e48`
- `0x180006f84`
- `0x1800071a0`
- `0x180007278`
- `0x180007358`
- `0x1800074bc`
- `0x180007a24`
- `0x180008b58`
- `0x18000a97c`

## callees

- `0x180008dcc`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180008ded`
- `KERNEL32!GetCurrentThreadId` at `0x180008e8b`
- `KERNEL32!GetCurrentThreadId` at `0x180008ded`
- `KERNEL32!GetCurrentThreadId` at `0x180008e8b`
- `KERNEL32!LeaveCriticalSection` at `0x180008e1d`
- `KERNEL32!LeaveCriticalSection` at `0x180008e97`
- `KERNEL32!LeaveCriticalSection` at `0x180008e1d`
- `KERNEL32!LeaveCriticalSection` at `0x180008e97`
- `KERNEL32!EnterCriticalSection` at `0x180008de4`
- `KERNEL32!EnterCriticalSection` at `0x180008e53`
- `KERNEL32!EnterCriticalSection` at `0x180008de4`
- `KERNEL32!EnterCriticalSection` at `0x180008e53`
- `KERNEL32!WaitForSingleObject` at `0x180008e29`
- `KERNEL32!WaitForSingleObject` at `0x180008e29`

## string_xrefs

- `0x180008e44`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180008e7f`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180008e78`: `m_ActiveWriter.m_uNestedReaders == 0`
- `0x180008e38`: `WaitForSingleObject(m_hReaderDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

## pseudocode

```c
void __fastcall CAutoWriterLock::Lock(LPCRITICAL_SECTION *this)
{
  LPCRITICAL_SECTION v1; // rbx
  int SpinCount; // edi
  int v4; // r9d
  unsigned int v5; // edx
  int v6; // r9d

  v1 = *this;
  EnterCriticalSection(*this);
  SpinCount = v1[1].SpinCount;
  if ( SpinCount != GetCurrentThreadId() )
  {
    if ( SpinCount || LODWORD(v1[2].LockSemaphore) )
    {
      ++LODWORD(v1[2].SpinCount);
      do
      {
        LeaveCriticalSection(v1);
        if ( WaitForSingleObject(v1[1].OwningThread, 0xFFFFFFFF) )
          WdsAssert(
            "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
            0x164u,
            "WaitForSingleObject(m_hReaderDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )",
            v6,
            0);
        EnterCriticalSection(v1);
      }
      while ( LODWORD(v1[2].LockSemaphore) || LODWORD(v1[1].SpinCount) );
      --LODWORD(v1[2].SpinCount);
      if ( !HIDWORD(v1[1].SpinCount) )
        goto LABEL_15;
      v5 = 371;
    }
    else
    {
      if ( !HIDWORD(v1[1].SpinCount) )
      {
LABEL_15:
        LODWORD(v1[1].SpinCount) = GetCurrentThreadId();
        goto LABEL_16;
      }
      v5 = 329;
    }
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      v5,
      "m_ActiveWriter.m_uNestedReaders == 0",
      v4,
      0);
    goto LABEL_15;
  }
  ++LODWORD(v1[2].DebugInfo);
LABEL_16:
  LeaveCriticalSection(v1);
  ++*((_DWORD *)this + 2);
}

```

## disassembly

```asm
0x180008dcc  mov     [rsp+arg_0], rbx
0x180008dd1  mov     [rsp+arg_8], rsi
0x180008dd6  push    rdi
0x180008dd7  sub     rsp, 30h
0x180008ddb  mov     rbx, [rcx]
0x180008dde  mov     rsi, rcx
0x180008de1  mov     rcx, rbx; lpCriticalSection
0x180008de4  call    cs:__imp_EnterCriticalSection
0x180008dea  mov     edi, [rbx+48h]
0x180008ded  call    cs:__imp_GetCurrentThreadId
0x180008df3  cmp     edi, eax
0x180008df5  jnz     short loc_180008DFF
0x180008df7  inc     dword ptr [rbx+50h]
0x180008dfa  jmp     loc_180008E94
0x180008dff  test    edi, edi
0x180008e01  jnz     short loc_180008E14
0x180008e03  cmp     [rbx+68h], edi
0x180008e06  jnz     short loc_180008E14
0x180008e08  cmp     [rbx+4Ch], edi
0x180008e0b  jz      short loc_180008E8B
0x180008e0d  mov     edx, 149h
0x180008e12  jmp     short loc_180008E73
0x180008e14  inc     dword ptr [rbx+70h]
0x180008e17  or      edi, 0FFFFFFFFh
0x180008e1a  mov     rcx, rbx; lpCriticalSection
0x180008e1d  call    cs:__imp_LeaveCriticalSection
0x180008e23  mov     rcx, [rbx+38h]; hHandle
0x180008e27  mov     edx, edi; dwMilliseconds
0x180008e29  call    cs:__imp_WaitForSingleObject
0x180008e2f  test    eax, eax
0x180008e31  jz      short loc_180008E50
0x180008e33  and     [rsp+38h+var_18], 0
0x180008e38  lea     r8, aWaitforsingleo_1; "WaitForSingleObject(m_hReaderDone, 0xFF"...
0x180008e3f  mov     edx, 164h; unsigned int
0x180008e44  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180008e4b  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180008e50  mov     rcx, rbx; lpCriticalSection
0x180008e53  call    cs:__imp_EnterCriticalSection
0x180008e59  cmp     dword ptr [rbx+68h], 0
0x180008e5d  jnz     short loc_180008E1A
0x180008e5f  cmp     dword ptr [rbx+48h], 0
0x180008e63  jnz     short loc_180008E1A
0x180008e65  add     [rbx+70h], edi
0x180008e68  cmp     dword ptr [rbx+4Ch], 0
0x180008e6c  jz      short loc_180008E8B
0x180008e6e  mov     edx, 173h; unsigned int
0x180008e73  and     [rsp+38h+var_18], 0
0x180008e78  lea     r8, aMActivewriterM_0; "m_ActiveWriter.m_uNestedReaders == 0"
0x180008e7f  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180008e86  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180008e8b  call    cs:__imp_GetCurrentThreadId
0x180008e91  mov     [rbx+48h], eax
0x180008e94  mov     rcx, rbx; lpCriticalSection
0x180008e97  call    cs:__imp_LeaveCriticalSection
0x180008e9d  inc     dword ptr [rsi+8]
0x180008ea0  mov     rsi, [rsp+38h+arg_8]
0x180008ea5  mov     rbx, [rsp+38h+arg_0]
0x180008eaa  add     rsp, 30h
0x180008eae  pop     rdi
0x180008eaf  retn
```
