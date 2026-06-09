# VMX_LOG::Flush(VMX_LOG_COPY *,uchar,void (*)(void *,long),void *)

- ea: `0x140008b38`
- end: `0x140008c29`
- name: `?Flush@VMX_LOG@@QEAAXPEAVVMX_LOG_COPY@@EP6AXPEAXJ@Z1@Z`
- size: `241`
- prototype: `void __usercall(VMX_LOG *__hidden this@<rcx>, struct VMX_LOG_COPY *@<rdx>, unsigned __int8@<r8b>, void (*)(void *, int)@<r9>, void *)`
- caller_count: `8`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140008a90`
- `0x14000b810`
- `0x14000b970`
- `0x14002a920`
- `0x140048830`
- `0x140049b84`
- `0x1400532d4`
- `0x14005343c`

## callees

- `0x140008b38`
- `0x140019524`
- `0x1400195a4`
- `0x1400199dc`
- `0x14001a494`

## string_xrefs

- `0x140008b7d`: `a copy`

## pseudocode

```c
void __fastcall VMX_LOG::Flush(VMX_LOG *this, struct VMX_LOG_COPY *a2, __int64 a3, void (*a4)(void *, int), void *a5)
{
  char v6; // bp
  const char *v9; // r9
  bool v10; // zf
  struct VMX_LOG_COPY *i; // rcx
  unsigned int v12; // r8d

  v6 = a3;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u )
  {
    v9 = "a copy";
    if ( !a2 )
      v9 = "all copies";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 3), a2, a3, v9);
  }
  v10 = *((_DWORD *)this + 9) == 0;
  *((_QWORD *)this + 26) = a5;
  *((_QWORD *)this + 23) = a2;
  *((_BYTE *)this + 192) = v6;
  *((_QWORD *)this + 25) = a4;
  if ( v10 )
  {
    VMX_LOG::FlushCompletionRoutine(this);
  }
  else
  {
    *((_DWORD *)this + 44) = 512;
    for ( i = (struct VMX_LOG_COPY *)*((_QWORD *)this + 2);
          i != (VMX_LOG *)((char *)this + 16);
          i = *(struct VMX_LOG_COPY **)i )
    {
      if ( !a2 || i == a2 )
      {
        if ( *((_BYTE *)i + 45) )
        {
          v12 = *(_DWORD *)(*((_QWORD *)i + 3) + 36LL);
          if ( v12 > *((_DWORD *)this + 44) )
            *((_DWORD *)this + 44) = v12;
        }
      }
    }
    *((_DWORD *)this + 54) = 1;
    if ( !VMX_LOG::FlushParallel(this) )
      VMX_LOG::FlushSequential(this);
  }
}

```

## disassembly

```asm
0x140008b38  push    rbx
0x140008b3a  push    rbp
0x140008b3b  push    rsi
0x140008b3c  push    rdi
0x140008b3d  sub     rsp, 28h
0x140008b41  mov     rsi, r9
0x140008b44  mov     bpl, r8b
0x140008b47  mov     rdi, rdx
0x140008b4a  mov     rbx, rcx
0x140008b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b54  lea     rax, WPP_GLOBAL_Control
0x140008b5b  cmp     rcx, rax
0x140008b5e  jz      short loc_140008B8D
0x140008b60  test    dword ptr [rcx+2Ch], 800h
0x140008b67  jz      short loc_140008B8D
0x140008b69  cmp     byte ptr [rcx+29h], 4
0x140008b6d  jb      short loc_140008B8D
0x140008b6f  mov     rcx, [rcx+18h]
0x140008b73  lea     rax, aAllCopies; "all copies"
0x140008b7a  test    rdx, rdx
0x140008b7d  lea     r9, aACopy; "a copy"
0x140008b84  cmovz   r9, rax
0x140008b88  call    WPP_SF_s
0x140008b8d  cmp     dword ptr [rbx+24h], 0
0x140008b91  mov     rax, [rsp+48h+arg_20]
0x140008b96  mov     [rbx+0D0h], rax
0x140008b9d  mov     [rbx+0B8h], rdi
0x140008ba4  mov     [rbx+0C0h], bpl
0x140008bab  mov     [rbx+0C8h], rsi
0x140008bb2  jnz     short loc_140008BBE
0x140008bb4  mov     rcx, rbx; this
0x140008bb7  call    ?FlushCompletionRoutine@VMX_LOG@@AEAAXXZ; VMX_LOG::FlushCompletionRoutine(void)
0x140008bbc  jmp     short loc_140008C1F
0x140008bbe  lea     rdx, [rbx+10h]
0x140008bc2  mov     dword ptr [rbx+0B0h], 200h
0x140008bcc  mov     rcx, [rdx]
0x140008bcf  jmp     short loc_140008BFC
0x140008bd1  test    rdi, rdi
0x140008bd4  jz      short loc_140008BDB
0x140008bd6  cmp     rcx, rdi
0x140008bd9  jnz     short loc_140008BF9
0x140008bdb  cmp     byte ptr [rcx+2Dh], 0
0x140008bdf  jz      short loc_140008BF9
0x140008be1  mov     rax, [rcx+18h]
0x140008be5  mov     r8d, [rax+24h]
0x140008be9  cmp     r8d, [rbx+0B0h]
0x140008bf0  jbe     short loc_140008BF9
0x140008bf2  mov     [rbx+0B0h], r8d
0x140008bf9  mov     rcx, [rcx]
0x140008bfc  cmp     rcx, rdx
0x140008bff  jnz     short loc_140008BD1
0x140008c01  mov     rcx, rbx; this
0x140008c04  mov     dword ptr [rbx+0D8h], 1
0x140008c0e  call    ?FlushParallel@VMX_LOG@@AEAAEXZ; VMX_LOG::FlushParallel(void)
0x140008c13  test    al, al
0x140008c15  jnz     short loc_140008C1F
0x140008c17  mov     rcx, rbx; this
0x140008c1a  call    ?FlushSequential@VMX_LOG@@AEAAXXZ; VMX_LOG::FlushSequential(void)
0x140008c1f  add     rsp, 28h
0x140008c23  pop     rdi
0x140008c24  pop     rsi
0x140008c25  pop     rbp
0x140008c26  pop     rbx
0x140008c27  retn
```
