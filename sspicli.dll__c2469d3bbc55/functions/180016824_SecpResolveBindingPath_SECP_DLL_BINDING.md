# SecpResolveBindingPath(_SECP_DLL_BINDING *)

- ea: `0x180016824`
- end: `0x1800169b1`
- name: `?SecpResolveBindingPath@@YAJPEAU_SECP_DLL_BINDING@@@Z`
- size: `397`
- prototype: `__int64 __fastcall(struct _SECP_DLL_BINDING *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000d3a8`
- `0x180016694`
- `0x18001caa0`

## callees

- `0x18000ee2c`
- `0x180016824`
- `0x18001d4e0`
- `0x180022190`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800168f0`
- `ntdll!RtlInitUnicodeString` at `0x1800168f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001689c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001693f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001689c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001693f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016970`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016970`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016874`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016874`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800168d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800168d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016914`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016914`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016988`

## pseudocode

```c
__int64 __fastcall SecpResolveBindingPath(struct _SECP_DLL_BINDING *a1)
{
  unsigned int v1; // ebx
  const WCHAR *v3; // rcx
  HMODULE Library; // rax
  char LastError; // al
  int v6; // r8d
  DWORD ModuleFileNameW; // eax
  char v8; // al
  int v9; // r8d
  HMODULE v10; // rcx
  HLOCAL hMem[2]; // [rsp+30h] [rbp-248h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-238h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-228h] BYREF

  v1 = 0;
  *(_OWORD *)hMem = 0;
  DestinationString = 0;
  if ( !*((_QWORD *)a1 + 1) )
  {
    v3 = (const WCHAR *)*((_QWORD *)a1 + 3);
    if ( v3 )
    {
      Library = LoadLibraryExW(v3, 0, 0);
      *((_QWORD *)a1 + 1) = Library;
      if ( !Library )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v6, *((_QWORD *)a1 + 3), LastError);
        }
        v1 = -1073741502;
        goto LABEL_17;
      }
      ModuleFileNameW = GetModuleFileNameW(Library, Filename, 0x105u);
      if ( ModuleFileNameW && ModuleFileNameW != 261 )
      {
        RtlInitUnicodeString(&DestinationString, Filename);
        if ( (unsigned int)SecpDuplicateString((struct _UNICODE_STRING *)hMem, &DestinationString) )
        {
          LocalFree(*((HLOCAL *)a1 + 3));
          *((_OWORD *)a1 + 1) = *(_OWORD *)hMem;
          return v1;
        }
        v1 = -1073741801;
        goto LABEL_17;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = GetLastError();
        WPP_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v9, *((_QWORD *)a1 + 3), v8);
      }
    }
    v1 = -1073741595;
LABEL_17:
    v10 = (HMODULE)*((_QWORD *)a1 + 1);
    if ( v10 )
    {
      FreeLibrary(v10);
      *((_QWORD *)a1 + 1) = 0;
    }
  }
  if ( hMem[1] )
    LocalFree(hMem[1]);
  return v1;
}

