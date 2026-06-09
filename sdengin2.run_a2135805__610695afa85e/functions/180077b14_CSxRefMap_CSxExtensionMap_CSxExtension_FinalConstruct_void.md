# CSxRefMap<CSxExtensionMap,CSxExtension>::FinalConstruct(void)

- ea: `0x180077b14`
- end: `0x180077bd3`
- name: `?FinalConstruct@?$CSxRefMap@VCSxExtensionMap@@VCSxExtension@@@@AEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180075c70`

## callees

- `0x180077b14`
- `0x18007aee0`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180077bb9`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180077bb9`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180077b53`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180077b53`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180077b3a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180077b3a`
- `ole32!CoTaskMemFree` at `0x180077b67`
- `ole32!CoTaskMemFree` at `0x180077b67`
- `ole32!CoTaskMemAlloc` at `0x180077b7f`
- `ole32!CoTaskMemAlloc` at `0x180077b7f`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CSxExtensionMap,CSxExtension>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CSxExtension *v3; // rbx
  CSxExtension **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CSxExtension **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CSxExtension::Release(v3);
    }
    CoTaskMemFree(v5);
    *(_QWORD *)TableContext = 0;
  }
  v6 = (struct _RTL_AVL_TABLE *)CoTaskMemAlloc(0x68u);
  *(_QWORD *)TableContext = v6;
  if ( v6 )
  {
    v7 = 0;
    RtlInitializeGenericTableAvl(
      v6,
      CSxRefMap<CSxExtensionMap,CSxExtension>::_CompareRoutine,
      CSxRefMap<CSxDirRuleMap,CSxDirRule>::_AllocateRoutine,
      CSxRefMap<CSdMediaMapFinder,CSdMedia>::_FreeRoutine,
      (PVOID)TableContext);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x180077b14  mov     [rsp+arg_0], rbx
0x180077b19  push    rdi
0x180077b1a  sub     rsp, 30h
0x180077b1e  mov     rdi, rcx
0x180077b21  lock inc dword ptr [rcx+8]
0x180077b25  cmp     qword ptr [rcx], 0
0x180077b29  jz      short loc_180077B7A
0x180077b2b  lock inc dword ptr [rcx+8]
0x180077b2f  mov     rcx, [rcx]
0x180077b32  jmp     short loc_180077B51
0x180077b34  mov     rbx, [rax]
0x180077b37  mov     rdx, rax; Buffer
0x180077b3a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180077b41  nop     dword ptr [rax+rax+00h]
0x180077b46  mov     rcx, rbx; this
0x180077b49  call    ?Release@CSxExtension@@QEAAKXZ; CSxExtension::Release(void)
0x180077b4e  mov     rcx, [rdi]; Table
0x180077b51  mov     dl, 1; Restart
0x180077b53  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180077b5a  nop     dword ptr [rax+rax+00h]
0x180077b5f  mov     rcx, [rdi]; pv
0x180077b62  test    rax, rax
0x180077b65  jnz     short loc_180077B34
0x180077b67  call    cs:__imp_CoTaskMemFree
0x180077b6e  nop     dword ptr [rax+rax+00h]
0x180077b73  mov     qword ptr [rdi], 0
0x180077b7a  mov     ecx, 68h ; 'h'; cb
0x180077b7f  call    cs:__imp_CoTaskMemAlloc
0x180077b86  nop     dword ptr [rax+rax+00h]
0x180077b8b  mov     [rdi], rax
0x180077b8e  test    rax, rax
0x180077b91  jnz     short loc_180077B9A
0x180077b93  mov     ebx, 8007000Eh
0x180077b98  jmp     short loc_180077BC5
0x180077b9a  xor     ebx, ebx
0x180077b9c  mov     [rsp+38h+TableContext], rdi; TableContext
0x180077ba1  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180077ba8  mov     rcx, rax; Table
0x180077bab  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180077bb2  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxExtensionMap@@VCSxExtension@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180077bb9  call    cs:__imp_RtlInitializeGenericTableAvl
0x180077bc0  nop     dword ptr [rax+rax+00h]
0x180077bc5  mov     eax, ebx
0x180077bc7  mov     rbx, [rsp+38h+arg_0]
0x180077bcc  add     rsp, 30h
0x180077bd0  pop     rdi
0x180077bd1  retn
```
