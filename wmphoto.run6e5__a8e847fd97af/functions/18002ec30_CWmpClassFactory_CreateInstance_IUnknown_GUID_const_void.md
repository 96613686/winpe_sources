# CWmpClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18002ec30`
- end: `0x18002ed88`
- name: `?CreateInstance@CWmpClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `344`
- prototype: `__int64 __fastcall(CWmpClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002eb90`
- `0x18002ec30`
- `0x18002ed90`
- `0x180035e74`
- `0x180044010`

## pseudocode

```c
__int64 __fastcall CWmpClassFactory::CreateInstance(
        CWmpClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // rax
  CGpWmpDecoder *v7; // rax
  __int64 v8; // rax
  CGpWmpEncoder *v9; // rax
  int v10; // esi
  CGpWmpDecoder *v11; // rbx
  __int64 result; // rax
  CGpWmpDecoder *v13; // [rsp+48h] [rbp+20h]

  *a4 = 0;
  if ( a2 )
  {
    v10 = -2147221232;
    goto LABEL_16;
  }
  v6 = *(_QWORD *)&CLSID_WICWmpDecoder.Data1 - *(_QWORD *)((char *)this + 12);
  if ( *(_QWORD *)&CLSID_WICWmpDecoder.Data1 == *(_QWORD *)((char *)this + 12) )
    v6 = *(_QWORD *)CLSID_WICWmpDecoder.Data4 - *(_QWORD *)((char *)this + 20);
  if ( v6 )
  {
    v8 = *(_QWORD *)&CLSID_WICWmpEncoder.Data1 - *(_QWORD *)((char *)this + 12);
    if ( *(_QWORD *)&CLSID_WICWmpEncoder.Data1 == *(_QWORD *)((char *)this + 12) )
      v8 = *(_QWORD *)CLSID_WICWmpEncoder.Data4 - *(_QWORD *)((char *)this + 20);
    if ( v8 )
    {
      try
      {
        v11 = (CGpWmpDecoder *)operator new(0x38u);
        *((_DWORD *)v11 + 2) = 0;
        *(_QWORD *)v11 = &CWmpImageDecodeFilter::`vftable'{for `CWmpCodecBase'};
        *((_QWORD *)v11 + 3) = &CWmpImageDecodeFilter::`vftable'{for `IImageDecodeFilter'};
        *((_QWORD *)v11 + 4) = 0;
        *((_QWORD *)v11 + 5) = 0;
        *((_QWORD *)v11 + 6) = 0;
        _InterlockedIncrement(&g_refcntWMPCodec);
        v13 = v11;
      }
      catch ( std::bad_alloc )
      {
LABEL_13:
        v11 = v13;
        v10 = -2147024882;
        if ( v13 )
          goto LABEL_14;
LABEL_16:
        result = (unsigned int)v10;
      }
    }
    else
    {
      try
      {
        v9 = (CGpWmpEncoder *)operator new(0x98u);
        v11 = CGpWmpEncoder::CGpWmpEncoder(v9);
        v13 = v11;
      }
      catch ( std::bad_alloc )
      {
        goto LABEL_13;
      }
    }
  }
  else
  {
    try
    {
      v7 = (CGpWmpDecoder *)operator new(0x98u);
      v11 = CGpWmpDecoder::CGpWmpDecoder(v7);
      v13 = v11;
    }
    catch ( std::bad_alloc )
    {
      goto LABEL_13;
    }
  }
  if ( !v11 )
  {
    v10 = -2147024882;
    goto LABEL_16;
  }
  v10 = (**(__int64 (__fastcall ***)(CGpWmpDecoder *, const struct _GUID *, void **))v11)(v11, a3, a4);
  if ( v10 >= 0 )
    goto LABEL_16;
LABEL_14:
  (*(void (__fastcall **)(CGpWmpDecoder *, __int64))(*(_QWORD *)v11 + 24LL))(v11, 1);
  goto LABEL_16;
}

```

## disassembly

```asm
0x18002ec30  mov     [rsp+arg_0], rbx
0x18002ec35  mov     [rsp+arg_10], rsi
0x18002ec3a  push    r14
0x18002ec3c  sub     rsp, 20h
0x18002ec40  mov     rsi, r9
0x18002ec43  mov     r14, r8
0x18002ec46  mov     qword ptr [r9], 0
0x18002ec4d  test    rdx, rdx
0x18002ec50  jnz     loc_18002ED70
0x18002ec56  mov     [rsp+28h+arg_18], rdx
0x18002ec5b  mov     rax, qword ptr cs:CLSID_WICWmpDecoder.Data1
0x18002ec62  sub     rax, [rcx+0Ch]
0x18002ec66  jnz     short loc_18002EC73
0x18002ec68  mov     rax, qword ptr cs:CLSID_WICWmpDecoder.Data4
0x18002ec6f  sub     rax, [rcx+14h]
0x18002ec73  test    rax, rax
0x18002ec76  jnz     short loc_18002EC9C
0x18002ec78  mov     ecx, 98h; Size
0x18002ec7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ec82  mov     rcx, rax; this
0x18002ec85  call    ??0CGpWmpDecoder@@QEAA@XZ; CGpWmpDecoder::CGpWmpDecoder(void)
0x18002ec8a  mov     rbx, rax
0x18002ec8d  mov     [rsp+28h+arg_18], rax
0x18002ec92  jmp     loc_18002ED24
0x18002ec97  jmp     loc_18002ED4C
0x18002ec9c  mov     rax, qword ptr cs:CLSID_WICWmpEncoder.Data1
0x18002eca3  sub     rax, [rcx+0Ch]
0x18002eca7  jnz     short loc_18002ECB4
0x18002eca9  mov     rax, qword ptr cs:CLSID_WICWmpEncoder.Data4
0x18002ecb0  sub     rax, [rcx+14h]
0x18002ecb4  test    rax, rax
0x18002ecb7  jnz     short loc_18002ECD7
0x18002ecb9  mov     ecx, 98h; Size
0x18002ecbe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ecc3  mov     rcx, rax; this
0x18002ecc6  call    ??0CGpWmpEncoder@@QEAA@XZ; CGpWmpEncoder::CGpWmpEncoder(void)
0x18002eccb  mov     rbx, rax
0x18002ecce  mov     [rsp+28h+arg_18], rax
0x18002ecd3  jmp     short loc_18002ED24
0x18002ecd5  jmp     short loc_18002ED4C
0x18002ecd7  mov     ecx, 38h ; '8'; Size
0x18002ecdc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ece1  mov     rbx, rax
0x18002ece4  mov     dword ptr [rax+8], 0
0x18002eceb  lea     rax, ??_7CWmpImageDecodeFilter@@6BCWmpCodecBase@@@; const CWmpImageDecodeFilter::`vftable'{for `CWmpCodecBase'}
0x18002ecf2  mov     [rbx], rax
0x18002ecf5  lea     rax, ??_7CWmpImageDecodeFilter@@6BIImageDecodeFilter@@@; const CWmpImageDecodeFilter::`vftable'{for `IImageDecodeFilter'}
0x18002ecfc  mov     [rbx+18h], rax
0x18002ed00  mov     qword ptr [rbx+20h], 0
0x18002ed08  mov     qword ptr [rbx+28h], 0
0x18002ed10  mov     qword ptr [rbx+30h], 0
0x18002ed18  lock inc cs:?g_refcntWMPCodec@@3JA; long g_refcntWMPCodec
0x18002ed1f  mov     [rsp+28h+arg_18], rbx
0x18002ed24  test    rbx, rbx
0x18002ed27  jnz     short loc_18002ED30
0x18002ed29  mov     esi, 8007000Eh
0x18002ed2e  jmp     short loc_18002ED75
0x18002ed30  mov     rax, [rbx]
0x18002ed33  mov     r8, rsi
0x18002ed36  mov     rdx, r14
0x18002ed39  mov     rcx, rbx
0x18002ed3c  mov     rax, [rax]
0x18002ed3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed44  mov     esi, eax
0x18002ed46  test    eax, eax
0x18002ed48  jns     short loc_18002ED75
0x18002ed4a  jmp     short loc_18002ED5A
0x18002ed4c  mov     rbx, [rsp+28h+arg_18]
0x18002ed51  mov     esi, [rsp+28h+arg_8]
0x18002ed55  test    rbx, rbx
0x18002ed58  jz      short loc_18002ED75
0x18002ed5a  mov     rax, [rbx]
0x18002ed5d  mov     edx, 1
0x18002ed62  mov     rcx, rbx
0x18002ed65  mov     rax, [rax+18h]
0x18002ed69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed6e  jmp     short loc_18002ED75
0x18002ed70  mov     esi, 80040110h
0x18002ed75  mov     eax, esi
0x18002ed77  mov     rbx, [rsp+28h+arg_0]
0x18002ed7c  mov     rsi, [rsp+28h+arg_10]
0x18002ed81  add     rsp, 20h
0x18002ed85  pop     r14
0x18002ed87  retn
```
