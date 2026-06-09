# SubscriptionReadData::Initialize(void)

- ea: `0x18000aa3c`
- end: `0x18000aa97`
- name: `?Initialize@SubscriptionReadData@@QEAAXXZ`
- size: `91`
- prototype: `void __fastcall(SubscriptionReadData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005f18`

## callees

- `0x18000262c`
- `0x18000aa3c`

## pseudocode

```c
void __fastcall SubscriptionReadData::Initialize(SubscriptionReadData *this)
{
  _BYTE *v1; // rax
  __int64 v3; // rdx
  __int64 v4; // rbx
  _BYTE *v5; // rcx

  v1 = *(_BYTE **)this;
  v3 = 16;
  do
  {
    *v1++ = 0;
    --v3;
  }
  while ( v3 );
  v4 = 768;
  *(_QWORD *)(*(_QWORD *)this + 8LL) = operator new(0x300u);
  **(_DWORD **)this = 32;
  v5 = *(_BYTE **)(*(_QWORD *)this + 8LL);
  do
  {
    *v5++ = 0;
    --v4;
  }
  while ( v4 );
}

```

## disassembly

```asm
0x18000aa3c  mov     [rsp+arg_0], rbx
0x18000aa41  push    rdi
0x18000aa42  sub     rsp, 20h
0x18000aa46  mov     rax, [rcx]
0x18000aa49  mov     rdi, rcx
0x18000aa4c  mov     edx, 10h
0x18000aa51  mov     byte ptr [rax], 0
0x18000aa54  inc     rax
0x18000aa57  sub     rdx, 1
0x18000aa5b  jnz     short loc_18000AA51
0x18000aa5d  mov     ebx, 300h
0x18000aa62  mov     ecx, ebx; dwBytes
0x18000aa64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aa69  mov     rcx, [rdi]
0x18000aa6c  mov     [rcx+8], rax
0x18000aa70  mov     rax, [rdi]
0x18000aa73  mov     dword ptr [rax], 20h ; ' '
0x18000aa79  mov     rax, [rdi]
0x18000aa7c  mov     rcx, [rax+8]
0x18000aa80  mov     byte ptr [rcx], 0
0x18000aa83  inc     rcx
0x18000aa86  sub     rbx, 1
0x18000aa8a  jnz     short loc_18000AA80
0x18000aa8c  mov     rbx, [rsp+28h+arg_0]
0x18000aa91  add     rsp, 20h
0x18000aa95  pop     rdi
0x18000aa96  retn
```
