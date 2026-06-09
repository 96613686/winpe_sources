# _pSpUtilsSetTextLogPath

- ea: `0x180017708`
- end: `0x1800177da`
- name: `_pSpUtilsSetTextLogPath`
- size: `210`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180016424`
- `0x1800164e0`

## callees

- `0x18000cba0`
- `0x180017708`
- `0x180018460`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001776a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800177a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001776a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800177a5`

## pseudocode

```c
__int64 __fastcall pSpUtilsSetTextLogPath(__int64 a1, int a2)
{
  void *v3; // rbx
  bool v4; // zf
  const wchar_t *v5; // rsi
  const wchar_t *v6; // rdx
  void *v9; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  v3 = 0;
  v4 = a2 == 0;
  v5 = L"setupapi.dev.log";
  v6 = L"setupapi.app.log";
  if ( v4 )
    v5 = L"setupapi.offline.log";
  if ( !a2 )
    v6 = L"setupapi.offline.log";
  if ( (unsigned int)pSetupAppendPath(a1, v6, &v9) )
  {
    v3 = v9;
    if ( qword_180023868 )
      HeapFree(hHeap, 0, qword_180023868);
    qword_180023868 = v3;
  }
  if ( (unsigned int)pSetupAppendPath(a1, v5, &v9) )
  {
    v3 = v9;
    if ( lpMem )
      HeapFree(hHeap, 0, lpMem);
    lpMem = v3;
  }
  if ( v3 )
    pSetupMakeSurePathExists(v3);
  TextLogOffline = a2 == 0;
  return 1;
}

```

## disassembly

```asm
0x180017708  push    rbx
0x18001770a  push    rbp
0x18001770b  push    rsi
0x18001770c  push    rdi
0x18001770d  sub     rsp, 28h
0x180017711  mov     edi, edx
0x180017713  mov     [rsp+48h+arg_10], 0
0x18001771c  lea     rax, aSetupapiOfflin; "setupapi.offline.log"
0x180017723  xor     ebx, ebx
0x180017725  test    edx, edx
0x180017727  lea     rsi, aSetupapiDevLog; "setupapi.dev.log"
0x18001772e  lea     rdx, aSetupapiAppLog; "setupapi.app.log"
0x180017735  mov     rbp, rcx
0x180017738  cmovz   rsi, rax
0x18001773c  lea     r8, [rsp+48h+arg_10]
0x180017741  test    edi, edi
0x180017743  cmovz   rdx, rax
0x180017747  call    pSetupAppendPath
0x18001774c  test    eax, eax
0x18001774e  jz      short loc_180017777
0x180017750  mov     r8, cs:qword_180023868; lpMem
0x180017757  mov     rbx, [rsp+48h+arg_10]
0x18001775c  test    r8, r8
0x18001775f  jz      short loc_180017770
0x180017761  mov     rcx, cs:hHeap; hHeap
0x180017768  xor     edx, edx; dwFlags
0x18001776a  call    cs:__imp_HeapFree
0x180017770  mov     cs:qword_180023868, rbx
0x180017777  lea     r8, [rsp+48h+arg_10]
0x18001777c  mov     rdx, rsi
0x18001777f  mov     rcx, rbp
0x180017782  call    pSetupAppendPath
0x180017787  test    eax, eax
0x180017789  jz      short loc_1800177B2
0x18001778b  mov     r8, cs:lpMem; lpMem
0x180017792  mov     rbx, [rsp+48h+arg_10]
0x180017797  test    r8, r8
0x18001779a  jz      short loc_1800177AB
0x18001779c  mov     rcx, cs:hHeap; hHeap
0x1800177a3  xor     edx, edx; dwFlags
0x1800177a5  call    cs:__imp_HeapFree
0x1800177ab  mov     cs:lpMem, rbx
0x1800177b2  test    rbx, rbx
0x1800177b5  jz      short loc_1800177BF
0x1800177b7  mov     rcx, rbx
0x1800177ba  call    pSetupMakeSurePathExists
0x1800177bf  xor     eax, eax
0x1800177c1  test    edi, edi
0x1800177c3  setz    al
0x1800177c6  mov     cs:TextLogOffline, eax
0x1800177cc  mov     eax, 1
0x1800177d1  add     rsp, 28h
0x1800177d5  pop     rdi
0x1800177d6  pop     rsi
0x1800177d7  pop     rbp
0x1800177d8  pop     rbx
0x1800177d9  retn
```
