# CWshURLShortcut::get_TargetPath(ushort * *)

- ea: `0x18000dbe0`
- end: `0x18000dcae`
- name: `?get_TargetPath@CWshURLShortcut@@UEAAJPEAPEAG@Z`
- size: `206`
- prototype: `int(CWshURLShortcut *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009b40`
- `0x18000dbe0`
- `0x180011010`

## import_xrefs

- `ole32!CoGetMalloc` at `0x18000dc2e`
- `ole32!CoGetMalloc` at `0x18000dc2e`

## pseudocode

```c
__int64 __fastcall CWshURLShortcut::get_TargetPath(CWshURLShortcut *this, unsigned __int16 **a2)
{
  bool v5; // zf
  HRESULT Malloc; // ebx
  LPCCH lpMultiByteStr; // [rsp+38h] [rbp+10h] BYREF
  LPMALLOC ppMalloc; // [rsp+40h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = *((_QWORD *)this + 9) == 0;
  ppMalloc = 0;
  lpMultiByteStr = 0;
  if ( v5 )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    Malloc = CoGetMalloc(1u, &ppMalloc);
    if ( Malloc >= 0 )
    {
      Malloc = (*(__int64 (__fastcall **)(_QWORD, LPCCH *))(**((_QWORD **)this + 9) + 32LL))(
                 *((_QWORD *)this + 9),
                 &lpMultiByteStr);
      if ( Malloc >= 0 )
      {
        Malloc = PSZToBSTR(lpMultiByteStr, a2);
        if ( Malloc >= 0 )
          Malloc = 0;
      }
    }
    if ( lpMultiByteStr )
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Free)(ppMalloc);
    if ( ppMalloc )
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  }
  return (unsigned int)Malloc;
}

```

## disassembly

```asm
0x18000dbe0  mov     [rsp+arg_0], rbx
0x18000dbe5  mov     [rsp+arg_18], rsi
0x18000dbea  push    rdi
0x18000dbeb  sub     rsp, 20h
0x18000dbef  mov     rdi, rdx
0x18000dbf2  mov     rsi, rcx
0x18000dbf5  test    rdx, rdx
0x18000dbf8  jnz     short loc_18000DC04
0x18000dbfa  mov     eax, 80004003h
0x18000dbff  jmp     loc_18000DC9E
0x18000dc04  cmp     qword ptr [rcx+48h], 0
0x18000dc09  mov     [rsp+28h+ppMalloc], 0
0x18000dc12  mov     [rsp+28h+lpMultiByteStr], 0
0x18000dc1b  jnz     short loc_18000DC24
0x18000dc1d  mov     ebx, 80004005h
0x18000dc22  jmp     short loc_18000DC9C
0x18000dc24  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18000dc29  mov     ecx, 1; dwMemContext
0x18000dc2e  call    cs:__imp_CoGetMalloc
0x18000dc34  mov     ebx, eax
0x18000dc36  test    eax, eax
0x18000dc38  js      short loc_18000DC6B
0x18000dc3a  mov     rcx, [rsi+48h]
0x18000dc3e  lea     rdx, [rsp+28h+lpMultiByteStr]
0x18000dc43  mov     rax, [rcx]
0x18000dc46  mov     rax, [rax+20h]
0x18000dc4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc4f  mov     ebx, eax
0x18000dc51  test    eax, eax
0x18000dc53  js      short loc_18000DC6B
0x18000dc55  mov     rcx, [rsp+28h+lpMultiByteStr]; lpMultiByteStr
0x18000dc5a  mov     rdx, rdi; unsigned __int16 **
0x18000dc5d  call    ?PSZToBSTR@@YAJPEBDPEAPEAG@Z; PSZToBSTR(char const *,ushort * *)
0x18000dc62  mov     ebx, eax
0x18000dc64  xor     eax, eax
0x18000dc66  test    ebx, ebx
0x18000dc68  cmovns  ebx, eax
0x18000dc6b  mov     rdx, [rsp+28h+lpMultiByteStr]
0x18000dc70  test    rdx, rdx
0x18000dc73  jz      short loc_18000DC86
0x18000dc75  mov     rcx, [rsp+28h+ppMalloc]
0x18000dc7a  mov     rax, [rcx]
0x18000dc7d  mov     rax, [rax+28h]
0x18000dc81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc86  mov     rcx, [rsp+28h+ppMalloc]
0x18000dc8b  test    rcx, rcx
0x18000dc8e  jz      short loc_18000DC9C
0x18000dc90  mov     rax, [rcx]
0x18000dc93  mov     rax, [rax+10h]
0x18000dc97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc9c  mov     eax, ebx
0x18000dc9e  mov     rbx, [rsp+28h+arg_0]
0x18000dca3  mov     rsi, [rsp+28h+arg_18]
0x18000dca8  add     rsp, 20h
0x18000dcac  pop     rdi
0x18000dcad  retn
```
