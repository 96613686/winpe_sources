# CBlbRestoreComponentAsync::FinalRelease(void)

- ea: `0x14006ba88`
- end: `0x14006bc10`
- name: `?FinalRelease@CBlbRestoreComponentAsync@@QEAAXXZ`
- size: `392`
- prototype: `void __fastcall(CBlbRestoreComponentAsync *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14003e080`

## callees

- `0x140006d88`
- `0x14000bfd8`
- `0x14006ba88`
- `0x140098c04`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14006bacf`
- `ole32!CoTaskMemFree` at `0x14006baec`
- `ole32!CoTaskMemFree` at `0x14006bb09`
- `ole32!CoTaskMemFree` at `0x14006bb26`
- `ole32!CoTaskMemFree` at `0x14006bb43`
- `ole32!CoTaskMemFree` at `0x14006bb88`
- `ole32!CoTaskMemFree` at `0x14006bb9a`
- `ole32!CoTaskMemFree` at `0x14006bacf`
- `ole32!CoTaskMemFree` at `0x14006baec`
- `ole32!CoTaskMemFree` at `0x14006bb09`
- `ole32!CoTaskMemFree` at `0x14006bb26`
- `ole32!CoTaskMemFree` at `0x14006bb43`
- `ole32!CoTaskMemFree` at `0x14006bb88`
- `ole32!CoTaskMemFree` at `0x14006bb9a`

## pseudocode

```c
void __fastcall CBlbRestoreComponentAsync::FinalRelease(CBlbRestoreComponentAsync *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rax
  void *v9; // rcx
  void *v10; // rcx
  unsigned int i; // edi
  _QWORD *v12; // rsi
  __int64 v13; // rcx

  v2 = *((_QWORD *)this + 28);
  if ( v2 )
  {
    if ( *(_QWORD *)(v2 - 8) )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 32LL))(v2, 3);
    else
      operator delete[]((void *)(v2 - 8));
  }
  v3 = (void *)*((_QWORD *)this + 34);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 34) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 35);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 35) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 36);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 36) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 37);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)this + 37) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 38);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)this + 38) = 0;
  }
  v8 = *((_QWORD *)this + 39) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v8 )
    v8 = *((_QWORD *)this + 40) - *(_QWORD *)GUID_NULL.Data4;
  if ( v8 )
    FreeBackupSetContents((CBlbRestoreComponentAsync *)((char *)this + 312));
  v9 = (void *)*((_QWORD *)this + 68);
  if ( v9 )
    CoTaskMemFree(v9);
  v10 = (void *)*((_QWORD *)this + 67);
  if ( v10 )
    CoTaskMemFree(v10);
  for ( i = 0; i < *((_DWORD *)this + 66); *v12 = 0 )
  {
    v12 = (_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                      (_QWORD *)this + 29,
                      i);
    if ( *v12 )
      (**(void (__fastcall ***)(_QWORD, __int64))*v12)(*v12, 1);
    ++i;
  }
  v13 = *((_QWORD *)this + 69);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)this + 69) = 0;
  }
}

