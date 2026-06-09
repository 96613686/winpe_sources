# CUwfStaticVolumeConfiguration::DeleteTightBindingConfiguration(void)

- ea: `0x1800072b0`
- end: `0x18000734f`
- name: `?DeleteTightBindingConfiguration@CUwfStaticVolumeConfiguration@@AEAAXXZ`
- size: `159`
- prototype: `void __fastcall(CUwfStaticVolumeConfiguration *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007120`
- `0x18000bc90`

## callees

- `0x1800072b0`
- `0x18000dd80`

## pseudocode

```c
void __fastcall CUwfStaticVolumeConfiguration::DeleteTightBindingConfiguration(CUwfStaticVolumeConfiguration *this)
{
  CUwfRegKey *v1; // rbx
  int v3; // eax
  int v4; // r8d

  v1 = (CUwfStaticVolumeConfiguration *)((char *)this + 16);
  v3 = CUwfRegKey::DeleteValue((CUwfStaticVolumeConfiguration *)((char *)this + 16), L"PartitionStyle");
  v4 = v3;
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -2147024894
    || (v4 = CUwfRegKey::DeleteValue(v1, L"PartitionOffset"), ((v4 + 0x80000000) & 0x80000000) == 0)
    && v4 != -2147024894
    || (v4 = CUwfRegKey::DeleteValue(v1, L"DiskSignature"), ((v4 + 0x80000000) & 0x80000000) == 0) && v4 != -2147024894
    || (v4 = CUwfRegKey::DeleteValue(v1, L"PartitionGuid"), ((v4 + 0x80000000) & 0x80000000) == 0) && v4 != -2147024894 )
  {
    *(_DWORD *)(*((_QWORD *)this + 3) + 16LL) = v4;
  }
}

```

## disassembly

```asm
0x1800072b0  push    rbx
0x1800072b2  push    rbp
0x1800072b3  push    rsi
0x1800072b4  push    rdi
0x1800072b5  sub     rsp, 28h
0x1800072b9  lea     rbx, [rcx+10h]
0x1800072bd  mov     rdi, rcx
0x1800072c0  mov     rcx, rbx; this
0x1800072c3  lea     rdx, aPartitionstyle; "PartitionStyle"
0x1800072ca  call    ?DeleteValue@CUwfRegKey@@QEAAJPEBG@Z; CUwfRegKey::DeleteValue(ushort const *)
0x1800072cf  mov     ebp, 80000000h
0x1800072d4  mov     r8d, eax
0x1800072d7  mov     esi, 80070002h
0x1800072dc  lea     edx, [rax+rbp]
0x1800072df  test    ebp, edx
0x1800072e1  jnz     short loc_1800072E7
0x1800072e3  cmp     eax, esi
0x1800072e5  jnz     short loc_18000733E
0x1800072e7  lea     rdx, aPartitionoffse; "PartitionOffset"
0x1800072ee  mov     rcx, rbx; this
0x1800072f1  call    ?DeleteValue@CUwfRegKey@@QEAAJPEBG@Z; CUwfRegKey::DeleteValue(ushort const *)
0x1800072f6  mov     r8d, eax
0x1800072f9  add     eax, ebp
0x1800072fb  test    ebp, eax
0x1800072fd  jnz     short loc_180007304
0x1800072ff  cmp     r8d, esi
0x180007302  jnz     short loc_18000733E
0x180007304  lea     rdx, aDisksignature; "DiskSignature"
0x18000730b  mov     rcx, rbx; this
0x18000730e  call    ?DeleteValue@CUwfRegKey@@QEAAJPEBG@Z; CUwfRegKey::DeleteValue(ushort const *)
0x180007313  mov     r8d, eax
0x180007316  add     eax, ebp
0x180007318  test    ebp, eax
0x18000731a  jnz     short loc_180007321
0x18000731c  cmp     r8d, esi
0x18000731f  jnz     short loc_18000733E
0x180007321  lea     rdx, aPartitionguid; "PartitionGuid"
0x180007328  mov     rcx, rbx; this
0x18000732b  call    ?DeleteValue@CUwfRegKey@@QEAAJPEBG@Z; CUwfRegKey::DeleteValue(ushort const *)
0x180007330  mov     r8d, eax
0x180007333  add     eax, ebp
0x180007335  test    ebp, eax
0x180007337  jnz     short loc_180007346
0x180007339  cmp     r8d, esi
0x18000733c  jz      short loc_180007346
0x18000733e  mov     rax, [rdi+18h]
0x180007342  mov     [rax+10h], r8d
0x180007346  add     rsp, 28h
0x18000734a  pop     rdi
0x18000734b  pop     rsi
0x18000734c  pop     rbp
0x18000734d  pop     rbx
0x18000734e  retn
```
