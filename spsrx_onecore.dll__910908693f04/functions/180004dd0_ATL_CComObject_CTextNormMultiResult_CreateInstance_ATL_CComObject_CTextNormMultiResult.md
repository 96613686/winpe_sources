# ATL::CComObject<CTextNormMultiResult>::CreateInstance(ATL::CComObject<CTextNormMultiResult> * *)

- ea: `0x180004dd0`
- end: `0x180004eba`
- name: `?CreateInstance@?$CComObject@VCTextNormMultiResult@@@ATL@@SAJPEAPEAV12@@Z`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180004ee0`

## callees

- `0x180001b50`
- `0x180002f3c`
- `0x180004c40`
- `0x180004dd0`
- `0x180005284`
- `0x18000b6d8`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004e14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004e14`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTextNormMultiResult>::CreateInstance(int **a1)
{
  unsigned int v3; // edi
  LPVOID v4; // rax
  int *v5; // rbx
  int *v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rdi
  int v9; // eax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  if ( g_heap && (v4 = HeapAlloc(g_heap, 0, 0xB8u)) != 0 )
    v5 = (int *)ATL::CComObject<CTextNormMultiResult>::CComObject<CTextNormMultiResult>(v4);
  else
    v5 = 0;
  v6 = v5;
  if ( v5 )
  {
    ATL::CComMultiThreadModel::SafeIncrementReference(v5 + 2);
    v8 = v7 + 8;
    v9 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v7 + 8));
    if ( v9 >= 0 )
    {
      *(_BYTE *)(v8 + 40) = 1;
      v9 = CTextNormMultiResult::FinalConstruct((CTextNormMultiResult *)v5);
    }
    v3 = 0;
    if ( v9 < 0 )
      v3 = v9;
    CTextNormMultiResult::InternalFinalConstructRelease((CTextNormMultiResult *)v5);
    if ( v3 )
    {
      (*(void (__fastcall **)(int *, __int64))(*(_QWORD *)v5 + 240LL))(v5, 1);
      v6 = 0;
    }
    else
    {
      v3 = 0;
    }
  }
  *a1 = v6;
  return v3;
}

```

## disassembly

```asm
0x180004dd0  mov     [rsp+arg_0], rcx
0x180004dd5  push    rbx
0x180004dd6  push    rsi
0x180004dd7  push    rdi
0x180004dd8  push    r14
0x180004dda  sub     rsp, 28h
0x180004dde  mov     rsi, rcx
0x180004de1  test    rcx, rcx
0x180004de4  jnz     short loc_180004DF0
0x180004de6  mov     eax, 80004003h
0x180004deb  jmp     loc_180004EB0
0x180004df0  mov     qword ptr [rcx], 0
0x180004df7  mov     edi, 8007000Eh
0x180004dfc  mov     [rsp+48h+arg_8], edi
0x180004e00  mov     rcx, cs:?g_heap@@3VCHeap@@A; hHeap
0x180004e07  test    rcx, rcx
0x180004e0a  jz      short loc_180004E2C
0x180004e0c  xor     edx, edx; dwFlags
0x180004e0e  mov     r8d, 0B8h; dwBytes
0x180004e14  call    cs:__imp_HeapAlloc
0x180004e1a  test    rax, rax
0x180004e1d  jz      short loc_180004E2C
0x180004e1f  mov     rcx, rax
0x180004e22  call    ??0?$CComObject@VCTextNormMultiResult@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CTextNormMultiResult>::CComObject<CTextNormMultiResult>(void *)
0x180004e27  mov     rbx, rax
0x180004e2a  jmp     short loc_180004E2E
0x180004e2c  xor     ebx, ebx
0x180004e2e  mov     [rsp+48h+arg_10], rbx
0x180004e33  mov     r14, rbx
0x180004e36  mov     [rsp+48h+arg_18], rbx
0x180004e3b  jmp     short loc_180004E50
0x180004e3d  mov     rsi, [rsp+48h+arg_0]
0x180004e42  mov     edi, [rsp+48h+arg_8]
0x180004e46  mov     r14, [rsp+48h+arg_18]
0x180004e4b  mov     rbx, [rsp+48h+arg_10]
0x180004e50  test    rbx, rbx
0x180004e53  jz      short loc_180004EAB
0x180004e55  lea     rcx, [rbx+8]; int *
0x180004e59  call    ?SafeIncrementReference@CComMultiThreadModel@ATL@@SAKPEAJ@Z; ATL::CComMultiThreadModel::SafeIncrementReference(long *)
0x180004e5e  lea     rdi, [rcx+8]
0x180004e62  mov     rcx, rdi; this
0x180004e65  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004e6a  test    eax, eax
0x180004e6c  js      short loc_180004E7A
0x180004e6e  mov     byte ptr [rdi+28h], 1
0x180004e72  mov     rcx, rbx; this
0x180004e75  call    ?FinalConstruct@CTextNormMultiResult@@QEAAJXZ; CTextNormMultiResult::FinalConstruct(void)
0x180004e7a  xor     edi, edi
0x180004e7c  test    eax, eax
0x180004e7e  cmovs   edi, eax
0x180004e81  mov     rcx, rbx; this
0x180004e84  call    ?InternalFinalConstructRelease@CTextNormMultiResult@@QEAAXXZ; CTextNormMultiResult::InternalFinalConstructRelease(void)
0x180004e89  test    edi, edi
0x180004e8b  jz      short loc_180004EA9
0x180004e8d  mov     rax, [rbx]
0x180004e90  mov     edx, 1
0x180004e95  mov     rcx, rbx
0x180004e98  mov     rax, [rax+0F0h]
0x180004e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ea4  xor     r14d, r14d
0x180004ea7  jmp     short loc_180004EAB
0x180004ea9  xor     edi, edi
0x180004eab  mov     [rsi], r14
0x180004eae  mov     eax, edi
0x180004eb0  add     rsp, 28h
0x180004eb4  pop     r14
0x180004eb6  pop     rdi
0x180004eb7  pop     rsi
0x180004eb8  pop     rbx
0x180004eb9  retn
```
