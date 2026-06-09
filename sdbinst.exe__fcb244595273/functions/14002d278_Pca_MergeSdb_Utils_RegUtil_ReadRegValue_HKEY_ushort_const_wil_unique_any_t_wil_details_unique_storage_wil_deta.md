# Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x14002d278`
- end: `0x14002d412`
- name: `?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpValue, void **)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002285c`
- `0x140028714`
- `0x140029ba0`
- `0x14002d660`

## callees

- `0x14001008c`
- `0x140020f9c`
- `0x1400248cc`
- `0x14002d278`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14002d2fd`
- `ADVAPI32!RegGetValueW` at `0x14002d38b`
- `ADVAPI32!RegGetValueW` at `0x14002d2fd`
- `ADVAPI32!RegGetValueW` at `0x14002d38b`
- `KERNEL32!GetLastError` at `0x14002d29b`
- `KERNEL32!GetLastError` at `0x14002d29b`
- `KERNEL32!GetProcessHeap` at `0x14002d2a3`
- `KERNEL32!GetProcessHeap` at `0x14002d3b9`
- `KERNEL32!GetProcessHeap` at `0x14002d3e9`
- `KERNEL32!GetProcessHeap` at `0x14002d2a3`
- `KERNEL32!GetProcessHeap` at `0x14002d3b9`
- `KERNEL32!GetProcessHeap` at `0x14002d3e9`
- `KERNEL32!SetLastError` at `0x14002d2b9`
- `KERNEL32!SetLastError` at `0x14002d2b9`
- `KERNEL32!HeapFree` at `0x14002d2b1`
- `KERNEL32!HeapFree` at `0x14002d3c7`
- `KERNEL32!HeapFree` at `0x14002d3f7`
- `KERNEL32!HeapFree` at `0x14002d2b1`
- `KERNEL32!HeapFree` at `0x14002d3c7`
- `KERNEL32!HeapFree` at `0x14002d3f7`

## string_xrefs

- `0x14002d315`: `Failed to read registry value to get size (%d)`
- `0x14002d39b`: `Failed to read registry value (%d)`
- `0x14002d322`: `Pca::MergeSdb::Utils::RegUtil::ReadRegValue`
- `0x14002d3a8`: `Pca::MergeSdb::Utils::RegUtil::ReadRegValue`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY hkey, LPCWSTR lpValue, void **a3)
{
  void *v6; // rsi
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  LSTATUS ValueW; // eax
  const char *v10; // r9
  unsigned int v11; // ebx
  PVOID v13; // rbx
  LSTATUS v14; // eax
  unsigned int v15; // esi
  HANDLE v16; // rax
  PVOID v17; // rbx
  HANDLE v18; // rax
  DWORD pcbData; // [rsp+70h] [rbp+18h] BYREF
  PVOID lpMem; // [rsp+78h] [rbp+20h] BYREF

  v6 = *a3;
  if ( *a3 )
  {
    LastError = GetLastError();
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
    SetLastError(LastError);
  }
  *a3 = 0;
  pcbData = 0;
  ValueW = RegGetValueW(hkey, &Format, lpValue, 0x10000006u, 0, 0, &pcbData);
  v11 = ValueW;
  if ( ValueW )
  {
    if ( (unsigned int)(ValueW - 2) > 1 )
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::RegUtil::ReadRegValue",
        81,
        "Failed to read registry value to get size (%d)",
        ValueW);
    return v11;
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpMem,
      0,
      (unsigned __int64)pcbData >> 1,
      v10);
    v13 = lpMem;
    if ( lpMem )
    {
      v14 = RegGetValueW(hkey, &Format, lpValue, 0x30000006u, 0, lpMem, &pcbData);
      v15 = v14;
      if ( v14 )
      {
        AslLogCallPrintf(
          1,
          "Pca::MergeSdb::Utils::RegUtil::ReadRegValue",
          100,
          "Failed to read registry value (%d)",
          v14);
        v16 = GetProcessHeap();
        HeapFree(v16, 0, v13);
        return v15;
      }
      else
      {
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
          a3,
          &lpMem);
        v17 = lpMem;
        if ( lpMem )
        {
          v18 = GetProcessHeap();
          HeapFree(v18, 0, v17);
        }
        return 0;
      }
    }
    else
    {
      return 14;
    }
  }
}

```

## disassembly

