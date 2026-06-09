# RegOpenConnectionKey(HKEY__ *,ushort *,HKEY__ * *)

- ea: `0x140002c80`
- end: `0x140002e18`
- name: `?RegOpenConnectionKey@@YAKPEAUHKEY__@@PEAGPEAPEAU1@@Z`
- size: `408`
- prototype: `unsigned int __fastcall(HKEY hKey, unsigned __int16 *, PHKEY phkResult)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400043e0`
- `0x140005630`
- `0x1400065e0`
- `0x1400727d8`

## callees

- `0x140002c80`
- `0x14000d450`
- `0x140015378`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002def`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002def`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140002cdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140002cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002cf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002cf6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002dd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002dd5`

## string_xrefs

- `0x140002d0f`: `DllAllocSplMem`

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
0x140002c80  mov     [rsp+arg_8], rbx
0x140002c85  mov     [rsp+arg_10], rbp
0x140002c8a  push    rsi
0x140002c8b  sub     rsp, 30h
0x140002c8f  mov     rsi, r8
0x140002c92  mov     rbx, rdx
0x140002c95  mov     rbp, rcx
0x140002c98  test    rdx, rdx
0x140002c9b  jz      loc_140002E02
0x140002ca1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140002ca8  nop     dword ptr [rax+rax+00000000h]
0x140002cb0  inc     rax
0x140002cb3  cmp     word ptr [rdx+rax*2], 0
0x140002cb8  jnz     short loc_140002CB0
0x140002cba  cmp     rax, 21Bh
0x140002cc0  jnb     loc_140002E02
0x140002cc6  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140002ccd  mov     edx, 8; dwFlags
0x140002cd2  mov     r8d, 462h; dwBytes
0x140002cd8  mov     [rsp+38h+arg_0], rdi
0x140002cdd  call    cs:__imp_HeapAlloc
0x140002ce4  nop     dword ptr [rax+rax+00h]
0x140002ce9  mov     rdi, rax
0x140002cec  test    rax, rax
0x140002cef  jnz     short loc_140002D3D
0x140002cf1  mov     ecx, 8; dwErrCode
0x140002cf6  call    cs:__imp_SetLastError
0x140002cfd  nop     dword ptr [rax+rax+00h]
0x140002d02  mov     r8d, 462h
0x140002d08  lea     rdx, aUnableToAlloca; "Unable to allocate %d bytes of memory o"...
0x140002d0f  lea     rcx, aDllallocsplmem; "DllAllocSplMem"
0x140002d16  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140002d1b  call    cs:__imp_GetLastError
0x140002d22  nop     dword ptr [rax+rax+00h]
0x140002d27  mov     rdi, [rsp+38h+arg_0]
0x140002d2c  mov     rbx, [rsp+38h+arg_8]
0x140002d31  mov     rbp, [rsp+38h+arg_10]
0x140002d36  add     rsp, 30h
0x140002d3a  pop     rsi
0x140002d3b  retn
0x140002d3d  mov     eax, 7FFFFFFEh
0x140002d42  lea     r8, gszPrinterConnections; "Printers\\Connections\\"
0x140002d49  mov     edx, 231h
0x140002d4e  mov     rcx, rdi
0x140002d51  test    rax, rax
0x140002d54  jz      short loc_140002D75
0x140002d56  movzx   r9d, word ptr [r8]
0x140002d5a  test    r9w, r9w
0x140002d5e  jz      short loc_140002D75
0x140002d60  mov     [rcx], r9w
0x140002d64  add     r8, 2
0x140002d68  add     rcx, 2
0x140002d6c  dec     rax
0x140002d6f  sub     rdx, 1
0x140002d73  jnz     short loc_140002D51
0x140002d75  test    rdx, rdx
0x140002d78  lea     rax, [rcx-2]
0x140002d7c  lea     r10, [rdi+2Ah]
0x140002d80  cmovnz  rax, rcx
0x140002d84  xor     ecx, ecx
0x140002d86  mov     [rax], cx
0x140002d89  cmp     r10, rbx
0x140002d8c  jz      short loc_140002D9E
0x140002d8e  mov     r8, rbx; unsigned __int16 *
0x140002d91  mov     edx, 21Ch; unsigned __int64
0x140002d96  mov     rcx, r10; unsigned __int16 *
0x140002d99  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140002d9e  movzx   eax, word ptr [r10]
0x140002da2  test    ax, ax
0x140002da5  jz      short loc_140002DC1
0x140002da7  cmp     ax, 5Ch ; '\'
0x140002dab  jnz     short loc_140002DB3
0x140002dad  mov     word ptr [r10], 2Ch ; ','
0x140002db3  movzx   eax, word ptr [r10+2]
0x140002db8  add     r10, 2
0x140002dbc  test    ax, ax
0x140002dbf  jnz     short loc_140002DA7
0x140002dc1  mov     r9d, 2001Fh; samDesired
0x140002dc7  mov     [rsp+38h+phkResult], rsi; phkResult
0x140002dcc  xor     r8d, r8d; ulOptions
0x140002dcf  mov     rdx, rdi; lpSubKey
0x140002dd2  mov     rcx, rbp; hKey
0x140002dd5  call    cs:__imp_RegOpenKeyExW
0x140002ddc  nop     dword ptr [rax+rax+00h]
0x140002de1  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140002de8  mov     r8, rdi; lpMem
0x140002deb  xor     edx, edx; dwFlags
0x140002ded  mov     ebx, eax
0x140002def  call    cs:__imp_HeapFree
0x140002df6  nop     dword ptr [rax+rax+00h]
0x140002dfb  mov     eax, ebx
0x140002dfd  jmp     loc_140002D27
0x140002e02  mov     rbx, [rsp+38h+arg_8]
0x140002e07  mov     eax, 57h ; 'W'
0x140002e0c  mov     rbp, [rsp+38h+arg_10]
0x140002e11  add     rsp, 30h
0x140002e15  pop     rsi
0x140002e16  retn
```
