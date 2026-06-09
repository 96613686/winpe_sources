# SampOpenRegKey(HKEY__ *,ushort const *,HKEY__ * *,void * *)

- ea: `0x18000b0ac`
- end: `0x18000b1be`
- name: `?SampOpenRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAPEAX@Z`
- size: `274`
- prototype: `int(HKEY, const unsigned __int16 *, HKEY *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000a3f0`

## callees

- `0x18000b0ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b0f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b160`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b0f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b160`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b191`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b191`
- `ntdll!NtOpenThreadToken` at `0x18000b113`
- `ntdll!NtOpenThreadToken` at `0x18000b113`
- `ntdll!NtSetInformationThread` at `0x18000b13b`
- `ntdll!NtSetInformationThread` at `0x18000b186`
- `ntdll!NtSetInformationThread` at `0x18000b13b`
- `ntdll!NtSetInformationThread` at `0x18000b186`

## pseudocode

```c
__int64 __fastcall SampOpenRegKey(HKEY a1, const unsigned __int16 *a2, HKEY *phkResult, void **a4)
{
  char v6; // si
  LSTATUS v7; // eax
  NTSTATUS v8; // ebx
  const unsigned __int16 *ThreadInformation; // [rsp+58h] [rbp+10h] BYREF

  ThreadInformation = a2;
  *phkResult = 0;
  *a4 = 0;
  v6 = 1;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 1u, phkResult);
  if ( v7 == 5 )
  {
    v8 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, a4);
    if ( v8 < 0 )
      return (unsigned int)v8;
    ThreadInformation = 0;
    v8 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( v8 < 0 )
      goto LABEL_9;
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 1u, phkResult);
  }
  else
  {
    v6 = 0;
    v8 = 0;
  }
  if ( !v7 )
    return (unsigned int)v8;
  if ( !v6 )
    goto LABEL_10;
  v8 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, a4, 8u);
LABEL_9:
  CloseHandle(*a4);
  *a4 = 0;
LABEL_10:
  if ( v8 >= 0 )
    return (unsigned int)-1073741823;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000b0ac  mov     rax, rsp
0x18000b0af  mov     [rax+8], rbx
0x18000b0b3  mov     [rax+18h], rsi
0x18000b0b7  mov     [rax+10h], rdx
0x18000b0bb  push    rdi
0x18000b0bc  push    r14
0x18000b0be  push    r15
0x18000b0c0  sub     rsp, 30h
0x18000b0c4  mov     qword ptr [r8], 0
0x18000b0cb  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Lsa"
0x18000b0d2  mov     qword ptr [r9], 0
0x18000b0d9  mov     rdi, r9
0x18000b0dc  mov     r14, r8
0x18000b0df  mov     [rax-28h], r8
0x18000b0e3  mov     esi, 1
0x18000b0e8  xor     r8d, r8d; ulOptions
0x18000b0eb  mov     r9d, esi; samDesired
0x18000b0ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b0f5  call    cs:__imp_RegOpenKeyExW
0x18000b0fb  mov     r15, 0FFFFFFFFFFFFFFFEh
0x18000b102  cmp     eax, 5
0x18000b105  jnz     short loc_18000B168
0x18000b107  mov     r9, rdi; TokenHandle
0x18000b10a  lea     edx, [rsi+3]; DesiredAccess
0x18000b10d  mov     r8b, sil; OpenAsSelf
0x18000b110  mov     rcx, r15; ThreadHandle
0x18000b113  call    cs:__imp_NtOpenThreadToken
0x18000b119  mov     ebx, eax
0x18000b11b  test    eax, eax
0x18000b11d  js      loc_18000B1A8
0x18000b123  lea     r9d, [rsi+7]; ThreadInformationLength
0x18000b127  mov     [rsp+48h+ThreadInformation], 0
0x18000b130  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x18000b135  mov     rcx, r15; ThreadHandle
0x18000b138  lea     edx, [rsi+4]; ThreadInformationClass
0x18000b13b  call    cs:__imp_NtSetInformationThread
0x18000b141  mov     ebx, eax
0x18000b143  test    eax, eax
0x18000b145  js      short loc_18000B18E
0x18000b147  mov     r9d, esi; samDesired
0x18000b14a  mov     [rsp+48h+phkResult], r14; phkResult
0x18000b14f  xor     r8d, r8d; ulOptions
0x18000b152  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Lsa"
0x18000b159  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b160  call    cs:__imp_RegOpenKeyExW
0x18000b166  jmp     short loc_18000B16D
0x18000b168  xor     sil, sil
0x18000b16b  xor     ebx, ebx
0x18000b16d  test    eax, eax
0x18000b16f  jz      short loc_18000B1A8
0x18000b171  test    sil, sil
0x18000b174  jz      short loc_18000B19E
0x18000b176  mov     r9d, 8; ThreadInformationLength
0x18000b17c  mov     r8, rdi; ThreadInformation
0x18000b17f  mov     rcx, r15; ThreadHandle
0x18000b182  lea     edx, [r9-3]; ThreadInformationClass
0x18000b186  call    cs:__imp_NtSetInformationThread
0x18000b18c  mov     ebx, eax
0x18000b18e  mov     rcx, [rdi]; hObject
0x18000b191  call    cs:__imp_CloseHandle
0x18000b197  mov     qword ptr [rdi], 0
0x18000b19e  test    ebx, ebx
0x18000b1a0  mov     eax, 0C0000001h
0x18000b1a5  cmovns  ebx, eax
0x18000b1a8  mov     rsi, [rsp+48h+arg_10]
0x18000b1ad  mov     eax, ebx
0x18000b1af  mov     rbx, [rsp+48h+arg_0]
0x18000b1b4  add     rsp, 30h
0x18000b1b8  pop     r15
0x18000b1ba  pop     r14
0x18000b1bc  pop     rdi
0x18000b1bd  retn
```
