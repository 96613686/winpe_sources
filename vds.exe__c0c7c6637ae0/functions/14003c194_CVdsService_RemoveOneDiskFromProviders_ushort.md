# CVdsService::RemoveOneDiskFromProviders(ushort *)

- ea: `0x14003c194`
- end: `0x14003c33a`
- name: `?RemoveOneDiskFromProviders@CVdsService@@SAHPEAG@Z`
- size: `422`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400070c0`
- `0x14004fd50`

## callees

- `0x140012c48`
- `0x140013298`
- `0x14003bf0c`
- `0x14003c194`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003c1d3`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003c1d3`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003c1ec`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003c1ec`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003c221`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003c221`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003c32e`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003c32e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003c1b8`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003c1b8`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003c2d7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003c2d7`
- `vdsutil!VdsTraceW` at `0x14003c236`
- `vdsutil!VdsTraceW` at `0x14003c28d`
- `vdsutil!VdsTraceW` at `0x14003c31a`
- `vdsutil!VdsTraceW` at `0x14003c236`
- `vdsutil!VdsTraceW` at `0x14003c28d`
- `vdsutil!VdsTraceW` at `0x14003c31a`

## string_xrefs

- `0x14003c1a8`: `CVdsService::RemoveOneDiskFromProviders()`
- `0x14003c22f`: `CVdsService::RemoveOneDiskFromProviders(), 1`
- `0x14003c284`: `CVdsService::RemoveOneDiskFromProviders(), 2, hr=%lX`
- `0x14003c311`: `CVdsService::RemoveOneDiskFromProviders(), 3, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsService::RemoveOneDiskFromProviders(wchar_t *String1)
{
  unsigned int v2; // edi
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rax
  signed int v4; // eax
  unsigned int v5; // ebx
  signed int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // [rsp+30h] [rbp-19h] BYREF
  __int128 Buf1; // [rsp+38h] [rbp-11h] BYREF
  __int128 Buf2; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v12[16]; // [rsp+60h] [rbp+17h] BYREF
  _BYTE v13[48]; // [rsp+70h] [rbp+27h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v12, 0x5Eu, "CVdsService::RemoveOneDiskFromProviders()");
  Buf1 = 0;
  v2 = 0;
  for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstSoftwareProviders, &Buf2);
        ;
        CRtlListIter::Next((CRtlListIter *)&Buf1) )
  {
    Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstSoftwareProviders, v13);
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      break;
    v9 = 0;
    EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
    if ( EntryPointer )
    {
      v4 = (**EntryPointer)(EntryPointer, &IID_IVdsSwProviderPrivate, &v9);
      v5 = v4;
      if ( v4 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, wchar_t *))(*(_QWORD *)v9 + 32LL))(v9, String1);
        v7 = v6;
        if ( v6 < 0 )
        {
          VdsLogError(0xC2000009, 0, 0, v6, 0x2000013u, 0);
          VdsTraceW(0, L"CVdsService::RemoveOneDiskFromProviders(), 3, hr=%lX", v7);
        }
        else if ( !v6 )
        {
          v2 = 1;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
          if ( dword_14009B190 != v7 )
            CVdsService::RemoveLunIdFromMap(String1);
          break;
        }
      }
      else
      {
        VdsLogError(0xC2000009, 0, 0, v4, 0x2000012u, 0);
        VdsTraceW(0, L"CVdsService::RemoveOneDiskFromProviders(), 2, hr=%lX", v5);
      }
    }
    else
    {
      VdsTraceW(0, L"CVdsService::RemoveOneDiskFromProviders(), 1");
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v12);
  return v2;
}

