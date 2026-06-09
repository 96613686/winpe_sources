# UbpmpGetCriticalActionsGuids(void)

- ea: `0x18002deb0`
- end: `0x18002e1cf`
- name: `?UbpmpGetCriticalActionsGuids@@YAKXZ`
- size: `799`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18002bb88`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x18002c768`
- `0x18002dc20`
- `0x18002deb0`
- `0x18004023a`
- `0x180040260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dfb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dfb6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002e0ab`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002e0ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e1a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e1a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002e00c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002e00c`
- `RPCRT4!UuidFromStringW` at `0x18002e119`
- `RPCRT4!UuidFromStringW` at `0x18002e119`

## string_xrefs

- `0x18002dee8`: `CriticalTask`
- `0x18002df63`: `OOBETask`

## pseudocode

```c
__int64 __fastcall UbpmpGetCriticalActionsGuids(unsigned __int16 *a1)
{
  int v1; // r15d
  WCHAR *v2; // r13
  void *v3; // rdi
  char *v4; // rsi
  __int64 v5; // rdx
  unsigned __int16 *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned __int16 *v10; // rcx
  unsigned __int16 *v11; // rcx
  unsigned int v12; // r14d
  DWORD i; // r12d
  char *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-29h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-25h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-21h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-1Dh] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-19h] BYREF
  DWORD Type; // [rsp+74h] [rbp-15h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-11h] BYREF
  DWORD v30; // [rsp+80h] [rbp-9h]
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
  v7 = UbpmUtilsTaskClassStart(a1, L"CriticalTask", (struct _UBPM_SPECIAL_TASK_CLASS *)&g_CriticalTasks);
  if ( !v7 )
  {
    v7 = UbpmUtilsTaskClassStart(
           v6,
           L"CriticalMaintenance",
           (struct _UBPM_SPECIAL_TASK_CLASS *)&g_CriticalMaintenanceTasks);
    if ( !v7 )
    {
      v7 = UbpmUtilsTaskClassStart(v10, L"OOBETask", (struct _UBPM_SPECIAL_TASK_CLASS *)&g_OOBEExemptedTasks);
      if ( !v7 )
      {
        v7 = UbpmUtilsTaskClassStart(
               v11,
               L"CriticalMeasured",
               (struct _UBPM_SPECIAL_TASK_CLASS *)&g_CriticalMeasuredTasks);
        if ( !v7 )
        {
          v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Ubpm", 0, 0x20019u, &hKey);
          if ( !v7 )
          {
            v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
            if ( !v7 )
            {
              if ( cValues )
              {
                cbMaxValueLen += 2;
                ++cbMaxValueNameLen;
                v2 = (WCHAR *)UbpmAlloc(2 * cbMaxValueNameLen);
                if ( !v2 || (v3 = UbpmAlloc(cbMaxValueLen)) == 0 )
                {
                  v7 = 14;
                  goto LABEL_28;
                }
                v12 = 0;
                if ( cValues )
                {
                  for ( i = 0; i < cValues; ++i )
                  {
                    cchValueName = cbMaxValueNameLen;
                    cbData = cbMaxValueLen;
                    v7 = RegEnumValueW(hKey, i, v2, &cchValueName, 0, &Type, (LPBYTE)v3, &cbData);
                    if ( !v7 && Type == 1 )
                    {
                      v30 = (cbData >> 1) - 1;
                      *((_WORD *)v3 + v30) = 0;
                      if ( cchValueName >= 0xE
                        && !wcsncmp_0(v2, L"CriticalAction", 0xEu)
                        && v30 == 38
                        && *(_WORD *)v3 == 123
                        && *((_WORD *)v3 + 37) == 125 )
                      {
                        *((_WORD *)v3 + 37) = 0;
                        if ( !UuidFromStringW((RPC_WSTR)v3 + 1, &Uuid) )
                        {
                          if ( v12 == v1 )
                          {
                            v14 = (char *)UbpmReAlloc(v4, (unsigned int)(16 * (v1 + 5)));
                            if ( !v14 )
                              goto LABEL_28;
                            v1 += 5;
                            v4 = v14;
                          }
                          v15 = 2LL * v12++;
                          *(UUID *)&v4[8 * v15] = Uuid;
                        }
                      }
                    }
                  }
                }
                g_dwCriticalActionsCount = v12;
                *(_QWORD *)&g_pCriticalActions.Data1 = v4;
              }
              v7 = 0;
              v4 = 0;
            }
          }
        }
      }
    }
  }
