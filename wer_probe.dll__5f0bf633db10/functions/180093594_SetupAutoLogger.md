# SetupAutoLogger

- ea: `0x180093594`
- end: `0x1800937b1`
- name: `SetupAutoLogger`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800937b8`

## callees

- `0x180093594`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800935fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800935fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009379d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009379d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093635`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18009366b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093696`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800936c1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18009372e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093758`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093783`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093635`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18009366b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093696`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800936c1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18009372e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093758`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093783`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x180093793`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x180093793`

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
0x180093594  mov     r11, rsp
0x180093597  mov     [r11+8], rbx
0x18009359b  push    rbp
0x18009359c  push    rsi
0x18009359d  push    r14
0x18009359f  mov     rbp, rsp
0x1800935a2  sub     rsp, 50h
0x1800935a6  lea     rax, [rbp+arg_10]
0x1800935aa  mov     [rbp+hKey], 0
0x1800935b2  mov     [r11-28h], rax
0x1800935b6  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x1800935bd  lea     rax, [rbp+hKey]
0x1800935c1  mov     [rbp+arg_10], 0
0x1800935c8  mov     [r11-30h], rax
0x1800935cc  mov     rbx, rcx
0x1800935cf  mov     qword ptr [r11-38h], 0
0x1800935d7  xor     r9d, r9d; lpClass
0x1800935da  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x1800935e2  xor     r8d, r8d; Reserved
0x1800935e5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800935ec  mov     [rsp+50h+dwOptions], 0; dwOptions
0x1800935f4  mov     [rbp+Data], 0
0x1800935fb  call    cs:__imp_RegCreateKeyExW
0x180093601  test    eax, eax
0x180093603  jnz     loc_1800937A3
0x180093609  cmp     [rbp+arg_10], 2
0x18009360d  mov     rcx, [rbp+hKey]; hKey
0x180093611  jz      loc_18009379D
0x180093617  mov     esi, 4
0x18009361c  lea     rax, [rbx+30h]
0x180093620  mov     [rsp+50h+samDesired], esi; cbData
0x180093624  lea     r8, aBuffersize; "BufferSize"
0x18009362b  mov     r9d, esi; dwType
0x18009362e  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180093633  xor     edx, edx; lpSubKey
0x180093635  call    cs:__imp_RegSetKeyValueW
0x18009363b  test    eax, eax
0x18009363d  jnz     loc_18009378D
0x180093643  mov     rcx, [rbp+hKey]; hKey
0x180093647  lea     rax, aC712af3dEd1e46; "{C712AF3D-ED1E-46A9-B843-E9014D29CAEE}"
0x18009364e  lea     r14d, [rsi-3]
0x180093652  mov     [rsp+50h+samDesired], 4Eh ; 'N'; cbData
0x18009365a  mov     r9d, r14d; dwType
0x18009365d  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180093662  lea     r8, aGuid; "Guid"
0x180093669  xor     edx, edx; lpSubKey
0x18009366b  call    cs:__imp_RegSetKeyValueW
0x180093671  test    eax, eax
0x180093673  jnz     loc_18009378D
0x180093679  mov     rcx, [rbp+hKey]; hKey
0x18009367d  lea     rax, [rbx+40h]
0x180093681  mov     [rsp+50h+samDesired], esi; cbData
0x180093685  lea     r8, aLogfilemode; "LogFileMode"
0x18009368c  mov     r9d, esi; dwType
0x18009368f  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180093694  xor     edx, edx; lpSubKey
0x180093696  call    cs:__imp_RegSetKeyValueW
0x18009369c  test    eax, eax
0x18009369e  jnz     loc_18009378D
0x1800936a4  mov     rcx, [rbp+hKey]; hKey
0x1800936a8  lea     rax, [rbx+34h]
0x1800936ac  mov     [rsp+50h+samDesired], esi; cbData
0x1800936b0  lea     r8, aMinimumbuffers; "MinimumBuffers"
0x1800936b7  mov     r9d, esi; dwType
0x1800936ba  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800936bf  xor     edx, edx; lpSubKey
0x1800936c1  call    cs:__imp_RegSetKeyValueW
0x1800936c7  test    eax, eax
0x1800936c9  jnz     loc_18009378D
0x1800936cf  cmp     [rbx+48h], eax
0x1800936d2  jge     short loc_18009370C
0x1800936d4  movzx   eax, word ptr [rbx+48h]
0x1800936d8  lea     rcx, [rbx+4]
0x1800936dc  add     rcx, rax
0x1800936df  xor     edx, edx
0x1800936e1  movzx   r8d, word ptr [rax+rbx+2]
0x1800936e7  test    r8d, r8d
0x1800936ea  jz      short loc_180093702
0x1800936ec  cmp     [rcx+2], r14w
0x1800936f1  jz      short loc_180093707
0x1800936f3  movzx   eax, word ptr [rcx]
0x1800936f6  add     edx, r14d
0x1800936f9  lea     rcx, [rcx+rax*4]
0x1800936fd  cmp     edx, r8d
0x180093700  jb      short loc_1800936EC
0x180093702  cmp     edx, r8d
0x180093705  jnb     short loc_18009370C
0x180093707  add     rcx, rsi
0x18009370a  jmp     short loc_18009370E
0x18009370c  xor     ecx, ecx
0x18009370e  mov     [rsp+50h+samDesired], 20h ; ' '; cbData
0x180093716  lea     r8, aEnablekernelfl; "EnableKernelFlags"
0x18009371d  mov     qword ptr [rsp+50h+dwOptions], rcx; lpData
0x180093722  mov     r9d, 3; dwType
0x180093728  mov     rcx, [rbp+hKey]; hKey
0x18009372c  xor     edx, edx; lpSubKey
0x18009372e  call    cs:__imp_RegSetKeyValueW
0x180093734  test    eax, eax
0x180093736  jnz     short loc_18009378D
0x180093738  mov     rcx, [rbp+hKey]; hKey
0x18009373c  lea     r8, aStatus; "Status"
0x180093743  mov     [rbp+Data], eax
0x180093746  mov     r9d, esi; dwType
0x180093749  lea     rax, [rbp+Data]
0x18009374d  mov     [rsp+50h+samDesired], esi; cbData
0x180093751  xor     edx, edx; lpSubKey
0x180093753  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180093758  call    cs:__imp_RegSetKeyValueW
0x18009375e  test    eax, eax
0x180093760  jnz     short loc_18009378D
0x180093762  mov     rcx, [rbp+hKey]; hKey
0x180093766  lea     rax, [rbp+Data]
0x18009376a  mov     [rsp+50h+samDesired], esi; cbData
0x18009376e  lea     r8, aStart; "Start"
0x180093775  mov     r9d, esi; dwType
0x180093778  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18009377d  xor     edx, edx; lpSubKey
0x18009377f  mov     [rbp+Data], r14d
0x180093783  call    cs:__imp_RegSetKeyValueW
0x180093789  test    eax, eax
0x18009378b  jz      short loc_180093799
0x18009378d  mov     rcx, [rbp+hKey]; hKey
0x180093791  xor     edx, edx; lpSubKey
0x180093793  call    cs:__imp_RegDeleteKeyA
0x180093799  mov     rcx, [rbp+hKey]; hKey
0x18009379d  call    cs:__imp_RegCloseKey
0x1800937a3  mov     rbx, [rsp+50h+arg_0]
0x1800937a8  add     rsp, 50h
0x1800937ac  pop     r14
0x1800937ae  pop     rsi
0x1800937af  pop     rbp
0x1800937b0  retn
```
