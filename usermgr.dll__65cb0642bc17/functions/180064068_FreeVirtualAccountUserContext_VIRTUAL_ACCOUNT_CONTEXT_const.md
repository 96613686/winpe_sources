# FreeVirtualAccountUserContext(_VIRTUAL_ACCOUNT_CONTEXT const *)

- ea: `0x180064068`
- end: `0x18006419f`
- name: `?FreeVirtualAccountUserContext@@YAJPEBU_VIRTUAL_ACCOUNT_CONTEXT@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(const struct _VIRTUAL_ACCOUNT_CONTEXT *lpMem)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800269c4`
- `0x18003cc3c`

## callees

- `0x180064068`
- `0x1800d60ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064109`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064153`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064177`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064109`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064153`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064177`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800640fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064145`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064169`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800640fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064145`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064169`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064163`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064163`
- `ntdll!RtlFreeSid` at `0x180064118`
- `ntdll!RtlFreeSid` at `0x180064127`
- `ntdll!RtlFreeSid` at `0x180064136`
- `ntdll!RtlFreeSid` at `0x180064118`
- `ntdll!RtlFreeSid` at `0x180064127`
- `ntdll!RtlFreeSid` at `0x180064136`
- `ntdll!RtlInitUnicodeString` at `0x1800640b8`
- `ntdll!RtlInitUnicodeString` at `0x1800640c7`
- `ntdll!RtlInitUnicodeString` at `0x1800640b8`
- `ntdll!RtlInitUnicodeString` at `0x1800640c7`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupManageSidNameMapping` at `0x1800640da`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupManageSidNameMapping` at `0x1800640da`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180064187`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180064187`

## pseudocode

```c
__int64 __fastcall FreeVirtualAccountUserContext(PCWSTR *lpMem)
{
  unsigned int v1; // esi
  int v3; // eax
  WCHAR *v4; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // rcx
  WCHAR *v7; // rcx
  WCHAR *v8; // rcx
  WCHAR *v9; // rdi
  HANDLE v10; // rax
  WCHAR *v11; // rcx
  HANDLE v12; // rax
  __int16 v14; // [rsp+20h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+22h] [rbp-36h] BYREF
  _BYTE v16[30]; // [rsp+32h] [rbp-26h] BYREF
  PVOID Buffer; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  v14 = 0;
  Buffer = 0;
  memset(v16, 0, sizeof(v16));
  DestinationString = 0;
  if ( lpMem )
  {
    RtlInitUnicodeString((PUNICODE_STRING)&v14, (PCWSTR)*(&g_virtualAccountDomainMap + 4 * *(unsigned int *)lpMem));
    RtlInitUnicodeString((PUNICODE_STRING)((char *)&DestinationString.Buffer + 6), lpMem[1]);
    v3 = LsaLookupManageSidNameMapping(1, &v14, &Buffer);
    if ( v3 >= 0 )
    {
      v4 = (WCHAR *)lpMem[1];
      if ( v4 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4);
      }
      v6 = (WCHAR *)lpMem[3];
      if ( v6 )
        RtlFreeSid(v6);
      v7 = (WCHAR *)lpMem[2];
      if ( v7 )
        RtlFreeSid(v7);
      v8 = (WCHAR *)lpMem[4];
      if ( v8 )
        RtlFreeSid(v8);
      v9 = (WCHAR *)lpMem[5];
      if ( v9 )
      {
        v10 = GetProcessHeap();
        HeapFree(v10, 0, v9);
      }
      v11 = (WCHAR *)lpMem[6];
      if ( v11 != (WCHAR *)-1LL )
        CloseHandle(v11);
      v12 = GetProcessHeap();
      HeapFree(v12, 0, lpMem);
    }
    else
    {
      v1 = ResultFromWin32FromStatus(v3);
    }
    if ( Buffer )
      LsaLookupFreeMemory(Buffer);
  }
  return v1;
}

