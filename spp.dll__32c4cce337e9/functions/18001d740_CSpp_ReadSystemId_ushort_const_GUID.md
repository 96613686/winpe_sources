# CSpp::_ReadSystemId(ushort const *,_GUID *)

- ea: `0x18001d740`
- end: `0x18001d976`
- name: `?_ReadSystemId@CSpp@@AEAAJPEBGPEAU_GUID@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(CSpp *this, const unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000b490`
- `0x180018844`

## callees

- `0x18001cac0`
- `0x18001d740`
- `0x180020908`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x180035b00`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001d85c`
- `KERNEL32!CreateFileW` at `0x18001d85c`
- `KERNEL32!ReadFile` at `0x18001d8a9`
- `KERNEL32!ReadFile` at `0x18001d8a9`
- `KERNEL32!CloseHandle` at `0x18001d927`
- `KERNEL32!CloseHandle` at `0x18001d927`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d8ff`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d8ff`

## string_xrefs

- `0x18001d7a1`: `CSpp::_ReadSystemId`

## pseudocode

```c
__int64 __fastcall CSpp::_ReadSystemId(CSpp *this, const unsigned __int16 *a2, struct _GUID *a3)
{
  __int64 v5; // rcx
  struct _GUID *v6; // rax
  HRESULT SystemIdFilename; // ebx
  __int16 v8; // ax
  __int64 v9; // rcx
  HANDLE FileW; // rdi
  __int64 v11; // rcx
  __int16 v12; // ax
  __int64 v13; // rdx
  __int64 v14; // r8
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-79h] BYREF
  int v17; // [rsp+48h] [rbp-71h] BYREF
  __int16 v18; // [rsp+4Ch] [rbp-6Dh]
  __int16 v19; // [rsp+4Eh] [rbp-6Bh]
  LPCWSTR lpFileName[2]; // [rsp+80h] [rbp-39h] BYREF
  GUID pclsid; // [rsp+90h] [rbp-29h] BYREF
  OLECHAR Buffer[40]; // [rsp+A0h] [rbp-19h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, a2);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CSpp::_ReadSystemId", 2903, 1);
  lpFileName[1] = 0;
  lpFileName[0] = &FileName;
  memset_0(Buffer, 0, 0x4Eu);
  NumberOfBytesRead = 0;
  pclsid = GUID_NULL;
  if ( !a3 )
  {
    SystemIdFilename = -2147024809;
    v8 = 2914;
    v17 = -2147024809;
    goto LABEL_20;
  }
  v5 = 16;
  v6 = a3;
  do
  {
    LOBYTE(v6->Data1) = 0;
    v6 = (struct _GUID *)((char *)v6 + 1);
    --v5;
  }
  while ( v5 );
  v17 = 0;
  v18 = 2914;
  SystemIdFilename = CSpp::_MakeSystemIdFilename(0, a2, (struct CBsString *)lpFileName);
  v17 = SystemIdFilename;
  v8 = 2916;
  if ( SystemIdFilename < 0 )
    goto LABEL_20;
  v18 = 2916;
  FileW = CreateFileW(lpFileName[0], 1u, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    SystemIdFilename = GetLastFailureAsHRESULT(v9);
    v17 = SystemIdFilename;
    v8 = 2919;
LABEL_20:
    v19 = v8;
    goto LABEL_21;
  }
  v17 = 0;
  v18 = 2919;
  if ( !ReadFile(FileW, Buffer, 0x4Cu, &NumberOfBytesRead, 0) )
  {
    SystemIdFilename = GetLastFailureAsHRESULT(v11);
    v17 = SystemIdFilename;
    v12 = 2923;
LABEL_12:
    v19 = v12;
    goto LABEL_17;
  }
  v18 = 2923;
  v12 = 2924;
  if ( NumberOfBytesRead != 76 )
  {
    SystemIdFilename = -2147418113;
    v17 = -2147418113;
    goto LABEL_12;
  }
  v18 = 2924;
  v17 = 0;
  Buffer[38] = 0;
  SystemIdFilename = CLSIDFromString(Buffer, &pclsid);
  v17 = SystemIdFilename;
  v12 = 2927;
  if ( SystemIdFilename < 0 )
    goto LABEL_12;
  v18 = 2927;
  *a3 = pclsid;
LABEL_17:
  if ( FileW )
  {
    CloseHandle(FileW);
    SystemIdFilename = v17;
  }
LABEL_21:
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17, v13, v14);
  return (unsigned int)SystemIdFilename;
}

```

