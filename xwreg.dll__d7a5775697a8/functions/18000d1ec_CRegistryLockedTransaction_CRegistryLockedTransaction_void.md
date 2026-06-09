# CRegistryLockedTransaction::~CRegistryLockedTransaction(void)

- ea: `0x18000d1ec`
- end: `0x18000d252`
- name: `??1CRegistryLockedTransaction@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(CRegistryLockedTransaction *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180007a5c`

## callees

- `0x180007820`
- `0x18000d1ec`
- `0x18000d26c`
- `0x18000d548`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d24b`

## pseudocode

```c
void __fastcall CRegistryLockedTransaction::~CRegistryLockedTransaction(WCHAR *this)
{
  int v2; // eax
  PVOID *v3; // rdx

  v2 = CRegistryLockedTransaction::HrReleaseKey((CRegistryLockedTransaction *)this);
  *((_DWORD *)this + 143) = v2;
  if ( v2 < 0 )
  {
    v3 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_b6864e106af034a19631ace060353c02_Traceguids,
        (unsigned int)v2);
  }
  if ( *(_QWORD *)this )
    CPXWizardMutexLock::`scalar deleting destructor'(*(CPXWizardMutexLock **)this, (unsigned int)v3);
  DeleteFileW(this + 8);
}

```

## disassembly

```asm
0x18000d1ec  push    rbx
0x18000d1ee  sub     rsp, 20h
0x18000d1f2  mov     rbx, rcx
0x18000d1f5  call    ?HrReleaseKey@CRegistryLockedTransaction@@QEAAJXZ; CRegistryLockedTransaction::HrReleaseKey(void)
0x18000d1fa  mov     [rbx+23Ch], eax
0x18000d200  test    eax, eax
0x18000d202  jns     short loc_18000D235
0x18000d204  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d20b  lea     rdx, WPP_GLOBAL_Control
0x18000d212  cmp     rcx, rdx
0x18000d215  jz      short loc_18000D235
0x18000d217  test    byte ptr [rcx+1Ch], 4
0x18000d21b  jz      short loc_18000D235
0x18000d21d  mov     rcx, [rcx+10h]
0x18000d221  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d228  mov     edx, 15h
0x18000d22d  mov     r9d, eax
0x18000d230  call    WPP_SF_D
0x18000d235  mov     rcx, [rbx]; this
0x18000d238  test    rcx, rcx
0x18000d23b  jz      short loc_18000D242
0x18000d23d  call    ??_GCPXWizardMutexLock@@QEAAPEAXI@Z; CPXWizardMutexLock::`scalar deleting destructor'(uint)
0x18000d242  lea     rcx, [rbx+10h]
0x18000d246  add     rsp, 20h
0x18000d24a  pop     rbx
0x18000d24b  jmp     cs:__imp_DeleteFileW
```
