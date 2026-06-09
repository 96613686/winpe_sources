# CVdsService::RemoveDiskFromVdProviders(ushort *)

- ea: `0x14000cac8`
- end: `0x14000cc54`
- name: `?RemoveDiskFromVdProviders@CVdsService@@SAJPEAG@Z`
- size: `396`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004fd50`

## callees

- `0x14000cac8`
- `0x140012c48`
- `0x140013298`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000cb09`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000cb09`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000cb22`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14000cb22`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14000cb57`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14000cb57`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14000cc28`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14000cc28`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000caf0`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000caf0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000cc37`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000cc37`
- `vdsutil!VdsTraceW` at `0x14000cb6c`
- `vdsutil!VdsTraceW` at `0x14000cbc3`
- `vdsutil!VdsTraceW` at `0x14000cc14`
- `vdsutil!VdsTraceW` at `0x14000cb6c`
- `vdsutil!VdsTraceW` at `0x14000cbc3`
- `vdsutil!VdsTraceW` at `0x14000cc14`

## string_xrefs

- `0x14000cae0`: `CVdsService::RemoveDiskFromVdProviders()`
- `0x14000cb65`: `CVdsService::RemoveDiskFromVdProviders, 1`
- `0x14000cbba`: `CVdsService::RemoveDiskFromVdProviders, 2, hr=%lX`
- `0x14000cc0b`: `CVdsService::RemoveDiskFromVdProviders, 3, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsService::RemoveDiskFromVdProviders(unsigned __int16 *a1)
{
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rax
  signed int v3; // eax
  unsigned int v4; // ebx
  signed int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // [rsp+30h] [rbp-50h] BYREF
  __int128 Buf1; // [rsp+38h] [rbp-48h] BYREF
  __int128 Buf2; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v11[16]; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v12[16]; // [rsp+70h] [rbp-10h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v11, 0x5Eu, "CVdsService::RemoveDiskFromVdProviders()");
  Buf1 = 0;
  for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstVirtualDiskProviders, &Buf2);
        ;
        CRtlListIter::Next((CRtlListIter *)&Buf1) )
  {
    Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstVirtualDiskProviders, v12);
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      break;
    v8 = 0;
    EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
    if ( EntryPointer )
    {
      v3 = (**EntryPointer)(EntryPointer, &IID_IVdsVdProviderPrivate, &v8);
      v4 = v3;
      if ( v3 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v8 + 32LL))(v8, a1);
        v6 = v5;
        if ( v5 < 0 )
        {
          VdsLogError(0xC2000009, 0, 0, v5, 0x2000034u, 0);
          VdsTraceW(0, L"CVdsService::RemoveDiskFromVdProviders, 3, hr=%lX", v6);
        }
      }
      else
      {
        VdsLogError(0xC2000009, 0, 0, v3, 0x2000033u, 0);
        VdsTraceW(0, L"CVdsService::RemoveDiskFromVdProviders, 2, hr=%lX", v4);
      }
    }
    else
    {
      VdsTraceW(0, L"CVdsService::RemoveDiskFromVdProviders, 1");
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
  return 0;
}

```

## disassembly

