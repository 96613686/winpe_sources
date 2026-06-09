# SampEnforceClientPasswordPolicy(_UNICODE_STRING *,void *)

- ea: `0x18000a3f0`
- end: `0x18000a4fa`
- name: `?SampEnforceClientPasswordPolicy@@YAJPEAU_UNICODE_STRING@@PEAX@Z`
- size: `266`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ccb0`
- `0x18000d020`

## callees

- `0x18000a3f0`
- `0x18000a840`
- `0x18000b0ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a46f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a46f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a4ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a4ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4dc`
- `ntdll!NtSetInformationThread` at `0x18000a4d0`
- `ntdll!NtSetInformationThread` at `0x18000a4d0`

## pseudocode

```c
__int64 __fastcall SampEnforceClientPasswordPolicy(__m128i *a1, unsigned __int16 *a2)
{
  int v4; // ebx
  NTSTATUS v5; // edi
  BYTE Data[4]; // [rsp+30h] [rbp-20h] BYREF
  int v8; // [rsp+34h] [rbp-1Ch] BYREF
  void *ThreadInformation; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+30h] BYREF
  DWORD Type; // [rsp+88h] [rbp+38h] BYREF

  v8 = 1;
  hKey = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  ThreadInformation = 0;
  v4 = SampOpenRegKey((HKEY)a1, a2, &hKey, &ThreadInformation);
  if ( v4 >= 0 )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnforceFIPSRequirementForPasswordOperations", 0, &Type, Data, &cbData)
      && Type == 4
      && *(_DWORD *)Data == 1 )
    {
      v4 = SampIsCallRemote(a1, (void **)a2, &v8);
      if ( v4 < 0 || v8 )
        v4 = -1073741637;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( ThreadInformation )
  {
    v5 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    CloseHandle(ThreadInformation);
    if ( v4 >= 0 && v5 < 0 )
      return (unsigned int)v5;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a3f0  mov     [rsp-18h+arg_0], rbx
0x18000a3f5  push    rbp
0x18000a3f6  push    rsi
0x18000a3f7  push    rdi
0x18000a3f8  mov     rbp, rsp
0x18000a3fb  sub     rsp, 50h
0x18000a3ff  lea     r9, [rbp+ThreadInformation]; void **
0x18000a403  mov     [rbp+var_1C], 1
0x18000a40a  lea     r8, [rbp+hKey]; HKEY *
0x18000a40e  mov     [rbp+hKey], 0
0x18000a416  mov     rdi, rdx
0x18000a419  mov     [rbp+cbData], 0
0x18000a420  mov     rsi, rcx
0x18000a423  mov     dword ptr [rbp+Data], 0
0x18000a42a  mov     [rbp+Type], 0
0x18000a431  mov     [rbp+ThreadInformation], 0
0x18000a439  call    ?SampOpenRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAPEAX@Z; SampOpenRegKey(HKEY__ *,ushort const *,HKEY__ * *,void * *)
0x18000a43e  mov     ebx, eax
0x18000a440  test    eax, eax
0x18000a442  js      short loc_18000A4A5
0x18000a444  mov     rcx, [rbp+hKey]; hKey
0x18000a448  lea     rax, [rbp+cbData]
0x18000a44c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000a451  lea     r9, [rbp+Type]; lpType
0x18000a455  lea     rax, [rbp+Data]
0x18000a459  mov     [rbp+cbData], 4
0x18000a460  xor     r8d, r8d; lpReserved
0x18000a463  mov     [rsp+50h+lpData], rax; lpData
0x18000a468  lea     rdx, ValueName; "EnforceFIPSRequirementForPasswordOperat"...
0x18000a46f  call    cs:__imp_RegQueryValueExW
0x18000a475  test    eax, eax
0x18000a477  jnz     short loc_18000A4A5
0x18000a479  cmp     [rbp+Type], 4
0x18000a47d  jnz     short loc_18000A4A5
0x18000a47f  cmp     dword ptr [rbp+Data], 1
0x18000a483  jnz     short loc_18000A4A5
0x18000a485  lea     r8, [rbp+var_1C]; int *
0x18000a489  mov     rdx, rdi; void *
0x18000a48c  mov     rcx, rsi; struct _UNICODE_STRING *
0x18000a48f  call    ?SampIsCallRemote@@YAJPEAU_UNICODE_STRING@@PEAXPEAH@Z; SampIsCallRemote(_UNICODE_STRING *,void *,int *)
0x18000a494  mov     ebx, eax
0x18000a496  test    eax, eax
0x18000a498  js      short loc_18000A4A0
0x18000a49a  cmp     [rbp+var_1C], 0
0x18000a49e  jz      short loc_18000A4A5
0x18000a4a0  mov     ebx, 0C00000BBh
0x18000a4a5  mov     rcx, [rbp+hKey]; hKey
0x18000a4a9  test    rcx, rcx
0x18000a4ac  jz      short loc_18000A4B4
0x18000a4ae  call    cs:__imp_RegCloseKey
0x18000a4b4  cmp     [rbp+ThreadInformation], 0
0x18000a4b9  jz      short loc_18000A4EB
0x18000a4bb  mov     r9d, 8; ThreadInformationLength
0x18000a4c1  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x18000a4c5  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000a4cc  lea     edx, [r9-3]; ThreadInformationClass
0x18000a4d0  call    cs:__imp_NtSetInformationThread
0x18000a4d6  mov     rcx, [rbp+ThreadInformation]; hObject
0x18000a4da  mov     edi, eax
0x18000a4dc  call    cs:__imp_CloseHandle
0x18000a4e2  test    ebx, ebx
0x18000a4e4  js      short loc_18000A4EB
0x18000a4e6  test    edi, edi
0x18000a4e8  cmovs   ebx, edi
0x18000a4eb  mov     eax, ebx
0x18000a4ed  mov     rbx, [rsp+50h+arg_0]
0x18000a4f2  add     rsp, 50h
0x18000a4f6  pop     rdi
0x18000a4f7  pop     rsi
0x18000a4f8  pop     rbp
0x18000a4f9  retn
```
