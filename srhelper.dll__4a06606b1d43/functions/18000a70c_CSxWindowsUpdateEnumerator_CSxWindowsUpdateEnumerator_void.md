# CSxWindowsUpdateEnumerator::~CSxWindowsUpdateEnumerator(void)

- ea: `0x18000a70c`
- end: `0x18000a785`
- name: `??1CSxWindowsUpdateEnumerator@@QEAA@XZ`
- size: `121`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18000cc20`

## callees

- `0x1800012d4`
- `0x180003f1c`
- `0x18000a70c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000a71d`
- `ole32!CoTaskMemFree` at `0x18000a72f`
- `ole32!CoTaskMemFree` at `0x18000a741`
- `ole32!CoTaskMemFree` at `0x18000a71d`
- `ole32!CoTaskMemFree` at `0x18000a72f`
- `ole32!CoTaskMemFree` at `0x18000a741`

## pseudocode

```c
void __fastcall CSxWindowsUpdateEnumerator::~CSxWindowsUpdateEnumerator(LPVOID *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rbx

  CoTaskMemFree(this[1]);
  v2 = this[2];
  this[1] = 0;
  CoTaskMemFree(v2);
  v3 = this[3];
  this[2] = 0;
  CoTaskMemFree(v3);
  this[3] = 0;
  v4 = *this;
  if ( *this )
  {
    *this = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4, 0xFFFFFFFF) == 1 )
    {
      CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&public: static void CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>::~CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&public: static void CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>((__int64)v4);
      operator delete(v4);
    }
  }
}

```

## disassembly

```asm
0x18000a70c  mov     [rsp+arg_8], rbx
0x18000a711  push    rdi
0x18000a712  sub     rsp, 20h
0x18000a716  mov     rdi, rcx
0x18000a719  mov     rcx, [rcx+8]; pv
0x18000a71d  call    cs:__imp_CoTaskMemFree
0x18000a723  mov     rcx, [rdi+10h]; pv
0x18000a727  mov     qword ptr [rdi+8], 0
0x18000a72f  call    cs:__imp_CoTaskMemFree
0x18000a735  mov     rcx, [rdi+18h]; pv
0x18000a739  mov     qword ptr [rdi+10h], 0
0x18000a741  call    cs:__imp_CoTaskMemFree
0x18000a747  mov     qword ptr [rdi+18h], 0
0x18000a74f  mov     rbx, [rdi]
0x18000a752  test    rbx, rbx
0x18000a755  jz      short loc_18000A77A
0x18000a757  mov     qword ptr [rdi], 0
0x18000a75e  or      eax, 0FFFFFFFFh
0x18000a761  lock xadd [rbx], eax
0x18000a765  cmp     eax, 1
0x18000a768  jnz     short loc_18000A77A
0x18000a76a  mov     rcx, rbx
0x18000a76d  call    ??1?$CSxArrayBuilder@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@$1?_FreeCbsHiveLoadInformation@2@SAXPEAU12@@Z$1??$SxDefaultInit@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@@@YAX0@Z$1??$SxDefaultTransfer@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@@@YAX00@Z@@AEAA@XZ; CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>::~CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>(void)
0x18000a772  mov     rcx, rbx; Block
0x18000a775  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a77a  mov     rbx, [rsp+28h+arg_8]
0x18000a77f  add     rsp, 20h
0x18000a783  pop     rdi
0x18000a784  retn
```
