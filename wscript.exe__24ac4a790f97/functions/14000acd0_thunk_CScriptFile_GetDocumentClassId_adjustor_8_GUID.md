# [thunk]:CScriptFile::GetDocumentClassId`adjustor{8}' (_GUID *)

- ea: `0x14000acd0`
- end: `0x14000acd9`
- name: `?GetDocumentClassId@CScriptFile@@W7EAAJPEAU_GUID@@@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x14000acb0`

## pseudocode

```c
__int64 __fastcall CScriptFile::GetDocumentClassId(__int64 a1, unsigned __int16 **a2)
{
  return CScriptingEngine::GetDocVersionString((CScriptingEngine *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x14000acd0  sub     rcx, 8; this
0x14000acd4  jmp     ?GetDocVersionString@CScriptingEngine@@UEAAJPEAPEAG@Z; CScriptingEngine::GetDocVersionString(ushort * *)
```