```asm
0x14000cac8  mov     [rsp-8+arg_0], rbx
0x14000cacd  mov     [rsp-8+arg_8], rdi
0x14000cad2  push    rbp
0x14000cad3  mov     rbp, rsp
0x14000cad6  sub     rsp, 80h
0x14000cadd  mov     rdi, rcx
0x14000cae0  lea     r8, aCvdsserviceRem_3; "CVdsService::RemoveDiskFromVdProviders("...
0x14000cae7  mov     edx, 5Eh ; '^'
0x14000caec  lea     rcx, [rbp+var_20]
0x14000caf0  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000caf6  nop
0x14000caf7  xorps   xmm0, xmm0
0x14000cafa  movups  [rbp+Buf1], xmm0
0x14000cafe  lea     rdx, [rbp+Buf2]
0x14000cb02  lea     rcx, ?m_lstVirtualDiskProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstVirtualDiskProviders
0x14000cb09  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14000cb0f  movups  xmm0, xmmword ptr [rax]
0x14000cb12  movdqu  [rbp+Buf1], xmm0
0x14000cb17  lea     rdx, [rbp+var_10]
0x14000cb1b  lea     rcx, ?m_lstVirtualDiskProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstVirtualDiskProviders
0x14000cb22  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14000cb28  movups  xmm0, xmmword ptr [rax]
0x14000cb2b  movdqu  [rbp+Buf2], xmm0
0x14000cb30  mov     r8d, 10h; Size
0x14000cb36  lea     rdx, [rbp+Buf2]; Buf2
0x14000cb3a  lea     rcx, [rbp+Buf1]; Buf1
0x14000cb3e  call    memcmp_0
0x14000cb43  test    eax, eax
0x14000cb45  jz      loc_14000CC33
0x14000cb4b  mov     [rbp+var_50], 0
0x14000cb53  lea     rcx, [rbp+Buf1]
0x14000cb57  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14000cb5d  mov     rcx, rax
0x14000cb60  test    rax, rax
0x14000cb63  jnz     short loc_14000CB78
0x14000cb65  lea     rdx, aCvdsserviceRem_5; "CVdsService::RemoveDiskFromVdProviders,"...
0x14000cb6c  call    cs:__imp_VdsTraceW
0x14000cb72  nop
0x14000cb73  jmp     loc_14000CC1B
0x14000cb78  mov     rax, [rax]
0x14000cb7b  lea     r8, [rbp+var_50]
0x14000cb7f  lea     rdx, IID_IVdsVdProviderPrivate
0x14000cb86  mov     rax, [rax]
0x14000cb89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb8e  mov     ebx, eax
0x14000cb90  test    eax, eax
0x14000cb92  jns     short loc_14000CBCC
0x14000cb94  mov     [rsp+80h+var_58], 0; unsigned __int16 *
0x14000cb9d  mov     [rsp+80h+var_60], 2000033h; unsigned int
0x14000cba5  mov     r9d, eax; unsigned int
0x14000cba8  xor     r8d, r8d; void *
0x14000cbab  xor     edx, edx; unsigned int
0x14000cbad  mov     ecx, 0C2000009h; unsigned int
0x14000cbb2  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000cbb7  mov     r8d, ebx
0x14000cbba  lea     rdx, aCvdsserviceRem_35; "CVdsService::RemoveDiskFromVdProviders,"...
0x14000cbc1  xor     ecx, ecx
0x14000cbc3  call    cs:__imp_VdsTraceW
0x14000cbc9  nop
0x14000cbca  jmp     short loc_14000CC1B
0x14000cbcc  mov     rcx, [rbp+var_50]
0x14000cbd0  mov     rax, [rcx]
0x14000cbd3  mov     rdx, rdi
0x14000cbd6  mov     rax, [rax+20h]
0x14000cbda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cbdf  mov     ebx, eax
0x14000cbe1  test    eax, eax
0x14000cbe3  jns     short loc_14000CC1B
0x14000cbe5  mov     [rsp+80h+var_58], 0; unsigned __int16 *
0x14000cbee  mov     [rsp+80h+var_60], 2000034h; unsigned int
0x14000cbf6  mov     r9d, eax; unsigned int
0x14000cbf9  xor     r8d, r8d; void *
0x14000cbfc  xor     edx, edx; unsigned int
0x14000cbfe  mov     ecx, 0C2000009h; unsigned int
0x14000cc03  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000cc08  mov     r8d, ebx
0x14000cc0b  lea     rdx, aCvdsserviceRem_6; "CVdsService::RemoveDiskFromVdProviders,"...
0x14000cc12  xor     ecx, ecx
0x14000cc14  call    cs:__imp_VdsTraceW
0x14000cc1a  nop
0x14000cc1b  lea     rcx, [rbp+var_50]
0x14000cc1f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000cc24  lea     rcx, [rbp+Buf1]
0x14000cc28  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14000cc2e  jmp     loc_14000CB17
0x14000cc33  lea     rcx, [rbp+var_20]
0x14000cc37  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000cc3d  xor     eax, eax
0x14000cc3f  lea     r11, [rsp+80h+var_s0]
0x14000cc47  mov     rbx, [r11+10h]
0x14000cc4b  mov     rdi, [r11+18h]
0x14000cc4f  mov     rsp, r11
0x14000cc52  pop     rbp
0x14000cc53  retn
```
