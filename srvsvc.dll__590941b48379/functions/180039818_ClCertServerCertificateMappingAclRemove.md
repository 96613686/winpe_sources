# ClCertServerCertificateMappingAclRemove

- ea: `0x180039818`
- end: `0x180039908`
- name: `ClCertServerCertificateMappingAclRemove`
- size: `240`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180033cb4`

## callees

- `0x1800215e8`
- `0x180038e20`
- `0x180039818`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003989d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003989d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003984e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003984e`

## string_xrefs

- `0x180039847`: `System\CurrentControlSet\Services\LanmanServer\CertsAcl`

## pseudocode

```c
__int64 __fastcall ClCertServerCertificateMappingAclRemove(LPCWSTR lpSubKey)
{
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  int v4; // edx
  LSTATUS v5; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\LanmanServer\\CertsAcl",
         0,
         0x10000u,
         &hKey);
  if ( v2 == 2 )
    goto LABEL_2;
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v4 = 22;
LABEL_14:
      WPP_SF_Sd(v3[2], v4, (unsigned int)WPP_053b19d310c5352633ee666709ba12ba_Traceguids, (_DWORD)lpSubKey, v2);
    }
  }
  else
  {
    v5 = RegDeleteKeyExW(hKey, lpSubKey, 0, 0);
    v2 = v5;
    if ( v5 == 2 )
    {
LABEL_2:
      v2 = 0;
      goto LABEL_15;
    }
    if ( v5 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v4 = 23;
        goto LABEL_14;
      }
    }
  }
LABEL_15:
  if ( hKey )
    ClCertRegCloseKey();
  return v2;
}

```

## disassembly

```asm
0x180039818  mov     r11, rsp
0x18003981b  mov     [r11+8], rbx
0x18003981f  push    rdi
0x180039820  sub     rsp, 30h
0x180039824  mov     rdi, rcx
0x180039827  mov     qword ptr [r11+10h], 0
0x18003982f  lea     rax, [r11+10h]
0x180039833  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003983a  mov     r9d, 10000h; samDesired
0x180039840  mov     [r11-18h], rax
0x180039844  xor     r8d, r8d; ulOptions
0x180039847  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\La"...
0x18003984e  call    cs:__imp_RegOpenKeyExW
0x180039854  mov     ebx, eax
0x180039856  cmp     eax, 2
0x180039859  jnz     short loc_180039862
0x18003985b  xor     ebx, ebx
0x18003985d  jmp     loc_1800398EC
0x180039862  test    ebx, ebx
0x180039864  jz      short loc_18003988F
0x180039866  mov     rcx, cs:WPP_GLOBAL_Control
0x18003986d  lea     rax, WPP_GLOBAL_Control
0x180039874  cmp     rcx, rax
0x180039877  jz      short loc_1800398EC
0x180039879  test    dword ptr [rcx+1Ch], 800h
0x180039880  jz      short loc_1800398EC
0x180039882  cmp     byte ptr [rcx+19h], 1
0x180039886  jb      short loc_1800398EC
0x180039888  mov     edx, 16h
0x18003988d  jmp     short loc_1800398D5
0x18003988f  mov     rcx, [rsp+38h+hKey]; hKey
0x180039894  xor     r9d, r9d; Reserved
0x180039897  xor     r8d, r8d; samDesired
0x18003989a  mov     rdx, rdi; lpSubKey
0x18003989d  call    cs:__imp_RegDeleteKeyExW
0x1800398a3  mov     ebx, eax
0x1800398a5  cmp     eax, 2
0x1800398a8  jz      short loc_18003985B
0x1800398aa  test    eax, eax
0x1800398ac  jz      short loc_1800398EC
0x1800398ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800398b5  lea     rax, WPP_GLOBAL_Control
0x1800398bc  cmp     rcx, rax
0x1800398bf  jz      short loc_1800398EC
0x1800398c1  test    dword ptr [rcx+1Ch], 800h
0x1800398c8  jz      short loc_1800398EC
0x1800398ca  cmp     byte ptr [rcx+19h], 1
0x1800398ce  jb      short loc_1800398EC
0x1800398d0  mov     edx, 17h
0x1800398d5  mov     rcx, [rcx+10h]
0x1800398d9  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x1800398e0  mov     r9, rdi
0x1800398e3  mov     [rsp+38h+var_18], ebx
0x1800398e7  call    WPP_SF_Sd
0x1800398ec  mov     rcx, [rsp+38h+hKey]
0x1800398f1  test    rcx, rcx
0x1800398f4  jz      short loc_1800398FB
0x1800398f6  call    ClCertRegCloseKey
0x1800398fb  mov     eax, ebx
0x1800398fd  mov     rbx, [rsp+38h+arg_0]
0x180039902  add     rsp, 30h
0x180039906  pop     rdi
0x180039907  retn
```