```

## disassembly

```asm
0x14006ba88  push    rbx
0x14006ba8a  push    rbp
0x14006ba8b  push    rsi
0x14006ba8c  push    rdi
0x14006ba8d  sub     rsp, 28h
0x14006ba91  mov     rbx, rcx
0x14006ba94  mov     rcx, [rcx+0E0h]
0x14006ba9b  test    rcx, rcx
0x14006ba9e  jz      short loc_14006BAC3
0x14006baa0  cmp     qword ptr [rcx-8], 0
0x14006baa5  jz      short loc_14006BABA
0x14006baa7  mov     rax, [rcx]
0x14006baaa  mov     edx, 3
0x14006baaf  mov     rax, [rax+20h]
0x14006bab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bab8  jmp     short loc_14006BAC3
0x14006baba  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x14006babe  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x14006bac3  mov     rcx, [rbx+110h]; pv
0x14006baca  test    rcx, rcx
0x14006bacd  jz      short loc_14006BAE0
0x14006bacf  call    cs:__imp_CoTaskMemFree
0x14006bad5  mov     qword ptr [rbx+110h], 0
0x14006bae0  mov     rcx, [rbx+118h]; pv
0x14006bae7  test    rcx, rcx
0x14006baea  jz      short loc_14006BAFD
0x14006baec  call    cs:__imp_CoTaskMemFree
0x14006baf2  mov     qword ptr [rbx+118h], 0
0x14006bafd  mov     rcx, [rbx+120h]; pv
0x14006bb04  test    rcx, rcx
0x14006bb07  jz      short loc_14006BB1A
0x14006bb09  call    cs:__imp_CoTaskMemFree
0x14006bb0f  mov     qword ptr [rbx+120h], 0
0x14006bb1a  mov     rcx, [rbx+128h]; pv
0x14006bb21  test    rcx, rcx
0x14006bb24  jz      short loc_14006BB37
0x14006bb26  call    cs:__imp_CoTaskMemFree
0x14006bb2c  mov     qword ptr [rbx+128h], 0
0x14006bb37  mov     rcx, [rbx+130h]; pv
0x14006bb3e  test    rcx, rcx
0x14006bb41  jz      short loc_14006BB54
0x14006bb43  call    cs:__imp_CoTaskMemFree
0x14006bb49  mov     qword ptr [rbx+130h], 0
0x14006bb54  lea     rcx, [rbx+138h]; struct _BLBCAT_BACKUP_SET_INFO *
0x14006bb5b  mov     rax, [rcx]
0x14006bb5e  sub     rax, qword ptr cs:GUID_NULL.Data1
0x14006bb65  jnz     short loc_14006BB72
0x14006bb67  mov     rax, [rcx+8]
0x14006bb6b  sub     rax, qword ptr cs:GUID_NULL.Data4
0x14006bb72  test    rax, rax
0x14006bb75  jz      short loc_14006BB7C
0x14006bb77  call    ?FreeBackupSetContents@@YAXPEAU_BLBCAT_BACKUP_SET_INFO@@@Z; FreeBackupSetContents(_BLBCAT_BACKUP_SET_INFO *)
0x14006bb7c  mov     rcx, [rbx+220h]; pv
0x14006bb83  test    rcx, rcx
0x14006bb86  jz      short loc_14006BB8E
0x14006bb88  call    cs:__imp_CoTaskMemFree
0x14006bb8e  mov     rcx, [rbx+218h]; pv
0x14006bb95  test    rcx, rcx
0x14006bb98  jz      short loc_14006BBA0
0x14006bb9a  call    cs:__imp_CoTaskMemFree
0x14006bba0  xor     edi, edi
0x14006bba2  cmp     [rbx+108h], edi
0x14006bba8  jbe     short loc_14006BBE4
0x14006bbaa  mov     edx, edi
0x14006bbac  lea     rcx, [rbx+0E8h]
0x14006bbb3  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x14006bbb8  mov     rsi, rax
0x14006bbbb  mov     rcx, [rax]
0x14006bbbe  test    rcx, rcx
0x14006bbc1  jz      short loc_14006BBD3
0x14006bbc3  mov     rdx, [rcx]
0x14006bbc6  mov     rax, [rdx]
0x14006bbc9  mov     edx, 1
0x14006bbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bbd3  inc     edi
0x14006bbd5  mov     qword ptr [rsi], 0
0x14006bbdc  cmp     edi, [rbx+108h]
0x14006bbe2  jb      short loc_14006BBAA
0x14006bbe4  mov     rcx, [rbx+228h]
0x14006bbeb  test    rcx, rcx
0x14006bbee  jz      short loc_14006BC07
0x14006bbf0  mov     rax, [rcx]
0x14006bbf3  mov     rax, [rax+10h]
0x14006bbf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006bbfc  mov     qword ptr [rbx+228h], 0
0x14006bc07  add     rsp, 28h
0x14006bc0b  pop     rdi
0x14006bc0c  pop     rsi
0x14006bc0d  pop     rbp
0x14006bc0e  pop     rbx
0x14006bc0f  retn
```
