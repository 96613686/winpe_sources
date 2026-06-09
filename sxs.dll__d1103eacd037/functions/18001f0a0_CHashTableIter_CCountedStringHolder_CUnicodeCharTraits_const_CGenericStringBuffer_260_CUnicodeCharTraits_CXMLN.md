# CHashTableIter<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::Next(void)

- ea: `0x18001f0a0`
- end: `0x18001f2b5`
- name: `?Next@?$CHashTableIter@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@QEAAXXZ`
- size: `533`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001db00`
- `0x1800507a4`

## callees

- `0x18001c2c8`
- `0x18001f0a0`
- `0x1800536b8`
- `0x18005cf40`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18001f1e2`
- `ntdll!RtlPopFrame` at `0x18001f267`
- `ntdll!RtlPopFrame` at `0x18001f1e2`
- `ntdll!RtlPopFrame` at `0x18001f267`
- `ntdll!RtlPushFrame` at `0x18001f0f5`
- `ntdll!RtlPushFrame` at `0x18001f1a0`
- `ntdll!RtlPushFrame` at `0x18001f0f5`
- `ntdll!RtlPushFrame` at `0x18001f1a0`

## pseudocode

```c
void __fastcall CHashTableIter<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::Next(
        __int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rax
  _DWORD *v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  _QWORD *v8; // rsi
  char v9; // cl
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+20h] [rbp-78h] BYREF
  __int64 v13; // [rsp+38h] [rbp-60h]
  int v14; // [rsp+40h] [rbp-58h]
  struct _TEB_ACTIVE_FRAME v15; // [rsp+48h] [rbp-50h] BYREF
  __int64 v16; // [rsp+60h] [rbp-38h]
  int v17; // [rsp+68h] [rbp-30h]

  v15.Flags = 1;
  v15.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CHashTableIter<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::Next'::`2'::__stc;
  v15.Previous = 0;
  v16 = 544438355;
  v17 = 959;
  RtlPushFrame(&v15);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    if ( !*(_BYTE *)(a1 + 28) )
      *(_QWORD *)(a1 + 16) = **(_QWORD **)(a1 + 16);
    *(_BYTE *)(a1 + 28) = 0;
    v3 = *(_QWORD *)(a1 + 16);
    if ( !v3 || v3 == v2 )
    {
      v4 = *(_DWORD **)a1;
      v5 = (unsigned int)(*(_DWORD *)(a1 + 24) + 1);
      *(_DWORD *)(a1 + 24) = v5;
      if ( (unsigned int)v5 < *v4 )
      {
        do
        {
          v6 = 5 * v5;
          Frame.Flags = 1;
          v7 = *((_QWORD *)v4 + 1);
          Frame.Previous = 0;
          Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CDequeIterator<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::Rebind'::`2'::__stc;
          v13 = 544438355;
          v8 = (_QWORD *)(v7 + 8 * v6);
          v14 = 542;
          RtlPushFrame(&Frame);
          v9 = g_FusionEnterExitTracingEnabled;
          if ( g_FusionEnterExitTracingEnabled )
          {
            FusionpTraceCallEntry();
            v9 = g_FusionEnterExitTracingEnabled;
          }
          if ( *(_QWORD *)(a1 + 16) )
            *(_QWORD *)(a1 + 16) = 0;
          *(_QWORD *)(a1 + 8) = v8;
          if ( v8 )
            *(_QWORD *)(a1 + 16) = *v8;
          if ( v9 )
            FusionpTraceCallExit();
          RtlPopFrame(&Frame);
          if ( *(_QWORD *)(a1 + 16) )
            *(_QWORD *)(a1 + 16) = 0;
          v10 = *(_QWORD **)(a1 + 8);
          v11 = (_QWORD *)*v10;
          *(_QWORD *)(a1 + 16) = *v10;
          if ( v11 && v11 != v10 )
            break;
          ++*(_DWORD *)(a1 + 24);
          v4 = *(_DWORD **)a1;
          v5 = *(unsigned int *)(a1 + 24);
        }
        while ( (unsigned int)v5 < **(_DWORD **)a1 );
      }
      if ( *(_DWORD *)(a1 + 24) == **(_DWORD **)a1 )
        CConstDequeIterator<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::Unbind(a1 + 8);
    }
  }
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallExit();
  RtlPopFrame(&v15);
}

