# GatewayIdList::Uninitialize(void)

- ea: `0x180059ab4`
- end: `0x180059b4f`
- name: `?Uninitialize@GatewayIdList@@QEAAXXZ`
- size: `155`
- prototype: `void __fastcall(GatewayIdList *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180057f70`
- `0x1800597ec`
- `0x180059844`

## callees

- `0x180059ab4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059ad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059b18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059b38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059ad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059b18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059b38`

## pseudocode

```c
void __fastcall GatewayIdList::Uninitialize(GatewayIdList *this)
{
  LPVOID *v1; // rsi
  unsigned int i; // ebp
  unsigned int j; // esi
  __int64 v5; // rbx
  __int64 v6; // rbx

  v1 = (LPVOID *)((char *)this + 8);
  for ( i = 0; i < *((_DWORD *)this + 4); *((_QWORD *)*v1 + v5) = 0 )
  {
    v5 = i;
    CoTaskMemFree(*((LPVOID *)*v1 + i++));
  }
  CoTaskMemFree(*v1);
  *v1 = 0;
  for ( j = 0; j < *((_DWORD *)this + 8); *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v6) = 0 )
  {
    v6 = j;
    CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 3) + 8LL * j++));
  }
  CoTaskMemFree(*((LPVOID *)this + 3));
  *((_QWORD *)this + 3) = 0;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
}

```

## disassembly

```asm
0x180059ab4  push    rbx
0x180059ab6  push    rbp
0x180059ab7  push    rsi
0x180059ab8  push    rdi
0x180059ab9  push    r14
0x180059abb  sub     rsp, 20h
0x180059abf  xor     r14d, r14d
0x180059ac2  lea     rsi, [rcx+8]
0x180059ac6  mov     rdi, rcx
0x180059ac9  mov     ebp, r14d
0x180059acc  cmp     [rcx+10h], r14d
0x180059ad0  ja      short loc_180059B0F
0x180059ad2  mov     rcx, [rsi]; pv
0x180059ad5  call    cs:__imp_CoTaskMemFree
0x180059adb  mov     [rsi], r14
0x180059ade  mov     esi, r14d
0x180059ae1  cmp     [rdi+20h], r14d
0x180059ae5  ja      short loc_180059B2E
0x180059ae7  mov     rcx, [rdi+18h]; pv
0x180059aeb  call    cs:__imp_CoTaskMemFree
0x180059af1  mov     [rdi+18h], r14
0x180059af5  mov     [rdi], r14
0x180059af8  mov     [rdi+10h], r14
0x180059afc  mov     [rdi+20h], r14
0x180059b00  mov     [rdi+28h], r14d
0x180059b04  add     rsp, 20h
0x180059b08  pop     r14
0x180059b0a  pop     rdi
0x180059b0b  pop     rsi
0x180059b0c  pop     rbp
0x180059b0d  pop     rbx
0x180059b0e  retn
0x180059b0f  mov     rcx, [rsi]
0x180059b12  mov     ebx, ebp
0x180059b14  mov     rcx, [rcx+rbx*8]; pv
0x180059b18  call    cs:__imp_CoTaskMemFree
0x180059b1e  mov     rax, [rsi]
0x180059b21  inc     ebp
0x180059b23  mov     [rax+rbx*8], r14
0x180059b27  cmp     ebp, [rdi+10h]
0x180059b2a  jb      short loc_180059B0F
0x180059b2c  jmp     short loc_180059AD2
0x180059b2e  mov     rcx, [rdi+18h]
0x180059b32  mov     ebx, esi
0x180059b34  mov     rcx, [rcx+rbx*8]; pv
0x180059b38  call    cs:__imp_CoTaskMemFree
0x180059b3e  mov     rax, [rdi+18h]
0x180059b42  inc     esi
0x180059b44  mov     [rax+rbx*8], r14
0x180059b48  cmp     esi, [rdi+20h]
0x180059b4b  jb      short loc_180059B2E
0x180059b4d  jmp     short loc_180059AE7
```
