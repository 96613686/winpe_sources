# LookupName(ushort const *,void * *)

- ea: `0x180005980`
- end: `0x1800059e5`
- name: `?LookupName@@YAJPEBGPEAPEAX@Z`
- size: `101`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ddc0`

## callees

- `0x180005980`
- `0x1800059f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059cb`

## pseudocode

```c
__int64 __fastcall LookupName(unsigned __int16 *a1, void **a2)
{
  __int64 result; // rax
  unsigned int v4; // edi
  void *v5; // rcx
  unsigned __int16 *v6; // [rsp+30h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp+18h] BYREF

  v6 = a1;
  if ( !a1 || !a2 )
    return 2147942487LL;
  *a2 = 0;
  pv = 0;
  result = LookupNames((void *)1, (const unsigned __int16 *const *)&v6, (void ***)&pv);
  v4 = result;
  if ( (int)result >= 0 )
  {
    v5 = pv;
    *a2 = *(void **)pv;
    CoTaskMemFree(v5);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180005980  mov     [rsp+arg_0], rcx
0x180005985  push    rbx
0x180005986  sub     rsp, 20h
0x18000598a  mov     rbx, rdx
0x18000598d  test    rcx, rcx
0x180005990  jz      short loc_1800059DE
0x180005992  test    rdx, rdx
0x180005995  jz      short loc_1800059DE
0x180005997  xor     eax, eax
0x180005999  mov     [rsp+28h+arg_8], rdi
0x18000599e  mov     [rdx], rax
0x1800059a1  lea     r8, [rsp+28h+pv]; void ***
0x1800059a6  lea     rdx, [rsp+28h+arg_0]; unsigned __int16 **
0x1800059ab  mov     [rsp+28h+pv], rax
0x1800059b0  mov     ecx, 1; Count
0x1800059b5  call    ?LookupNames@@YAJKPEBQEBGPEAPEAPEAX@Z; LookupNames(ulong,ushort const * const *,void * * *)
0x1800059ba  mov     edi, eax
0x1800059bc  test    eax, eax
0x1800059be  js      short loc_1800059D3
0x1800059c0  mov     rcx, [rsp+28h+pv]; pv
0x1800059c5  mov     rax, [rcx]
0x1800059c8  mov     [rbx], rax
0x1800059cb  call    cs:__imp_CoTaskMemFree
0x1800059d1  mov     eax, edi
0x1800059d3  mov     rdi, [rsp+28h+arg_8]
0x1800059d8  add     rsp, 20h
0x1800059dc  pop     rbx
0x1800059dd  retn
0x1800059de  mov     eax, 80070057h
0x1800059e3  jmp     short loc_1800059D8
```
