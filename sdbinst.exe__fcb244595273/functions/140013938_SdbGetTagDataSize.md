# SdbGetTagDataSize

- ea: `0x140013938`
- end: `0x140013b7b`
- name: `SdbGetTagDataSize`
- size: `579`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x1400142e0`
- `0x140015538`
- `0x1400176a4`
- `0x140018cb4`
- `0x140018d48`
- `0x140019410`
- `0x14001b2f0`
- `0x14001c730`
- `0x14001d808`
- `0x14001f90c`

## callees

- `0x14001008c`
- `0x140013738`
- `0x140013938`
- `0x140016148`
- `0x1400178a0`

## string_xrefs

- `0x1400139f4`: `Error reading size data [%x]`
- `0x140013a7b`: `Error reading size data [%x]`
- `0x140013afa`: `Error reading size data`
- `0x140013b44`: `Error reading size data`

## pseudocode

```c
__int64 __fastcall SdbGetTagDataSize(__int64 a1, __int64 a2)
{
  int v2; // r15d
  unsigned __int16 TagFromTagID; // ax
  int v5; // r12d
  int v6; // ebx
  unsigned int v7; // ebx
  unsigned int v9; // [rsp+58h] [rbp+10h] BYREF

  v2 = a2;
  TagFromTagID = SdbGetTagFromTagID(a1, a2);
  v5 = TagFromTagID;
  v6 = TagFromTagID & 0xF000;
  if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    switch ( v6 )
    {
      case 4096:
        v7 = 0;
        break;
      case 8192:
        v7 = 1;
        break;
      case 12288:
        v7 = 2;
        break;
      default:
        if ( v6 != 0x4000 )
        {
          if ( v6 == 20480 )
          {
            v7 = 8;
            break;
          }
          if ( v6 != 24576 )
          {
            v9 = 0;
            if ( !(unsigned int)SdbpReadMappedData(a1, (unsigned int)(v2 + 2), &v9, 4) )
              AslLogCallPrintf(1, "SdbGetTagDataSize", 364, "Error reading size data");
            v7 = v9;
            break;
          }
        }
        v7 = 4;
        break;
    }
    if ( v7 + v2 >= v7 && v7 + v2 <= *(_DWORD *)(a1 + 20) )
      return v7;
    AslLogCallPrintf(1, "SdbGetTagDataSize", 375, "Error reading size data");
    return 0x20000000;
  }
  switch ( v6 )
  {
    case 4096:
      v7 = 0;
      break;
    case 8192:
      v7 = 1;
      break;
    case 12288:
      v7 = 2;
      break;
    default:
      if ( v6 != 0x4000 )
      {
        if ( v6 == 20480 )
        {
          v7 = 8;
          break;
        }
        if ( v6 != 24576 )
        {
          if ( ((v6 - 28672) & 0xFFFFCFFF) != 0 || v6 == 40960 )
          {
            AslLogCallPrintf(1, "SdbGetTagDataSize", 318, "Invalid TAG_TYPE encountered TAG: [0x%x]", v5);
            return 0x20000000;
          }
          v9 = 0;
          if ( (unsigned int)SdbpReadMappedData(a1, (unsigned int)(v2 + 2), &v9, 4) )
          {
            v7 = v9;
          }
          else
          {
            v7 = 0x20000000;
            AslLogCallPrintf(1, "SdbGetTagDataSize", 311, "Error reading size data [%x]", -1073741789);
          }
          break;
        }
      }
      v7 = 4;
      break;
  }
  if ( v7 + v2 >= v7 && v7 + v2 <= *(_DWORD *)(a1 + 20) )
    return v7;
  AslLogCallPrintf(1, "SdbGetTagDataSize", 329, "Error reading size data [%x]", -1073741675);
  return 0x20000000;
}

