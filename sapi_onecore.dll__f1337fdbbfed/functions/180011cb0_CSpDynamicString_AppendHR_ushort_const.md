# CSpDynamicString::AppendHR(ushort const *)

- ea: `0x180011cb0`
- end: `0x180011e3e`
- name: `?AppendHR@CSpDynamicString@@QEAAJPEBG@Z`
- size: `398`
- prototype: `__int64 __fastcall(CSpDynamicString *__hidden this, const unsigned __int16 *Src)`
- caller_count: `32`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c290`
- `0x18004a820`
- `0x18004dd20`
- `0x180055344`
- `0x18005aa44`
- `0x18006d428`
- `0x1800a2a70`
- `0x1800ad640`
- `0x1800aded4`
- `0x1800bd214`
- `0x1800bd820`
- `0x1800c7b1c`
- `0x1800c7d88`
- `0x1800c9fb4`
- `0x1800ca1d4`
- `0x1800cb948`
- `0x1800cedc8`
- `0x1800d5e6c`
- `0x1800d6478`
- `0x1800d66f4`
- `0x1800e82b0`
- `0x1800eea28`
- `0x1800eed80`
- `0x1800efed8`
- `0x1800fbbd0`
- `0x180171cfc`
- `0x180174930`
- `0x180174a88`
- `0x1801a9460`
- `0x180263a30`
- `0x180263d70`
- `0x180264330`

## callees

- `0x180011cb0`
- `0x180016c20`
- `0x18007d7b1`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180011db8`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180011db8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011daa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011daa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011dfb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011e12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011dfb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011e12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011deb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011deb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d60`

## pseudocode

```c
__int64 __fastcall CSpDynamicString::AppendHR(CSpDynamicString *this, const unsigned __int16 *Src)
{
  __int64 result; // rax
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rcx
  unsigned int v8; // edx
  unsigned __int64 v9; // rbx
  __int64 v10; // r14
  unsigned __int64 v11; // rdx
  unsigned int v12; // ebp
  __int64 v13; // rbp
  SIZE_T v14; // rcx
  _WORD *v15; // rdi
  size_t v16; // rbx
  void *v17; // rbx
  HANDLE ProcessHeap; // rax
  SIZE_T v19; // rax
  SIZE_T v20; // rax
  __int64 v21; // rcx
  _WORD *v22; // rdi

  result = 0;
  if ( Src )
  {
    v5 = -1;
    v6 = -1;
    do
      ++v6;
    while ( Src[v6] );
    v7 = *(_QWORD *)this;
    if ( !(_DWORD)v6 )
    {
      v12 = 0;
      if ( !v7 )
        return (unsigned int)CSpDynamicString::_allocate(this, 0);
      return v12;
    }
    v8 = 0;
    if ( v7 )
    {
      do
        ++v5;
      while ( *(_WORD *)(v7 + 2 * v5) );
      v8 = v5;
    }
    v9 = v8;
    v10 = (unsigned int)v6;
    v11 = v8 + (unsigned __int64)(unsigned int)v6;
    if ( v11 <= v9 )
      return (unsigned int)-2147024362;
    if ( (unsigned int)v11 >= 0x4FFFFFFF
      || (v13 = (unsigned int)v11, v14 = 2LL * (unsigned int)(v11 + 1), v14 <= (unsigned int)v11) )
    {
      SetLastError(0x216u);
      return (unsigned int)-2147024362;
    }
    v15 = CoTaskMemAlloc(v14);
    if ( !v15 )
    {
      SetLastError(0xEu);
      return (unsigned int)-2147024882;
    }
    v16 = v9;
    v15[v13] = 0;
    v12 = 0;
    memcpy_0(v15, *(const void **)this, v16 * 2);
    memcpy_0(&v15[v16], Src, 2 * v10);
    v17 = *(void **)this;
    *(_QWORD *)this = v15;
    if ( !v17 )
      return v12;
    ProcessHeap = GetProcessHeap();
    v19 = HeapSize(ProcessHeap, 0, v17);
    if ( v19 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v20 = v19 >> 1;
      v21 = v20 - 1;
      if ( v20 - 1 >= 8 )
      {
        v21 = 8;
        goto LABEL_19;
      }
      if ( v20 != 1 )
      {
LABEL_19:
        v22 = v17;
        while ( v21 )
        {
          *v22++ = -8531;
          --v21;
        }
      }
    }
    CoTaskMemFree(v17);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180011cb0  push    rsi
0x180011cb2  push    r15
0x180011cb4  sub     rsp, 28h
0x180011cb8  xor     eax, eax
0x180011cba  mov     rsi, rdx
0x180011cbd  mov     r15, rcx
0x180011cc0  test    rdx, rdx
0x180011cc3  jz      short loc_180011D3B
0x180011cc5  mov     [rsp+38h+arg_10], rbp
0x180011cca  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180011cd1  mov     [rsp+38h+arg_18], rdi
0x180011cd6  mov     rdi, rax
0x180011cd9  nop     dword ptr [rax+00000000h]
0x180011ce0  inc     rdi
0x180011ce3  cmp     word ptr [rdx+rdi*2], 0
0x180011ce8  jnz     short loc_180011CE0
0x180011cea  mov     rcx, [rcx]
0x180011ced  mov     [rsp+38h+arg_0], rbx
0x180011cf2  mov     [rsp+38h+var_18], r14
0x180011cf7  test    edi, edi
0x180011cf9  jz      loc_180011E22
0x180011cff  xor     edx, edx
0x180011d01  test    rcx, rcx
0x180011d04  jz      short loc_180011D12
0x180011d06  inc     rax
0x180011d09  cmp     [rcx+rax*2], dx
0x180011d0d  jnz     short loc_180011D06
0x180011d0f  mov     rdx, rax
0x180011d12  mov     ebx, edx
0x180011d14  mov     r14d, edi
0x180011d17  lea     rdx, [rbx+r14]
0x180011d1b  cmp     rdx, rbx
0x180011d1e  ja      short loc_180011D43
0x180011d20  mov     ebp, 80070216h
0x180011d25  mov     r14, [rsp+38h+var_18]
0x180011d2a  mov     eax, ebp
0x180011d2c  mov     rbp, [rsp+38h+arg_10]
0x180011d31  mov     rdi, [rsp+38h+arg_18]
0x180011d36  mov     rbx, [rsp+38h+arg_0]
0x180011d3b  add     rsp, 28h
0x180011d3f  pop     r15
0x180011d41  pop     rsi
0x180011d42  retn
0x180011d43  cmp     edx, 4FFFFFFFh
0x180011d49  jnb     loc_180011DF6
0x180011d4f  lea     ecx, [rdx+1]
0x180011d52  mov     ebp, edx
0x180011d54  add     rcx, rcx; cb
0x180011d57  cmp     rcx, rbp
0x180011d5a  jbe     loc_180011DF6
0x180011d60  call    cs:__imp_CoTaskMemAlloc
0x180011d66  mov     rdi, rax
0x180011d69  test    rax, rax
0x180011d6c  jz      loc_180011E0D
0x180011d72  xor     eax, eax
0x180011d74  add     rbx, rbx
0x180011d77  mov     [rdi+rbp*2], ax
0x180011d7b  mov     r8, rbx; Size
0x180011d7e  mov     rdx, [r15]; Src
0x180011d81  mov     rcx, rdi; void *
0x180011d84  xor     ebp, ebp
0x180011d86  call    memcpy_0
0x180011d8b  lea     r8, [r14+r14]; Size
0x180011d8f  mov     rdx, rsi; Src
0x180011d92  lea     rcx, [rbx+rdi]; void *
0x180011d96  call    memcpy_0
0x180011d9b  mov     rbx, [r15]
0x180011d9e  mov     [r15], rdi
0x180011da1  test    rbx, rbx
0x180011da4  jz      loc_180011D25
0x180011daa  call    cs:__imp_GetProcessHeap
0x180011db0  mov     r8, rbx; lpMem
0x180011db3  xor     edx, edx; dwFlags
0x180011db5  mov     rcx, rax; hHeap
0x180011db8  call    cs:__imp_HeapSize
0x180011dbe  lea     rcx, [rax-3]
0x180011dc2  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x180011dc6  ja      short loc_180011DE8
0x180011dc8  shr     rax, 1
0x180011dcb  lea     rcx, [rax-1]
0x180011dcf  cmp     rcx, 8
0x180011dd3  jb      short loc_180011E06
0x180011dd5  mov     ecx, 8
0x180011dda  mov     eax, 0DEADh
0x180011ddf  mov     rdi, rbx
0x180011de2  movzx   eax, ax
0x180011de5  rep stosw
0x180011de8  mov     rcx, rbx; pv
0x180011deb  call    cs:__imp_CoTaskMemFree
0x180011df1  jmp     loc_180011D25
0x180011df6  mov     ecx, 216h; dwErrCode
0x180011dfb  call    cs:__imp_SetLastError
0x180011e01  jmp     loc_180011D20
0x180011e06  test    rcx, rcx
0x180011e09  jz      short loc_180011DE8
0x180011e0b  jmp     short loc_180011DDA
0x180011e0d  mov     ecx, 0Eh; dwErrCode
0x180011e12  call    cs:__imp_SetLastError
0x180011e18  mov     ebp, 8007000Eh
0x180011e1d  jmp     loc_180011D25
0x180011e22  xor     ebp, ebp
0x180011e24  test    rcx, rcx
0x180011e27  jnz     loc_180011D25
0x180011e2d  xor     edx, edx; unsigned int
0x180011e2f  mov     rcx, r15; this
0x180011e32  call    ?_allocate@CSpDynamicString@@AEAAJK@Z; CSpDynamicString::_allocate(ulong)
0x180011e37  mov     ebp, eax
0x180011e39  jmp     loc_180011D25
```
