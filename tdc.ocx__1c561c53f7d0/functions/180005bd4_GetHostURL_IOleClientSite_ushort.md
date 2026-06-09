# GetHostURL(IOleClientSite *,ushort * *)

- ea: `0x180005bd4`
- end: `0x180005c8b`
- name: `?GetHostURL@@YAJPEAUIOleClientSite@@PEAPEAG@Z`
- size: `183`
- prototype: `__int64 __fastcall(struct IOleClientSite *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003c90`
- `0x180008b40`
- `0x180008d70`
- `0x180008e40`

## callees

- `0x180005bd4`
- `0x180015010`

## import_xrefs

- `ole32!CreateBindCtx` at `0x180005c25`
- `ole32!CreateBindCtx` at `0x180005c25`

## pseudocode

```c
__int64 __fastcall GetHostURL(struct IOleClientSite *a1, unsigned __int16 **a2)
{
  HRESULT v3; // ebx
  LPBC ppbc; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  ppbc = 0;
  if ( a1 )
  {
    v3 = ((__int64 (__fastcall *)(struct IOleClientSite *, __int64, __int64, __int64 *))a1->lpVtbl->GetMoniker)(
           a1,
           1,
           1,
           &v6);
    if ( v3 >= 0 )
    {
      v3 = CreateBindCtx(0, &ppbc);
      if ( v3 >= 0 )
        v3 = (*(__int64 (__fastcall **)(__int64, LPBC, _QWORD, unsigned __int16 **))(*(_QWORD *)v6 + 160LL))(
               v6,
               ppbc,
               0,
               a2);
    }
    if ( ppbc )
      ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180005bd4  mov     [rsp+arg_8], rbx
0x180005bd9  push    rdi
0x180005bda  sub     rsp, 30h
0x180005bde  mov     [rsp+38h+arg_10], 0
0x180005be7  mov     rdi, rdx
0x180005bea  mov     [rsp+38h+ppbc], 0
0x180005bf3  test    rcx, rcx
0x180005bf6  jnz     short loc_180005BFF
0x180005bf8  mov     ebx, 80004005h
0x180005bfd  jmp     short loc_180005C7E
0x180005bff  mov     rax, [rcx]
0x180005c02  lea     r9, [rsp+38h+arg_10]
0x180005c07  mov     edx, 1
0x180005c0c  mov     r8d, edx
0x180005c0f  mov     rax, [rax+20h]
0x180005c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c18  mov     ebx, eax
0x180005c1a  test    eax, eax
0x180005c1c  js      short loc_180005C52
0x180005c1e  lea     rdx, [rsp+38h+ppbc]; ppbc
0x180005c23  xor     ecx, ecx; reserved
0x180005c25  call    cs:__imp_CreateBindCtx
0x180005c2b  mov     ebx, eax
0x180005c2d  test    eax, eax
0x180005c2f  js      short loc_180005C52
0x180005c31  mov     rcx, [rsp+38h+arg_10]
0x180005c36  mov     r9, rdi
0x180005c39  mov     rdx, [rsp+38h+ppbc]
0x180005c3e  xor     r8d, r8d
0x180005c41  mov     rax, [rcx]
0x180005c44  mov     rax, [rax+0A0h]
0x180005c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c50  mov     ebx, eax
0x180005c52  mov     rcx, [rsp+38h+ppbc]
0x180005c57  test    rcx, rcx
0x180005c5a  jz      short loc_180005C68
0x180005c5c  mov     rax, [rcx]
0x180005c5f  mov     rax, [rax+10h]
0x180005c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c68  mov     rcx, [rsp+38h+arg_10]
0x180005c6d  test    rcx, rcx
0x180005c70  jz      short loc_180005C7E
0x180005c72  mov     rax, [rcx]
0x180005c75  mov     rax, [rax+10h]
0x180005c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c7e  mov     eax, ebx
0x180005c80  mov     rbx, [rsp+38h+arg_8]
0x180005c85  add     rsp, 30h
0x180005c89  pop     rdi
0x180005c8a  retn
```
