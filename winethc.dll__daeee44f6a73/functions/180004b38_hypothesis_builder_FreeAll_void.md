# _hypothesis_builder::FreeAll(void)

- ea: `0x180004b38`
- end: `0x180004bd6`
- name: `?FreeAll@_hypothesis_builder@@QEAAXXZ`
- size: `158`
- prototype: `void __fastcall(_hypothesis_builder *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800032ec`
- `0x180005b30`
- `0x180012940`
- `0x1800129e8`

## callees

- `0x180004ac4`
- `0x180004b38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ba6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004bb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ba6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004bb6`

## pseudocode

```c
void __fastcall _hypothesis_builder::FreeAll(LPVOID *this)
{
  void *v2; // rcx
  __int64 i; // rdi
  LPVOID *v4; // rcx

  CoTaskMemFree(*this);
  v2 = this[1];
  *this = 0;
  CoTaskMemFree(v2);
  this[1] = 0;
  if ( this[3] )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
      _attribute_t::FreeAll((_attribute_t *)((char *)this[3] + 144 * i));
  }
  v4 = (LPVOID *)this[4];
  if ( v4 )
    CoTaskMemFree(v4[3]);
  CoTaskMemFree(this[4]);
  this[4] = 0;
}

```

## disassembly

```asm
0x180004b38  mov     [rsp+arg_0], rbx
0x180004b3d  push    rdi
0x180004b3e  sub     rsp, 20h
0x180004b42  mov     rbx, rcx
0x180004b45  mov     rcx, [rcx]; pv
0x180004b48  call    cs:__imp_CoTaskMemFree
0x180004b4f  nop     dword ptr [rax+rax+00h]
0x180004b54  mov     rcx, [rbx+8]; pv
0x180004b58  mov     qword ptr [rbx], 0
0x180004b5f  call    cs:__imp_CoTaskMemFree
0x180004b66  nop     dword ptr [rax+rax+00h]
0x180004b6b  mov     qword ptr [rbx+8], 0
0x180004b73  cmp     qword ptr [rbx+18h], 0
0x180004b78  jz      short loc_180004B99
0x180004b7a  xor     edi, edi
0x180004b7c  cmp     [rbx+10h], edi
0x180004b7f  jbe     short loc_180004B99
0x180004b81  lea     rcx, [rdi+rdi*8]
0x180004b85  shl     rcx, 4
0x180004b89  add     rcx, [rbx+18h]; this
0x180004b8d  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180004b92  inc     edi
0x180004b94  cmp     edi, [rbx+10h]
0x180004b97  jb      short loc_180004B81
0x180004b99  mov     rcx, [rbx+20h]
0x180004b9d  test    rcx, rcx
0x180004ba0  jz      short loc_180004BB2
0x180004ba2  mov     rcx, [rcx+18h]; pv
0x180004ba6  call    cs:__imp_CoTaskMemFree
0x180004bad  nop     dword ptr [rax+rax+00h]
0x180004bb2  mov     rcx, [rbx+20h]; pv
0x180004bb6  call    cs:__imp_CoTaskMemFree
0x180004bbd  nop     dword ptr [rax+rax+00h]
0x180004bc2  mov     qword ptr [rbx+20h], 0
0x180004bca  mov     rbx, [rsp+28h+arg_0]
0x180004bcf  add     rsp, 20h
0x180004bd3  pop     rdi
0x180004bd4  retn
```
