# LoadWinsParam

- ea: `0x18006ca24`
- end: `0x18006cc4c`
- name: `LoadWinsParam`
- size: `552`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18006c42c`

## callees

- `0x180020bdc`
- `0x18006ca24`
- `0x18006d288`
- `0x18006f864`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cae0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cc0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cc0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006cb8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006cb8a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006cad2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006cad2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cbfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cc1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cbfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cc1a`

## string_xrefs

- `0x18006cbb4`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18006cbcd`: `RegOpenKeyEx(%ws) failed and returned %d`

## pseudocode

```c
__int64 __fastcall LoadWinsParam(HKEY hKey, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  size_t v6; // rbx
  wchar_t *v7; // rsi
  DWORD LastError; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  HKEY hKeya; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKeya = 0;
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800AB328 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        xmmword_1800AB328,
        L"LoadWinsParam");
  }
  else
  {
    TraceHlp("LoadWinsParam");
  }
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(*(_QWORD *)(a2 + 8) + 2 * v4) );
  v5 = (unsigned int)(v4 + 7);
  v6 = (unsigned int)v5;
  v7 = (wchar_t *)LocalAlloc(0x40u, 2 * v5);
  if ( v7 )
  {
    StringCchPrintfW(v7, v6, L"%s%s", L"Tcpip_", *(_QWORD *)(a2 + 8));
    v10 = RegOpenKeyExW(hKey, v7, 0, 0x20019u, &hKeya);
    v9 = v10;
    if ( v10 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( unk_1800AB320 )
        {
          LOWORD(v13) = 0;
          FormatRRASErrorString(&v13, L"RegOpenKeyEx(%ws) failed and returned %d", v7, v10);
LABEL_11:
          ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, unk_1800AB320, &v13);
        }
      }
      else
      {
        TraceHlp("RegOpenKeyEx(%ws) failed and returned %d");
      }
    }
    else
    {
      RegQueryValueWithAllocW(hKeya, L"NameServerList");
    }
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !unk_1800AB320 )
        goto LABEL_19;
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"LocalAlloc failed and returned %d", LastError);
      goto LABEL_11;
    }
    TraceHlp("LocalAlloc failed and returned %d");
  }
