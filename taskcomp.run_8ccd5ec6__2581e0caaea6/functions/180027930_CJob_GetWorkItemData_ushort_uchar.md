# CJob::GetWorkItemData(ushort *,uchar * *)

- ea: `0x180027930`
- end: `0x1800279b2`
- name: `?GetWorkItemData@CJob@@UEAAJPEAGPEAPEAE@Z`
- size: `130`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008c66`
- `0x180027930`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027959`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027959`

## pseudocode

```c
__int64 __fastcall CJob::GetWorkItemData(const void **this, unsigned __int16 *a2, unsigned __int8 **a3)
{
  unsigned __int8 *v6; // rax

  if ( this[21] )
  {
    v6 = (unsigned __int8 *)CoTaskMemAlloc(*((unsigned __int16 *)this + 88));
    *a3 = v6;
    if ( !v6 )
      return 2147942414LL;
    memcpy_0(v6, this[21], *((unsigned __int16 *)this + 88));
    *a2 = *((_WORD *)this + 88);
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180027930  mov     [rsp+arg_0], rbx
0x180027935  mov     [rsp+arg_8], rsi
0x18002793a  push    rdi
0x18002793b  sub     rsp, 20h
0x18002793f  cmp     qword ptr [rcx+0A8h], 0
0x180027947  mov     rdi, r8
0x18002794a  mov     rsi, rdx
0x18002794d  mov     rbx, rcx
0x180027950  jz      short loc_180027997
0x180027952  movzx   ecx, word ptr [rcx+0B0h]; cb
0x180027959  call    cs:__imp_CoTaskMemAlloc
0x180027960  nop     dword ptr [rax+rax+00h]
0x180027965  mov     [rdi], rax
0x180027968  test    rax, rax
0x18002796b  jnz     short loc_180027974
0x18002796d  mov     eax, 8007000Eh
0x180027972  jmp     short loc_1800279A1
0x180027974  movzx   r8d, word ptr [rbx+0B0h]; Size
0x18002797c  mov     rcx, rax; void *
0x18002797f  mov     rdx, [rbx+0A8h]; Src
0x180027986  call    memcpy_0
0x18002798b  movzx   eax, word ptr [rbx+0B0h]
0x180027992  mov     [rsi], ax
0x180027995  jmp     short loc_18002799F
0x180027997  xor     eax, eax
0x180027999  mov     [rdx], ax
0x18002799c  mov     [r8], rax
0x18002799f  xor     eax, eax
0x1800279a1  mov     rbx, [rsp+28h+arg_0]
0x1800279a6  mov     rsi, [rsp+28h+arg_8]
0x1800279ab  add     rsp, 20h
0x1800279af  pop     rdi
0x1800279b0  retn
```
