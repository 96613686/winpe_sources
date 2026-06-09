# ConvertAndSaveHelper(VER_INDICES_SETTINGS *,_MIB_IPADDRTABLE *)

- ea: `0x1800c6b10`
- end: `0x1800c6c55`
- name: `?ConvertAndSaveHelper@@YAHPEAUVER_INDICES_SETTINGS@@PEAU_MIB_IPADDRTABLE@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(struct VER_INDICES_SETTINGS *, struct _MIB_IPADDRTABLE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18009d010`

## callees

- `0x180021e70`
- `0x180022870`
- `0x1800c6b10`
- `0x1800c78fc`
- `0x1800ca031`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c6c0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c6c0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c6c36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c6c36`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800c6c2b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800c6c2b`

## string_xrefs

- `0x1800c6c01`: `System\CurrentControlSet\Services\Rpc`
- `0x1800c6c1e`: `Linkage`

## pseudocode

```c
void *__fastcall ConvertAndSaveHelper(struct VER_INDICES_SETTINGS *a1, struct _MIB_IPADDRTABLE *a2)
{
  void *result; // rax
  void *v5; // r14
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 i; // r8
  DWORD v9; // esi
  BYTE *v10; // rax
  BYTE *v11; // rdi
  unsigned int v12; // ebx
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  result = AllocWrapper(saturated_mul(a2->dwNumEntries, 4u));
  v5 = result;
  if ( result )
  {
    v6 = 0;
    v7 = 0;
    if ( !a2->dwNumEntries )
      goto LABEL_14;
    do
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)a1; i = (unsigned int)(i + 1) )
      {
        if ( a2->table[v7].dwIndex == *((_DWORD *)a1 + i + 1) )
        {
          *((_DWORD *)result + v6) = a2->table[v7].dwAddr & a2->table[v7].dwMask;
          v6 = (unsigned int)(v6 + 1);
          break;
        }
      }
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (unsigned int)v7 < a2->dwNumEntries );
    if ( (_DWORD)v6 )
    {
      v9 = 4 * v6 + 12;
      if ( (unsigned int)(4 * v6) < 0xFFFFFFF4 && (v10 = (BYTE *)AllocWrapper(v9), (v11 = v10) != 0) )
      {
        *(_DWORD *)v10 = 880169033;
        *((_DWORD *)v10 + 2) = v6;
        *((_DWORD *)v10 + 1) = 1;
        memcpy_0(v10 + 12, v5, 4LL * (unsigned int)v6);
        v12 = SetSelectiveBindingBuffer(v9, v11);
        FreeWrapper(v11);
      }
      else
      {
        v12 = 14;
      }
    }
    else
    {
LABEL_14:
      v12 = 0;
      hKey = 0;
      if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\Rpc", 0, 0xF003Fu, &hKey) )
      {
        RegDeleteKeyExA(hKey, "Linkage", 0, 0);
        RegCloseKey(hKey);
      }
    }
    FreeWrapper(v5);
    return (void *)(v12 == 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800c6b10  push    rbx
0x1800c6b12  push    rsi
0x1800c6b13  push    rdi
0x1800c6b14  push    r14
0x1800c6b16  sub     rsp, 38h
0x1800c6b1a  mov     r8d, [rdx]
0x1800c6b1d  mov     rsi, rcx
0x1800c6b20  mov     rdi, rdx
0x1800c6b23  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c6b2a  mov     eax, 4
0x1800c6b2f  mul     r8
0x1800c6b32  cmovb   rax, rcx
0x1800c6b36  mov     rcx, rax; dwBytes
0x1800c6b39  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800c6b3e  mov     r14, rax
0x1800c6b41  test    rax, rax
0x1800c6b44  jz      loc_1800C6C4B
0x1800c6b4a  xor     ebx, ebx
0x1800c6b4c  xor     edx, edx
0x1800c6b4e  cmp     [rdi], edx
0x1800c6b50  jbe     loc_1800C6BE7
0x1800c6b56  lea     r9, [rdx+rdx*2]
0x1800c6b5a  xor     r8d, r8d
0x1800c6b5d  cmp     r8d, [rsi]
0x1800c6b60  jnb     short loc_1800C6B82
0x1800c6b62  mov     ecx, [rsi+r8*4+4]
0x1800c6b67  cmp     [rdi+r9*8+8], ecx
0x1800c6b6c  jz      short loc_1800C6B73
0x1800c6b6e  inc     r8d
0x1800c6b71  jmp     short loc_1800C6B5D
0x1800c6b73  mov     ecx, [rdi+r9*8+0Ch]
0x1800c6b78  and     ecx, [rdi+r9*8+4]
0x1800c6b7d  mov     [rax+rbx*4], ecx
0x1800c6b80  inc     ebx
0x1800c6b82  inc     edx
0x1800c6b84  cmp     edx, [rdi]
0x1800c6b86  jb      short loc_1800C6B56
0x1800c6b88  test    ebx, ebx
0x1800c6b8a  jz      short loc_1800C6BE7
0x1800c6b8c  lea     esi, ds:0Ch[rbx*4]
0x1800c6b93  cmp     esi, 0Ch
0x1800c6b96  jb      short loc_1800C6BE0
0x1800c6b98  mov     ecx, esi; dwBytes
0x1800c6b9a  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800c6b9f  mov     rdi, rax
0x1800c6ba2  test    rax, rax
0x1800c6ba5  jz      short loc_1800C6BE0
0x1800c6ba7  mov     r8d, ebx
0x1800c6baa  lea     rcx, [rax+0Ch]; void *
0x1800c6bae  shl     r8, 2; Size
0x1800c6bb2  mov     rdx, r14; Src
0x1800c6bb5  mov     dword ptr [rax], 34765049h
0x1800c6bbb  mov     [rax+8], ebx
0x1800c6bbe  mov     dword ptr [rax+4], 1
0x1800c6bc5  call    memcpy_0
0x1800c6bca  mov     rdx, rdi; lpData
0x1800c6bcd  mov     ecx, esi; cbData
0x1800c6bcf  call    ?SetSelectiveBindingBuffer@@YAKKPEAX@Z; SetSelectiveBindingBuffer(ulong,void *)
0x1800c6bd4  mov     rcx, rdi; lpMem
0x1800c6bd7  mov     ebx, eax
0x1800c6bd9  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800c6bde  jmp     short loc_1800C6C3C
0x1800c6be0  mov     ebx, 0Eh
0x1800c6be5  jmp     short loc_1800C6C3C
0x1800c6be7  lea     rax, [rsp+58h+hKey]
0x1800c6bec  xor     ebx, ebx
0x1800c6bee  mov     r9d, 0F003Fh; samDesired
0x1800c6bf4  mov     [rsp+58h+hKey], rbx
0x1800c6bf9  xor     r8d, r8d; ulOptions
0x1800c6bfc  mov     [rsp+58h+phkResult], rax; phkResult
0x1800c6c01  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Rp"...
0x1800c6c08  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c6c0f  call    cs:__imp_RegOpenKeyExA
0x1800c6c15  test    eax, eax
0x1800c6c17  jnz     short loc_1800C6C3C
0x1800c6c19  mov     rcx, [rsp+58h+hKey]; hKey
0x1800c6c1e  lea     rdx, aLinkage; "Linkage"
0x1800c6c25  xor     r9d, r9d; Reserved
0x1800c6c28  xor     r8d, r8d; samDesired
0x1800c6c2b  call    cs:__imp_RegDeleteKeyExA
0x1800c6c31  mov     rcx, [rsp+58h+hKey]; hKey
0x1800c6c36  call    cs:__imp_RegCloseKey
0x1800c6c3c  mov     rcx, r14; lpMem
0x1800c6c3f  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800c6c44  xor     eax, eax
0x1800c6c46  test    ebx, ebx
0x1800c6c48  setz    al
0x1800c6c4b  add     rsp, 38h
0x1800c6c4f  pop     r14
0x1800c6c51  pop     rdi
0x1800c6c52  pop     rsi
0x1800c6c53  pop     rbx
0x1800c6c54  retn
```
