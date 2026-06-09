# DllGetClassObject

- ea: `0x18002eec0`
- end: `0x18002f011`
- name: `DllGetClassObject`
- size: `337`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002eec0`
- `0x18002f018`
- `0x180032100`
- `0x180034fd0`
- `0x180035e74`
- `0x180037d0c`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT inited; // ebx
  __int64 v7; // rax
  __int64 v8; // rax
  CWmpClassFactory *v9; // rax
  CWmpClassFactory *v10; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  struct _GUID v15; // [rsp+20h] [rbp-28h] BYREF

  *ppv = 0;
  inited = InitWICFactory();
  if ( inited >= 0 )
  {
    v7 = *(_QWORD *)&CLSID_WICWmpDecoder.Data1 - *(_QWORD *)&rclsid->Data1;
    if ( *(_QWORD *)&CLSID_WICWmpDecoder.Data1 == *(_QWORD *)&rclsid->Data1 )
      v7 = *(_QWORD *)CLSID_WICWmpDecoder.Data4 - *(_QWORD *)rclsid->Data4;
    if ( !v7 )
      goto LABEL_5;
    v12 = *(_QWORD *)&CLSID_WICWmpEncoder.Data1 - *(_QWORD *)&rclsid->Data1;
    if ( *(_QWORD *)&CLSID_WICWmpEncoder.Data1 == *(_QWORD *)&rclsid->Data1 )
      v12 = *(_QWORD *)CLSID_WICWmpEncoder.Data4 - *(_QWORD *)rclsid->Data4;
    if ( !v12 )
      goto LABEL_5;
    v13 = *(_QWORD *)&CLSID_WmpImageDecodeFilter.Data1 - *(_QWORD *)&rclsid->Data1;
    if ( *(_QWORD *)&CLSID_WmpImageDecodeFilter.Data1 == *(_QWORD *)&rclsid->Data1 )
      v13 = *(_QWORD *)CLSID_WmpImageDecodeFilter.Data4 - *(_QWORD *)rclsid->Data4;
    if ( v13 )
    {
      return -2147221231;
    }
    else
    {
LABEL_5:
      v8 = *(_QWORD *)&IID_IUnknown.Data1 - *(_QWORD *)&riid->Data1;
      if ( *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&riid->Data1 )
        v8 = *(_QWORD *)IID_IUnknown.Data4 - *(_QWORD *)riid->Data4;
      if ( !v8 )
        goto LABEL_8;
      v14 = *(_QWORD *)&IID_IClassFactory.Data1 - *(_QWORD *)&riid->Data1;
      if ( *(_QWORD *)&IID_IClassFactory.Data1 == *(_QWORD *)&riid->Data1 )
        v14 = *(_QWORD *)IID_IClassFactory.Data4 - *(_QWORD *)riid->Data4;
      if ( v14 )
      {
        return -2147467262;
      }
      else
      {
LABEL_8:
        v9 = (CWmpClassFactory *)operator new(0x20u);
        v15 = *rclsid;
        v10 = CWmpClassFactory::CWmpClassFactory(v9, &v15);
        if ( v10 )
        {
          inited = 0;
          CWmpClassFactory::QueryInterface(v10, riid, ppv);
        }
        else
        {
          return -2147024882;
        }
      }
    }
  }
  return inited;
}

```

## disassembly

