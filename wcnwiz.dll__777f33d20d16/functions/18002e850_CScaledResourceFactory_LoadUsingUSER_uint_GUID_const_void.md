# CScaledResourceFactory::_LoadUsingUSER(uint *,_GUID const &,void * *)

- ea: `0x18002e850`
- end: `0x18002e927`
- name: `?_LoadUsingUSER@CScaledResourceFactory@@AEAAJPEAIAEBU_GUID@@PEAPEAX@Z`
- size: `215`
- prototype: `__int64 __fastcall(CScaledResourceFactory *__hidden this, unsigned int *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e76c`

## callees

- `0x18002e850`
- `0x180031010`

## import_xrefs

- `USER32!LoadImageW` at `0x18002e891`
- `USER32!LoadImageW` at `0x18002e891`
- `GDI32!DeleteObject` at `0x18002e905`
- `GDI32!DeleteObject` at `0x18002e905`

## pseudocode

```c
__int64 __fastcall CScaledResourceFactory::_LoadUsingUSER(
        CScaledResourceFactory *this,
        unsigned int *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v7; // ebx
  HANDLE ImageW; // rax
  void *v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // r9
  __int64 result; // rax
  const struct _GUID *v13; // [rsp+60h] [rbp+18h] BYREF

  v13 = a3;
  v7 = -2147467259;
  ImageW = LoadImageW(*((HINSTANCE *)this + 4), *((LPCWSTR *)this + 5), 0, 0, 0, 0x2000u);
  v9 = ImageW;
  if ( ImageW )
  {
    v10 = *((_QWORD *)this + 3);
    v11 = *((unsigned int *)this + 14);
    v13 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, HANDLE, _QWORD, __int64, const struct _GUID **))(*(_QWORD *)v10 + 168LL))(
           v10,
           ImageW,
           0,
           v11,
           &v13);
    if ( v7 >= 0 )
    {
      v7 = (**(__int64 (__fastcall ***)(const struct _GUID *, GUID *, void **))&v13->Data1)(
             v13,
             &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
             a4);
      (*(void (__fastcall **)(const struct _GUID *))(*(_QWORD *)&v13->Data1 + 16LL))(v13);
    }
    DeleteObject(v9);
  }
  result = (unsigned int)v7;
  *a2 = 96;
  return result;
}

```

## disassembly

```asm
0x18002e850  mov     rax, rsp
0x18002e853  mov     [rax+8], rbx
0x18002e857  mov     [rax+10h], rbp
0x18002e85b  mov     [rax+18h], r8
0x18002e85f  push    rsi
0x18002e860  push    rdi
0x18002e861  push    r14
0x18002e863  sub     rsp, 30h
0x18002e867  mov     r14, rdx
0x18002e86a  mov     dword ptr [rax-20h], 2000h
0x18002e871  mov     rdx, [rcx+28h]; name
0x18002e875  mov     rbp, r9
0x18002e878  mov     rsi, rcx
0x18002e87b  mov     dword ptr [rax-28h], 0
0x18002e882  mov     rcx, [rcx+20h]; hInst
0x18002e886  xor     r9d, r9d; cx
0x18002e889  xor     r8d, r8d; type
0x18002e88c  mov     ebx, 80004005h
0x18002e891  call    cs:__imp_LoadImageW
0x18002e897  mov     rdi, rax
0x18002e89a  test    rax, rax
0x18002e89d  jz      short loc_18002E90B
0x18002e89f  mov     rcx, [rsi+18h]
0x18002e8a3  lea     rdx, [rsp+48h+arg_10]
0x18002e8a8  mov     r9d, [rsi+38h]
0x18002e8ac  xor     r8d, r8d
0x18002e8af  mov     [rsp+48h+arg_10], 0
0x18002e8b8  mov     [rsp+48h+var_28], rdx
0x18002e8bd  mov     rdx, rdi
0x18002e8c0  mov     rax, [rcx]
0x18002e8c3  mov     rax, [rax+0A8h]
0x18002e8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8cf  mov     ebx, eax
0x18002e8d1  test    eax, eax
0x18002e8d3  js      short loc_18002E902
0x18002e8d5  mov     rcx, [rsp+48h+arg_10]
0x18002e8da  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x18002e8e1  mov     r8, rbp
0x18002e8e4  mov     rax, [rcx]
0x18002e8e7  mov     rax, [rax]
0x18002e8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8ef  mov     rcx, [rsp+48h+arg_10]
0x18002e8f4  mov     ebx, eax
0x18002e8f6  mov     rax, [rcx]
0x18002e8f9  mov     rax, [rax+10h]
0x18002e8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e902  mov     rcx, rdi; ho
0x18002e905  call    cs:__imp_DeleteObject
0x18002e90b  mov     rbp, [rsp+48h+arg_8]
0x18002e910  mov     eax, ebx
0x18002e912  mov     rbx, [rsp+48h+arg_0]
0x18002e917  mov     dword ptr [r14], 60h ; '`'
0x18002e91e  add     rsp, 30h
0x18002e922  pop     r14
0x18002e924  pop     rdi
0x18002e925  pop     rsi
0x18002e926  retn
```
