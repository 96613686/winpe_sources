# UbpmpGetCriticalActionsGuids(void)

- ea: `0x18002be80`
- end: `0x18002c180`
- name: `?UbpmpGetCriticalActionsGuids@@YAKXZ`
- size: `768`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18002a0cc`

## callees

- `0x18000f9a0`
- `0x180019d90`
- `0x18002ab08`
- `0x18002bc0c`
- `0x18002be80`
- `0x18003d7ea`
- `0x18003d810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bf86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bf86`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002c06f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002c06f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c158`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c158`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002bfd6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002bfd6`
- `RPCRT4!UuidFromStringW` at `0x18002c0d7`
- `RPCRT4!UuidFromStringW` at `0x18002c0d7`

## string_xrefs

- `0x18002beb8`: `CriticalTask`
- `0x18002bf33`: `OOBETask`

## pseudocode

```c
__int64 __fastcall UbpmpGetCriticalActionsGuids(unsigned __int16 *a1)
{
  int v1; // r15d
  WCHAR *v2; // r13
  void *v3; // rdi
  char *v4; // rsi
  unsigned __int16 *v5; // rcx
  unsigned int v6; // ebx
  unsigned __int16 *v7; // rcx
  unsigned __int16 *v8; // rcx
  unsigned int v9; // r14d
  DWORD i; // r12d
  char *v11; // rax
  __int64 v12; // rax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-29h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-25h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-21h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-1Dh] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-19h] BYREF
  DWORD Type; // [rsp+74h] [rbp-15h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-11h] BYREF
  DWORD v21; // [rsp+80h] [rbp-9h]
  UUID Uuid; // [rsp+88h] [rbp-1h] BYREF

  v1 = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v2 = 0;
  cchValueName = 0;
  v3 = 0;
  cbData = 0;
  v4 = 0;
  Type = 0;
  Uuid = 0;
  hKey = 0;
  g_CriticalTasks = 0;
  g_CriticalMaintenanceTasks = 0;
  g_OOBEExemptedTasks = 0;
  g_CriticalMeasuredTasks = 0;
  v6 = UbpmUtilsTaskClassStart(a1, L"CriticalTask", (struct _UBPM_SPECIAL_TASK_CLASS *)&g_CriticalTasks);
  if ( !v6 )
  {
    v6 = UbpmUtilsTaskClassStart(
           v5,
           L"CriticalMaintenance",
           (struct _UBPM_SPECIAL_TASK_CLASS *)&g_CriticalMaintenanceTasks);
    if ( !v6 )
    {
      v6 = UbpmUtilsTaskClassStart(v7, L"OOBETask", (struct _UBPM_SPECIAL_TASK_CLASS *)&g_OOBEExemptedTasks);
      if ( !v6 )
      {
        v6 = UbpmUtilsTaskClassStart(
               v8,
               L"CriticalMeasured",
               (struct _UBPM_SPECIAL_TASK_CLASS *)&g_CriticalMeasuredTasks);
        if ( !v6 )
        {
          v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Ubpm", 0, 0x20019u, &hKey);
          if ( !v6 )
          {
            v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
            if ( !v6 )
            {
              if ( cValues )
              {
                cbMaxValueLen += 2;
                ++cbMaxValueNameLen;
                v2 = (WCHAR *)UbpmAlloc(2 * cbMaxValueNameLen);
                if ( !v2 || (v3 = UbpmAlloc(cbMaxValueLen)) == 0 )
                {
                  v6 = 14;
                  goto LABEL_28;
                }
                v9 = 0;
                if ( cValues )
                {
                  for ( i = 0; i < cValues; ++i )
                  {
                    cchValueName = cbMaxValueNameLen;
                    cbData = cbMaxValueLen;
                    v6 = RegEnumValueW(hKey, i, v2, &cchValueName, 0, &Type, (LPBYTE)v3, &cbData);
                    if ( !v6 && Type == 1 )
                    {
                      v21 = (cbData >> 1) - 1;
                      *((_WORD *)v3 + v21) = 0;
                      if ( cchValueName >= 0xE
                        && !wcsncmp_0(v2, L"CriticalAction", 0xEu)
                        && v21 == 38
                        && *(_WORD *)v3 == 123
                        && *((_WORD *)v3 + 37) == 125 )
                      {
                        *((_WORD *)v3 + 37) = 0;
                        if ( !UuidFromStringW((RPC_WSTR)v3 + 1, &Uuid) )
                        {
                          if ( v9 == v1 )
                          {
                            v11 = (char *)UbpmReAlloc(v4, (unsigned int)(16 * (v1 + 5)));
                            if ( !v11 )
                              goto LABEL_28;
                            v1 += 5;
                            v4 = v11;
                          }
                          v12 = 2LL * v9++;
                          *(UUID *)&v4[8 * v12] = Uuid;
                        }
                      }
                    }
                  }
                }
                g_dwCriticalActionsCount = v9;
                *(_QWORD *)&g_pCriticalActions.Data1 = v4;
              }
              v6 = 0;
              v4 = 0;
            }
          }
        }
      }
    }
  }
LABEL_28:
  UBPM_MIDL_user_free(v4);
  UBPM_MIDL_user_free(v2);
  UBPM_MIDL_user_free(v3);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18002be80  push    rbp
0x18002be82  push    rbx
0x18002be83  push    rsi
0x18002be84  push    rdi
0x18002be85  push    r12
0x18002be87  push    r13
0x18002be89  push    r14
0x18002be8b  push    r15
0x18002be8d  lea     rbp, [rsp-1Fh]
0x18002be92  sub     rsp, 0A8h
0x18002be99  mov     rax, cs:__security_cookie
0x18002bea0  xor     rax, rsp
0x18002bea3  mov     [rbp+57h+var_48], rax
0x18002bea7  xor     r15d, r15d
0x18002beaa  lea     r8, ?g_CriticalTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; struct _UBPM_SPECIAL_TASK_CLASS *
0x18002beb1  xorps   xmm0, xmm0
0x18002beb4  mov     [rbp+57h+cValues], r15d
0x18002beb8  lea     rdx, aCriticaltask; "CriticalTask"
0x18002bebf  mov     [rbp+57h+cbMaxValueNameLen], r15d
0x18002bec3  mov     [rbp+57h+cbMaxValueLen], r15d
0x18002bec7  mov     r13d, r15d
0x18002beca  mov     [rbp+57h+cchValueName], r15d
0x18002bece  mov     edi, r15d
0x18002bed1  mov     [rbp+57h+cbData], r15d
0x18002bed5  mov     esi, r15d
0x18002bed8  mov     [rbp+57h+Type], r15d
0x18002bedc  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18002bee0  mov     [rbp+57h+hKey], r15
0x18002bee4  mov     cs:?g_CriticalTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A, r15; _UBPM_SPECIAL_TASK_CLASS g_CriticalTasks
0x18002beeb  mov     cs:?g_CriticalMaintenanceTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A, r15; _UBPM_SPECIAL_TASK_CLASS g_CriticalMaintenanceTasks
0x18002bef2  mov     cs:?g_OOBEExemptedTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A, r15; _UBPM_SPECIAL_TASK_CLASS g_OOBEExemptedTasks
0x18002bef9  mov     cs:?g_CriticalMeasuredTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A, r15; _UBPM_SPECIAL_TASK_CLASS g_CriticalMeasuredTasks
0x18002bf00  call    ?UbpmUtilsTaskClassStart@@YAKPEAG0PEAU_UBPM_SPECIAL_TASK_CLASS@@@Z; UbpmUtilsTaskClassStart(ushort *,ushort *,_UBPM_SPECIAL_TASK_CLASS *)
0x18002bf05  mov     ebx, eax
0x18002bf07  test    eax, eax
0x18002bf09  jnz     loc_18002C137
0x18002bf0f  lea     r8, ?g_CriticalMaintenanceTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; struct _UBPM_SPECIAL_TASK_CLASS *
0x18002bf16  lea     rdx, aCriticalmainte; "CriticalMaintenance"
0x18002bf1d  call    ?UbpmUtilsTaskClassStart@@YAKPEAG0PEAU_UBPM_SPECIAL_TASK_CLASS@@@Z; UbpmUtilsTaskClassStart(ushort *,ushort *,_UBPM_SPECIAL_TASK_CLASS *)
0x18002bf22  mov     ebx, eax
0x18002bf24  test    eax, eax
0x18002bf26  jnz     loc_18002C137
0x18002bf2c  lea     r8, ?g_OOBEExemptedTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; struct _UBPM_SPECIAL_TASK_CLASS *
0x18002bf33  lea     rdx, aOobetask; "OOBETask"
0x18002bf3a  call    ?UbpmUtilsTaskClassStart@@YAKPEAG0PEAU_UBPM_SPECIAL_TASK_CLASS@@@Z; UbpmUtilsTaskClassStart(ushort *,ushort *,_UBPM_SPECIAL_TASK_CLASS *)
0x18002bf3f  mov     ebx, eax
0x18002bf41  test    eax, eax
0x18002bf43  jnz     loc_18002C137
0x18002bf49  lea     r8, ?g_CriticalMeasuredTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; struct _UBPM_SPECIAL_TASK_CLASS *
0x18002bf50  lea     rdx, aCriticalmeasur; "CriticalMeasured"
0x18002bf57  call    ?UbpmUtilsTaskClassStart@@YAKPEAG0PEAU_UBPM_SPECIAL_TASK_CLASS@@@Z; UbpmUtilsTaskClassStart(ushort *,ushort *,_UBPM_SPECIAL_TASK_CLASS *)
0x18002bf5c  mov     ebx, eax
0x18002bf5e  test    eax, eax
0x18002bf60  jnz     loc_18002C137
0x18002bf66  lea     rax, [rbp+57h+hKey]
0x18002bf6a  mov     r9d, 20019h; samDesired
0x18002bf70  xor     r8d, r8d; ulOptions
0x18002bf73  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002bf78  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Ubp"...
0x18002bf7f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bf86  call    cs:__imp_RegOpenKeyExW
0x18002bf8c  mov     ebx, eax
0x18002bf8e  test    eax, eax
0x18002bf90  jnz     loc_18002C137
0x18002bf96  mov     rcx, [rbp+57h+hKey]; hKey
0x18002bf9a  lea     rax, [rbp+57h+cbMaxValueLen]
0x18002bf9e  mov     [rsp+0E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002bfa3  xor     r9d, r9d; lpReserved
0x18002bfa6  mov     [rsp+0E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002bfab  xor     r8d, r8d; lpcchClass
0x18002bfae  mov     [rsp+0E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18002bfb3  xor     edx, edx; lpClass
0x18002bfb5  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18002bfb9  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18002bfbe  lea     rax, [rbp+57h+cValues]
0x18002bfc2  mov     [rsp+0E0h+lpcValues], rax; lpcValues
0x18002bfc7  mov     [rsp+0E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002bfcc  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18002bfd1  mov     [rsp+0E0h+phkResult], r15; lpcSubKeys
0x18002bfd6  call    cs:__imp_RegQueryInfoKeyW
0x18002bfdc  mov     ebx, eax
0x18002bfde  test    eax, eax
0x18002bfe0  jnz     loc_18002C137
0x18002bfe6  cmp     [rbp+57h+cValues], r15d
0x18002bfea  jbe     loc_18002C131
0x18002bff0  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18002bff3  add     [rbp+57h+cbMaxValueLen], 2
0x18002bff7  inc     ecx
0x18002bff9  mov     [rbp+57h+cbMaxValueNameLen], ecx
0x18002bffc  add     ecx, ecx; Size
0x18002bffe  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002c003  mov     r13, rax
0x18002c006  test    rax, rax
0x18002c009  jnz     short loc_18002C015
0x18002c00b  mov     ebx, 0Eh
0x18002c010  jmp     loc_18002C137
0x18002c015  mov     ecx, [rbp+57h+cbMaxValueLen]; Size
0x18002c018  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002c01d  mov     rdi, rax
0x18002c020  test    rax, rax
0x18002c023  jz      short loc_18002C00B
0x18002c025  mov     r14d, r15d
0x18002c028  cmp     [rbp+57h+cValues], r15d
0x18002c02c  jbe     loc_18002C123
0x18002c032  mov     r12d, r15d
0x18002c035  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18002c038  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18002c03c  mov     rcx, [rbp+57h+hKey]; hKey
0x18002c040  mov     r8, r13; lpValueName
0x18002c043  mov     [rbp+57h+cchValueName], eax
0x18002c046  mov     edx, r12d; dwIndex
0x18002c049  mov     eax, [rbp+57h+cbMaxValueLen]
0x18002c04c  mov     [rbp+57h+cbData], eax
0x18002c04f  lea     rax, [rbp+57h+cbData]
0x18002c053  mov     [rsp+0E0h+lpcValues], rax; lpcbData
0x18002c058  lea     rax, [rbp+57h+Type]
0x18002c05c  mov     [rsp+0E0h+lpcbMaxClassLen], rdi; lpData
0x18002c061  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpType
0x18002c066  mov     [rsp+0E0h+phkResult], 0; lpReserved
0x18002c06f  call    cs:__imp_RegEnumValueW
0x18002c075  mov     ebx, eax
0x18002c077  test    eax, eax
0x18002c079  jnz     loc_18002C113
0x18002c07f  cmp     [rbp+57h+Type], 1
0x18002c083  jnz     loc_18002C113
0x18002c089  mov     eax, [rbp+57h+cbData]
0x18002c08c  shr     eax, 1
0x18002c08e  dec     eax
0x18002c090  mov     ecx, eax
0x18002c092  mov     [rbp+57h+var_60], eax
0x18002c095  xor     eax, eax
0x18002c097  mov     [rdi+rcx*2], ax
0x18002c09b  cmp     [rbp+57h+cchValueName], 0Eh
0x18002c09f  jb      short loc_18002C113
0x18002c0a1  lea     r8d, [rbx+0Eh]; MaxCount
0x18002c0a5  mov     rcx, r13; String1
0x18002c0a8  lea     rdx, aCriticalaction; "CriticalAction"
0x18002c0af  call    wcsncmp_0
0x18002c0b4  test    eax, eax
0x18002c0b6  jnz     short loc_18002C113
0x18002c0b8  cmp     [rbp+57h+var_60], 26h ; '&'
0x18002c0bc  jnz     short loc_18002C113
0x18002c0be  cmp     word ptr [rdi], 7Bh ; '{'
0x18002c0c2  jnz     short loc_18002C113
0x18002c0c4  cmp     word ptr [rdi+4Ah], 7Dh ; '}'
0x18002c0c9  jnz     short loc_18002C113
0x18002c0cb  lea     rcx, [rdi+2]; StringUuid
0x18002c0cf  lea     rdx, [rbp+57h+Uuid]; Uuid
0x18002c0d3  mov     [rcx+48h], ax
0x18002c0d7  call    cs:__imp_UuidFromStringW
0x18002c0dd  test    eax, eax
0x18002c0df  jnz     short loc_18002C113
0x18002c0e1  cmp     r14d, r15d
0x18002c0e4  jnz     short loc_18002C101
0x18002c0e6  lea     edx, [r15+5]
0x18002c0ea  mov     rcx, rsi; Ptr
0x18002c0ed  shl     edx, 4; Size
0x18002c0f0  call    ?UbpmReAlloc@@YAPEAXPEAXK@Z; UbpmReAlloc(void *,ulong)
0x18002c0f5  test    rax, rax
0x18002c0f8  jz      short loc_18002C137
0x18002c0fa  add     r15d, 5
0x18002c0fe  mov     rsi, rax
0x18002c101  movups  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x18002c105  mov     eax, r14d
0x18002c108  add     rax, rax
0x18002c10b  inc     r14d
0x18002c10e  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x18002c113  inc     r12d
0x18002c116  cmp     r12d, [rbp+57h+cValues]
0x18002c11a  jb      loc_18002C035
0x18002c120  xor     r15d, r15d
0x18002c123  mov     cs:?g_dwCriticalActionsCount@@3KA, r14d; ulong g_dwCriticalActionsCount
0x18002c12a  mov     qword ptr cs:?g_pCriticalActions@@3PEAU_GUID@@EA.Data1, rsi; _GUID * g_pCriticalActions ...
0x18002c131  mov     ebx, r15d
0x18002c134  mov     rsi, r15
0x18002c137  mov     rcx, rsi
0x18002c13a  call    UBPM_MIDL_user_free
0x18002c13f  mov     rcx, r13
0x18002c142  call    UBPM_MIDL_user_free
0x18002c147  mov     rcx, rdi
0x18002c14a  call    UBPM_MIDL_user_free
0x18002c14f  mov     rcx, [rbp+57h+hKey]; hKey
0x18002c153  test    rcx, rcx
0x18002c156  jz      short loc_18002C15E
0x18002c158  call    cs:__imp_RegCloseKey
0x18002c15e  mov     eax, ebx
0x18002c160  mov     rcx, [rbp+57h+var_48]
0x18002c164  xor     rcx, rsp; StackCookie
0x18002c167  call    __security_check_cookie
0x18002c16c  add     rsp, 0A8h
0x18002c173  pop     r15
0x18002c175  pop     r14
0x18002c177  pop     r13
0x18002c179  pop     r12
0x18002c17b  pop     rdi
0x18002c17c  pop     rsi
0x18002c17d  pop     rbx
0x18002c17e  pop     rbp
0x18002c17f  retn
```
