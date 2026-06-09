# QuerySingleServiceHeapInformation

- ea: `0x140001180`
- end: `0x140001271`
- name: `QuerySingleServiceHeapInformation`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x140001070`
- `0x140001120`

## callees

- `0x140001180`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400011b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400011b3`
- `ntdll!RtlQueryHeapInformation` at `0x1400011fc`
- `ntdll!RtlQueryHeapInformation` at `0x1400011fc`

## pseudocode

```c
NTSTATUS QuerySingleServiceHeapInformation()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // r10d
  __int64 v2; // rcx
  unsigned __int64 v3; // r9
  __int64 v4; // rax
  unsigned __int64 v5; // r8
  __int128 HeapInformation; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v7; // [rsp+40h] [rbp-58h]
  int v8; // [rsp+44h] [rbp-54h]
  __int64 (__fastcall *v9)(); // [rsp+48h] [rbp-50h]
  __int128 v10; // [rsp+50h] [rbp-48h]
  __int128 v11; // [rsp+60h] [rbp-38h]
  __int128 v12; // [rsp+70h] [rbp-28h]
  __int64 v13; // [rsp+80h] [rbp-18h]
  unsigned __int64 v14; // [rsp+A0h] [rbp+8h] BYREF

  HeapInformation = 0;
  v8 = 0;
  v14 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v7 = 0x80000000;
  *(_QWORD *)&HeapInformation = GetCurrentProcess();
  v9 = QueryHeapCallback;
  *(_QWORD *)&v10 = &v14;
  result = RtlQueryHeapInformation(0, (HEAP_INFORMATION_CLASS)2, &HeapInformation, 0x58u, 0);
  v1 = result;
  if ( result >= 0 )
  {
    v2 = ServiceArray;
    v3 = v14;
    v4 = *(_QWORD *)(ServiceArray + 64);
    if ( v4 )
      v5 = 20 * (v14 + 4 * v4) / 0x64;
    else
      v5 = v14;
    *(_QWORD *)(ServiceArray + 64) = v5;
    if ( *(_QWORD *)(v2 + 56) < v3 )
      *(_QWORD *)(v2 + 56) = v3;
    *(_QWORD *)(v2 + 72) = v3;
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x140001180  mov     r11, rsp
0x140001183  push    rbx
0x140001184  sub     rsp, 90h
0x14000118b  xorps   xmm0, xmm0
0x14000118e  xor     eax, eax
0x140001190  movups  [rsp+98h+HeapInformation], xmm0
0x140001195  xor     ebx, ebx
0x140001197  movups  [rsp+98h+var_58], xmm0
0x14000119c  mov     [r11+8], rbx
0x1400011a0  movups  [rsp+98h+var_48], xmm0
0x1400011a5  movups  [rsp+98h+var_38], xmm0
0x1400011aa  movups  [rsp+98h+var_28], xmm0
0x1400011af  mov     [r11-18h], rax
0x1400011b3  call    cs:__imp_GetCurrentProcess
0x1400011ba  nop     dword ptr [rax+rax+00h]
0x1400011bf  mov     r9d, 58h ; 'X'; HeapInformationLength
0x1400011c5  mov     dword ptr [rsp+98h+var_58], 80000000h
0x1400011cd  mov     qword ptr [rsp+98h+HeapInformation], rax
0x1400011d2  lea     r8, [rsp+98h+HeapInformation]; HeapInformation
0x1400011d7  lea     rax, QueryHeapCallback
0x1400011de  mov     [rsp+98h+ReturnLength], rbx; ReturnLength
0x1400011e3  mov     qword ptr [rsp+98h+var_58+8], rax
0x1400011e8  mov     edx, 2; HeapInformationClass
0x1400011ed  lea     rax, [rsp+98h+arg_0]
0x1400011f5  xor     ecx, ecx; HeapHandle
0x1400011f7  mov     qword ptr [rsp+98h+var_48], rax
0x1400011fc  call    cs:__imp_RtlQueryHeapInformation
0x140001203  nop     dword ptr [rax+rax+00h]
0x140001208  mov     r10d, eax
0x14000120b  test    eax, eax
0x14000120d  js      short loc_140001262
0x14000120f  mov     rcx, cs:ServiceArray
0x140001216  mov     r9, [rsp+98h+arg_0]
0x14000121e  mov     rax, [rcx+40h]
0x140001222  test    rax, rax
0x140001225  jz      short loc_14000126C
0x140001227  lea     rax, [r9+rax*4]
0x14000122b  lea     r8, [rax+rax*4]
0x14000122f  mov     rax, 47AE147AE147AE15h
0x140001239  shl     r8, 2
0x14000123d  mul     r8
0x140001240  sub     r8, rdx
0x140001243  shr     r8, 1
0x140001246  add     r8, rdx
0x140001249  shr     r8, 6
0x14000124d  mov     [rcx+40h], r8
0x140001251  cmp     [rcx+38h], r9
0x140001255  jnb     short loc_14000125B
0x140001257  mov     [rcx+38h], r9
0x14000125b  mov     [rcx+48h], r9
0x14000125f  mov     eax, r10d
0x140001262  add     rsp, 90h
0x140001269  pop     rbx
0x14000126a  retn
0x14000126c  mov     r8, r9
0x14000126f  jmp     short loc_14000124D
```