LABEL_19:
  LocalFree(v7);
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v9 )
  {
    LocalFree(*(HLOCAL *)(a2 + 112));
    *(_QWORD *)(a2 + 112) = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18006ca24  mov     [rsp-8+arg_10], rbx
0x18006ca29  push    rbp
0x18006ca2a  push    rsi
0x18006ca2b  push    rdi
0x18006ca2c  push    r14
0x18006ca2e  push    r15
0x18006ca30  lea     rbp, [rsp-750h]
0x18006ca38  sub     rsp, 850h
0x18006ca3f  mov     rax, cs:__security_cookie
0x18006ca46  xor     rax, rsp
0x18006ca49  mov     [rbp+770h+var_30], rax
0x18006ca50  mov     rdi, rdx
0x18006ca53  mov     r14, rcx
0x18006ca56  xor     r15d, r15d
0x18006ca59  lea     rcx, [rsp+870h+var_82C]; void *
0x18006ca5e  xor     edx, edx; Val
0x18006ca60  mov     [rsp+870h+hKey], r15
0x18006ca65  mov     r8d, 7FCh; Size
0x18006ca6b  mov     [rsp+870h+var_830], r15d
0x18006ca70  call    memset_0
0x18006ca75  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006ca7c  jz      short loc_18006CAA6
0x18006ca7e  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006ca85  test    rdx, rdx
0x18006ca88  jz      short loc_18006CAB2
0x18006ca8a  mov     rcx, cs:gIphlpEtwContext
0x18006ca91  lea     r8, aLoadwinsparam_0; "LoadWinsParam"
0x18006ca98  mov     rax, cs:gIphlpTemplateFunc
0x18006ca9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006caa4  jmp     short loc_18006CAB2
0x18006caa6  lea     rcx, aLoadwinsparam; "LoadWinsParam"
0x18006caad  call    TraceHlp
0x18006cab2  mov     rcx, [rdi+8]
0x18006cab6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006caba  inc     rax
0x18006cabd  cmp     [rcx+rax*2], r15w
0x18006cac2  jnz     short loc_18006CABA
0x18006cac4  add     eax, 7
0x18006cac7  mov     ecx, 40h ; '@'; uFlags
0x18006cacc  mov     ebx, eax
0x18006cace  lea     rdx, [rax+rax]; uBytes
0x18006cad2  call    cs:__imp_LocalAlloc
0x18006cad8  mov     rsi, rax
0x18006cadb  test    rax, rax
0x18006cade  jnz     short loc_18006CB4F
0x18006cae0  call    cs:__imp_GetLastError
0x18006cae6  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006caed  mov     ebx, eax
0x18006caef  jz      short loc_18006CB3C
0x18006caf1  cmp     qword ptr cs:unk_1800AB320, r15
0x18006caf8  jz      loc_18006CBF9
0x18006cafe  mov     r8d, eax
0x18006cb01  mov     word ptr [rsp+870h+var_830], r15w
0x18006cb07  lea     rdx, aLocalallocFail_2; "LocalAlloc failed and returned %d"
0x18006cb0e  lea     rcx, [rsp+870h+var_830]
0x18006cb13  call    FormatRRASErrorString
0x18006cb18  mov     rdx, qword ptr cs:unk_1800AB320
0x18006cb1f  lea     r8, [rsp+870h+var_830]
0x18006cb24  mov     rcx, cs:gIphlpEtwContext
0x18006cb2b  mov     rax, cs:gIphlpTemplateFunc
0x18006cb32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cb37  jmp     loc_18006CBF9
0x18006cb3c  mov     edx, eax
0x18006cb3e  lea     rcx, aLocalallocFail_0; "LocalAlloc failed and returned %d"
0x18006cb45  call    TraceHlp
0x18006cb4a  jmp     loc_18006CBF9
0x18006cb4f  mov     rax, [rdi+8]
0x18006cb53  lea     r9, aTcpip; "Tcpip_"
0x18006cb5a  lea     r8, aSS_0; "%s%s"
0x18006cb61  mov     [rsp+870h+phkResult], rax
0x18006cb66  mov     rdx, rbx; cchDest
0x18006cb69  mov     rcx, rsi; pszDest
0x18006cb6c  call    StringCchPrintfW
0x18006cb71  lea     rax, [rsp+870h+hKey]
0x18006cb76  mov     r9d, 20019h; samDesired
0x18006cb7c  xor     r8d, r8d; ulOptions
0x18006cb7f  mov     [rsp+870h+phkResult], rax; phkResult
0x18006cb84  mov     rdx, rsi; lpSubKey
0x18006cb87  mov     rcx, r14; hKey
0x18006cb8a  call    cs:__imp_RegOpenKeyExW
0x18006cb90  mov     ebx, eax
0x18006cb92  test    eax, eax
0x18006cb94  jz      short loc_18006CBDE
0x18006cb96  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006cb9d  jz      short loc_18006CBCA
0x18006cb9f  cmp     qword ptr cs:unk_1800AB320, r15
0x18006cba6  jz      short loc_18006CBF9
0x18006cba8  mov     r9d, eax
0x18006cbab  mov     word ptr [rsp+870h+var_830], r15w
0x18006cbb1  mov     r8, rsi
0x18006cbb4  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006cbbb  lea     rcx, [rsp+870h+var_830]
0x18006cbc0  call    FormatRRASErrorString
0x18006cbc5  jmp     loc_18006CB18
0x18006cbca  mov     r8d, eax
0x18006cbcd  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006cbd4  mov     rdx, rsi
0x18006cbd7  call    TraceHlp
0x18006cbdc  jmp     short loc_18006CBF9
0x18006cbde  mov     rcx, [rsp+870h+hKey]; hKey
0x18006cbe3  lea     r9, [rdi+70h]
0x18006cbe7  mov     r8d, 7
0x18006cbed  lea     rdx, aNameserverlist; "NameServerList"
0x18006cbf4  call    RegQueryValueWithAllocW
0x18006cbf9  mov     rcx, rsi; hMem
0x18006cbfc  call    cs:__imp_LocalFree
0x18006cc02  mov     rcx, [rsp+870h+hKey]; hKey
0x18006cc07  test    rcx, rcx
0x18006cc0a  jz      short loc_18006CC12
0x18006cc0c  call    cs:__imp_RegCloseKey
0x18006cc12  test    ebx, ebx
0x18006cc14  jz      short loc_18006CC24
0x18006cc16  mov     rcx, [rdi+70h]; hMem
0x18006cc1a  call    cs:__imp_LocalFree
0x18006cc20  mov     [rdi+70h], r15
0x18006cc24  mov     eax, ebx
0x18006cc26  mov     rcx, [rbp+770h+var_30]
0x18006cc2d  xor     rcx, rsp; StackCookie
0x18006cc30  call    __security_check_cookie
0x18006cc35  mov     rbx, [rsp+870h+arg_10]
0x18006cc3d  add     rsp, 850h
0x18006cc44  pop     r15
0x18006cc46  pop     r14
0x18006cc48  pop     rdi
0x18006cc49  pop     rsi
0x18006cc4a  pop     rbp
0x18006cc4b  retn
```
