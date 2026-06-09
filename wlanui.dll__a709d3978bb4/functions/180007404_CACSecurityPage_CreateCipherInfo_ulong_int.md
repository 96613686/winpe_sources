# CACSecurityPage::CreateCipherInfo(ulong,int)

- ea: `0x180007404`
- end: `0x18000743f`
- name: `?CreateCipherInfo@CACSecurityPage@@AEAAPEAU_AUI_CIPHER_INFO@@KH@Z`
- size: `59`
- prototype: `struct _AUI_CIPHER_INFO *__fastcall(CACSecurityPage *__hidden this, unsigned int, int)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800078f4`
- `0x180007ae4`
- `0x18000b6f8`
- `0x18000bb54`
- `0x18000bd88`

## callees

- `0x180007404`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180007424`
- `KERNEL32!HeapAlloc` at `0x180007424`
- `KERNEL32!GetProcessHeap` at `0x180007413`
- `KERNEL32!GetProcessHeap` at `0x180007413`

## pseudocode

```c
struct _AUI_CIPHER_INFO *__fastcall CACSecurityPage::CreateCipherInfo(CACSecurityPage *this, int a2, int a3)
{
  HANDLE ProcessHeap; // rax
  struct _AUI_CIPHER_INFO *result; // rax

  ProcessHeap = GetProcessHeap();
  result = (struct _AUI_CIPHER_INFO *)HeapAlloc(ProcessHeap, 8u, 8u);
  if ( result )
  {
    *(_DWORD *)result = a3;
    *((_DWORD *)result + 1) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x180007404  mov     [rsp+arg_0], rbx
0x180007409  push    rdi
0x18000740a  sub     rsp, 20h
0x18000740e  mov     ebx, r8d
0x180007411  mov     edi, edx
0x180007413  call    cs:__imp_GetProcessHeap
0x180007419  mov     edx, 8; dwFlags
0x18000741e  mov     rcx, rax; hHeap
0x180007421  mov     r8d, edx; dwBytes
0x180007424  call    cs:__imp_HeapAlloc
0x18000742a  test    rax, rax
0x18000742d  jz      short loc_180007434
0x18000742f  mov     [rax], ebx
0x180007431  mov     [rax+4], edi
0x180007434  mov     rbx, [rsp+28h+arg_0]
0x180007439  add     rsp, 20h
0x18000743d  pop     rdi
0x18000743e  retn
```
