# CBaseFolder::_IsValidItemName(ushort const *)

- ea: `0x180039c8c`
- end: `0x180039d6e`
- name: `?_IsValidItemName@CBaseFolder@@IEAAHPEBG@Z`
- size: `226`
- prototype: `int(CBaseFolder *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180042af0`
- `0x1800430b0`
- `0x180043320`
- `0x1800441d0`
- `0x180044370`
- `0x1800446b0`

## callees

- `0x180039c8c`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180039cfa`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180039cfa`
- `ole32!CoTaskMemFree` at `0x180039d0b`
- `ole32!CoTaskMemFree` at `0x180039d1b`
- `ole32!CoTaskMemFree` at `0x180039d0b`
- `ole32!CoTaskMemFree` at `0x180039d1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall CBaseFolder::_IsValidItemName(CBaseFolder *this, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rdi
  char *v4; // r14
  bool v5; // bl
  wchar_t *Control; // [rsp+48h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+18h] BYREF

  if ( !a2 )
    return 0;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  if ( !v3 )
    return 0;
  pv = 0;
  Control = 0;
  v4 = (char *)this + 32;
  v5 = (*(int (__fastcall **)(char *, LPVOID *, wchar_t **))(*((_QWORD *)this + 4) + 24LL))(
         (char *)this + 32,
         &pv,
         &Control) >= 0
    && wcscspn(a2, Control) == v3;
  CoTaskMemFree(Control);
  Control = 0;
  CoTaskMemFree(pv);
  if ( v5 )
  {
    LODWORD(Control) = 0;
    return (*(int (__fastcall **)(char *, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v4 + 32LL))(
             v4,
             a2,
             &Control) >= 0
        && (!(_DWORD)Control || v3 <= (unsigned int)Control);
  }
  return v5;
}

```

## disassembly

```asm
0x180039c8c  mov     [rsp+arg_0], rbx
0x180039c91  mov     [rsp+arg_18], rbp
0x180039c96  push    rsi
0x180039c97  push    rdi
0x180039c98  push    r14
0x180039c9a  sub     rsp, 20h
0x180039c9e  mov     rsi, rdx
0x180039ca1  xor     ebp, ebp
0x180039ca3  test    rdx, rdx
0x180039ca6  jz      loc_180039D55
0x180039cac  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180039cb0  inc     rdi
0x180039cb3  cmp     [rdx+rdi*2], bp
0x180039cb7  jnz     short loc_180039CB0
0x180039cb9  test    rdi, rdi
0x180039cbc  jz      loc_180039D55
0x180039cc2  mov     [rsp+38h+pv], rbp
0x180039cc7  mov     [rsp+38h+Control], rbp
0x180039ccc  lea     r14, [rcx+20h]
0x180039cd0  mov     rax, [r14]
0x180039cd3  lea     r8, [rsp+38h+Control]
0x180039cd8  lea     rdx, [rsp+38h+pv]
0x180039cdd  mov     rcx, r14
0x180039ce0  mov     rax, [rax+18h]
0x180039ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ce9  test    eax, eax
0x180039ceb  jns     short loc_180039CF2
0x180039ced  mov     bl, bpl
0x180039cf0  jmp     short loc_180039D06
0x180039cf2  mov     rdx, [rsp+38h+Control]; Control
0x180039cf7  mov     rcx, rsi; String
0x180039cfa  call    cs:__imp_wcscspn
0x180039d00  cmp     rax, rdi
0x180039d03  setz    bl
0x180039d06  mov     rcx, [rsp+38h+Control]; pv
0x180039d0b  call    cs:__imp_CoTaskMemFree
0x180039d11  mov     [rsp+38h+Control], rbp
0x180039d16  mov     rcx, [rsp+38h+pv]; pv
0x180039d1b  call    cs:__imp_CoTaskMemFree
0x180039d21  test    bl, bl
0x180039d23  jz      short loc_180039D58
0x180039d25  mov     dword ptr [rsp+38h+Control], ebp
0x180039d29  mov     rax, [r14]
0x180039d2c  lea     r8, [rsp+38h+Control]
0x180039d31  mov     rdx, rsi
0x180039d34  mov     rcx, r14
0x180039d37  mov     rax, [rax+20h]
0x180039d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d40  test    eax, eax
0x180039d42  js      short loc_180039D55
0x180039d44  mov     eax, dword ptr [rsp+38h+Control]
0x180039d48  test    eax, eax
0x180039d4a  jz      short loc_180039D51
0x180039d4c  cmp     rdi, rax
0x180039d4f  ja      short loc_180039D55
0x180039d51  mov     bl, 1
0x180039d53  jmp     short loc_180039D58
0x180039d55  mov     bl, bpl
0x180039d58  movzx   eax, bl
0x180039d5b  mov     rbx, [rsp+38h+arg_0]
0x180039d60  mov     rbp, [rsp+38h+arg_18]
0x180039d65  add     rsp, 20h
0x180039d69  pop     r14
0x180039d6b  pop     rdi
0x180039d6c  pop     rsi
0x180039d6d  retn
```
