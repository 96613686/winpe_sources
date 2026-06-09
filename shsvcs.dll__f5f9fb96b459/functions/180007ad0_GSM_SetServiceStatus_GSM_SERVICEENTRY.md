# GSM::_SetServiceStatus(GSM::SERVICEENTRY *)

- ea: `0x180007ad0`
- end: `0x180007afc`
- name: `?_SetServiceStatus@GSM@@YAXPEAUSERVICEENTRY@1@@Z`
- size: `44`
- prototype: `void __fastcall(GSM *__hidden this, struct GSM::SERVICEENTRY *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800074c0`
- `0x1800077e0`
- `0x180022130`

## callees

- `0x180007ad0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007af4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007af4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007aea`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007aea`

## pseudocode

```c
void __fastcall GSM::_SetServiceStatus(GSM *this, struct GSM::SERVICEENTRY *a2)
{
  if ( GSM::g_loadedcontext == 1
    && !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 6), (LPSERVICE_STATUS)((char *)this + 8)) )
  {
    GetLastError();
  }
}

```

## disassembly

```asm
0x180007ad0  sub     rsp, 28h
0x180007ad4  cmp     cs:?g_loadedcontext@GSM@@3W4LOADEDCONTEXT@1@A, 1; GSM::LOADEDCONTEXT GSM::g_loadedcontext
0x180007adb  jz      short loc_180007AE2
0x180007add  add     rsp, 28h
0x180007ae1  retn
0x180007ae2  lea     rdx, [rcx+8]; lpServiceStatus
0x180007ae6  mov     rcx, [rcx+30h]; hServiceStatus
0x180007aea  call    cs:__imp_SetServiceStatus
0x180007af0  test    eax, eax
0x180007af2  jnz     short loc_180007ADD
0x180007af4  call    cs:__imp_GetLastError
0x180007afa  jmp     short loc_180007ADD
```
