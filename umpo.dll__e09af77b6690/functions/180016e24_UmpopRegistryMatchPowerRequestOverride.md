# UmpopRegistryMatchPowerRequestOverride

- ea: `0x180016e24`
- end: `0x180016fcd`
- name: `UmpopRegistryMatchPowerRequestOverride`
- size: `425`
- prototype: `char __fastcall(HKEY hKey, wchar_t *Str, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180002f7c`

## callees

- `0x180016e24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016f66`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016f66`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180016ef8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180016ef8`
- `ntdll!RtlAllocateHeap` at `0x180016eb4`
- `ntdll!RtlAllocateHeap` at `0x180016ee0`
- `ntdll!RtlAllocateHeap` at `0x180016eb4`
- `ntdll!RtlAllocateHeap` at `0x180016ee0`
- `ntdll!RtlFreeHeap` at `0x180016f96`
- `ntdll!RtlFreeHeap` at `0x180016fad`
- `ntdll!RtlFreeHeap` at `0x180016f96`
- `ntdll!RtlFreeHeap` at `0x180016fad`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180016f4d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180016f4d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016e8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016e8c`

## pseudocode

```c
char __fastcall UmpopRegistryMatchPowerRequestOverride(HKEY hKey, wchar_t *Str, _DWORD *a3)
{
  HKEY v5; // r12
  char v6; // bl
  WCHAR *Heap; // r15
  BYTE *lpData; // rsi
  wchar_t *v9; // rax
  wchar_t *v10; // rdi
  DWORD v11; // r14d
  LSTATUS v12; // r12d
  int v13; // ecx
  DWORD v15; // [rsp+60h] [rbp-10h] BYREF
  DWORD cchValueName; // [rsp+64h] [rbp-Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-8h] BYREF
  SIZE_T Size; // [rsp+C8h] [rbp+58h] BYREF

  cbData = 0;
  v5 = hKey;
  v6 = 0;
  cchValueName = 0;
  v15 = 0;
  LODWORD(Size) = 0;
  if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, &v15, (LPDWORD)&Size, 0, 0) )
  {
    cchValueName = 2 * v15 + 2;
    Heap = (WCHAR *)RtlAllocateHeap(UmpoHeapHandle, 8u, cchValueName);
    if ( Heap )
    {
      lpData = 0;
      if ( (unsigned int)Size >= 4 )
      {
        lpData = (BYTE *)RtlAllocateHeap(UmpoHeapHandle, 8u, (unsigned int)Size);
        if ( lpData )
        {
          v9 = wcsrchr(Str, 0x5Cu);
          if ( v9 )
            v10 = v9 + 1;
          else
            v10 = Str;
          v11 = 0;
          while ( 1 )
          {
            cbData = Size;
            cchValueName = v15 + 1;
            v12 = RegEnumValueW(v5, v11, Heap, &cchValueName, 0, 0, lpData, &cbData);
            if ( !v12 && cbData == 4 && !(unsigned int)_o__wcsicmp(v10) )
              break;
            v13 = 0;
            v6 = 0;
            ++v11;
            if ( v12 )
              goto LABEL_15;
            v5 = hKey;
          }
          v13 = *(_DWORD *)lpData;
          v6 = 1;
LABEL_15:
          *a3 = v13;
        }
      }
      RtlFreeHeap(UmpoHeapHandle, 0, Heap);
      if ( lpData )
        RtlFreeHeap(UmpoHeapHandle, 0, lpData);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180016e24  mov     r11, rsp
0x180016e27  mov     [r11+10h], rbx
0x180016e2b  mov     [r11+8], rcx
0x180016e2f  push    rbp
0x180016e30  push    rsi
0x180016e31  push    rdi
0x180016e32  push    r12
0x180016e34  push    r13
0x180016e36  push    r14
0x180016e38  push    r15
0x180016e3a  mov     rbp, rsp
0x180016e3d  sub     rsp, 70h
0x180016e41  xor     edi, edi
0x180016e43  lea     rax, [rbp+Size]
0x180016e47  mov     [r11-50h], rdi
0x180016e4b  mov     r13, r8
0x180016e4e  mov     [r11-58h], rdi
0x180016e52  mov     r14, rdx
0x180016e55  mov     [r11-60h], rax
0x180016e59  xor     r9d, r9d; lpReserved
0x180016e5c  lea     rax, [rbp+var_10]
0x180016e60  mov     [rbp+cbData], edi
0x180016e63  mov     [r11-68h], rax
0x180016e67  xor     r8d, r8d; lpcchClass
0x180016e6a  mov     [r11-70h], rdi
0x180016e6e  xor     edx, edx; lpClass
0x180016e70  mov     [r11-78h], rdi
0x180016e74  mov     r12, rcx
0x180016e77  mov     [r11-80h], rdi
0x180016e7b  mov     bl, dil
0x180016e7e  mov     [rsp+70h+lpcSubKeys], rdi; lpcSubKeys
0x180016e83  mov     [rbp+cchValueName], edi
0x180016e86  mov     [rbp+var_10], edi
0x180016e89  mov     dword ptr [rbp+Size], edi
0x180016e8c  call    cs:__imp_RegQueryInfoKeyW
0x180016e92  test    eax, eax
0x180016e94  jnz     loc_180016FB3
0x180016e9a  mov     eax, [rbp+var_10]
0x180016e9d  lea     edx, [rdi+8]; Flags
0x180016ea0  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180016ea7  lea     eax, ds:2[rax*2]
0x180016eae  mov     r8d, eax; Size
0x180016eb1  mov     [rbp+cchValueName], eax
0x180016eb4  call    cs:__imp_RtlAllocateHeap
0x180016eba  mov     r15, rax
0x180016ebd  test    rax, rax
0x180016ec0  jz      loc_180016FB3
0x180016ec6  cmp     dword ptr [rbp+Size], 4
0x180016eca  mov     esi, edi
0x180016ecc  jb      loc_180016F8A
0x180016ed2  mov     r8d, dword ptr [rbp+Size]; Size
0x180016ed6  lea     edx, [rdi+8]; Flags
0x180016ed9  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180016ee0  call    cs:__imp_RtlAllocateHeap
0x180016ee6  mov     rsi, rax
0x180016ee9  test    rax, rax
0x180016eec  jz      loc_180016F8A
0x180016ef2  lea     edx, [rdi+5Ch]; Ch
0x180016ef5  mov     rcx, r14; Str
0x180016ef8  call    cs:__imp_wcsrchr
0x180016efe  mov     rdi, rax
0x180016f01  test    rax, rax
0x180016f04  jnz     short loc_180016F0B
0x180016f06  mov     rdi, r14
0x180016f09  jmp     short loc_180016F0F
0x180016f0b  add     rdi, 2
0x180016f0f  xor     r14d, r14d
0x180016f12  mov     eax, dword ptr [rbp+Size]
0x180016f15  lea     r9, [rbp+cchValueName]; lpcchValueName
0x180016f19  mov     [rbp+cbData], eax
0x180016f1c  mov     r8, r15; lpValueName
0x180016f1f  mov     eax, [rbp+var_10]
0x180016f22  mov     edx, r14d; dwIndex
0x180016f25  inc     eax
0x180016f27  mov     rcx, r12; hKey
0x180016f2a  mov     [rbp+cchValueName], eax
0x180016f2d  lea     rax, [rbp+cbData]
0x180016f31  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180016f36  mov     [rsp+70h+lpData], rsi; lpData
0x180016f3b  mov     [rsp+70h+lpType], 0; lpType
0x180016f44  mov     [rsp+70h+lpcSubKeys], 0; lpReserved
0x180016f4d  call    cs:__imp_RegEnumValueW
0x180016f53  mov     r12d, eax
0x180016f56  test    eax, eax
0x180016f58  jnz     short loc_180016F70
0x180016f5a  cmp     [rbp+cbData], 4
0x180016f5e  jnz     short loc_180016F70
0x180016f60  mov     rdx, r15
0x180016f63  mov     rcx, rdi
0x180016f66  call    cs:__imp__o__wcsicmp
0x180016f6c  test    eax, eax
0x180016f6e  jz      short loc_180016F82
0x180016f70  xor     ecx, ecx
0x180016f72  xor     bl, bl
0x180016f74  inc     r14d
0x180016f77  test    r12d, r12d
0x180016f7a  jnz     short loc_180016F86
0x180016f7c  mov     r12, [rbp+arg_0]
0x180016f80  jmp     short loc_180016F12
0x180016f82  mov     ecx, [rsi]
0x180016f84  mov     bl, 1
0x180016f86  mov     [r13+0], ecx
0x180016f8a  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180016f91  mov     r8, r15; P
0x180016f94  xor     edx, edx; Flags
0x180016f96  call    cs:__imp_RtlFreeHeap
0x180016f9c  test    rsi, rsi
0x180016f9f  jz      short loc_180016FB3
0x180016fa1  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180016fa8  mov     r8, rsi; P
0x180016fab  xor     edx, edx; Flags
0x180016fad  call    cs:__imp_RtlFreeHeap
0x180016fb3  mov     al, bl
0x180016fb5  mov     rbx, [rsp+70h+arg_8]
0x180016fbd  add     rsp, 70h
0x180016fc1  pop     r15
0x180016fc3  pop     r14
0x180016fc5  pop     r13
0x180016fc7  pop     r12
0x180016fc9  pop     rdi
0x180016fca  pop     rsi
0x180016fcb  pop     rbp
0x180016fcc  retn
```
