# HrGetSpecifiedWizardModule(_GUID const *,tagXW_REGISTRY_SECTION_TYPE,HINSTANCE__ * *)

- ea: `0x18000c3ac`
- end: `0x18000c499`
- name: `?HrGetSpecifiedWizardModule@@YAJPEBU_GUID@@W4tagXW_REGISTRY_SECTION_TYPE@@PEAPEAUHINSTANCE__@@@Z`
- size: `237`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f8d0`
- `0x18000f990`
- `0x18001c19c`
- `0x180021d04`
- `0x180024074`

## callees

- `0x180004370`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000c3ac`
- `0x18000c4a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c40b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c40b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c45c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c45c`

## pseudocode

```c
__int64 __fastcall HrGetSpecifiedWizardModule(const GUID *a1, int a2, HMODULE *a3)
{
  int SpecifiedWizardModuleFileName; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  HMODULE Library; // rax
  int LastErrorHRESULT; // eax
  LPCWSTR lpLibFileName; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  lpLibFileName = 0;
  SpecifiedWizardModuleFileName = HrGetSpecifiedWizardModuleFileName(a1, a2, (unsigned __int16 **)&lpLibFileName);
  if ( SpecifiedWizardModuleFileName >= 0 )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 0);
    *a3 = Library;
    if ( !Library )
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      SpecifiedWizardModuleFileName = LastErrorHRESULT;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          84,
          (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
          (_DWORD)lpLibFileName,
          LastErrorHRESULT);
    }
    CoTaskMemFree((LPVOID)lpLibFileName);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 85;
      goto LABEL_12;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 83;
LABEL_12:
      WPP_SF_d(v5[2], v6, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, (unsigned int)SpecifiedWizardModuleFileName);
    }
  }
  return (unsigned int)SpecifiedWizardModuleFileName;
}

```

## disassembly

```asm
0x18000c3ac  mov     [rsp+arg_0], rbx
0x18000c3b1  push    rdi
0x18000c3b2  sub     rsp, 30h
0x18000c3b6  mov     rdi, r8
0x18000c3b9  mov     qword ptr [r8], 0
0x18000c3c0  lea     r8, [rsp+38h+lpLibFileName]
0x18000c3c5  mov     [rsp+38h+lpLibFileName], 0
0x18000c3ce  call    ?HrGetSpecifiedWizardModuleFileName@@YAJPEBU_GUID@@W4tagXW_REGISTRY_SECTION_TYPE@@PEAPEAG@Z; HrGetSpecifiedWizardModuleFileName(_GUID const *,tagXW_REGISTRY_SECTION_TYPE,ushort * *)
0x18000c3d3  mov     ebx, eax
0x18000c3d5  test    eax, eax
0x18000c3d7  jns     short loc_18000C401
0x18000c3d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3e0  lea     rdi, WPP_GLOBAL_Control
0x18000c3e7  cmp     rcx, rdi
0x18000c3ea  jz      loc_18000C48C
0x18000c3f0  test    byte ptr [rcx+1Ch], 10h
0x18000c3f4  jz      loc_18000C48C
0x18000c3fa  mov     edx, 53h ; 'S'
0x18000c3ff  jmp     short loc_18000C479
0x18000c401  mov     rcx, [rsp+38h+lpLibFileName]; lpLibFileName
0x18000c406  xor     r8d, r8d; dwFlags
0x18000c409  xor     edx, edx; hFile
0x18000c40b  call    cs:__imp_LoadLibraryExW
0x18000c411  mov     [rdi], rax
0x18000c414  lea     rdi, WPP_GLOBAL_Control
0x18000c41b  test    rax, rax
0x18000c41e  jnz     short loc_18000C457
0x18000c420  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000c425  mov     ebx, eax
0x18000c427  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c42e  cmp     rcx, rdi
0x18000c431  jz      short loc_18000C457
0x18000c433  test    byte ptr [rcx+1Ch], 4
0x18000c437  jz      short loc_18000C457
0x18000c439  mov     r9, [rsp+38h+lpLibFileName]
0x18000c43e  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000c445  mov     rcx, [rcx+10h]
0x18000c449  mov     edx, 54h ; 'T'
0x18000c44e  mov     [rsp+38h+var_18], eax
0x18000c452  call    WPP_SF_SD
0x18000c457  mov     rcx, [rsp+38h+lpLibFileName]; pv
0x18000c45c  call    cs:__imp_CoTaskMemFree
0x18000c462  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c469  cmp     rcx, rdi
0x18000c46c  jz      short loc_18000C48C
0x18000c46e  test    byte ptr [rcx+1Ch], 10h
0x18000c472  jz      short loc_18000C48C
0x18000c474  mov     edx, 55h ; 'U'
0x18000c479  mov     rcx, [rcx+10h]
0x18000c47d  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000c484  mov     r9d, ebx
0x18000c487  call    WPP_SF_d
0x18000c48c  mov     eax, ebx
0x18000c48e  mov     rbx, [rsp+38h+arg_0]
0x18000c493  add     rsp, 30h
0x18000c497  pop     rdi
0x18000c498  retn
```
