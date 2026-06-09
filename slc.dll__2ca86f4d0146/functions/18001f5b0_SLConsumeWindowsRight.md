# SLConsumeWindowsRight

- ea: `0x18001f5b0`
- end: `0x18001f708`
- name: `SLConsumeWindowsRight`
- size: `344`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18001d5c8`
- `0x18001d9c8`
- `0x18001d9e8`
- `0x18001e540`
- `0x18001e854`
- `0x18001f5b0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f657`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f63c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f63c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f676`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f676`
- `sppc!SLOpen` at `0x18001f688`
- `sppc!SLOpen` at `0x18001f688`
- `sppc!SLClose` at `0x18001f6f3`
- `sppc!SLClose` at `0x18001f6f3`

## string_xrefs

- `0x18001f633`: `SPPC.DLL`

## pseudocode

```c
__int64 __fastcall SLConsumeWindowsRight(__int64 a1, __int64 a2)
{
  int v2; // esi
  HRESULT v3; // eax
  __int64 v4; // rdi
  unsigned int v5; // ebx
  HMODULE Library; // rbx
  DWORD LastError; // eax
  FARPROC SLCallServer; // rsi
  __int128 v10; // [rsp+30h] [rbp-20h] BYREF
  __int128 v11; // [rsp+40h] [rbp-10h]
  HMODULE v12; // [rsp+78h] [rbp+28h] BYREF
  HSLC phSLC; // [rsp+80h] [rbp+30h] BYREF
  __int64 v14; // [rsp+88h] [rbp+38h] BYREF

  phSLC = 0;
  v12 = 0;
  v10 = 0;
  v2 = a1;
  v14 = 0;
  v11 = 0;
  v3 = sub_18001D9E8(a1, a2, &v14);
  v4 = v14;
  v5 = v3;
  if ( v3 < 0 )
    goto LABEL_9;
  DWORD2(v10) = 1;
  *(_QWORD *)&v10 = L"SppNotificationFlags";
  LODWORD(v11) = v2;
  v3 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v14 + 72LL))(v14, &v10, 0);
  v5 = v3;
  if ( v3 < 0 )
    goto LABEL_9;
  Library = LoadLibraryExW(L"SPPC.DLL", 0, 0);
  sub_18001E854(&v12);
  if ( !Library )
  {
    v12 = 0;
LABEL_5:
    LastError = GetLastError();
    v3 = sub_18001D5C8(LastError);
    v5 = v3;
LABEL_9:
    sub_18001D9C8((unsigned int)v3);
    goto LABEL_10;
  }
  v12 = Library;
  SLCallServer = GetProcAddress(Library, "SLCallServer");
  if ( !SLCallServer )
    goto LABEL_5;
  v3 = SLOpen_0(&phSLC);
  v5 = v3;
  if ( v3 < 0 )
    goto LABEL_9;
  v3 = ((__int64 (__fastcall *)(HSLC, const wchar_t *, __int64, __int64, _QWORD))SLCallServer)(
         phSLC,
         L"ConsumeWindowsRight",
         1,
         v4,
         0);
  v5 = v3;
  if ( v3 < 0 )
    goto LABEL_9;
LABEL_10:
  sub_18001E540(v5);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  sub_18001E854(&v12);
  if ( phSLC )
    SLClose_0(phSLC);
  return v5;
}

