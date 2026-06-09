# tlx::_UndoSolo__QueryLogCommand::PublisherCache::Open_::_8_::_lambda_1___::__UndoSolo__QueryLogCommand::PublisherCache::Open_::_8_::_lambda_1___

- ea: `0x14001c2f8`
- end: `0x14001c310`
- name: `tlx::_UndoSolo__QueryLogCommand::PublisherCache::Open_::_8_::_lambda_1___::__UndoSolo__QueryLogCommand::PublisherCache::Open_::_8_::_lambda_1___`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001c0a8`

## callees

- `0x14001c2f8`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x14001c305`
- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x14001c305`

## pseudocode

```c
LANGID __fastcall tlx::_UndoSolo__QueryLogCommand::PublisherCache::Open_::_8_::_lambda_1___::__UndoSolo__QueryLogCommand::PublisherCache::Open_::_8_::_lambda_1___(
        __int64 a1)
{
  LANGID result; // ax

  if ( *(_BYTE *)(a1 + 2) )
    return SetThreadUILanguage(*(_WORD *)a1);
  return result;
}

```

## disassembly

```asm
0x14001c2f8  sub     rsp, 28h
0x14001c2fc  cmp     byte ptr [rcx+2], 0
0x14001c300  jz      short loc_14001C30B
0x14001c302  movzx   ecx, word ptr [rcx]; LangId
0x14001c305  call    cs:__imp_SetThreadUILanguage
0x14001c30b  add     rsp, 28h
0x14001c30f  retn
```