```

## disassembly

```asm
0x180016824  mov     [rsp+arg_8], rbx
0x180016829  push    rdi
0x18001682a  sub     rsp, 270h
0x180016831  mov     rax, cs:__security_cookie
0x180016838  xor     rax, rsp
0x18001683b  mov     [rsp+278h+var_18], rax
0x180016843  xor     ebx, ebx
0x180016845  xorps   xmm0, xmm0
0x180016848  xorps   xmm1, xmm1
0x18001684b  mov     rdi, rcx
0x18001684e  movups  xmmword ptr [rsp+278h+hMem], xmm0
0x180016853  movups  xmmword ptr [rsp+278h+DestinationString.Length], xmm1
0x180016858  cmp     [rcx+8], rbx
0x18001685c  jnz     loc_18001697E
0x180016862  mov     rcx, [rcx+18h]; lpLibFileName
0x180016866  test    rcx, rcx
0x180016869  jz      loc_180016962
0x18001686f  xor     r8d, r8d; dwFlags
0x180016872  xor     edx, edx; hFile
0x180016874  call    cs:__imp_LoadLibraryExW
0x18001687a  mov     [rdi+8], rax
0x18001687e  test    rax, rax
0x180016881  jnz     short loc_1800168C7
0x180016883  mov     rcx, cs:WPP_GLOBAL_Control
0x18001688a  lea     rax, WPP_GLOBAL_Control
0x180016891  cmp     rcx, rax
0x180016894  jz      short loc_1800168BD
0x180016896  test    byte ptr [rcx+1Ch], 1
0x18001689a  jz      short loc_1800168BD
0x18001689c  call    cs:__imp_GetLastError
0x1800168a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168a9  lea     edx, [rbx+10h]
0x1800168ac  mov     r9, [rdi+18h]
0x1800168b0  mov     [rsp+278h+var_258], eax
0x1800168b4  mov     rcx, [rcx+10h]
0x1800168b8  call    WPP_SF_SL
0x1800168bd  mov     ebx, 0C0000142h
0x1800168c2  jmp     loc_180016967
0x1800168c7  mov     r8d, 105h; nSize
0x1800168cd  lea     rdx, [rsp+278h+Filename]; lpFilename
0x1800168d2  mov     rcx, rax; hModule
0x1800168d5  call    cs:__imp_GetModuleFileNameW
0x1800168db  test    eax, eax
0x1800168dd  jz      short loc_180016926
0x1800168df  cmp     eax, 105h
0x1800168e4  jz      short loc_180016926
0x1800168e6  lea     rdx, [rsp+278h+Filename]; SourceString
0x1800168eb  lea     rcx, [rsp+278h+DestinationString]; DestinationString
0x1800168f0  call    cs:__imp_RtlInitUnicodeString
0x1800168f6  lea     rdx, [rsp+278h+DestinationString]; struct _UNICODE_STRING *
0x1800168fb  lea     rcx, [rsp+278h+hMem]; struct _UNICODE_STRING *
0x180016900  call    ?SecpDuplicateString@@YAHPEAU_UNICODE_STRING@@0@Z; SecpDuplicateString(_UNICODE_STRING *,_UNICODE_STRING *)
0x180016905  test    eax, eax
0x180016907  jnz     short loc_180016910
0x180016909  mov     ebx, 0C0000017h
0x18001690e  jmp     short loc_180016967
0x180016910  mov     rcx, [rdi+18h]; hMem
0x180016914  call    cs:__imp_LocalFree
0x18001691a  movups  xmm0, xmmword ptr [rsp+278h+hMem]
0x18001691f  movdqu  xmmword ptr [rdi+10h], xmm0
0x180016924  jmp     short loc_18001698E
0x180016926  mov     rcx, cs:WPP_GLOBAL_Control
0x18001692d  lea     rax, WPP_GLOBAL_Control
0x180016934  cmp     rcx, rax
0x180016937  jz      short loc_180016962
0x180016939  test    byte ptr [rcx+1Ch], 1
0x18001693d  jz      short loc_180016962
0x18001693f  call    cs:__imp_GetLastError
0x180016945  mov     rcx, cs:WPP_GLOBAL_Control
0x18001694c  mov     edx, 11h
0x180016951  mov     r9, [rdi+18h]
0x180016955  mov     [rsp+278h+var_258], eax
0x180016959  mov     rcx, [rcx+10h]
0x18001695d  call    WPP_SF_SL
0x180016962  mov     ebx, 0C00000E5h
0x180016967  mov     rcx, [rdi+8]; hLibModule
0x18001696b  test    rcx, rcx
0x18001696e  jz      short loc_18001697E
0x180016970  call    cs:__imp_FreeLibrary
0x180016976  mov     qword ptr [rdi+8], 0
0x18001697e  mov     rcx, [rsp+278h+hMem+8]; hMem
0x180016983  test    rcx, rcx
0x180016986  jz      short loc_18001698E
0x180016988  call    cs:__imp_LocalFree
0x18001698e  mov     eax, ebx
0x180016990  mov     rcx, [rsp+278h+var_18]
0x180016998  xor     rcx, rsp; StackCookie
0x18001699b  call    __security_check_cookie
0x1800169a0  mov     rbx, [rsp+278h+arg_8]
0x1800169a8  add     rsp, 270h
0x1800169af  pop     rdi
0x1800169b0  retn
```
