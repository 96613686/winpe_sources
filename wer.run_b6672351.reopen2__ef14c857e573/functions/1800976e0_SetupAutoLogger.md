# SetupAutoLogger

- ea: `0x1800976e0`
- end: `0x18009793a`
- name: `SetupAutoLogger`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180097940`

## callees

- `0x1800976e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180097747`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180097747`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009791f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009791f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180097787`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800977c3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800977f4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180097825`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180097898`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800978c8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800978f9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180097787`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800977c3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800977f4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180097825`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180097898`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800978c8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800978f9`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x18009790f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x18009790f`

## pseudocode

```c
LSTATUS __fastcall SetupAutoLogger(unsigned __int16 *a1)
{
  LSTATUS result; // eax
  HKEY v3; // rcx
  __int64 v4; // rax
  unsigned __int16 *v5; // rcx
  unsigned int v6; // edx
  unsigned int v7; // r8d
  const void *v8; // rcx
  int Data; // [rsp+78h] [rbp+28h] BYREF
  DWORD v10; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  v10 = 0;
  Data = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger\\Microsoft-OCA-IPT",
             0,
             0,
             0,
             0xF003Fu,
             0,
             &hKey,
             &v10);
  if ( !result )
  {
    v3 = hKey;
    if ( v10 == 2 )
      return RegCloseKey(v3);
    if ( RegSetKeyValueW(hKey, 0, L"BufferSize", 4u, a1 + 24, 4u)
      || RegSetKeyValueW(hKey, 0, L"Guid", 1u, L"{C712AF3D-ED1E-46A9-B843-E9014D29CAEE}", 0x4Eu)
      || RegSetKeyValueW(hKey, 0, L"LogFileMode", 4u, a1 + 32, 4u)
      || RegSetKeyValueW(hKey, 0, L"MinimumBuffers", 4u, a1 + 26, 4u) )
    {
LABEL_17:
      RegDeleteKeyA(hKey, 0);
LABEL_18:
      v3 = hKey;
      return RegCloseKey(v3);
    }
    if ( *((int *)a1 + 18) < 0 )
    {
      v4 = a1[36];
      v5 = (unsigned __int16 *)((char *)a1 + v4 + 4);
      v6 = 0;
      v7 = *(unsigned __int16 *)((char *)a1 + v4 + 2);
      if ( *(unsigned __int16 *)((char *)a1 + v4 + 2) )
      {
        while ( v5[1] != 1 )
        {
          ++v6;
          v5 += 2 * *v5;
          if ( v6 >= v7 )
            goto LABEL_11;
        }
        goto LABEL_12;
      }
LABEL_11:
      if ( v6 < v7 )
      {
LABEL_12:
        v8 = v5 + 2;
LABEL_14:
        if ( !RegSetKeyValueW(hKey, 0, L"EnableKernelFlags", 3u, v8, 0x20u) )
        {
          Data = 0;
          if ( !RegSetKeyValueW(hKey, 0, L"Status", 4u, &Data, 4u) )
          {
            Data = 1;
            if ( !RegSetKeyValueW(hKey, 0, L"Start", 4u, &Data, 4u) )
              goto LABEL_18;
          }
        }
        goto LABEL_17;
      }
    }
    v8 = 0;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x1800976e0  mov     r11, rsp
0x1800976e3  mov     [r11+8], rbx
0x1800976e7  push    rbp
0x1800976e8  push    rsi
0x1800976e9  push    r14
0x1800976eb  mov     rbp, rsp
0x1800976ee  sub     rsp, 50h
0x1800976f2  lea     rax, [rbp+arg_10]
0x1800976f6  mov     [rbp+hKey], 0
0x1800976fe  mov     [r11-28h], rax
0x180097702  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x180097709  lea     rax, [rbp+hKey]
0x18009770d  mov     [rbp+arg_10], 0
0x180097714  mov     [r11-30h], rax
0x180097718  mov     rbx, rcx
0x18009771b  mov     qword ptr [r11-38h], 0
0x180097723  xor     r9d, r9d; lpClass
0x180097726  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x18009772e  xor     r8d, r8d; Reserved
0x180097731  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180097738  mov     [rsp+50h+dwOptions], 0; dwOptions
0x180097740  mov     [rbp+Data], 0
0x180097747  call    cs:__imp_RegCreateKeyExW
0x18009774e  nop     dword ptr [rax+rax+00h]
0x180097753  test    eax, eax
0x180097755  jnz     loc_18009792B
0x18009775b  cmp     [rbp+arg_10], 2
0x18009775f  mov     rcx, [rbp+hKey]; hKey
0x180097763  jz      loc_18009791F
0x180097769  mov     esi, 4
0x18009776e  lea     rax, [rbx+30h]
0x180097772  mov     [rsp+50h+samDesired], esi; cbData
0x180097776  lea     r8, aBuffersize; "BufferSize"
0x18009777d  mov     r9d, esi; dwType
0x180097780  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180097785  xor     edx, edx; lpSubKey
0x180097787  call    cs:__imp_RegSetKeyValueW
0x18009778e  nop     dword ptr [rax+rax+00h]
0x180097793  test    eax, eax
0x180097795  jnz     loc_180097909
0x18009779b  mov     rcx, [rbp+hKey]; hKey
0x18009779f  lea     rax, aC712af3dEd1e46; "{C712AF3D-ED1E-46A9-B843-E9014D29CAEE}"
0x1800977a6  lea     r14d, [rsi-3]
0x1800977aa  mov     [rsp+50h+samDesired], 4Eh ; 'N'; cbData
0x1800977b2  mov     r9d, r14d; dwType
0x1800977b5  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800977ba  lea     r8, aGuid; "Guid"
0x1800977c1  xor     edx, edx; lpSubKey
0x1800977c3  call    cs:__imp_RegSetKeyValueW
0x1800977ca  nop     dword ptr [rax+rax+00h]
0x1800977cf  test    eax, eax
0x1800977d1  jnz     loc_180097909
0x1800977d7  mov     rcx, [rbp+hKey]; hKey
0x1800977db  lea     rax, [rbx+40h]
0x1800977df  mov     [rsp+50h+samDesired], esi; cbData
0x1800977e3  lea     r8, aLogfilemode; "LogFileMode"
0x1800977ea  mov     r9d, esi; dwType
0x1800977ed  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800977f2  xor     edx, edx; lpSubKey
0x1800977f4  call    cs:__imp_RegSetKeyValueW
0x1800977fb  nop     dword ptr [rax+rax+00h]
0x180097800  test    eax, eax
0x180097802  jnz     loc_180097909
0x180097808  mov     rcx, [rbp+hKey]; hKey
0x18009780c  lea     rax, [rbx+34h]
0x180097810  mov     [rsp+50h+samDesired], esi; cbData
0x180097814  lea     r8, aMinimumbuffers; "MinimumBuffers"
0x18009781b  mov     r9d, esi; dwType
0x18009781e  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180097823  xor     edx, edx; lpSubKey
0x180097825  call    cs:__imp_RegSetKeyValueW
0x18009782c  nop     dword ptr [rax+rax+00h]
0x180097831  test    eax, eax
0x180097833  jnz     loc_180097909
0x180097839  cmp     [rbx+48h], eax
0x18009783c  jge     short loc_180097876
0x18009783e  movzx   eax, word ptr [rbx+48h]
0x180097842  lea     rcx, [rbx+4]
0x180097846  add     rcx, rax
0x180097849  xor     edx, edx
0x18009784b  movzx   r8d, word ptr [rax+rbx+2]
0x180097851  test    r8d, r8d
0x180097854  jz      short loc_18009786C
0x180097856  cmp     [rcx+2], r14w
0x18009785b  jz      short loc_180097871
0x18009785d  movzx   eax, word ptr [rcx]
0x180097860  add     edx, r14d
0x180097863  lea     rcx, [rcx+rax*4]
0x180097867  cmp     edx, r8d
0x18009786a  jb      short loc_180097856
0x18009786c  cmp     edx, r8d
0x18009786f  jnb     short loc_180097876
0x180097871  add     rcx, rsi
0x180097874  jmp     short loc_180097878
0x180097876  xor     ecx, ecx
0x180097878  mov     [rsp+50h+samDesired], 20h ; ' '; cbData
0x180097880  lea     r8, aEnablekernelfl; "EnableKernelFlags"
0x180097887  mov     qword ptr [rsp+50h+dwOptions], rcx; lpData
0x18009788c  mov     r9d, 3; dwType
0x180097892  mov     rcx, [rbp+hKey]; hKey
0x180097896  xor     edx, edx; lpSubKey
0x180097898  call    cs:__imp_RegSetKeyValueW
0x18009789f  nop     dword ptr [rax+rax+00h]
0x1800978a4  test    eax, eax
0x1800978a6  jnz     short loc_180097909
0x1800978a8  mov     rcx, [rbp+hKey]; hKey
0x1800978ac  lea     r8, aStatus; "Status"
0x1800978b3  mov     [rbp+Data], eax
0x1800978b6  mov     r9d, esi; dwType
0x1800978b9  lea     rax, [rbp+Data]
0x1800978bd  mov     [rsp+50h+samDesired], esi; cbData
0x1800978c1  xor     edx, edx; lpSubKey
0x1800978c3  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800978c8  call    cs:__imp_RegSetKeyValueW
0x1800978cf  nop     dword ptr [rax+rax+00h]
0x1800978d4  test    eax, eax
0x1800978d6  jnz     short loc_180097909
0x1800978d8  mov     rcx, [rbp+hKey]; hKey
0x1800978dc  lea     rax, [rbp+Data]
0x1800978e0  mov     [rsp+50h+samDesired], esi; cbData
0x1800978e4  lea     r8, aStart; "Start"
0x1800978eb  mov     r9d, esi; dwType
0x1800978ee  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800978f3  xor     edx, edx; lpSubKey
0x1800978f5  mov     [rbp+Data], r14d
0x1800978f9  call    cs:__imp_RegSetKeyValueW
0x180097900  nop     dword ptr [rax+rax+00h]
0x180097905  test    eax, eax
0x180097907  jz      short loc_18009791B
0x180097909  mov     rcx, [rbp+hKey]; hKey
0x18009790d  xor     edx, edx; lpSubKey
0x18009790f  call    cs:__imp_RegDeleteKeyA
0x180097916  nop     dword ptr [rax+rax+00h]
0x18009791b  mov     rcx, [rbp+hKey]; hKey
0x18009791f  call    cs:__imp_RegCloseKey
0x180097926  nop     dword ptr [rax+rax+00h]
0x18009792b  mov     rbx, [rsp+50h+arg_0]
0x180097930  add     rsp, 50h
0x180097934  pop     r14
0x180097936  pop     rsi
0x180097937  pop     rbp
0x180097938  retn
```
