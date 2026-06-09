# ATL::AtlUnRegisterTypeLib(HINSTANCE__ *,wchar_t const *)

- ea: `0x18000565c`
- end: `0x18000576a`
- name: `?AtlUnRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEB_W@Z`
- size: `270`
- prototype: `__int64 __fastcall(HINSTANCE, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004b70`

## callees

- `0x18000565c`
- `0x180005bec`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800056d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800056d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800056e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800056e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000574b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000574b`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x1800056f3`

## string_xrefs

- `0x1800056c9`: `OLEAUT32.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ATL::AtlUnRegisterTypeLib(HINSTANCE a1, const wchar_t *a2)
{
  int v2; // ebx
  HMODULE ModuleHandleW; // rax
  void *ProcAddress; // r10
  BSTR bstrString; // [rsp+30h] [rbp-20h] BYREF
  __int64 v7; // [rsp+38h] [rbp-18h] BYREF
  struct ITypeLib *v8; // [rsp+40h] [rbp-10h] BYREF

  bstrString = 0;
  v8 = 0;
  v2 = ATL::AtlLoadTypeLib(a1, a2, &bstrString, &v8);
  if ( v2 >= 0 )
  {
    v7 = 0;
    v2 = ((__int64 (__fastcall *)(struct ITypeLib *, __int64 *))v8->lpVtbl->GetLibAttr)(v8, &v7);
    if ( v2 >= 0 )
    {
      if ( !ATL::_AtlRegisterPerUser
        || (ModuleHandleW = GetModuleHandleW(L"OLEAUT32.DLL")) == 0
        || (ProcAddress = GetProcAddress(ModuleHandleW, "UnRegisterTypeLibForUser")) == 0 )
      {
        ProcAddress = UnRegisterTypeLib;
      }
      v2 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))ProcAddress)(
             v7,
             *(unsigned __int16 *)(v7 + 24),
             *(unsigned __int16 *)(v7 + 26),
             *(unsigned int *)(v7 + 16),
             *(_DWORD *)(v7 + 20));
      ((void (__fastcall *)(struct ITypeLib *, __int64))v8->lpVtbl->ReleaseTLibAttr)(v8, v7);
    }
  }
  if ( v8 )
    ((void (__fastcall *)(struct ITypeLib *))v8->lpVtbl->Release)(v8);
  SysFreeString(bstrString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000565c  mov     [rsp-8+arg_8], rbx
0x180005661  push    rbp
0x180005662  mov     rbp, rsp
0x180005665  sub     rsp, 50h
0x180005669  mov     rax, cs:__security_cookie
0x180005670  xor     rax, rsp
0x180005673  mov     [rbp+var_8], rax
0x180005677  mov     [rbp+bstrString], 0
0x18000567f  mov     [rbp+var_10], 0
0x180005687  lea     r9, [rbp+var_10]; struct ITypeLib **
0x18000568b  lea     r8, [rbp+bstrString]; wchar_t **
0x18000568f  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEB_WPEAPEA_WPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,wchar_t const *,wchar_t * *,ITypeLib * *)
0x180005694  mov     ebx, eax
0x180005696  test    eax, eax
0x180005698  js      loc_180005731
0x18000569e  mov     [rbp+var_18], 0
0x1800056a6  mov     rcx, [rbp+var_10]
0x1800056aa  mov     rax, [rcx]
0x1800056ad  lea     rdx, [rbp+var_18]
0x1800056b1  mov     rax, [rax+38h]
0x1800056b5  call    _guard_dispatch_icall
0x1800056ba  mov     ebx, eax
0x1800056bc  test    eax, eax
0x1800056be  js      short loc_180005731
0x1800056c0  cmp     cs:?_AtlRegisterPerUser@ATL@@3_NA, 1; bool ATL::_AtlRegisterPerUser
0x1800056c7  jnz     short loc_1800056F3
0x1800056c9  lea     rcx, ModuleName; "OLEAUT32.DLL"
0x1800056d0  call    cs:__imp_GetModuleHandleW
0x1800056d6  test    rax, rax
0x1800056d9  jz      short loc_1800056F3
0x1800056db  lea     rdx, ProcName; "UnRegisterTypeLibForUser"
0x1800056e2  mov     rcx, rax; hModule
0x1800056e5  call    cs:__imp_GetProcAddress
0x1800056eb  mov     r10, rax
0x1800056ee  test    rax, rax
0x1800056f1  jnz     short loc_1800056FA
0x1800056f3  mov     r10, cs:__imp_UnRegisterTypeLib
0x1800056fa  mov     rcx, [rbp+var_18]
0x1800056fe  mov     eax, [rcx+14h]
0x180005701  mov     [rsp+50h+var_30], eax
0x180005705  mov     r9d, [rcx+10h]
0x180005709  movzx   r8d, word ptr [rcx+1Ah]
0x18000570e  movzx   edx, word ptr [rcx+18h]
0x180005712  mov     rax, r10
0x180005715  call    _guard_dispatch_icall
0x18000571a  mov     ebx, eax
0x18000571c  mov     rcx, [rbp+var_10]
0x180005720  mov     rax, [rcx]
0x180005723  mov     rdx, [rbp+var_18]
0x180005727  mov     rax, [rax+60h]
0x18000572b  call    _guard_dispatch_icall
0x180005730  nop
0x180005731  mov     rcx, [rbp+var_10]
0x180005735  test    rcx, rcx
0x180005738  jz      short loc_180005747
0x18000573a  mov     rax, [rcx]
0x18000573d  mov     rax, [rax+10h]
0x180005741  call    _guard_dispatch_icall
0x180005746  nop
0x180005747  mov     rcx, [rbp+bstrString]; bstrString
0x18000574b  call    cs:__imp_SysFreeString
0x180005751  mov     eax, ebx
0x180005753  mov     rcx, [rbp+var_8]
0x180005757  xor     rcx, rsp; StackCookie
0x18000575a  call    __security_check_cookie
0x18000575f  mov     rbx, [rsp+50h+arg_8]
0x180005764  add     rsp, 50h
0x180005768  pop     rbp
0x180005769  retn
```
