# RegOpenConnectionKey(HKEY__ *,ushort *,HKEY__ * *)

- ea: `0x140002070`
- end: `0x1400021e8`
- name: `?RegOpenConnectionKey@@YAKPEAUHKEY__@@PEAGPEAPEAU1@@Z`
- size: `376`
- prototype: `unsigned int __fastcall(HKEY hKey, unsigned __int16 *, PHKEY phkResult)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400038f0`
- `0x140004e90`
- `0x140005c30`
- `0x14006bbc8`

## callees

- `0x140002070`
- `0x14000c490`
- `0x1400140cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400021c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400021c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400020cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400020cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400020ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400020ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400020e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400020e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400021b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400021b2`

## string_xrefs

- `0x1400020f3`: `DllAllocSplMem`

## pseudocode

```c
DWORD __fastcall RegOpenConnectionKey(HKEY hKey, unsigned __int16 *a2, PHKEY phkResult)
{
  unsigned __int64 v6; // rax
  _WORD *v7; // rdi
  __int64 v9; // rax
  const unsigned __int16 *v10; // r8
  __int64 v11; // rdx
  _WORD *v12; // rcx
  _WORD *v13; // rax
  unsigned __int16 *v14; // r10
  unsigned __int16 i; // ax
  LSTATUS v16; // ebx

  if ( !a2 )
    return 87;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 >= 0x21B )
    return 87;
  v7 = HeapAlloc(g_hSpoolssHeap, 8u, 0x462u);
  if ( v7 )
  {
    v9 = 2147483646;
    v10 = L"Printers\\Connections\\";
    v11 = 561;
    v12 = v7;
    do
    {
      if ( !v9 )
        break;
      if ( !*v10 )
        break;
      *v12++ = *v10++;
      --v9;
      --v11;
    }
    while ( v11 );
    v13 = v12 - 1;
    v14 = v7 + 21;
    if ( v11 )
      v13 = v12;
    *v13 = 0;
    if ( v14 != a2 )
      StringCchCopyW(v7 + 21, 0x21Cu, a2);
    for ( i = *v14; i; ++v14 )
    {
      if ( i == 92 )
        *v14 = 44;
      i = v14[1];
    }
    v16 = RegOpenKeyExW(hKey, v7, 0, 0x2001Fu, phkResult);
    HeapFree(g_hSpoolssHeap, 0, v7);
    return v16;
  }
  else
  {
    SetLastError(8u);
    PrvSpoolssTelemetry::WriteDbgTraceError("DllAllocSplMem", L"Unable to allocate %d bytes of memory on heap.", 1122);
    return GetLastError();
  }
}

```

## disassembly

```asm
0x140002070  mov     [rsp+arg_8], rbx
0x140002075  mov     [rsp+arg_10], rbp
0x14000207a  push    rsi
0x14000207b  sub     rsp, 30h
0x14000207f  mov     rsi, r8
0x140002082  mov     rbx, rdx
0x140002085  mov     rbp, rcx
0x140002088  test    rdx, rdx
0x14000208b  jz      loc_1400021D3
0x140002091  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140002098  nop     dword ptr [rax+rax+00000000h]
0x1400020a0  inc     rax
0x1400020a3  cmp     word ptr [rdx+rax*2], 0
0x1400020a8  jnz     short loc_1400020A0
0x1400020aa  cmp     rax, 21Bh
0x1400020b0  jnb     loc_1400021D3
0x1400020b6  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x1400020bd  mov     edx, 8; dwFlags
0x1400020c2  mov     r8d, 462h; dwBytes
0x1400020c8  mov     [rsp+38h+arg_0], rdi
0x1400020cd  call    cs:__imp_HeapAlloc
0x1400020d3  mov     rdi, rax
0x1400020d6  test    rax, rax
0x1400020d9  jnz     short loc_14000211A
0x1400020db  mov     ecx, 8; dwErrCode
0x1400020e0  call    cs:__imp_SetLastError
0x1400020e6  mov     r8d, 462h
0x1400020ec  lea     rdx, aUnableToAlloca; "Unable to allocate %d bytes of memory o"...
0x1400020f3  lea     rcx, aDllallocsplmem; "DllAllocSplMem"
0x1400020fa  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400020ff  call    cs:__imp_GetLastError
0x140002105  mov     rdi, [rsp+38h+arg_0]
0x14000210a  mov     rbx, [rsp+38h+arg_8]
0x14000210f  mov     rbp, [rsp+38h+arg_10]
0x140002114  add     rsp, 30h
0x140002118  pop     rsi
0x140002119  retn
0x14000211a  mov     eax, 7FFFFFFEh
0x14000211f  lea     r8, gszPrinterConnections; "Printers\\Connections\\"
0x140002126  mov     edx, 231h
0x14000212b  mov     rcx, rdi
0x14000212e  test    rax, rax
0x140002131  jz      short loc_140002152
0x140002133  movzx   r9d, word ptr [r8]
0x140002137  test    r9w, r9w
0x14000213b  jz      short loc_140002152
0x14000213d  mov     [rcx], r9w
0x140002141  add     r8, 2
0x140002145  add     rcx, 2
0x140002149  dec     rax
0x14000214c  sub     rdx, 1
0x140002150  jnz     short loc_14000212E
0x140002152  test    rdx, rdx
0x140002155  lea     rax, [rcx-2]
0x140002159  lea     r10, [rdi+2Ah]
0x14000215d  cmovnz  rax, rcx
0x140002161  xor     ecx, ecx
0x140002163  mov     [rax], cx
0x140002166  cmp     r10, rbx
0x140002169  jz      short loc_14000217B
0x14000216b  mov     r8, rbx; unsigned __int16 *
0x14000216e  mov     edx, 21Ch; unsigned __int64
0x140002173  mov     rcx, r10; unsigned __int16 *
0x140002176  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000217b  movzx   eax, word ptr [r10]
0x14000217f  test    ax, ax
0x140002182  jz      short loc_14000219E
0x140002184  cmp     ax, 5Ch ; '\'
0x140002188  jnz     short loc_140002190
0x14000218a  mov     word ptr [r10], 2Ch ; ','
0x140002190  movzx   eax, word ptr [r10+2]
0x140002195  add     r10, 2
0x140002199  test    ax, ax
0x14000219c  jnz     short loc_140002184
0x14000219e  mov     r9d, 2001Fh; samDesired
0x1400021a4  mov     [rsp+38h+phkResult], rsi; phkResult
0x1400021a9  xor     r8d, r8d; ulOptions
0x1400021ac  mov     rdx, rdi; lpSubKey
0x1400021af  mov     rcx, rbp; hKey
0x1400021b2  call    cs:__imp_RegOpenKeyExW
0x1400021b8  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x1400021bf  mov     r8, rdi; lpMem
0x1400021c2  xor     edx, edx; dwFlags
0x1400021c4  mov     ebx, eax
0x1400021c6  call    cs:__imp_HeapFree
0x1400021cc  mov     eax, ebx
0x1400021ce  jmp     loc_140002105
0x1400021d3  mov     rbx, [rsp+38h+arg_8]
0x1400021d8  mov     eax, 57h ; 'W'
0x1400021dd  mov     rbp, [rsp+38h+arg_10]
0x1400021e2  add     rsp, 30h
0x1400021e6  pop     rsi
0x1400021e7  retn
```