```

## disassembly

```asm
0x18001f5b0  mov     [rsp-18h+arg_0], rbx
0x18001f5b5  push    rbp
0x18001f5b6  push    rsi
0x18001f5b7  push    rdi
0x18001f5b8  mov     rbp, rsp
0x18001f5bb  sub     rsp, 50h
0x18001f5bf  xorps   xmm0, xmm0
0x18001f5c2  mov     [rbp+phSLC], 0
0x18001f5ca  lea     r8, [rbp+arg_18]
0x18001f5ce  mov     [rbp+arg_8], 0
0x18001f5d6  movups  [rbp+var_20], xmm0
0x18001f5da  mov     esi, ecx
0x18001f5dc  mov     [rbp+arg_18], 0
0x18001f5e4  movups  [rbp+var_10], xmm0
0x18001f5e8  call    sub_18001D9E8
0x18001f5ed  mov     rdi, [rbp+arg_18]
0x18001f5f1  mov     ebx, eax
0x18001f5f3  test    eax, eax
0x18001f5f5  js      loc_18001F6BF
0x18001f5fb  lea     rax, aSppnotificatio_0; "SppNotificationFlags"
0x18001f602  mov     dword ptr [rbp+var_20+8], 1
0x18001f609  mov     qword ptr [rbp+var_20], rax
0x18001f60d  lea     rdx, [rbp+var_20]
0x18001f611  mov     dword ptr [rbp+var_10], esi
0x18001f614  xor     r8d, r8d
0x18001f617  mov     rax, [rdi]
0x18001f61a  mov     rcx, rdi
0x18001f61d  mov     rax, [rax+48h]
0x18001f621  call    j_j__guard_dispatch_icall_nop
0x18001f626  mov     ebx, eax
0x18001f628  test    eax, eax
0x18001f62a  js      loc_18001F6BF
0x18001f630  xor     r8d, r8d; dwFlags
0x18001f633  lea     rcx, LibFileName; "SPPC.DLL"
0x18001f63a  xor     edx, edx; hFile
0x18001f63c  call    cs:LoadLibraryExW
0x18001f642  lea     rcx, [rbp+arg_8]
0x18001f646  mov     rbx, rax
0x18001f649  call    sub_18001E854
0x18001f64e  test    rbx, rbx
0x18001f651  jnz     short loc_18001F668
0x18001f653  mov     [rbp+arg_8], rbx
0x18001f657  call    cs:GetLastError
0x18001f65d  mov     ecx, eax
0x18001f65f  call    sub_18001D5C8
0x18001f664  mov     ebx, eax
0x18001f666  jmp     short loc_18001F6BF
0x18001f668  lea     rdx, aSlcallserver; "SLCallServer"
0x18001f66f  mov     [rbp+arg_8], rbx
0x18001f673  mov     rcx, rbx; hModule
0x18001f676  call    cs:GetProcAddress
0x18001f67c  mov     rsi, rax
0x18001f67f  test    rax, rax
0x18001f682  jz      short loc_18001F657
0x18001f684  lea     rcx, [rbp+phSLC]; phSLC
0x18001f688  call    cs:SLOpen_0
0x18001f68e  mov     ebx, eax
0x18001f690  test    eax, eax
0x18001f692  js      short loc_18001F6BF
0x18001f694  mov     rcx, [rbp+phSLC]
0x18001f698  lea     rdx, aConsumewindows; "ConsumeWindowsRight"
0x18001f69f  mov     r9, rdi
0x18001f6a2  mov     [rsp+50h+var_30], 0
0x18001f6ab  mov     r8d, 1
0x18001f6b1  mov     rax, rsi
0x18001f6b4  call    j_j__guard_dispatch_icall_nop
0x18001f6b9  mov     ebx, eax
0x18001f6bb  test    eax, eax
0x18001f6bd  jns     short loc_18001F6C6
0x18001f6bf  mov     ecx, eax
0x18001f6c1  call    sub_18001D9C8
0x18001f6c6  mov     ecx, ebx
0x18001f6c8  call    sub_18001E540
0x18001f6cd  test    rdi, rdi
0x18001f6d0  jz      short loc_18001F6E1
0x18001f6d2  mov     rax, [rdi]
0x18001f6d5  mov     rcx, rdi
0x18001f6d8  mov     rax, [rax+10h]
0x18001f6dc  call    j_j__guard_dispatch_icall_nop
0x18001f6e1  lea     rcx, [rbp+arg_8]
0x18001f6e5  call    sub_18001E854
0x18001f6ea  mov     rcx, [rbp+phSLC]; hSLC
0x18001f6ee  test    rcx, rcx
0x18001f6f1  jz      short loc_18001F6F9
0x18001f6f3  call    cs:SLClose_0
0x18001f6f9  mov     eax, ebx
0x18001f6fb  mov     rbx, [rsp+50h+arg_0]
0x18001f700  add     rsp, 50h
0x18001f704  pop     rdi
0x18001f705  pop     rsi
0x18001f706  pop     rbp
0x18001f707  retn
```
