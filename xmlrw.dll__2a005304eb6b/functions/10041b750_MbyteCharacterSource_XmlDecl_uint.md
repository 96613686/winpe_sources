# MbyteCharacterSource::XmlDecl(uint *)

- ea: `0x10041b750`
- end: `0x10041b88f`
- name: `?XmlDecl@MbyteCharacterSource@@UEAAPEBEPEAI@Z`
- size: `319`
- prototype: `const unsigned __int8 *__fastcall(MbyteCharacterSource *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x100401780`
- `0x10041b750`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10041b826`
- `KERNEL32!HeapAlloc` at `0x10041b826`
- `KERNEL32!HeapFree` at `0x10041b7a8`
- `KERNEL32!HeapFree` at `0x10041b7a8`
- `KERNEL32!WideCharToMultiByte` at `0x10041b7dd`
- `KERNEL32!WideCharToMultiByte` at `0x10041b860`
- `KERNEL32!WideCharToMultiByte` at `0x10041b7dd`
- `KERNEL32!WideCharToMultiByte` at `0x10041b860`

## string_xrefs

- `0x10041b7bb`: `<?xml version="1.0"?>`
- `0x10041b837`: `<?xml version="1.0"?>`

## pseudocode

```c
const unsigned __int8 *__fastcall MbyteCharacterSource::XmlDecl(MbyteCharacterSource *this, unsigned int *a2)
{
  void *v2; // r8
  struct IMalloc *v5; // rcx
  unsigned int v6; // eax
  __int64 v7; // rcx
  int cbMultiByte; // edi
  CHAR *lpMultiByteStr; // rax
  UINT v10; // ecx

  v2 = (void *)*((_QWORD *)this + 32);
  if ( v2 )
  {
    v5 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v5 || (v5 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, void *))v5->lpVtbl->Free)(v5, v2);
    else
      HeapFree(g_hHeap, 0, v2);
    *((_QWORD *)this + 32) = 0;
  }
  v6 = WideCharToMultiByte(*((_DWORD *)this + 62), 0, L"<?xml version=\"1.0\"?>", 21, 0, 0, 0, 0);
  v7 = *((_QWORD *)this + 1);
  cbMultiByte = v6;
  if ( v7 )
  {
    lpMultiByteStr = (CHAR *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 24LL))(v7, v6);
  }
  else if ( g_pMalloc )
  {
    lpMultiByteStr = (CHAR *)((__int64 (__fastcall *)(struct IMalloc *, _QWORD))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, v6);
  }
  else
  {
    lpMultiByteStr = (CHAR *)HeapAlloc(g_hHeap, 0, v6);
  }
  if ( !lpMultiByteStr )
  {
    MXRRaiseException(-2147024882);
    JUMPOUT(0x10041B88ELL);
  }
  v10 = *((_DWORD *)this + 62);
  *((_QWORD *)this + 32) = lpMultiByteStr;
  WideCharToMultiByte(v10, 0, L"<?xml version=\"1.0\"?>", 21, lpMultiByteStr, cbMultiByte, 0, 0);
  *a2 = cbMultiByte;
  return (const unsigned __int8 *)*((_QWORD *)this + 32);
}

```

## disassembly

```asm
0x10041b750  mov     [rsp+arg_0], rbx
0x10041b755  mov     [rsp+arg_8], rbp
0x10041b75a  mov     [rsp+arg_10], rsi
0x10041b75f  push    rdi
0x10041b760  sub     rsp, 40h
0x10041b764  mov     r8, [rcx+100h]; lpMem
0x10041b76b  xor     ebp, ebp
0x10041b76d  mov     rsi, rdx
0x10041b770  mov     rbx, rcx
0x10041b773  test    r8, r8
0x10041b776  jz      short loc_10041B7B5
0x10041b778  mov     rcx, [rcx+8]
0x10041b77c  test    rcx, rcx
0x10041b77f  jnz     short loc_10041B78D
0x10041b781  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041b788  test    rcx, rcx
0x10041b78b  jz      short loc_10041B79F
0x10041b78d  mov     rax, [rcx]
0x10041b790  mov     rdx, r8
0x10041b793  mov     rax, [rax+28h]
0x10041b797  call    cs:__guard_dispatch_icall_fptr
0x10041b79d  jmp     short loc_10041B7AE
0x10041b79f  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041b7a6  xor     edx, edx; dwFlags
0x10041b7a8  call    cs:__imp_HeapFree
0x10041b7ae  mov     [rbx+100h], rbp
0x10041b7b5  mov     ecx, [rbx+0F8h]; CodePage
0x10041b7bb  lea     r8, WideCharStr; "<?xml version=\"1.0\"?>"
0x10041b7c2  mov     [rsp+48h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x10041b7c7  mov     r9d, 15h; cchWideChar
0x10041b7cd  mov     [rsp+48h+lpDefaultChar], rbp; lpDefaultChar
0x10041b7d2  xor     edx, edx; dwFlags
0x10041b7d4  mov     [rsp+48h+cbMultiByte], ebp; cbMultiByte
0x10041b7d8  mov     [rsp+48h+lpMultiByteStr], rbp; lpMultiByteStr
0x10041b7dd  call    cs:__imp_WideCharToMultiByte
0x10041b7e3  mov     rcx, [rbx+8]
0x10041b7e7  mov     edi, eax
0x10041b7e9  mov     edx, eax
0x10041b7eb  test    rcx, rcx
0x10041b7ee  jz      short loc_10041B7FF
0x10041b7f0  mov     r8, [rcx]
0x10041b7f3  mov     rax, [r8+18h]
0x10041b7f7  call    cs:__guard_dispatch_icall_fptr
0x10041b7fd  jmp     short loc_10041B82C
0x10041b7ff  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041b806  test    rcx, rcx
0x10041b809  jz      short loc_10041B81A
0x10041b80b  mov     rax, [rcx]
0x10041b80e  mov     rax, [rax+18h]
0x10041b812  call    cs:__guard_dispatch_icall_fptr
0x10041b818  jmp     short loc_10041B82C
0x10041b81a  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041b821  mov     r8, rdx; dwBytes
0x10041b824  xor     edx, edx; dwFlags
0x10041b826  call    cs:__imp_HeapAlloc
0x10041b82c  test    rax, rax
0x10041b82f  jz      short loc_10041B884
0x10041b831  mov     ecx, [rbx+0F8h]; CodePage
0x10041b837  lea     r8, WideCharStr; "<?xml version=\"1.0\"?>"
0x10041b83e  mov     [rsp+48h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x10041b843  mov     r9d, 15h; cchWideChar
0x10041b849  mov     [rsp+48h+lpDefaultChar], rbp; lpDefaultChar
0x10041b84e  xor     edx, edx; dwFlags
0x10041b850  mov     [rsp+48h+cbMultiByte], edi; cbMultiByte
0x10041b854  mov     [rsp+48h+lpMultiByteStr], rax; lpMultiByteStr
0x10041b859  mov     [rbx+100h], rax
0x10041b860  call    cs:__imp_WideCharToMultiByte
0x10041b866  mov     rbp, [rsp+48h+arg_8]
0x10041b86b  mov     [rsi], edi
0x10041b86d  mov     rax, [rbx+100h]
0x10041b874  mov     rbx, [rsp+48h+arg_0]
0x10041b879  mov     rsi, [rsp+48h+arg_10]
0x10041b87e  add     rsp, 40h
0x10041b882  pop     rdi
0x10041b883  retn
0x10041b884  mov     ecx, 8007000Eh; int
0x10041b889  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
