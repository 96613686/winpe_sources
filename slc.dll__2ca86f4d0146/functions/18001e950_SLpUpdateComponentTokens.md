# SLpUpdateComponentTokens

- ea: `0x18001e950`
- end: `0x18001ea8c`
- name: `SLpUpdateComponentTokens`
- size: `316`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001d5c8`
- `0x18001d9c8`
- `0x18001e540`
- `0x18001e854`
- `0x18001e950`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e9c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e9c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e9a7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e9a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e9e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e9e3`

## string_xrefs

- `0x18001e99e`: `SPPC.DLL`
- `0x18001e9fa`: `UpdateComponentTokens`
- `0x18001ea1b`: `SppNotificationUpdated`

## pseudocode

```c
__int64 __fastcall SLpUpdateComponentTokens(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  HMODULE Library; // rbx
  DWORD LastError; // eax
  int v8; // eax
  FARPROC SLCallServer; // rax
  __int128 v11; // [rsp+30h] [rbp-20h] BYREF
  __int128 v12; // [rsp+40h] [rbp-10h]
  HMODULE v13; // [rsp+80h] [rbp+30h] BYREF

  v13 = 0;
  v11 = 0;
  v12 = 0;
  if ( a1 && a2 )
  {
    Library = LoadLibraryExW(L"SPPC.DLL", 0, 0);
    sub_18001E854(&v13);
    if ( !Library )
    {
      v13 = 0;
LABEL_7:
      LastError = GetLastError();
      v8 = sub_18001D5C8(LastError);
      v5 = v8;
LABEL_8:
      v4 = (unsigned int)v8;
      goto LABEL_3;
    }
    v13 = Library;
    SLCallServer = GetProcAddress(Library, "SLCallServer");
    if ( !SLCallServer )
      goto LABEL_7;
    v8 = ((__int64 (__fastcall *)(__int64, const wchar_t *, __int64))SLCallServer)(a1, L"UpdateComponentTokens", 1);
    v5 = v8;
    if ( v8 < 0 )
      goto LABEL_8;
    v8 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int128 *))(MEMORY[0] + 48LL))(
           0,
           L"SppNotificationUpdated",
           &v11);
    v5 = v8;
    if ( v8 < 0 )
      goto LABEL_8;
    if ( DWORD2(v11) == 1 )
    {
      *a2 = v12 != 0;
      goto LABEL_15;
    }
    v5 = -1073418210;
    v4 = 3221549086LL;
  }
  else
  {
    v4 = 2147942487LL;
    v5 = -2147024809;
  }
LABEL_3:
  sub_18001D9C8(v4);
LABEL_15:
  sub_18001E540(v5);
  sub_18001E854(&v13);
  return v5;
}

```

## disassembly

```asm
0x18001e950  mov     [rsp-18h+arg_8], rbx
0x18001e955  push    rbp
0x18001e956  push    rsi
0x18001e957  push    rdi
0x18001e958  mov     rbp, rsp
0x18001e95b  sub     rsp, 50h
0x18001e95f  mov     [rbp+arg_10], 0
0x18001e967  xorps   xmm0, xmm0
0x18001e96a  mov     [rbp+arg_0], 0
0x18001e972  mov     rdi, rdx
0x18001e975  mov     rsi, rcx
0x18001e978  movups  [rbp+var_20], xmm0
0x18001e97c  movups  [rbp+var_10], xmm0
0x18001e980  test    rcx, rcx
0x18001e983  jnz     short loc_18001E996
0x18001e985  mov     ecx, 80070057h
0x18001e98a  mov     ebx, ecx
0x18001e98c  call    sub_18001D9C8
0x18001e991  jmp     loc_18001EA50
0x18001e996  test    rdi, rdi
0x18001e999  jz      short loc_18001E985
0x18001e99b  xor     r8d, r8d; dwFlags
0x18001e99e  lea     rcx, LibFileName; "SPPC.DLL"
0x18001e9a5  xor     edx, edx; hFile
0x18001e9a7  call    cs:LoadLibraryExW
0x18001e9ad  lea     rcx, [rbp+arg_10]
0x18001e9b1  mov     rbx, rax
0x18001e9b4  call    sub_18001E854
0x18001e9b9  test    rbx, rbx
0x18001e9bc  jnz     short loc_18001E9D5
0x18001e9be  mov     [rbp+arg_10], rbx
0x18001e9c2  call    cs:GetLastError
0x18001e9c8  mov     ecx, eax
0x18001e9ca  call    sub_18001D5C8
0x18001e9cf  mov     ebx, eax
0x18001e9d1  mov     ecx, eax
0x18001e9d3  jmp     short loc_18001E98C
0x18001e9d5  lea     rdx, aSlcallserver; "SLCallServer"
0x18001e9dc  mov     [rbp+arg_10], rbx
0x18001e9e0  mov     rcx, rbx; hModule
0x18001e9e3  call    cs:GetProcAddress
0x18001e9e9  test    rax, rax
0x18001e9ec  jz      short loc_18001E9C2
0x18001e9ee  xor     r9d, r9d
0x18001e9f1  lea     rcx, [rbp+arg_0]
0x18001e9f5  mov     [rsp+50h+var_30], rcx
0x18001e9fa  lea     rdx, aUpdatecomponen; "UpdateComponentTokens"
0x18001ea01  mov     rcx, rsi
0x18001ea04  lea     r8d, [r9+1]
0x18001ea08  call    j_j__guard_dispatch_icall_nop
0x18001ea0d  mov     ebx, eax
0x18001ea0f  test    eax, eax
0x18001ea11  js      short loc_18001E9D1
0x18001ea13  mov     rcx, [rbp+arg_0]
0x18001ea17  lea     r8, [rbp+var_20]
0x18001ea1b  lea     rdx, aSppnotificatio; "SppNotificationUpdated"
0x18001ea22  mov     rax, [rcx]
0x18001ea25  mov     rax, [rax+30h]
0x18001ea29  call    j_j__guard_dispatch_icall_nop
0x18001ea2e  mov     ebx, eax
0x18001ea30  test    eax, eax
0x18001ea32  js      short loc_18001E9D1
0x18001ea34  cmp     dword ptr [rbp+var_20+8], 1
0x18001ea38  jz      short loc_18001EA46
0x18001ea3a  mov     ebx, 0C004F01Eh
0x18001ea3f  mov     ecx, ebx
0x18001ea41  jmp     loc_18001E98C
0x18001ea46  xor     eax, eax
0x18001ea48  cmp     dword ptr [rbp+var_10], eax
0x18001ea4b  setnz   al
0x18001ea4e  mov     [rdi], eax
0x18001ea50  mov     ecx, ebx
0x18001ea52  call    sub_18001E540
0x18001ea57  mov     rcx, [rbp+arg_0]
0x18001ea5b  test    rcx, rcx
0x18001ea5e  jz      short loc_18001EA74
0x18001ea60  mov     rax, [rcx]
0x18001ea63  mov     rax, [rax+10h]
0x18001ea67  call    j_j__guard_dispatch_icall_nop
0x18001ea6c  mov     [rbp+arg_0], 0
0x18001ea74  lea     rcx, [rbp+arg_10]
0x18001ea78  call    sub_18001E854
0x18001ea7d  mov     eax, ebx
0x18001ea7f  mov     rbx, [rsp+50h+arg_8]
0x18001ea84  add     rsp, 50h
0x18001ea88  pop     rdi
0x18001ea89  pop     rsi
0x18001ea8a  pop     rbp
0x18001ea8b  retn
```