LABEL_28:
  UBPM_MIDL_user_free(v4, v5, v8, v9);
  UBPM_MIDL_user_free(v2, v16, v17, v18);
  UBPM_MIDL_user_free(v3, v19, v20, v21);
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x18002deb0  push    rbp
0x18002deb2  push    rbx
0x18002deb3  push    rsi
0x18002deb4  push    rdi
0x18002deb5  push    r12
0x18002deb7  push    r13
0x18002deb9  push    r14
0x18002debb  push    r15
0x18002debd  lea     rbp, [rsp-1Fh]
0x18002dec2  sub     rsp, 0A8h
0x18002dec9  mov     rax, cs:__security_cookie
0x18002ded0  xor     rax, rsp
0x18002ded3  mov     [rbp+57h+var_48], rax
0x18002ded7  xor     r15d, r15d
0x18002deda  lea     r8, ?g_CriticalTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; struct _UBPM_SPECIAL_TASK_CLASS *
0x18002dee1  xorps   xmm0, xmm0
0x18002dee4  mov     [rbp+57h+cValues], r15d
0x18002dee8  lea     rdx, aCriticaltask; "CriticalTask"
0x18002deef  mov     [rbp+57h+cbMaxValueNameLen], r15d
0x18002def3  mov     [rbp+57h+cbMaxValueLen], r15d
0x18002def7  mov     r13d, r15d
0x18002defa  mov     [rbp+57h+cchValueName], r15d
0x18002defe  mov     edi, r15d
0x18002df01  mov     [rbp+57h+cbData], r15d
0x18002df05  mov     esi, r15d
0x18002df08  mov     [rbp+57h+Type], r15d
0x18002df0c  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18002df10  mov     [rbp+57h+hKey], r15
0x18002df14  mov     cs:?g_CriticalTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A, r15; _UBPM_SPECIAL_TASK_CLASS g_CriticalTasks
0x18002df1b  mov     cs:?g_CriticalMaintenanceTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A, r15; _UBPM_SPECIAL_TASK_CLASS g_CriticalMaintenanceTasks
0x18002df22  mov     cs:?g_OOBEExemptedTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A, r15; _UBPM_SPECIAL_TASK_CLASS g_OOBEExemptedTasks
0x18002df29  mov     cs:?g_CriticalMeasuredTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A, r15; _UBPM_SPECIAL_TASK_CLASS g_CriticalMeasuredTasks
0x18002df30  call    ?UbpmUtilsTaskClassStart@@YAKPEAG0PEAU_UBPM_SPECIAL_TASK_CLASS@@@Z; UbpmUtilsTaskClassStart(ushort *,ushort *,_UBPM_SPECIAL_TASK_CLASS *)
0x18002df35  mov     ebx, eax
0x18002df37  test    eax, eax
0x18002df39  jnz     loc_18002E17F
0x18002df3f  lea     r8, ?g_CriticalMaintenanceTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; struct _UBPM_SPECIAL_TASK_CLASS *
0x18002df46  lea     rdx, aCriticalmainte; "CriticalMaintenance"
0x18002df4d  call    ?UbpmUtilsTaskClassStart@@YAKPEAG0PEAU_UBPM_SPECIAL_TASK_CLASS@@@Z; UbpmUtilsTaskClassStart(ushort *,ushort *,_UBPM_SPECIAL_TASK_CLASS *)
0x18002df52  mov     ebx, eax
0x18002df54  test    eax, eax
0x18002df56  jnz     loc_18002E17F
0x18002df5c  lea     r8, ?g_OOBEExemptedTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; struct _UBPM_SPECIAL_TASK_CLASS *
0x18002df63  lea     rdx, aOobetask; "OOBETask"
0x18002df6a  call    ?UbpmUtilsTaskClassStart@@YAKPEAG0PEAU_UBPM_SPECIAL_TASK_CLASS@@@Z; UbpmUtilsTaskClassStart(ushort *,ushort *,_UBPM_SPECIAL_TASK_CLASS *)
0x18002df6f  mov     ebx, eax
0x18002df71  test    eax, eax
0x18002df73  jnz     loc_18002E17F
0x18002df79  lea     r8, ?g_CriticalMeasuredTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; struct _UBPM_SPECIAL_TASK_CLASS *
0x18002df80  lea     rdx, aCriticalmeasur; "CriticalMeasured"
0x18002df87  call    ?UbpmUtilsTaskClassStart@@YAKPEAG0PEAU_UBPM_SPECIAL_TASK_CLASS@@@Z; UbpmUtilsTaskClassStart(ushort *,ushort *,_UBPM_SPECIAL_TASK_CLASS *)
0x18002df8c  mov     ebx, eax
0x18002df8e  test    eax, eax
0x18002df90  jnz     loc_18002E17F
0x18002df96  lea     rax, [rbp+57h+hKey]
0x18002df9a  mov     r9d, 20019h; samDesired
0x18002dfa0  xor     r8d, r8d; ulOptions
0x18002dfa3  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002dfa8  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Ubp"...
0x18002dfaf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002dfb6  call    cs:__imp_RegOpenKeyExW
0x18002dfbd  nop     dword ptr [rax+rax+00h]
0x18002dfc2  mov     ebx, eax
0x18002dfc4  test    eax, eax
0x18002dfc6  jnz     loc_18002E17F
0x18002dfcc  mov     rcx, [rbp+57h+hKey]; hKey
0x18002dfd0  lea     rax, [rbp+57h+cbMaxValueLen]
0x18002dfd4  mov     [rsp+0E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002dfd9  xor     r9d, r9d; lpReserved
0x18002dfdc  mov     [rsp+0E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002dfe1  xor     r8d, r8d; lpcchClass
0x18002dfe4  mov     [rsp+0E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18002dfe9  xor     edx, edx; lpClass
0x18002dfeb  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18002dfef  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18002dff4  lea     rax, [rbp+57h+cValues]
0x18002dff8  mov     [rsp+0E0h+lpcValues], rax; lpcValues
0x18002dffd  mov     [rsp+0E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002e002  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18002e007  mov     [rsp+0E0h+phkResult], r15; lpcSubKeys
0x18002e00c  call    cs:__imp_RegQueryInfoKeyW
0x18002e013  nop     dword ptr [rax+rax+00h]
0x18002e018  mov     ebx, eax
0x18002e01a  test    eax, eax
0x18002e01c  jnz     loc_18002E17F
0x18002e022  cmp     [rbp+57h+cValues], r15d
0x18002e026  jbe     loc_18002E179
0x18002e02c  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18002e02f  add     [rbp+57h+cbMaxValueLen], 2
0x18002e033  inc     ecx
0x18002e035  mov     [rbp+57h+cbMaxValueNameLen], ecx
0x18002e038  add     ecx, ecx; Size
0x18002e03a  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002e03f  mov     r13, rax
0x18002e042  test    rax, rax
0x18002e045  jnz     short loc_18002E051
0x18002e047  mov     ebx, 0Eh
0x18002e04c  jmp     loc_18002E17F
0x18002e051  mov     ecx, [rbp+57h+cbMaxValueLen]; Size
0x18002e054  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002e059  mov     rdi, rax
0x18002e05c  test    rax, rax
0x18002e05f  jz      short loc_18002E047
0x18002e061  mov     r14d, r15d
0x18002e064  cmp     [rbp+57h+cValues], r15d
0x18002e068  jbe     loc_18002E16B
0x18002e06e  mov     r12d, r15d
0x18002e071  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18002e074  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18002e078  mov     rcx, [rbp+57h+hKey]; hKey
0x18002e07c  mov     r8, r13; lpValueName
0x18002e07f  mov     [rbp+57h+cchValueName], eax
0x18002e082  mov     edx, r12d; dwIndex
0x18002e085  mov     eax, [rbp+57h+cbMaxValueLen]
0x18002e088  mov     [rbp+57h+cbData], eax
0x18002e08b  lea     rax, [rbp+57h+cbData]
0x18002e08f  mov     [rsp+0E0h+lpcValues], rax; lpcbData
0x18002e094  lea     rax, [rbp+57h+Type]
0x18002e098  mov     [rsp+0E0h+lpcbMaxClassLen], rdi; lpData
0x18002e09d  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpType
0x18002e0a2  mov     [rsp+0E0h+phkResult], 0; lpReserved
0x18002e0ab  call    cs:__imp_RegEnumValueW
0x18002e0b2  nop     dword ptr [rax+rax+00h]
0x18002e0b7  mov     ebx, eax
0x18002e0b9  test    eax, eax
0x18002e0bb  jnz     loc_18002E15B
0x18002e0c1  cmp     [rbp+57h+Type], 1
0x18002e0c5  jnz     loc_18002E15B
0x18002e0cb  mov     eax, [rbp+57h+cbData]
0x18002e0ce  shr     eax, 1
0x18002e0d0  dec     eax
0x18002e0d2  mov     ecx, eax
0x18002e0d4  mov     [rbp+57h+var_60], eax
0x18002e0d7  xor     eax, eax
0x18002e0d9  mov     [rdi+rcx*2], ax
0x18002e0dd  cmp     [rbp+57h+cchValueName], 0Eh
0x18002e0e1  jb      short loc_18002E15B
0x18002e0e3  lea     r8d, [rbx+0Eh]; MaxCount
0x18002e0e7  mov     rcx, r13; String1
0x18002e0ea  lea     rdx, aCriticalaction; "CriticalAction"
0x18002e0f1  call    wcsncmp_0
0x18002e0f6  test    eax, eax
0x18002e0f8  jnz     short loc_18002E15B
0x18002e0fa  cmp     [rbp+57h+var_60], 26h ; '&'
0x18002e0fe  jnz     short loc_18002E15B
0x18002e100  cmp     word ptr [rdi], 7Bh ; '{'
0x18002e104  jnz     short loc_18002E15B
0x18002e106  cmp     word ptr [rdi+4Ah], 7Dh ; '}'
0x18002e10b  jnz     short loc_18002E15B
0x18002e10d  lea     rcx, [rdi+2]; StringUuid
0x18002e111  lea     rdx, [rbp+57h+Uuid]; Uuid
0x18002e115  mov     [rcx+48h], ax
0x18002e119  call    cs:__imp_UuidFromStringW
0x18002e120  nop     dword ptr [rax+rax+00h]
0x18002e125  test    eax, eax
0x18002e127  jnz     short loc_18002E15B
0x18002e129  cmp     r14d, r15d
0x18002e12c  jnz     short loc_18002E149
0x18002e12e  lea     edx, [r15+5]
0x18002e132  mov     rcx, rsi; Ptr
0x18002e135  shl     edx, 4; Size
0x18002e138  call    ?UbpmReAlloc@@YAPEAXPEAXK@Z; UbpmReAlloc(void *,ulong)
0x18002e13d  test    rax, rax
0x18002e140  jz      short loc_18002E17F
0x18002e142  add     r15d, 5
0x18002e146  mov     rsi, rax
0x18002e149  movups  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x18002e14d  mov     eax, r14d
0x18002e150  add     rax, rax
0x18002e153  inc     r14d
0x18002e156  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x18002e15b  inc     r12d
0x18002e15e  cmp     r12d, [rbp+57h+cValues]
0x18002e162  jb      loc_18002E071
0x18002e168  xor     r15d, r15d
0x18002e16b  mov     cs:?g_dwCriticalActionsCount@@3KA, r14d; ulong g_dwCriticalActionsCount
0x18002e172  mov     qword ptr cs:?g_pCriticalActions@@3PEAU_GUID@@EA.Data1, rsi; _GUID * g_pCriticalActions ...
0x18002e179  mov     ebx, r15d
0x18002e17c  mov     rsi, r15
0x18002e17f  mov     rcx, rsi
0x18002e182  call    UBPM_MIDL_user_free
0x18002e187  mov     rcx, r13
0x18002e18a  call    UBPM_MIDL_user_free
0x18002e18f  mov     rcx, rdi
0x18002e192  call    UBPM_MIDL_user_free
0x18002e197  mov     rcx, [rbp+57h+hKey]; hKey
0x18002e19b  test    rcx, rcx
0x18002e19e  jz      short loc_18002E1AC
0x18002e1a0  call    cs:__imp_RegCloseKey
0x18002e1a7  nop     dword ptr [rax+rax+00h]
0x18002e1ac  mov     eax, ebx
0x18002e1ae  mov     rcx, [rbp+57h+var_48]
0x18002e1b2  xor     rcx, rsp; StackCookie
0x18002e1b5  call    __security_check_cookie
0x18002e1ba  add     rsp, 0A8h
0x18002e1c1  pop     r15
0x18002e1c3  pop     r14
0x18002e1c5  pop     r13
0x18002e1c7  pop     r12
0x18002e1c9  pop     rdi
0x18002e1ca  pop     rsi
0x18002e1cb  pop     rbx
0x18002e1cc  pop     rbp
0x18002e1cd  retn
```