## disassembly

```asm
0x18001d740  mov     [rsp-8+arg_0], rbx
0x18001d745  push    rbp
0x18001d746  push    rsi
0x18001d747  push    rdi
0x18001d748  lea     rbp, [rsp-47h]
0x18001d74d  sub     rsp, 100h
0x18001d754  mov     rax, cs:__security_cookie
0x18001d75b  xor     rax, rsp
0x18001d75e  mov     [rbp+57h+var_20], rax
0x18001d762  mov     rsi, r8
0x18001d765  mov     rbx, rdx
0x18001d768  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d76f  lea     rax, WPP_GLOBAL_Control
0x18001d776  cmp     rcx, rax
0x18001d779  jz      short loc_18001D79C
0x18001d77b  test    dword ptr [rcx+1Ch], 20000000h
0x18001d782  jz      short loc_18001D79C
0x18001d784  mov     rcx, [rcx+10h]
0x18001d788  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001d78f  mov     edx, 1Dh
0x18001d794  mov     r9, rbx
0x18001d797  call    WPP_SF_S
0x18001d79c  mov     edi, 1
0x18001d7a1  lea     rdx, aCsppReadsystem; "CSpp::_ReadSystemId"
0x18001d7a8  mov     r9d, edi; unsigned __int16
0x18001d7ab  lea     rcx, [rbp+57h+var_C8]; this
0x18001d7af  mov     r8d, 0B57h; unsigned __int16
0x18001d7b5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001d7ba  lea     rax, FileName
0x18001d7c1  mov     [rbp+57h+var_88], 0
0x18001d7c9  xor     edx, edx; Val
0x18001d7cb  mov     [rbp+57h+lpFileName], rax
0x18001d7cf  lea     r8d, [rdi+4Dh]; Size
0x18001d7d3  lea     rcx, [rbp+57h+Buffer]; void *
0x18001d7d7  call    memset_0
0x18001d7dc  mov     [rbp+57h+NumberOfBytesRead], 0
0x18001d7e3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001d7ea  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18001d7ef  test    rsi, rsi
0x18001d7f2  jz      loc_18001D932
0x18001d7f8  lea     ecx, [rdi+0Fh]
0x18001d7fb  mov     rax, rsi
0x18001d7fe  mov     byte ptr [rax], 0
0x18001d801  add     rax, rdi
0x18001d804  sub     rcx, rdi; this
0x18001d807  jnz     short loc_18001D7FE
0x18001d809  mov     eax, 0B62h
0x18001d80e  mov     [rbp+57h+var_C8], ecx
0x18001d811  lea     r8, [rbp+57h+lpFileName]; struct CBsString *
0x18001d815  mov     [rbp+57h+var_C4], ax
0x18001d819  mov     rdx, rbx; unsigned __int16 *
0x18001d81c  call    ?_MakeSystemIdFilename@CSpp@@AEAAJPEBGPEAVCBsString@@@Z; CSpp::_MakeSystemIdFilename(ushort const *,CBsString *)
0x18001d821  mov     ebx, eax
0x18001d823  mov     [rbp+57h+var_C8], eax
0x18001d826  test    eax, eax
0x18001d828  mov     eax, 0B64h
0x18001d82d  js      loc_18001D93F
0x18001d833  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18001d837  xor     r9d, r9d; lpSecurityAttributes
0x18001d83a  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x18001d843  mov     r8d, edi; dwShareMode
0x18001d846  mov     [rsp+110h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001d84e  mov     edx, edi; dwDesiredAccess
0x18001d850  mov     [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x18001d858  mov     [rbp+57h+var_C4], ax
0x18001d85c  call    cs:__imp_CreateFileW
0x18001d862  mov     rdi, rax
0x18001d865  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d869  jnz     short loc_18001D87F
0x18001d86b  call    GetLastFailureAsHRESULT
0x18001d870  mov     ebx, eax
0x18001d872  mov     [rbp+57h+var_C8], eax
0x18001d875  mov     eax, 0B67h
0x18001d87a  jmp     loc_18001D93F
0x18001d87f  mov     eax, 0B67h
0x18001d884  mov     [rbp+57h+var_C8], 0
0x18001d88b  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001d88f  mov     [rbp+57h+var_C4], ax
0x18001d893  mov     r8d, 4Ch ; 'L'; nNumberOfBytesToRead
0x18001d899  mov     qword ptr [rsp+110h+dwCreationDisposition], 0; lpOverlapped
0x18001d8a2  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18001d8a6  mov     rcx, rdi; hFile
0x18001d8a9  call    cs:__imp_ReadFile
0x18001d8af  test    eax, eax
0x18001d8b1  jnz     short loc_18001D8C8
0x18001d8b3  call    GetLastFailureAsHRESULT
0x18001d8b8  mov     ebx, eax
0x18001d8ba  mov     [rbp+57h+var_C8], eax
0x18001d8bd  mov     eax, 0B6Bh
0x18001d8c2  mov     [rbp+57h+var_C2], ax
0x18001d8c6  jmp     short loc_18001D91F
0x18001d8c8  cmp     [rbp+57h+NumberOfBytesRead], 4Ch ; 'L'
0x18001d8cc  mov     eax, 0B6Bh
0x18001d8d1  mov     [rbp+57h+var_C4], ax
0x18001d8d5  mov     eax, 0B6Ch
0x18001d8da  jz      short loc_18001D8E6
0x18001d8dc  mov     ebx, 8000FFFFh
0x18001d8e1  mov     [rbp+57h+var_C8], ebx
0x18001d8e4  jmp     short loc_18001D8C2
0x18001d8e6  mov     [rbp+57h+var_C4], ax
0x18001d8ea  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18001d8ee  xor     eax, eax
0x18001d8f0  mov     [rbp+57h+var_C8], 0
0x18001d8f7  lea     rcx, [rbp+57h+Buffer]; lpsz
0x18001d8fb  mov     [rbp+57h+var_24], ax
0x18001d8ff  call    cs:__imp_CLSIDFromString
0x18001d905  mov     ebx, eax
0x18001d907  mov     [rbp+57h+var_C8], eax
0x18001d90a  test    eax, eax
0x18001d90c  mov     eax, 0B6Fh
0x18001d911  js      short loc_18001D8C2
0x18001d913  movups  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x18001d917  mov     [rbp+57h+var_C4], ax
0x18001d91b  movdqu  xmmword ptr [rsi], xmm0
0x18001d91f  test    rdi, rdi
0x18001d922  jz      short loc_18001D943
0x18001d924  mov     rcx, rdi; hObject
0x18001d927  call    cs:__imp_CloseHandle
0x18001d92d  mov     ebx, [rbp+57h+var_C8]
0x18001d930  jmp     short loc_18001D943
0x18001d932  mov     ebx, 80070057h
0x18001d937  mov     eax, 0B62h
0x18001d93c  mov     [rbp+57h+var_C8], ebx
0x18001d93f  mov     [rbp+57h+var_C2], ax
0x18001d943  lea     rcx, [rbp+57h+lpFileName]; this
0x18001d947  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001d94c  lea     rcx, [rbp+57h+var_C8]; this
0x18001d950  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001d955  mov     eax, ebx
0x18001d957  mov     rcx, [rbp+57h+var_20]
0x18001d95b  xor     rcx, rsp; StackCookie
0x18001d95e  call    __security_check_cookie
0x18001d963  mov     rbx, [rsp+110h+arg_0]
0x18001d96b  add     rsp, 100h
0x18001d972  pop     rdi
0x18001d973  pop     rsi
0x18001d974  pop     rbp
0x18001d975  retn
```