```asm
0x14002d278  mov     [rsp+arg_0], rbx
0x14002d27d  mov     [rsp+arg_8], rbp
0x14002d282  push    rsi
0x14002d283  push    rdi
0x14002d284  push    r14
0x14002d286  sub     rsp, 40h
0x14002d28a  mov     rdi, r8
0x14002d28d  mov     rbp, rdx
0x14002d290  mov     r14, rcx
0x14002d293  mov     rsi, [r8]
0x14002d296  test    rsi, rsi
0x14002d299  jz      short loc_14002D2BF
0x14002d29b  call    cs:__imp_GetLastError
0x14002d2a1  mov     ebx, eax
0x14002d2a3  call    cs:__imp_GetProcessHeap
0x14002d2a9  mov     rcx, rax; hHeap
0x14002d2ac  mov     r8, rsi; lpMem
0x14002d2af  xor     edx, edx; dwFlags
0x14002d2b1  call    cs:__imp_HeapFree
0x14002d2b7  mov     ecx, ebx; dwErrCode
0x14002d2b9  call    cs:__imp_SetLastError
0x14002d2bf  mov     qword ptr [rdi], 0
0x14002d2c6  mov     [rsp+58h+arg_10], 0
0x14002d2ce  lea     rax, [rsp+58h+arg_10]
0x14002d2d3  mov     [rsp+58h+pcbData], rax; pcbData
0x14002d2d8  mov     [rsp+58h+pvData], 0; pvData
0x14002d2e1  mov     [rsp+58h+pdwType], 0; pdwType
0x14002d2ea  mov     r9d, 10000006h; dwFlags
0x14002d2f0  mov     r8, rbp; lpValue
0x14002d2f3  lea     rdx, Format; lpSubKey
0x14002d2fa  mov     rcx, r14; hkey
0x14002d2fd  call    cs:__imp_RegGetValueW
0x14002d303  mov     ebx, eax
0x14002d305  test    eax, eax
0x14002d307  jz      short loc_14002D339
0x14002d309  lea     edx, [rax-2]
0x14002d30c  cmp     edx, 1
0x14002d30f  jbe     short loc_14002D332
0x14002d311  mov     dword ptr [rsp+58h+pdwType], eax
0x14002d315  lea     r9, aFailedToReadRe_2; "Failed to read registry value to get si"...
0x14002d31c  mov     r8d, 51h ; 'Q'
0x14002d322  lea     rdx, aPcaMergesdbUti_14; "Pca::MergeSdb::Utils::RegUtil::ReadRegV"...
0x14002d329  lea     ecx, [r8-50h]
0x14002d32d  call    AslLogCallPrintf
0x14002d332  mov     eax, ebx
0x14002d334  jmp     loc_14002D3FF
0x14002d339  mov     r8d, [rsp+58h+arg_10]
0x14002d33e  shr     r8, 1
0x14002d341  xor     edx, edx
0x14002d343  lea     rcx, [rsp+58h+lpMem]
0x14002d348  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14002d34d  nop
0x14002d34e  mov     rbx, [rsp+58h+lpMem]
0x14002d353  test    rbx, rbx
0x14002d356  jnz     short loc_14002D360
0x14002d358  lea     eax, [rbx+0Eh]
0x14002d35b  jmp     loc_14002D3FF
0x14002d360  lea     rax, [rsp+58h+arg_10]
0x14002d365  mov     [rsp+58h+pcbData], rax; pcbData
0x14002d36a  mov     [rsp+58h+pvData], rbx; pvData
0x14002d36f  mov     [rsp+58h+pdwType], 0; pdwType
0x14002d378  mov     r9d, 30000006h; dwFlags
0x14002d37e  mov     r8, rbp; lpValue
0x14002d381  lea     rdx, Format; lpSubKey
0x14002d388  mov     rcx, r14; hkey
0x14002d38b  call    cs:__imp_RegGetValueW
0x14002d391  mov     esi, eax
0x14002d393  test    eax, eax
0x14002d395  jz      short loc_14002D3D1
0x14002d397  mov     dword ptr [rsp+58h+pdwType], eax
0x14002d39b  lea     r9, aFailedToReadRe; "Failed to read registry value (%d)"
0x14002d3a2  mov     r8d, 64h ; 'd'
0x14002d3a8  lea     rdx, aPcaMergesdbUti_14; "Pca::MergeSdb::Utils::RegUtil::ReadRegV"...
0x14002d3af  lea     ecx, [r8-63h]
0x14002d3b3  call    AslLogCallPrintf
0x14002d3b8  nop
0x14002d3b9  call    cs:__imp_GetProcessHeap
0x14002d3bf  mov     rcx, rax; hHeap
0x14002d3c2  mov     r8, rbx; lpMem
0x14002d3c5  xor     edx, edx; dwFlags
0x14002d3c7  call    cs:__imp_HeapFree
0x14002d3cd  mov     eax, esi
0x14002d3cf  jmp     short loc_14002D3FF
0x14002d3d1  lea     rdx, [rsp+58h+lpMem]
0x14002d3d6  mov     rcx, rdi
0x14002d3d9  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002d3de  nop
0x14002d3df  mov     rbx, [rsp+58h+lpMem]
0x14002d3e4  test    rbx, rbx
0x14002d3e7  jz      short loc_14002D3FD
0x14002d3e9  call    cs:__imp_GetProcessHeap
0x14002d3ef  mov     rcx, rax; hHeap
0x14002d3f2  mov     r8, rbx; lpMem
0x14002d3f5  xor     edx, edx; dwFlags
0x14002d3f7  call    cs:__imp_HeapFree
0x14002d3fd  xor     eax, eax
0x14002d3ff  mov     rbx, [rsp+58h+arg_0]
0x14002d404  mov     rbp, [rsp+58h+arg_8]
0x14002d409  add     rsp, 40h
0x14002d40d  pop     r14
0x14002d40f  pop     rdi
0x14002d410  pop     rsi
0x14002d411  retn
```
