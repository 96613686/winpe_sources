# CEnumImages::GetImageFromHandle(void *,CImage * *)

- ea: `0x1800083b4`
- end: `0x180008444`
- name: `?GetImageFromHandle@CEnumImages@@SAJPEAXPEAPEAVCImage@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(void *, struct CImage **)`
- caller_count: `39`
- callee_count: `3`
- tags: ``

## callers

- `0x180003eb0`
- `0x180003f40`
- `0x1800041a0`
- `0x180004320`
- `0x180004600`
- `0x180004690`
- `0x180004710`
- `0x180004790`
- `0x180004830`
- `0x1800048d0`
- `0x180004950`
- `0x1800049d0`
- `0x180004a70`
- `0x180004af0`
- `0x180004b90`
- `0x180004c10`
- `0x180004ca0`
- `0x180004d20`
- `0x180004da0`
- `0x180004e40`
- `0x180004ee0`
- `0x180004f60`
- `0x180005000`
- `0x180005080`
- `0x180005120`
- `0x1800051c0`
- `0x180005250`
- `0x1800052e0`
- `0x180005380`
- `0x180005410`
- `0x1800054b0`
- `0x180005540`
- `0x1800055e0`
- `0x180005810`
- `0x180005d70`
- `0x180005e10`
- `0x180005ea0`
- `0x180005f40`
- `0x180005fe0`

## callees

- `0x1800083b4`
- `0x1800086e4`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CEnumImages::GetImageFromHandle(_DWORD *a1, struct CImage **a2)
{
  unsigned int v2; // ebx
  struct CImage *v3; // rdi
  _DWORD *v5; // r8
  struct CImage *v6; // rcx

  v2 = 0;
  v3 = 0;
  v5 = a1;
  if ( !a1 )
    return (unsigned int)-2147024809;
  if ( a1[4] == 4 )
  {
    v3 = (struct CImage *)a1;
    (**(void (__fastcall ***)(_DWORD *))a1)(a1);
    goto LABEL_12;
  }
  if ( a1[4] != 6 )
    return (unsigned int)-1056833019;
  v6 = (struct CImage *)*((_QWORD *)a1 + 8);
  if ( v6 )
  {
    v3 = v6;
    (**(void (__fastcall ***)(struct CImage *, struct CImage **, _DWORD *))v6)(v6, a2, v5);
  }
  else
  {
    v2 = -1056833013;
  }
  if ( (int)ElValidateHr_4(v2, a2, v5, 618) >= 0 )
LABEL_12:
    *a2 = v3;
  return v2;
}

```

## disassembly

```asm
0x1800083b4  mov     [rsp+arg_0], rbx
0x1800083b9  mov     [rsp+arg_8], rsi
0x1800083be  push    rdi
0x1800083bf  sub     rsp, 20h
0x1800083c3  xor     ebx, ebx
0x1800083c5  xor     edi, edi
0x1800083c7  mov     rsi, rdx
0x1800083ca  mov     r8, rcx
0x1800083cd  test    rcx, rcx
0x1800083d0  jnz     short loc_1800083D9
0x1800083d2  mov     ebx, 80070057h
0x1800083d7  jmp     short loc_180008431
0x1800083d9  cmp     dword ptr [rcx+10h], 4
0x1800083dd  jz      short loc_18000841D
0x1800083df  cmp     dword ptr [rcx+10h], 6
0x1800083e3  jz      short loc_1800083EC
0x1800083e5  mov     ebx, 0C1020205h
0x1800083ea  jmp     short loc_180008431
0x1800083ec  mov     rcx, [rcx+40h]
0x1800083f0  test    rcx, rcx
0x1800083f3  jnz     short loc_1800083FC
0x1800083f5  mov     ebx, 0C102020Bh
0x1800083fa  jmp     short loc_18000840A
0x1800083fc  mov     rax, [rcx]
0x1800083ff  mov     rdi, rcx
0x180008402  mov     rax, [rax]
0x180008405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000840a  mov     r9d, 26Ah
0x180008410  mov     ecx, ebx
0x180008412  call    ElValidateHr_4
0x180008417  test    eax, eax
0x180008419  js      short loc_180008431
0x18000841b  jmp     short loc_18000842E
0x18000841d  mov     rcx, [rcx]
0x180008420  mov     rdi, r8
0x180008423  mov     rax, [rcx]
0x180008426  mov     rcx, r8
0x180008429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000842e  mov     [rsi], rdi
0x180008431  mov     rsi, [rsp+28h+arg_8]
0x180008436  mov     eax, ebx
0x180008438  mov     rbx, [rsp+28h+arg_0]
0x18000843d  add     rsp, 20h
0x180008441  pop     rdi
0x180008442  retn
```
