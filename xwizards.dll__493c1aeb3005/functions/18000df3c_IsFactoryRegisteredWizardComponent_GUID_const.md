# IsFactoryRegisteredWizardComponent(_GUID const *)

- ea: `0x18000df3c`
- end: `0x18000e034`
- name: `?IsFactoryRegisteredWizardComponent@@YAHPEBU_GUID@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017c40`
- `0x18001cd9c`
- `0x18001efb0`
- `0x180021d04`
- `0x180024074`
- `0x180028c50`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x18000c4a0`
- `0x18000df3c`
- `0x18000e8dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dfc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dfc0`

## string_xrefs

- `0x18000df7a`: `xwizards.dll`

## pseudocode

```c
_BOOL8 __fastcall IsFactoryRegisteredWizardComponent(const struct _GUID *a1)
{
  BOOL v1; // edi
  unsigned __int16 *v3; // rbx
  PVOID *v4; // rcx
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF

  v1 = 1;
  pv = 0;
  if ( (int)HrGetSpecifiedWizardModuleFileName(a1, 1, (unsigned __int16 **)&pv) >= 0 )
  {
    v3 = wcsistr((const unsigned __int16 *)pv, L"xwizards.dll");
    CoTaskMemFree(pv);
    if ( v3 || (pv = 0, (int)HrGetSpecifiedWizardModuleFileName(a1, 2, (unsigned __int16 **)&pv) < 0) )
      v1 = v3 != 0;
    else
      CoTaskMemFree(pv);
    goto LABEL_9;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  v1 = 0;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids);
LABEL_9:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 )
    WPP_SF_d(v4[2], 132, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18000df3c  mov     rax, rsp
0x18000df3f  mov     [rax+8], rbx
0x18000df43  mov     [rax+18h], rbp
0x18000df47  push    rsi
0x18000df48  push    rdi
0x18000df49  push    r14
0x18000df4b  sub     rsp, 20h
0x18000df4f  mov     edi, 1
0x18000df54  mov     qword ptr [rax+10h], 0
0x18000df5c  mov     edx, edi
0x18000df5e  lea     r8, [rax+10h]
0x18000df62  mov     rbp, rcx
0x18000df65  call    ?HrGetSpecifiedWizardModuleFileName@@YAJPEBU_GUID@@W4tagXW_REGISTRY_SECTION_TYPE@@PEAPEAG@Z; HrGetSpecifiedWizardModuleFileName(_GUID const *,tagXW_REGISTRY_SECTION_TYPE,ushort * *)
0x18000df6a  lea     r14, WPP_GLOBAL_Control
0x18000df71  test    eax, eax
0x18000df73  js      short loc_18000DFCC
0x18000df75  mov     rcx, [rsp+38h+pv]; unsigned __int16 *
0x18000df7a  lea     rdx, aXwizardsDll_0; "xwizards.dll"
0x18000df81  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x18000df86  mov     rcx, [rsp+38h+pv]; pv
0x18000df8b  xor     esi, esi
0x18000df8d  test    rax, rax
0x18000df90  mov     rbx, rax
0x18000df93  setnz   sil
0x18000df97  call    cs:__imp_CoTaskMemFree
0x18000df9d  test    rbx, rbx
0x18000dfa0  jnz     short loc_18000DFC8
0x18000dfa2  lea     r8, [rsp+38h+pv]
0x18000dfa7  mov     [rsp+38h+pv], rbx
0x18000dfac  lea     edx, [rdi+1]
0x18000dfaf  mov     rcx, rbp
0x18000dfb2  call    ?HrGetSpecifiedWizardModuleFileName@@YAJPEBU_GUID@@W4tagXW_REGISTRY_SECTION_TYPE@@PEAPEAG@Z; HrGetSpecifiedWizardModuleFileName(_GUID const *,tagXW_REGISTRY_SECTION_TYPE,ushort * *)
0x18000dfb7  test    eax, eax
0x18000dfb9  js      short loc_18000DFC8
0x18000dfbb  mov     rcx, [rsp+38h+pv]; pv
0x18000dfc0  call    cs:__imp_CoTaskMemFree
0x18000dfc6  jmp     short loc_18000DFF5
0x18000dfc8  mov     edi, esi
0x18000dfca  jmp     short loc_18000DFF5
0x18000dfcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfd3  xor     edi, edi
0x18000dfd5  cmp     rcx, r14
0x18000dfd8  jz      short loc_18000E01F
0x18000dfda  test    byte ptr [rcx+1Ch], 10h
0x18000dfde  jz      short loc_18000DFFC
0x18000dfe0  mov     rcx, [rcx+10h]
0x18000dfe4  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000dfeb  mov     edx, 83h
0x18000dff0  call    WPP_SF_
0x18000dff5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dffc  cmp     rcx, r14
0x18000dfff  jz      short loc_18000E01F
0x18000e001  test    byte ptr [rcx+1Ch], 10h
0x18000e005  jz      short loc_18000E01F
0x18000e007  mov     rcx, [rcx+10h]
0x18000e00b  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000e012  mov     edx, 84h
0x18000e017  mov     r9d, edi
0x18000e01a  call    WPP_SF_d
0x18000e01f  mov     rbx, [rsp+38h+arg_0]
0x18000e024  mov     eax, edi
0x18000e026  mov     rbp, [rsp+38h+arg_10]
0x18000e02b  add     rsp, 20h
0x18000e02f  pop     r14
0x18000e031  pop     rdi
0x18000e032  pop     rsi
0x18000e033  retn
```
