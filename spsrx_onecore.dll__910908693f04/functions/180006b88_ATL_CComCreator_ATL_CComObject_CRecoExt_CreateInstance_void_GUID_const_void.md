# ATL::CComCreator<ATL::CComObject<CRecoExt>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006b88`
- end: `0x180006c87`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCRecoExt@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001760`

## callees

- `0x180001b50`
- `0x180002f48`
- `0x180003cf4`
- `0x1800056f8`
- `0x180006b88`
- `0x180006f0c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006bd9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006bd9`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CRecoExt>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v6; // edi
  LPVOID v7; // rax
  volatile int *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rdi
  int v11; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  if ( g_heap && (v7 = HeapAlloc(g_heap, 0, 0x88u)) != 0 )
    v8 = (volatile int *)ATL::CComObject<CRecoExt>::CComObject<CRecoExt>((__int64)v7);
  else
    v8 = 0;
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread(v8 + 16);
    v10 = v9 + 8;
    v11 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 8));
    if ( v11 >= 0 )
    {
      *(_BYTE *)(v10 + 40) = 1;
      v11 = CRecoExt::FinalConstruct((CRecoExt *)v8);
    }
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    CRecoExt::InternalFinalConstructRelease((CRecoExt *)v8);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(volatile int *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v8 + 376LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180006b88  mov     [rsp+arg_10], r8
0x180006b8d  mov     [rsp+arg_8], rdx
0x180006b92  mov     [rsp+arg_0], rcx
0x180006b97  push    rbx
0x180006b98  push    rsi
0x180006b99  push    rdi
0x180006b9a  push    r14
0x180006b9c  sub     rsp, 28h
0x180006ba0  mov     rsi, r8
0x180006ba3  mov     r14, rdx
0x180006ba6  test    r8, r8
0x180006ba9  jnz     short loc_180006BB5
0x180006bab  mov     eax, 80004003h
0x180006bb0  jmp     loc_180006C7D
0x180006bb5  mov     qword ptr [r8], 0
0x180006bbc  mov     edi, 8007000Eh
0x180006bc1  mov     dword ptr [rsp+48h+arg_0], edi
0x180006bc5  mov     rcx, cs:?g_heap@@3VCHeap@@A; hHeap
0x180006bcc  test    rcx, rcx
0x180006bcf  jz      short loc_180006BF1
0x180006bd1  xor     edx, edx; dwFlags
0x180006bd3  mov     r8d, 88h; dwBytes
0x180006bd9  call    cs:__imp_HeapAlloc
0x180006bdf  test    rax, rax
0x180006be2  jz      short loc_180006BF1
0x180006be4  mov     rcx, rax
0x180006be7  call    ??0?$CComObject@VCRecoExt@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CRecoExt>::CComObject<CRecoExt>(void *)
0x180006bec  mov     rbx, rax
0x180006bef  jmp     short loc_180006BF3
0x180006bf1  xor     ebx, ebx
0x180006bf3  mov     [rsp+48h+arg_18], rbx
0x180006bf8  jmp     short loc_180006C0D
0x180006bfa  mov     rsi, [rsp+48h+arg_10]
0x180006bff  mov     r14, [rsp+48h+arg_8]
0x180006c04  mov     edi, dword ptr [rsp+48h+arg_0]
0x180006c08  mov     rbx, [rsp+48h+arg_18]
0x180006c0d  test    rbx, rbx
0x180006c10  jz      short loc_180006C7B
0x180006c12  lea     rcx, [rbx+40h]; volatile int *
0x180006c16  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180006c1b  lea     rdi, [rcx+8]
0x180006c1f  mov     rcx, rdi; this
0x180006c22  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006c27  test    eax, eax
0x180006c29  js      short loc_180006C37
0x180006c2b  mov     byte ptr [rdi+28h], 1
0x180006c2f  mov     rcx, rbx; this
0x180006c32  call    ?FinalConstruct@CRecoExt@@QEAAJXZ; CRecoExt::FinalConstruct(void)
0x180006c37  xor     edi, edi
0x180006c39  test    eax, eax
0x180006c3b  cmovs   edi, eax
0x180006c3e  mov     rcx, rbx; this
0x180006c41  call    ?InternalFinalConstructRelease@CRecoExt@@QEAAXXZ; CRecoExt::InternalFinalConstructRelease(void)
0x180006c46  test    edi, edi
0x180006c48  jnz     short loc_180006C64
0x180006c4a  mov     rax, [rbx]
0x180006c4d  mov     r8, rsi
0x180006c50  mov     rdx, r14
0x180006c53  mov     rcx, rbx
0x180006c56  mov     rax, [rax]
0x180006c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c5e  mov     edi, eax
0x180006c60  test    eax, eax
0x180006c62  jz      short loc_180006C7B
0x180006c64  mov     rcx, [rbx]
0x180006c67  mov     rax, [rcx+178h]
0x180006c6e  mov     edx, 1
0x180006c73  mov     rcx, rbx
0x180006c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c7b  mov     eax, edi
0x180006c7d  add     rsp, 28h
0x180006c81  pop     r14
0x180006c83  pop     rdi
0x180006c84  pop     rsi
0x180006c85  pop     rbx
0x180006c86  retn
```
