# IsComponentModuleNameResolved(_GUID const *)

- ea: `0x180010518`
- end: `0x1800105b7`
- name: `?IsComponentModuleNameResolved@@YAHPEBU_GUID@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007b28`

## callees

- `0x180007820`
- `0x18000e140`
- `0x180010518`
- `0x1800107bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001054c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001054c`

## pseudocode

```c
__int64 __fastcall IsComponentModuleNameResolved(const struct _GUID *a1, __int64 a2)
{
  unsigned int v2; // ebx
  PVOID *v3; // rcx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  pv = 0;
  if ( (int)HrGetSpecifiedWizardModuleFileName(a1, a2, (unsigned __int16 **)&pv) >= 0 )
  {
    LOBYTE(v2) = *(_WORD *)pv != 42;
    CoTaskMemFree(pv);
LABEL_6:
    v3 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
  v2 = 1;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids);
    goto LABEL_6;
  }
LABEL_7:
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x10) != 0 )
    WPP_SF_D(v3[2], 134, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180010518  mov     [rsp+arg_0], rbx
0x18001051d  push    rdi
0x18001051e  sub     rsp, 20h
0x180010522  xor     ebx, ebx
0x180010524  lea     r8, [rsp+28h+pv]
0x180010529  mov     [rsp+28h+pv], rbx
0x18001052e  call    ?HrGetSpecifiedWizardModuleFileName@@YAJPEBU_GUID@@W4tagXW_REGISTRY_SECTION_TYPE@@PEAPEAG@Z; HrGetSpecifiedWizardModuleFileName(_GUID const *,tagXW_REGISTRY_SECTION_TYPE,ushort * *)
0x180010533  lea     rdi, WPP_GLOBAL_Control
0x18001053a  test    eax, eax
0x18001053c  js      short loc_180010554
0x18001053e  mov     rcx, [rsp+28h+pv]; pv
0x180010543  lea     eax, [rbx+2Ah]
0x180010546  cmp     ax, [rcx]
0x180010549  setnz   bl
0x18001054c  call    cs:__imp_CoTaskMemFree
0x180010552  jmp     short loc_180010580
0x180010554  mov     rcx, cs:WPP_GLOBAL_Control
0x18001055b  mov     ebx, 1
0x180010560  cmp     rcx, rdi
0x180010563  jz      short loc_1800105AA
0x180010565  test    byte ptr [rcx+1Ch], 10h
0x180010569  jz      short loc_180010587
0x18001056b  mov     rcx, [rcx+10h]
0x18001056f  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x180010576  mov     edx, 85h
0x18001057b  call    WPP_SF_
0x180010580  mov     rcx, cs:WPP_GLOBAL_Control
0x180010587  cmp     rcx, rdi
0x18001058a  jz      short loc_1800105AA
0x18001058c  test    byte ptr [rcx+1Ch], 10h
0x180010590  jz      short loc_1800105AA
0x180010592  mov     rcx, [rcx+10h]
0x180010596  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18001059d  mov     edx, 86h
0x1800105a2  mov     r9d, ebx
0x1800105a5  call    WPP_SF_D
0x1800105aa  mov     eax, ebx
0x1800105ac  mov     rbx, [rsp+28h+arg_0]
0x1800105b1  add     rsp, 20h
0x1800105b5  pop     rdi
0x1800105b6  retn
```
