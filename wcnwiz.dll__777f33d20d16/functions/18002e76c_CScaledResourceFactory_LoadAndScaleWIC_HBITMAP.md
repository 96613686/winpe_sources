# CScaledResourceFactory::_LoadAndScaleWIC(HBITMAP__ * *)

- ea: `0x18002e76c`
- end: `0x18002e847`
- name: `?_LoadAndScaleWIC@CScaledResourceFactory@@AEAAJPEAPEAUHBITMAP__@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(CScaledResourceFactory *__hidden this, HBITMAP *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002e5ec`

## callees

- `0x18002e76c`
- `0x18002e850`
- `0x18002e930`
- `0x18002e9f4`
- `0x180031010`

## import_xrefs

- `WindowsCodecs!WICCreateImagingFactory_Proxy` at `0x18002e794`
- `WindowsCodecs!WICCreateImagingFactory_Proxy` at `0x18002e794`

## pseudocode

```c
__int64 __fastcall CScaledResourceFactory::_LoadAndScaleWIC(
        CScaledResourceFactory *this,
        HBITMAP *a2,
        const struct _GUID *a3)
{
  HBITMAP v3; // rsi
  int v6; // edi
  const struct _GUID *v7; // r8
  unsigned int v8; // r9d
  int v9; // r8d
  unsigned int v11; // [rsp+60h] [rbp+30h] BYREF
  struct IWICBitmapSource *v12; // [rsp+68h] [rbp+38h] BYREF
  HBITMAP v13; // [rsp+70h] [rbp+40h] BYREF

  v3 = 0;
  v13 = 0;
  if ( *((_QWORD *)this + 3) || (v6 = WICCreateImagingFactory_Proxy(567), v6 >= 0) )
  {
    v11 = 0;
    v12 = 0;
    if ( (int)CScaledResourceFactory::_LoadUsingWIC(this, &v11, a3, (void **)&v12) >= 0
      || (v6 = CScaledResourceFactory::_LoadUsingUSER(this, &v11, v7, (void **)&v12), v6 >= 0) )
    {
      if ( *((_BYTE *)this + 12) )
      {
        v8 = 100 * v11;
        v9 = 96 * (int)(float)((float)(*((float *)this + 2) * 100.0) + 0.5);
      }
      else
      {
        v8 = v11;
        v9 = *((_DWORD *)this + 12);
      }
      v6 = CScaledResourceFactory::_ScaleSource(this, v12, v9, v8, &v13);
      ((void (__fastcall *)(struct IWICBitmapSource *))v12->lpVtbl->Release)(v12);
      v3 = v13;
    }
  }
  *a2 = v3;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002e76c  push    rbp
0x18002e76e  push    rbx
0x18002e76f  push    rsi
0x18002e770  push    rdi
0x18002e771  push    r14
0x18002e773  mov     rbp, rsp
0x18002e776  sub     rsp, 30h
0x18002e77a  xor     esi, esi
0x18002e77c  mov     r14, rdx
0x18002e77f  lea     rdx, [rcx+18h]
0x18002e783  mov     [rbp+arg_10], rsi
0x18002e787  mov     rbx, rcx
0x18002e78a  cmp     [rdx], rsi
0x18002e78d  jnz     short loc_18002E7A4
0x18002e78f  mov     ecx, 237h
0x18002e794  call    cs:__imp_WICCreateImagingFactory_Proxy
0x18002e79a  mov     edi, eax
0x18002e79c  test    eax, eax
0x18002e79e  js      loc_18002E837
0x18002e7a4  lea     r9, [rbp+arg_8]; void **
0x18002e7a8  mov     [rbp+arg_0], esi
0x18002e7ab  lea     rdx, [rbp+arg_0]; unsigned int *
0x18002e7af  mov     [rbp+arg_8], rsi
0x18002e7b3  mov     rcx, rbx; this
0x18002e7b6  call    ?_LoadUsingWIC@CScaledResourceFactory@@AEAAJPEAIAEBU_GUID@@PEAPEAX@Z; CScaledResourceFactory::_LoadUsingWIC(uint *,_GUID const &,void * *)
0x18002e7bb  test    eax, eax
0x18002e7bd  jns     short loc_18002E7D5
0x18002e7bf  lea     r9, [rbp+arg_8]; void **
0x18002e7c3  mov     rcx, rbx; this
0x18002e7c6  lea     rdx, [rbp+arg_0]; unsigned int *
0x18002e7ca  call    ?_LoadUsingUSER@CScaledResourceFactory@@AEAAJPEAIAEBU_GUID@@PEAPEAX@Z; CScaledResourceFactory::_LoadUsingUSER(uint *,_GUID const &,void * *)
0x18002e7cf  mov     edi, eax
0x18002e7d1  test    eax, eax
0x18002e7d3  js      short loc_18002E837
0x18002e7d5  mov     rcx, rbx; this
0x18002e7d8  mov     rdx, [rbp+arg_8]; struct IWICBitmapSource *
0x18002e7dc  cmp     [rbx+0Ch], sil
0x18002e7e0  jz      short loc_18002E80B
0x18002e7e2  movss   xmm0, dword ptr [rbx+8]
0x18002e7e7  mulss   xmm0, cs:__real@42c80000
0x18002e7ef  imul    r9d, [rbp+arg_0], 64h ; 'd'
0x18002e7f4  addss   xmm0, cs:__real@3f000000
0x18002e7fc  cvttss2si rax, xmm0
0x18002e801  lea     r8d, [rax+rax*2]
0x18002e805  shl     r8d, 5
0x18002e809  jmp     short loc_18002E813
0x18002e80b  mov     r9d, [rbp+arg_0]; int
0x18002e80f  mov     r8d, [rbx+30h]; int
0x18002e813  lea     rax, [rbp+arg_10]
0x18002e817  mov     [rsp+30h+var_10], rax; HBITMAP *
0x18002e81c  call    ?_ScaleSource@CScaledResourceFactory@@AEAAJPEAUIWICBitmapSource@@HHPEAPEAUHBITMAP__@@@Z; CScaledResourceFactory::_ScaleSource(IWICBitmapSource *,int,int,HBITMAP__ * *)
0x18002e821  mov     rcx, [rbp+arg_8]
0x18002e825  mov     edi, eax
0x18002e827  mov     rax, [rcx]
0x18002e82a  mov     rax, [rax+10h]
0x18002e82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e833  mov     rsi, [rbp+arg_10]
0x18002e837  mov     [r14], rsi
0x18002e83a  mov     eax, edi
0x18002e83c  add     rsp, 30h
0x18002e840  pop     r14
0x18002e842  pop     rdi
0x18002e843  pop     rsi
0x18002e844  pop     rbx
0x18002e845  pop     rbp
0x18002e846  retn
```
