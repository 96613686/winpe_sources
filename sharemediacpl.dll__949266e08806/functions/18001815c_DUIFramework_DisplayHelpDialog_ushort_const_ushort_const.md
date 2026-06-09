# DUIFramework_DisplayHelpDialog(ushort const *,ushort const *)

- ea: `0x18001815c`
- end: `0x180018312`
- name: `?DUIFramework_DisplayHelpDialog@@YAJPEBG0@Z`
- size: `438`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007270`
- `0x18000735c`
- `0x18000b78c`

## callees

- `0x18001815c`
- `0x1800187c0`
- `0x18001e010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180018214`
- `KERNEL32!LocalAlloc` at `0x180018214`
- `KERNEL32!LocalFree` at `0x1800182d9`
- `KERNEL32!LocalFree` at `0x1800182d9`
- `ntdll!WinSqmAddToStream` at `0x1800181bc`
- `ntdll!WinSqmAddToStream` at `0x1800181bc`
- `ole32!CoCreateInstance` at `0x1800181eb`
- `ole32!CoCreateInstance` at `0x1800181eb`
- `USER32!SetCursor` at `0x18001817f`
- `USER32!SetCursor` at `0x1800182fd`
- `USER32!SetCursor` at `0x18001817f`
- `USER32!SetCursor` at `0x1800182fd`
- `USER32!LoadCursorW` at `0x180018176`
- `USER32!LoadCursorW` at `0x180018176`

## pseudocode

```c
__int64 __fastcall DUIFramework_DisplayHelpDialog(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HCURSOR CursorW; // rax
  HCURSOR v5; // r14
  bool v6; // zf
  HRESULT v7; // ebx
  __int64 v8; // rdi
  unsigned __int64 v9; // rdi
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rsi
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  unsigned __int64 v14; // rdx
  unsigned __int16 *v15; // r8
  unsigned __int16 *v16; // rcx
  int v18; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v19; // [rsp+38h] [rbp-40h]
  LPVOID ppv; // [rsp+88h] [rbp+10h] BYREF

  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v5 = SetCursor(CursorW);
  if ( a2 )
  {
    v6 = *a2 == 0;
    v18 = 2;
    if ( v6 )
      a2 = L"(null)";
    v19 = a2;
    WinSqmAddToStream(0, 911, 1, &v18);
  }
  ppv = 0;
  v7 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &ppv);
  if ( v7 >= 0 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a1[v8] );
    v9 = v8 + 22;
    v10 = (unsigned __int16 *)LocalAlloc(0, 2 * v9);
    v11 = v10;
    if ( v10 )
    {
      if ( v9 )
      {
        if ( v9 <= 0x7FFFFFFF )
        {
          v12 = 2147483646;
          v13 = L"mshelp://windows/?id=";
          v14 = v9;
          v15 = v11;
          do
          {
            if ( !v12 )
              break;
            if ( !*v13 )
              break;
            *v15++ = *v13++;
            --v12;
            --v14;
          }
          while ( v14 );
          v16 = v15 - 1;
          v7 = v14 == 0 ? 0x8007007A : 0;
          if ( v14 )
            v16 = v15;
          *v16 = 0;
          if ( v14 )
          {
            v7 = StringCchCatW(v11, v9, a1);
            if ( v7 >= 0 )
              v7 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, v11);
          }
        }
        else
        {
          v7 = -2147024809;
          *v10 = 0;
        }
      }
      else
      {
        v7 = -2147024809;
      }
      LocalFree(v11);
    }
    else
    {
      v7 = -2147024882;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  SetCursor(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001815c  push    rbx
0x18001815e  push    rbp
0x18001815f  push    rsi
0x180018160  push    rdi
0x180018161  push    r14
0x180018163  push    r15
0x180018165  sub     rsp, 48h
0x180018169  mov     rbx, rdx
0x18001816c  mov     rbp, rcx
0x18001816f  mov     edx, 7F02h; lpCursorName
0x180018174  xor     ecx, ecx; hInstance
0x180018176  call    cs:__imp_LoadCursorW
0x18001817c  mov     rcx, rax; hCursor
0x18001817f  call    cs:__imp_SetCursor
0x180018185  xor     r15d, r15d
0x180018188  mov     r14, rax
0x18001818b  test    rbx, rbx
0x18001818e  jz      short loc_1800181C2
0x180018190  cmp     [rbx], r15w
0x180018194  lea     rax, aNull; "(null)"
0x18001819b  lea     r9, [rsp+78h+var_48]
0x1800181a0  mov     [rsp+78h+var_48], 2
0x1800181a8  cmovz   rbx, rax
0x1800181ac  lea     r8d, [r15+1]
0x1800181b0  xor     ecx, ecx
0x1800181b2  mov     [rsp+78h+var_40], rbx
0x1800181b7  mov     edx, 38Fh
0x1800181bc  call    cs:__imp_WinSqmAddToStream
0x1800181c2  xor     edx, edx; pUnkOuter
0x1800181c4  mov     [rsp+78h+arg_8], r15
0x1800181cc  lea     rax, [rsp+78h+arg_8]
0x1800181d4  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x1800181db  mov     [rsp+78h+ppv], rax; ppv
0x1800181e0  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x1800181e7  lea     r8d, [rdx+1]; dwClsContext
0x1800181eb  call    cs:__imp_CoCreateInstance
0x1800181f1  mov     ebx, eax
0x1800181f3  test    eax, eax
0x1800181f5  js      loc_1800182FA
0x1800181fb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800181ff  inc     rdi
0x180018202  cmp     [rbp+rdi*2+0], r15w
0x180018208  jnz     short loc_1800181FF
0x18001820a  add     rdi, 16h
0x18001820e  xor     ecx, ecx; uFlags
0x180018210  lea     rdx, [rdi+rdi]; uBytes
0x180018214  call    cs:__imp_LocalAlloc
0x18001821a  mov     rsi, rax
0x18001821d  test    rax, rax
0x180018220  jz      loc_1800182E1
0x180018226  test    rdi, rdi
0x180018229  jz      loc_1800182C8
0x18001822f  cmp     rdi, 7FFFFFFFh
0x180018236  jbe     short loc_180018242
0x180018238  mov     ebx, 80070057h
0x18001823d  jmp     loc_1800182D2
0x180018242  mov     eax, 7FFFFFFEh
0x180018247  lea     rcx, aMshelpWindowsI; "mshelp://windows/?id="
0x18001824e  mov     rdx, rdi
0x180018251  mov     r8, rsi
0x180018254  test    rax, rax
0x180018257  jz      short loc_180018278
0x180018259  movzx   r9d, word ptr [rcx]
0x18001825d  test    r9w, r9w
0x180018261  jz      short loc_180018278
0x180018263  mov     [r8], r9w
0x180018267  add     rcx, 2
0x18001826b  add     r8, 2
0x18001826f  dec     rax
0x180018272  sub     rdx, 1
0x180018276  jnz     short loc_180018254
0x180018278  mov     rax, rdx
0x18001827b  lea     rcx, [r8-2]
0x18001827f  neg     rax
0x180018282  sbb     ebx, ebx
0x180018284  not     ebx
0x180018286  and     ebx, 8007007Ah
0x18001828c  test    rdx, rdx
0x18001828f  cmovnz  rcx, r8
0x180018293  mov     [rcx], r15w
0x180018297  jz      short loc_1800182D6
0x180018299  mov     r8, rbp; unsigned __int16 *
0x18001829c  mov     rdx, rdi; unsigned __int64
0x18001829f  mov     rcx, rsi; unsigned __int16 *
0x1800182a2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800182a7  mov     ebx, eax
0x1800182a9  test    eax, eax
0x1800182ab  js      short loc_1800182D6
0x1800182ad  mov     rcx, [rsp+78h+arg_8]
0x1800182b5  mov     rdx, rsi
0x1800182b8  mov     rax, [rcx]
0x1800182bb  mov     rax, [rax+18h]
0x1800182bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182c4  mov     ebx, eax
0x1800182c6  jmp     short loc_1800182D6
0x1800182c8  mov     ebx, 80070057h
0x1800182cd  test    rdi, rdi
0x1800182d0  jz      short loc_1800182D6
0x1800182d2  mov     [rax], r15w
0x1800182d6  mov     rcx, rsi; hMem
0x1800182d9  call    cs:__imp_LocalFree
0x1800182df  jmp     short loc_1800182E6
0x1800182e1  mov     ebx, 8007000Eh
0x1800182e6  mov     rcx, [rsp+78h+arg_8]
0x1800182ee  mov     rax, [rcx]
0x1800182f1  mov     rax, [rax+10h]
0x1800182f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182fa  mov     rcx, r14; hCursor
0x1800182fd  call    cs:__imp_SetCursor
0x180018303  mov     eax, ebx
0x180018305  add     rsp, 48h
0x180018309  pop     r15
0x18001830b  pop     r14
0x18001830d  pop     rdi
0x18001830e  pop     rsi
0x18001830f  pop     rbp
0x180018310  pop     rbx
0x180018311  retn
```
