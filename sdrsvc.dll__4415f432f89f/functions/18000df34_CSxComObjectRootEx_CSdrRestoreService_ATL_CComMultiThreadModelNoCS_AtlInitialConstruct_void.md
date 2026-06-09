# CSxComObjectRootEx<CSdrRestoreService,ATL::CComMultiThreadModelNoCS>::_AtlInitialConstruct(void)

- ea: `0x18000df34`
- end: `0x18000dff3`
- name: `?_AtlInitialConstruct@?$CSxComObjectRootEx@VCSdrRestoreService@@VCComMultiThreadModelNoCS@ATL@@@@IEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a1f8`
- `0x18000a460`
- `0x18000a8fc`

## callees

- `0x180001554`
- `0x180001578`
- `0x18000df34`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x18000dfca`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x18000dfca`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000df8e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000df8e`
- `ntdll!RtlFreeHeap` at `0x18000df84`
- `ntdll!RtlFreeHeap` at `0x18000df84`

## pseudocode

```c
__int64 __fastcall CSxComObjectRootEx<CSdrRestoreService,ATL::CComMultiThreadModelNoCS>::_AtlInitialConstruct(
        __int64 a1)
{
  __int64 result; // rax
  union _SLIST_HEADER **v2; // rdi
  union _SLIST_HEADER *v3; // rbx
  PSLIST_ENTRY v4; // rax
  union _SLIST_HEADER *v5; // rax
  union _SLIST_HEADER *v6; // rbx

  result = 0;
  if ( CSxComObjectRootEx<CSdrRestoreService,ATL::CComMultiThreadModelNoCS>::s_fEnableRefTrace )
  {
    v2 = (union _SLIST_HEADER **)(a1 + 16);
    v3 = *(union _SLIST_HEADER **)(a1 + 16);
    if ( v3 )
    {
      *v2 = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 )
      {
        while ( 1 )
        {
          v4 = InterlockedPopEntrySList(v3 + 1);
          if ( !v4 )
            break;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, &v4[-17]);
        }
        operator delete(v3);
      }
    }
    if ( v2 )
    {
      *v2 = 0;
      v5 = (union _SLIST_HEADER *)operator new(0x20u);
      v6 = v5;
      if ( v5 )
      {
        v5->Alignment = 1;
        InitializeSListHead(v5 + 1);
        result = 0;
        *v2 = v6;
      }
      else
      {
        return 2147942414LL;
      }
    }
    else
    {
      return 2147942487LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000df34  mov     [rsp+arg_0], rbx
0x18000df39  mov     [rsp+arg_10], rsi
0x18000df3e  push    rdi
0x18000df3f  sub     rsp, 20h
0x18000df43  xor     eax, eax
0x18000df45  cmp     cs:?s_fEnableRefTrace@?$CSxComObjectRootEx@VCSdrRestoreService@@VCComMultiThreadModelNoCS@ATL@@@@0HA, eax; int CSxComObjectRootEx<CSdrRestoreService,ATL::CComMultiThreadModelNoCS>::s_fEnableRefTrace
0x18000df4b  jz      loc_18000DFE3
0x18000df51  lea     rdi, [rcx+10h]
0x18000df55  mov     rbx, [rdi]
0x18000df58  test    rbx, rbx
0x18000df5b  jz      short loc_18000DFA1
0x18000df5d  mov     [rdi], rax
0x18000df60  or      eax, 0FFFFFFFFh
0x18000df63  lock xadd [rbx], eax
0x18000df67  cmp     eax, 1
0x18000df6a  jnz     short loc_18000DFA1
0x18000df6c  jmp     short loc_18000DF8A
0x18000df6e  mov     rcx, gs:60h
0x18000df77  lea     r8, [rax-110h]; P
0x18000df7e  xor     edx, edx; Flags
0x18000df80  mov     rcx, [rcx+30h]; HeapHandle
0x18000df84  call    cs:__imp_RtlFreeHeap
0x18000df8a  lea     rcx, [rbx+10h]; ListHead
0x18000df8e  call    cs:__imp_InterlockedPopEntrySList
0x18000df94  test    rax, rax
0x18000df97  jnz     short loc_18000DF6E
0x18000df99  mov     rcx, rbx; Block
0x18000df9c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dfa1  test    rdi, rdi
0x18000dfa4  jz      short loc_18000DFDE
0x18000dfa6  mov     ecx, 20h ; ' '; Size
0x18000dfab  mov     qword ptr [rdi], 0
0x18000dfb2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dfb7  mov     rbx, rax
0x18000dfba  test    rax, rax
0x18000dfbd  jz      short loc_18000DFD7
0x18000dfbf  lea     rcx, [rax+10h]; ListHead
0x18000dfc3  mov     qword ptr [rax], 1
0x18000dfca  call    cs:__imp_InitializeSListHead
0x18000dfd0  xor     eax, eax
0x18000dfd2  mov     [rdi], rbx
0x18000dfd5  jmp     short loc_18000DFE3
0x18000dfd7  mov     eax, 8007000Eh
0x18000dfdc  jmp     short loc_18000DFE3
0x18000dfde  mov     eax, 80070057h
0x18000dfe3  mov     rbx, [rsp+28h+arg_0]
0x18000dfe8  mov     rsi, [rsp+28h+arg_10]
0x18000dfed  add     rsp, 20h
0x18000dff1  pop     rdi
0x18000dff2  retn
```
