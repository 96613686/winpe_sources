# RegistryJson::GetValueAlloc(ushort * *)

- ea: `0x180050850`
- end: `0x1800509f9`
- name: `?GetValueAlloc@RegistryJson@@UEAAJPEAPEAG@Z`
- size: `425`
- prototype: `__int64 __fastcall(RegistryJson *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000e5ac`
- `0x180010130`
- `0x18004fc9c`
- `0x18005024c`
- `0x180050318`
- `0x180050850`
- `0x1800515a4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800508dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800508dc`

## string_xrefs

- `0x1800508b5`: `onecore\base\flighting\common\regvalet\registryjson.cpp`
- `0x18005098c`: `onecore\base\flighting\common\regvalet\registryjson.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegistryJson::GetValueAlloc(RegistryJson *this, unsigned __int16 **a2)
{
  HSTRING v4; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  int v6; // eax
  int ValueRecursive; // ebx
  struct IKvpEncoder *v9; // rdi
  const unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 (__fastcall *v13)(struct IKvpEncoder *, unsigned __int16 **); // rbx
  int v14; // eax
  unsigned __int16 *v15; // rax
  __int64 v16; // rcx
  int v17; // [rsp+20h] [rbp-30h]
  int v18; // [rsp+20h] [rbp-30h]
  unsigned __int16 *v19; // [rsp+30h] [rbp-20h] BYREF
  __int64 v20; // [rsp+38h] [rbp-18h]
  __int64 v21; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  struct IKvpEncoder *v23; // [rsp+70h] [rbp+20h] BYREF
  struct IKvpEncoder *v24; // [rsp+80h] [rbp+30h]

  v24 = 0;
  v23 = 0;
  v4 = (HSTRING)*((_QWORD *)this + 5);
  if ( v4 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v4, 0);
    v6 = KvpEncoder::CreateInstance(&v23, StringRawBuffer);
  }
  else
  {
    v6 = KvpEncoder::CreateInstance(&v23, 4);
  }
  ValueRecursive = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecore\\base\\flighting\\common\\regvalet\\registryjson.cpp",
      (const char *)(unsigned int)v6,
      v17);
    return (unsigned int)ValueRecursive;
  }
  v9 = v23;
  v24 = v23;
  v10 = WindowsGetStringRawBuffer(*((HSTRING *)this + 3), 0);
  ValueRecursive = RegistryJson::_GetValueRecursive(this, v9, *((HKEY *)this + 2), v10, 0);
  if ( ValueRecursive < 0 )
  {
LABEL_8:
    if ( v9 )
      wistd::default_delete<IKvpEncoder>::operator()(v11, v9);
    return (unsigned int)ValueRecursive;
  }
  if ( (*(unsigned __int8 (__fastcall **)(struct IKvpEncoder *))(*(_QWORD *)v9 + 24LL))(v9) )
  {
    if ( v9 )
      wistd::default_delete<IKvpEncoder>::operator()(v12, v9);
    return 2147942402LL;
  }
  else
  {
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v13 = *(__int64 (__fastcall **)(struct IKvpEncoder *, unsigned __int16 **))(*(_QWORD *)v9 + 32LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v19);
    v20 = -1;
    v21 = -1;
    v14 = v13(v9, &v19);
    ValueRecursive = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecore\\base\\flighting\\common\\regvalet\\registryjson.cpp",
        (const char *)(unsigned int)v14,
        v18);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v19);
      goto LABEL_8;
    }
    v15 = v19;
    v19 = 0;
    v21 = 0;
    v20 = 0;
    *a2 = v15;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v19);
    if ( v9 )
      wistd::default_delete<IKvpEncoder>::operator()(v16, v9);
    return 0;
  }
}

```

## disassembly

