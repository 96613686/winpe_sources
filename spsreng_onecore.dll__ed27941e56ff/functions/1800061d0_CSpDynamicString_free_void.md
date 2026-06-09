# CSpDynamicString::_free(void)

- ea: `0x1800061d0`
- end: `0x180006276`
- name: `?_free@CSpDynamicString@@AEAAXXZ`
- size: `166`
- prototype: `void __fastcall(CSpDynamicString *__hidden this)`
- caller_count: `53`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800048ec`
- `0x1800049e0`
- `0x1800049f0`
- `0x180004a18`
- `0x180004a80`
- `0x180004b60`
- `0x180004c18`
- `0x180004ebc`
- `0x1800056fc`
- `0x180005fb8`
- `0x180006bb0`
- `0x18000725c`
- `0x18000761c`
- `0x180007b70`
- `0x180007eec`
- `0x180008d6c`
- `0x18000ab60`
- `0x18000ad60`
- `0x18000adcc`
- `0x18000b9f8`
- `0x18000c808`
- `0x18000ca0c`
- `0x18000d258`
- `0x18000e6b0`
- `0x18000f948`
- `0x180011800`
- `0x180011870`
- `0x1800137e0`
- `0x1800158e8`
- `0x180075788`
- `0x180098928`
- `0x180098c00`
- `0x180099390`
- `0x1800999d8`
- `0x1800afb24`
- `0x1800b04a4`
- `0x1800b1240`
- `0x1800b14d8`
- `0x1800b1784`
- `0x1800c6aa0`
- `0x1800c7f80`
- `0x1800c8b30`
- `0x1800c921c`
- `0x1800c94c4`
- `0x1800c963c`
- `0x1800ca1a8`
- `0x1800ca774`
- `0x1800da5e0`
- `0x1800dbb28`
- `0x1800f4e84`

## callees

- `0x1800061d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800061f7`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800061f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000625e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000625e`

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
0x1800061d0  mov     [rsp+arg_0], rbx
0x1800061d5  push    rdi
0x1800061d6  sub     rsp, 20h
0x1800061da  mov     rdi, [rcx]
0x1800061dd  mov     rbx, rcx
0x1800061e0  test    rdi, rdi
0x1800061e3  jz      loc_18000626B
0x1800061e9  call    cs:__imp_GetProcessHeap
0x1800061ef  mov     r8, rdi; lpMem
0x1800061f2  xor     edx, edx; dwFlags
0x1800061f4  mov     rcx, rax; hHeap
0x1800061f7  call    cs:__imp_HeapSize
0x1800061fd  lea     rdx, [rax-3]
0x180006201  cmp     rdx, 0FFFFFFFFFFFFFFFBh
0x180006205  ja      short loc_18000625B
0x180006207  shr     rax, 1
0x18000620a  mov     r9d, 8
0x180006210  lea     rdx, [rax-1]
0x180006214  cmp     rdx, r9
0x180006217  jnb     short loc_180006222
0x180006219  test    rdx, rdx
0x18000621c  jz      short loc_18000625B
0x18000621e  xor     ecx, ecx
0x180006220  jmp     short loc_180006238
0x180006222  mov     rdi, [rbx]
0x180006225  cmp     rdi, rbx
0x180006228  ja      short loc_18000624B
0x18000622a  xor     ecx, ecx
0x18000622c  lea     rax, [rdi+0Eh]
0x180006230  mov     rdx, r9
0x180006233  cmp     rax, rbx
0x180006236  jb      short loc_18000624B
0x180006238  mov     rax, [rbx]
0x18000623b  mov     word ptr [rax+rcx*2], 0DEADh
0x180006241  inc     rcx
0x180006244  cmp     rcx, rdx
0x180006247  jb      short loc_180006238
0x180006249  jmp     short loc_18000625B
0x18000624b  mov     r8d, 0DEADh
0x180006251  mov     rcx, r9
0x180006254  movzx   eax, r8w
0x180006258  rep stosw
0x18000625b  mov     rcx, [rbx]; pv
0x18000625e  call    cs:__imp_CoTaskMemFree
0x180006264  mov     qword ptr [rbx], 0
0x18000626b  mov     rbx, [rsp+28h+arg_0]
0x180006270  add     rsp, 20h
0x180006274  pop     rdi
0x180006275  retn
```
