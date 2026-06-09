# SxCheckSupportedDriveType(ushort const *)

- ea: `0x18002b9dc`
- end: `0x18002baf6`
- name: `?SxCheckSupportedDriveType@@YAJPEBG@Z`
- size: `282`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c910`

## callees

- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002b9dc`
- `0x18002d778`

## import_xrefs

- `KERNEL32!GetDriveTypeW` at `0x18002ba93`
- `KERNEL32!GetDriveTypeW` at `0x18002ba93`
- `ntdll!RtlSetThreadErrorMode` at `0x18002ba71`
- `ntdll!RtlSetThreadErrorMode` at `0x18002baa0`
- `ntdll!RtlSetThreadErrorMode` at `0x18002ba71`
- `ntdll!RtlSetThreadErrorMode` at `0x18002baa0`

## pseudocode

```c
__int64 __fastcall SxCheckSupportedDriveType(LPCWSTR lpRootPathName)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int16 v4; // ax
  int v5; // ebx
  unsigned int v6; // eax
  UINT DriveTypeW; // edi
  unsigned int v8; // eax
  int v10; // [rsp+20h] [rbp-40h] BYREF
  __int16 v11; // [rsp+24h] [rbp-3Ch]
  __int16 v12; // [rsp+26h] [rbp-3Ah]
  ULONG OldMode; // [rsp+70h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "SxCheckSupportedDriveType", 978, 1);
  OldMode = 0;
  v4 = 983;
  if ( !lpRootPathName )
  {
    v5 = -2147024809;
    v10 = -2147024809;
LABEL_6:
    v12 = v4;
    goto LABEL_11;
  }
  v10 = 0;
  v11 = 983;
  v6 = RtlSetThreadErrorMode(0x10u, &OldMode);
  v5 = HRESULTFromNTSTATUS(v6);
  v10 = v5;
  v4 = 985;
  if ( v5 < 0 )
    goto LABEL_6;
  v11 = 985;
  DriveTypeW = GetDriveTypeW(lpRootPathName);
  v8 = RtlSetThreadErrorMode(OldMode, 0);
  v5 = HRESULTFromNTSTATUS(v8);
  v10 = v5;
  v4 = 987;
  if ( v5 < 0 )
    goto LABEL_6;
  v11 = 987;
  if ( DriveTypeW != 3 )
  {
    v10 = 1;
    v11 = 991;
    v5 = 1;
  }
LABEL_11:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10, v2, v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002b9dc  mov     [rsp-8+arg_8], rbx
0x18002b9e1  mov     [rsp-8+arg_10], rdi
0x18002b9e6  push    rbp
0x18002b9e7  mov     rbp, rsp
0x18002b9ea  sub     rsp, 60h
0x18002b9ee  mov     rdi, rcx
0x18002b9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9f8  lea     rax, WPP_GLOBAL_Control
0x18002b9ff  cmp     rcx, rax
0x18002ba02  jz      short loc_18002BA22
0x18002ba04  test    dword ptr [rcx+1Ch], 20000000h
0x18002ba0b  jz      short loc_18002BA22
0x18002ba0d  mov     rcx, [rcx+10h]
0x18002ba11  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002ba18  mov     edx, 1Ch
0x18002ba1d  call    WPP_SF_
0x18002ba22  mov     r9d, 1; unsigned __int16
0x18002ba28  lea     rdx, aSxchecksupport_0; "SxCheckSupportedDriveType"
0x18002ba2f  mov     r8d, 3D2h; unsigned __int16
0x18002ba35  lea     rcx, [rbp+var_40]; this
0x18002ba39  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002ba3e  mov     [rbp+OldMode], 0
0x18002ba45  mov     eax, 3D7h
0x18002ba4a  test    rdi, rdi
0x18002ba4d  jnz     short loc_18002BA5D
0x18002ba4f  mov     ebx, 80070057h
0x18002ba54  mov     [rbp+var_40], ebx
0x18002ba57  mov     [rbp+var_3A], ax
0x18002ba5b  jmp     short loc_18002BAD9
0x18002ba5d  lea     rdx, [rbp+OldMode]; OldMode
0x18002ba61  mov     [rbp+var_40], 0
0x18002ba68  mov     ecx, 10h; NewMode
0x18002ba6d  mov     [rbp+var_3C], ax
0x18002ba71  call    cs:__imp_RtlSetThreadErrorMode
0x18002ba77  mov     ecx, eax
0x18002ba79  call    HRESULTFromNTSTATUS
0x18002ba7e  mov     ebx, eax
0x18002ba80  mov     [rbp+var_40], eax
0x18002ba83  test    eax, eax
0x18002ba85  mov     eax, 3D9h
0x18002ba8a  js      short loc_18002BA57
0x18002ba8c  mov     rcx, rdi; lpRootPathName
0x18002ba8f  mov     [rbp+var_3C], ax
0x18002ba93  call    cs:__imp_GetDriveTypeW
0x18002ba99  mov     ecx, [rbp+OldMode]; NewMode
0x18002ba9c  xor     edx, edx; OldMode
0x18002ba9e  mov     edi, eax
0x18002baa0  call    cs:__imp_RtlSetThreadErrorMode
0x18002baa6  mov     ecx, eax
0x18002baa8  call    HRESULTFromNTSTATUS
0x18002baad  mov     ebx, eax
0x18002baaf  mov     [rbp+var_40], eax
0x18002bab2  test    eax, eax
0x18002bab4  mov     eax, 3DBh
0x18002bab9  js      short loc_18002BA57
0x18002babb  mov     [rbp+var_3C], ax
0x18002babf  cmp     edi, 3
0x18002bac2  jz      short loc_18002BAD9
0x18002bac4  mov     eax, 3DFh
0x18002bac9  mov     [rbp+var_40], 1
0x18002bad0  mov     [rbp+var_3C], ax
0x18002bad4  mov     ebx, 1
0x18002bad9  lea     rcx, [rbp+var_40]; this
0x18002badd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002bae2  lea     r11, [rsp+60h+var_s0]
0x18002bae7  mov     eax, ebx
0x18002bae9  mov     rbx, [r11+18h]
0x18002baed  mov     rdi, [r11+20h]
0x18002baf1  mov     rsp, r11
0x18002baf4  pop     rbp
0x18002baf5  retn
```
