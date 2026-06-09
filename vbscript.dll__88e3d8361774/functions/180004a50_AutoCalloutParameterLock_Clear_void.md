# AutoCalloutParameterLock::Clear(void)

- ea: `0x180004a50`
- end: `0x180004ac3`
- name: `?Clear@AutoCalloutParameterLock@@QEAAXXZ`
- size: `115`
- prototype: `void __fastcall(AutoCalloutParameterLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180006550`

## callees

- `0x180004a50`
- `0x1800051f0`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x180004abb`
- `OLE32!CoTaskMemFree` at `0x180004abb`

## pseudocode

```c
void __fastcall AutoCalloutParameterLock::Clear(AutoCalloutParameterLock *this)
{
  __int64 v1; // rax
  unsigned int v3; // edi
  char *v4; // rcx

  v1 = *((_QWORD *)this + 1);
  if ( v1 )
    *(_QWORD *)(v1 + 56) = **(_QWORD **)(v1 + 56);
  if ( *((_DWORD *)this + 6) )
  {
    v3 = 0;
    do
      AutoVariantRef::~AutoVariantRef((VARIANTARG *)(*((_QWORD *)this + 2) + 32LL * v3++));
    while ( v3 < *((_DWORD *)this + 6) );
    v4 = (char *)*((_QWORD *)this + 2);
    if ( v4 )
    {
      if ( v4 != (char *)this + 32 )
        CoTaskMemFree(v4);
    }
    *((_DWORD *)this + 6) = 0;
  }
}

```

## disassembly

```asm
0x180004a50  push    rbx
0x180004a52  sub     rsp, 20h
0x180004a56  mov     rax, [rcx+8]
0x180004a5a  mov     rbx, rcx
0x180004a5d  test    rax, rax
0x180004a60  jz      short loc_180004A6D
0x180004a62  mov     rdx, [rax+38h]
0x180004a66  mov     r8, [rdx]
0x180004a69  mov     [rax+38h], r8
0x180004a6d  mov     eax, [rcx+18h]
0x180004a70  test    eax, eax
0x180004a72  jnz     short loc_180004A7A
0x180004a74  add     rsp, 20h
0x180004a78  pop     rbx
0x180004a79  retn
0x180004a7a  mov     [rsp+28h+arg_0], rdi
0x180004a7f  xor     edi, edi
0x180004a81  test    eax, eax
0x180004a83  jz      short loc_180004A9B
0x180004a85  mov     ecx, edi
0x180004a87  shl     rcx, 5
0x180004a8b  add     rcx, [rbx+10h]; pvarg
0x180004a8f  call    ??1AutoVariantRef@@QEAA@XZ; AutoVariantRef::~AutoVariantRef(void)
0x180004a94  inc     edi
0x180004a96  cmp     edi, [rbx+18h]
0x180004a99  jb      short loc_180004A85
0x180004a9b  mov     rcx, [rbx+10h]; pv
0x180004a9f  mov     rdi, [rsp+28h+arg_0]
0x180004aa4  test    rcx, rcx
0x180004aa7  jnz     short loc_180004AB2
0x180004aa9  mov     dword ptr [rbx+18h], 0
0x180004ab0  jmp     short loc_180004A74
0x180004ab2  lea     rax, [rbx+20h]
0x180004ab6  cmp     rcx, rax
0x180004ab9  jz      short loc_180004AA9
0x180004abb  call    cs:__imp_CoTaskMemFree
0x180004ac1  jmp     short loc_180004AA9
```