```

## disassembly

```asm
0x180064068  mov     r11, rsp
0x18006406b  mov     [r11+10h], rbx
0x18006406f  mov     [r11+18h], rsi
0x180064073  push    rdi
0x180064074  sub     rsp, 50h
0x180064078  xor     eax, eax
0x18006407a  xorps   xmm0, xmm0
0x18006407d  xor     esi, esi
0x18006407f  mov     [rsp+58h+var_38], ax
0x180064084  mov     [r11+8], rax
0x180064088  mov     rbx, rcx
0x18006408b  movups  xmmword ptr [rsp+58h+var_26], xmm0
0x180064090  movups  xmmword ptr [rsp+58h+var_26+0Eh], xmm0
0x180064095  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18006409a  test    rcx, rcx
0x18006409d  jz      loc_18006418D
0x1800640a3  mov     edx, [rcx]
0x1800640a5  lea     rax, ?g_virtualAccountDomainMap@@3PAU_VIRTUAL_ACCOUNT_DOMAIN_MAP@@A; _VIRTUAL_ACCOUNT_DOMAIN_MAP near * g_virtualAccountDomainMap
0x1800640ac  shl     rdx, 5
0x1800640b0  lea     rcx, [r11-38h]; DestinationString
0x1800640b4  mov     rdx, [rdx+rax]; SourceString
0x1800640b8  call    cs:__imp_RtlInitUnicodeString
0x1800640be  mov     rdx, [rbx+8]; SourceString
0x1800640c2  lea     rcx, [rsp+58h+DestinationString.Buffer+6]; DestinationString
0x1800640c7  call    cs:__imp_RtlInitUnicodeString
0x1800640cd  lea     r8, [rsp+58h+Buffer]
0x1800640d2  lea     rdx, [rsp+58h+var_38]
0x1800640d7  lea     ecx, [rsi+1]
0x1800640da  call    cs:__imp_LsaLookupManageSidNameMapping
0x1800640e0  test    eax, eax
0x1800640e2  jns     short loc_1800640F2
0x1800640e4  mov     ecx, eax; int
0x1800640e6  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x1800640eb  mov     esi, eax
0x1800640ed  jmp     loc_18006417D
0x1800640f2  mov     rdi, [rbx+8]
0x1800640f6  test    rdi, rdi
0x1800640f9  jz      short loc_18006410F
0x1800640fb  call    cs:__imp_GetProcessHeap
0x180064101  mov     r8, rdi; lpMem
0x180064104  xor     edx, edx; dwFlags
0x180064106  mov     rcx, rax; hHeap
0x180064109  call    cs:__imp_HeapFree
0x18006410f  mov     rcx, [rbx+18h]; Sid
0x180064113  test    rcx, rcx
0x180064116  jz      short loc_18006411E
0x180064118  call    cs:__imp_RtlFreeSid
0x18006411e  mov     rcx, [rbx+10h]; Sid
0x180064122  test    rcx, rcx
0x180064125  jz      short loc_18006412D
0x180064127  call    cs:__imp_RtlFreeSid
0x18006412d  mov     rcx, [rbx+20h]; Sid
0x180064131  test    rcx, rcx
0x180064134  jz      short loc_18006413C
0x180064136  call    cs:__imp_RtlFreeSid
0x18006413c  mov     rdi, [rbx+28h]
0x180064140  test    rdi, rdi
0x180064143  jz      short loc_180064159
0x180064145  call    cs:__imp_GetProcessHeap
0x18006414b  mov     r8, rdi; lpMem
0x18006414e  xor     edx, edx; dwFlags
0x180064150  mov     rcx, rax; hHeap
0x180064153  call    cs:__imp_HeapFree
0x180064159  mov     rcx, [rbx+30h]; hObject
0x18006415d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180064161  jz      short loc_180064169
0x180064163  call    cs:__imp_CloseHandle
0x180064169  call    cs:__imp_GetProcessHeap
0x18006416f  mov     r8, rbx; lpMem
0x180064172  xor     edx, edx; dwFlags
0x180064174  mov     rcx, rax; hHeap
0x180064177  call    cs:__imp_HeapFree
0x18006417d  mov     rcx, [rsp+58h+Buffer]; Buffer
0x180064182  test    rcx, rcx
0x180064185  jz      short loc_18006418D
0x180064187  call    cs:__imp_LsaLookupFreeMemory
0x18006418d  mov     rbx, [rsp+58h+arg_8]
0x180064192  mov     eax, esi
0x180064194  mov     rsi, [rsp+58h+arg_10]
0x180064199  add     rsp, 50h
0x18006419d  pop     rdi
0x18006419e  retn
```
