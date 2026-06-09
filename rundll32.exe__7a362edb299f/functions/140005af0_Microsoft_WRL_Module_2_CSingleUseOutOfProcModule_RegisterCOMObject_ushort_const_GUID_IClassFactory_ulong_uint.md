# Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::RegisterCOMObject(ushort const *,_GUID *,IClassFactory * *,ulong *,uint)

- ea: `0x140005af0`
- end: `0x140005b89`
- name: `?RegisterCOMObject@?$Module@$01VCSingleUseOutOfProcModule@@@WRL@Microsoft@@UEAAJPEBGPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z`
- size: `153`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005af0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140005b3e`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140005b3e`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140005b50`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140005b50`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140005b66`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140005b66`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::RegisterCOMObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6)
{
  HRESULT v6; // edi
  __int64 v7; // rbp
  HRESULT v10; // eax
  __int64 i; // rsi

  v6 = 0;
  v7 = 0;
  if ( a6 )
  {
    while ( v6 >= 0 )
    {
      v10 = CoRegisterClassObject(
              (const IID *const)(a3 + 16LL * (unsigned int)v7),
              *(LPUNKNOWN *)(a4 + 8 * v7),
              4u,
              5u,
              (LPDWORD)(a5 + 4 * v7));
      v7 = (unsigned int)(v7 + 1);
      v6 = v10;
      if ( (unsigned int)v7 >= a6 )
      {
        if ( v10 < 0 )
          break;
        goto LABEL_5;
      }
    }
  }
  else
  {
LABEL_5:
    v6 = CoResumeClassObjects();
    if ( v6 >= 0 )
      return (unsigned int)v6;
  }
  for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
  {
    CoRevokeClassObject(*(_DWORD *)(a5 + 4 * i));
    *(_DWORD *)(a5 + 4 * i) = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140005af0  push    rbx
0x140005af2  push    rbp
0x140005af3  push    rsi
0x140005af4  push    rdi
0x140005af5  push    r14
0x140005af7  push    r15
0x140005af9  sub     rsp, 38h
0x140005afd  mov     ebx, [rsp+68h+arg_28]
0x140005b04  xor     edi, edi
0x140005b06  mov     r14, [rsp+68h+arg_20]
0x140005b0e  xor     ebp, ebp
0x140005b10  mov     rsi, r9
0x140005b13  mov     r15, r8
0x140005b16  test    ebx, ebx
0x140005b18  jz      short loc_140005B50
0x140005b1a  test    edi, edi
0x140005b1c  js      short loc_140005B5C
0x140005b1e  mov     rdx, [rsi+rbp*8]; pUnk
0x140005b22  lea     rax, [r14+rbp*4]
0x140005b26  mov     r9d, 5; flags
0x140005b2c  mov     ecx, ebp
0x140005b2e  shl     rcx, 4
0x140005b32  add     rcx, r15; rclsid
0x140005b35  mov     [rsp+68h+lpdwRegister], rax; lpdwRegister
0x140005b3a  lea     r8d, [r9-1]; dwClsContext
0x140005b3e  call    cs:__imp_CoRegisterClassObject
0x140005b44  inc     ebp
0x140005b46  mov     edi, eax
0x140005b48  cmp     ebp, ebx
0x140005b4a  jb      short loc_140005B1A
0x140005b4c  test    eax, eax
0x140005b4e  js      short loc_140005B5C
0x140005b50  call    cs:__imp_CoResumeClassObjects
0x140005b56  mov     edi, eax
0x140005b58  test    eax, eax
0x140005b5a  jns     short loc_140005B7A
0x140005b5c  xor     esi, esi
0x140005b5e  test    ebp, ebp
0x140005b60  jz      short loc_140005B7A
0x140005b62  mov     ecx, [r14+rsi*4]; dwRegister
0x140005b66  call    cs:__imp_CoRevokeClassObject
0x140005b6c  mov     dword ptr [r14+rsi*4], 0
0x140005b74  inc     esi
0x140005b76  cmp     esi, ebp
0x140005b78  jb      short loc_140005B62
0x140005b7a  mov     eax, edi
0x140005b7c  add     rsp, 38h
0x140005b80  pop     r15
0x140005b82  pop     r14
0x140005b84  pop     rdi
0x140005b85  pop     rsi
0x140005b86  pop     rbp
0x140005b87  pop     rbx
0x140005b88  retn
```
