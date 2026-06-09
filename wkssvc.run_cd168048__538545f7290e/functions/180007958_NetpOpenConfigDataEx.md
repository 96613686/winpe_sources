# NetpOpenConfigDataEx

- ea: `0x180007958`
- end: `0x180007a87`
- name: `NetpOpenConfigDataEx`
- size: `303`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800061d8`
- `0x18000743c`
- `0x180007844`
- `0x18002c5a8`
- `0x18002d1e8`

## callees

- `0x180007958`
- `0x180007cb0`
- `0x180007cd4`
- `0x1800204d2`
- `0x1800204de`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007a36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007a36`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007983`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007983`

## string_xrefs

- `0x1800079cb`: `System\CurrentControlSet\Services\`

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
  v8 = (wchar_t *)NetpMemoryAllocate(126);
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
0x180007958  mov     [rsp+arg_0], rbx
0x18000795d  mov     [rsp+arg_8], rbp
0x180007962  mov     [rsp+arg_10], r8
0x180007967  push    rsi
0x180007968  push    rdi
0x180007969  push    r14
0x18000796b  sub     rsp, 30h
0x18000796f  mov     r14, rcx
0x180007972  mov     qword ptr [rcx], 0
0x180007979  xor     ecx, ecx; uFlags
0x18000797b  mov     edx, 10h; uBytes
0x180007980  mov     esi, r9d
0x180007983  call    cs:__imp_LocalAlloc
0x18000798a  nop     dword ptr [rax+rax+00h]
0x18000798f  mov     rbx, rax
0x180007992  test    rax, rax
0x180007995  jnz     short loc_1800079A1
0x180007997  mov     eax, 8
0x18000799c  jmp     loc_180007A73
0x1800079a1  mov     ecx, 7Eh ; '~'
0x1800079a6  mov     [rsp+48h+arg_10], 0
0x1800079af  call    NetpMemoryAllocate
0x1800079b4  mov     rdi, rax
0x1800079b7  test    rax, rax
0x1800079ba  jnz     short loc_1800079C6
0x1800079bc  mov     rcx, rbx
0x1800079bf  call    NetpMemoryFree
0x1800079c4  jmp     short loc_180007997
0x1800079c6  mov     ebp, 3Fh ; '?'
0x1800079cb  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\"
0x1800079d2  mov     edx, ebp; SizeInWords
0x1800079d4  mov     rcx, rdi; Destination
0x1800079d7  call    wcscpy_s
0x1800079dc  lea     r8, aLanmanworkstat; "LanmanWorkstation"
0x1800079e3  mov     edx, ebp; SizeInWords
0x1800079e5  mov     rcx, rdi; Destination
0x1800079e8  call    wcscat_s
0x1800079ed  lea     r8, Src; "\\"
0x1800079f4  mov     edx, ebp; SizeInWords
0x1800079f6  mov     rcx, rdi; Destination
0x1800079f9  call    wcscat_s
0x1800079fe  lea     r8, aParameters; "Parameters"
0x180007a05  mov     edx, ebp; SizeInWords
0x180007a07  mov     rcx, rdi; Destination
0x180007a0a  call    wcscat_s
0x180007a0f  lea     rax, [rsp+48h+arg_10]
0x180007a14  neg     esi
0x180007a16  mov     rdx, rdi; lpSubKey
0x180007a19  mov     [rsp+48h+phkResult], rax; phkResult
0x180007a1e  sbb     r9d, r9d
0x180007a21  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007a28  and     r9d, 0FFFFFFFAh
0x180007a2c  xor     r8d, r8d; ulOptions
0x180007a2f  add     r9d, 2001Fh; samDesired
0x180007a36  call    cs:__imp_RegOpenKeyExW
0x180007a3d  nop     dword ptr [rax+rax+00h]
0x180007a42  mov     esi, eax
0x180007a44  cmp     eax, 2
0x180007a47  jnz     short loc_180007A4E
0x180007a49  mov     esi, 862h
0x180007a4e  mov     rcx, rdi
0x180007a51  call    NetpMemoryFree
0x180007a56  test    esi, esi
0x180007a58  jz      short loc_180007A66
0x180007a5a  mov     rcx, rbx
0x180007a5d  call    NetpMemoryFree
0x180007a62  xor     ebx, ebx
0x180007a64  jmp     short loc_180007A6E
0x180007a66  mov     rcx, [rsp+48h+arg_10]
0x180007a6b  mov     [rbx], rcx
0x180007a6e  mov     [r14], rbx
0x180007a71  mov     eax, esi
0x180007a73  mov     rbx, [rsp+48h+arg_0]
0x180007a78  mov     rbp, [rsp+48h+arg_8]
0x180007a7d  add     rsp, 30h
0x180007a81  pop     r14
0x180007a83  pop     rdi
0x180007a84  pop     rsi
0x180007a85  retn
```
