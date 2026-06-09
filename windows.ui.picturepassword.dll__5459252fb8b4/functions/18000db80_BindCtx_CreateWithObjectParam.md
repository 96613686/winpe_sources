# BindCtx_CreateWithObjectParam

- ea: `0x18000db80`
- end: `0x18000dc48`
- name: `BindCtx_CreateWithObjectParam`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011250`

## callees

- `0x180003ffc`
- `0x18000cccc`
- `0x18000db80`
- `0x180010c90`
- `0x18001f010`

## import_xrefs

- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18000dbac`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18000dbac`

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
  LPBC v11; // [rsp+38h] [rbp+10h] BYREF

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
             L"BindToLocalStream",
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
0x18000db80  mov     rax, rsp
0x18000db83  mov     [rax+8], rbx
0x18000db87  mov     [rax+18h], rsi
0x18000db8b  mov     [rax+10h], rdx
0x18000db8f  push    rdi
0x18000db90  sub     rsp, 20h
0x18000db94  lea     rdx, [rax+10h]; ppbc
0x18000db98  mov     qword ptr [r8], 0
0x18000db9f  xor     ecx, ecx; reserved
0x18000dba1  mov     qword ptr [rax+10h], 0
0x18000dba9  mov     rsi, r8
0x18000dbac  call    cs:__imp_CreateBindCtx
0x18000dbb2  mov     ebx, eax
0x18000dbb4  test    eax, eax
0x18000dbb6  js      short loc_18000DC36
0x18000dbb8  mov     rbx, [rsp+28h+arg_8]
0x18000dbbd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dbc4  mov     ecx, 40h ; '@'; unsigned __int64
0x18000dbc9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000dbce  test    rax, rax
0x18000dbd1  jz      short loc_18000DC20
0x18000dbd3  mov     rcx, rax; this
0x18000dbd6  call    ??0CDummyUnknown@@QEAA@XZ; CDummyUnknown::CDummyUnknown(void)
0x18000dbdb  mov     rdi, rax
0x18000dbde  test    rax, rax
0x18000dbe1  jz      short loc_18000DC20
0x18000dbe3  mov     rdx, [rbx]
0x18000dbe6  mov     r8, rdi
0x18000dbe9  mov     rcx, rbx
0x18000dbec  mov     rax, [rdx+48h]
0x18000dbf0  lea     rdx, aBindtolocalstr; "BindToLocalStream"
0x18000dbf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbfc  mov     rcx, rdi; this
0x18000dbff  mov     ebx, eax
0x18000dc01  call    ?Release@CDummyUnknown@@UEAAKXZ; CDummyUnknown::Release(void)
0x18000dc06  test    ebx, ebx
0x18000dc08  js      short loc_18000DC25
0x18000dc0a  mov     rcx, [rsp+28h+arg_8]
0x18000dc0f  mov     [rsi], rcx
0x18000dc12  mov     rax, [rcx]
0x18000dc15  mov     rax, [rax+8]
0x18000dc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc1e  jmp     short loc_18000DC25
0x18000dc20  mov     ebx, 8007000Eh
0x18000dc25  mov     rcx, [rsp+28h+arg_8]
0x18000dc2a  mov     rax, [rcx]
0x18000dc2d  mov     rax, [rax+10h]
0x18000dc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc36  mov     rsi, [rsp+28h+arg_10]
0x18000dc3b  mov     eax, ebx
0x18000dc3d  mov     rbx, [rsp+28h+arg_0]
0x18000dc42  add     rsp, 20h
0x18000dc46  pop     rdi
0x18000dc47  retn
```
