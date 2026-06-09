# CUwfStaticVolumeConfiguration::DeleteLooseBindingConfiguration(void)

- ea: `0x1800071d0`
- end: `0x180007242`
- name: `?DeleteLooseBindingConfiguration@CUwfStaticVolumeConfiguration@@AEAAXXZ`
- size: `114`
- prototype: `void __fastcall(CUwfStaticVolumeConfiguration *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007120`
- `0x18000bc90`

## callees

- `0x1800071d0`
- `0x18000dd80`

## pseudocode

```c
void __fastcall CUwfStaticVolumeConfiguration::DeleteLooseBindingConfiguration(CUwfStaticVolumeConfiguration *this)
{
  int v2; // eax
  int v3; // r8d

  v2 = CUwfRegKey::DeleteValue((CUwfStaticVolumeConfiguration *)((char *)this + 16), L"DiskNumber");
  v3 = v2;
  if ( (int)(v2 + 0x80000000) >= 0 && v2 != -2147024894
    || (v3 = CUwfRegKey::DeleteValue((CUwfStaticVolumeConfiguration *)((char *)this + 16), L"PartitionNumber"),
        ((v3 + 0x80000000) & 0x80000000) == 0)
    && v3 != -2147024894 )
  {
    *(_DWORD *)(*((_QWORD *)this + 3) + 16LL) = v3;
  }
}

```

## disassembly

```asm
0x1800071d0  mov     [rsp+arg_0], rbx
0x1800071d5  mov     [rsp+arg_8], rbp
0x1800071da  push    rdi
0x1800071db  sub     rsp, 20h
0x1800071df  mov     rbx, rcx
0x1800071e2  lea     rdx, aDisknumber; "DiskNumber"
0x1800071e9  add     rcx, 10h; this
0x1800071ed  call    ?DeleteValue@CUwfRegKey@@QEAAJPEBG@Z; CUwfRegKey::DeleteValue(ushort const *)
0x1800071f2  mov     ebp, 80000000h
0x1800071f7  mov     r8d, eax
0x1800071fa  lea     edx, [rax+rbp]
0x1800071fd  test    ebp, edx
0x1800071ff  jnz     short loc_180007208
0x180007201  cmp     eax, 80070002h
0x180007206  jnz     short loc_18000722A
0x180007208  lea     rdx, aPartitionnumbe; "PartitionNumber"
0x18000720f  lea     rcx, [rbx+10h]; this
0x180007213  call    ?DeleteValue@CUwfRegKey@@QEAAJPEBG@Z; CUwfRegKey::DeleteValue(ushort const *)
0x180007218  mov     r8d, eax
0x18000721b  add     eax, ebp
0x18000721d  test    ebp, eax
0x18000721f  jnz     short loc_180007232
0x180007221  cmp     r8d, 80070002h
0x180007228  jz      short loc_180007232
0x18000722a  mov     rax, [rbx+18h]
0x18000722e  mov     [rax+10h], r8d
0x180007232  mov     rbx, [rsp+28h+arg_0]
0x180007237  mov     rbp, [rsp+28h+arg_8]
0x18000723c  add     rsp, 20h
0x180007240  pop     rdi
0x180007241  retn
```
