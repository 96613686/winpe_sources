# CImpersonateCaller::GetCallerSID(void * *)

- ea: `0x180006d54`
- end: `0x180006df4`
- name: `?GetCallerSID@CImpersonateCaller@@SAJPEAPEAX@Z`
- size: `160`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006480`
- `0x180006f80`
- `0x1800071c0`
- `0x18000b318`

## callees

- `0x1800043a4`
- `0x180005d48`
- `0x180006d54`
- `0x180015c90`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180006d8b`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180006d8b`

## pseudocode

```c
__int64 __fastcall CImpersonateCaller::GetCallerSID(void **a1)
{
  HRESULT v2; // eax
  __int64 v3; // rcx
  int v4; // ebx
  char v6[8]; // [rsp+20h] [rbp-18h] BYREF
  void *ppInterface[2]; // [rsp+28h] [rbp-10h] BYREF

  *a1 = 0;
  v6[0] = 0;
  ppInterface[0] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ppInterface);
  v2 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, ppInterface);
  v4 = v2;
  if ( v2 == -2147417833 )
    goto LABEL_7;
  if ( v2 )
  {
    if ( v2 >= 0 )
      goto LABEL_7;
  }
  else
  {
    if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface[0] + 48LL))(ppInterface[0]) )
    {
LABEL_7:
      v4 = SHGetUserSidFallbackForImpersonation(v3, a1);
      goto LABEL_8;
    }
    v4 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface[0] + 32LL))(ppInterface[0]);
    if ( v4 >= 0 )
    {
      v6[0] = 1;
      goto LABEL_7;
    }
  }
LABEL_8:
  CImpersonateCaller::~CImpersonateCaller((CImpersonateCaller *)v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180006d54  mov     rax, rsp
0x180006d57  mov     [rax+8], rbx
0x180006d5b  push    rdi
0x180006d5c  sub     rsp, 30h
0x180006d60  mov     rdi, rcx
0x180006d63  mov     qword ptr [rcx], 0
0x180006d6a  lea     rcx, [rax-10h]
0x180006d6e  mov     byte ptr [rax-18h], 0
0x180006d72  mov     qword ptr [rax-10h], 0
0x180006d7a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180006d7f  lea     rdx, [rsp+38h+ppInterface]; ppInterface
0x180006d84  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x180006d8b  call    cs:__imp_CoGetCallContext
0x180006d91  mov     ebx, eax
0x180006d93  cmp     eax, 80010117h
0x180006d98  jz      short loc_180006DD3
0x180006d9a  test    eax, eax
0x180006d9c  jnz     short loc_180006DD1
0x180006d9e  mov     rcx, [rsp+38h+ppInterface]
0x180006da3  mov     rax, [rcx]
0x180006da6  mov     rax, [rax+30h]
0x180006daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006daf  test    eax, eax
0x180006db1  jnz     short loc_180006DD3
0x180006db3  mov     rcx, [rsp+38h+ppInterface]
0x180006db8  mov     rax, [rcx]
0x180006dbb  mov     rax, [rax+20h]
0x180006dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dc4  mov     ebx, eax
0x180006dc6  test    eax, eax
0x180006dc8  js      short loc_180006DDD
0x180006dca  mov     [rsp+38h+var_18], 1
0x180006dcf  jmp     short loc_180006DD3
0x180006dd1  js      short loc_180006DDD
0x180006dd3  mov     rdx, rdi
0x180006dd6  call    SHGetUserSidFallbackForImpersonation
0x180006ddb  mov     ebx, eax
0x180006ddd  lea     rcx, [rsp+38h+var_18]; this
0x180006de2  call    ??1CImpersonateCaller@@QEAA@XZ; CImpersonateCaller::~CImpersonateCaller(void)
0x180006de7  mov     eax, ebx
0x180006de9  mov     rbx, [rsp+38h+arg_0]
0x180006dee  add     rsp, 30h
0x180006df2  pop     rdi
0x180006df3  retn
```
