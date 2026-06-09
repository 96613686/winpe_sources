# CWdsMetadataStoreManagementClient::Initialize(void)

- ea: `0x18000d494`
- end: `0x18000d539`
- name: `?Initialize@CWdsMetadataStoreManagementClient@@QEAAKXZ`
- size: `165`
- prototype: `unsigned int __fastcall(CWdsMetadataStoreManagementClient *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e14`
- `0x180002268`

## callees

- `0x18000d494`
- `0x180014d58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d4c0`
- `KERNEL32!GetLastError` at `0x18000d4fd`
- `KERNEL32!GetLastError` at `0x18000d4c0`
- `KERNEL32!GetLastError` at `0x18000d4fd`
- `KERNEL32!GetProcAddress` at `0x18000d4ef`
- `KERNEL32!GetProcAddress` at `0x18000d4ef`
- `KERNEL32!FreeLibrary` at `0x18000d526`
- `KERNEL32!FreeLibrary` at `0x18000d526`
- `KERNEL32!GetModuleHandleExW` at `0x18000d4b6`
- `KERNEL32!GetModuleHandleExW` at `0x18000d4b6`

## string_xrefs

- `0x18000d4cc`: `base\eco\wds\lib\metadata\com\wdsmetadatastoremanagementclient.cpp`

## pseudocode

```c
__int64 __fastcall CWdsMetadataStoreManagementClient::Initialize(CWdsMetadataStoreManagementClient *this)
{
  unsigned int v2; // ebx
  DWORD LastError; // eax
  const char *v4; // rdx
  unsigned int v5; // r9d
  FARPROC ProcAddress; // rcx
  HMODULE v7; // rax
  HMODULE phModule; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  phModule = 0;
  if ( GetModuleHandleExW(0, L"wdsmdmgr", &phModule) )
  {
    ProcAddress = GetProcAddress(phModule, "MetadataStoreManagementClientRequest");
    if ( ProcAddress )
    {
      v7 = phModule;
      phModule = 0;
      *(_QWORD *)this = v7;
      *((_QWORD *)this + 1) = ProcAddress;
      goto LABEL_8;
    }
    LastError = GetLastError();
    v5 = 110;
  }
  else
  {
    LastError = GetLastError();
    v5 = 103;
  }
  v2 = ElValidateWin32(LastError, v4, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp", v5);
  if ( !v2 )
    v2 = 31;
LABEL_8:
  if ( phModule )
    FreeLibrary(phModule);
  return v2;
}

```

## disassembly

```asm
0x18000d494  mov     [rsp+arg_0], rbx
0x18000d499  push    rdi
0x18000d49a  sub     rsp, 20h
0x18000d49e  mov     rdi, rcx
0x18000d4a1  lea     r8, [rsp+28h+phModule]; phModule
0x18000d4a6  xor     ebx, ebx
0x18000d4a8  lea     rdx, aWdsmdmgr; "wdsmdmgr"
0x18000d4af  and     [rsp+28h+phModule], rbx
0x18000d4b4  xor     ecx, ecx; dwFlags
0x18000d4b6  call    cs:__imp_GetModuleHandleExW
0x18000d4bc  test    eax, eax
0x18000d4be  jnz     short loc_18000D4E3
0x18000d4c0  call    cs:__imp_GetLastError
0x18000d4c6  lea     r9d, [rbx+67h]; unsigned int
0x18000d4ca  mov     ecx, eax; unsigned int
0x18000d4cc  lea     r8, aBaseEcoWdsLibM_1; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000d4d3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d4d8  mov     ebx, eax
0x18000d4da  test    eax, eax
0x18000d4dc  jnz     short loc_18000D51C
0x18000d4de  lea     ebx, [rax+1Fh]
0x18000d4e1  jmp     short loc_18000D51C
0x18000d4e3  mov     rcx, [rsp+28h+phModule]; hModule
0x18000d4e8  lea     rdx, aMetadatastorem; "MetadataStoreManagementClientRequest"
0x18000d4ef  call    cs:__imp_GetProcAddress
0x18000d4f5  mov     rcx, rax
0x18000d4f8  test    rax, rax
0x18000d4fb  jnz     short loc_18000D50B
0x18000d4fd  call    cs:__imp_GetLastError
0x18000d503  mov     r9d, 6Eh ; 'n'
0x18000d509  jmp     short loc_18000D4CA
0x18000d50b  mov     rax, [rsp+28h+phModule]
0x18000d510  and     [rsp+28h+phModule], rbx
0x18000d515  mov     [rdi], rax
0x18000d518  mov     [rdi+8], rcx
0x18000d51c  mov     rcx, [rsp+28h+phModule]; hLibModule
0x18000d521  test    rcx, rcx
0x18000d524  jz      short loc_18000D52C
0x18000d526  call    cs:__imp_FreeLibrary
0x18000d52c  mov     eax, ebx
0x18000d52e  mov     rbx, [rsp+28h+arg_0]
0x18000d533  add     rsp, 20h
0x18000d537  pop     rdi
0x18000d538  retn
```
