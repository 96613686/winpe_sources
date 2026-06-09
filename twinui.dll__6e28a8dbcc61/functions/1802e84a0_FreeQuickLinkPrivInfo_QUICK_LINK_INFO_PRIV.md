# FreeQuickLinkPrivInfo(QUICK_LINK_INFO_PRIV *)

- ea: `0x1802e84a0`
- end: `0x1802e8528`
- name: `?FreeQuickLinkPrivInfo@@YAXPEAUQUICK_LINK_INFO_PRIV@@@Z`
- size: `136`
- prototype: `void __fastcall(struct QUICK_LINK_INFO_PRIV *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802e7d98`
- `0x1802ff0ac`

## callees

- `0x18013df8c`
- `0x1802e8530`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e84e8`

## pseudocode

```c
void __fastcall FreeQuickLinkPrivInfo(struct QUICK_LINK_INFO_PRIV *a1)
{
  unsigned __int16 **v2; // rdx
  unsigned int v3; // ecx

  CoTaskMemFree(*(LPVOID *)a1);
  CoTaskMemFree(*((LPVOID *)a1 + 1));
  CoTaskMemFree(*((LPVOID *)a1 + 2));
  CoTaskMemFree(*((LPVOID *)a1 + 3));
  CoTaskMemFree(*((LPVOID *)a1 + 4));
  CoTaskMemFree(*((LPVOID *)a1 + 5));
  CoTaskMemFree(*((LPVOID *)a1 + 6));
  FreeStringArray(*((_DWORD *)a1 + 14), *((unsigned __int16 ***)a1 + 8));
  v2 = (unsigned __int16 **)*((_QWORD *)a1 + 9);
  v3 = *((_DWORD *)a1 + 15);
  *((_DWORD *)a1 + 14) = 0;
  *((_QWORD *)a1 + 8) = 0;
  FreeStringArray(v3, v2);
  memset_0(a1, 0, 0x58u);
}

```

## disassembly

```asm
0x1802e84a0  push    rbx
0x1802e84a2  sub     rsp, 20h
0x1802e84a6  mov     rbx, rcx
0x1802e84a9  mov     rcx, [rcx]; pv
0x1802e84ac  call    cs:__imp_CoTaskMemFree
0x1802e84b2  mov     rcx, [rbx+8]; pv
0x1802e84b6  call    cs:__imp_CoTaskMemFree
0x1802e84bc  mov     rcx, [rbx+10h]; pv
0x1802e84c0  call    cs:__imp_CoTaskMemFree
0x1802e84c6  mov     rcx, [rbx+18h]; pv
0x1802e84ca  call    cs:__imp_CoTaskMemFree
0x1802e84d0  mov     rcx, [rbx+20h]; pv
0x1802e84d4  call    cs:__imp_CoTaskMemFree
0x1802e84da  mov     rcx, [rbx+28h]; pv
0x1802e84de  call    cs:__imp_CoTaskMemFree
0x1802e84e4  mov     rcx, [rbx+30h]; pv
0x1802e84e8  call    cs:__imp_CoTaskMemFree
0x1802e84ee  mov     rdx, [rbx+40h]; unsigned __int16 **
0x1802e84f2  mov     ecx, [rbx+38h]; unsigned int
0x1802e84f5  call    ?FreeStringArray@@YAXKPEAPEAG@Z; FreeStringArray(ulong,ushort * *)
0x1802e84fa  mov     rdx, [rbx+48h]; unsigned __int16 **
0x1802e84fe  mov     ecx, [rbx+3Ch]; unsigned int
0x1802e8501  mov     dword ptr [rbx+38h], 0
0x1802e8508  mov     qword ptr [rbx+40h], 0
0x1802e8510  call    ?FreeStringArray@@YAXKPEAPEAG@Z; FreeStringArray(ulong,ushort * *)
0x1802e8515  xor     edx, edx; Val
0x1802e8517  mov     rcx, rbx; void *
0x1802e851a  lea     r8d, [rdx+58h]; Size
0x1802e851e  add     rsp, 20h
0x1802e8522  pop     rbx
0x1802e8523  jmp     memset_0
```
