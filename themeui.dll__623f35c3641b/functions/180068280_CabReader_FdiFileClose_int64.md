# CabReader::FdiFileClose(__int64)

- ea: `0x180068280`
- end: `0x1800682cd`
- name: `?FdiFileClose@CabReader@@CAH_J@Z`
- size: `77`
- prototype: `int __cdecl(INT_PTR hf)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180067c20`
- `0x180068804`

## callees

- `0x180068280`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800682a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800682a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006829d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800682ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006829d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800682ba`

## pseudocode

```c
__int64 __fastcall CabReader::FdiFileClose(INT_PTR hf)
{
  unsigned int v1; // edi

  v1 = 0;
  if ( (*(_BYTE *)hf & 1) != 0 )
  {
    if ( (*(_BYTE *)hf & 2) != 0 )
      CoTaskMemFree(*(LPVOID *)(hf + 8));
  }
  else if ( !CloseHandle(*(HANDLE *)(hf + 32)) )
  {
    v1 = -1;
  }
  CoTaskMemFree((LPVOID)hf);
  return v1;
}

```

## disassembly

```asm
0x180068280  mov     [rsp+arg_0], rbx
0x180068285  push    rdi
0x180068286  sub     rsp, 20h
0x18006828a  xor     edi, edi
0x18006828c  mov     rbx, rcx
0x18006828f  test    byte ptr [rcx], 1
0x180068292  jz      short loc_1800682A5
0x180068294  test    byte ptr [rcx], 2
0x180068297  jz      short loc_1800682B7
0x180068299  mov     rcx, [rcx+8]; pv
0x18006829d  call    cs:__imp_CoTaskMemFree
0x1800682a3  jmp     short loc_1800682B7
0x1800682a5  mov     rcx, [rcx+20h]; hObject
0x1800682a9  call    cs:__imp_CloseHandle
0x1800682af  or      ecx, 0FFFFFFFFh
0x1800682b2  test    eax, eax
0x1800682b4  cmovz   edi, ecx
0x1800682b7  mov     rcx, rbx; pv
0x1800682ba  call    cs:__imp_CoTaskMemFree
0x1800682c0  mov     rbx, [rsp+28h+arg_0]
0x1800682c5  mov     eax, edi
0x1800682c7  add     rsp, 20h
0x1800682cb  pop     rdi
0x1800682cc  retn
```
