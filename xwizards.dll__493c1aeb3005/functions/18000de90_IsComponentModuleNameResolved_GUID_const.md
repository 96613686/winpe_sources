# IsComponentModuleNameResolved(_GUID const *)

- ea: `0x18000de90`
- end: `0x18000df35`
- name: `?IsComponentModuleNameResolved@@YAHPEBU_GUID@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021634`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x18000c4a0`
- `0x18000de90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000decf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000decf`

## pseudocode

```c
_BOOL8 __fastcall IsComponentModuleNameResolved(const struct _GUID *a1)
{
  BOOL v1; // ebx
  PVOID *v2; // rcx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  v1 = 1;
  pv = 0;
  if ( (int)HrGetSpecifiedWizardModuleFileName(a1, 1, (unsigned __int16 **)&pv) >= 0 )
  {
    v1 = *(_WORD *)pv != 42;
    CoTaskMemFree(pv);
LABEL_6:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids);
    goto LABEL_6;
  }
LABEL_7:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x10) != 0 )
    WPP_SF_d(v2[2], 134, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18000de90  mov     [rsp+arg_0], rbx
0x18000de95  push    rdi
0x18000de96  sub     rsp, 20h
0x18000de9a  mov     ebx, 1
0x18000de9f  mov     [rsp+28h+pv], 0
0x18000dea8  mov     edx, ebx
0x18000deaa  lea     r8, [rsp+28h+pv]
0x18000deaf  call    ?HrGetSpecifiedWizardModuleFileName@@YAJPEBU_GUID@@W4tagXW_REGISTRY_SECTION_TYPE@@PEAPEAG@Z; HrGetSpecifiedWizardModuleFileName(_GUID const *,tagXW_REGISTRY_SECTION_TYPE,ushort * *)
0x18000deb4  lea     rdi, WPP_GLOBAL_Control
0x18000debb  test    eax, eax
0x18000debd  js      short loc_18000DED7
0x18000debf  mov     rcx, [rsp+28h+pv]; pv
0x18000dec4  lea     eax, [rbx+29h]
0x18000dec7  xor     ebx, ebx
0x18000dec9  cmp     ax, [rcx]
0x18000decc  setnz   bl
0x18000decf  call    cs:__imp_CoTaskMemFree
0x18000ded5  jmp     short loc_18000DEFE
0x18000ded7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dede  cmp     rcx, rdi
0x18000dee1  jz      short loc_18000DF28
0x18000dee3  test    byte ptr [rcx+1Ch], 10h
0x18000dee7  jz      short loc_18000DF05
0x18000dee9  mov     rcx, [rcx+10h]
0x18000deed  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000def4  mov     edx, 85h
0x18000def9  call    WPP_SF_
0x18000defe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df05  cmp     rcx, rdi
0x18000df08  jz      short loc_18000DF28
0x18000df0a  test    byte ptr [rcx+1Ch], 10h
0x18000df0e  jz      short loc_18000DF28
0x18000df10  mov     rcx, [rcx+10h]
0x18000df14  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000df1b  mov     edx, 86h
0x18000df20  mov     r9d, ebx
0x18000df23  call    WPP_SF_d
0x18000df28  mov     eax, ebx
0x18000df2a  mov     rbx, [rsp+28h+arg_0]
0x18000df2f  add     rsp, 20h
0x18000df33  pop     rdi
0x18000df34  retn
```
