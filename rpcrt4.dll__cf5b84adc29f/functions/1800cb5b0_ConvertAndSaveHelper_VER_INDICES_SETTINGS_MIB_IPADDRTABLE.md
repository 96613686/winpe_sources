# ConvertAndSaveHelper(VER_INDICES_SETTINGS *,_MIB_IPADDRTABLE *)

- ea: `0x1800cb5b0`
- end: `0x1800cb708`
- name: `?ConvertAndSaveHelper@@YAHPEAUVER_INDICES_SETTINGS@@PEAU_MIB_IPADDRTABLE@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(struct VER_INDICES_SETTINGS *, struct _MIB_IPADDRTABLE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800a086c`

## callees

- `0x180023020`
- `0x180023a40`
- `0x1800cb5b0`
- `0x1800cc458`
- `0x1800cec91`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cb6af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cb6af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cb6e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cb6e2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800cb6d1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800cb6d1`

## string_xrefs

- `0x1800cb6a1`: `System\CurrentControlSet\Services\Rpc`
- `0x1800cb6c4`: `Linkage`

## pseudocode

```c
LPVOID __fastcall ConvertAndSaveHelper(struct VER_INDICES_SETTINGS *a1, struct _MIB_IPADDRTABLE *a2)
{
  LPVOID result; // rax
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
    return (LPVOID)(v12 == 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800cb5b0  push    rbx
0x1800cb5b2  push    rsi
0x1800cb5b3  push    rdi
0x1800cb5b4  push    r14
0x1800cb5b6  sub     rsp, 38h
0x1800cb5ba  mov     r8d, [rdx]
0x1800cb5bd  mov     rsi, rcx
0x1800cb5c0  mov     rdi, rdx
0x1800cb5c3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800cb5ca  mov     eax, 4
0x1800cb5cf  mul     r8
0x1800cb5d2  cmovb   rax, rcx
0x1800cb5d6  mov     rcx, rax; dwBytes
0x1800cb5d9  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800cb5de  mov     r14, rax
0x1800cb5e1  test    rax, rax
0x1800cb5e4  jz      loc_1800CB6FD
0x1800cb5ea  xor     ebx, ebx
0x1800cb5ec  xor     edx, edx
0x1800cb5ee  cmp     [rdi], edx
0x1800cb5f0  jbe     loc_1800CB687
0x1800cb5f6  lea     r9, [rdx+rdx*2]
0x1800cb5fa  xor     r8d, r8d
0x1800cb5fd  cmp     r8d, [rsi]
0x1800cb600  jnb     short loc_1800CB622
0x1800cb602  mov     ecx, [rsi+r8*4+4]
0x1800cb607  cmp     [rdi+r9*8+8], ecx
0x1800cb60c  jz      short loc_1800CB613
0x1800cb60e  inc     r8d
0x1800cb611  jmp     short loc_1800CB5FD
0x1800cb613  mov     ecx, [rdi+r9*8+0Ch]
0x1800cb618  and     ecx, [rdi+r9*8+4]
0x1800cb61d  mov     [rax+rbx*4], ecx
0x1800cb620  inc     ebx
0x1800cb622  inc     edx
0x1800cb624  cmp     edx, [rdi]
0x1800cb626  jb      short loc_1800CB5F6
0x1800cb628  test    ebx, ebx
0x1800cb62a  jz      short loc_1800CB687
0x1800cb62c  lea     esi, ds:0Ch[rbx*4]
0x1800cb633  cmp     esi, 0Ch
0x1800cb636  jb      short loc_1800CB680
0x1800cb638  mov     ecx, esi; dwBytes
0x1800cb63a  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800cb63f  mov     rdi, rax
0x1800cb642  test    rax, rax
0x1800cb645  jz      short loc_1800CB680
0x1800cb647  mov     r8d, ebx
0x1800cb64a  lea     rcx, [rax+0Ch]; void *
0x1800cb64e  shl     r8, 2; Size
0x1800cb652  mov     rdx, r14; Src
0x1800cb655  mov     dword ptr [rax], 34765049h
0x1800cb65b  mov     [rax+8], ebx
0x1800cb65e  mov     dword ptr [rax+4], 1
0x1800cb665  call    memcpy_0
0x1800cb66a  mov     rdx, rdi; lpData
0x1800cb66d  mov     ecx, esi; cbData
0x1800cb66f  call    ?SetSelectiveBindingBuffer@@YAKKPEAX@Z; SetSelectiveBindingBuffer(ulong,void *)
0x1800cb674  mov     rcx, rdi; lpMem
0x1800cb677  mov     ebx, eax
0x1800cb679  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800cb67e  jmp     short loc_1800CB6EE
0x1800cb680  mov     ebx, 0Eh
0x1800cb685  jmp     short loc_1800CB6EE
0x1800cb687  lea     rax, [rsp+58h+hKey]
0x1800cb68c  xor     ebx, ebx
0x1800cb68e  mov     r9d, 0F003Fh; samDesired
0x1800cb694  mov     [rsp+58h+hKey], rbx
0x1800cb699  xor     r8d, r8d; ulOptions
0x1800cb69c  mov     [rsp+58h+phkResult], rax; phkResult
0x1800cb6a1  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Rp"...
0x1800cb6a8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cb6af  call    cs:__imp_RegOpenKeyExA
0x1800cb6b6  nop     dword ptr [rax+rax+00h]
0x1800cb6bb  test    eax, eax
0x1800cb6bd  jnz     short loc_1800CB6EE
0x1800cb6bf  mov     rcx, [rsp+58h+hKey]; hKey
0x1800cb6c4  lea     rdx, aLinkage; "Linkage"
0x1800cb6cb  xor     r9d, r9d; Reserved
0x1800cb6ce  xor     r8d, r8d; samDesired
0x1800cb6d1  call    cs:__imp_RegDeleteKeyExA
0x1800cb6d8  nop     dword ptr [rax+rax+00h]
0x1800cb6dd  mov     rcx, [rsp+58h+hKey]; hKey
0x1800cb6e2  call    cs:__imp_RegCloseKey
0x1800cb6e9  nop     dword ptr [rax+rax+00h]
0x1800cb6ee  mov     rcx, r14; lpMem
0x1800cb6f1  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800cb6f6  xor     eax, eax
0x1800cb6f8  test    ebx, ebx
0x1800cb6fa  setz    al
0x1800cb6fd  add     rsp, 38h
0x1800cb701  pop     r14
0x1800cb703  pop     rdi
0x1800cb704  pop     rsi
0x1800cb705  pop     rbx
0x1800cb706  retn
```
