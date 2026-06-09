# ATL::CComObject<CWdsTransportTftpManager>::CreateInstance(ATL::CComObject<CWdsTransportTftpManager> * *)

- ea: `0x180019750`
- end: `0x180019872`
- name: `?CreateInstance@?$CComObject@VCWdsTransportTftpManager@@@ATL@@SAJPEAPEAV12@@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180019878`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x180018310`
- `0x180018348`
- `0x180019750`
- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800197bf`
- `KERNEL32!InitializeCriticalSection` at `0x1800197bf`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportTftpManager>::CreateInstance(struct _RTL_CRITICAL_SECTION **a1)
{
  unsigned int v3; // r14d
  struct _RTL_CRITICAL_SECTION *v4; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  int v6; // eax
  int v7; // edx

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  v4 = (struct _RTL_CRITICAL_SECTION *)operator new(0x88u);
  v5 = v4;
  if ( v4 )
  {
    v4->LockCount = 0;
    *(_OWORD *)&v4->OwningThread = 0;
    *(_OWORD *)&v4->SpinCount = 0;
    *(_QWORD *)&v4[1].LockCount = 0;
    LOBYTE(v4[1].OwningThread) = 0;
    v4[1].LockSemaphore = 0;
    LODWORD(v4[1].SpinCount) = 0;
    InitializeCriticalSection(v4 + 2);
    v5[3].DebugInfo = 0;
    v5[3].LockCount = 0;
    v5[3].RecursionCount = 0;
    v5->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComObject<CWdsTransportTftpManager>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v5 )
  {
    CWdsTransportServerComObjectRoot::InternalAddRef((CWdsTransportServerComObjectRoot *)&v5->LockCount);
    v6 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)&v5->OwningThread);
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    CWdsTransportServerComObjectRoot::InternalRelease((CWdsTransportServerComObjectRoot *)&v5->LockCount);
    if ( v3 )
    {
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v5->DebugInfo[1].ProcessLocksList.Flink)(v5, 1);
      v5 = 0;
    }
  }
  *a1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180019750  mov     [rsp+arg_18], rbx
0x180019755  mov     [rsp+arg_0], rcx
0x18001975a  push    rdi
0x18001975b  push    r14
0x18001975d  push    r15
0x18001975f  sub     rsp, 20h
0x180019763  mov     r15, rcx
0x180019766  test    rcx, rcx
0x180019769  jnz     short loc_180019775
0x18001976b  mov     eax, 80004003h
0x180019770  jmp     loc_180019862
0x180019775  and     qword ptr [rcx], 0
0x180019779  mov     r14d, 8007000Eh
0x18001977f  mov     [rsp+38h+arg_8], r14d
0x180019784  and     [rsp+38h+arg_10], 0
0x18001978a  mov     ecx, 88h; Size
0x18001978f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019794  mov     rdi, rax
0x180019797  test    rdi, rdi
0x18001979a  jz      short loc_1800197FB
0x18001979c  and     dword ptr [rax+8], 0
0x1800197a0  xorps   xmm0, xmm0
0x1800197a3  xor     eax, eax
0x1800197a5  movups  xmmword ptr [rdi+10h], xmm0
0x1800197a9  movups  xmmword ptr [rdi+20h], xmm0
0x1800197ad  mov     [rdi+30h], rax
0x1800197b1  mov     [rdi+38h], al
0x1800197b4  and     [rdi+40h], rax
0x1800197b8  and     [rdi+48h], eax
0x1800197bb  lea     rcx, [rdi+50h]; lpCriticalSection
0x1800197bf  call    cs:__imp_InitializeCriticalSection
0x1800197c6  nop     dword ptr [rax+rax+00h]
0x1800197cb  and     qword ptr [rdi+78h], 0
0x1800197d0  and     dword ptr [rdi+80h], 0
0x1800197d7  and     dword ptr [rdi+84h], 0
0x1800197de  lea     rax, ??_7?$CComObject@VCWdsTransportTftpManager@@@ATL@@6B@; const ATL::CComObject<CWdsTransportTftpManager>::`vftable'
0x1800197e5  mov     [rdi], rax
0x1800197e8  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800197ef  mov     rax, [rcx]
0x1800197f2  mov     rax, [rax+8]
0x1800197f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197fb  mov     [rsp+38h+arg_10], rdi
0x180019800  jmp     short loc_180019811
0x180019802  mov     r15, [rsp+38h+arg_0]
0x180019807  mov     r14d, [rsp+38h+arg_8]
0x18001980c  mov     rdi, [rsp+38h+arg_10]
0x180019811  test    rdi, rdi
0x180019814  jz      short loc_18001985C
0x180019816  lea     rcx, [rdi+8]; this
0x18001981a  call    ?InternalAddRef@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalAddRef(void)
0x18001981f  lea     rcx, [rdi+10h]; this
0x180019823  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180019828  xor     edx, edx
0x18001982a  test    eax, eax
0x18001982c  cmovs   edx, eax
0x18001982f  xor     r14d, r14d
0x180019832  test    edx, edx
0x180019834  cmovs   r14d, edx
0x180019838  lea     rcx, [rdi+8]; this
0x18001983c  call    ?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalRelease(void)
0x180019841  test    r14d, r14d
0x180019844  jz      short loc_18001985C
0x180019846  mov     rdx, [rdi]
0x180019849  mov     rax, [rdx+40h]
0x18001984d  mov     edx, 1
0x180019852  mov     rcx, rdi
0x180019855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001985a  xor     edi, edi
0x18001985c  mov     [r15], rdi
0x18001985f  mov     eax, r14d
0x180019862  mov     rbx, [rsp+38h+arg_18]
0x180019867  add     rsp, 20h
0x18001986b  pop     r15
0x18001986d  pop     r14
0x18001986f  pop     rdi
0x180019870  retn
```