```

## disassembly

```asm
0x140013938  mov     [rsp+arg_0], rbx
0x14001393d  mov     [rsp+arg_10], rdi
0x140013942  push    r12
0x140013944  push    r14
0x140013946  push    r15
0x140013948  sub     rsp, 30h
0x14001394c  mov     r15d, edx
0x14001394f  mov     r14, rcx
0x140013952  call    SdbGetTagFromTagID
0x140013957  movzx   r12d, ax
0x14001395b  mov     ebx, r12d
0x14001395e  and     ebx, 0F000h
0x140013964  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x140013969  mov     edi, 1
0x14001396e  test    eax, eax
0x140013970  jz      loc_140013AA3
0x140013976  cmp     ebx, 1000h
0x14001397c  jz      loc_140013A67
0x140013982  cmp     ebx, 2000h
0x140013988  jz      loc_140013A63
0x14001398e  cmp     ebx, 3000h
0x140013994  jz      loc_140013A5C
0x14001399a  cmp     ebx, 4000h
0x1400139a0  jz      loc_140013A55
0x1400139a6  cmp     ebx, 5000h
0x1400139ac  jz      loc_140013A4E
0x1400139b2  cmp     ebx, 6000h
0x1400139b8  jz      loc_140013A55
0x1400139be  lea     eax, [rbx-7000h]
0x1400139c4  test    eax, 0FFFFCFFFh
0x1400139c9  jnz     short loc_140013A24
0x1400139cb  cmp     ebx, 0A000h
0x1400139d1  jz      short loc_140013A24
0x1400139d3  lea     edx, [r15+2]
0x1400139d7  mov     [rsp+48h+arg_8], 0
0x1400139df  lea     r9d, [rdi+3]
0x1400139e3  mov     rcx, r14
0x1400139e6  lea     r8, [rsp+48h+arg_8]
0x1400139eb  call    SdbpReadMappedData
0x1400139f0  test    eax, eax
0x1400139f2  jnz     short loc_140013A1E
0x1400139f4  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x1400139fb  mov     [rsp+48h+var_28], 0C0000023h
0x140013a03  mov     r8d, 137h
0x140013a09  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x140013a10  mov     ecx, edi
0x140013a12  mov     ebx, 20000000h
0x140013a17  call    AslLogCallPrintf
0x140013a1c  jmp     short loc_140013A69
0x140013a1e  mov     ebx, [rsp+48h+arg_8]
0x140013a22  jmp     short loc_140013A69
0x140013a24  lea     r9, aInvalidTagType_0; "Invalid TAG_TYPE encountered TAG: [0x%x"...
0x140013a2b  mov     [rsp+48h+var_28], r12d
0x140013a30  mov     r8d, 13Eh
0x140013a36  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x140013a3d  mov     ecx, edi
0x140013a3f  call    AslLogCallPrintf
0x140013a44  mov     eax, 20000000h
0x140013a49  jmp     loc_140013B66
0x140013a4e  mov     ebx, 8
0x140013a53  jmp     short loc_140013A69
0x140013a55  mov     ebx, 4
0x140013a5a  jmp     short loc_140013A69
0x140013a5c  mov     ebx, 2
0x140013a61  jmp     short loc_140013A69
0x140013a63  mov     ebx, edi
0x140013a65  jmp     short loc_140013A69
0x140013a67  xor     ebx, ebx
0x140013a69  lea     eax, [rbx+r15]
0x140013a6d  cmp     eax, ebx
0x140013a6f  jb      short loc_140013A7B
0x140013a71  cmp     eax, [r14+14h]
0x140013a75  jbe     loc_140013B64
0x140013a7b  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x140013a82  mov     [rsp+48h+var_28], 0C0000095h
0x140013a8a  mov     r8d, 149h
0x140013a90  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x140013a97  mov     ecx, edi
0x140013a99  call    AslLogCallPrintf
0x140013a9e  jmp     loc_140013B5F
0x140013aa3  cmp     ebx, 1000h
0x140013aa9  jz      loc_140013B34
0x140013aaf  cmp     ebx, 2000h
0x140013ab5  jz      short loc_140013B30
0x140013ab7  cmp     ebx, 3000h
0x140013abd  jz      short loc_140013B29
0x140013abf  cmp     ebx, 4000h
0x140013ac5  jz      short loc_140013B22
0x140013ac7  cmp     ebx, 5000h
0x140013acd  jz      short loc_140013B1B
0x140013acf  cmp     ebx, 6000h
0x140013ad5  jz      short loc_140013B22
0x140013ad7  lea     edx, [r15+2]
0x140013adb  mov     [rsp+48h+arg_8], 0
0x140013ae3  mov     r9d, 4
0x140013ae9  lea     r8, [rsp+48h+arg_8]
0x140013aee  mov     rcx, r14
0x140013af1  call    SdbpReadMappedData
0x140013af6  test    eax, eax
0x140013af8  jnz     short loc_140013B15
0x140013afa  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x140013b01  mov     r8d, 16Ch
0x140013b07  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x140013b0e  mov     ecx, edi
0x140013b10  call    AslLogCallPrintf
0x140013b15  mov     ebx, [rsp+48h+arg_8]
0x140013b19  jmp     short loc_140013B36
0x140013b1b  mov     ebx, 8
0x140013b20  jmp     short loc_140013B36
0x140013b22  mov     ebx, 4
0x140013b27  jmp     short loc_140013B36
0x140013b29  mov     ebx, 2
0x140013b2e  jmp     short loc_140013B36
0x140013b30  mov     ebx, edi
0x140013b32  jmp     short loc_140013B36
0x140013b34  xor     ebx, ebx
0x140013b36  lea     eax, [rbx+r15]
0x140013b3a  cmp     eax, ebx
0x140013b3c  jb      short loc_140013B44
0x140013b3e  cmp     eax, [r14+14h]
0x140013b42  jbe     short loc_140013B64
0x140013b44  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x140013b4b  mov     r8d, 177h
0x140013b51  lea     rdx, aSdbgettagdatas_0; "SdbGetTagDataSize"
0x140013b58  mov     ecx, edi
0x140013b5a  call    AslLogCallPrintf
0x140013b5f  mov     ebx, 20000000h
0x140013b64  mov     eax, ebx
0x140013b66  mov     rbx, [rsp+48h+arg_0]
0x140013b6b  mov     rdi, [rsp+48h+arg_10]
0x140013b70  add     rsp, 30h
0x140013b74  pop     r15
0x140013b76  pop     r14
0x140013b78  pop     r12
0x140013b7a  retn
```
