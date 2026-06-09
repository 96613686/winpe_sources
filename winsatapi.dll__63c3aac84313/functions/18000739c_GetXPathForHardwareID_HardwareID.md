# GetXPathForHardwareID(HardwareID)

- ea: `0x18000739c`
- end: `0x18000745a`
- name: `?GetXPathForHardwareID@@YAPEBGW4HardwareID@@@Z`
- size: `190`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006970`
- `0x18002b2e4`
- `0x18002b3e8`
- `0x18002b49c`
- `0x18002b558`
- `0x18002b5f8`

## callees

- `0x18000739c`

## string_xrefs

- `0x1800073d1`: `SystemConfig/Memory/DIMM`
- `0x18000742e`: `SystemConfig/Processor/Instance/X64Running`
- `0x1800073f1`: `SystemConfig/System/MotherBoard`
- `0x1800073e9`: `SystemConfig/Processor/Instance/Signature/Manufacturer`
- `0x1800073e1`: `SystemConfig/Processor/Instance/Signature/CompactSignature`
- `0x1800073d9`: `SystemConfig/Memory/TotalPhysical/Bytes`
- `0x1800073c9`: `SystemConfig/Disk/SystemDisk/Size`
- `0x1800073f9`: `SystemConfig/Disk/SystemDisk/DiskNum`
- `0x180007452`: `SystemConfig/Graphics/PNPID`
- `0x18000744a`: `SystemConfig/Graphics/DriverVersion`
- `0x180007442`: `SystemConfig/Graphics/LDDM`

## pseudocode

```c
const wchar_t *__fastcall GetXPathForHardwareID(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  const wchar_t *result; // rax

  if ( a1 > 64 )
  {
    switch ( a1 )
    {
      case 128:
        return L"SystemConfig/Graphics/PNPID";
      case 256:
        return L"SystemConfig/Graphics/DriverVersion";
      case 512:
        return L"SystemConfig/Graphics/LDDM";
      case 1024:
        return L"ProgramInfo/WinEIVersion";
      default:
        result = L"SystemConfig/Processor/Instance/X64Running";
        if ( a1 != 2048 )
          return &String2;
        break;
    }
  }
  else if ( a1 == 64 )
  {
    return L"SystemConfig/Disk/SystemDisk/DiskNum";
  }
  else
  {
    v1 = a1 - 1;
    if ( v1 )
    {
      v2 = v1 - 1;
      if ( v2 )
      {
        v3 = v2 - 2;
        if ( v3 )
        {
          v4 = v3 - 4;
          if ( v4 )
          {
            v5 = v4 - 8;
            if ( v5 )
            {
              if ( v5 == 16 )
                return L"SystemConfig/Disk/SystemDisk/Size";
              else
                return &String2;
            }
            else
            {
              return L"SystemConfig/Memory/DIMM";
            }
          }
          else
          {
            return L"SystemConfig/Memory/TotalPhysical/Bytes";
          }
        }
        else
        {
          return L"SystemConfig/Processor/Instance/Signature/CompactSignature";
        }
      }
      else
      {
        return L"SystemConfig/Processor/Instance/Signature/Manufacturer";
      }
    }
    else
    {
      return L"SystemConfig/System/MotherBoard";
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000739c  cmp     ecx, 40h ; '@'
0x18000739f  jg      short loc_180007401
0x1800073a1  jz      short loc_1800073F9
0x1800073a3  sub     ecx, 1
0x1800073a6  jz      short loc_1800073F1
0x1800073a8  sub     ecx, 1
0x1800073ab  jz      short loc_1800073E9
0x1800073ad  sub     ecx, 2
0x1800073b0  jz      short loc_1800073E1
0x1800073b2  sub     ecx, 4
0x1800073b5  jz      short loc_1800073D9
0x1800073b7  sub     ecx, 8
0x1800073ba  jz      short loc_1800073D1
0x1800073bc  cmp     ecx, 10h
0x1800073bf  jz      short loc_1800073C9
0x1800073c1  lea     rax, String2
0x1800073c8  retn
0x1800073c9  lea     rax, aSystemconfigDi; "SystemConfig/Disk/SystemDisk/Size"
0x1800073d0  retn
0x1800073d1  lea     rax, aSystemconfigMe_0; "SystemConfig/Memory/DIMM"
0x1800073d8  retn
0x1800073d9  lea     rax, aSystemconfigMe; "SystemConfig/Memory/TotalPhysical/Bytes"
0x1800073e0  retn
0x1800073e1  lea     rax, aSystemconfigPr; "SystemConfig/Processor/Instance/Signatu"...
0x1800073e8  retn
0x1800073e9  lea     rax, aSystemconfigPr_1; "SystemConfig/Processor/Instance/Signatu"...
0x1800073f0  retn
0x1800073f1  lea     rax, aSystemconfigSy; "SystemConfig/System/MotherBoard"
0x1800073f8  retn
0x1800073f9  lea     rax, aSystemconfigDi_0; "SystemConfig/Disk/SystemDisk/DiskNum"
0x180007400  retn
0x180007401  cmp     ecx, 80h
0x180007407  jz      short loc_180007452
0x180007409  cmp     ecx, 100h
0x18000740f  jz      short loc_18000744A
0x180007411  cmp     ecx, 200h
0x180007417  jz      short loc_180007442
0x180007419  cmp     ecx, 400h
0x18000741f  jz      short loc_18000743A
0x180007421  cmp     ecx, 800h
0x180007427  lea     rdx, String2
0x18000742e  lea     rax, aSystemconfigPr_0; "SystemConfig/Processor/Instance/X64Runn"...
0x180007435  cmovnz  rax, rdx
0x180007439  retn
0x18000743a  lea     rax, aPrograminfoWin; "ProgramInfo/WinEIVersion"
0x180007441  retn
0x180007442  lea     rax, aSystemconfigGr; "SystemConfig/Graphics/LDDM"
0x180007449  retn
0x18000744a  lea     rax, aSystemconfigGr_0; "SystemConfig/Graphics/DriverVersion"
0x180007451  retn
0x180007452  lea     rax, aSystemconfigGr_1; "SystemConfig/Graphics/PNPID"
0x180007459  retn
```
