# _attribute_t::SetValue(ushort const *)

- ea: `0x18000c6cc`
- end: `0x18000c75d`
- name: `?SetValue@_attribute_t@@QEAAJPEBG@Z`
- size: `145`
- prototype: `int(_attribute_t *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002ccc`
- `0x180004330`
- `0x180005b30`
- `0x180011ef0`

## callees

- `0x18000c6cc`
- `0x18000ca0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c6ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c70f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c6ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c70f`

## pseudocode

```c
int __fastcall _attribute_t::SetValue(LPVOID *this, const unsigned __int16 *a2)
{
  int result; // eax
  int v5; // ecx

  if ( *((_DWORD *)this + 2) == 10 )
  {
    CoTaskMemFree(this[2]);
    this[2] = 0;
  }
  else if ( *((_DWORD *)this + 2) == 14 )
  {
    CoTaskMemFree(this[3]);
    this[3] = 0;
    *((_DWORD *)this + 4) = 0;
  }
  result = 0;
  if ( a2 )
  {
    result = StringCchCopyWithAlloc((unsigned __int16 **)this + 2, 0xFFFFu, a2);
    v5 = 0;
    if ( result >= 0 )
      v5 = 10;
    *((_DWORD *)this + 2) = v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000c6cc  mov     [rsp+arg_0], rbx
0x18000c6d1  mov     [rsp+arg_8], rbp
0x18000c6d6  push    rdi
0x18000c6d7  sub     rsp, 20h
0x18000c6db  mov     ebp, 0Ah
0x18000c6e0  mov     rdi, rdx
0x18000c6e3  mov     rbx, rcx
0x18000c6e6  cmp     [rcx+8], ebp
0x18000c6e9  jnz     short loc_18000C705
0x18000c6eb  mov     rcx, [rcx+10h]; pv
0x18000c6ef  call    cs:__imp_CoTaskMemFree
0x18000c6f6  nop     dword ptr [rax+rax+00h]
0x18000c6fb  mov     qword ptr [rbx+10h], 0
0x18000c703  jmp     short loc_18000C72A
0x18000c705  cmp     dword ptr [rcx+8], 0Eh
0x18000c709  jnz     short loc_18000C72A
0x18000c70b  mov     rcx, [rcx+18h]; pv
0x18000c70f  call    cs:__imp_CoTaskMemFree
0x18000c716  nop     dword ptr [rax+rax+00h]
0x18000c71b  mov     qword ptr [rbx+18h], 0
0x18000c723  mov     dword ptr [rbx+10h], 0
0x18000c72a  xor     eax, eax
0x18000c72c  test    rdi, rdi
0x18000c72f  jz      short loc_18000C74C
0x18000c731  lea     rcx, [rbx+10h]; unsigned __int16 **
0x18000c735  mov     r8, rdi; unsigned __int16 *
0x18000c738  mov     edx, 0FFFFh; unsigned __int64
0x18000c73d  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000c742  xor     ecx, ecx
0x18000c744  test    eax, eax
0x18000c746  cmovns  ecx, ebp
0x18000c749  mov     [rbx+8], ecx
0x18000c74c  mov     rbx, [rsp+28h+arg_0]
0x18000c751  mov     rbp, [rsp+28h+arg_8]
0x18000c756  add     rsp, 20h
0x18000c75a  pop     rdi
0x18000c75b  retn
```
