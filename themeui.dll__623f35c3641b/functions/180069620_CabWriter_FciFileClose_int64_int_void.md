# CabWriter::FciFileClose(__int64,int *,void *)

- ea: `0x180069620`
- end: `0x180069681`
- name: `?FciFileClose@CabWriter@@CAH_JPEAHPEAX@Z`
- size: `97`
- prototype: `int __cdecl(INT_PTR hf, int *err, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180069620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006965b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006965b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069651`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069651`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069669`

## pseudocode

```c
__int64 __fastcall CabWriter::FciFileClose(INT_PTR hf, DWORD *err, void *pv)
{
  unsigned int v3; // edi

  v3 = 0;
  if ( (*(_BYTE *)hf & 1) != 0 )
  {
    if ( (*(_BYTE *)hf & 2) != 0 )
      CoTaskMemFree(*(LPVOID *)(hf + 8));
  }
  else if ( !CloseHandle(*(HANDLE *)(hf + 32)) )
  {
    *err = GetLastError();
    v3 = -1;
  }
  CoTaskMemFree((LPVOID)hf);
  return v3;
}

```

## disassembly

```asm
0x180069620  mov     [rsp+arg_0], rbx
0x180069625  mov     [rsp+arg_8], rsi
0x18006962a  push    rdi
0x18006962b  sub     rsp, 20h
0x18006962f  xor     edi, edi
0x180069631  mov     rsi, rdx
0x180069634  test    byte ptr [rcx], 1
0x180069637  mov     rbx, rcx
0x18006963a  jz      short loc_18006964D
0x18006963c  test    byte ptr [rcx], 2
0x18006963f  jz      short loc_180069666
0x180069641  mov     rcx, [rcx+8]; pv
0x180069645  call    cs:__imp_CoTaskMemFree
0x18006964b  jmp     short loc_180069666
0x18006964d  mov     rcx, [rcx+20h]; hObject
0x180069651  call    cs:__imp_CloseHandle
0x180069657  test    eax, eax
0x180069659  jnz     short loc_180069666
0x18006965b  call    cs:__imp_GetLastError
0x180069661  mov     [rsi], eax
0x180069663  or      edi, 0FFFFFFFFh
0x180069666  mov     rcx, rbx; pv
0x180069669  call    cs:__imp_CoTaskMemFree
0x18006966f  mov     rbx, [rsp+28h+arg_0]
0x180069674  mov     eax, edi
0x180069676  mov     rsi, [rsp+28h+arg_8]
0x18006967b  add     rsp, 20h
0x18006967f  pop     rdi
0x180069680  retn
```
