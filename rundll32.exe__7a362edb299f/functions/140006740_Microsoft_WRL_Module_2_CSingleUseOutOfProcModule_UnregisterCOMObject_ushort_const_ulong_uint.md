# Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x140006740`
- end: `0x140006783`
- name: `?UnregisterCOMObject@?$Module@$01VCSingleUseOutOfProcModule@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `67`
- prototype: `HRESULT __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140006763`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140006763`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::UnregisterCOMObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  HRESULT result; // eax
  __int64 i; // rbx
  DWORD v8; // ecx

  result = 0;
  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
  {
    if ( result < 0 )
      break;
    v8 = *(_DWORD *)(a3 + 4 * i);
    if ( v8 )
    {
      result = CoRevokeClassObject(v8);
      if ( result >= 0 )
        *(_DWORD *)(a3 + 4 * i) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140006740  push    rbx
0x140006742  push    rbp
0x140006743  push    rsi
0x140006744  push    rdi
0x140006745  sub     rsp, 28h
0x140006749  xor     eax, eax
0x14000674b  xor     ebx, ebx
0x14000674d  mov     ebp, r9d
0x140006750  mov     rsi, r8
0x140006753  test    r9d, r9d
0x140006756  jz      short loc_14000677A
0x140006758  test    eax, eax
0x14000675a  js      short loc_14000677A
0x14000675c  mov     ecx, [rsi+rbx*4]; dwRegister
0x14000675f  test    ecx, ecx
0x140006761  jz      short loc_140006774
0x140006763  call    cs:__imp_CoRevokeClassObject
0x140006769  test    eax, eax
0x14000676b  js      short loc_140006774
0x14000676d  mov     dword ptr [rsi+rbx*4], 0
0x140006774  inc     ebx
0x140006776  cmp     ebx, ebp
0x140006778  jb      short loc_140006758
0x14000677a  add     rsp, 28h
0x14000677e  pop     rdi
0x14000677f  pop     rsi
0x140006780  pop     rbp
0x140006781  pop     rbx
0x140006782  retn
```
