# CStatusCode::StatusCodeOfLastError(void)

- ea: `0x18000674c`
- end: `0x180006769`
- name: `?StatusCodeOfLastError@CStatusCode@@SAJXZ`
- size: `29`
- prototype: `__int64(void)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180002270`
- `0x180002940`
- `0x180002b64`
- `0x180002f98`
- `0x1800030ec`
- `0x180003190`
- `0x180003280`
- `0x180003434`
- `0x180004178`
- `0x180004d80`
- `0x18000acc0`
- `0x18000aefc`
- `0x18000d094`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006750`

## pseudocode

```c
__int64 CStatusCode::StatusCodeOfLastError(void)
{
  DWORD LastError; // eax

  LastError = GetLastError();
  return LastError != 0 ? LastError | 0x80070000 : 0;
}

```

## disassembly

```asm
0x18000674c  sub     rsp, 28h
0x180006750  call    cs:__imp_GetLastError
0x180006756  mov     ecx, eax
0x180006758  or      ecx, 80070000h
0x18000675e  neg     eax
0x180006760  sbb     eax, eax
0x180006762  and     eax, ecx
0x180006764  add     rsp, 28h
0x180006768  retn
```
