# CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::~CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>(void)

- ea: `0x180050868`
- end: `0x180050996`
- name: `??1?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@QEAA@XZ`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800507a4`

## callees

- `0x180006840`
- `0x18000df40`
- `0x180022f60`
- `0x180050868`
- `0x18005099c`
- `0x180051d60`
- `0x18005cf40`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180050942`
- `ntdll!RtlPopFrame` at `0x180050942`

## pseudocode

```c
void __fastcall CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::~CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>(
        _DWORD *a1)
{
  __int64 v1; // rbp
  char **i; // rsi
  char *v4; // rcx
  __int64 v5; // rbx
  char *v6; // rdi
  char *v7; // rax
  CDequeBase *v8; // rbx
  char *v9; // rbx
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+20h] [rbp-58h] BYREF
  __int64 v11; // [rsp+38h] [rbp-40h]
  int v12; // [rsp+40h] [rbp-38h]

  v1 = 0;
  for ( i = (char **)(a1 + 2); (unsigned int)v1 < *a1; v1 = (unsigned int)(v1 + 1) )
  {
    v7 = *i;
    Frame.Flags = 1;
    Frame.Previous = 0;
    v11 = 544438355;
    v12 = 695;
    v8 = (CDequeBase *)&v7[40 * v1];
    Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucketChain::ClearNoCallback'::`2'::__stc;
    CFrame::BaseEnter((CFrame *)&Frame);
    CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::Clear<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>>(v8);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallExit();
    RtlPopFrame(&Frame);
  }
  v4 = *i;
  if ( *i != (char *)(a1 + 4) && v4 )
  {
    v9 = v4 - 8;
    `vector destructor iterator'(
      v4,
      0x28u,
      *((_QWORD *)v4 - 1),
      CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucketChain::~CBucketChain);
    operator delete(v9);
    *i = 0;
  }
  *a1 = 0;
  v5 = 7;
  *i = 0;
  v6 = (char *)(a1 + 74);
  do
  {
    v6 -= 40;
    CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucketChain::~CBucketChain(v6);
    --v5;
  }
  while ( v5 );
}

```

## disassembly

```asm
0x180050868  push    rbx
0x18005086a  push    rbp
0x18005086b  push    rsi
0x18005086c  push    rdi
0x18005086d  sub     rsp, 58h
0x180050871  mov     rax, cs:__security_cookie
0x180050878  xor     rax, rsp
0x18005087b  mov     [rsp+78h+var_30], rax
0x180050880  xor     ebp, ebp
0x180050882  lea     rsi, [rcx+8]
0x180050886  mov     rdi, rcx
0x180050889  cmp     [rcx], ebp
0x18005088b  ja      short loc_1800508DF
0x18005088d  mov     rcx, [rsi]; void *
0x180050890  lea     rax, [rdi+10h]
0x180050894  cmp     rcx, rax
0x180050897  jnz     loc_180050961
0x18005089d  mov     dword ptr [rdi], 0
0x1800508a3  mov     ebx, 7
0x1800508a8  mov     qword ptr [rsi], 0
0x1800508af  add     rdi, 128h
0x1800508b6  sub     rdi, 28h ; '('
0x1800508ba  mov     rcx, rdi; void *
0x1800508bd  call    ??1CBucketChain@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@QEAA@XZ; CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucketChain::~CBucketChain(void)
0x1800508c2  sub     rbx, 1
0x1800508c6  jnz     short loc_1800508B6
0x1800508c8  mov     rcx, [rsp+78h+var_30]
0x1800508cd  xor     rcx, rsp; StackCookie
0x1800508d0  call    __security_check_cookie
0x1800508d5  add     rsp, 58h
0x1800508d9  pop     rdi
0x1800508da  pop     rsi
0x1800508db  pop     rbp
0x1800508dc  pop     rbx
0x1800508dd  retn
0x1800508df  mov     rax, [rsi]
0x1800508e2  lea     rcx, ds:0[rbp*4]
0x1800508ea  add     rcx, rbp
0x1800508ed  mov     [rsp+78h+Frame.Flags], 1
0x1800508f5  mov     [rsp+78h+Frame.Previous], 0
0x1800508fe  mov     [rsp+78h+var_40], 20737853h
0x180050907  mov     [rsp+78h+var_38], 2B7h
0x18005090f  lea     rbx, [rax+rcx*8]
0x180050913  lea     rax, ?__stc@?1??ClearNoCallback@CBucketChain@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@QEAAXPEBV3@AEA_K@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucketChain::ClearNoCallback(CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0> const *,unsigned __int64 &)'::`2'::__stc
0x18005091a  lea     rcx, [rsp+78h+Frame]; this
0x18005091f  mov     [rsp+78h+Frame.Context], rax
0x180050924  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180050929  mov     rdx, rdi
0x18005092c  mov     rcx, rbx; this
0x18005092f  call    ??$Clear@V?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@@?$CDeque@VCBucket@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@$0CEA@@@QEAAXPEBV?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@P81@EBAXPEAVCBucket@1@@Z@Z; CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::Clear<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>>(CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0> const *,void (CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::*)(CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket *))
0x180050934  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18005093b  jnz     short loc_18005095A
0x18005093d  lea     rcx, [rsp+78h+Frame]; Frame
0x180050942  call    cs:__imp_RtlPopFrame
0x180050949  nop     dword ptr [rax+rax+00h]
0x18005094e  inc     ebp
0x180050950  cmp     ebp, [rdi]
0x180050952  jnb     loc_18005088D
0x180050958  jmp     short loc_1800508DF
0x18005095a  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x18005095f  jmp     short loc_18005093D
0x180050961  test    rcx, rcx
0x180050964  jz      loc_18005089D
0x18005096a  lea     rbx, [rcx-8]
0x18005096e  mov     edx, 28h ; '('; unsigned __int64
0x180050973  mov     r8, [rbx]; unsigned __int64
0x180050976  lea     r9, ??1CBucketChain@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@QEAA@XZ; void (*)(void *)
0x18005097d  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180050982  mov     rcx, rbx; void *
0x180050985  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005098a  mov     qword ptr [rsi], 0
0x180050991  jmp     loc_18005089D
```
