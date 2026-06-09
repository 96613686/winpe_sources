# SXReadBase::SetStream(IStream *)

- ea: `0x1004112e0`
- end: `0x100411337`
- name: `?SetStream@SXReadBase@@IEAAXPEAUIStream@@@Z`
- size: `87`
- prototype: `void __fastcall(SXReadBase *__hidden this, struct IStream *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x100404b80`
- `0x100404ec0`

## callees

- `0x1004112e0`
- `0x100424580`

## pseudocode

```c
void __fastcall SXReadBase::SetStream(SXReadBase *this, struct IStream *a2)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 180);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_QWORD *)this + 180) = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
  *((_BYTE *)this + 1448) = 0;
}

```

## disassembly

```asm
0x1004112e0  mov     [rsp+arg_0], rbx
0x1004112e5  push    rdi
0x1004112e6  sub     rsp, 20h
0x1004112ea  mov     rbx, rcx
0x1004112ed  mov     rdi, rdx
0x1004112f0  mov     rcx, [rcx+5A0h]
0x1004112f7  test    rcx, rcx
0x1004112fa  jz      short loc_100411309
0x1004112fc  mov     rax, [rcx]
0x1004112ff  mov     rax, [rax+10h]
0x100411303  call    cs:__guard_dispatch_icall_fptr
0x100411309  mov     [rbx+5A0h], rdi
0x100411310  test    rdi, rdi
0x100411313  jz      short loc_100411325
0x100411315  mov     rax, [rdi]
0x100411318  mov     rcx, rdi
0x10041131b  mov     rax, [rax+8]
0x10041131f  call    cs:__guard_dispatch_icall_fptr
0x100411325  mov     byte ptr [rbx+5A8h], 0
0x10041132c  mov     rbx, [rsp+28h+arg_0]
0x100411331  add     rsp, 20h
0x100411335  pop     rdi
0x100411336  retn
```
