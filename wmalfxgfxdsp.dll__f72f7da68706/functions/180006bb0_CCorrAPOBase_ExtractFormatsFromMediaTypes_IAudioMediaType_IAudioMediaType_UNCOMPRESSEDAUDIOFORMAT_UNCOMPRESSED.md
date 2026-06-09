# CCorrAPOBase::ExtractFormatsFromMediaTypes(IAudioMediaType *,IAudioMediaType *,_UNCOMPRESSEDAUDIOFORMAT *,_UNCOMPRESSEDAUDIOFORMAT *)

- ea: `0x180006bb0`
- end: `0x180006c61`
- name: `?ExtractFormatsFromMediaTypes@CCorrAPOBase@@IEAAJPEAUIAudioMediaType@@0PEAU_UNCOMPRESSEDAUDIOFORMAT@@1@Z`
- size: `177`
- prototype: `__int64 __fastcall(CCorrAPOBase *__hidden this, struct IAudioMediaType *, struct IAudioMediaType *, struct _UNCOMPRESSEDAUDIOFORMAT *, struct _UNCOMPRESSEDAUDIOFORMAT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000662c`
- `0x1800066e0`
- `0x180006970`

## callees

- `0x180006bb0`
- `0x180006c68`
- `0x180086010`

## pseudocode

```c
__int64 __fastcall CCorrAPOBase::ExtractFormatsFromMediaTypes(
        CCorrAPOBase *this,
        struct IAudioMediaType *a2,
        struct IAudioMediaType *a3,
        struct _UNCOMPRESSEDAUDIOFORMAT *a4,
        struct _UNCOMPRESSEDAUDIOFORMAT *a5)
{
  __int64 result; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // r9

  if ( !a2 || !a3 )
    return 2147500035LL;
  result = ((__int64 (__fastcall *)(struct IAudioMediaType *, struct _UNCOMPRESSEDAUDIOFORMAT *))a2->lpVtbl->GetUncompressedAudioFormat)(
             a2,
             a4);
  if ( (int)result >= 0 )
  {
    result = ((__int64 (__fastcall *)(struct IAudioMediaType *, struct _UNCOMPRESSEDAUDIOFORMAT *))a3->lpVtbl->GetUncompressedAudioFormat)(
               a3,
               a5);
    if ( (int)result >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct IAudioMediaType *))a2->lpVtbl->GetAudioFormat)(a2);
      v10 = ((__int64 (__fastcall *)(struct IAudioMediaType *))a3->lpVtbl->GetAudioFormat)(a3);
      if ( v9 && v10 )
      {
        a4->dwChannelMask = ChannelMask(v9, v10, v11, v10);
        a5->dwChannelMask = ChannelMask(v13, v9, v12, v13);
        return 0;
      }
      return 2147500035LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006bb0  push    rbx
0x180006bb2  push    rbp
0x180006bb3  push    rsi
0x180006bb4  push    rdi
0x180006bb5  sub     rsp, 28h
0x180006bb9  mov     rsi, r9
0x180006bbc  mov     rbx, r8
0x180006bbf  mov     rdi, rdx
0x180006bc2  test    rdx, rdx
0x180006bc5  jz      loc_180006C5A
0x180006bcb  test    rbx, rbx
0x180006bce  jz      loc_180006C5A
0x180006bd4  mov     rax, [rdx]
0x180006bd7  mov     rcx, rdi
0x180006bda  mov     rdx, r9
0x180006bdd  mov     rax, [rax+30h]
0x180006be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006be6  test    eax, eax
0x180006be8  js      short loc_180006C51
0x180006bea  mov     rax, [rbx]
0x180006bed  mov     rcx, rbx
0x180006bf0  mov     rbp, [rsp+48h+arg_20]
0x180006bf5  mov     rdx, rbp
0x180006bf8  mov     rax, [rax+30h]
0x180006bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c01  test    eax, eax
0x180006c03  js      short loc_180006C51
0x180006c05  mov     rax, [rdi]
0x180006c08  mov     rcx, rdi
0x180006c0b  mov     rax, [rax+28h]
0x180006c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c14  mov     rcx, [rbx]
0x180006c17  mov     rdi, rax
0x180006c1a  mov     rax, [rcx+28h]
0x180006c1e  mov     rcx, rbx
0x180006c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c26  mov     r9, rax
0x180006c29  test    rdi, rdi
0x180006c2c  jz      short loc_180006C5A
0x180006c2e  test    rax, rax
0x180006c31  jz      short loc_180006C5A
0x180006c33  mov     rdx, rax
0x180006c36  mov     rcx, rdi
0x180006c39  call    ChannelMask
0x180006c3e  mov     rcx, r9
0x180006c41  mov     [rsi+20h], eax
0x180006c44  mov     rdx, rdi
0x180006c47  call    ChannelMask
0x180006c4c  mov     [rbp+20h], eax
0x180006c4f  xor     eax, eax
0x180006c51  add     rsp, 28h
0x180006c55  pop     rdi
0x180006c56  pop     rsi
0x180006c57  pop     rbp
0x180006c58  pop     rbx
0x180006c59  retn
0x180006c5a  mov     eax, 80004003h
0x180006c5f  jmp     short loc_180006C51
```
