# DeclExternalId::ResolveSystemId(StringPtr *)

- ea: `0x10040d950`
- end: `0x10040da4c`
- name: `?ResolveSystemId@DeclExternalId@@IEAAJPEAUStringPtr@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(DeclExternalId *__hidden this, struct StringPtr *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10040da60`

## callees

- `0x1004013b0`
- `0x10040d950`
- `0x100424d90`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10040da32`
- `KERNEL32!HeapFree` at `0x10040da32`
- `SHLWAPI!UrlCombineW` at `0x10040d9ae`
- `SHLWAPI!UrlCombineW` at `0x10040d9ae`

## pseudocode

```c
__int64 __fastcall DeclExternalId::ResolveSystemId(DeclExternalId *this, PCWSTR *a2)
{
  WCHAR *v4; // rbx
  unsigned int v5; // esi
  struct IMalloc *v6; // rcx
  WCHAR *v8; // [rsp+60h] [rbp-18h] BYREF
  DWORD v9; // [rsp+68h] [rbp-10h]
  DWORD pcchCombined; // [rsp+90h] [rbp+18h] BYREF

  v4 = (WCHAR *)operator new(0x2000u, *((struct IMalloc **)this + 1));
  pcchCombined = 4096;
  v5 = UrlCombineW(*a2, *((PCWSTR *)this + 8), v4, &pcchCombined, 0);
  if ( !v5 )
  {
    v8 = v4;
    v9 = pcchCombined;
    (*(void (__fastcall **)(DeclExternalId *, WCHAR **))(*(_QWORD *)this + 48LL))(this, &v8);
  }
  v6 = (struct IMalloc *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    if ( v6 || (v6 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, WCHAR *))v6->lpVtbl->Free)(v6, v4);
    else
      HeapFree(g_hHeap, 0, v4);
  }
  return v5;
}

```

## disassembly

```asm
0x10040d950  mov     [rsp+arg_8], rbx
0x10040d955  mov     [rsp+arg_18], rsi
0x10040d95a  mov     [rsp+arg_0], rcx
0x10040d95f  push    rdi
0x10040d960  sub     rsp, 70h
0x10040d964  mov     rsi, rdx
0x10040d967  mov     rdi, rcx
0x10040d96a  mov     [rsp+78h+var_30], 0
0x10040d973  mov     rdx, [rcx+8]; struct IMalloc *
0x10040d977  mov     ecx, 2000h; dwBytes
0x10040d97c  call    ??2@YAPEAX_KPEAUIMalloc@@@Z; operator new(unsigned __int64,IMalloc *)
0x10040d981  mov     rbx, rax
0x10040d984  mov     [rsp+78h+var_30], rax
0x10040d989  mov     [rsp+78h+pcchCombined], 1000h
0x10040d994  mov     [rsp+78h+dwFlags], 0; dwFlags
0x10040d99c  lea     r9, [rsp+78h+pcchCombined]; pcchCombined
0x10040d9a4  mov     r8, rax; pszCombined
0x10040d9a7  mov     rdx, [rdi+40h]; pszRelative
0x10040d9ab  mov     rcx, [rsi]; pszBase
0x10040d9ae  call    cs:__imp_UrlCombineW
0x10040d9b4  mov     esi, eax
0x10040d9b6  mov     [rsp+78h+var_40], eax
0x10040d9ba  test    eax, eax
0x10040d9bc  jnz     short loc_10040D9FA
0x10040d9be  mov     [rsp+78h+var_18], rbx
0x10040d9c3  mov     eax, [rsp+78h+pcchCombined]
0x10040d9ca  mov     [rsp+78h+var_10], eax
0x10040d9ce  mov     rax, [rdi]
0x10040d9d1  lea     rdx, [rsp+78h+var_18]
0x10040d9d6  mov     rcx, rdi
0x10040d9d9  mov     rax, [rax+30h]
0x10040d9dd  call    cs:__guard_dispatch_icall_fptr
0x10040d9e3  jmp     short loc_10040D9FA
0x10040d9e5  mov     esi, [rsp+78h+var_48]
0x10040d9e9  mov     [rsp+78h+var_40], esi
0x10040d9ed  mov     rdi, [rsp+78h+arg_0]
0x10040d9f5  mov     rbx, [rsp+78h+var_30]
0x10040d9fa  mov     rcx, [rdi+8]
0x10040d9fe  test    rbx, rbx
0x10040da01  jz      short loc_10040DA38
0x10040da03  test    rcx, rcx
0x10040da06  jnz     short loc_10040DA14
0x10040da08  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040da0f  test    rcx, rcx
0x10040da12  jz      short loc_10040DA26
0x10040da14  mov     rax, [rcx]
0x10040da17  mov     rdx, rbx
0x10040da1a  mov     rax, [rax+28h]
0x10040da1e  call    cs:__guard_dispatch_icall_fptr
0x10040da24  jmp     short loc_10040DA38
0x10040da26  mov     r8, rbx; lpMem
0x10040da29  xor     edx, edx; dwFlags
0x10040da2b  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040da32  call    cs:__imp_HeapFree
0x10040da38  mov     eax, esi
0x10040da3a  lea     r11, [rsp+78h+var_8]
0x10040da3f  mov     rbx, [r11+18h]
0x10040da43  mov     rsi, [r11+28h]
0x10040da47  mov     rsp, r11
0x10040da4a  pop     rdi
0x10040da4b  retn
0x10043a0e0  push    rbp
0x10043a0e2  sub     rsp, 30h
0x10043a0e6  mov     rbp, rdx
0x10043a0e9  mov     [rbp+58h], rcx
0x10043a0ed  mov     [rbp+50h], rcx
0x10043a0f1  mov     rax, [rbp+50h]
0x10043a0f5  mov     rcx, [rax]
0x10043a0f8  mov     [rbp+40h], rcx
0x10043a0fc  mov     rax, [rbp+40h]
0x10043a100  mov     eax, [rax]
0x10043a102  cmp     eax, 0C0000005h
0x10043a107  jz      short loc_10043A139
0x10043a109  add     eax, 1FFFFFFFh
0x10043a10e  cmp     eax, 1
0x10043a111  ja      short loc_10043A129
0x10043a113  mov     rax, [rbp+40h]
0x10043a117  cmp     dword ptr [rax+18h], 1
0x10043a11b  jnz     short loc_10043A129
0x10043a11d  mov     rax, [rbp+40h]
0x10043a121  mov     ecx, [rax+20h]
0x10043a124  mov     [rbp+30h], ecx
0x10043a127  jmp     short loc_10043A130
0x10043a129  mov     dword ptr [rbp+30h], 8000FFFFh
0x10043a130  mov     dword ptr [rbp+34h], 1
0x10043a137  jmp     short loc_10043A140
0x10043a139  mov     dword ptr [rbp+34h], 0
0x10043a140  mov     eax, [rbp+34h]
0x10043a143  add     rsp, 30h
0x10043a147  pop     rbp
0x10043a148  retn
```
