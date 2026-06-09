# CLoggedOnAccounts::Reset(void)

- ea: `0x18000bd20`
- end: `0x18000bd4a`
- name: `?Reset@CLoggedOnAccounts@@UEAAJXZ`
- size: `42`
- prototype: `__int64 __fastcall(CLoggedOnAccounts *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bd2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bd2d`

## pseudocode

```c
__int64 __fastcall CLoggedOnAccounts::Reset(LPVOID *this)
{
  __int64 result; // rax

  CoTaskMemFree(this[2]);
  result = 0;
  this[2] = 0;
  *((_DWORD *)this + 3) = 0;
  return result;
}

```

## disassembly

```asm
0x18000bd20  push    rbx
0x18000bd22  sub     rsp, 20h
0x18000bd26  mov     rbx, rcx
0x18000bd29  mov     rcx, [rcx+10h]; pv
0x18000bd2d  call    cs:__imp_CoTaskMemFree
0x18000bd33  xor     eax, eax
0x18000bd35  mov     qword ptr [rbx+10h], 0
0x18000bd3d  mov     dword ptr [rbx+0Ch], 0
0x18000bd44  add     rsp, 20h
0x18000bd48  pop     rbx
0x18000bd49  retn
```
