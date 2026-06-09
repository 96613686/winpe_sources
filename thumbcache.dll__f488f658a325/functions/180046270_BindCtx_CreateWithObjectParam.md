# BindCtx_CreateWithObjectParam

- ea: `0x180046270`
- end: `0x180046359`
- name: `BindCtx_CreateWithObjectParam`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180046b60`

## callees

- `0x180035830`
- `0x180035860`
- `0x1800461c4`
- `0x180046270`
- `0x180046e40`
- `0x180049010`

## import_xrefs

- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800462a7`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800462a7`

## string_xrefs

- `0x1800462f4`: `Don't Resolve Link`

## pseudocode

```c
__int64 __fastcall BindCtx_CreateWithObjectParam(__int64 a1, __int64 a2, _QWORD *a3)
{
  HRESULT v4; // ebx
  LPBC v5; // rbx
  CDummyUnknown *v6; // rax
  CDummyUnknown *v7; // rax
  CDummyUnknown *v8; // rdi
  LPBC v9; // rcx
  LPBC v11; // [rsp+28h] [rbp-20h] BYREF

  *a3 = 0;
  v11 = 0;
  v4 = CreateBindCtx(0, &v11);
  if ( v4 >= 0 )
  {
    v5 = v11;
    v6 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 && (v7 = CDummyUnknown::CDummyUnknown(v6), (v8 = v7) != 0) )
    {
      v4 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, CDummyUnknown *))v5->lpVtbl->RegisterObjectParam)(
             v5,
             L"Don't Resolve Link",
             v7);
      CDummyUnknown::Release(v8);
      if ( v4 >= 0 )
      {
        v9 = v11;
        *a3 = v11;
        ((void (__fastcall *)(LPBC))v9->lpVtbl->AddRef)(v9);
      }
    }
    else
    {
      v4 = -2147024882;
    }
    ((void (__fastcall *)(LPBC))v11->lpVtbl->Release)(v11);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180046270  mov     r11, rsp
0x180046273  mov     [r11+8], rbx
0x180046277  mov     [r11+10h], rsi
0x18004627b  push    rdi
0x18004627c  sub     rsp, 40h
0x180046280  mov     rax, cs:__security_cookie
0x180046287  xor     rax, rsp
0x18004628a  mov     [rsp+48h+var_18], rax
0x18004628f  lea     rdx, [r11-20h]; ppbc
0x180046293  mov     qword ptr [r8], 0
0x18004629a  xor     ecx, ecx; reserved
0x18004629c  mov     qword ptr [r11-20h], 0
0x1800462a4  mov     rsi, r8
0x1800462a7  call    cs:__imp_CreateBindCtx
0x1800462ad  mov     ebx, eax
0x1800462af  test    eax, eax
0x1800462b1  js      loc_18004633A
0x1800462b7  mov     rbx, [rsp+48h+var_20]
0x1800462bc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800462c3  mov     ecx, 40h ; '@'; unsigned __int64
0x1800462c8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800462cd  mov     [rsp+48h+var_28], rax
0x1800462d2  test    rax, rax
0x1800462d5  jz      short loc_180046324
0x1800462d7  mov     rcx, rax; this
0x1800462da  call    ??0CDummyUnknown@@QEAA@XZ; CDummyUnknown::CDummyUnknown(void)
0x1800462df  mov     rdi, rax
0x1800462e2  test    rax, rax
0x1800462e5  jz      short loc_180046324
0x1800462e7  mov     rdx, [rbx]
0x1800462ea  mov     r8, rdi
0x1800462ed  mov     rcx, rbx
0x1800462f0  mov     rax, [rdx+48h]
0x1800462f4  lea     rdx, aDonTResolveLin; "Don't Resolve Link"
0x1800462fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046300  mov     rcx, rdi; this
0x180046303  mov     ebx, eax
0x180046305  call    ?Release@CDummyUnknown@@UEAAKXZ; CDummyUnknown::Release(void)
0x18004630a  test    ebx, ebx
0x18004630c  js      short loc_180046329
0x18004630e  mov     rcx, [rsp+48h+var_20]
0x180046313  mov     [rsi], rcx
0x180046316  mov     rax, [rcx]
0x180046319  mov     rax, [rax+8]
0x18004631d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046322  jmp     short loc_180046329
0x180046324  mov     ebx, 8007000Eh
0x180046329  mov     rcx, [rsp+48h+var_20]
0x18004632e  mov     rax, [rcx]
0x180046331  mov     rax, [rax+10h]
0x180046335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004633a  mov     eax, ebx
0x18004633c  mov     rcx, [rsp+48h+var_18]
0x180046341  xor     rcx, rsp; StackCookie
0x180046344  call    __security_check_cookie
0x180046349  mov     rbx, [rsp+48h+arg_0]
0x18004634e  mov     rsi, [rsp+48h+arg_8]
0x180046353  add     rsp, 40h
0x180046357  pop     rdi
0x180046358  retn
```
