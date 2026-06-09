# RegReadByteArrayValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &)

- ea: `0x14002f384`
- end: `0x14002f473`
- name: `?RegReadByteArrayValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpSubKey, LPCWSTR lpValue, LPDWORD pcbData, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x140014988`
- `0x1400151ec`
- `0x140015cac`

## callees

- `0x1400039a0`
- `0x140004ab0`
- `0x140015898`
- `0x140022510`
- `0x14002f384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002f3c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002f460`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002f3c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002f460`

## pseudocode

```c
LSTATUS __fastcall RegReadByteArrayValueNoThrow(
        HKEY hkey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValue,
        LPDWORD pcbData,
        void **a5)
{
  LSTATUS result; // eax
  const struct std::nothrow_t *v10; // rdx
  DWORD v11; // edi
  void *v12; // rax
  void *v13; // rbx
  PVOID *v14; // rdi
  void *v15; // rcx
  _QWORD v16[9]; // [rsp+40h] [rbp-48h] BYREF
  DWORD pdwType; // [rsp+A8h] [rbp+20h] BYREF

  pdwType = 0;
  *pcbData = 0;
  result = RegGetValueW(hkey, lpSubKey, lpValue, 0x28u, &pdwType, 0, pcbData);
  if ( !result && *pcbData )
  {
    v11 = *pcbData;
    v12 = operator new(*pcbData, v10);
    v13 = v12;
    if ( v12 )
      memset_0(v12, 0, v11);
    else
      v13 = 0;
    v14 = a5;
    v16[0] = 0;
    v15 = *a5;
    *a5 = v13;
    if ( v15 )
      operator delete(v15);
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(v16);
    if ( *v14 )
      return RegGetValueW(hkey, lpSubKey, lpValue, 0x28u, &pdwType, *v14, pcbData);
    else
      return 14;
  }
  return result;
}

```

## disassembly

```asm
0x14002f384  mov     rax, rsp
0x14002f387  push    rbx
0x14002f388  push    rbp
0x14002f389  push    rsi
0x14002f38a  push    rdi
0x14002f38b  push    r14
0x14002f38d  push    r15
0x14002f38f  sub     rsp, 58h
0x14002f393  mov     [rax-58h], r9
0x14002f397  mov     rsi, r9
0x14002f39a  mov     qword ptr [rax-60h], 0
0x14002f3a2  mov     rbp, r8
0x14002f3a5  mov     dword ptr [rax+20h], 0
0x14002f3ac  lea     rax, [rax+20h]
0x14002f3b0  mov     dword ptr [r9], 0
0x14002f3b7  mov     r14, rdx
0x14002f3ba  mov     r9d, 28h ; '('; dwFlags
0x14002f3c0  mov     [rsp+88h+pdwType], rax; pdwType
0x14002f3c5  mov     r15, rcx
0x14002f3c8  call    cs:__imp_RegGetValueW
0x14002f3ce  test    eax, eax
0x14002f3d0  jnz     loc_14002F466
0x14002f3d6  cmp     [rsi], eax
0x14002f3d8  jbe     loc_14002F466
0x14002f3de  mov     edi, [rsi]
0x14002f3e0  mov     ecx, edi; unsigned __int64
0x14002f3e2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002f3e7  mov     rbx, rax
0x14002f3ea  test    rax, rax
0x14002f3ed  jz      short loc_14002F3FE
0x14002f3ef  mov     r8d, edi; Size
0x14002f3f2  xor     edx, edx; Val
0x14002f3f4  mov     rcx, rax; void *
0x14002f3f7  call    memset_0
0x14002f3fc  jmp     short loc_14002F400
0x14002f3fe  xor     ebx, ebx
0x14002f400  mov     rdi, [rsp+88h+arg_20]
0x14002f408  mov     [rsp+88h+var_48], 0
0x14002f411  mov     rcx, [rdi]; void *
0x14002f414  mov     [rdi], rbx
0x14002f417  test    rcx, rcx
0x14002f41a  jz      short loc_14002F421
0x14002f41c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002f421  lea     rcx, [rsp+88h+var_48]
0x14002f426  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x14002f42b  mov     rax, [rdi]
0x14002f42e  test    rax, rax
0x14002f431  jnz     short loc_14002F43A
0x14002f433  mov     eax, 0Eh
0x14002f438  jmp     short loc_14002F466
0x14002f43a  mov     [rsp+88h+pcbData], rsi; pcbData
0x14002f43f  mov     r9d, 28h ; '('; dwFlags
0x14002f445  mov     [rsp+88h+pvData], rax; pvData
0x14002f44a  mov     r8, rbp; lpValue
0x14002f44d  lea     rax, [rsp+88h+arg_18]
0x14002f455  mov     rdx, r14; lpSubKey
0x14002f458  mov     rcx, r15; hkey
0x14002f45b  mov     [rsp+88h+pdwType], rax; pdwType
0x14002f460  call    cs:__imp_RegGetValueW
0x14002f466  add     rsp, 58h
0x14002f46a  pop     r15
0x14002f46c  pop     r14
0x14002f46e  pop     rdi
0x14002f46f  pop     rsi
0x14002f470  pop     rbp
0x14002f471  pop     rbx
0x14002f472  retn
```
