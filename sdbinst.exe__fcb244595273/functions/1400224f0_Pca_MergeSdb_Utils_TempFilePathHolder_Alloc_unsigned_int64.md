# Pca::MergeSdb::Utils::TempFilePathHolder::Alloc(unsigned __int64)

- ea: `0x1400224f0`
- end: `0x140022574`
- name: `?Alloc@TempFilePathHolder@Utils@MergeSdb@Pca@@QEAAX_K@Z`
- size: `132`
- prototype: `void __fastcall(void **this, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140024958`

## callees

- `0x140020f9c`
- `0x1400224f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140022522`
- `KERNEL32!GetLastError` at `0x140022522`
- `KERNEL32!GetProcessHeap` at `0x14002252a`
- `KERNEL32!GetProcessHeap` at `0x140022557`
- `KERNEL32!GetProcessHeap` at `0x14002252a`
- `KERNEL32!GetProcessHeap` at `0x140022557`
- `KERNEL32!SetLastError` at `0x140022540`
- `KERNEL32!SetLastError` at `0x140022540`
- `KERNEL32!HeapFree` at `0x140022538`
- `KERNEL32!HeapFree` at `0x140022565`
- `KERNEL32!HeapFree` at `0x140022538`
- `KERNEL32!HeapFree` at `0x140022565`

## pseudocode

```c
void __fastcall Pca::MergeSdb::Utils::TempFilePathHolder::Alloc(void **this, __int64 a2)
{
  void *v3; // rsi
  void *v4; // rbp
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  void *v7; // rbx
  HANDLE v8; // rax
  _QWORD v9[7]; // [rsp+20h] [rbp-38h] BYREF

  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    v9,
    0,
    a2);
  if ( this == v9 )
  {
    v7 = (void *)v9[0];
  }
  else
  {
    v3 = *this;
    v4 = (void *)v9[0];
    if ( *this )
    {
      LastError = GetLastError();
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
      SetLastError(LastError);
    }
    *this = v4;
    v7 = 0;
  }
  if ( v7 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v7);
  }
}

```

## disassembly

```asm
0x1400224f0  push    rbx
0x1400224f2  push    rbp
0x1400224f3  push    rsi
0x1400224f4  push    rdi
0x1400224f5  sub     rsp, 38h
0x1400224f9  mov     rdi, rcx
0x1400224fc  mov     r8, rdx
0x1400224ff  xor     edx, edx
0x140022501  lea     rcx, [rsp+58h+var_38]
0x140022506  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14002250b  lea     rax, [rsp+58h+var_38]
0x140022510  cmp     rdi, rax
0x140022513  jz      short loc_14002254D
0x140022515  mov     rsi, [rdi]
0x140022518  mov     rbp, [rsp+58h+var_38]
0x14002251d  test    rsi, rsi
0x140022520  jz      short loc_140022546
0x140022522  call    cs:__imp_GetLastError
0x140022528  mov     ebx, eax
0x14002252a  call    cs:__imp_GetProcessHeap
0x140022530  mov     r8, rsi; lpMem
0x140022533  xor     edx, edx; dwFlags
0x140022535  mov     rcx, rax; hHeap
0x140022538  call    cs:__imp_HeapFree
0x14002253e  mov     ecx, ebx; dwErrCode
0x140022540  call    cs:__imp_SetLastError
0x140022546  mov     [rdi], rbp
0x140022549  xor     ebx, ebx
0x14002254b  jmp     short loc_140022552
0x14002254d  mov     rbx, [rsp+58h+var_38]
0x140022552  test    rbx, rbx
0x140022555  jz      short loc_14002256B
0x140022557  call    cs:__imp_GetProcessHeap
0x14002255d  mov     r8, rbx; lpMem
0x140022560  xor     edx, edx; dwFlags
0x140022562  mov     rcx, rax; hHeap
0x140022565  call    cs:__imp_HeapFree
0x14002256b  add     rsp, 38h
0x14002256f  pop     rdi
0x140022570  pop     rsi
0x140022571  pop     rbp
0x140022572  pop     rbx
0x140022573  retn
```
