# QuerySingleServiceHeapInformation

- ea: `0x140001160`
- end: `0x140001244`
- name: `QuerySingleServiceHeapInformation`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x140001070`
- `0x140001110`

## callees

- `0x140001160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001193`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001193`
- `ntdll!RtlQueryHeapInformation` at `0x1400011d6`
- `ntdll!RtlQueryHeapInformation` at `0x1400011d6`

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
0x140001160  mov     r11, rsp
0x140001163  push    rbx
0x140001164  sub     rsp, 90h
0x14000116b  xorps   xmm0, xmm0
0x14000116e  xor     eax, eax
0x140001170  movups  [rsp+98h+HeapInformation], xmm0
0x140001175  xor     ebx, ebx
0x140001177  movups  [rsp+98h+var_58], xmm0
0x14000117c  mov     [r11+8], rbx
0x140001180  movups  [rsp+98h+var_48], xmm0
0x140001185  movups  [rsp+98h+var_38], xmm0
0x14000118a  movups  [rsp+98h+var_28], xmm0
0x14000118f  mov     [r11-18h], rax
0x140001193  call    cs:__imp_GetCurrentProcess
0x140001199  mov     r9d, 58h ; 'X'; HeapInformationLength
0x14000119f  mov     dword ptr [rsp+98h+var_58], 80000000h
0x1400011a7  mov     qword ptr [rsp+98h+HeapInformation], rax
0x1400011ac  lea     r8, [rsp+98h+HeapInformation]; HeapInformation
0x1400011b1  lea     rax, QueryHeapCallback
0x1400011b8  mov     [rsp+98h+ReturnLength], rbx; ReturnLength
0x1400011bd  mov     qword ptr [rsp+98h+var_58+8], rax
0x1400011c2  mov     edx, 2; HeapInformationClass
0x1400011c7  lea     rax, [rsp+98h+arg_0]
0x1400011cf  xor     ecx, ecx; HeapHandle
0x1400011d1  mov     qword ptr [rsp+98h+var_48], rax
0x1400011d6  call    cs:__imp_RtlQueryHeapInformation
0x1400011dc  mov     r10d, eax
0x1400011df  test    eax, eax
0x1400011e1  js      short loc_140001236
0x1400011e3  mov     rcx, cs:ServiceArray
0x1400011ea  mov     r9, [rsp+98h+arg_0]
0x1400011f2  mov     rax, [rcx+40h]
0x1400011f6  test    rax, rax
0x1400011f9  jz      short loc_14000123F
0x1400011fb  lea     rax, [r9+rax*4]
0x1400011ff  lea     r8, [rax+rax*4]
0x140001203  mov     rax, 47AE147AE147AE15h
0x14000120d  shl     r8, 2
0x140001211  mul     r8
0x140001214  sub     r8, rdx
0x140001217  shr     r8, 1
0x14000121a  add     r8, rdx
0x14000121d  shr     r8, 6
0x140001221  mov     [rcx+40h], r8
0x140001225  cmp     [rcx+38h], r9
0x140001229  jnb     short loc_14000122F
0x14000122b  mov     [rcx+38h], r9
0x14000122f  mov     [rcx+48h], r9
0x140001233  mov     eax, r10d
0x140001236  add     rsp, 90h
0x14000123d  pop     rbx
0x14000123e  retn
0x14000123f  mov     r8, r9
0x140001242  jmp     short loc_140001221
```
