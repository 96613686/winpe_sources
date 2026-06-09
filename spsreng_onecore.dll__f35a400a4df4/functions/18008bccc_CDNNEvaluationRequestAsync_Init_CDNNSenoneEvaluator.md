# CDNNEvaluationRequestAsync::Init(CDNNSenoneEvaluator *)

- ea: `0x18008bccc`
- end: `0x18008bd92`
- name: `?Init@CDNNEvaluationRequestAsync@@QEAAJPEAVCDNNSenoneEvaluator@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(PVOID pv, struct CDNNSenoneEvaluator *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18008bf60`

## callees

- `0x180002470`
- `0x180089e0c`
- `0x18008bccc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bd60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bd60`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008bd52`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008bd52`

## pseudocode

```c
__int64 __fastcall CDNNEvaluationRequestAsync::Init(PTP_WORK *pv, struct CDNNSenoneEvaluator *a2)
{
  int v2; // ebx
  _QWORD *v5; // rax
  __int64 v6; // rdx
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax

  v2 = 0;
  pv[1] = a2;
  if ( pv[2] )
    goto LABEL_12;
  v5 = CWinHeap::Alloc((CWinHeap *)&g_heap, 0x30u, 0);
  if ( !v5 )
  {
    pv[2] = 0;
    return (unsigned int)-2147024882;
  }
  *v5 = 0;
  v5[1] = 0;
  *((_DWORD *)v5 + 4) = 0;
  *((_BYTE *)v5 + 42) = 0;
  pv[2] = (PTP_WORK)v5;
  v6 = *(_QWORD *)(*((_QWORD *)a2 + 2) + 96LL);
  *v5 = *(_QWORD *)v6;
  v2 = CMLP::Initialize((CMLP *)v5, *(_WORD *)(v6 + 40));
  if ( v2 >= 0 )
  {
LABEL_12:
    if ( !*pv )
    {
      ThreadpoolWork = CreateThreadpoolWork(CDNNEvaluationRequestAsync::ThreadpoolCallback, pv, 0);
      *pv = ThreadpoolWork;
      if ( !ThreadpoolWork )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18008bccc  mov     [rsp+arg_8], rbx
0x18008bcd1  mov     [rsp+arg_10], rsi
0x18008bcd6  push    rdi
0x18008bcd7  sub     rsp, 20h
0x18008bcdb  xor     ebx, ebx
0x18008bcdd  mov     [rcx+8], rdx
0x18008bce1  mov     rsi, rdx
0x18008bce4  mov     rdi, rcx
0x18008bce7  cmp     [rcx+10h], rbx
0x18008bceb  jnz     short loc_18008BD3F
0x18008bced  xor     r8d, r8d; bool
0x18008bcf0  lea     edx, [rbx+30h]; unsigned __int64
0x18008bcf3  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18008bcfa  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x18008bcff  mov     [rsp+28h+arg_0], rax
0x18008bd04  mov     rcx, rax; this
0x18008bd07  test    rax, rax
0x18008bd0a  jz      short loc_18008BD87
0x18008bd0c  mov     [rax], rbx
0x18008bd0f  mov     [rax+8], rbx
0x18008bd13  mov     [rax+10h], ebx
0x18008bd16  mov     [rax+2Ah], bl
0x18008bd19  mov     [rdi+10h], rax
0x18008bd1d  test    rax, rax
0x18008bd20  jz      short loc_18008BD8B
0x18008bd22  mov     rax, [rsi+10h]
0x18008bd26  mov     rdx, [rax+60h]
0x18008bd2a  mov     rax, [rdx]
0x18008bd2d  mov     [rcx], rax
0x18008bd30  movzx   edx, word ptr [rdx+28h]; unsigned __int16
0x18008bd34  call    ?Initialize@CMLP@@AEAAJG@Z; CMLP::Initialize(ushort)
0x18008bd39  mov     ebx, eax
0x18008bd3b  test    eax, eax
0x18008bd3d  js      short loc_18008BD75
0x18008bd3f  cmp     qword ptr [rdi], 0
0x18008bd43  jnz     short loc_18008BD75
0x18008bd45  xor     r8d, r8d; pcbe
0x18008bd48  lea     rcx, ?ThreadpoolCallback@CDNNEvaluationRequestAsync@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18008bd4f  mov     rdx, rdi; pv
0x18008bd52  call    cs:__imp_CreateThreadpoolWork
0x18008bd58  mov     [rdi], rax
0x18008bd5b  test    rax, rax
0x18008bd5e  jnz     short loc_18008BD75
0x18008bd60  call    cs:__imp_GetLastError
0x18008bd66  mov     ebx, eax
0x18008bd68  test    eax, eax
0x18008bd6a  jle     short loc_18008BD75
0x18008bd6c  movzx   ebx, ax
0x18008bd6f  or      ebx, 80070000h
0x18008bd75  mov     rsi, [rsp+28h+arg_10]
0x18008bd7a  mov     eax, ebx
0x18008bd7c  mov     rbx, [rsp+28h+arg_8]
0x18008bd81  add     rsp, 20h
0x18008bd85  pop     rdi
0x18008bd86  retn
0x18008bd87  mov     [rdi+10h], rbx
0x18008bd8b  mov     ebx, 8007000Eh
0x18008bd90  jmp     short loc_18008BD75
```
