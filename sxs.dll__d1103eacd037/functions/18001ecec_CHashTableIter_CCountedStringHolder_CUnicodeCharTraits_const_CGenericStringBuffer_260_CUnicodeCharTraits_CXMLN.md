# CHashTableIter<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::Reset(void)

- ea: `0x18001ecec`
- end: `0x18001ee8a`
- name: `?Reset@?$CHashTableIter@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@QEAAXXZ`
- size: `414`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001db00`
- `0x1800507a4`

## callees

- `0x18000df40`
- `0x18001c2c8`
- `0x18001ecec`
- `0x1800536b8`
- `0x18005cf40`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18001edda`
- `ntdll!RtlPopFrame` at `0x18001ee3b`
- `ntdll!RtlPopFrame` at `0x18001edda`
- `ntdll!RtlPopFrame` at `0x18001ee3b`
- `ntdll!RtlPushFrame` at `0x18001ed95`
- `ntdll!RtlPushFrame` at `0x18001ed95`

## pseudocode

```c
void __fastcall CHashTableIter<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::Reset(
        __int64 a1)
{
  _DWORD *v2; // rdx
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rax
  _QWORD *v6; // rdi
  char v7; // cl
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+20h] [rbp-60h] BYREF
  __int64 v11; // [rsp+38h] [rbp-48h]
  int v12; // [rsp+40h] [rbp-40h]
  struct _TEB_ACTIVE_FRAME v13; // [rsp+48h] [rbp-38h] BYREF
  __int64 v14; // [rsp+60h] [rbp-20h]
  int v15; // [rsp+68h] [rbp-18h]

  v13.Flags = 1;
  v13.Previous = 0;
  v13.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CHashTableIter<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::Reset'::`2'::__stc;
  v14 = 544438355;
  v15 = 896;
  CFrame::BaseEnter((CFrame *)&v13);
  v2 = *(_DWORD **)a1;
  v3 = 0;
  *(_BYTE *)(a1 + 28) = 0;
  *(_DWORD *)(a1 + 24) = 0;
  if ( *v2 )
  {
    do
    {
      v4 = 5 * v3;
      Frame.Flags = 1;
      v5 = *((_QWORD *)v2 + 1);
      Frame.Previous = 0;
      v11 = 544438355;
      v12 = 542;
      v6 = (_QWORD *)(v5 + 8 * v4);
      Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CDequeIterator<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::Rebind'::`2'::__stc;
      RtlPushFrame(&Frame);
      v7 = g_FusionEnterExitTracingEnabled;
      if ( g_FusionEnterExitTracingEnabled )
      {
        FusionpTraceCallEntry();
        v7 = g_FusionEnterExitTracingEnabled;
      }
      if ( *(_QWORD *)(a1 + 16) )
        *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 8) = v6;
      if ( v6 )
        *(_QWORD *)(a1 + 16) = *v6;
      if ( v7 )
        FusionpTraceCallExit();
      RtlPopFrame(&Frame);
      if ( *(_QWORD *)(a1 + 16) )
        *(_QWORD *)(a1 + 16) = 0;
      v8 = *(_QWORD **)(a1 + 8);
      v9 = (_QWORD *)*v8;
      *(_QWORD *)(a1 + 16) = *v8;
      if ( v9 && v9 != v8 )
        break;
      ++*(_DWORD *)(a1 + 24);
      v2 = *(_DWORD **)a1;
      v3 = *(unsigned int *)(a1 + 24);
    }
    while ( (unsigned int)v3 < **(_DWORD **)a1 );
  }
  if ( *(_DWORD *)(a1 + 24) == **(_DWORD **)a1 )
    CConstDequeIterator<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::Unbind(a1 + 8);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallExit();
  RtlPopFrame(&v13);
}

