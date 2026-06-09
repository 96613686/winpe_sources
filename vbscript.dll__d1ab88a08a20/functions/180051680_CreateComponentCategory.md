# CreateComponentCategory

- ea: `0x180051680`
- end: `0x18005179b`
- name: `CreateComponentCategory`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045c4c`

## callees

- `0x180051680`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18005172f`
- `msvcrt!wcsncpy_s` at `0x18005172f`
- `OLE32!CoCreateInstance` at `0x1800516d4`
- `OLE32!CoCreateInstance` at `0x1800516d4`

## pseudocode

```c
HRESULT __fastcall CreateComponentCategory(__int128 *a1, const wchar_t *a2)
{
  __int128 v2; // xmm6
  HRESULT result; // eax
  rsize_t v5; // rbx
  LPVOID v6; // rcx
  int v7; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-158h] BYREF
  __int128 v9; // [rsp+40h] [rbp-148h] BYREF
  int v10; // [rsp+50h] [rbp-138h]
  wchar_t Destination[134]; // [rsp+54h] [rbp-134h] BYREF

  v2 = *a1;
  ppv = 0;
  result = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &ppv);
  if ( result >= 0 )
  {
    memset_0(Destination, 0, 0x100u);
    v5 = -1;
    v10 = 1033;
    v9 = v2;
    do
      ++v5;
    while ( a2[v5] );
    if ( v5 > 0x7F )
      v5 = 127;
    wcsncpy_s(Destination, 0x80u, a2, v5);
    v6 = ppv;
    Destination[v5] = 0;
    v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)v6 + 24LL))(v6, 1, &v9);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180051680  mov     rax, rsp
0x180051683  mov     [rax+18h], rbx
0x180051687  mov     [rax+20h], rsi
0x18005168b  push    rdi
0x18005168c  sub     rsp, 180h
0x180051693  movaps  xmmword ptr [rax-18h], xmm6
0x180051697  mov     rax, cs:__security_cookie
0x18005169e  xor     rax, rsp
0x1800516a1  mov     [rsp+188h+var_28], rax
0x1800516a9  movaps  xmm6, xmmword ptr [rcx]
0x1800516ac  lea     rax, [rsp+188h+var_158]
0x1800516b1  xor     esi, esi
0x1800516b3  mov     [rsp+188h+ppv], rax; ppv
0x1800516b8  mov     rdi, rdx
0x1800516bb  mov     [rsp+188h+var_158], rsi
0x1800516c0  lea     r9, IID_ICatRegister; riid
0x1800516c7  xor     edx, edx; pUnkOuter
0x1800516c9  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800516d0  lea     r8d, [rsi+1]; dwClsContext
0x1800516d4  call    cs:__imp_CoCreateInstance
0x1800516db  nop     dword ptr [rax+rax+00h]
0x1800516e0  test    eax, eax
0x1800516e2  js      loc_180051770
0x1800516e8  xor     edx, edx; Val
0x1800516ea  lea     rcx, [rsp+188h+Destination]; void *
0x1800516ef  mov     r8d, 100h; Size
0x1800516f5  call    memset_0
0x1800516fa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800516fe  mov     [rsp+188h+var_138], 409h
0x180051706  movdqu  [rsp+188h+var_148], xmm6
0x18005170c  inc     rbx
0x18005170f  cmp     [rdi+rbx*2], si
0x180051713  jnz     short loc_18005170C
0x180051715  mov     eax, 7Fh
0x18005171a  lea     rcx, [rsp+188h+Destination]; Destination
0x18005171f  cmp     rbx, rax
0x180051722  mov     r8, rdi; Source
0x180051725  cmova   rbx, rax
0x180051729  mov     r9, rbx; MaxCount
0x18005172c  lea     edx, [rax+1]; SizeInWords
0x18005172f  call    cs:__imp_wcsncpy_s
0x180051736  nop     dword ptr [rax+rax+00h]
0x18005173b  mov     rcx, [rsp+188h+var_158]
0x180051740  lea     r8, [rsp+188h+var_148]
0x180051745  mov     [rsp+rbx*2+188h+Destination], si
0x18005174a  mov     edx, 1
0x18005174f  mov     rax, [rcx]
0x180051752  mov     rax, [rax+18h]
0x180051756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005175b  mov     rcx, [rsp+188h+var_158]
0x180051760  mov     ebx, eax
0x180051762  mov     rdx, [rcx]
0x180051765  mov     rax, [rdx+10h]
0x180051769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005176e  mov     eax, ebx
0x180051770  mov     rcx, [rsp+188h+var_28]
0x180051778  xor     rcx, rsp; StackCookie
0x18005177b  call    __security_check_cookie
0x180051780  lea     r11, [rsp+188h+var_8]
0x180051788  mov     rbx, [r11+20h]
0x18005178c  mov     rsi, [r11+28h]
0x180051790  movaps  xmm6, xmmword ptr [r11-10h]
0x180051795  mov     rsp, r11
0x180051798  pop     rdi
0x180051799  retn
```