```

## disassembly

```asm
0x18001f0a0  mov     r11, rsp
0x18001f0a3  sub     rsp, 98h
0x18001f0aa  mov     rax, cs:__security_cookie
0x18001f0b1  xor     rax, rsp
0x18001f0b4  mov     [rsp+98h+var_28], rax
0x18001f0b9  mov     [r11+10h], rbx
0x18001f0bd  lea     rax, ?__stc@?1??Next@?$CHashTableIter@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@QEAAXXZ@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CHashTableIter<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::Next(void)'::`2'::__stc
0x18001f0c4  mov     [rsp+98h+var_50.Flags], 1
0x18001f0cc  mov     rbx, rcx
0x18001f0cf  mov     [r11+18h], rbp
0x18001f0d3  lea     rcx, [r11-50h]; Frame
0x18001f0d7  mov     [r11-40h], rax
0x18001f0db  xor     ebp, ebp
0x18001f0dd  mov     [r11-48h], rbp
0x18001f0e1  mov     qword ptr [r11-38h], 20737853h
0x18001f0e9  mov     [rsp+98h+var_30], 3BFh
0x18001f0f1  mov     [r11-10h], rdi
0x18001f0f5  call    cs:__imp_RtlPushFrame
0x18001f0fc  nop     dword ptr [rax+rax+00h]
0x18001f101  cmp     cs:g_FusionEnterExitTracingEnabled, bpl
0x18001f108  jnz     loc_18001F289
0x18001f10e  mov     rdx, [rbx+8]
0x18001f112  test    rdx, rdx
0x18001f115  jz      loc_18001F241
0x18001f11b  cmp     [rbx+1Ch], bpl
0x18001f11f  jnz     short loc_18001F12C
0x18001f121  mov     rax, [rbx+10h]
0x18001f125  mov     rcx, [rax]
0x18001f128  mov     [rbx+10h], rcx
0x18001f12c  mov     [rbx+1Ch], bpl
0x18001f130  mov     rax, [rbx+10h]
0x18001f134  test    rax, rax
0x18001f137  jz      short loc_18001F142
0x18001f139  cmp     rax, rdx
0x18001f13c  jnz     loc_18001F241
0x18001f142  mov     eax, [rbx+18h]
0x18001f145  mov     rdx, [rbx]
0x18001f148  inc     eax
0x18001f14a  mov     [rbx+18h], eax
0x18001f14d  cmp     eax, [rdx]
0x18001f14f  jnb     loc_18001F22E
0x18001f155  mov     [rsp+98h+var_8], rsi
0x18001f15d  mov     [rsp+98h+var_18], r14
0x18001f165  lea     r14, ?__stc@?1??Rebind@?$CDequeIterator@VCBucket@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@$0CEA@@@QEAAXPEAV?$CDeque@VCBucket@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@$0CEA@@@@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CDequeIterator<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::Rebind(CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576> *)'::`2'::__stc
0x18001f16c  lea     rcx, [rax+rax*4]
0x18001f170  mov     [rsp+98h+Frame.Flags], 1
0x18001f178  mov     rax, [rdx+8]
0x18001f17c  mov     [rsp+98h+Frame.Previous], rbp
0x18001f181  mov     [rsp+98h+Frame.Context], r14
0x18001f186  mov     [rsp+98h+var_60], 20737853h
0x18001f18f  lea     rsi, [rax+rcx*8]
0x18001f193  mov     [rsp+98h+var_58], 21Eh
0x18001f19b  lea     rcx, [rsp+98h+Frame]; Frame
0x18001f1a0  call    cs:__imp_RtlPushFrame
0x18001f1a7  nop     dword ptr [rax+rax+00h]
0x18001f1ac  movzx   ecx, cs:g_FusionEnterExitTracingEnabled
0x18001f1b3  test    cl, cl
0x18001f1b5  jnz     loc_18001F293
0x18001f1bb  cmp     [rbx+10h], rbp
0x18001f1bf  jz      short loc_18001F1C5
0x18001f1c1  mov     [rbx+10h], rbp
0x18001f1c5  mov     [rbx+8], rsi
0x18001f1c9  test    rsi, rsi
0x18001f1cc  jz      short loc_18001F1D5
0x18001f1ce  mov     rax, [rsi]
0x18001f1d1  mov     [rbx+10h], rax
0x18001f1d5  test    cl, cl
0x18001f1d7  jnz     loc_18001F2A4
0x18001f1dd  lea     rcx, [rsp+98h+Frame]; Frame
0x18001f1e2  call    cs:__imp_RtlPopFrame
0x18001f1e9  nop     dword ptr [rax+rax+00h]
0x18001f1ee  cmp     [rbx+10h], rbp
0x18001f1f2  jz      short loc_18001F1F8
0x18001f1f4  mov     [rbx+10h], rbp
0x18001f1f8  mov     rcx, [rbx+8]
0x18001f1fc  mov     rax, [rcx]
0x18001f1ff  mov     [rbx+10h], rax
0x18001f203  test    rax, rax
0x18001f206  jz      short loc_18001F20D
0x18001f208  cmp     rax, rcx
0x18001f20b  jnz     short loc_18001F21E
0x18001f20d  inc     dword ptr [rbx+18h]
0x18001f210  mov     rdx, [rbx]
0x18001f213  mov     eax, [rbx+18h]
0x18001f216  cmp     eax, [rdx]
0x18001f218  jb      loc_18001F16C
0x18001f21e  mov     rsi, [rsp+98h+var_8]
0x18001f226  mov     r14, [rsp+98h+var_18]
0x18001f22e  mov     rax, [rbx]
0x18001f231  mov     edx, [rax]
0x18001f233  cmp     [rbx+18h], edx
0x18001f236  jnz     short loc_18001F241
0x18001f238  lea     rcx, [rbx+8]
0x18001f23c  call    ?Unbind@?$CConstDequeIterator@VCBucket@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@$0CEA@@@QEAAXXZ; CConstDequeIterator<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::Unbind(void)
0x18001f241  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18001f248  mov     rdi, [rsp+98h+var_10]
0x18001f250  mov     rbp, [rsp+98h+arg_10]
0x18001f258  mov     rbx, [rsp+98h+arg_8]
0x18001f260  jnz     short loc_18001F2AE
0x18001f262  lea     rcx, [rsp+98h+var_50]; Frame
0x18001f267  call    cs:__imp_RtlPopFrame
0x18001f26e  nop     dword ptr [rax+rax+00h]
0x18001f273  mov     rcx, [rsp+98h+var_28]
0x18001f278  xor     rcx, rsp; StackCookie
0x18001f27b  call    __security_check_cookie
0x18001f280  add     rsp, 98h
0x18001f287  retn
0x18001f289  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18001f28e  jmp     loc_18001F10E
0x18001f293  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18001f298  movzx   ecx, cs:g_FusionEnterExitTracingEnabled
0x18001f29f  jmp     loc_18001F1BB
0x18001f2a4  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x18001f2a9  jmp     loc_18001F1DD
0x18001f2ae  call    ?FusionpTraceCallExit@@YAXXZ; FusionpTraceCallExit(void)
0x18001f2b3  jmp     short loc_18001F262
```
