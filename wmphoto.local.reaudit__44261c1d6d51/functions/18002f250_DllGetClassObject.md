# DllGetClassObject

- ea: `0x18002f250`
- end: `0x18002f3a2`
- name: `DllGetClassObject`
- size: `338`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002f250`
- `0x18002f3a8`
- `0x1800324a0`
- `0x1800355a0`
- `0x180036444`
- `0x18003833c`

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
0x18002f250  mov     [rsp+arg_0], rbx
0x18002f255  push    rsi
0x18002f256  push    rdi
0x18002f257  push    r14
0x18002f259  sub     rsp, 30h
0x18002f25d  mov     r14, r8
0x18002f260  mov     rsi, rdx
0x18002f263  mov     rdi, rcx
0x18002f266  mov     qword ptr [r8], 0
0x18002f26d  call    ?InitWICFactory@@YAJXZ; InitWICFactory(void)
0x18002f272  mov     ebx, eax
0x18002f274  test    eax, eax
0x18002f276  js      short loc_18002F2F6
0x18002f278  mov     rax, qword ptr cs:CLSID_WICWmpDecoder.Data1
0x18002f27f  sub     rax, [rdi]
0x18002f282  jnz     short loc_18002F28F
0x18002f284  mov     rax, qword ptr cs:CLSID_WICWmpDecoder.Data4
0x18002f28b  sub     rax, [rdi+8]
0x18002f28f  test    rax, rax
0x18002f292  jnz     short loc_18002F307
0x18002f294  mov     [rsp+48h+arg_18], 0
0x18002f29d  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x18002f2a4  sub     rax, [rsi]
0x18002f2a7  jnz     short loc_18002F2B4
0x18002f2a9  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x18002f2b0  sub     rax, [rsi+8]
0x18002f2b4  test    rax, rax
0x18002f2b7  jnz     loc_18002F34E
0x18002f2bd  mov     ecx, 20h ; ' '; Size
0x18002f2c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f2c7  movups  xmm0, xmmword ptr [rdi]
0x18002f2ca  movdqu  xmmword ptr [rsp+48h+var_28.Data1], xmm0
0x18002f2d0  lea     rdx, [rsp+48h+var_28]; struct _GUID
0x18002f2d5  mov     rcx, rax; this
0x18002f2d8  call    ??0CWmpClassFactory@@QEAA@U_GUID@@@Z; CWmpClassFactory::CWmpClassFactory(_GUID)
0x18002f2dd  mov     [rsp+48h+arg_18], rax
0x18002f2e2  test    rax, rax
0x18002f2e5  jnz     loc_18002F375
0x18002f2eb  mov     ebx, 8007000Eh
0x18002f2f0  jmp     short loc_18002F2F6
0x18002f2f2  mov     ebx, [rsp+48h+arg_10]
0x18002f2f6  mov     eax, ebx
0x18002f2f8  mov     rbx, [rsp+48h+arg_0]
0x18002f2fd  add     rsp, 30h
0x18002f301  pop     r14
0x18002f303  pop     rdi
0x18002f304  pop     rsi
0x18002f305  retn
0x18002f307  mov     rax, qword ptr cs:CLSID_WICWmpEncoder.Data1
0x18002f30e  sub     rax, [rdi]
0x18002f311  jnz     short loc_18002F31E
0x18002f313  mov     rax, qword ptr cs:CLSID_WICWmpEncoder.Data4
0x18002f31a  sub     rax, [rdi+8]
0x18002f31e  test    rax, rax
0x18002f321  jz      loc_18002F294
0x18002f327  mov     rax, qword ptr cs:CLSID_WmpImageDecodeFilter.Data1
0x18002f32e  sub     rax, [rdi]
0x18002f331  jnz     short loc_18002F33E
0x18002f333  mov     rax, qword ptr cs:CLSID_WmpImageDecodeFilter.Data4
0x18002f33a  sub     rax, [rdi+8]
0x18002f33e  test    rax, rax
0x18002f341  jz      loc_18002F294
0x18002f347  mov     ebx, 80040111h
0x18002f34c  jmp     short loc_18002F2F6
0x18002f34e  mov     rax, qword ptr cs:IID_IClassFactory.Data1
0x18002f355  sub     rax, [rsi]
0x18002f358  jnz     short loc_18002F365
0x18002f35a  mov     rax, qword ptr cs:IID_IClassFactory.Data4
0x18002f361  sub     rax, [rsi+8]
0x18002f365  test    rax, rax
0x18002f368  jz      loc_18002F2BD
0x18002f36e  mov     ebx, 80004002h
0x18002f373  jmp     short loc_18002F2F6
0x18002f375  xor     ebx, ebx
0x18002f377  mov     r8, r14; void **
0x18002f37a  mov     rdx, rsi; struct _GUID *
0x18002f37d  mov     rcx, rax; this
0x18002f380  call    ?QueryInterface@CWmpClassFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWmpClassFactory::QueryInterface(_GUID const &,void * *)
0x18002f385  jmp     loc_18002F2F6
0x18002f38a  mov     rcx, [rsp+48h+arg_18]; this
0x18002f38f  test    rcx, rcx
0x18002f392  jz      loc_18002F2F2
0x18002f398  call    ?Release@CWmpClassFactory@@UEAAKXZ; CWmpClassFactory::Release(void)
0x18002f39d  jmp     loc_18002F2F2
```
