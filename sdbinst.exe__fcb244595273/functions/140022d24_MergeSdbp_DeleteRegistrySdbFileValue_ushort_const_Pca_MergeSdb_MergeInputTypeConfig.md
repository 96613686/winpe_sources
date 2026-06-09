# MergeSdbp_DeleteRegistrySdbFileValue(ushort const *,Pca::MergeSdb::MergeInputTypeConfig)

- ea: `0x140022d24`
- end: `0x140022e15`
- name: `?MergeSdbp_DeleteRegistrySdbFileValue@@YAKPEBGUMergeInputTypeConfig@MergeSdb@Pca@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140027c80`

## callees

- `0x14001008c`
- `0x140021c68`
- `0x140022d24`

## import_xrefs

- `ADVAPI32!RegDeleteKeyValueW` at `0x140022db8`
- `ADVAPI32!RegDeleteKeyValueW` at `0x140022db8`
- `KERNEL32!GetProcessHeap` at `0x140022d8f`
- `KERNEL32!GetProcessHeap` at `0x140022df2`
- `KERNEL32!GetProcessHeap` at `0x140022d8f`
- `KERNEL32!GetProcessHeap` at `0x140022df2`
- `KERNEL32!HeapFree` at `0x140022d9f`
- `KERNEL32!HeapFree` at `0x140022e02`
- `KERNEL32!HeapFree` at `0x140022d9f`
- `KERNEL32!HeapFree` at `0x140022e02`

## string_xrefs

- `0x140022d68`: `Failed to concat the sdb merge input type registry key path (%d)`
- `0x140022dcb`: `RegDeleteKeyValueW failed to delete value '%S' (%d)`
- `0x140022d75`: `MergeSdbp_DeleteRegistrySdbFileValue`
- `0x140022dd8`: `MergeSdbp_DeleteRegistrySdbFileValue`
- `0x140022d3e`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`

## pseudocode

```c
__int64 __fastcall MergeSdbp_DeleteRegistrySdbFileValue(const WCHAR *a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  unsigned int v5; // edi
  HANDLE v6; // rax
  LSTATUS v8; // eax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+48h] [rbp+10h] BYREF

  lpMem = 0;
  v4 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [71],unsigned short [2],unsigned short const *>(
         &lpMem,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
         a3,
         a2 + 8);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v8 = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, (LPCWSTR)lpMem, a1);
    if ( v8 )
      AslLogCallPrintf(
        1,
        "MergeSdbp_DeleteRegistrySdbFileValue",
        236,
        "RegDeleteKeyValueW failed to delete value '%S' (%d)",
        a1,
        v8);
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
    return 0;
  }
  else
  {
    if ( (v4 & 0x1FFF0000) == 0x70000 )
      v5 = (unsigned __int16)v4;
    AslLogCallPrintf(
      1,
      "MergeSdbp_DeleteRegistrySdbFileValue",
      229,
      "Failed to concat the sdb merge input type registry key path (%d)",
      v5);
    if ( lpMem )
    {
      v6 = GetProcessHeap();
      HeapFree(v6, 0, lpMem);
    }
    return v5;
  }
}

```

## disassembly

```asm
0x140022d24  mov     [rsp+arg_0], rsi
0x140022d29  push    rdi
0x140022d2a  sub     rsp, 30h
0x140022d2e  mov     rsi, rcx
0x140022d31  mov     [rsp+38h+lpMem], 0
0x140022d3a  lea     r9, [rdx+8]
0x140022d3e  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140022d45  lea     rcx, [rsp+38h+lpMem]
0x140022d4a  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0EH@G$$BY01GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0EH@$$CBGAEAY01$$CBGAEBQEBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [71],ushort [2],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[71],ushort const (&)[2],ushort const * const &)
0x140022d4f  mov     edi, eax
0x140022d51  test    eax, eax
0x140022d53  jns     short loc_140022DA9
0x140022d55  and     eax, 1FFF0000h
0x140022d5a  cmp     eax, 70000h
0x140022d5f  jnz     short loc_140022D64
0x140022d61  movzx   edi, di
0x140022d64  mov     dword ptr [rsp+38h+var_18], edi
0x140022d68  lea     r9, aFailedToConcat_1; "Failed to concat the sdb merge input ty"...
0x140022d6f  mov     r8d, 0E5h
0x140022d75  lea     rdx, aMergesdbpDelet; "MergeSdbp_DeleteRegistrySdbFileValue"
0x140022d7c  mov     ecx, 1
0x140022d81  call    AslLogCallPrintf
0x140022d86  nop
0x140022d87  cmp     [rsp+38h+lpMem], 0
0x140022d8d  jz      short loc_140022DA5
0x140022d8f  call    cs:__imp_GetProcessHeap
0x140022d95  mov     rcx, rax; hHeap
0x140022d98  mov     r8, [rsp+38h+lpMem]; lpMem
0x140022d9d  xor     edx, edx; dwFlags
0x140022d9f  call    cs:__imp_HeapFree
0x140022da5  mov     eax, edi
0x140022da7  jmp     short loc_140022E0A
0x140022da9  mov     r8, rsi; lpValueName
0x140022dac  mov     rdx, [rsp+38h+lpMem]; lpSubKey
0x140022db1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140022db8  call    cs:__imp_RegDeleteKeyValueW
0x140022dbe  test    eax, eax
0x140022dc0  jz      short loc_140022DEA
0x140022dc2  mov     [rsp+38h+var_10], eax
0x140022dc6  mov     [rsp+38h+var_18], rsi
0x140022dcb  lea     r9, aRegdeletekeyva; "RegDeleteKeyValueW failed to delete val"...
0x140022dd2  mov     r8d, 0ECh
0x140022dd8  lea     rdx, aMergesdbpDelet; "MergeSdbp_DeleteRegistrySdbFileValue"
0x140022ddf  mov     ecx, 1
0x140022de4  call    AslLogCallPrintf
0x140022de9  nop
0x140022dea  cmp     [rsp+38h+lpMem], 0
0x140022df0  jz      short loc_140022E08
0x140022df2  call    cs:__imp_GetProcessHeap
0x140022df8  mov     rcx, rax; hHeap
0x140022dfb  mov     r8, [rsp+38h+lpMem]; lpMem
0x140022e00  xor     edx, edx; dwFlags
0x140022e02  call    cs:__imp_HeapFree
0x140022e08  xor     eax, eax
0x140022e0a  mov     rsi, [rsp+38h+arg_0]
0x140022e0f  add     rsp, 30h
0x140022e13  pop     rdi
0x140022e14  retn
```