```asm
0x18002eec0  mov     [rsp+arg_0], rbx
0x18002eec5  push    rsi
0x18002eec6  push    rdi
0x18002eec7  push    r14
0x18002eec9  sub     rsp, 30h
0x18002eecd  mov     r14, r8
0x18002eed0  mov     rsi, rdx
0x18002eed3  mov     rdi, rcx
0x18002eed6  mov     qword ptr [r8], 0
0x18002eedd  call    ?InitWICFactory@@YAJXZ; InitWICFactory(void)
0x18002eee2  mov     ebx, eax
0x18002eee4  test    eax, eax
0x18002eee6  js      short loc_18002EF66
0x18002eee8  mov     rax, qword ptr cs:CLSID_WICWmpDecoder.Data1
0x18002eeef  sub     rax, [rdi]
0x18002eef2  jnz     short loc_18002EEFF
0x18002eef4  mov     rax, qword ptr cs:CLSID_WICWmpDecoder.Data4
0x18002eefb  sub     rax, [rdi+8]
0x18002eeff  test    rax, rax
0x18002ef02  jnz     short loc_18002EF76
0x18002ef04  mov     [rsp+48h+arg_18], 0
0x18002ef0d  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x18002ef14  sub     rax, [rsi]
0x18002ef17  jnz     short loc_18002EF24
0x18002ef19  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x18002ef20  sub     rax, [rsi+8]
0x18002ef24  test    rax, rax
0x18002ef27  jnz     loc_18002EFBD
0x18002ef2d  mov     ecx, 20h ; ' '; Size
0x18002ef32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ef37  movups  xmm0, xmmword ptr [rdi]
0x18002ef3a  movdqu  xmmword ptr [rsp+48h+var_28.Data1], xmm0
0x18002ef40  lea     rdx, [rsp+48h+var_28]; struct _GUID
0x18002ef45  mov     rcx, rax; this
0x18002ef48  call    ??0CWmpClassFactory@@QEAA@U_GUID@@@Z; CWmpClassFactory::CWmpClassFactory(_GUID)
0x18002ef4d  mov     [rsp+48h+arg_18], rax
0x18002ef52  test    rax, rax
0x18002ef55  jnz     loc_18002EFE4
0x18002ef5b  mov     ebx, 8007000Eh
0x18002ef60  jmp     short loc_18002EF66
0x18002ef62  mov     ebx, [rsp+48h+arg_10]
0x18002ef66  mov     eax, ebx
0x18002ef68  mov     rbx, [rsp+48h+arg_0]
0x18002ef6d  add     rsp, 30h
0x18002ef71  pop     r14
0x18002ef73  pop     rdi
0x18002ef74  pop     rsi
0x18002ef75  retn
0x18002ef76  mov     rax, qword ptr cs:CLSID_WICWmpEncoder.Data1
0x18002ef7d  sub     rax, [rdi]
0x18002ef80  jnz     short loc_18002EF8D
0x18002ef82  mov     rax, qword ptr cs:CLSID_WICWmpEncoder.Data4
0x18002ef89  sub     rax, [rdi+8]
0x18002ef8d  test    rax, rax
0x18002ef90  jz      loc_18002EF04
0x18002ef96  mov     rax, qword ptr cs:CLSID_WmpImageDecodeFilter.Data1
0x18002ef9d  sub     rax, [rdi]
0x18002efa0  jnz     short loc_18002EFAD
0x18002efa2  mov     rax, qword ptr cs:CLSID_WmpImageDecodeFilter.Data4
0x18002efa9  sub     rax, [rdi+8]
0x18002efad  test    rax, rax
0x18002efb0  jz      loc_18002EF04
0x18002efb6  mov     ebx, 80040111h
0x18002efbb  jmp     short loc_18002EF66
0x18002efbd  mov     rax, qword ptr cs:IID_IClassFactory.Data1
0x18002efc4  sub     rax, [rsi]
0x18002efc7  jnz     short loc_18002EFD4
0x18002efc9  mov     rax, qword ptr cs:IID_IClassFactory.Data4
0x18002efd0  sub     rax, [rsi+8]
0x18002efd4  test    rax, rax
0x18002efd7  jz      loc_18002EF2D
0x18002efdd  mov     ebx, 80004002h
0x18002efe2  jmp     short loc_18002EF66
0x18002efe4  xor     ebx, ebx
0x18002efe6  mov     r8, r14; void **
0x18002efe9  mov     rdx, rsi; struct _GUID *
0x18002efec  mov     rcx, rax; this
0x18002efef  call    ?QueryInterface@CWmpClassFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWmpClassFactory::QueryInterface(_GUID const &,void * *)
0x18002eff4  jmp     loc_18002EF66
0x18002eff9  mov     rcx, [rsp+48h+arg_18]; this
0x18002effe  test    rcx, rcx
0x18002f001  jz      loc_18002EF62
0x18002f007  call    ?Release@CWmpClassFactory@@UEAAKXZ; CWmpClassFactory::Release(void)
0x18002f00c  jmp     loc_18002EF62
```
