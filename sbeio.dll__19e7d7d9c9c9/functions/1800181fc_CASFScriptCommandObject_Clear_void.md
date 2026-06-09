# CASFScriptCommandObject::Clear(void)

- ea: `0x1800181fc`
- end: `0x1800182cd`
- name: `?Clear@CASFScriptCommandObject@@QEAAXXZ`
- size: `209`
- prototype: `void __fastcall(CASFScriptCommandObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016028`
- `0x1800230f0`

## callees

- `0x180001194`
- `0x1800181fc`

## pseudocode

```c
void __fastcall CASFScriptCommandObject::Clear(CASFScriptCommandObject *this)
{
  __int64 i; // rdi
  void *v3; // rcx
  void *v4; // rcx
  unsigned int j; // edi
  __int64 v6; // rsi
  void *v7; // rcx
  void *v8; // rcx

  if ( *((_QWORD *)this + 10) )
  {
    for ( i = 0; (unsigned int)i < *((unsigned __int16 *)this + 37); i = (unsigned int)(i + 1) )
    {
      v3 = *(void **)(*((_QWORD *)this + 10) + 8 * i);
      if ( v3 )
      {
        operator delete(v3);
        *(_QWORD *)(*((_QWORD *)this + 10) + 8 * i) = 0;
      }
    }
    v4 = (void *)*((_QWORD *)this + 10);
    if ( v4 )
    {
      operator delete(v4);
      *((_QWORD *)this + 10) = 0;
    }
  }
  *((_WORD *)this + 37) = 0;
  if ( *((_QWORD *)this + 11) )
  {
    for ( j = 0; j < *((unsigned __int16 *)this + 36); ++j )
    {
      v6 = 14LL * j;
      v7 = *(void **)(*((_QWORD *)this + 11) + v6 + 6);
      if ( v7 )
      {
        operator delete(v7);
        *(_QWORD *)(*((_QWORD *)this + 11) + v6 + 6) = 0;
      }
    }
    v8 = (void *)*((_QWORD *)this + 11);
    if ( v8 )
    {
      operator delete(v8);
      *((_QWORD *)this + 11) = 0;
    }
  }
  *((_WORD *)this + 36) = 0;
}

```

## disassembly

```asm
0x1800181fc  mov     [rsp+arg_0], rbx
0x180018201  mov     [rsp+arg_8], rsi
0x180018206  push    rdi
0x180018207  sub     rsp, 20h
0x18001820b  cmp     qword ptr [rcx+50h], 0
0x180018210  mov     rbx, rcx
0x180018213  jz      short loc_18001825D
0x180018215  xor     edi, edi
0x180018217  xor     eax, eax
0x180018219  cmp     ax, [rcx+4Ah]
0x18001821d  jnb     short loc_180018247
0x18001821f  mov     rax, [rbx+50h]
0x180018223  mov     rcx, [rax+rdi*8]; void *
0x180018227  test    rcx, rcx
0x18001822a  jz      short loc_18001823D
0x18001822c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018231  mov     rax, [rbx+50h]
0x180018235  mov     qword ptr [rax+rdi*8], 0
0x18001823d  movzx   eax, word ptr [rbx+4Ah]
0x180018241  inc     edi
0x180018243  cmp     edi, eax
0x180018245  jb      short loc_18001821F
0x180018247  mov     rcx, [rbx+50h]; void *
0x18001824b  test    rcx, rcx
0x18001824e  jz      short loc_18001825D
0x180018250  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018255  mov     qword ptr [rbx+50h], 0
0x18001825d  xor     eax, eax
0x18001825f  mov     [rbx+4Ah], ax
0x180018263  cmp     [rbx+58h], rax
0x180018267  jz      short loc_1800182B7
0x180018269  xor     edi, edi
0x18001826b  cmp     ax, [rbx+48h]
0x18001826f  jnb     short loc_1800182A1
0x180018271  mov     eax, edi
0x180018273  imul    rsi, rax, 0Eh
0x180018277  mov     rax, [rbx+58h]
0x18001827b  mov     rcx, [rax+rsi+6]; void *
0x180018280  test    rcx, rcx
0x180018283  jz      short loc_180018297
0x180018285  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001828a  mov     rax, [rbx+58h]
0x18001828e  mov     qword ptr [rax+rsi+6], 0
0x180018297  movzx   eax, word ptr [rbx+48h]
0x18001829b  inc     edi
0x18001829d  cmp     edi, eax
0x18001829f  jb      short loc_180018271
0x1800182a1  mov     rcx, [rbx+58h]; void *
0x1800182a5  test    rcx, rcx
0x1800182a8  jz      short loc_1800182B7
0x1800182aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800182af  mov     qword ptr [rbx+58h], 0
0x1800182b7  mov     rsi, [rsp+28h+arg_8]
0x1800182bc  xor     eax, eax
0x1800182be  mov     [rbx+48h], ax
0x1800182c2  mov     rbx, [rsp+28h+arg_0]
0x1800182c7  add     rsp, 20h
0x1800182cb  pop     rdi
0x1800182cc  retn
```
