# WlAccessibilityOnBoot(_WLSM_GLOBAL_CONTEXT *)

- ea: `0x14003c3e0`
- end: `0x14003c792`
- name: `?WlAccessibilityOnBoot@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@@Z`
- size: `946`
- prototype: `unsigned int __fastcall(struct _WLSM_GLOBAL_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400877f0`

## callees

- `0x1400057f4`
- `0x140019838`
- `0x1400198e0`
- `0x140019df8`
- `0x14001a200`
- `0x14003c3e0`
- `0x140041c34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14003c683`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14003c683`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003c42f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003c42f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003c4fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003c5c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003c4fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003c5c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c735`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c74f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009e741`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009e751`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c735`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c74f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009e741`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009e751`

## string_xrefs

- `0x14003c421`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x14003c6c1`: `atbroker.exe`
- `0x14003c4f1`: `Configuration`
- `0x14003c5b8`: `Configuration`
- `0x14003c677`: `SecureConfiguration`

## pseudocode

```c
__int64 __fastcall WlAccessibilityOnBoot(struct _WLSM_GLOBAL_CONTEXT *a1)
{
  void *v2; // rsi
  unsigned int started; // eax
  __int64 v4; // r9
  unsigned int v5; // edi
  CUser *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  unsigned int v9; // r8d
  void **phkResult; // [rsp+20h] [rbp-38h]
  void *v12; // [rsp+30h] [rbp-28h] BYREF
  HKEY v13; // [rsp+38h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  v13 = 0;
  cbData = 0;
  Type = 0;
  v2 = 0;
  v12 = 0;
  started = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility",
              0,
              1u,
              &hKey);
  v5 = started;
  if ( started == 2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_47;
    }
    v7 = 43;
    goto LABEL_6;
  }
  if ( started )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 44;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v6 + 2), v8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, started);
LABEL_13:
      v6 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    started = RegQueryValueExW(hKey, L"Configuration", 0, 0, 0, &cbData);
    v5 = started;
    if ( started == 2 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_47;
      }
      v7 = 45;
LABEL_6:
      WPP_SF_(*((_QWORD *)v6 + 2), v7, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v4);
LABEL_46:
      v6 = WPP_GLOBAL_Control;
LABEL_47:
      v5 = 0;
      goto LABEL_48;
    }
    if ( started )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 46;
        goto LABEL_12;
      }
    }
    else
    {
      v2 = WLAlloc(cbData);
      v12 = v2;
      if ( !v2 )
      {
        v5 = 14;
        goto LABEL_13;
      }
      started = RegQueryValueExW(hKey, L"Configuration", 0, &Type, (LPBYTE)v2, &cbData);
      v5 = started;
      if ( started )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 47;
          goto LABEL_12;
        }
      }
      else
      {
        started = WlAccessibilitypCreateSATKey(1, *(_DWORD *)(*((_QWORD *)a1 + 2) + 88LL), 0xF003Fu, &v13);
        v5 = started;
        if ( started )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = 48;
            goto LABEL_12;
          }
        }
        else
        {
          started = RegSetValueExW(v13, L"SecureConfiguration", 0, Type, (const BYTE *)v2, cbData);
          v5 = started;
          if ( started )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v8 = 49;
              goto LABEL_12;
            }
          }
          else
          {
            started = WlAccessibilitypStartProcessInAtJob(a1, L"atbroker.exe", v9, 1, phkResult);
            v5 = started;
            if ( !started )
              goto LABEL_46;
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v8 = 50;
              goto LABEL_12;
            }
          }
        }
      }
    }
  }
LABEL_48:
  if ( v2 )
  {
    UHHeapFree(&v12);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v13 )
  {
    RegCloseKey(v13);
    v6 = WPP_GLOBAL_Control;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x40000) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)v6 + 2), 51, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x14003c3e0  mov     rax, rsp
0x14003c3e3  push    rbx
0x14003c3e4  push    rsi
0x14003c3e5  push    rdi
0x14003c3e6  sub     rsp, 40h
0x14003c3ea  mov     rbx, rcx
0x14003c3ed  mov     qword ptr [rax+20h], 0
0x14003c3f5  mov     qword ptr [rax-20h], 0
0x14003c3fd  mov     dword ptr [rax+10h], 0
0x14003c404  mov     dword ptr [rax+18h], 0
0x14003c40b  xor     esi, esi
0x14003c40d  mov     [rax-28h], rsi
0x14003c411  lea     rax, [rax+20h]
0x14003c415  mov     [rsp+58h+phkResult], rax; phkResult
0x14003c41a  lea     r9d, [rsi+1]; samDesired
0x14003c41e  xor     r8d, r8d; ulOptions
0x14003c421  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows NT\\Curren"...
0x14003c428  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003c42f  call    cs:__imp_RegOpenKeyExW
0x14003c435  mov     edi, eax
0x14003c437  cmp     eax, 2
0x14003c43a  jnz     short loc_14003C482
0x14003c43c  lea     rbx, WPP_GLOBAL_Control
0x14003c443  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c44a  cmp     rcx, rbx
0x14003c44d  jz      loc_14003C710
0x14003c453  test    dword ptr [rcx+1Ch], 40000h
0x14003c45a  jz      loc_14003C710
0x14003c460  cmp     byte ptr [rcx+19h], 4
0x14003c464  jb      loc_14003C710
0x14003c46a  lea     edx, [rsi+2Bh]
0x14003c46d  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x14003c474  mov     rcx, [rcx+10h]
0x14003c478  call    WPP_SF_
0x14003c47d  jmp     loc_14003C709
0x14003c482  test    eax, eax
0x14003c484  jz      short loc_14003C4D8
0x14003c486  lea     rbx, WPP_GLOBAL_Control
0x14003c48d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c494  cmp     rcx, rbx
0x14003c497  jz      loc_14003C712
0x14003c49d  test    dword ptr [rcx+1Ch], 40000h
0x14003c4a4  jz      loc_14003C712
0x14003c4aa  cmp     byte ptr [rcx+19h], 2
0x14003c4ae  jb      loc_14003C712
0x14003c4b4  mov     edx, 2Ch ; ','
0x14003c4b9  mov     r9d, eax
0x14003c4bc  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x14003c4c3  mov     rcx, [rcx+10h]
0x14003c4c7  call    WPP_SF_d
0x14003c4cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c4d3  jmp     loc_14003C712
0x14003c4d8  lea     rax, [rsp+58h+cbData]
0x14003c4dd  mov     [rsp+58h+lpcbData], rax; lpcbData
0x14003c4e2  mov     [rsp+58h+phkResult], 0; lpData
0x14003c4eb  xor     r9d, r9d; lpType
0x14003c4ee  xor     r8d, r8d; lpReserved
0x14003c4f1  lea     rdx, ValueName; "Configuration"
0x14003c4f8  mov     rcx, [rsp+58h+hKey]; hKey
0x14003c4fd  call    cs:__imp_RegQueryValueExW
0x14003c503  mov     edi, eax
0x14003c505  cmp     eax, 2
0x14003c508  jnz     short loc_14003C540
0x14003c50a  lea     rbx, WPP_GLOBAL_Control
0x14003c511  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c518  cmp     rcx, rbx
0x14003c51b  jz      loc_14003C710
0x14003c521  test    dword ptr [rcx+1Ch], 40000h
0x14003c528  jz      loc_14003C710
0x14003c52e  cmp     byte ptr [rcx+19h], 4
0x14003c532  jb      loc_14003C710
0x14003c538  lea     edx, [rax+2Bh]
0x14003c53b  jmp     loc_14003C46D
0x14003c540  test    eax, eax
0x14003c542  jz      short loc_14003C57C
0x14003c544  lea     rbx, WPP_GLOBAL_Control
0x14003c54b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c552  cmp     rcx, rbx
0x14003c555  jz      loc_14003C712
0x14003c55b  test    dword ptr [rcx+1Ch], 40000h
0x14003c562  jz      loc_14003C712
0x14003c568  cmp     byte ptr [rcx+19h], 2
0x14003c56c  jb      loc_14003C712
0x14003c572  mov     edx, 2Eh ; '.'
0x14003c577  jmp     loc_14003C4B9
0x14003c57c  mov     ecx, [rsp+58h+cbData]; unsigned __int64
0x14003c580  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x14003c585  mov     rsi, rax
0x14003c588  mov     [rsp+58h+var_28], rax
0x14003c58d  test    rax, rax
0x14003c590  jnz     short loc_14003C5A1
0x14003c592  lea     edi, [rax+0Eh]
0x14003c595  lea     rbx, WPP_GLOBAL_Control
0x14003c59c  jmp     loc_14003C4CC
0x14003c5a1  lea     rax, [rsp+58h+cbData]
0x14003c5a6  mov     [rsp+58h+lpcbData], rax; lpcbData
0x14003c5ab  mov     [rsp+58h+phkResult], rsi; lpData
0x14003c5b0  lea     r9, [rsp+58h+Type]; lpType
0x14003c5b5  xor     r8d, r8d; lpReserved
0x14003c5b8  lea     rdx, ValueName; "Configuration"
0x14003c5bf  mov     rcx, [rsp+58h+hKey]; hKey
0x14003c5c4  call    cs:__imp_RegQueryValueExW
0x14003c5ca  mov     edi, eax
0x14003c5cc  test    eax, eax
0x14003c5ce  jz      short loc_14003C608
0x14003c5d0  lea     rbx, WPP_GLOBAL_Control
0x14003c5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c5de  cmp     rcx, rbx
0x14003c5e1  jz      loc_14003C712
0x14003c5e7  test    dword ptr [rcx+1Ch], 40000h
0x14003c5ee  jz      loc_14003C712
0x14003c5f4  cmp     byte ptr [rcx+19h], 2
0x14003c5f8  jb      loc_14003C712
0x14003c5fe  mov     edx, 2Fh ; '/'
0x14003c603  jmp     loc_14003C4B9
0x14003c608  mov     rdx, [rbx+10h]
0x14003c60c  lea     r9, [rsp+58h+var_20]; HKEY *
0x14003c611  mov     r8d, 0F003Fh; unsigned int
0x14003c617  mov     edx, [rdx+58h]; unsigned int
0x14003c61a  mov     ecx, 1; int
0x14003c61f  call    ?WlAccessibilitypCreateSATKey@@YAKHKKPEAPEAUHKEY__@@@Z; WlAccessibilitypCreateSATKey(int,ulong,ulong,HKEY__ * *)
0x14003c624  mov     edi, eax
0x14003c626  test    eax, eax
0x14003c628  jz      short loc_14003C662
0x14003c62a  lea     rbx, WPP_GLOBAL_Control
0x14003c631  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c638  cmp     rcx, rbx
0x14003c63b  jz      loc_14003C712
0x14003c641  test    dword ptr [rcx+1Ch], 40000h
0x14003c648  jz      loc_14003C712
0x14003c64e  cmp     byte ptr [rcx+19h], 2
0x14003c652  jb      loc_14003C712
0x14003c658  mov     edx, 30h ; '0'
0x14003c65d  jmp     loc_14003C4B9
0x14003c662  mov     eax, [rsp+58h+cbData]
0x14003c666  mov     dword ptr [rsp+58h+lpcbData], eax; cbData
0x14003c66a  mov     [rsp+58h+phkResult], rsi; void **
0x14003c66f  mov     r9d, [rsp+58h+Type]; dwType
0x14003c674  xor     r8d, r8d; Reserved
0x14003c677  lea     rdx, aSecureconfigur; "SecureConfiguration"
0x14003c67e  mov     rcx, [rsp+58h+var_20]; hKey
0x14003c683  call    cs:__imp_RegSetValueExW
0x14003c689  mov     edi, eax
0x14003c68b  test    eax, eax
0x14003c68d  jz      short loc_14003C6BB
0x14003c68f  lea     rbx, WPP_GLOBAL_Control
0x14003c696  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c69d  cmp     rcx, rbx
0x14003c6a0  jz      short loc_14003C712
0x14003c6a2  test    dword ptr [rcx+1Ch], 40000h
0x14003c6a9  jz      short loc_14003C712
0x14003c6ab  cmp     byte ptr [rcx+19h], 2
0x14003c6af  jb      short loc_14003C712
0x14003c6b1  mov     edx, 31h ; '1'
0x14003c6b6  jmp     loc_14003C4B9
0x14003c6bb  mov     r9d, 1; int
0x14003c6c1  lea     rdx, aAtbrokerExe; "atbroker.exe"
0x14003c6c8  mov     rcx, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x14003c6cb  call    ?WlAccessibilitypStartProcessInAtJob@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@PEBGKHPEAPEAX@Z; WlAccessibilitypStartProcessInAtJob(_WLSM_GLOBAL_CONTEXT *,ushort const *,ulong,int,void * *)
0x14003c6d0  mov     edi, eax
0x14003c6d2  test    eax, eax
0x14003c6d4  jz      short loc_14003C702
0x14003c6d6  lea     rbx, WPP_GLOBAL_Control
0x14003c6dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c6e4  cmp     rcx, rbx
0x14003c6e7  jz      short loc_14003C712
0x14003c6e9  test    dword ptr [rcx+1Ch], 40000h
0x14003c6f0  jz      short loc_14003C712
0x14003c6f2  cmp     byte ptr [rcx+19h], 2
0x14003c6f6  jb      short loc_14003C712
0x14003c6f8  mov     edx, 32h ; '2'
0x14003c6fd  jmp     loc_14003C4B9
0x14003c702  lea     rbx, WPP_GLOBAL_Control
0x14003c709  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c710  xor     edi, edi
0x14003c712  test    rsi, rsi
0x14003c715  jz      short loc_14003C728
0x14003c717  lea     rcx, [rsp+58h+var_28]
0x14003c71c  call    UHHeapFree
0x14003c721  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c728  mov     rax, [rsp+58h+var_20]
0x14003c72d  test    rax, rax
0x14003c730  jz      short loc_14003C742
0x14003c732  mov     rcx, rax; hKey
0x14003c735  call    cs:__imp_RegCloseKey
0x14003c73b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c742  mov     rax, [rsp+58h+hKey]
0x14003c747  test    rax, rax
0x14003c74a  jz      short loc_14003C75C
0x14003c74c  mov     rcx, rax; hKey
0x14003c74f  call    cs:__imp_RegCloseKey
0x14003c755  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c75c  cmp     rcx, rbx
0x14003c75f  jz      short loc_14003C788
0x14003c761  test    dword ptr [rcx+1Ch], 40000h
0x14003c768  jz      short loc_14003C788
0x14003c76a  cmp     byte ptr [rcx+19h], 4
0x14003c76e  jb      short loc_14003C788
0x14003c770  mov     edx, 33h ; '3'
0x14003c775  mov     r9d, edi
0x14003c778  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x14003c77f  mov     rcx, [rcx+10h]
0x14003c783  call    WPP_SF_d
0x14003c788  mov     eax, edi
0x14003c78a  add     rsp, 40h
0x14003c78e  pop     rdi
0x14003c78f  pop     rsi
0x14003c790  pop     rbx
0x14003c791  retn
0x14009e71e  push    rbp
0x14009e720  sub     rsp, 30h
0x14009e724  mov     rbp, rdx
0x14009e727  cmp     qword ptr [rbp+30h], 0
0x14009e72c  jz      short loc_14009E738
0x14009e72e  lea     rcx, [rbp+30h]
0x14009e732  call    UHHeapFree
0x14009e737  nop
0x14009e738  mov     rcx, [rbp+38h]; hKey
0x14009e73c  test    rcx, rcx
0x14009e73f  jz      short loc_14009E748
0x14009e741  call    cs:__imp_RegCloseKey
0x14009e747  nop
0x14009e748  mov     rcx, [rbp+78h]; hKey
0x14009e74c  test    rcx, rcx
0x14009e74f  jz      short loc_14009E758
0x14009e751  call    cs:__imp_RegCloseKey
0x14009e757  nop
0x14009e758  add     rsp, 30h
0x14009e75c  pop     rbp
0x14009e75d  retn
```
