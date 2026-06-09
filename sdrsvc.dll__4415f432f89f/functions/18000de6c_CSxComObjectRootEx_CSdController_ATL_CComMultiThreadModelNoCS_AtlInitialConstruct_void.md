# CSxComObjectRootEx<CSdController,ATL::CComMultiThreadModelNoCS>::_AtlInitialConstruct(void)

- ea: `0x18000de6c`
- end: `0x18000df2b`
- name: `?_AtlInitialConstruct@?$CSxComObjectRootEx@VCSdController@@VCComMultiThreadModelNoCS@ATL@@@@IEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000a0b4`
- `0x18000a308`
- `0x18000a7a8`

## callees

- `0x180001554`
- `0x180001578`
- `0x18000de6c`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x18000df02`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x18000df02`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000dec6`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000dec6`
- `ntdll!RtlFreeHeap` at `0x18000debc`
- `ntdll!RtlFreeHeap` at `0x18000debc`

## pseudocode

```c
__int64 __fastcall CSxComObjectRootEx<CSdController,ATL::CComMultiThreadModelNoCS>::_AtlInitialConstruct(__int64 a1)
{
  __int64 result; // rax
  union _SLIST_HEADER **v2; // rdi
  union _SLIST_HEADER *v3; // rbx
  PSLIST_ENTRY v4; // rax
  union _SLIST_HEADER *v5; // rax
  union _SLIST_HEADER *v6; // rbx

  result = 0;
  if ( CSxComObjectRootEx<CSdController,ATL::CComMultiThreadModelNoCS>::s_fEnableRefTrace )
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
0x18000de6c  mov     [rsp+arg_0], rbx
0x18000de71  mov     [rsp+arg_10], rsi
0x18000de76  push    rdi
0x18000de77  sub     rsp, 20h
0x18000de7b  xor     eax, eax
0x18000de7d  cmp     cs:?s_fEnableRefTrace@?$CSxComObjectRootEx@VCSdController@@VCComMultiThreadModelNoCS@ATL@@@@0HA, eax; int CSxComObjectRootEx<CSdController,ATL::CComMultiThreadModelNoCS>::s_fEnableRefTrace
0x18000de83  jz      loc_18000DF1B
0x18000de89  lea     rdi, [rcx+10h]
0x18000de8d  mov     rbx, [rdi]
0x18000de90  test    rbx, rbx
0x18000de93  jz      short loc_18000DED9
0x18000de95  mov     [rdi], rax
0x18000de98  or      eax, 0FFFFFFFFh
0x18000de9b  lock xadd [rbx], eax
0x18000de9f  cmp     eax, 1
0x18000dea2  jnz     short loc_18000DED9
0x18000dea4  jmp     short loc_18000DEC2
0x18000dea6  mov     rcx, gs:60h
0x18000deaf  lea     r8, [rax-110h]; P
0x18000deb6  xor     edx, edx; Flags
0x18000deb8  mov     rcx, [rcx+30h]; HeapHandle
0x18000debc  call    cs:__imp_RtlFreeHeap
0x18000dec2  lea     rcx, [rbx+10h]; ListHead
0x18000dec6  call    cs:__imp_InterlockedPopEntrySList
0x18000decc  test    rax, rax
0x18000decf  jnz     short loc_18000DEA6
0x18000ded1  mov     rcx, rbx; Block
0x18000ded4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ded9  test    rdi, rdi
0x18000dedc  jz      short loc_18000DF16
0x18000dede  mov     ecx, 20h ; ' '; Size
0x18000dee3  mov     qword ptr [rdi], 0
0x18000deea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000deef  mov     rbx, rax
0x18000def2  test    rax, rax
0x18000def5  jz      short loc_18000DF0F
0x18000def7  lea     rcx, [rax+10h]; ListHead
0x18000defb  mov     qword ptr [rax], 1
0x18000df02  call    cs:__imp_InitializeSListHead
0x18000df08  xor     eax, eax
0x18000df0a  mov     [rdi], rbx
0x18000df0d  jmp     short loc_18000DF1B
0x18000df0f  mov     eax, 8007000Eh
0x18000df14  jmp     short loc_18000DF1B
0x18000df16  mov     eax, 80070057h
0x18000df1b  mov     rbx, [rsp+28h+arg_0]
0x18000df20  mov     rsi, [rsp+28h+arg_10]
0x18000df25  add     rsp, 20h
0x18000df29  pop     rdi
0x18000df2a  retn
```
