# Vml::VmThreadpool::CreateInstance(ulong)

- ea: `0x1401df034`
- end: `0x1401df104`
- name: `?CreateInstance@VmThreadpool@Vml@@SAPEAV12@K@Z`
- size: `208`
- prototype: `struct Vml::VmThreadpool *__fastcall(DWORD cthrdMost)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1401e0dd4`
- `0x14027541c`

## callees

- `0x140021d20`
- `0x140042260`
- `0x140054a90`
- `0x140132d0c`
- `0x14013361c`
- `0x1401de4f0`
- `0x1401df034`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1401df049`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1401df049`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1401df0c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1401df0c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1401df067`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1401df067`

## string_xrefs

- `0x1401df0e2`: `Failed to allocate private threadpool!\n`

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
0x1401df034  mov     [rsp+arg_0], rbx
0x1401df039  mov     [rsp+arg_18], rsi
0x1401df03e  push    rdi
0x1401df03f  sub     rsp, 20h
0x1401df043  mov     esi, ecx
0x1401df045  xor     ebx, ebx
0x1401df047  xor     ecx, ecx; reserved
0x1401df049  call    cs:__imp_CreateThreadpool
0x1401df050  nop     dword ptr [rax+rax+00h]
0x1401df055  mov     rdi, rax
0x1401df058  mov     [rsp+28h+arg_10], rax
0x1401df05d  test    rax, rax
0x1401df060  jz      short loc_1401DF0D2
0x1401df062  mov     edx, esi; cthrdMost
0x1401df064  mov     rcx, rax; ptpp
0x1401df067  call    cs:__imp_SetThreadpoolThreadMaximum
0x1401df06e  nop     dword ptr [rax+rax+00h]
0x1401df073  nop
0x1401df074  mov     esi, 0B8h
0x1401df079  mov     ecx, esi; Size
0x1401df07b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401df080  mov     rbx, rax
0x1401df083  mov     r8d, esi; Size
0x1401df086  xor     edx, edx; Val
0x1401df088  mov     rcx, rax; void *
0x1401df08b  call    memset_0
0x1401df090  mov     rdx, rdi; struct _TP_POOL *
0x1401df093  mov     rcx, rbx; this
0x1401df096  call    ??0VmNewThreadpool@Vml@@AEAA@PEAU_TP_POOL@@@Z; Vml::VmNewThreadpool::VmNewThreadpool(_TP_POOL *)
0x1401df09b  mov     rbx, rax
0x1401df09e  test    rbx, rbx
0x1401df0a1  jz      short loc_1401DF0C3
0x1401df0a3  mov     rax, [rax+8]
0x1401df0a7  movsxd  rcx, dword ptr [rax+4]
0x1401df0ab  add     rcx, 8
0x1401df0af  add     rcx, rbx; this
0x1401df0b2  call    ?IncrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::IncrementUserCount(void)
0x1401df0b7  jmp     short loc_1401DF0F0
0x1401df0b9  mov     rbx, [rsp+28h+arg_8]
0x1401df0be  mov     rdi, [rsp+28h+arg_10]
0x1401df0c3  mov     rcx, rdi; ptpp
0x1401df0c6  call    cs:__imp_CloseThreadpool
0x1401df0cd  nop     dword ptr [rax+rax+00h]
0x1401df0d2  mov     edi, 4000h
0x1401df0d7  mov     ecx, edi
0x1401df0d9  call    VmlIsDebugTraceEnabled
0x1401df0de  test    eax, eax
0x1401df0e0  jz      short loc_1401DF0F0
0x1401df0e2  lea     rdx, aFailedToAlloca_3; "Failed to allocate private threadpool!"...
0x1401df0e9  mov     ecx, edi
0x1401df0eb  call    VmlDebugTrace
0x1401df0f0  mov     rax, rbx
0x1401df0f3  mov     rbx, [rsp+28h+arg_0]
0x1401df0f8  mov     rsi, [rsp+28h+arg_18]
0x1401df0fd  add     rsp, 20h
0x1401df101  pop     rdi
0x1401df102  retn
```