```

## disassembly

```asm
0x18001ecec  mov     [rsp-8+arg_8], rbx
0x18001ecf1  mov     [rsp-8+arg_10], rdi
0x18001ecf6  push    rbp
0x18001ecf7  mov     rbp, rsp
0x18001ecfa  sub     rsp, 80h
0x18001ed01  mov     rax, cs:__security_cookie
0x18001ed08  xor     rax, rsp
0x18001ed0b  mov     [rbp+var_10], rax
0x18001ed0f  mov     rbx, rcx
0x18001ed12  mov     [rbp+var_38.Flags], 1
0x18001ed19  lea     rax, ?__stc@?1??Reset@?$CHashTableIter@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@QEAAXXZ@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CHashTableIter<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::Reset(void)'::`2'::__stc
0x18001ed20  mov     [rbp+var_38.Previous], 0
0x18001ed28  lea     rcx, [rbp+var_38]; this
0x18001ed2c  mov     [rbp+var_38.Context], rax
0x18001ed30  mov     [rbp+var_20], 20737853h
0x18001ed38  mov     [rbp+var_18], 380h
0x18001ed3f  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18001ed44  mov     rdx, [rbx]
0x18001ed47  xor     eax, eax
0x18001ed49  mov     byte ptr [rbx+1Ch], 0
0x18001ed4d  mov     dword ptr [rbx+18h], 0
0x18001ed54  cmp     [rdx], eax
0x18001ed56  jbe     loc_18001EE1B
0x18001ed5c  lea     rcx, [rax+rax*4]
0x18001ed60  mov     [rbp+Frame.Flags], 1
0x18001ed67  mov     rax, [rdx+8]
0x18001ed6b  mov     [rbp+Frame.Previous], 0
0x18001ed73  mov     [rbp+var_48], 20737853h
0x18001ed7b  mov     [rbp+var_40], 21Eh
0x18001ed82  lea     rdi, [rax+rcx*8]
0x18001ed86  lea     rax, ?__stc@?1??Rebind@?$CDequeIterator@VCBucket@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@$0CEA@@@QEAAXPEAV?$CDeque@VCBucket@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@$0CEA@@@@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CDequeIterator<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::Rebind(CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576> *)'::`2'::__stc
0x18001ed8d  lea     rcx, [rbp+Frame]; Frame
0x18001ed91  mov     [rbp+Frame.Context], rax
0x18001ed95  call    cs:__imp_RtlPushFrame
0x18001ed9c  nop     dword ptr [rax+rax+00h]
0x18001eda1  mov     cl, cs:g_FusionEnterExitTracingEnabled
0x18001eda7  test    cl, cl
0x18001eda9  jnz     loc_18001EE69
0x18001edaf  cmp     qword ptr [rbx+10h], 0
0x18001edb4  jz      short loc_18001EDBE
0x18001edb6  mov     qword ptr [rbx+10h], 0
0x18001edbe  mov     [rbx+8], rdi
0x18001edc2  test    rdi, rdi
0x18001edc5  jz      short loc_18001EDCE
0x18001edc7  mov     rax, [rdi]
0x18001edca  mov     [rbx+10h], rax
0x18001edce  test    cl, cl
0x18001edd0  jnz     loc_18001EE79
0x18001edd6  lea     rcx, [rbp+Frame]; Frame
0x18001edda  call    cs:__imp_RtlPopFrame
0x18001ede1  nop     dword ptr [rax+rax+00h]
0x18001ede6  cmp     qword ptr [rbx+10h], 0
0x18001edeb  jz      short loc_18001EDF5
0x18001eded  mov     qword ptr [rbx+10h], 0
0x18001edf5  mov     rcx, [rbx+8]
0x18001edf9  mov     rax, [rcx]
0x18001edfc  mov     [rbx+10h], rax
0x18001ee00  test    rax, rax
0x18001ee03  jz      short loc_18001EE0A
0x18001ee05  cmp     rax, rcx
0x18001ee08  jnz     short loc_18001EE1B
0x18001ee0a  inc     dword ptr [rbx+18h]
0x18001ee0d  mov     rdx, [rbx]
0x18001ee10  mov     eax, [rbx+18h]
0x18001ee13  cmp     eax, [rdx]
0x18001ee15  jb      loc_18001ED5C
0x18001ee1b  mov     rax, [rbx]
0x18001ee1e  mov     ecx, [rax]
0x18001ee20  cmp     [rbx+18h], ecx
0x18001ee23  jnz     short loc_18001EE2E
0x18001ee25  lea     rcx, [rbx+8]
0x18001ee29  call    ?Unbind@?$CConstDequeIterator@VCBucket@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@$0CEA@@@QEAAXXZ; CConstDequeIterator<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::Unbind(void)
0x18001ee2e  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18001ee35  jnz     short loc_18001EE83
0x18001ee37  lea     rcx, [rbp+var_38]; Frame
0x18001ee3b  call    cs:__imp_RtlPopFrame
0x18001ee42  nop     dword ptr [rax+rax+00h]
0x18001ee47  mov     rcx, [rbp+var_10]
0x18001ee4b  xor     rcx, rsp; StackCookie
0x18001ee4e  call    __security_check_cookie
0x18001ee53  lea     r11, [rsp+80h+var_s0]
0x18001ee5b  mov     rbx, [r11+18h]
0x18001ee5f  mov     rdi, [r11+20h]
0x18001ee63  mov     rsp, r11
0x18001ee66  pop     rbp
0x18001ee67  retn
0x18001ee69  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18001ee6e  mov     cl, cs:g_FusionEnterExitTracingEnabled
0x18001ee74  jmp     loc_18001EDAF
0x18001ee79  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x18001ee7e  jmp     loc_18001EDD6
0x18001ee83  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x18001ee88  jmp     short loc_18001EE37
```
