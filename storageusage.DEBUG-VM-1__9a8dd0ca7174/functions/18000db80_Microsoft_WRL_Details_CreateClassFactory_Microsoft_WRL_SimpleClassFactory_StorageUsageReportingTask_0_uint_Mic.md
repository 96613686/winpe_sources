# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x18000db80`
- end: `0x18000dc31`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VStorageUsageReportingTask@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000db80`
- `0x18000dd00`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v7; // ebx
  _DWORD *v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12[7]; // [rsp+20h] [rbp-38h] BYREF

  v12[0] = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>,Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>,>(v12);
  if ( v7 >= 0 )
  {
    v9 = (_DWORD *)v12[0];
    *(_DWORD *)(v12[0] + 20) = *a1;
    v10 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v9)(v9, a3, a4);
    v11 = v10;
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      if ( v10 < 0 )
      {
        v9[5] &= 0xFFFFFFFA;
      }
      else if ( (*(_BYTE *)a1 & 4) != 0 )
      {
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      }
      else
      {
        v9 = 0;
      }
    }
    if ( v9 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
    return v11;
  }
  else
  {
    if ( v12[0] )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12[0] + 16LL))(v12[0]);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x18000db80  push    rbx
0x18000db82  push    rbp
0x18000db83  push    rsi
0x18000db84  push    rdi
0x18000db85  sub     rsp, 38h
0x18000db89  mov     rdi, r9
0x18000db8c  mov     rbp, r8
0x18000db8f  mov     rsi, rcx
0x18000db92  mov     [rsp+58h+var_38], 0
0x18000db9b  lea     rcx, [rsp+58h+var_38]
0x18000dba0  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VStorageUsageReportingTask@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VStorageUsageReportingTask@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>,Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>,>(Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0> * *)
0x18000dba5  mov     ebx, eax
0x18000dba7  test    eax, eax
0x18000dba9  jns     short loc_18000DBC6
0x18000dbab  mov     rcx, [rsp+58h+var_38]
0x18000dbb0  test    rcx, rcx
0x18000dbb3  jz      short loc_18000DBC2
0x18000dbb5  mov     rdx, [rcx]
0x18000dbb8  mov     rax, [rdx+10h]
0x18000dbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc1  nop
0x18000dbc2  mov     eax, ebx
0x18000dbc4  jmp     short loc_18000DC28
0x18000dbc6  mov     rbx, [rsp+58h+var_38]
0x18000dbcb  mov     eax, [rsi]
0x18000dbcd  mov     [rbx+14h], eax
0x18000dbd0  mov     rax, [rbx]
0x18000dbd3  mov     r8, rdi
0x18000dbd6  mov     rdx, rbp
0x18000dbd9  mov     rcx, rbx
0x18000dbdc  mov     rax, [rax]
0x18000dbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbe4  mov     edi, eax
0x18000dbe6  test    byte ptr [rsi], 1
0x18000dbe9  jz      short loc_18000DC11
0x18000dbeb  test    eax, eax
0x18000dbed  js      short loc_18000DC0D
0x18000dbef  test    byte ptr [rsi], 4
0x18000dbf2  jz      short loc_18000DC09
0x18000dbf4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000dbfb  mov     rax, [rcx]
0x18000dbfe  mov     rax, [rax+8]
0x18000dc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc07  jmp     short loc_18000DC11
0x18000dc09  xor     ebx, ebx
0x18000dc0b  jmp     short loc_18000DC11
0x18000dc0d  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x18000dc11  test    rbx, rbx
0x18000dc14  jz      short loc_18000DC26
0x18000dc16  mov     rax, [rbx]
0x18000dc19  mov     rcx, rbx
0x18000dc1c  mov     rax, [rax+10h]
0x18000dc20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc25  nop
0x18000dc26  mov     eax, edi
0x18000dc28  add     rsp, 38h
0x18000dc2c  pop     rdi
0x18000dc2d  pop     rsi
0x18000dc2e  pop     rbp
0x18000dc2f  pop     rbx
0x18000dc30  retn
```
