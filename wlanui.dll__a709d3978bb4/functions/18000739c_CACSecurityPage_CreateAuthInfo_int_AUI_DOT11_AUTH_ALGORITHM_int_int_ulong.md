# CACSecurityPage::CreateAuthInfo(int,AUI_DOT11_AUTH_ALGORITHM,int,int,ulong)

- ea: `0x18000739c`
- end: `0x1800073fc`
- name: `?CreateAuthInfo@CACSecurityPage@@AEAAPEAU_AUI_AUTH_INFO@@HW4AUI_DOT11_AUTH_ALGORITHM@@HHK@Z`
- size: `96`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b6f8`
- `0x18000bb54`
- `0x18000bd88`
- `0x18000c050`

## callees

- `0x18000739c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800073c5`
- `KERNEL32!HeapAlloc` at `0x1800073c5`
- `KERNEL32!GetProcessHeap` at `0x1800073b3`
- `KERNEL32!GetProcessHeap` at `0x1800073b3`

## pseudocode

```c
_DWORD *__fastcall CACSecurityPage::CreateAuthInfo(__int64 a1, int a2, int a3, int a4, int a5, int a6)
{
  HANDLE ProcessHeap; // rax
  _DWORD *result; // rax

  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, 8u, 0x14u);
  if ( result )
  {
    *result = a2;
    result[1] = a3;
    result[2] = a4;
    result[3] = a5;
    result[4] = a6;
  }
  return result;
}

```

## disassembly

```asm
0x18000739c  mov     [rsp+arg_0], rbx
0x1800073a1  mov     [rsp+arg_8], rsi
0x1800073a6  push    rdi
0x1800073a7  sub     rsp, 20h
0x1800073ab  mov     ebx, r9d
0x1800073ae  mov     edi, r8d
0x1800073b1  mov     esi, edx
0x1800073b3  call    cs:__imp_GetProcessHeap
0x1800073b9  mov     edx, 8; dwFlags
0x1800073be  mov     rcx, rax; hHeap
0x1800073c1  lea     r8d, [rdx+0Ch]; dwBytes
0x1800073c5  call    cs:__imp_HeapAlloc
0x1800073cb  mov     rcx, rax
0x1800073ce  test    rax, rax
0x1800073d1  jz      short loc_1800073EC
0x1800073d3  mov     [rax], esi
0x1800073d5  mov     [rax+4], edi
0x1800073d8  mov     [rax+8], ebx
0x1800073db  mov     eax, [rsp+28h+arg_20]
0x1800073df  mov     [rcx+0Ch], eax
0x1800073e2  mov     eax, [rsp+28h+arg_28]
0x1800073e6  mov     [rcx+10h], eax
0x1800073e9  mov     rax, rcx
0x1800073ec  mov     rbx, [rsp+28h+arg_0]
0x1800073f1  mov     rsi, [rsp+28h+arg_8]
0x1800073f6  add     rsp, 20h
0x1800073fa  pop     rdi
0x1800073fb  retn
```
