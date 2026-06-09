# DeleteSubKeyTree(HKEY__ *,ushort *)

- ea: `0x14006914c`
- end: `0x1400692b8`
- name: `?DeleteSubKeyTree@@YAHPEAUHKEY__@@PEAG@Z`
- size: `364`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140063c38`
- `0x140064ca0`
- `0x14006914c`

## callees

- `0x140004790`
- `0x140015378`
- `0x14006914c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140069263`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140069263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069286`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400691a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006927a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400691a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006927a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140069196`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140069196`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140069244`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140069244`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14006920b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14006920b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140069220`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140069220`

## string_xrefs

- `0x14006929c`: `DeleteSubKeyTree`

## pseudocode

```c
__int64 __fastcall DeleteSubKeyTree(HKEY hKey, LPCWSTR lpSubKey)
{
  WCHAR *v4; // rdi
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  DWORD LastError; // eax
  DWORD cchName; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKeya; // [rsp+78h] [rbp+20h] BYREF

  hKeya = 0;
  v4 = (WCHAR *)DllAllocSplMem(0x208u);
  if ( !v4 )
  {
    v6 = 0;
    SetLastError(8u);
LABEL_15:
    LastError = GetLastError();
    PrvSpoolssTelemetry::WriteDbgTraceError("DeleteSubKeyTree", L"Failed.  Error %d.", LastError);
    return v6;
  }
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x2001Fu, &hKeya);
  if ( v5 )
  {
    SetLastError(v5);
LABEL_9:
    v6 = 0;
    goto LABEL_12;
  }
  v6 = 1;
  do
  {
    cchName = 260;
    if ( RegEnumKeyExW(hKeya, 0, v4, &cchName, 0, 0, 0, 0) )
      break;
    v6 = DeleteSubKeyTree(hKeya, v4);
  }
  while ( v6 );
  v7 = RegCloseKey(hKeya);
  if ( v6 )
  {
    if ( v7 )
      goto LABEL_9;
    if ( RegDeleteKeyExW(hKey, lpSubKey, 0, 0) )
      v6 = 0;
  }
LABEL_12:
  HeapFree(g_hSpoolssHeap, 0, v4);
  if ( !v6 )
    goto LABEL_15;
  return v6;
}

```

## disassembly

```asm
0x14006914c  mov     [rsp+arg_0], rbx
0x140069151  push    rbp
0x140069152  push    rsi
0x140069153  push    rdi
0x140069154  sub     rsp, 40h
0x140069158  mov     rbp, rcx
0x14006915b  mov     [rsp+58h+hKey], 0
0x140069164  mov     ecx, 208h; dwBytes
0x140069169  mov     rsi, rdx
0x14006916c  call    DllAllocSplMem
0x140069171  mov     rdi, rax
0x140069174  test    rax, rax
0x140069177  jz      loc_140069275
0x14006917d  lea     rax, [rsp+58h+hKey]
0x140069182  mov     r9d, 2001Fh; samDesired
0x140069188  xor     r8d, r8d; ulOptions
0x14006918b  mov     [rsp+58h+phkResult], rax; phkResult
0x140069190  mov     rdx, rsi; lpSubKey
0x140069193  mov     rcx, rbp; hKey
0x140069196  call    cs:__imp_RegOpenKeyExW
0x14006919d  nop     dword ptr [rax+rax+00h]
0x1400691a2  test    eax, eax
0x1400691a4  jz      short loc_1400691B6
0x1400691a6  mov     ecx, eax; dwErrCode
0x1400691a8  call    cs:__imp_SetLastError
0x1400691af  nop     dword ptr [rax+rax+00h]
0x1400691b4  jmp     short loc_140069234
0x1400691b6  mov     ebx, 1
0x1400691bb  jmp     short loc_1400691D0
0x1400691bd  mov     rcx, [rsp+58h+hKey]; hKey
0x1400691c2  mov     rdx, rdi; lpSubKey
0x1400691c5  call    ?DeleteSubKeyTree@@YAHPEAUHKEY__@@PEAG@Z; DeleteSubKeyTree(HKEY__ *,ushort *)
0x1400691ca  mov     ebx, eax
0x1400691cc  test    eax, eax
0x1400691ce  jz      short loc_14006921B
0x1400691d0  mov     rcx, [rsp+58h+hKey]; hKey
0x1400691d5  lea     r9, [rsp+58h+cchName]; lpcchName
0x1400691da  mov     [rsp+58h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1400691e3  mov     r8, rdi; lpName
0x1400691e6  mov     [rsp+58h+lpcchClass], 0; lpcchClass
0x1400691ef  xor     edx, edx; dwIndex
0x1400691f1  mov     [rsp+58h+lpClass], 0; lpClass
0x1400691fa  mov     [rsp+58h+phkResult], 0; lpReserved
0x140069203  mov     [rsp+58h+cchName], 104h
0x14006920b  call    cs:__imp_RegEnumKeyExW
0x140069212  nop     dword ptr [rax+rax+00h]
0x140069217  test    eax, eax
0x140069219  jz      short loc_1400691BD
0x14006921b  mov     rcx, [rsp+58h+hKey]; hKey
0x140069220  call    cs:__imp_RegCloseKey
0x140069227  nop     dword ptr [rax+rax+00h]
0x14006922c  test    ebx, ebx
0x14006922e  jz      short loc_140069257
0x140069230  test    eax, eax
0x140069232  jz      short loc_140069238
0x140069234  xor     ebx, ebx
0x140069236  jmp     short loc_140069257
0x140069238  xor     r9d, r9d; Reserved
0x14006923b  xor     r8d, r8d; samDesired
0x14006923e  mov     rdx, rsi; lpSubKey
0x140069241  mov     rcx, rbp; hKey
0x140069244  call    cs:__imp_RegDeleteKeyExW
0x14006924b  nop     dword ptr [rax+rax+00h]
0x140069250  xor     ecx, ecx
0x140069252  test    eax, eax
0x140069254  cmovnz  ebx, ecx
0x140069257  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006925e  mov     r8, rdi; lpMem
0x140069261  xor     edx, edx; dwFlags
0x140069263  call    cs:__imp_HeapFree
0x14006926a  nop     dword ptr [rax+rax+00h]
0x14006926f  test    ebx, ebx
0x140069271  jnz     short loc_1400692A8
0x140069273  jmp     short loc_140069286
0x140069275  xor     ebx, ebx
0x140069277  lea     ecx, [rbx+8]; dwErrCode
0x14006927a  call    cs:__imp_SetLastError
0x140069281  nop     dword ptr [rax+rax+00h]
0x140069286  call    cs:__imp_GetLastError
0x14006928d  nop     dword ptr [rax+rax+00h]
0x140069292  mov     r8d, eax
0x140069295  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x14006929c  lea     rcx, aDeletesubkeytr; "DeleteSubKeyTree"
0x1400692a3  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400692a8  mov     eax, ebx
0x1400692aa  mov     rbx, [rsp+58h+arg_0]
0x1400692af  add     rsp, 40h
0x1400692b3  pop     rdi
0x1400692b4  pop     rsi
0x1400692b5  pop     rbp
0x1400692b6  retn
```
