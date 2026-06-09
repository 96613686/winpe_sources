# cxl::TraceManager::Acquire(void)

- ea: `0x18000ddf0`
- end: `0x18000de93`
- name: `?Acquire@TraceManager@cxl@@AEAAPEAUTraceBuffer@12@XZ`
- size: `163`
- prototype: `struct cxl::TraceManager::TraceBuffer *__fastcall(cxl::TraceManager *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18000df84`
- `0x18000e27c`
- `0x18000e2b0`

## callees

- `0x180002ae0`
- `0x180002f00`
- `0x18000c9f0`
- `0x18000dad8`
- `0x18000ddf0`
- `0x18000e1e4`
- `0x18000f828`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000de13`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000de13`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000de25`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000de25`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct cxl::TraceManager::TraceBuffer *__fastcall cxl::TraceManager::Acquire(union _SLIST_HEADER *this)
{
  struct cxl::TraceManager::TraceBuffer *result; // rax
  PSLIST_ENTRY v3; // rax
  __int64 v4; // rbx
  struct _SLIST_ENTRY *v5; // rcx
  int v6; // edx
  cxl::TraceManager::TraceBuffer *v7; // [rsp+20h] [rbp-38h]
  _BYTE v8[32]; // [rsp+28h] [rbp-30h] BYREF

  if ( cxl::ThreadLocal<cxl::TraceManager::TraceBuffer>::tlsIndex == -1 )
  {
    std::wstring::wstring(v8, L"tlsIndex != TLS_OUT_OF_INDEXES is false");
    cxl::Throw::AssertionFailed(v8);
  }
  result = (struct cxl::TraceManager::TraceBuffer *)TlsGetValue(cxl::ThreadLocal<cxl::TraceManager::TraceBuffer>::tlsIndex);
  if ( !result )
  {
    v3 = InterlockedPopEntrySList(this + 14);
    if ( !v3 || (v4 = (__int64)&v3[-2], v3 == (PSLIST_ENTRY)32) )
    {
      v7 = (cxl::TraceManager::TraceBuffer *)operator new(0x40u);
      v4 = cxl::TraceManager::TraceBuffer::TraceBuffer(v7, v6);
      v5 = (struct _SLIST_ENTRY *)v4;
    }
    else
    {
      v5 = v3 - 2;
    }
    cxl::ThreadLocal<cxl::TraceManager::TraceBuffer>::TlsSet(v5);
    return (struct cxl::TraceManager::TraceBuffer *)v4;
  }
  return result;
}

```

## disassembly

```asm
0x18000ddf0  push    rbx
0x18000ddf2  sub     rsp, 50h
0x18000ddf6  mov     rax, cs:__security_cookie
0x18000ddfd  xor     rax, rsp
0x18000de00  mov     [rsp+58h+var_10], rax
0x18000de05  mov     rbx, rcx
0x18000de08  mov     ecx, cs:?tlsIndex@?$ThreadLocal@UTraceBuffer@TraceManager@cxl@@@cxl@@0HA; dwTlsIndex
0x18000de0e  cmp     ecx, 0FFFFFFFFh
0x18000de11  jz      short loc_18000DE76
0x18000de13  call    cs:__imp_TlsGetValue
0x18000de19  test    rax, rax
0x18000de1c  jnz     short loc_18000DE44
0x18000de1e  lea     rcx, [rbx+0E0h]; ListHead
0x18000de25  call    cs:__imp_InterlockedPopEntrySList
0x18000de2b  test    rax, rax
0x18000de2e  jz      short loc_18000DE57
0x18000de30  lea     rbx, [rax-20h]
0x18000de34  test    rbx, rbx
0x18000de37  jz      short loc_18000DE57
0x18000de39  mov     rcx, rbx; lpTlsValue
0x18000de3c  call    ?TlsSet@?$ThreadLocal@UTraceBuffer@TraceManager@cxl@@@cxl@@SAXPEAUTraceBuffer@TraceManager@2@@Z; cxl::ThreadLocal<cxl::TraceManager::TraceBuffer>::TlsSet(cxl::TraceManager::TraceBuffer *)
0x18000de41  mov     rax, rbx
0x18000de44  mov     rcx, [rsp+58h+var_10]
0x18000de49  xor     rcx, rsp; StackCookie
0x18000de4c  call    __security_check_cookie
0x18000de51  add     rsp, 50h
0x18000de55  pop     rbx
0x18000de56  retn
0x18000de57  mov     ecx, 40h ; '@'; Size
0x18000de5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000de61  mov     [rsp+58h+var_38], rax
0x18000de66  mov     rcx, rax; this
0x18000de69  call    ??0TraceBuffer@TraceManager@cxl@@QEAA@H@Z; cxl::TraceManager::TraceBuffer::TraceBuffer(int)
0x18000de6e  mov     rbx, rax
0x18000de71  mov     rcx, rax
0x18000de74  jmp     short loc_18000DE3C
0x18000de76  lea     rdx, aTlsindexTlsOut; "tlsIndex != TLS_OUT_OF_INDEXES is false"
0x18000de7d  lea     rcx, [rsp+58h+var_30]
0x18000de82  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000de87  nop
0x18000de88  lea     rcx, [rsp+58h+var_30]
0x18000de8d  call    ?AssertionFailed@Throw@cxl@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Throw::AssertionFailed(std::wstring const &)
```
