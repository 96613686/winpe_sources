# Microsoft::WRL::Module<1,CSingleUseOutOfProcModule>::RegisterCOMObject(ushort const *,_GUID *,IClassFactory * *,ulong *,uint)

- ea: `0x140005ac0`
- end: `0x140005adb`
- name: `?RegisterCOMObject@?$Module@$00VCSingleUseOutOfProcModule@@@WRL@Microsoft@@UEAAJPEBGPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z`
- size: `27`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140005acb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140005acb`

## pseudocode

```c
__int64 Microsoft::WRL::Module<1,CSingleUseOutOfProcModule>::RegisterCOMObject()
{
  RoOriginateError(2147500033LL, 0);
  return 2147500033LL;
}

```

## disassembly

```asm
0x140005ac0  sub     rsp, 28h
0x140005ac4  xor     edx, edx
0x140005ac6  mov     ecx, 80004001h
0x140005acb  call    cs:__imp_RoOriginateError
0x140005ad1  mov     eax, 80004001h
0x140005ad6  add     rsp, 28h
0x140005ada  retn
```
