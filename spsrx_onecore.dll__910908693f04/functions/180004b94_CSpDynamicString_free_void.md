# CSpDynamicString::_free(void)

- ea: `0x180004b94`
- end: `0x180004c3a`
- name: `?_free@CSpDynamicString@@AEAAXXZ`
- size: `166`
- prototype: `void __fastcall(CSpDynamicString *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800043c0`

## callees

- `0x180004b94`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180004bbb`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180004bbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c22`

## pseudocode

```c
void __fastcall CSpDynamicString::_free(LPVOID *this)
{
  const void *v1; // rdi
  HANDLE ProcessHeap; // rax
  SIZE_T v4; // rax
  SIZE_T v5; // rax
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  _WORD *v8; // rdi
  __int64 i; // rcx

  v1 = *this;
  if ( *this )
  {
    ProcessHeap = GetProcessHeap();
    v4 = HeapSize(ProcessHeap, 0, v1);
    if ( v4 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v5 = v4 >> 1;
      v6 = v5 - 1;
      if ( v5 - 1 >= 8 )
      {
        v8 = *this;
        if ( *this > this || (v7 = 0, v6 = 8, v8 + 7 < (_WORD *)this) )
        {
          for ( i = 8; i; --i )
            *v8++ = -8531;
          goto LABEL_13;
        }
        goto LABEL_8;
      }
      if ( v5 != 1 )
      {
        v7 = 0;
        do
LABEL_8:
          *((_WORD *)*this + v7++) = -8531;
        while ( v7 < v6 );
      }
    }
LABEL_13:
    CoTaskMemFree(*this);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180004b94  mov     [rsp+arg_0], rbx
0x180004b99  push    rdi
0x180004b9a  sub     rsp, 20h
0x180004b9e  mov     rdi, [rcx]
0x180004ba1  mov     rbx, rcx
0x180004ba4  test    rdi, rdi
0x180004ba7  jz      loc_180004C2F
0x180004bad  call    cs:__imp_GetProcessHeap
0x180004bb3  mov     r8, rdi; lpMem
0x180004bb6  xor     edx, edx; dwFlags
0x180004bb8  mov     rcx, rax; hHeap
0x180004bbb  call    cs:__imp_HeapSize
0x180004bc1  lea     rdx, [rax-3]
0x180004bc5  cmp     rdx, 0FFFFFFFFFFFFFFFBh
0x180004bc9  ja      short loc_180004C1F
0x180004bcb  shr     rax, 1
0x180004bce  mov     r9d, 8
0x180004bd4  lea     rdx, [rax-1]
0x180004bd8  cmp     rdx, r9
0x180004bdb  jnb     short loc_180004BE6
0x180004bdd  test    rdx, rdx
0x180004be0  jz      short loc_180004C1F
0x180004be2  xor     ecx, ecx
0x180004be4  jmp     short loc_180004BFC
0x180004be6  mov     rdi, [rbx]
0x180004be9  cmp     rdi, rbx
0x180004bec  ja      short loc_180004C0F
0x180004bee  xor     ecx, ecx
0x180004bf0  lea     rax, [rdi+0Eh]
0x180004bf4  mov     rdx, r9
0x180004bf7  cmp     rax, rbx
0x180004bfa  jb      short loc_180004C0F
0x180004bfc  mov     rax, [rbx]
0x180004bff  mov     word ptr [rax+rcx*2], 0DEADh
0x180004c05  inc     rcx
0x180004c08  cmp     rcx, rdx
0x180004c0b  jb      short loc_180004BFC
0x180004c0d  jmp     short loc_180004C1F
0x180004c0f  mov     r8d, 0DEADh
0x180004c15  mov     rcx, r9
0x180004c18  movzx   eax, r8w
0x180004c1c  rep stosw
0x180004c1f  mov     rcx, [rbx]; pv
0x180004c22  call    cs:__imp_CoTaskMemFree
0x180004c28  mov     qword ptr [rbx], 0
0x180004c2f  mov     rbx, [rsp+28h+arg_0]
0x180004c34  add     rsp, 20h
0x180004c38  pop     rdi
0x180004c39  retn
```
