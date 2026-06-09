# CCFGEngine::LoadGrammarFromFile(ushort const *,ushort const *,ushort const *,ushort const *,SPGRAMMARHANDLE__ *,void *,int,CCFGGrammar * *,ISpeechResourceLoader *,IInternetSecurityManager *,ulong,SPGRAMMAROPTIONS)

- ea: `0x18013b9cc`
- end: `0x18013c1a4`
- name: `?LoadGrammarFromFile@CCFGEngine@@QEAAJPEBG000PEAUSPGRAMMARHANDLE__@@PEAXHPEAPEAVCCFGGrammar@@PEAUISpeechResourceLoader@@PEAUIInternetSecurityManager@@KW4SPGRAMMAROPTIONS@@@Z`
- size: `2008`
- prototype: `int(CCFGEngine *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct SPGRAMMARHANDLE__ *, void *, int, struct CCFGGrammar **, struct ISpeechResourceLoader *, struct IInternetSecurityManager *, unsigned int, enum SPGRAMMAROPTIONS)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006d818`
- `0x180197ec0`

## callees

- `0x180013ec0`
- `0x1800156f0`
- `0x18001ae00`
- `0x180079e30`
- `0x18007a2dc`
- `0x18013a83c`
- `0x18013a9a4`
- `0x18013b7dc`
- `0x18013b9cc`
- `0x18013c988`
- `0x18016c418`
- `0x180196d20`
- `0x1801975ac`
- `0x180198704`
- `0x18019b7fc`
- `0x18019b92c`
- `0x18019bc38`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18013c16f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18013c178`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18013c16f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18013c178`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18013ba3d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18013bc62`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18013ba3d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18013bc62`
- `OLEAUT32!__imp_SysFreeString` at `0x18013bd90`
- `OLEAUT32!__imp_SysFreeString` at `0x18013bec5`
- `OLEAUT32!__imp_SysFreeString` at `0x18013c0d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18013bd90`
- `OLEAUT32!__imp_SysFreeString` at `0x18013bec5`
- `OLEAUT32!__imp_SysFreeString` at `0x18013c0d0`

## string_xrefs

- `0x18013bae8`: `CFGEngine is loading grammar from file %S, base uri=%S, sharing uri = %S, options=0x%X`
- `0x18013bd53`: `Release local copy %S`
- `0x18013be88`: `Release local copy %S`
- `0x18013c096`: `Release local copy %S`

## pseudocode

```c

```