```

## disassembly

```asm
0x14003c194  push    rbp
0x14003c196  push    rbx
0x14003c197  push    rsi
0x14003c198  push    rdi
0x14003c199  lea     rbp, [rsp-3Fh]
0x14003c19e  sub     rsp, 88h
0x14003c1a5  mov     rsi, rcx
0x14003c1a8  lea     r8, aCvdsserviceRem_9; "CVdsService::RemoveOneDiskFromProviders"...
0x14003c1af  mov     edx, 5Eh ; '^'
0x14003c1b4  lea     rcx, [rbp+57h+var_40]
0x14003c1b8  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003c1be  nop
0x14003c1bf  xorps   xmm0, xmm0
0x14003c1c2  movups  [rbp+57h+Buf1], xmm0
0x14003c1c6  xor     edi, edi
0x14003c1c8  lea     rdx, [rbp+57h+Buf2]
0x14003c1cc  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x14003c1d3  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14003c1d9  movups  xmm0, xmmword ptr [rax]
0x14003c1dc  movdqu  [rbp+57h+Buf1], xmm0
0x14003c1e1  lea     rdx, [rbp+57h+var_30]
0x14003c1e5  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x14003c1ec  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14003c1f2  movups  xmm0, xmmword ptr [rax]
0x14003c1f5  movdqu  [rbp+57h+Buf2], xmm0
0x14003c1fa  mov     r8d, 10h; Size
0x14003c200  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14003c204  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14003c208  call    memcmp_0
0x14003c20d  test    eax, eax
0x14003c20f  jz      loc_14003C2D3
0x14003c215  mov     [rbp+57h+var_70], 0
0x14003c21d  lea     rcx, [rbp+57h+Buf1]
0x14003c221  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14003c227  mov     rcx, rax
0x14003c22a  test    rax, rax
0x14003c22d  jnz     short loc_14003C242
0x14003c22f  lea     rdx, aCvdsserviceRem_34; "CVdsService::RemoveOneDiskFromProviders"...
0x14003c236  call    cs:__imp_VdsTraceW
0x14003c23c  nop
0x14003c23d  jmp     loc_14003C321
0x14003c242  mov     rax, [rax]
0x14003c245  lea     r8, [rbp+57h+var_70]
0x14003c249  lea     rdx, IID_IVdsSwProviderPrivate
0x14003c250  mov     rax, [rax]
0x14003c253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c258  mov     ebx, eax
0x14003c25a  test    eax, eax
0x14003c25c  jns     short loc_14003C299
0x14003c25e  mov     [rsp+0A0h+var_78], 0; unsigned __int16 *
0x14003c267  mov     [rsp+0A0h+var_80], 2000012h; unsigned int
0x14003c26f  mov     r9d, eax; unsigned int
0x14003c272  xor     r8d, r8d; void *
0x14003c275  xor     edx, edx; unsigned int
0x14003c277  mov     ecx, 0C2000009h; unsigned int
0x14003c27c  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14003c281  mov     r8d, ebx
0x14003c284  lea     rdx, aCvdsserviceRem_7; "CVdsService::RemoveOneDiskFromProviders"...
0x14003c28b  xor     ecx, ecx
0x14003c28d  call    cs:__imp_VdsTraceW
0x14003c293  nop
0x14003c294  jmp     loc_14003C321
0x14003c299  mov     rcx, [rbp+57h+var_70]
0x14003c29d  mov     rax, [rcx]
0x14003c2a0  mov     rdx, rsi
0x14003c2a3  mov     rax, [rax+20h]
0x14003c2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c2ac  mov     ebx, eax
0x14003c2ae  test    eax, eax
0x14003c2b0  js      short loc_14003C2EB
0x14003c2b2  test    eax, eax
0x14003c2b4  jnz     short loc_14003C321
0x14003c2b6  lea     edi, [rax+1]
0x14003c2b9  lea     rcx, [rbp+57h+var_70]
0x14003c2bd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003c2c2  cmp     cs:dword_14009B190, ebx
0x14003c2c8  jz      short loc_14003C2D3
0x14003c2ca  mov     rcx, rsi; String1
0x14003c2cd  call    ?RemoveLunIdFromMap@CVdsService@@CAJPEAG@Z; CVdsService::RemoveLunIdFromMap(ushort *)
0x14003c2d2  nop
0x14003c2d3  lea     rcx, [rbp+57h+var_40]
0x14003c2d7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003c2dd  mov     eax, edi
0x14003c2df  add     rsp, 88h
0x14003c2e6  pop     rdi
0x14003c2e7  pop     rsi
0x14003c2e8  pop     rbx
0x14003c2e9  pop     rbp
0x14003c2ea  retn
0x14003c2eb  mov     [rsp+0A0h+var_78], 0; unsigned __int16 *
0x14003c2f4  mov     [rsp+0A0h+var_80], 2000013h; unsigned int
0x14003c2fc  mov     r9d, ebx; unsigned int
0x14003c2ff  xor     r8d, r8d; void *
0x14003c302  xor     edx, edx; unsigned int
0x14003c304  mov     ecx, 0C2000009h; unsigned int
0x14003c309  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14003c30e  mov     r8d, ebx
0x14003c311  lea     rdx, aCvdsserviceRem_24; "CVdsService::RemoveOneDiskFromProviders"...
0x14003c318  xor     ecx, ecx
0x14003c31a  call    cs:__imp_VdsTraceW
0x14003c320  nop
0x14003c321  lea     rcx, [rbp+57h+var_70]
0x14003c325  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003c32a  lea     rcx, [rbp+57h+Buf1]
0x14003c32e  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14003c334  jmp     loc_14003C1E1
```
