# cxl::TraceManager::Acquire(void)

- ea: `0x18000e250`
- end: `0x18000e300`
- name: `?Acquire@TraceManager@cxl@@AEAAPEAUTraceBuffer@12@XZ`
- size: `176`
- prototype: `struct cxl::TraceManager::TraceBuffer *__fastcall(cxl::TraceManager *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e3f4`
- `0x18000e70c`
- `0x18000e740`

## callees

- `0x180002b50`
- `0x180002f70`
- `0x18000cd9c`
- `0x18000df0c`
- `0x18000e250`
- `0x18000e660`
- `0x18000fcec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000e273`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000e273`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000e28b`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000e28b`

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
0x18000e250  push    rbx
0x18000e252  sub     rsp, 50h
0x18000e256  mov     rax, cs:__security_cookie
0x18000e25d  xor     rax, rsp
0x18000e260  mov     [rsp+58h+var_10], rax
0x18000e265  mov     rbx, rcx
0x18000e268  mov     ecx, cs:?tlsIndex@?$ThreadLocal@UTraceBuffer@TraceManager@cxl@@@cxl@@0HA; dwTlsIndex
0x18000e26e  cmp     ecx, 0FFFFFFFFh
0x18000e271  jz      short loc_18000E2E3
0x18000e273  call    cs:__imp_TlsGetValue
0x18000e27a  nop     dword ptr [rax+rax+00h]
0x18000e27f  test    rax, rax
0x18000e282  jnz     short loc_18000E2B0
0x18000e284  lea     rcx, [rbx+0E0h]; ListHead
0x18000e28b  call    cs:__imp_InterlockedPopEntrySList
0x18000e292  nop     dword ptr [rax+rax+00h]
0x18000e297  test    rax, rax
0x18000e29a  jz      short loc_18000E2C4
0x18000e29c  lea     rbx, [rax-20h]
0x18000e2a0  test    rbx, rbx
0x18000e2a3  jz      short loc_18000E2C4
0x18000e2a5  mov     rcx, rbx; lpTlsValue
0x18000e2a8  call    ?TlsSet@?$ThreadLocal@UTraceBuffer@TraceManager@cxl@@@cxl@@SAXPEAUTraceBuffer@TraceManager@2@@Z; cxl::ThreadLocal<cxl::TraceManager::TraceBuffer>::TlsSet(cxl::TraceManager::TraceBuffer *)
0x18000e2ad  mov     rax, rbx
0x18000e2b0  mov     rcx, [rsp+58h+var_10]
0x18000e2b5  xor     rcx, rsp; StackCookie
0x18000e2b8  call    __security_check_cookie
0x18000e2bd  add     rsp, 50h
0x18000e2c1  pop     rbx
0x18000e2c2  retn
0x18000e2c4  mov     ecx, 40h ; '@'; Size
0x18000e2c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e2ce  mov     [rsp+58h+var_38], rax
0x18000e2d3  mov     rcx, rax; this
0x18000e2d6  call    ??0TraceBuffer@TraceManager@cxl@@QEAA@H@Z; cxl::TraceManager::TraceBuffer::TraceBuffer(int)
0x18000e2db  mov     rbx, rax
0x18000e2de  mov     rcx, rax
0x18000e2e1  jmp     short loc_18000E2A8
0x18000e2e3  lea     rdx, aTlsindexTlsOut; "tlsIndex != TLS_OUT_OF_INDEXES is false"
0x18000e2ea  lea     rcx, [rsp+58h+var_30]
0x18000e2ef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000e2f4  nop
0x18000e2f5  lea     rcx, [rsp+58h+var_30]
0x18000e2fa  call    ?AssertionFailed@Throw@cxl@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Throw::AssertionFailed(std::wstring const &)
```
