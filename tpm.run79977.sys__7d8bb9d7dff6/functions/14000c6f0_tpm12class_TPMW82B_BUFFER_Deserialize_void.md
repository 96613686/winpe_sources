# tpm12class::TPMW82B_BUFFER::Deserialize(void)

- ea: `0x14000c6f0`
- end: `0x14000c7a5`
- name: `?Deserialize@TPMW82B_BUFFER@tpm12class@@MEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(tpm12class::TPMW82B_BUFFER *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x14000c6f0`
- `0x14000c93c`
- `0x14000cb50`
- `0x14000cb70`
- `0x140039b40`
- `0x1400454a0`

## pseudocode

```c
int __fastcall tpm12class::TPMW82B_BUFFER::Deserialize(tpm12class::TPMW82B_BUFFER *this)
{
  _BYTE *v1; // rax
  unsigned __int16 *v2; // rdi
  int result; // eax
  void *v5; // rcx
  void *v6; // rax
  __int64 v7; // rcx

  v1 = (_BYTE *)*((_QWORD *)this + 8);
  v2 = (unsigned __int16 *)((char *)this + 56);
  if ( v1 )
  {
    v7 = *v2;
    if ( *v2 )
    {
      do
      {
        *v1++ = 0;
        --v7;
      }
      while ( v7 );
    }
    TpmFree(*((void **)this + 8));
    *((_QWORD *)this + 8) = 0;
  }
  result = tpm12class::TpmDataObject::GetData(this, v2);
  if ( result >= 0 && *v2 )
  {
    v5 = (void *)*((_QWORD *)this + 8);
    if ( v5 )
    {
      TpmFree(v5);
      *((_QWORD *)this + 8) = 0;
    }
    v6 = operator new(*v2);
    *((_QWORD *)this + 8) = v6;
    if ( v6 )
    {
      memset(v6, 0, *v2);
      return tpm12class::TpmDataObject::GetData(this, *((unsigned __int8 **)this + 8), *v2);
    }
    else
    {
      return -2147024888;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c6f0  mov     [rsp+arg_0], rbx
0x14000c6f5  mov     [rsp+arg_8], rsi
0x14000c6fa  push    rdi
0x14000c6fb  sub     rsp, 20h
0x14000c6ff  mov     rax, [rcx+40h]
0x14000c703  lea     rdi, [rcx+38h]
0x14000c707  xor     esi, esi
0x14000c709  mov     rbx, rcx
0x14000c70c  test    rax, rax
0x14000c70f  jnz     short loc_14000C76E
0x14000c711  mov     rdx, rdi; unsigned __int16 *
0x14000c714  mov     rcx, rbx; this
0x14000c717  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAG@Z; tpm12class::TpmDataObject::GetData(ushort *)
0x14000c71c  test    eax, eax
0x14000c71e  js      short loc_14000C75D
0x14000c720  cmp     [rdi], si
0x14000c723  jbe     short loc_14000C75D
0x14000c725  mov     rcx, [rbx+40h]; void *
0x14000c729  test    rcx, rcx
0x14000c72c  jnz     short loc_14000C793
0x14000c72e  movzx   ecx, word ptr [rdi]; unsigned __int64
0x14000c731  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000c736  mov     [rbx+40h], rax
0x14000c73a  test    rax, rax
0x14000c73d  jz      short loc_14000C79E
0x14000c73f  movzx   r8d, word ptr [rdi]; Size
0x14000c743  xor     edx, edx; Val
0x14000c745  mov     rcx, rax; void *
0x14000c748  call    memset
0x14000c74d  movzx   r8d, word ptr [rdi]; unsigned int
0x14000c751  mov     rcx, rbx; this
0x14000c754  mov     rdx, [rbx+40h]; unsigned __int8 *
0x14000c758  call    ?GetData@TpmDataObject@tpm12class@@QEAAJPEAEI@Z; tpm12class::TpmDataObject::GetData(uchar *,uint)
0x14000c75d  mov     rbx, [rsp+28h+arg_0]
0x14000c762  mov     rsi, [rsp+28h+arg_8]
0x14000c767  add     rsp, 20h
0x14000c76b  pop     rdi
0x14000c76c  retn
0x14000c76e  movzx   ecx, word ptr [rdi]
0x14000c771  test    rcx, rcx
0x14000c774  jnz     short loc_14000C785
0x14000c776  mov     rcx, [rbx+40h]; void *
0x14000c77a  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14000c77f  mov     [rbx+40h], rsi
0x14000c783  jmp     short loc_14000C711
0x14000c785  mov     [rax], sil
0x14000c788  inc     rax
0x14000c78b  sub     rcx, 1
0x14000c78f  jnz     short loc_14000C785
0x14000c791  jmp     short loc_14000C776
0x14000c793  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14000c798  mov     [rbx+40h], rsi
0x14000c79c  jmp     short loc_14000C72E
0x14000c79e  mov     eax, 80070008h
0x14000c7a3  jmp     short loc_14000C75D
```
