# CCompAttribLex::GetAttributeTable(uchar * *,ulong *)

- ea: `0x1800fd200`
- end: `0x1800fd29d`
- name: `?GetAttributeTable@CCompAttribLex@@UEAAJPEAPEAEPEAK@Z`
- size: `157`
- prototype: `__int64 __fastcall(CCompAttribLex *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ca5c`
- `0x1800fd200`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fd250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fd250`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCompAttribLex::GetAttributeTable(CCompAttribLex *this, unsigned __int8 **a2, unsigned int *a3)
{
  unsigned int v3; // ebx
  SIZE_T v8; // rbp
  unsigned __int8 *v9; // rax
  unsigned __int8 *v10; // r15

  v3 = 0;
  if ( !*((_BYTE *)this + 72) )
    return 2147766273LL;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a2 = 0;
  *a3 = 0;
  if ( *((_QWORD *)this + 28) )
  {
    v8 = *(unsigned int *)(*((_QWORD *)this + 19) + 124LL);
    v9 = (unsigned __int8 *)CoTaskMemAlloc(v8);
    v10 = v9;
    if ( v9 )
    {
      memcpy_s(
        v9,
        v8,
        (const void *const)(*((_QWORD *)this + 13) + *(unsigned int *)(*((_QWORD *)this + 19) + 120LL)),
        v8);
      *a2 = v10;
      *a3 = v8;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147200966;
  }
  return v3;
}

```

## disassembly

```asm
0x1800fd200  push    rbx
0x1800fd202  push    rbp
0x1800fd203  push    rsi
0x1800fd204  push    rdi
0x1800fd205  push    r14
0x1800fd207  push    r15
0x1800fd209  sub     rsp, 28h
0x1800fd20d  xor     ebx, ebx
0x1800fd20f  mov     rsi, r8
0x1800fd212  mov     r14, rdx
0x1800fd215  mov     rdi, rcx
0x1800fd218  cmp     [rcx+48h], bl
0x1800fd21b  jnz     short loc_1800FD224
0x1800fd21d  mov     eax, 80045001h
0x1800fd222  jmp     short loc_1800FD290
0x1800fd224  test    r14, r14
0x1800fd227  jz      short loc_1800FD28B
0x1800fd229  test    rsi, rsi
0x1800fd22c  jz      short loc_1800FD28B
0x1800fd22e  mov     [rdx], rbx
0x1800fd231  mov     [r8], ebx
0x1800fd234  cmp     [rcx+0E0h], rbx
0x1800fd23b  jnz     short loc_1800FD244
0x1800fd23d  mov     ebx, 8004503Ah
0x1800fd242  jmp     short loc_1800FD287
0x1800fd244  mov     rax, [rcx+98h]
0x1800fd24b  mov     ebp, [rax+7Ch]
0x1800fd24e  mov     ecx, ebp; cb
0x1800fd250  call    cs:__imp_CoTaskMemAlloc
0x1800fd256  mov     r15, rax
0x1800fd259  test    rax, rax
0x1800fd25c  jnz     short loc_1800FD265
0x1800fd25e  mov     ebx, 8007000Eh
0x1800fd263  jmp     short loc_1800FD287
0x1800fd265  mov     rcx, [rdi+98h]
0x1800fd26c  mov     r9, rbp; SourceSize
0x1800fd26f  mov     rdx, rbp; DestinationSize
0x1800fd272  mov     r8d, [rcx+78h]
0x1800fd276  mov     rcx, r15; Destination
0x1800fd279  add     r8, [rdi+68h]; Source
0x1800fd27d  call    memcpy_s
0x1800fd282  mov     [r14], r15
0x1800fd285  mov     [rsi], ebp
0x1800fd287  mov     eax, ebx
0x1800fd289  jmp     short loc_1800FD290
0x1800fd28b  mov     eax, 80004003h
0x1800fd290  add     rsp, 28h
0x1800fd294  pop     r15
0x1800fd296  pop     r14
0x1800fd298  pop     rdi
0x1800fd299  pop     rsi
0x1800fd29a  pop     rbp
0x1800fd29b  pop     rbx
0x1800fd29c  retn
```
