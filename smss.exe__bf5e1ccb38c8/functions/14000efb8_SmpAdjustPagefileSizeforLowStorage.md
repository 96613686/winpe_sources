# SmpAdjustPagefileSizeforLowStorage

- ea: `0x14000efb8`
- end: `0x14000f116`
- name: `SmpAdjustPagefileSizeforLowStorage`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x14000fcf8`

## callees

- `0x14000efb8`

## import_xrefs

- `ntdll!NtQueryLicenseValue` at `0x14000f05e`
- `ntdll!NtQueryLicenseValue` at `0x14000f05e`

## string_xrefs

- `0x14000efcc`: `System-ConfigurePagefileForLowStorage-Enabled`

## pseudocode

```c
__int64 SmpAdjustPagefileSizeforLowStorage()
{
  __int64 result; // rax
  _QWORD *v1; // rbx
  __int64 v2; // rcx
  __int16 v3; // ax
  __int64 v4; // rcx
  __int64 v5; // rdx
  _QWORD v6[2]; // [rsp+30h] [rbp-10h] BYREF
  int v7; // [rsp+50h] [rbp+10h] BYREF
  int v8; // [rsp+58h] [rbp+18h] BYREF
  int v9; // [rsp+60h] [rbp+20h] BYREF

  result = (__int64)L"System-ConfigurePagefileForLowStorage-Enabled";
  v6[1] = L"System-ConfigurePagefileForLowStorage-Enabled";
  v6[0] = 6029402;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( SmpNumberOfPagefileDescriptors == 1 )
  {
    v1 = SmpPagingFileDescriptorList;
    result = (__int64)&SmpPagingFileDescriptorList;
    if ( SmpPagingFileDescriptorList != &SmpPagingFileDescriptorList )
    {
      result = *((_DWORD *)SmpPagingFileDescriptorList + 23) & 6;
      if ( (*((_BYTE *)SmpPagingFileDescriptorList + 92) & 6) == 6 )
      {
        result = SmpOsVolumeDescriptor;
        if ( SmpOsVolumeDescriptor )
        {
          if ( *(_QWORD *)(SmpOsVolumeDescriptor + 40) <= 0x800000000uLL )
          {
            result = NtQueryLicenseValue(v6, &v7, &v9, 4, &v8);
            if ( (int)result >= 0 && v7 == 4 && v8 == 4 && v9 )
            {
              v2 = v1[3];
              v3 = SmpOsVolumeLetter;
              *((_DWORD *)v1 + 23) &= 0xFFFFFFF9;
              SmpAnyDriveDescriptorCreated = 0;
              *(_WORD *)(v2 + 8) = v3;
              if ( *(_QWORD *)(SmpOsVolumeDescriptor + 40) > 0x400000000uLL )
              {
                result = 0x80000000LL;
                v5 = 0x10000000;
                if ( (unsigned __int64)SmpMemorySize > 0xC0000000 )
                  result = 1610612736;
                v4 = 4026531840LL;
              }
              else
              {
                v4 = 0x80000000LL;
                if ( (unsigned __int64)SmpMemorySize > 0xC0000000 )
                  v4 = 0x4000000;
                v5 = 0;
                result = (unsigned int)v4;
              }
              v1[7] = result;
              SmpMaxSwapFileSize = v5;
              v1[8] = v4;
              v1[6] = result;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000efb8  mov     [rsp-8+arg_18], rbx
0x14000efbd  push    rbp
0x14000efbe  mov     rbp, rsp
0x14000efc1  sub     rsp, 40h
0x14000efc5  cmp     cs:SmpNumberOfPagefileDescriptors, 1
0x14000efcc  lea     rax, aSystemConfigur; "System-ConfigurePagefileForLowStorage-E"...
0x14000efd3  mov     [rbp+var_8], rax
0x14000efd7  mov     [rbp+var_10], 5C005Ah
0x14000efdf  mov     [rbp+arg_0], 0
0x14000efe6  mov     [rbp+arg_8], 0
0x14000efed  mov     [rbp+arg_10], 0
0x14000eff4  jnz     loc_14000F10B
0x14000effa  mov     rbx, cs:SmpPagingFileDescriptorList
0x14000f001  lea     rax, SmpPagingFileDescriptorList
0x14000f008  cmp     rbx, rax
0x14000f00b  jz      loc_14000F10B
0x14000f011  mov     eax, [rbx+5Ch]
0x14000f014  and     eax, 6
0x14000f017  cmp     al, 6
0x14000f019  jnz     loc_14000F10B
0x14000f01f  mov     rax, cs:SmpOsVolumeDescriptor
0x14000f026  test    rax, rax
0x14000f029  jz      loc_14000F10B
0x14000f02f  mov     rcx, 800000000h
0x14000f039  cmp     [rax+28h], rcx
0x14000f03d  ja      loc_14000F10B
0x14000f043  lea     rax, [rbp+arg_8]
0x14000f047  mov     r9d, 4
0x14000f04d  lea     r8, [rbp+arg_10]
0x14000f051  mov     [rsp+40h+var_20], rax
0x14000f056  lea     rdx, [rbp+arg_0]
0x14000f05a  lea     rcx, [rbp+var_10]
0x14000f05e  call    cs:__imp_NtQueryLicenseValue
0x14000f064  test    eax, eax
0x14000f066  js      loc_14000F10B
0x14000f06c  cmp     [rbp+arg_0], 4
0x14000f070  jnz     loc_14000F10B
0x14000f076  cmp     [rbp+arg_8], 4
0x14000f07a  jnz     loc_14000F10B
0x14000f080  cmp     [rbp+arg_10], 0
0x14000f084  jz      loc_14000F10B
0x14000f08a  mov     rcx, [rbx+18h]
0x14000f08e  mov     edx, 0C0000000h
0x14000f093  movzx   eax, cs:SmpOsVolumeLetter
0x14000f09a  and     dword ptr [rbx+5Ch], 0FFFFFFF9h
0x14000f09e  mov     cs:SmpAnyDriveDescriptorCreated, 0
0x14000f0a5  mov     [rcx+8], ax
0x14000f0a9  mov     rcx, 400000000h
0x14000f0b3  mov     rax, cs:SmpOsVolumeDescriptor
0x14000f0ba  cmp     [rax+28h], rcx
0x14000f0be  ja      short loc_14000F0DA
0x14000f0c0  cmp     cs:SmpMemorySize, rdx
0x14000f0c7  mov     eax, 4000000h
0x14000f0cc  mov     ecx, 80000000h
0x14000f0d1  cmova   ecx, eax
0x14000f0d4  xor     edx, edx
0x14000f0d6  mov     eax, ecx
0x14000f0d8  jmp     short loc_14000F0F8
0x14000f0da  cmp     cs:SmpMemorySize, rdx
0x14000f0e1  mov     ecx, 60000000h
0x14000f0e6  mov     eax, 80000000h
0x14000f0eb  mov     edx, 10000000h
0x14000f0f0  cmova   eax, ecx
0x14000f0f3  mov     ecx, 0F0000000h
0x14000f0f8  mov     [rbx+38h], rax
0x14000f0fc  mov     cs:SmpMaxSwapFileSize, rdx
0x14000f103  mov     [rbx+40h], rcx
0x14000f107  mov     [rbx+30h], rax
0x14000f10b  mov     rbx, [rsp+40h+arg_18]
0x14000f110  add     rsp, 40h
0x14000f114  pop     rbp
0x14000f115  retn
```
