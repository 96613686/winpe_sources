# CUpdateHistoryEntry::FreeDSHistoryEvent(tagDSHistoryEvent_V3 *)

- ea: `0x180067e28`
- end: `0x180067eb4`
- name: `?FreeDSHistoryEvent@CUpdateHistoryEntry@@IEAAXPEAUtagDSHistoryEvent_V3@@@Z`
- size: `140`
- prototype: `void(CUpdateHistoryEntry *__hidden this, struct tagDSHistoryEvent_V3 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180067ebc`
- `0x180068b5c`

## callees

- `0x180067e28`
- `0x1800821b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067e47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067e51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067e5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067e65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067e9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067ea8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067e47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067e51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067e5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067e65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067e9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067ea8`

## pseudocode

```c
void __fastcall CUpdateHistoryEntry::FreeDSHistoryEvent(CUpdateHistoryEntry *this, struct tagDSHistoryEvent_V3 *a2)
{
  if ( a2 )
  {
    CoTaskMemFree(*((LPVOID *)a2 + 8));
    CoTaskMemFree(*((LPVOID *)a2 + 9));
    CoTaskMemFree(*((LPVOID *)a2 + 10));
    CoTaskMemFree(*((LPVOID *)a2 + 11));
    CoTaskMemFree(*((LPVOID *)a2 + 12));
    CoFreeStringArray(*((wchar_t **const *)a2 + 14), *((_DWORD *)a2 + 26));
    CoFreeStringArray(*((wchar_t **const *)a2 + 16), *((_DWORD *)a2 + 30));
    CoFreeStringArray(*((wchar_t **const *)a2 + 18), *((_DWORD *)a2 + 35));
    CoTaskMemFree(*((LPVOID *)a2 + 20));
    CoTaskMemFree(a2);
  }
}

```

## disassembly

```asm
0x180067e28  test    rdx, rdx
0x180067e2b  jz      locret_180067EB3
0x180067e31  push    rbx
0x180067e32  sub     rsp, 20h
0x180067e36  mov     rcx, [rdx+40h]; pv
0x180067e3a  mov     rbx, rdx
0x180067e3d  call    cs:__imp_CoTaskMemFree
0x180067e43  mov     rcx, [rbx+48h]; pv
0x180067e47  call    cs:__imp_CoTaskMemFree
0x180067e4d  mov     rcx, [rbx+50h]; pv
0x180067e51  call    cs:__imp_CoTaskMemFree
0x180067e57  mov     rcx, [rbx+58h]; pv
0x180067e5b  call    cs:__imp_CoTaskMemFree
0x180067e61  mov     rcx, [rbx+60h]; pv
0x180067e65  call    cs:__imp_CoTaskMemFree
0x180067e6b  mov     edx, [rbx+68h]; unsigned int
0x180067e6e  mov     rcx, [rbx+70h]; pv
0x180067e72  call    ?CoFreeStringArray@@YAJQEAPEA_WI@Z; CoFreeStringArray(wchar_t * * const,uint)
0x180067e77  mov     edx, [rbx+78h]; unsigned int
0x180067e7a  mov     rcx, [rbx+80h]; pv
0x180067e81  call    ?CoFreeStringArray@@YAJQEAPEA_WI@Z; CoFreeStringArray(wchar_t * * const,uint)
0x180067e86  mov     edx, [rbx+8Ch]; unsigned int
0x180067e8c  mov     rcx, [rbx+90h]; pv
0x180067e93  call    ?CoFreeStringArray@@YAJQEAPEA_WI@Z; CoFreeStringArray(wchar_t * * const,uint)
0x180067e98  mov     rcx, [rbx+0A0h]; pv
0x180067e9f  call    cs:__imp_CoTaskMemFree
0x180067ea5  mov     rcx, rbx; pv
0x180067ea8  call    cs:__imp_CoTaskMemFree
0x180067eae  add     rsp, 20h
0x180067eb2  pop     rbx
0x180067eb3  retn
```
