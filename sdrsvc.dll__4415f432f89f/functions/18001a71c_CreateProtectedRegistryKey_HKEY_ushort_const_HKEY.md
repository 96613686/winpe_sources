# CreateProtectedRegistryKey(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x18001a71c`
- end: `0x18001a892`
- name: `?CreateProtectedRegistryKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z`
- size: `374`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001b770`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001a71c`
- `0x18001c58c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a81a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a81a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a873`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a873`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a85d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a85d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a799`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a799`

## string_xrefs

- `0x18001a7c9`: `Security`
- `0x18001a736`: `CreateProtectedRegistryKey`

## pseudocode

```c
__int64 __fastcall CreateProtectedRegistryKey(HKEY hKey, const unsigned __int16 *a2, HKEY *a3)
{
  __int64 v5; // rcx
  __int16 v6; // ax
  int v7; // eax
  bool v8; // sf
  unsigned int v9; // ebx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-9h] BYREF
  int LastFailureAsHRESULT; // [rsp+68h] [rbp+Fh] BYREF
  int v13; // [rsp+6Ch] [rbp+13h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+C0h] [rbp+67h] BYREF
  const unsigned __int16 *dwDisposition; // [rsp+C8h] [rbp+6Fh] BYREF
  HKEY phkResult; // [rsp+D0h] [rbp+77h] BYREF

  dwDisposition = a2;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CreateProtectedRegistryKey",
    0x27u,
    1u);
  phkResult = 0;
  LODWORD(dwDisposition) = 0;
  SecurityDescriptor = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( a3 )
  {
    *a3 = 0;
    LastFailureAsHRESULT = 0;
    LOWORD(v13) = 49;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"O:BAG:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v5);
      v6 = 54;
LABEL_4:
      HIWORD(v13) = v6;
      goto LABEL_10;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v13) = 54;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    SecurityAttributes.nLength = 24;
    SecurityAttributes.bInheritHandle = 0;
    v7 = RegCreateKeyExW(hKey, L"Security", 0, 0, 0, 0x2001Fu, &SecurityAttributes, &phkResult, (LPDWORD)&dwDisposition);
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    LastFailureAsHRESULT = v7;
    v8 = v7 < 0;
    v6 = 60;
    if ( v8 )
      goto LABEL_4;
    LOWORD(v13) = 60;
    hKey = 0;
    *a3 = phkResult;
  }
  else
  {
    v13 = 3211312;
    LastFailureAsHRESULT = -2147024809;
  }
LABEL_10:
  LocalFree(SecurityDescriptor);
  SecurityDescriptor = 0;
  if ( hKey )
    RegCloseKey(hKey);
  v9 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v9;
}

```

## disassembly

```asm
0x18001a71c  mov     [rsp-8+dwDisposition], rdx
0x18001a721  push    rbp
0x18001a722  push    rbx
0x18001a723  push    rdi
0x18001a724  lea     rbp, [rsp-47h]
0x18001a729  sub     rsp, 0A0h
0x18001a730  mov     r9d, 1; unsigned __int16
0x18001a736  lea     rdx, aCreateprotecte; "CreateProtectedRegistryKey"
0x18001a73d  mov     rdi, r8
0x18001a740  mov     rbx, rcx
0x18001a743  lea     rcx, [rbp+57h+var_48]; this
0x18001a747  lea     r8d, [r9+26h]; unsigned __int16
0x18001a74b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001a750  xor     eax, eax
0x18001a752  mov     [rbp+57h+arg_10], 0
0x18001a75a  mov     dword ptr [rbp+57h+dwDisposition], 0
0x18001a761  xorps   xmm0, xmm0
0x18001a764  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18001a768  mov     [rbp+57h+SecurityDescriptor], rax
0x18001a76c  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x18001a770  test    rdi, rdi
0x18001a773  jz      loc_18001A84B
0x18001a779  mov     [rdi], rax
0x18001a77c  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18001a780  mov     [rbp+57h+var_48], eax
0x18001a783  lea     rcx, aOBagBadPAOiciG_0; "O:BAG:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;"...
0x18001a78a  mov     eax, 31h ; '1'
0x18001a78f  xor     r9d, r9d; SecurityDescriptorSize
0x18001a792  mov     word ptr [rbp+57h+var_44], ax
0x18001a796  lea     edx, [rax-30h]; StringSDRevision
0x18001a799  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001a79f  test    eax, eax
0x18001a7a1  jnz     short loc_18001A7B9
0x18001a7a3  call    GetLastFailureAsHRESULT
0x18001a7a8  mov     [rbp+57h+var_48], eax
0x18001a7ab  mov     eax, 36h ; '6'
0x18001a7b0  mov     word ptr [rbp+57h+var_44+2], ax
0x18001a7b4  jmp     loc_18001A859
0x18001a7b9  mov     eax, 36h ; '6'
0x18001a7be  mov     [rbp+57h+var_48], 0
0x18001a7c5  mov     word ptr [rbp+57h+var_44], ax
0x18001a7c9  lea     rdx, c_wszSafedocsCredentialsKey; "Security"
0x18001a7d0  mov     rax, [rbp+57h+SecurityDescriptor]
0x18001a7d4  xor     r9d, r9d; lpClass
0x18001a7d7  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x18001a7db  xor     r8d, r8d; Reserved
0x18001a7de  lea     rax, [rbp+57h+dwDisposition]
0x18001a7e2  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x18001a7e9  mov     [rsp+0B0h+lpdwDisposition], rax; lpdwDisposition
0x18001a7ee  mov     rcx, rbx; hKey
0x18001a7f1  lea     rax, [rbp+57h+arg_10]
0x18001a7f5  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x18001a7fc  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18001a801  lea     rax, [rbp+57h+SecurityAttributes]
0x18001a805  mov     [rsp+0B0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18001a80a  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x18001a812  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x18001a81a  call    cs:__imp_RegCreateKeyExW
0x18001a820  test    eax, eax
0x18001a822  jle     short loc_18001A82C
0x18001a824  movzx   eax, ax
0x18001a827  or      eax, 80070000h
0x18001a82c  mov     [rbp+57h+var_48], eax
0x18001a82f  test    eax, eax
0x18001a831  mov     eax, 3Ch ; '<'
0x18001a836  js      loc_18001A7B0
0x18001a83c  mov     word ptr [rbp+57h+var_44], ax
0x18001a840  xor     ebx, ebx
0x18001a842  mov     rax, [rbp+57h+arg_10]
0x18001a846  mov     [rdi], rax
0x18001a849  jmp     short loc_18001A859
0x18001a84b  mov     [rbp+57h+var_44], 310030h
0x18001a852  mov     [rbp+57h+var_48], 80070057h
0x18001a859  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18001a85d  call    cs:__imp_LocalFree
0x18001a863  mov     [rbp+57h+SecurityDescriptor], 0
0x18001a86b  test    rbx, rbx
0x18001a86e  jz      short loc_18001A879
0x18001a870  mov     rcx, rbx; hKey
0x18001a873  call    cs:__imp_RegCloseKey
0x18001a879  mov     ebx, [rbp+57h+var_48]
0x18001a87c  lea     rcx, [rbp+57h+var_48]; this
0x18001a880  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001a885  mov     eax, ebx
0x18001a887  add     rsp, 0A0h
0x18001a88e  pop     rdi
0x18001a88f  pop     rbx
0x18001a890  pop     rbp
0x18001a891  retn
```
