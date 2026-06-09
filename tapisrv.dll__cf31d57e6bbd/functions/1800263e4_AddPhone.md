# AddPhone

- ea: `0x1800263e4`
- end: `0x1800265f9`
- name: `AddPhone`
- size: `533`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002c8fc`

## callees

- `0x18001ea48`
- `0x1800263e4`
- `0x18002a508`
- `0x18002ba10`
- `0x18002c8d4`
- `0x18003dc84`
- `0x18003fb7c`
- `0x180040010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800264fe`
- `KERNEL32!HeapAlloc` at `0x180026587`
- `KERNEL32!HeapAlloc` at `0x1800264fe`
- `KERNEL32!HeapAlloc` at `0x180026587`
- `KERNEL32!GetLastError` at `0x18002645f`
- `KERNEL32!GetLastError` at `0x18002645f`
- `KERNEL32!CreateMutexW` at `0x180026451`
- `KERNEL32!CreateMutexW` at `0x180026451`

## string_xrefs

- `0x180026465`: `AddPhone: MyCreateMutex failed, err=%u`

## pseudocode

```c
__int64 __fastcall AddPhone(__int64 a1, unsigned int a2, int a3)
{
  unsigned int (__fastcall *v5)(_QWORD, __int64, __int64, unsigned int *); // rax
  HANDLE MutexW; // rsi
  DWORD LastError; // eax
  unsigned int *i; // rbx
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // r10
  unsigned __int64 v14; // rcx
  _DWORD *v15; // rax
  _DWORD *v16; // rdi
  unsigned __int64 v17; // rcx
  __int64 v18; // rcx
  ULONG pulResult; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v20; // [rsp+68h] [rbp+20h] BYREF

  v20 = 0;
  pulResult = 0;
  v5 = *(unsigned int (__fastcall **)(_QWORD, __int64, __int64, unsigned int *))(a1 + 848);
  if ( !v5 )
    return 2415919133LL;
  if ( v5(a2, 65539, 196609, &v20) )
    return 2415919132LL;
  MutexW = CreateMutexW(0, 0, 0);
  if ( !MutexW )
  {
    LastError = GetLastError();
    TRACELogPrint(65538, "AddPhone: MyCreateMutex failed, err=%u", LastError);
    return 2415919132LL;
  }
  for ( i = (unsigned int *)qword_180051930; *((_QWORD *)i + 1); i = (unsigned int *)*((_QWORD *)i + 1) )
    ;
  v11 = *i;
  if ( i[1] != (_DWORD)v11 )
    goto LABEL_24;
  if ( !a3 )
  {
    if ( ULongSub(v11, 1u, &pulResult) >= 0 )
    {
      v17 = 40LL * pulResult;
      if ( v17 <= 0xFFFFFFFF && (int)v17 + 56 >= (unsigned int)v17 )
      {
        v16 = HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(v17 + 56));
        if ( v16 )
        {
          *v16 = *i;
          *((_QWORD *)i + 1) = v16;
          goto LABEL_23;
        }
      }
    }
LABEL_27:
    MyCloseMutex(MutexW);
    return 2415919130LL;
  }
  v12 = 2 * v11;
  if ( v12 > 0xFFFFFFFF )
    goto LABEL_27;
  pulResult = v12;
  if ( ULongSub(v12, 1u, &pulResult) < 0 )
    goto LABEL_27;
  v14 = 40LL * pulResult;
  if ( v14 > v13 )
    goto LABEL_27;
  if ( (int)v14 + 56 < (unsigned int)v14 )
    goto LABEL_27;
  v15 = HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(v14 + 56));
  v16 = v15;
  if ( !v15 )
    goto LABEL_27;
  *v15 = 2 * *i;
  v15[1] = *i;
  memcpy_0(v15 + 4, i + 4, 40LL * *i);
  ServerFree(i);
  qword_180051930 = v16;
LABEL_23:
  i = v16;
LABEL_24:
  v18 = 5LL * i[1];
  i[2 * v18 + 4] = v20;
  *(_QWORD *)&i[2 * v18 + 8] = MutexW;
  *(_QWORD *)&i[2 * v18 + 10] = a1;
  ++i[1];
  if ( gbNTServer )
    GetPermPhoneIDAndInsertInTable(a1, a2, v20);
  return 0;
}

