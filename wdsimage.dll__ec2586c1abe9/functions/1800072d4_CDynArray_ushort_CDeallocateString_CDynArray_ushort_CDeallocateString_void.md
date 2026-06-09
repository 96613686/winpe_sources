# CDynArray<ushort *,CDeallocateString>::~CDynArray<ushort *,CDeallocateString>(void)

- ea: `0x1800072d4`
- end: `0x180007344`
- name: `??1?$CDynArray@PEAGVCDeallocateString@@@@QEAA@XZ`
- size: `112`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007350`
- `0x180007cac`
- `0x18000a13c`

## callees

- `0x1800072d4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800072fd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000731b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800072fd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000731b`

## pseudocode

```c
void __fastcall CDynArray<unsigned short *,CDeallocateString>::~CDynArray<unsigned short *,CDeallocateString>(
        __int64 a1)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  void *v4; // rcx

  if ( *(_DWORD *)(a1 + 12) )
  {
    v2 = *(unsigned int *)(a1 + 12);
    v3 = 0;
    do
    {
      v4 = *(void **)(v3 + *(_QWORD *)a1);
      if ( v4 )
        operator delete(v4);
      v3 += 8;
      --v2;
    }
    while ( v2 );
  }
  if ( *(_QWORD *)a1 )
  {
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_DWORD *)(a1 + 12) = 0;
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800072d4  mov     [rsp+arg_0], rbx
0x1800072d9  mov     [rsp+arg_8], rsi
0x1800072de  push    rdi
0x1800072df  sub     rsp, 20h
0x1800072e3  cmp     dword ptr [rcx+0Ch], 0
0x1800072e7  mov     rbx, rcx
0x1800072ea  jbe     short loc_180007313
0x1800072ec  mov     esi, [rcx+0Ch]
0x1800072ef  xor     edi, edi
0x1800072f1  mov     rax, [rbx]
0x1800072f4  mov     rcx, [rdi+rax]
0x1800072f8  test    rcx, rcx
0x1800072fb  jz      short loc_180007309
0x1800072fd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007304  nop     dword ptr [rax+rax+00h]
0x180007309  add     rdi, 8
0x18000730d  sub     rsi, 1
0x180007311  jnz     short loc_1800072F1
0x180007313  mov     rcx, [rbx]
0x180007316  test    rcx, rcx
0x180007319  jz      short loc_180007333
0x18000731b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007322  nop     dword ptr [rax+rax+00h]
0x180007327  and     qword ptr [rbx], 0
0x18000732b  and     dword ptr [rbx+0Ch], 0
0x18000732f  and     dword ptr [rbx+8], 0
0x180007333  mov     rbx, [rsp+28h+arg_0]
0x180007338  mov     rsi, [rsp+28h+arg_8]
0x18000733d  add     rsp, 20h
0x180007341  pop     rdi
0x180007342  retn
```
