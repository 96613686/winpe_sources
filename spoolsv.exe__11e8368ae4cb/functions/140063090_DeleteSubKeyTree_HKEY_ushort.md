# DeleteSubKeyTree(HKEY__ *,ushort *)

- ea: `0x140063090`
- end: `0x1400631cb`
- name: `?DeleteSubKeyTree@@YAHPEAUHKEY__@@PEAG@Z`
- size: `315`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14005dfe4`
- `0x14005ef30`
- `0x140063090`

## callees

- `0x1400041c0`
- `0x1400140cc`
- `0x140063090`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140063189`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140063189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400631a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400631a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400630e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006319a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400630e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006319a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400630da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400630da`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140063170`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140063170`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140063143`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140063143`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140063152`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140063152`

## string_xrefs

- `0x1400631b0`: `DeleteSubKeyTree`

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
0x140063090  mov     [rsp+arg_0], rbx
0x140063095  push    rbp
0x140063096  push    rsi
0x140063097  push    rdi
0x140063098  sub     rsp, 40h
0x14006309c  mov     rbp, rcx
0x14006309f  mov     [rsp+58h+hKey], 0
0x1400630a8  mov     ecx, 208h; dwBytes
0x1400630ad  mov     rsi, rdx
0x1400630b0  call    DllAllocSplMem
0x1400630b5  mov     rdi, rax
0x1400630b8  test    rax, rax
0x1400630bb  jz      loc_140063195
0x1400630c1  lea     rax, [rsp+58h+hKey]
0x1400630c6  mov     r9d, 2001Fh; samDesired
0x1400630cc  xor     r8d, r8d; ulOptions
0x1400630cf  mov     [rsp+58h+phkResult], rax; phkResult
0x1400630d4  mov     rdx, rsi; lpSubKey
0x1400630d7  mov     rcx, rbp; hKey
0x1400630da  call    cs:__imp_RegOpenKeyExW
0x1400630e0  test    eax, eax
0x1400630e2  jz      short loc_1400630EE
0x1400630e4  mov     ecx, eax; dwErrCode
0x1400630e6  call    cs:__imp_SetLastError
0x1400630ec  jmp     short loc_140063160
0x1400630ee  mov     ebx, 1
0x1400630f3  jmp     short loc_140063108
0x1400630f5  mov     rcx, [rsp+58h+hKey]; hKey
0x1400630fa  mov     rdx, rdi; lpSubKey
0x1400630fd  call    ?DeleteSubKeyTree@@YAHPEAUHKEY__@@PEAG@Z; DeleteSubKeyTree(HKEY__ *,ushort *)
0x140063102  mov     ebx, eax
0x140063104  test    eax, eax
0x140063106  jz      short loc_14006314D
0x140063108  mov     rcx, [rsp+58h+hKey]; hKey
0x14006310d  lea     r9, [rsp+58h+cchName]; lpcchName
0x140063112  mov     [rsp+58h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14006311b  mov     r8, rdi; lpName
0x14006311e  mov     [rsp+58h+lpcchClass], 0; lpcchClass
0x140063127  xor     edx, edx; dwIndex
0x140063129  mov     [rsp+58h+lpClass], 0; lpClass
0x140063132  mov     [rsp+58h+phkResult], 0; lpReserved
0x14006313b  mov     [rsp+58h+cchName], 104h
0x140063143  call    cs:__imp_RegEnumKeyExW
0x140063149  test    eax, eax
0x14006314b  jz      short loc_1400630F5
0x14006314d  mov     rcx, [rsp+58h+hKey]; hKey
0x140063152  call    cs:__imp_RegCloseKey
0x140063158  test    ebx, ebx
0x14006315a  jz      short loc_14006317D
0x14006315c  test    eax, eax
0x14006315e  jz      short loc_140063164
0x140063160  xor     ebx, ebx
0x140063162  jmp     short loc_14006317D
0x140063164  xor     r9d, r9d; Reserved
0x140063167  xor     r8d, r8d; samDesired
0x14006316a  mov     rdx, rsi; lpSubKey
0x14006316d  mov     rcx, rbp; hKey
0x140063170  call    cs:__imp_RegDeleteKeyExW
0x140063176  xor     ecx, ecx
0x140063178  test    eax, eax
0x14006317a  cmovnz  ebx, ecx
0x14006317d  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140063184  mov     r8, rdi; lpMem
0x140063187  xor     edx, edx; dwFlags
0x140063189  call    cs:__imp_HeapFree
0x14006318f  test    ebx, ebx
0x140063191  jnz     short loc_1400631BC
0x140063193  jmp     short loc_1400631A0
0x140063195  xor     ebx, ebx
0x140063197  lea     ecx, [rbx+8]; dwErrCode
0x14006319a  call    cs:__imp_SetLastError
0x1400631a0  call    cs:__imp_GetLastError
0x1400631a6  mov     r8d, eax
0x1400631a9  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x1400631b0  lea     rcx, aDeletesubkeytr; "DeleteSubKeyTree"
0x1400631b7  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400631bc  mov     eax, ebx
0x1400631be  mov     rbx, [rsp+58h+arg_0]
0x1400631c3  add     rsp, 40h
0x1400631c7  pop     rdi
0x1400631c8  pop     rsi
0x1400631c9  pop     rbp
0x1400631ca  retn
```
