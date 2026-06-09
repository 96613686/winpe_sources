# CWnd::OnCommand(unsigned __int64,__int64)

- ea: `0x1800047a0`
- end: `0x180004817`
- name: `?OnCommand@CWnd@@MEAA_N_K_J@Z`
- size: `119`
- prototype: `bool __fastcall(CWnd *__hidden this, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800047a0`
- `0x18000e010`

## pseudocode

```c
char __fastcall CWnd::OnCommand(CWnd *this, int a2)
{
  int v3; // edi
  int v4; // esi
  _QWORD *v5; // rdx
  __int64 i; // rax

  v3 = (unsigned __int16)a2;
  v4 = HIWORD(a2);
  v5 = (_QWORD *)(**(__int64 (__fastcall ***)(CWnd *))this)(this);
LABEL_2:
  if ( !v5 )
    return 0;
  for ( i = v5[1]; ; i += 24 )
  {
    if ( !*(_DWORD *)i )
    {
      v5 = (_QWORD *)*v5;
      goto LABEL_2;
    }
    if ( *(_DWORD *)i == 273 && *(_DWORD *)(i + 4) == v3 && *(_DWORD *)(i + 8) == v4 )
      break;
  }
  (*(void (__fastcall **)(CWnd *))(i + 16))(this);
  return 1;
}

```

## disassembly

```asm
0x1800047a0  mov     [rsp+arg_0], rbx
0x1800047a5  mov     [rsp+arg_8], rsi
0x1800047aa  push    rdi
0x1800047ab  sub     rsp, 20h
0x1800047af  mov     rax, [rcx]
0x1800047b2  mov     rbx, rcx
0x1800047b5  movzx   edi, dx
0x1800047b8  shr     rdx, 10h
0x1800047bc  movzx   esi, dx
0x1800047bf  mov     rax, [rax]
0x1800047c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047c7  mov     rdx, rax
0x1800047ca  test    rdx, rdx
0x1800047cd  jz      short loc_180004805
0x1800047cf  mov     rax, [rdx+8]
0x1800047d3  cmp     dword ptr [rax], 0
0x1800047d6  jz      short loc_1800047F0
0x1800047d8  cmp     dword ptr [rax], 111h
0x1800047de  jnz     short loc_1800047EA
0x1800047e0  cmp     [rax+4], edi
0x1800047e3  jnz     short loc_1800047EA
0x1800047e5  cmp     [rax+8], esi
0x1800047e8  jz      short loc_1800047F5
0x1800047ea  add     rax, 18h
0x1800047ee  jmp     short loc_1800047D3
0x1800047f0  mov     rdx, [rdx]
0x1800047f3  jmp     short loc_1800047CA
0x1800047f5  mov     rax, [rax+10h]
0x1800047f9  mov     rcx, rbx
0x1800047fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004801  mov     al, 1
0x180004803  jmp     short loc_180004807
0x180004805  xor     al, al
0x180004807  mov     rbx, [rsp+28h+arg_0]
0x18000480c  mov     rsi, [rsp+28h+arg_8]
0x180004811  add     rsp, 20h
0x180004815  pop     rdi
0x180004816  retn
```
