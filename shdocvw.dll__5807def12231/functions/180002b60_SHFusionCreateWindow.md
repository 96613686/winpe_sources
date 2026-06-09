# SHFusionCreateWindow

- ea: `0x180002b60`
- end: `0x180002c28`
- name: `SHFusionCreateWindow`
- size: `200`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpClassName@<rcx>, LPCWSTR lpWindowName@<rdx>, DWORD dwStyle@<r8d>, int, int, int, HWND, ULONG_PTR ulCookie, int, LPVOID)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180019ef8`

## callees

- `0x180002b60`
- `0x180002ca0`
- `0x180006880`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180002c14`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180002c14`
- `USER32!CreateWindowExW` at `0x180002bfc`
- `USER32!CreateWindowExW` at `0x180002bfc`

## pseudocode

```c
HWND __fastcall SHFusionCreateWindow(
        LPCWSTR lpClassName,
        LPCWSTR lpWindowName,
        DWORD dwStyle,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        HWND hWndParent,
        ULONG_PTR ulCookie,
        int a10,
        LPVOID lpParam)
{
  HINSTANCE hInstance; // rbx
  HWND Window; // rbx

  hInstance = g_hinst;
  ulCookie = 0;
  if ( !(unsigned int)SHActivateContext(&ulCookie) )
    return 0;
  if ( g_hActCtx != (HANDLE)-3LL )
    DelayLoadCC();
  Window = CreateWindowExW(
             0,
             lpClassName,
             lpWindowName,
             dwStyle,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             hWndParent,
             0,
             hInstance,
             lpParam);
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return Window;
}

```

## disassembly

```asm
0x180002b60  mov     rax, rsp
0x180002b63  push    rbx
0x180002b64  push    rbp
0x180002b65  push    rsi
0x180002b66  push    rdi
0x180002b67  push    r14
0x180002b69  sub     rsp, 60h
0x180002b6d  mov     rbx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x180002b74  mov     rbp, rcx
0x180002b77  xor     r14d, r14d
0x180002b7a  lea     rcx, [rax+48h]
0x180002b7e  mov     [rax+48h], r14
0x180002b82  mov     edi, r8d
0x180002b85  mov     rsi, rdx
0x180002b88  call    SHActivateContext
0x180002b8d  test    eax, eax
0x180002b8f  jnz     short loc_180002B9E
0x180002b91  xor     eax, eax
0x180002b93  add     rsp, 60h
0x180002b97  pop     r14
0x180002b99  pop     rdi
0x180002b9a  pop     rsi
0x180002b9b  pop     rbp
0x180002b9c  pop     rbx
0x180002b9d  retn
0x180002b9e  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x180002ba6  jz      short loc_180002BAD
0x180002ba8  call    DelayLoadCC
0x180002bad  mov     rax, [rsp+88h+arg_50]
0x180002bb5  mov     r9d, edi; dwStyle
0x180002bb8  mov     [rsp+88h+lpParam], rax; lpParam
0x180002bbd  mov     r8, rsi; lpWindowName
0x180002bc0  mov     rax, [rsp+88h+arg_38]
0x180002bc8  mov     rdx, rbp; lpClassName
0x180002bcb  mov     [rsp+88h+hInstance], rbx; hInstance
0x180002bd0  xor     ecx, ecx; dwExStyle
0x180002bd2  mov     [rsp+88h+hMenu], r14; hMenu
0x180002bd7  mov     [rsp+88h+hWndParent], rax; hWndParent
0x180002bdc  mov     [rsp+88h+nHeight], 80000000h; nHeight
0x180002be4  mov     [rsp+88h+nWidth], 80000000h; nWidth
0x180002bec  mov     [rsp+88h+Y], 80000000h; Y
0x180002bf4  mov     [rsp+88h+X], 80000000h; X
0x180002bfc  call    cs:__imp_CreateWindowExW
0x180002c02  mov     rdx, [rsp+88h+ulCookie]; ulCookie
0x180002c0a  mov     rbx, rax
0x180002c0d  test    rdx, rdx
0x180002c10  jz      short loc_180002C1A
0x180002c12  xor     ecx, ecx; dwFlags
0x180002c14  call    cs:__imp_DeactivateActCtx
0x180002c1a  mov     rax, rbx
0x180002c1d  add     rsp, 60h
0x180002c21  pop     r14
0x180002c23  pop     rdi
0x180002c24  pop     rsi
0x180002c25  pop     rbp
0x180002c26  pop     rbx
0x180002c27  retn
```
