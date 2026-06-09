# CJob::GetWorkItemData(ushort *,uchar * *)

- ea: `0x180026180`
- end: `0x1800261fb`
- name: `?GetWorkItemData@CJob@@UEAAJPEAGPEAPEAE@Z`
- size: `123`
- prototype: `__int64 __fastcall(const void **this, unsigned __int16 *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800087a6`
- `0x180026180`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800261a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800261a9`

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
0x180026180  mov     [rsp+arg_0], rbx
0x180026185  mov     [rsp+arg_8], rsi
0x18002618a  push    rdi
0x18002618b  sub     rsp, 20h
0x18002618f  cmp     qword ptr [rcx+0A8h], 0
0x180026197  mov     rdi, r8
0x18002619a  mov     rsi, rdx
0x18002619d  mov     rbx, rcx
0x1800261a0  jz      short loc_1800261E1
0x1800261a2  movzx   ecx, word ptr [rcx+0B0h]; cb
0x1800261a9  call    cs:__imp_CoTaskMemAlloc
0x1800261af  mov     [rdi], rax
0x1800261b2  test    rax, rax
0x1800261b5  jnz     short loc_1800261BE
0x1800261b7  mov     eax, 8007000Eh
0x1800261bc  jmp     short loc_1800261EB
0x1800261be  movzx   r8d, word ptr [rbx+0B0h]; Size
0x1800261c6  mov     rcx, rax; void *
0x1800261c9  mov     rdx, [rbx+0A8h]; Src
0x1800261d0  call    memcpy_0
0x1800261d5  movzx   eax, word ptr [rbx+0B0h]
0x1800261dc  mov     [rsi], ax
0x1800261df  jmp     short loc_1800261E9
0x1800261e1  xor     eax, eax
0x1800261e3  mov     [rdx], ax
0x1800261e6  mov     [r8], rax
0x1800261e9  xor     eax, eax
0x1800261eb  mov     rbx, [rsp+28h+arg_0]
0x1800261f0  mov     rsi, [rsp+28h+arg_8]
0x1800261f5  add     rsp, 20h
0x1800261f9  pop     rdi
0x1800261fa  retn
```
