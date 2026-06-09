# INI_STORE::Initialize(IPubPropertyStoreInitializer *)

- ea: `0x180002420`
- end: `0x1800024b3`
- name: `?Initialize@INI_STORE@@UEAAJPEAVIPubPropertyStoreInitializer@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(INI_STORE *this, int (__fastcall ***)(struct IPubPropertyStoreInitializer *, const wchar_t *, wchar_t **))`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002420`
- `0x180004010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002495`
- `msvcrt!_wcsicmp` at `0x180002495`

## pseudocode

```c
__int64 __fastcall INI_STORE::Initialize(
        INI_STORE *this,
        int (__fastcall ***a2)(struct IPubPropertyStoreInitializer *, const wchar_t *, wchar_t **))
{
  int (__fastcall **v2)(struct IPubPropertyStoreInitializer *, const wchar_t *, wchar_t **); // rax
  int v5; // ebx
  wchar_t *v6; // rcx
  wchar_t *String1; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a2;
  String1 = 0;
  v5 = 0;
  if ( v2[1]((struct IPubPropertyStoreInitializer *)a2, L"useAlternateDataStreams", &String1) < 0
    || (v6 = String1) == 0
    || !*String1 )
  {
    if ( (**a2)((struct IPubPropertyStoreInitializer *)a2, L"useAlternateDataStreams", &String1) < 0 )
      goto LABEL_9;
    v6 = String1;
  }
  if ( v6 && !_wcsicmp(v6, L"true") )
    v5 = 1;
LABEL_9:
  *((_DWORD *)this + 3) = v5;
  return 0;
}

```

## disassembly

```asm
0x180002420  push    rbx
0x180002422  push    rbp
0x180002423  push    rsi
0x180002424  push    rdi
0x180002425  sub     rsp, 28h
0x180002429  mov     rax, [rdx]
0x18000242c  lea     r8, [rsp+48h+String1]
0x180002431  mov     rdi, rdx
0x180002434  mov     rsi, rcx
0x180002437  xor     ebp, ebp
0x180002439  lea     rdx, aUsealternateda; "useAlternateDataStreams"
0x180002440  mov     rcx, rdi
0x180002443  mov     [rsp+48h+String1], rbp
0x180002448  mov     rax, [rax+8]
0x18000244c  mov     ebx, ebp
0x18000244e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002453  test    eax, eax
0x180002455  js      short loc_180002466
0x180002457  mov     rcx, [rsp+48h+String1]
0x18000245c  test    rcx, rcx
0x18000245f  jz      short loc_180002466
0x180002461  cmp     [rcx], bp
0x180002464  jnz     short loc_180002489
0x180002466  mov     rax, [rdi]
0x180002469  lea     r8, [rsp+48h+String1]
0x18000246e  lea     rdx, aUsealternateda; "useAlternateDataStreams"
0x180002475  mov     rcx, rdi
0x180002478  mov     rax, [rax]
0x18000247b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002480  test    eax, eax
0x180002482  js      short loc_1800024A5
0x180002484  mov     rcx, [rsp+48h+String1]; String1
0x180002489  test    rcx, rcx
0x18000248c  jz      short loc_1800024A5
0x18000248e  lea     rdx, aTrue; "true"
0x180002495  call    cs:__imp__wcsicmp
0x18000249b  test    eax, eax
0x18000249d  mov     ecx, 1
0x1800024a2  cmovz   ebx, ecx
0x1800024a5  mov     [rsi+0Ch], ebx
0x1800024a8  xor     eax, eax
0x1800024aa  add     rsp, 28h
0x1800024ae  pop     rdi
0x1800024af  pop     rsi
0x1800024b0  pop     rbp
0x1800024b1  pop     rbx
0x1800024b2  retn
```
