# ATL::CComAggObject<CWMPRichPreviewExt>::Release(void)

- ea: `0x14000c550`
- end: `0x14000c5d4`
- name: `?Release@?$CComAggObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ`
- size: `132`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001008`
- `0x140002370`
- `0x140004784`
- `0x14000c550`
- `0x14000c818`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CWMPRichPreviewExt>::Release(_DWORD *a1)
{
  int v1; // esi
  unsigned int v3; // esi
  CExeModule *v4; // rcx

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[2] = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_1400153D8);
      if ( a1 )
      {
        a1[2] = 1;
        *(_QWORD *)a1 = &ATL::CComAggObject<CWMPRichPreviewExt>::`vftable';
        CWMPRichPreviewExt::FinalRelease((CWMPRichPreviewExt *)(a1 + 4));
        CExeModule::Unlock(v4);
        CWMPRichPreviewExt::~CWMPRichPreviewExt((CWMPRichPreviewExt *)(a1 + 4));
        operator delete(a1);
      }
      CExeModule::Unlock((CExeModule *)a1);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14000c550  mov     [rsp+arg_0], rbx
0x14000c555  mov     [rsp+arg_8], rsi
0x14000c55a  push    rdi
0x14000c55b  sub     rsp, 20h
0x14000c55f  mov     esi, [rcx+8]
0x14000c562  mov     rdi, rcx
0x14000c565  cmp     esi, 7FFFFFFFh
0x14000c56b  jnz     short loc_14000C574
0x14000c56d  mov     esi, 7FFFFFFEh
0x14000c572  jmp     short loc_14000C5C2
0x14000c574  sub     esi, 1
0x14000c577  mov     [rcx+8], esi
0x14000c57a  jnz     short loc_14000C5C2
0x14000c57c  lock inc cs:dword_1400153D8
0x14000c583  test    rdi, rdi
0x14000c586  jz      short loc_14000C5BD
0x14000c588  lea     rax, ??_7?$CComAggObject@VCWMPRichPreviewExt@@@ATL@@6B@; const ATL::CComAggObject<CWMPRichPreviewExt>::`vftable'
0x14000c58f  mov     dword ptr [rcx+8], 1
0x14000c596  mov     [rcx], rax
0x14000c599  add     rcx, 10h; this
0x14000c59d  call    ?FinalRelease@CWMPRichPreviewExt@@QEAAJXZ; CWMPRichPreviewExt::FinalRelease(void)
0x14000c5a2  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x14000c5a7  lea     rcx, [rdi+10h]; this
0x14000c5ab  call    ??1CWMPRichPreviewExt@@QEAA@XZ; CWMPRichPreviewExt::~CWMPRichPreviewExt(void)
0x14000c5b0  mov     edx, 0B0h; unsigned __int64
0x14000c5b5  mov     rcx, rdi; void *
0x14000c5b8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c5bd  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x14000c5c2  mov     rbx, [rsp+28h+arg_0]
0x14000c5c7  mov     eax, esi
0x14000c5c9  mov     rsi, [rsp+28h+arg_8]
0x14000c5ce  add     rsp, 20h
0x14000c5d2  pop     rdi
0x14000c5d3  retn
```