```asm
0x180050850  mov     [rsp-18h+arg_8], rbx
0x180050855  mov     [rsp-18h+arg_18], rsi
0x18005085a  push    rbp
0x18005085b  push    rdi
0x18005085c  push    r14
0x18005085e  mov     rbp, rsp
0x180050861  sub     rsp, 50h
0x180050865  mov     r14, rdx
0x180050868  mov     rsi, rcx
0x18005086b  mov     [rbp+arg_10], 0
0x180050873  mov     [rbp+arg_0], 0
0x18005087b  mov     rcx, [rcx+28h]; string
0x18005087f  test    rcx, rcx
0x180050882  jz      short loc_18005089A
0x180050884  xor     edx, edx; length
0x180050886  call    cs:__imp_WindowsGetStringRawBuffer
0x18005088c  mov     rdx, rax; unsigned __int16 *
0x18005088f  lea     rcx, [rbp+arg_0]; struct IKvpEncoder **
0x180050893  call    ?CreateInstance@KvpEncoder@@SAJPEAPEAUIKvpEncoder@@PEBG@Z; KvpEncoder::CreateInstance(IKvpEncoder * *,ushort const *)
0x180050898  jmp     short loc_1800508A8
0x18005089a  mov     edx, 4
0x18005089f  lea     rcx, [rbp+arg_0]
0x1800508a3  call    ?CreateInstance@KvpEncoder@@SAJPEAPEAUIKvpEncoder@@W4KvpEncoderMethod@@@Z; KvpEncoder::CreateInstance(IKvpEncoder * *,KvpEncoderMethod)
0x1800508a8  mov     ebx, eax
0x1800508aa  test    eax, eax
0x1800508ac  jns     short loc_1800508CE
0x1800508ae  mov     rcx, [rbp+18h]; this
0x1800508b2  mov     r9d, eax; char *
0x1800508b5  lea     r8, aOnecoreBaseFli_4; "onecore\\base\\flighting\\common\\regva"...
0x1800508bc  mov     edx, 0D7h; void *
0x1800508c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800508c6  nop
0x1800508c7  mov     eax, ebx
0x1800508c9  jmp     loc_1800509E4
0x1800508ce  mov     rdi, [rbp+arg_0]
0x1800508d2  mov     [rbp+arg_10], rdi
0x1800508d6  xor     edx, edx; length
0x1800508d8  mov     rcx, [rsi+18h]; string
0x1800508dc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800508e2  mov     qword ptr [rsp+50h+var_30], 0; int
0x1800508eb  mov     r9, rax; unsigned __int16 *
0x1800508ee  mov     r8, [rsi+10h]; HKEY
0x1800508f2  mov     rdx, rdi; struct IKvpEncoder *
0x1800508f5  mov     rcx, rsi; this
0x1800508f8  call    ?_GetValueRecursive@RegistryJson@@AEAAJPEAUIKvpEncoder@@PEAUHKEY__@@PEBG2@Z; RegistryJson::_GetValueRecursive(IKvpEncoder *,HKEY__ *,ushort const *,ushort const *)
0x1800508fd  mov     ebx, eax
0x1800508ff  test    eax, eax
0x180050901  jns     short loc_180050912
0x180050903  test    rdi, rdi
0x180050906  jz      short loc_1800508C7
0x180050908  mov     rdx, rdi
0x18005090b  call    ??R?$default_delete@UIKvpEncoder@@@wistd@@QEBAXPEAUIKvpEncoder@@@Z; wistd::default_delete<IKvpEncoder>::operator()(IKvpEncoder *)
0x180050910  jmp     short loc_1800508C7
0x180050912  mov     rax, [rdi]
0x180050915  mov     rcx, rdi
0x180050918  mov     rax, [rax+18h]
0x18005091c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050921  test    al, al
0x180050923  jz      short loc_18005093C
0x180050925  test    rdi, rdi
0x180050928  jz      short loc_180050932
0x18005092a  mov     rdx, rdi
0x18005092d  call    ??R?$default_delete@UIKvpEncoder@@@wistd@@QEBAXPEAUIKvpEncoder@@@Z; wistd::default_delete<IKvpEncoder>::operator()(IKvpEncoder *)
0x180050932  mov     eax, 80070002h
0x180050937  jmp     loc_1800509E4
0x18005093c  mov     [rbp+var_20], 0
0x180050944  mov     [rbp+var_18], 0
0x18005094c  mov     [rbp+var_10], 0
0x180050954  mov     rax, [rdi]
0x180050957  mov     rbx, [rax+20h]
0x18005095b  lea     rcx, [rbp+var_20]
0x18005095f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180050964  or      rax, 0FFFFFFFFFFFFFFFFh
0x180050968  mov     [rbp+var_18], rax
0x18005096c  mov     [rbp+var_10], rax
0x180050970  lea     rdx, [rbp+var_20]
0x180050974  mov     rcx, rdi
0x180050977  mov     rax, rbx
0x18005097a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005097f  mov     ebx, eax
0x180050981  test    eax, eax
0x180050983  jns     short loc_1800509AC
0x180050985  mov     rcx, [rbp+18h]; this
0x180050989  mov     r9d, eax; char *
0x18005098c  lea     r8, aOnecoreBaseFli_4; "onecore\\base\\flighting\\common\\regva"...
0x180050993  mov     edx, 0E5h; void *
0x180050998  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005099d  nop
0x18005099e  lea     rcx, [rbp+var_20]
0x1800509a2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800509a7  jmp     loc_180050903
0x1800509ac  mov     rax, [rbp+var_20]
0x1800509b0  mov     [rbp+var_20], 0
0x1800509b8  mov     [rbp+var_10], 0
0x1800509c0  mov     [rbp+var_18], 0
0x1800509c8  mov     [r14], rax
0x1800509cb  lea     rcx, [rbp+var_20]
0x1800509cf  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800509d4  nop
0x1800509d5  test    rdi, rdi
0x1800509d8  jz      short loc_1800509E2
0x1800509da  mov     rdx, rdi
0x1800509dd  call    ??R?$default_delete@UIKvpEncoder@@@wistd@@QEBAXPEAUIKvpEncoder@@@Z; wistd::default_delete<IKvpEncoder>::operator()(IKvpEncoder *)
0x1800509e2  xor     eax, eax
0x1800509e4  lea     r11, [rsp+50h+var_s0]
0x1800509e9  mov     rbx, [r11+28h]
0x1800509ed  mov     rsi, [r11+38h]
0x1800509f1  mov     rsp, r11
0x1800509f4  pop     r14
0x1800509f6  pop     rdi
0x1800509f7  pop     rbp
0x1800509f8  retn
```
