# CPropertyBagFieldsBase::ClearInFileSecureProperties(_FSRM_IN_FILE_SECURE_PROPERTIES * &)

- ea: `0x180084e28`
- end: `0x180084ea8`
- name: `?ClearInFileSecureProperties@CPropertyBagFieldsBase@@KAXAEAPEAU_FSRM_IN_FILE_SECURE_PROPERTIES@@@Z`
- size: `128`
- prototype: `void __fastcall(struct _FSRM_IN_FILE_SECURE_PROPERTIES **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180084608`
- `0x180085ba8`

## callees

- `0x180084e28`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180084e5d`
- `ole32!CoTaskMemFree` at `0x180084e6f`
- `ole32!CoTaskMemFree` at `0x180084e82`
- `ole32!CoTaskMemFree` at `0x180084e8b`
- `ole32!CoTaskMemFree` at `0x180084e5d`
- `ole32!CoTaskMemFree` at `0x180084e6f`
- `ole32!CoTaskMemFree` at `0x180084e82`
- `ole32!CoTaskMemFree` at `0x180084e8b`

## pseudocode

```c
void __fastcall CPropertyBagFieldsBase::ClearInFileSecureProperties(LPVOID *a1)
{
  _QWORD *v2; // rcx
  unsigned int v3; // esi

  v2 = *a1;
  if ( v2 )
  {
    if ( v2[1] )
    {
      if ( *(_DWORD *)v2 )
      {
        v3 = 0;
        do
        {
          CoTaskMemFree(*(LPVOID *)(v2[1] + 16LL * v3));
          CoTaskMemFree(*(LPVOID *)(*((_QWORD *)*a1 + 1) + 16LL * v3 + 8));
          v2 = *a1;
          ++v3;
        }
        while ( v3 < *(_DWORD *)*a1 );
      }
      CoTaskMemFree((LPVOID)v2[1]);
    }
    CoTaskMemFree(*a1);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180084e28  mov     [rsp+arg_0], rbx
0x180084e2d  mov     [rsp+arg_8], rsi
0x180084e32  push    rdi
0x180084e33  sub     rsp, 20h
0x180084e37  mov     rdi, rcx
0x180084e3a  mov     rcx, [rcx]
0x180084e3d  test    rcx, rcx
0x180084e40  jz      short loc_180084E98
0x180084e42  cmp     qword ptr [rcx+8], 0
0x180084e47  jz      short loc_180084E88
0x180084e49  cmp     dword ptr [rcx], 0
0x180084e4c  jbe     short loc_180084E7E
0x180084e4e  xor     esi, esi
0x180084e50  mov     rcx, [rcx+8]
0x180084e54  mov     ebx, esi
0x180084e56  add     rbx, rbx
0x180084e59  mov     rcx, [rcx+rbx*8]; pv
0x180084e5d  call    cs:__imp_CoTaskMemFree
0x180084e63  mov     rax, [rdi]
0x180084e66  mov     rcx, [rax+8]
0x180084e6a  mov     rcx, [rcx+rbx*8+8]; pv
0x180084e6f  call    cs:__imp_CoTaskMemFree
0x180084e75  mov     rcx, [rdi]
0x180084e78  inc     esi
0x180084e7a  cmp     esi, [rcx]
0x180084e7c  jb      short loc_180084E50
0x180084e7e  mov     rcx, [rcx+8]; pv
0x180084e82  call    cs:__imp_CoTaskMemFree
0x180084e88  mov     rcx, [rdi]; pv
0x180084e8b  call    cs:__imp_CoTaskMemFree
0x180084e91  mov     qword ptr [rdi], 0
0x180084e98  mov     rbx, [rsp+28h+arg_0]
0x180084e9d  mov     rsi, [rsp+28h+arg_8]
0x180084ea2  add     rsp, 20h
0x180084ea6  pop     rdi
0x180084ea7  retn
```
