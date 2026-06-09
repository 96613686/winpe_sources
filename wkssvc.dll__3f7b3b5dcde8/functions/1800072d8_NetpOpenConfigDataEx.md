# NetpOpenConfigDataEx

- ea: `0x1800072d8`
- end: `0x1800073fa`
- name: `NetpOpenConfigDataEx`
- size: `290`
- prototype: `__int64 __fastcall(_QWORD *, __int64, HKEY, int)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180005dec`
- `0x180006e04`
- `0x1800071d8`
- `0x18002a06c`
- `0x18002abe4`

## callees

- `0x1800072d8`
- `0x180007604`
- `0x180007710`
- `0x18001ed22`
- `0x18001ed2e`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800073b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800073b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007303`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007303`

## string_xrefs

- `0x180007345`: `System\CurrentControlSet\Services\`

## pseudocode

```c
__int64 __fastcall NetpOpenConfigDataEx(_QWORD *a1, __int64 a2, HKEY a3, int a4)
{
  _QWORD *v6; // rbx
  wchar_t *v8; // rax
  wchar_t *v9; // rdi
  unsigned int v10; // esi
  HKEY phkResult; // [rsp+60h] [rbp+18h] BYREF

  phkResult = a3;
  *a1 = 0;
  v6 = LocalAlloc(0, 0x10u);
  if ( !v6 )
    return 8;
  phkResult = 0;
  v8 = (wchar_t *)NetpMemoryAllocate(0x7Eu);
  v9 = v8;
  if ( !v8 )
  {
    NetpMemoryFree(v6);
    return 8;
  }
  wcscpy_s(v8, 0x3Fu, L"System\\CurrentControlSet\\Services\\");
  wcscat_s(v9, 0x3Fu, L"LanmanWorkstation");
  wcscat_s(v9, 0x3Fu, L"\\");
  wcscat_s(v9, 0x3Fu, L"Parameters");
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, a4 != 0 ? 131097 : 131103, &phkResult);
  if ( v10 == 2 )
    v10 = 2146;
  NetpMemoryFree(v9);
  if ( v10 )
  {
    NetpMemoryFree(v6);
    v6 = 0;
  }
  else
  {
    *v6 = phkResult;
  }
  *a1 = v6;
  return v10;
}

```

## disassembly

```asm
0x1800072d8  mov     [rsp+arg_0], rbx
0x1800072dd  mov     [rsp+arg_8], rbp
0x1800072e2  mov     [rsp+arg_10], r8
0x1800072e7  push    rsi
0x1800072e8  push    rdi
0x1800072e9  push    r14
0x1800072eb  sub     rsp, 30h
0x1800072ef  mov     r14, rcx
0x1800072f2  mov     qword ptr [rcx], 0
0x1800072f9  xor     ecx, ecx; uFlags
0x1800072fb  mov     edx, 10h; uBytes
0x180007300  mov     esi, r9d
0x180007303  call    cs:__imp_LocalAlloc
0x180007309  mov     rbx, rax
0x18000730c  test    rax, rax
0x18000730f  jnz     short loc_18000731B
0x180007311  mov     eax, 8
0x180007316  jmp     loc_1800073E7
0x18000731b  mov     ecx, 7Eh ; '~'
0x180007320  mov     [rsp+48h+arg_10], 0
0x180007329  call    NetpMemoryAllocate
0x18000732e  mov     rdi, rax
0x180007331  test    rax, rax
0x180007334  jnz     short loc_180007340
0x180007336  mov     rcx, rbx
0x180007339  call    NetpMemoryFree
0x18000733e  jmp     short loc_180007311
0x180007340  mov     ebp, 3Fh ; '?'
0x180007345  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\"
0x18000734c  mov     edx, ebp; SizeInWords
0x18000734e  mov     rcx, rdi; Destination
0x180007351  call    wcscpy_s
0x180007356  lea     r8, aLanmanworkstat; "LanmanWorkstation"
0x18000735d  mov     edx, ebp; SizeInWords
0x18000735f  mov     rcx, rdi; Destination
0x180007362  call    wcscat_s
0x180007367  lea     r8, Src; "\\"
0x18000736e  mov     edx, ebp; SizeInWords
0x180007370  mov     rcx, rdi; Destination
0x180007373  call    wcscat_s
0x180007378  lea     r8, aParameters; "Parameters"
0x18000737f  mov     edx, ebp; SizeInWords
0x180007381  mov     rcx, rdi; Destination
0x180007384  call    wcscat_s
0x180007389  lea     rax, [rsp+48h+arg_10]
0x18000738e  neg     esi
0x180007390  mov     rdx, rdi; lpSubKey
0x180007393  mov     [rsp+48h+phkResult], rax; phkResult
0x180007398  sbb     r9d, r9d
0x18000739b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800073a2  and     r9d, 0FFFFFFFAh
0x1800073a6  xor     r8d, r8d; ulOptions
0x1800073a9  add     r9d, 2001Fh; samDesired
0x1800073b0  call    cs:__imp_RegOpenKeyExW
0x1800073b6  mov     esi, eax
0x1800073b8  cmp     eax, 2
0x1800073bb  jnz     short loc_1800073C2
0x1800073bd  mov     esi, 862h
0x1800073c2  mov     rcx, rdi
0x1800073c5  call    NetpMemoryFree
0x1800073ca  test    esi, esi
0x1800073cc  jz      short loc_1800073DA
0x1800073ce  mov     rcx, rbx
0x1800073d1  call    NetpMemoryFree
0x1800073d6  xor     ebx, ebx
0x1800073d8  jmp     short loc_1800073E2
0x1800073da  mov     rcx, [rsp+48h+arg_10]
0x1800073df  mov     [rbx], rcx
0x1800073e2  mov     [r14], rbx
0x1800073e5  mov     eax, esi
0x1800073e7  mov     rbx, [rsp+48h+arg_0]
0x1800073ec  mov     rbp, [rsp+48h+arg_8]
0x1800073f1  add     rsp, 30h
0x1800073f5  pop     r14
0x1800073f7  pop     rdi
0x1800073f8  pop     rsi
0x1800073f9  retn
```
