# SmpComputeDesiredPfSizeForCrashDump

- ea: `0x14000dd1c`
- end: `0x14000de6f`
- name: `SmpComputeDesiredPfSizeForCrashDump`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d92c`

## callees

- `0x14000dd1c`
- `0x140012168`

## pseudocode

```c
unsigned __int64 SmpComputeDesiredPfSizeForCrashDump()
{
  unsigned __int64 v0; // rbx
  unsigned __int64 v1; // rdi
  unsigned __int64 v2; // rbx
  unsigned __int64 v3; // rcx

  v0 = 0;
  SmpTryHardForCrashDump = 0;
  if ( SmpUseDedicatedDumpFile != 1 )
  {
    if ( SmpDumpType != 7 )
    {
      if ( SmpDumpType == 2 )
        goto LABEL_18;
      if ( SmpDumpType != 1 )
        return v0;
      if ( SmpUseFilterPagesDumpFile )
      {
LABEL_18:
        v0 = SmpMemorySize;
      }
      else
      {
        v0 = 0x40000000;
        v3 = ~(unsigned __int64)(unsigned int)(dword_140030B68 - 1)
           & (((SmpHighestPhysicalAddress / (unsigned __int64)(unsigned int)dword_140030B68 + 7) >> 3)
            + (unsigned int)(dword_140030B68 - 1)
            + 8256LL);
        if ( v3 + SmpMemorySize + 0x10000000 > 0x40000000 )
          v0 = v3 + SmpMemorySize + 0x10000000;
      }
      SmpTryHardForCrashDump = 1;
      return v0;
    }
    v1 = 0x800000000LL;
    if ( (unsigned __int64)SmpMemorySize >= 0x100000000LL )
    {
      v2 = 0x800000000LL;
      if ( (unsigned __int64)(SmpMemorySize - 0x100000000LL) >> 3 < 0x800000000LL )
        v2 = (unsigned __int64)(SmpMemorySize - 0x100000000LL) >> 3;
      v0 = ((unsigned __int64)(SmpMemorySize - 0x100000000LL) >> 6) + 715827882 + v2;
    }
    else
    {
      v0 = SmpMemorySize / 6uLL;
    }
    if ( v0 < 0x10000000 )
      v0 = 0x10000000;
    if ( (unsigned __int64)(MEMORY[0x7FFE0014] - SmpQueryPagefileTooSmallForDump()) < 0x1600A3910000LL )
    {
      if ( (unsigned __int64)SmpMemorySize < 0x800000000LL )
        v1 = SmpMemorySize;
      if ( v0 < v1 )
        return v1;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x14000dd1c  mov     [rsp+arg_0], rbx
0x14000dd21  push    rdi
0x14000dd22  sub     rsp, 20h
0x14000dd26  xor     ebx, ebx
0x14000dd28  cmp     cs:SmpUseDedicatedDumpFile, 1
0x14000dd2f  mov     cs:SmpTryHardForCrashDump, bl
0x14000dd35  jz      loc_14000DE61
0x14000dd3b  mov     eax, cs:SmpDumpType
0x14000dd41  cmp     eax, 7
0x14000dd44  jnz     loc_14000DDF4
0x14000dd4a  mov     rcx, cs:SmpMemorySize
0x14000dd51  mov     rax, 100000000h
0x14000dd5b  mov     rdi, 800000000h
0x14000dd65  cmp     rcx, rax
0x14000dd68  jnb     short loc_14000DD80
0x14000dd6a  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000dd74  mul     rcx
0x14000dd77  mov     rbx, rdx
0x14000dd7a  shr     rbx, 2
0x14000dd7e  jmp     short loc_14000DDAC
0x14000dd80  mov     rdx, 0FFFFFFFF00000000h
0x14000dd8a  mov     rbx, rdi
0x14000dd8d  add     rdx, rcx
0x14000dd90  mov     rax, rdx
0x14000dd93  shr     rax, 3
0x14000dd97  cmp     rax, rdi
0x14000dd9a  cmovb   rbx, rax
0x14000dd9e  shr     rdx, 6
0x14000dda2  add     rdx, 2AAAAAAAh
0x14000dda9  add     rbx, rdx
0x14000ddac  mov     eax, 10000000h
0x14000ddb1  cmp     rbx, rax
0x14000ddb4  cmovb   rbx, rax
0x14000ddb8  call    SmpQueryPagefileTooSmallForDump
0x14000ddbd  mov     ecx, 7FFE0014h
0x14000ddc2  mov     rcx, [rcx]
0x14000ddc5  sub     rcx, rax
0x14000ddc8  mov     rax, 1600A3910000h
0x14000ddd2  cmp     rcx, rax
0x14000ddd5  jnb     loc_14000DE61
0x14000dddb  cmp     cs:SmpMemorySize, rdi
0x14000dde2  cmovb   rdi, cs:SmpMemorySize
0x14000ddea  cmp     rbx, rdi
0x14000dded  jnb     short loc_14000DE61
0x14000ddef  mov     rbx, rdi
0x14000ddf2  jmp     short loc_14000DE61
0x14000ddf4  cmp     eax, 2
0x14000ddf7  jz      short loc_14000DE06
0x14000ddf9  cmp     eax, 1
0x14000ddfc  jnz     short loc_14000DE61
0x14000ddfe  cmp     cs:SmpUseFilterPagesDumpFile, bl
0x14000de04  jz      short loc_14000DE0F
0x14000de06  mov     rbx, cs:SmpMemorySize
0x14000de0d  jmp     short loc_14000DE5A
0x14000de0f  mov     ecx, cs:dword_140030B68
0x14000de15  xor     edx, edx
0x14000de17  mov     rax, cs:SmpHighestPhysicalAddress
0x14000de1e  mov     ebx, 40000000h
0x14000de23  div     rcx
0x14000de26  mov     rdx, cs:SmpMemorySize
0x14000de2d  lea     r9d, [rcx-1]
0x14000de31  add     rax, 7
0x14000de35  lea     rcx, [r9+2040h]
0x14000de3c  shr     rax, 3
0x14000de40  add     rdx, 10000000h
0x14000de47  add     rcx, rax
0x14000de4a  not     r9
0x14000de4d  and     rcx, r9
0x14000de50  add     rdx, rcx
0x14000de53  cmp     rdx, rbx
0x14000de56  cmova   rbx, rdx
0x14000de5a  mov     cs:SmpTryHardForCrashDump, 1
0x14000de61  mov     rax, rbx
0x14000de64  mov     rbx, [rsp+28h+arg_0]
0x14000de69  add     rsp, 20h
0x14000de6d  pop     rdi
0x14000de6e  retn
```
