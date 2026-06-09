# Vml::VmThreadpool::CreateInstance(ulong)

- ea: `0x1401ce6e4`
- end: `0x1401ce7b4`
- name: `?CreateInstance@VmThreadpool@Vml@@SAPEAV12@K@Z`
- size: `208`
- prototype: `struct Vml::VmThreadpool *__fastcall(DWORD cthrdMost)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1401d0484`
- `0x14027b53c`

## callees

- `0x140022290`
- `0x1400364a0`
- `0x1400545bc`
- `0x14011edec`
- `0x14011f6fc`
- `0x1401cdb74`
- `0x1401ce6e4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1401ce6f9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1401ce6f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1401ce776`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1401ce776`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1401ce717`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1401ce717`

## string_xrefs

- `0x1401ce792`: `Failed to allocate private threadpool!\n`

## pseudocode

```c
struct Vml::VmThreadpool *__fastcall Vml::VmThreadpool::CreateInstance(DWORD cthrdMost)
{
  __int64 v2; // rbx
  struct _TP_POOL *Threadpool; // rax
  struct _TP_POOL *v4; // rdi
  void *v5; // rbx
  __int64 v6; // rax
  struct _TP_POOL *v8; // [rsp+40h] [rbp+18h]

  v2 = 0;
  Threadpool = CreateThreadpool(0);
  v4 = Threadpool;
  v8 = Threadpool;
  if ( Threadpool )
  {
    SetThreadpoolThreadMaximum(Threadpool, cthrdMost);
    try
    {
      v5 = operator new(0xB8u);
      memset_0(v5, 0, 0xB8u);
      v6 = Vml::VmNewThreadpool::VmNewThreadpool((Vml::VmNewThreadpool *)v5, v4);
    }
    catch ( ... )
    {
      v2 = 0;
      v4 = v8;
      goto LABEL_5;
    }
    v2 = v6;
    if ( v6 )
    {
      Vml::VmSharableObject::IncrementUserCount((Vml::VmSharableObject *)(v6 + *(int *)(*(_QWORD *)(v6 + 8) + 4LL) + 8LL));
      return (struct Vml::VmThreadpool *)v2;
    }
LABEL_5:
    CloseThreadpool(v4);
  }
  if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
    VmlDebugTrace(0x4000, L"Failed to allocate private threadpool!\n");
  return (struct Vml::VmThreadpool *)v2;
}

```

## disassembly

```asm
0x1401ce6e4  mov     [rsp+arg_0], rbx
0x1401ce6e9  mov     [rsp+arg_18], rsi
0x1401ce6ee  push    rdi
0x1401ce6ef  sub     rsp, 20h
0x1401ce6f3  mov     esi, ecx
0x1401ce6f5  xor     ebx, ebx
0x1401ce6f7  xor     ecx, ecx; reserved
0x1401ce6f9  call    cs:__imp_CreateThreadpool
0x1401ce700  nop     dword ptr [rax+rax+00h]
0x1401ce705  mov     rdi, rax
0x1401ce708  mov     [rsp+28h+arg_10], rax
0x1401ce70d  test    rax, rax
0x1401ce710  jz      short loc_1401CE782
0x1401ce712  mov     edx, esi; cthrdMost
0x1401ce714  mov     rcx, rax; ptpp
0x1401ce717  call    cs:__imp_SetThreadpoolThreadMaximum
0x1401ce71e  nop     dword ptr [rax+rax+00h]
0x1401ce723  nop
0x1401ce724  mov     esi, 0B8h
0x1401ce729  mov     ecx, esi; Size
0x1401ce72b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401ce730  mov     rbx, rax
0x1401ce733  mov     r8d, esi; Size
0x1401ce736  xor     edx, edx; Val
0x1401ce738  mov     rcx, rax; void *
0x1401ce73b  call    memset_0
0x1401ce740  mov     rdx, rdi; struct _TP_POOL *
0x1401ce743  mov     rcx, rbx; this
0x1401ce746  call    ??0VmNewThreadpool@Vml@@AEAA@PEAU_TP_POOL@@@Z; Vml::VmNewThreadpool::VmNewThreadpool(_TP_POOL *)
0x1401ce74b  mov     rbx, rax
0x1401ce74e  test    rbx, rbx
0x1401ce751  jz      short loc_1401CE773
0x1401ce753  mov     rax, [rax+8]
0x1401ce757  movsxd  rcx, dword ptr [rax+4]
0x1401ce75b  add     rcx, 8
0x1401ce75f  add     rcx, rbx; this
0x1401ce762  call    ?IncrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::IncrementUserCount(void)
0x1401ce767  jmp     short loc_1401CE7A0
0x1401ce769  mov     rbx, [rsp+28h+arg_8]
0x1401ce76e  mov     rdi, [rsp+28h+arg_10]
0x1401ce773  mov     rcx, rdi; ptpp
0x1401ce776  call    cs:__imp_CloseThreadpool
0x1401ce77d  nop     dword ptr [rax+rax+00h]
0x1401ce782  mov     edi, 4000h
0x1401ce787  mov     ecx, edi
0x1401ce789  call    VmlIsDebugTraceEnabled
0x1401ce78e  test    eax, eax
0x1401ce790  jz      short loc_1401CE7A0
0x1401ce792  lea     rdx, aFailedToAlloca_3; "Failed to allocate private threadpool!"...
0x1401ce799  mov     ecx, edi
0x1401ce79b  call    VmlDebugTrace
0x1401ce7a0  mov     rax, rbx
0x1401ce7a3  mov     rbx, [rsp+28h+arg_0]
0x1401ce7a8  mov     rsi, [rsp+28h+arg_18]
0x1401ce7ad  add     rsp, 20h
0x1401ce7b1  pop     rdi
0x1401ce7b2  retn
```
