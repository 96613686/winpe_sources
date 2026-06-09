# CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>::~CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>(void)

- ea: `0x180003f1c`
- end: `0x180003f78`
- name: `??1?$CSxArrayBuilder@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@$1?_FreeCbsHiveLoadInformation@2@SAXPEAU12@@Z$1??$SxDefaultInit@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@@@YAX0@Z$1??$SxDefaultTransfer@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@@@YAX00@Z@@AEAA@XZ`
- size: `92`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x1800044ac`
- `0x18000a70c`

## callees

- `0x180003f1c`
- `0x18000508c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003f53`
- `ole32!CoTaskMemFree` at `0x180003f53`

## pseudocode

```c
void __fastcall CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&public: static void CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>::~CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&public: static void CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>(
        __int64 a1)
{
  __int64 v1; // rsi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); (unsigned int)v1 < *(_DWORD *)(a1 + 16); v1 = (unsigned int)(v1 + 1) )
    CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation((struct CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)((char *)*i + 24 * v1));
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180003f1c  mov     [rsp+arg_0], rbx
0x180003f21  mov     [rsp+arg_8], rsi
0x180003f26  push    rdi
0x180003f27  sub     rsp, 20h
0x180003f2b  xor     esi, esi
0x180003f2d  lea     rbx, [rcx+8]
0x180003f31  mov     rdi, rcx
0x180003f34  cmp     [rcx+10h], esi
0x180003f37  jbe     short loc_180003F50
0x180003f39  mov     rax, [rbx]
0x180003f3c  lea     rcx, [rsi+rsi*2]
0x180003f40  lea     rcx, [rax+rcx*8]; struct CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *
0x180003f44  call    ?_FreeCbsHiveLoadInformation@CSxWindowsUpdateEnumerator@@SAXPEAU_CBS_LOADED_HIVE_INFORMATION@1@@Z; CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)
0x180003f49  inc     esi
0x180003f4b  cmp     esi, [rdi+10h]
0x180003f4e  jb      short loc_180003F39
0x180003f50  mov     rcx, [rbx]; pv
0x180003f53  call    cs:__imp_CoTaskMemFree
0x180003f59  mov     rsi, [rsp+28h+arg_8]
0x180003f5e  mov     qword ptr [rbx], 0
0x180003f65  mov     rbx, [rsp+28h+arg_0]
0x180003f6a  mov     qword ptr [rdi+10h], 0
0x180003f72  add     rsp, 20h
0x180003f76  pop     rdi
0x180003f77  retn
```