```

## disassembly

```asm
0x1800263e4  mov     rax, rsp
0x1800263e7  mov     [rax+10h], rbx
0x1800263eb  mov     [rax+18h], rbp
0x1800263ef  push    rsi
0x1800263f0  push    rdi
0x1800263f1  push    r14
0x1800263f3  sub     rsp, 30h
0x1800263f7  mov     dword ptr [rax+20h], 0
0x1800263fe  mov     edi, r8d
0x180026401  mov     dword ptr [rax+8], 0
0x180026408  mov     r14d, edx
0x18002640b  mov     rax, [rcx+350h]
0x180026412  mov     rbp, rcx
0x180026415  test    rax, rax
0x180026418  jnz     short loc_180026424
0x18002641a  mov     eax, 9000001Dh
0x18002641f  jmp     loc_1800265D7
0x180026424  lea     r9, [rsp+48h+arg_18]
0x180026429  mov     edx, 10003h
0x18002642e  mov     r8d, 30001h
0x180026434  mov     ecx, r14d
0x180026437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002643c  test    eax, eax
0x18002643e  jz      short loc_18002644A
0x180026440  mov     eax, 9000001Ch
0x180026445  jmp     loc_1800265D7
0x18002644a  xor     r8d, r8d; lpName
0x18002644d  xor     edx, edx; bInitialOwner
0x18002644f  xor     ecx, ecx; lpMutexAttributes
0x180026451  call    cs:__imp_CreateMutexW
0x180026457  mov     rsi, rax
0x18002645a  test    rax, rax
0x18002645d  jnz     short loc_18002647B
0x18002645f  call    cs:__imp_GetLastError
0x180026465  lea     rdx, aAddphoneMycrea; "AddPhone: MyCreateMutex failed, err=%u"
0x18002646c  mov     ecx, 10002h
0x180026471  mov     r8d, eax
0x180026474  call    TRACELogPrint
0x180026479  jmp     short loc_180026440
0x18002647b  mov     rbx, cs:qword_180051930
0x180026482  jmp     short loc_180026488
0x180026484  mov     rbx, [rbx+8]
0x180026488  cmp     qword ptr [rbx+8], 0
0x18002648d  jnz     short loc_180026484
0x18002648f  mov     ecx, [rbx]; ulMinuend
0x180026491  cmp     [rbx+4], ecx
0x180026494  jnz     loc_1800265A0
0x18002649a  test    edi, edi
0x18002649c  jz      loc_180026543
0x1800264a2  add     rcx, rcx; ulMinuend
0x1800264a5  mov     r10d, 0FFFFFFFFh
0x1800264ab  cmp     rcx, r10
0x1800264ae  ja      loc_1800265EA
0x1800264b4  lea     r8, [rsp+48h+pulResult]; pulResult
0x1800264b9  mov     [rsp+48h+pulResult], ecx
0x1800264bd  mov     edx, 1; ulSubtrahend
0x1800264c2  call    ULongSub
0x1800264c7  test    eax, eax
0x1800264c9  js      loc_1800265EA
0x1800264cf  mov     eax, [rsp+48h+pulResult]
0x1800264d3  lea     rcx, [rax+rax*4]
0x1800264d7  shl     rcx, 3
0x1800264db  cmp     rcx, r10
0x1800264de  ja      loc_1800265EA
0x1800264e4  lea     eax, [rcx+38h]
0x1800264e7  cmp     eax, ecx
0x1800264e9  jb      loc_1800265EA
0x1800264ef  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800264f6  mov     edx, 8; dwFlags
0x1800264fb  mov     r8d, eax; dwBytes
0x1800264fe  call    cs:__imp_HeapAlloc
0x180026504  mov     rdi, rax
0x180026507  test    rax, rax
0x18002650a  jz      loc_1800265EA
0x180026510  mov     edx, [rbx]
0x180026512  lea     rcx, [rax+10h]; void *
0x180026516  add     edx, edx
0x180026518  mov     [rax], edx
0x18002651a  mov     edx, [rbx]
0x18002651c  mov     [rax+4], edx
0x18002651f  mov     edx, [rbx]
0x180026521  lea     r8, [rdx+rdx*4]
0x180026525  shl     r8, 3; Size
0x180026529  lea     rdx, [rbx+10h]; Src
0x18002652d  call    memcpy_0
0x180026532  mov     rcx, rbx; lpMem
0x180026535  call    ServerFree
0x18002653a  mov     cs:qword_180051930, rdi
0x180026541  jmp     short loc_18002659D
0x180026543  lea     r8, [rsp+48h+pulResult]; pulResult
0x180026548  mov     edx, 1; ulSubtrahend
0x18002654d  call    ULongSub
0x180026552  test    eax, eax
0x180026554  js      loc_1800265EA
0x18002655a  mov     eax, [rsp+48h+pulResult]
0x18002655e  mov     r10d, 0FFFFFFFFh
0x180026564  lea     rcx, [rax+rax*4]
0x180026568  shl     rcx, 3
0x18002656c  cmp     rcx, r10
0x18002656f  ja      short loc_1800265EA
0x180026571  lea     eax, [rcx+38h]
0x180026574  cmp     eax, ecx
0x180026576  jb      short loc_1800265EA
0x180026578  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002657f  mov     edx, 8; dwFlags
0x180026584  mov     r8d, eax; dwBytes
0x180026587  call    cs:__imp_HeapAlloc
0x18002658d  mov     rdi, rax
0x180026590  test    rax, rax
0x180026593  jz      short loc_1800265EA
0x180026595  mov     eax, [rbx]
0x180026597  mov     [rdi], eax
0x180026599  mov     [rbx+8], rdi
0x18002659d  mov     rbx, rdi
0x1800265a0  mov     eax, [rbx+4]
0x1800265a3  lea     rcx, [rax+rax*4]
0x1800265a7  mov     eax, [rsp+48h+arg_18]
0x1800265ab  mov     [rbx+rcx*8+10h], eax
0x1800265af  mov     [rbx+rcx*8+20h], rsi
0x1800265b4  mov     [rbx+rcx*8+28h], rbp
0x1800265b9  inc     dword ptr [rbx+4]
0x1800265bc  cmp     cs:gbNTServer, 0
0x1800265c3  jz      short loc_1800265D5
0x1800265c5  mov     r8d, [rsp+48h+arg_18]
0x1800265ca  mov     edx, r14d
0x1800265cd  mov     rcx, rbp
0x1800265d0  call    GetPermPhoneIDAndInsertInTable
0x1800265d5  xor     eax, eax
0x1800265d7  mov     rbx, [rsp+48h+arg_8]
0x1800265dc  mov     rbp, [rsp+48h+arg_10]
0x1800265e1  add     rsp, 30h
0x1800265e5  pop     r14
0x1800265e7  pop     rdi
0x1800265e8  pop     rsi
0x1800265e9  retn
0x1800265ea  mov     rcx, rsi
0x1800265ed  call    MyCloseMutex
0x1800265f2  mov     eax, 9000001Ah
0x1800265f7  jmp     short loc_1800265D7
```
