# FreeRecoResult(SPRECORESULTINFO *)

- ea: `0x180079fd8`
- end: `0x18007a052`
- name: `?FreeRecoResult@@YAXPEAUSPRECORESULTINFO@@@Z`
- size: `122`
- prototype: `void __fastcall(struct SPRECORESULTINFO *)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010cd4`
- `0x18006c3a8`
- `0x180075788`
- `0x180077e44`

## callees

- `0x180002aac`
- `0x180079fd8`
- `0x18008352c`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079fee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a01e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079fee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a01e`

## pseudocode

```c
void __fastcall FreeRecoResult(struct SPRECORESULTINFO *a1)
{
  ISpPhraseBuilder *pPhrase; // rcx
  __int64 i; // rdi
  SPPHRASEALT *aPhraseAlts; // rcx

  pPhrase = a1->pPhrase;
  if ( pPhrase )
    CoTaskMemFree(pPhrase);
  if ( *(_QWORD *)&a1->ulNumAlts )
  {
    for ( i = 0; (unsigned int)i < a1[1].cbSize; i = (unsigned int)(i + 1) )
      FreeAlternate((struct tagSPPHRASEALT *)(*(_QWORD *)&a1->ulNumAlts + 40 * i));
    CoTaskMemFree(*(LPVOID *)&a1->ulNumAlts);
  }
  aPhraseAlts = a1->aPhraseAlts;
  if ( aPhraseAlts )
    ((void (__fastcall *)(SPPHRASEALT *))aPhraseAlts->pPhrase[2].lpVtbl)(aPhraseAlts);
  CWinHeap::Free((CWinHeap *)&g_heap, a1);
}

```

## disassembly

```asm
0x180079fd8  mov     [rsp+arg_0], rbx
0x180079fdd  push    rdi
0x180079fde  sub     rsp, 20h
0x180079fe2  mov     rbx, rcx
0x180079fe5  mov     rcx, [rcx+38h]; pv
0x180079fe9  test    rcx, rcx
0x180079fec  jz      short loc_180079FF4
0x180079fee  call    cs:__imp_CoTaskMemFree
0x180079ff4  cmp     qword ptr [rbx+48h], 0
0x180079ff9  jz      short loc_18007A024
0x180079ffb  xor     edi, edi
0x180079ffd  cmp     [rbx+50h], edi
0x18007a000  jbe     short loc_18007A01A
0x18007a002  mov     rax, [rbx+48h]
0x18007a006  lea     rcx, [rdi+rdi*4]
0x18007a00a  lea     rcx, [rax+rcx*8]; struct tagSPPHRASEALT *
0x18007a00e  call    ?FreeAlternate@@YAXPEAUtagSPPHRASEALT@@@Z; FreeAlternate(tagSPPHRASEALT *)
0x18007a013  inc     edi
0x18007a015  cmp     edi, [rbx+50h]
0x18007a018  jb      short loc_18007A002
0x18007a01a  mov     rcx, [rbx+48h]; pv
0x18007a01e  call    cs:__imp_CoTaskMemFree
0x18007a024  mov     rcx, [rbx+40h]
0x18007a028  test    rcx, rcx
0x18007a02b  jz      short loc_18007A039
0x18007a02d  mov     rax, [rcx]
0x18007a030  mov     rax, [rax+10h]
0x18007a034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a039  mov     rdx, rbx; void *
0x18007a03c  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18007a043  mov     rbx, [rsp+28h+arg_0]
0x18007a048  add     rsp, 20h
0x18007a04c  pop     rdi
0x18007a04d  jmp     ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
```
