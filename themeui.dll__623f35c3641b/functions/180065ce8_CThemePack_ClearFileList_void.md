# CThemePack::ClearFileList(void)

- ea: `0x180065ce8`
- end: `0x180065d81`
- name: `?ClearFileList@CThemePack@@QEAAJXZ`
- size: `153`
- prototype: `__int64 __fastcall(CThemePack *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180062c40`
- `0x180065cac`
- `0x180066168`

## callees

- `0x1800179e0`
- `0x180065ce8`
- `0x18006a6f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065d48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065d48`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065d05`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065d05`
- `OLEAUT32!__imp_SysFreeString` at `0x180065d0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180065d22`
- `OLEAUT32!__imp_SysFreeString` at `0x180065d0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180065d22`

## pseudocode

```c
__int64 __fastcall CThemePack::ClearFileList(CThemePack *this)
{
  unsigned int v2; // edi
  const WCHAR *v3; // rcx
  OLECHAR *v4; // rcx
  int v5; // esi
  PVOID Ptr; // rax

  v2 = 0;
  v3 = (const WCHAR *)*((_QWORD *)this + 11);
  if ( v3 )
  {
    DeleteFileW(v3);
    SysFreeString(*((BSTR *)this + 11));
    *((_QWORD *)this + 11) = 0;
  }
  v4 = (OLECHAR *)*((_QWORD *)this + 12);
  if ( v4 )
  {
    SysFreeString(v4);
    *((_QWORD *)this + 12) = 0;
  }
  if ( *(_QWORD *)this )
  {
    v5 = **(_DWORD **)this;
    if ( v5 > 0 )
    {
      do
      {
        Ptr = g_pfn_DPA_GetPtr(*(HDPA *)this, v2);
        CoTaskMemFree(Ptr);
        ++v2;
      }
      while ( (int)v2 < v5 );
      if ( *(_QWORD *)this && g_pfn_DPA_DeleteAllPtrs(*(HDPA *)this) )
        return 0;
      else
        return (unsigned int)-2147467259;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180065ce8  mov     [rsp+arg_0], rbx
0x180065ced  mov     [rsp+arg_8], rsi
0x180065cf2  push    rdi
0x180065cf3  sub     rsp, 20h
0x180065cf7  mov     rbx, rcx
0x180065cfa  xor     edi, edi
0x180065cfc  mov     rcx, [rcx+58h]; lpFileName
0x180065d00  test    rcx, rcx
0x180065d03  jz      short loc_180065D19
0x180065d05  call    cs:__imp_DeleteFileW
0x180065d0b  mov     rcx, [rbx+58h]; bstrString
0x180065d0f  call    cs:__imp_SysFreeString
0x180065d15  mov     [rbx+58h], rdi
0x180065d19  mov     rcx, [rbx+60h]; bstrString
0x180065d1d  test    rcx, rcx
0x180065d20  jz      short loc_180065D2C
0x180065d22  call    cs:__imp_SysFreeString
0x180065d28  mov     [rbx+60h], rdi
0x180065d2c  mov     rax, [rbx]
0x180065d2f  test    rax, rax
0x180065d32  jz      short loc_180065D6F
0x180065d34  mov     esi, [rax]
0x180065d36  test    esi, esi
0x180065d38  jle     short loc_180065D6F
0x180065d3a  mov     rcx, [rbx]; hdpa
0x180065d3d  mov     edx, edi; i
0x180065d3f  call    cs:g_pfn_DPA_GetPtr
0x180065d45  mov     rcx, rax; pv
0x180065d48  call    cs:__imp_CoTaskMemFree
0x180065d4e  inc     edi
0x180065d50  cmp     edi, esi
0x180065d52  jl      short loc_180065D3A
0x180065d54  mov     rcx, [rbx]; hdpa
0x180065d57  test    rcx, rcx
0x180065d5a  jz      short loc_180065D6A
0x180065d5c  call    cs:g_pfn_DPA_DeleteAllPtrs
0x180065d62  test    eax, eax
0x180065d64  jz      short loc_180065D6A
0x180065d66  xor     edi, edi
0x180065d68  jmp     short loc_180065D6F
0x180065d6a  mov     edi, 80004005h
0x180065d6f  mov     rbx, [rsp+28h+arg_0]
0x180065d74  mov     eax, edi
0x180065d76  mov     rsi, [rsp+28h+arg_8]
0x180065d7b  add     rsp, 20h
0x180065d7f  pop     rdi
0x180065d80  retn
```
