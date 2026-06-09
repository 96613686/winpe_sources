# cxl::TraceManager::Acquire(void)

- ea: `0x18000e4a0`
- end: `0x18000e543`
- name: `?Acquire@TraceManager@cxl@@AEAAPEAUTraceBuffer@12@XZ`
- size: `163`
- prototype: `struct cxl::TraceManager::TraceBuffer *__fastcall(cxl::TraceManager *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e634`
- `0x18000e92c`
- `0x18000e960`

## callees

- `0x180002a70`
- `0x180002a94`
- `0x180005e68`
- `0x18000e188`
- `0x18000e4a0`
- `0x18000e894`
- `0x180010b68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000e4c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000e4c3`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000e4d5`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000e4d5`

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
0x18000e4a0  push    rbx
0x18000e4a2  sub     rsp, 50h
0x18000e4a6  mov     rax, cs:__security_cookie
0x18000e4ad  xor     rax, rsp
0x18000e4b0  mov     [rsp+58h+var_10], rax
0x18000e4b5  mov     rbx, rcx
0x18000e4b8  mov     ecx, cs:?tlsIndex@?$ThreadLocal@UTraceBuffer@TraceManager@cxl@@@cxl@@0HA; dwTlsIndex
0x18000e4be  cmp     ecx, 0FFFFFFFFh
0x18000e4c1  jz      short loc_18000E526
0x18000e4c3  call    cs:__imp_TlsGetValue
0x18000e4c9  test    rax, rax
0x18000e4cc  jnz     short loc_18000E4F4
0x18000e4ce  lea     rcx, [rbx+0E0h]; ListHead
0x18000e4d5  call    cs:__imp_InterlockedPopEntrySList
0x18000e4db  test    rax, rax
0x18000e4de  jz      short loc_18000E507
0x18000e4e0  lea     rbx, [rax-20h]
0x18000e4e4  test    rbx, rbx
0x18000e4e7  jz      short loc_18000E507
0x18000e4e9  mov     rcx, rbx; lpTlsValue
0x18000e4ec  call    ?TlsSet@?$ThreadLocal@UTraceBuffer@TraceManager@cxl@@@cxl@@SAXPEAUTraceBuffer@TraceManager@2@@Z; cxl::ThreadLocal<cxl::TraceManager::TraceBuffer>::TlsSet(cxl::TraceManager::TraceBuffer *)
0x18000e4f1  mov     rax, rbx
0x18000e4f4  mov     rcx, [rsp+58h+var_10]
0x18000e4f9  xor     rcx, rsp; StackCookie
0x18000e4fc  call    __security_check_cookie
0x18000e501  add     rsp, 50h
0x18000e505  pop     rbx
0x18000e506  retn
0x18000e507  mov     ecx, 40h ; '@'; Size
0x18000e50c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e511  mov     [rsp+58h+var_38], rax
0x18000e516  mov     rcx, rax; this
0x18000e519  call    ??0TraceBuffer@TraceManager@cxl@@QEAA@H@Z; cxl::TraceManager::TraceBuffer::TraceBuffer(int)
0x18000e51e  mov     rbx, rax
0x18000e521  mov     rcx, rax
0x18000e524  jmp     short loc_18000E4EC
0x18000e526  lea     rdx, aTlsindexTlsOut; "tlsIndex != TLS_OUT_OF_INDEXES is false"
0x18000e52d  lea     rcx, [rsp+58h+var_30]
0x18000e532  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000e537  nop
0x18000e538  lea     rcx, [rsp+58h+var_30]
0x18000e53d  call    ?AssertionFailed@Throw@cxl@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Throw::AssertionFailed(std::wstring const &)
```
