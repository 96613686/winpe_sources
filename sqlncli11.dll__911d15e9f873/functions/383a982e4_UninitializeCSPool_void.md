# UninitializeCSPool(void)

- ea: `0x383a982e4`
- end: `0x383a983ba`
- name: `?UninitializeCSPool@@YAXXZ`
- size: `214`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x3838924f8`
- `0x3838925e4`

## callees

- `0x3838be2fc`
- `0x383a982e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a983a9`
- `KERNEL32!GetLastError` at `0x383a983a9`
- `KERNEL32!TlsFree` at `0x383a98398`
- `KERNEL32!TlsFree` at `0x383a98398`
- `KERNEL32!InterlockedPopEntrySList` at `0x383a98314`
- `KERNEL32!InterlockedPopEntrySList` at `0x383a98314`

## pseudocode

```c
void UninitializeCSPool(void)
{
  struct CMPCritSecPool *v0; // rbx
  unsigned int v1; // edi
  PSLIST_ENTRY v2; // rax
  char *v3; // rcx
  char *v4; // rdi
  BOOL v5; // eax

  v0 = g_pMPCritSecPool;
  if ( g_pMPCritSecPool )
  {
    if ( *(_QWORD *)g_pMPCritSecPool )
    {
      v1 = 0;
      if ( *((_DWORD *)g_pMPCritSecPool + 2) )
      {
        do
        {
          while ( 1 )
          {
            v2 = InterlockedPopEntrySList((PSLIST_HEADER)(*(_QWORD *)v0 + 32LL * v1));
            if ( !v2 )
              break;
            if ( v2 != (PSLIST_ENTRY)16 )
              ((void (__fastcall *)(struct _SLIST_ENTRY *, __int64))v2[-1].Next->Next)(&v2[-1], 1);
          }
          ++v1;
        }
        while ( v1 < *((_DWORD *)v0 + 2) );
      }
      v3 = *(char **)v0;
      if ( *(_QWORD *)v0 )
      {
        v4 = v3 - 16;
        `eh vector destructor iterator'(
          v3,
          0x20u,
          *((_DWORD *)v3 - 4),
          _tagCDynQueue<CCriticalSection *>::~_tagCDynQueue<CCriticalSection *>);
        if ( v4 )
          ((void (__fastcall *)(struct IMalloc *, char *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v4);
      }
    }
    ((void (__fastcall *)(struct IMalloc *, struct CMPCritSecPool *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v0);
    g_pMPCritSecPool = 0;
  }
  if ( g_tlsCSTLSIndex != -1 )
  {
    v5 = TlsFree(g_tlsCSTLSIndex);
    g_tlsCSTLSIndex = -1;
    if ( !v5 )
      GetLastError();
  }
}

```

## disassembly

```asm
0x383a982e4  mov     [rsp+arg_0], rbx
0x383a982e9  push    rdi
0x383a982ea  sub     rsp, 20h
0x383a982ee  mov     rbx, cs:?g_pMPCritSecPool@@3PEAVCMPCritSecPool@@EA; CMPCritSecPool * g_pMPCritSecPool
0x383a982f5  test    rbx, rbx
0x383a982f8  jz      loc_383A9838B
0x383a982fe  cmp     qword ptr [rbx], 0
0x383a98302  jz      short loc_383A98373
0x383a98304  xor     edi, edi
0x383a98306  cmp     [rbx+8], edi
0x383a98309  jbe     short loc_383A9833B
0x383a9830b  mov     ecx, edi
0x383a9830d  shl     rcx, 5
0x383a98311  add     rcx, [rbx]; ListHead
0x383a98314  call    cs:__imp_InterlockedPopEntrySList
0x383a9831a  test    rax, rax
0x383a9831d  jz      short loc_383A98334
0x383a9831f  lea     rcx, [rax-10h]
0x383a98323  test    rcx, rcx
0x383a98326  jz      short loc_383A9830B
0x383a98328  mov     rax, [rcx]
0x383a9832b  mov     edx, 1
0x383a98330  call    qword ptr [rax]
0x383a98332  jmp     short loc_383A9830B
0x383a98334  inc     edi
0x383a98336  cmp     edi, [rbx+8]
0x383a98339  jb      short loc_383A9830B
0x383a9833b  mov     rcx, [rbx]; void *
0x383a9833e  test    rcx, rcx
0x383a98341  jz      short loc_383A98373
0x383a98343  lea     rdi, [rcx-10h]
0x383a98347  lea     r9, ??1?$_tagCDynQueue@PEAVCCriticalSection@@@@QEAA@XZ; void (*)(void *)
0x383a9834e  mov     edx, 20h ; ' '; unsigned __int64
0x383a98353  mov     r8d, [rdi]; int
0x383a98356  call    ??_M@YAXPEAX_KHP6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,int,void (*)(void *))
0x383a9835b  test    rdi, rdi
0x383a9835e  jz      short loc_383A98373
0x383a98360  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a98367  mov     rdx, rdi
0x383a9836a  mov     rax, [rcx]
0x383a9836d  call    qword ptr [rax+80h]
0x383a98373  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a9837a  mov     rdx, rbx
0x383a9837d  mov     rax, [rcx]
0x383a98380  call    qword ptr [rax+68h]
0x383a98383  and     cs:?g_pMPCritSecPool@@3PEAVCMPCritSecPool@@EA, 0; CMPCritSecPool * g_pMPCritSecPool
0x383a9838b  mov     ecx, cs:?g_tlsCSTLSIndex@@3VThreadLocalKey@@A; dwTlsIndex
0x383a98391  or      ebx, 0FFFFFFFFh
0x383a98394  cmp     ecx, ebx
0x383a98396  jz      short loc_383A983AF
0x383a98398  call    cs:__imp_TlsFree
0x383a9839e  mov     cs:?g_tlsCSTLSIndex@@3VThreadLocalKey@@A, ebx; ThreadLocalKey g_tlsCSTLSIndex
0x383a983a4  cmp     eax, 1
0x383a983a7  jz      short loc_383A983AF
0x383a983a9  call    cs:__imp_GetLastError
0x383a983af  mov     rbx, [rsp+28h+arg_0]
0x383a983b4  add     rsp, 20h
0x383a983b8  pop     rdi
0x383a983b9  retn
```
