# _attribute_t::FreeAll(void)

- ea: `0x180004ac4`
- end: `0x180004b2f`
- name: `?FreeAll@_attribute_t@@QEAAXXZ`
- size: `107`
- prototype: `void __fastcall(_attribute_t *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002e38`
- `0x1800032ec`
- `0x180004330`
- `0x180004b38`
- `0x180005b30`
- `0x1800081b0`
- `0x180011ef0`
- `0x180012350`
- `0x1800126c0`
- `0x180012b74`

## callees

- `0x180004ac4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ad7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004af7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ad7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004af7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b15`

## pseudocode

```c
void __fastcall _attribute_t::FreeAll(LPVOID *this)
{
  if ( *((_DWORD *)this + 2) == 10 )
  {
    CoTaskMemFree(this[2]);
    this[2] = 0;
  }
  else if ( *((_DWORD *)this + 2) == 14 )
  {
    CoTaskMemFree(this[3]);
    this[3] = 0;
    *((_DWORD *)this + 4) = 0;
  }
  CoTaskMemFree(*this);
  *this = 0;
}

```

## disassembly

```asm
0x180004ac4  push    rbx
0x180004ac6  sub     rsp, 20h
0x180004aca  cmp     dword ptr [rcx+8], 0Ah
0x180004ace  mov     rbx, rcx
0x180004ad1  jnz     short loc_180004AED
0x180004ad3  mov     rcx, [rcx+10h]; pv
0x180004ad7  call    cs:__imp_CoTaskMemFree
0x180004ade  nop     dword ptr [rax+rax+00h]
0x180004ae3  mov     qword ptr [rbx+10h], 0
0x180004aeb  jmp     short loc_180004B12
0x180004aed  cmp     dword ptr [rcx+8], 0Eh
0x180004af1  jnz     short loc_180004B12
0x180004af3  mov     rcx, [rcx+18h]; pv
0x180004af7  call    cs:__imp_CoTaskMemFree
0x180004afe  nop     dword ptr [rax+rax+00h]
0x180004b03  mov     qword ptr [rbx+18h], 0
0x180004b0b  mov     dword ptr [rbx+10h], 0
0x180004b12  mov     rcx, [rbx]; pv
0x180004b15  call    cs:__imp_CoTaskMemFree
0x180004b1c  nop     dword ptr [rax+rax+00h]
0x180004b21  mov     qword ptr [rbx], 0
0x180004b28  add     rsp, 20h
0x180004b2c  pop     rbx
0x180004b2d  retn
```
