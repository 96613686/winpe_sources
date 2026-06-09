# CWmpClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18002efc0`
- end: `0x18002f119`
- name: `?CreateInstance@CWmpClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `345`
- prototype: `__int64 __fastcall(CWmpClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002ef14`
- `0x18002efc0`
- `0x18002f120`
- `0x180036444`
- `0x180045010`

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
0x18002efc0  mov     [rsp+arg_0], rbx
0x18002efc5  mov     [rsp+arg_10], rsi
0x18002efca  push    r14
0x18002efcc  sub     rsp, 20h
0x18002efd0  mov     rsi, r9
0x18002efd3  mov     r14, r8
0x18002efd6  mov     qword ptr [r9], 0
0x18002efdd  test    rdx, rdx
0x18002efe0  jnz     loc_18002F100
0x18002efe6  mov     [rsp+28h+arg_18], rdx
0x18002efeb  mov     rax, qword ptr cs:CLSID_WICWmpDecoder.Data1
0x18002eff2  sub     rax, [rcx+0Ch]
0x18002eff6  jnz     short loc_18002F003
0x18002eff8  mov     rax, qword ptr cs:CLSID_WICWmpDecoder.Data4
0x18002efff  sub     rax, [rcx+14h]
0x18002f003  test    rax, rax
0x18002f006  jnz     short loc_18002F02C
0x18002f008  mov     ecx, 98h; Size
0x18002f00d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f012  mov     rcx, rax; this
0x18002f015  call    ??0CGpWmpDecoder@@QEAA@XZ; CGpWmpDecoder::CGpWmpDecoder(void)
0x18002f01a  mov     rbx, rax
0x18002f01d  mov     [rsp+28h+arg_18], rax
0x18002f022  jmp     loc_18002F0B4
0x18002f027  jmp     loc_18002F0DC
0x18002f02c  mov     rax, qword ptr cs:CLSID_WICWmpEncoder.Data1
0x18002f033  sub     rax, [rcx+0Ch]
0x18002f037  jnz     short loc_18002F044
0x18002f039  mov     rax, qword ptr cs:CLSID_WICWmpEncoder.Data4
0x18002f040  sub     rax, [rcx+14h]
0x18002f044  test    rax, rax
0x18002f047  jnz     short loc_18002F067
0x18002f049  mov     ecx, 98h; Size
0x18002f04e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f053  mov     rcx, rax; this
0x18002f056  call    ??0CGpWmpEncoder@@QEAA@XZ; CGpWmpEncoder::CGpWmpEncoder(void)
0x18002f05b  mov     rbx, rax
0x18002f05e  mov     [rsp+28h+arg_18], rax
0x18002f063  jmp     short loc_18002F0B4
0x18002f065  jmp     short loc_18002F0DC
0x18002f067  mov     ecx, 38h ; '8'; Size
0x18002f06c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f071  mov     rbx, rax
0x18002f074  mov     dword ptr [rax+8], 0
0x18002f07b  lea     rax, ??_7CWmpImageDecodeFilter@@6BCWmpCodecBase@@@; const CWmpImageDecodeFilter::`vftable'{for `CWmpCodecBase'}
0x18002f082  mov     [rbx], rax
0x18002f085  lea     rax, ??_7CWmpImageDecodeFilter@@6BIImageDecodeFilter@@@; const CWmpImageDecodeFilter::`vftable'{for `IImageDecodeFilter'}
0x18002f08c  mov     [rbx+18h], rax
0x18002f090  mov     qword ptr [rbx+20h], 0
0x18002f098  mov     qword ptr [rbx+28h], 0
0x18002f0a0  mov     qword ptr [rbx+30h], 0
0x18002f0a8  lock inc cs:?g_refcntWMPCodec@@3JA; long g_refcntWMPCodec
0x18002f0af  mov     [rsp+28h+arg_18], rbx
0x18002f0b4  test    rbx, rbx
0x18002f0b7  jnz     short loc_18002F0C0
0x18002f0b9  mov     esi, 8007000Eh
0x18002f0be  jmp     short loc_18002F105
0x18002f0c0  mov     rax, [rbx]
0x18002f0c3  mov     r8, rsi
0x18002f0c6  mov     rdx, r14
0x18002f0c9  mov     rcx, rbx
0x18002f0cc  mov     rax, [rax]
0x18002f0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0d4  mov     esi, eax
0x18002f0d6  test    eax, eax
0x18002f0d8  jns     short loc_18002F105
0x18002f0da  jmp     short loc_18002F0EA
0x18002f0dc  mov     rbx, [rsp+28h+arg_18]
0x18002f0e1  mov     esi, [rsp+28h+arg_8]
0x18002f0e5  test    rbx, rbx
0x18002f0e8  jz      short loc_18002F105
0x18002f0ea  mov     rax, [rbx]
0x18002f0ed  mov     edx, 1
0x18002f0f2  mov     rcx, rbx
0x18002f0f5  mov     rax, [rax+18h]
0x18002f0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0fe  jmp     short loc_18002F105
0x18002f100  mov     esi, 80040110h
0x18002f105  mov     eax, esi
0x18002f107  mov     rbx, [rsp+28h+arg_0]
0x18002f10c  mov     rsi, [rsp+28h+arg_10]
0x18002f111  add     rsp, 20h
0x18002f115  pop     r14
0x18002f117  retn
```
