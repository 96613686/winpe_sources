# GetCurrentRoleInstance(ushort * *)

- ea: `0x18008cc44`
- end: `0x18008ce0a`
- name: `?GetCurrentRoleInstance@@YAJPEAPEAG@Z`
- size: `454`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008d58c`

## callees

- `0x18000224c`
- `0x1800058d4`
- `0x18000ec94`
- `0x180010ba4`
- `0x18001a008`
- `0x180027914`
- `0x18008cc44`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18008cde9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18008cde9`
- `OLEAUT32!__imp_SysFreeString` at `0x18008cdf2`
- `OLEAUT32!__imp_SysFreeString` at `0x18008cdf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cd34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cd9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cd34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cd9c`
- `KERNEL32!GetComputerNameExW` at `0x18008ccdd`
- `KERNEL32!GetComputerNameExW` at `0x18008cd26`
- `KERNEL32!GetComputerNameExW` at `0x18008ccdd`
- `KERNEL32!GetComputerNameExW` at `0x18008cd26`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCurrentRoleInstance(unsigned __int16 **a1)
{
  WCHAR *v2; // rdi
  int ActivityIdPrefix; // eax
  signed int LastError; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  DWORD nSize; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int16 *v9; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  nSize = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v9, &LocaleName);
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_67a1c77dc5563be25fa382ab8ed47b03_Traceguids,
        ActivityIdPrefix,
        (__int64)"ppbstrCurrentRoleInstance");
    }
    LastError = -2147467261;
    goto LABEL_25;
  }
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize) )
    goto LABEL_24;
  if ( GetLastError() != 234 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_15;
    }
    v5 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v6 = 16;
    goto LABEL_14;
  }
  v2 = (WCHAR *)operator new[](saturated_mul(nSize, 2u));
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v2, &nSize) )
  {
LABEL_24:
    ATL::CComBSTR::operator=(&v9, v2);
    LastError = 0;
    goto LABEL_25;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_15;
  }
  v5 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
  v6 = 15;
LABEL_14:
  WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_67a1c77dc5563be25fa382ab8ed47b03_Traceguids, v5, LastError);
LABEL_15:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    LastError = -2147467259;
LABEL_25:
  *a1 = v9;
  operator delete[](v2);
  SysFreeString(0);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18008cc44  mov     rax, rsp
0x18008cc47  push    rdi
0x18008cc48  sub     rsp, 40h
0x18008cc4c  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18008cc54  mov     [rax+18h], rbx
0x18008cc58  mov     [rax+20h], rsi
0x18008cc5c  mov     rsi, rcx
0x18008cc5f  xor     edi, edi
0x18008cc61  mov     [rax+8], edi
0x18008cc64  lea     rdx, LocaleName; unsigned __int16 *
0x18008cc6b  lea     rcx, [rax+10h]; this
0x18008cc6f  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18008cc74  nop
0x18008cc75  test    rsi, rsi
0x18008cc78  jnz     short loc_18008CCD1
0x18008cc7a  lea     rax, WPP_GLOBAL_Control
0x18008cc81  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cc88  cmp     rcx, rax
0x18008cc8b  jz      short loc_18008CCC7
0x18008cc8d  test    byte ptr [rcx+1Ch], 8
0x18008cc91  jz      short loc_18008CCC7
0x18008cc93  cmp     byte ptr [rcx+19h], 2
0x18008cc97  jb      short loc_18008CCC7
0x18008cc99  call    RdpX_GetActivityIdPrefix
0x18008cc9e  lea     edx, [rdi+0Eh]
0x18008cca1  lea     rcx, aPpbstrcurrentr; "ppbstrCurrentRoleInstance"
0x18008cca8  mov     [rsp+48h+var_28], rcx
0x18008ccad  mov     r9d, eax
0x18008ccb0  lea     r8, WPP_67a1c77dc5563be25fa382ab8ed47b03_Traceguids
0x18008ccb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ccbe  mov     rcx, [rcx+10h]
0x18008ccc2  call    WPP_SF_Ds
0x18008ccc7  mov     ebx, 80004003h
0x18008cccc  jmp     loc_18008CDDE
0x18008ccd1  lea     r8, [rsp+48h+nSize]; nSize
0x18008ccd6  xor     edx, edx; lpBuffer
0x18008ccd8  lea     ebx, [rdx+3]
0x18008ccdb  mov     ecx, ebx; NameType
0x18008ccdd  call    cs:__imp_GetComputerNameExW
0x18008cce3  test    eax, eax
0x18008cce5  jnz     loc_18008CDCF
0x18008cceb  call    cs:__imp_GetLastError
0x18008ccf1  cmp     eax, 0EAh
0x18008ccf6  jnz     loc_18008CD9C
0x18008ccfc  mov     edx, [rsp+48h+nSize]
0x18008cd00  lea     eax, [rbx-1]
0x18008cd03  mul     rdx
0x18008cd06  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18008cd0d  cmovb   rax, rdx
0x18008cd11  mov     rcx, rax; unsigned __int64
0x18008cd14  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008cd19  mov     rdi, rax
0x18008cd1c  lea     r8, [rsp+48h+nSize]; nSize
0x18008cd21  mov     rdx, rax; lpBuffer
0x18008cd24  mov     ecx, ebx; NameType
0x18008cd26  call    cs:__imp_GetComputerNameExW
0x18008cd2c  test    eax, eax
0x18008cd2e  jnz     loc_18008CDCF
0x18008cd34  call    cs:__imp_GetLastError
0x18008cd3a  mov     ebx, eax
0x18008cd3c  lea     rax, WPP_GLOBAL_Control
0x18008cd43  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cd4a  cmp     rcx, rax
0x18008cd4d  jz      short loc_18008CD83
0x18008cd4f  test    byte ptr [rcx+1Ch], 8
0x18008cd53  jz      short loc_18008CD83
0x18008cd55  cmp     byte ptr [rcx+19h], 2
0x18008cd59  jb      short loc_18008CD83
0x18008cd5b  call    RdpX_GetActivityIdPrefix
0x18008cd60  mov     edx, 0Fh
0x18008cd65  mov     dword ptr [rsp+48h+var_28], ebx
0x18008cd69  mov     r9d, eax
0x18008cd6c  lea     r8, WPP_67a1c77dc5563be25fa382ab8ed47b03_Traceguids
0x18008cd73  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cd7a  mov     rcx, [rcx+10h]
0x18008cd7e  call    WPP_SF_Dd
0x18008cd83  test    ebx, ebx
0x18008cd85  jle     short loc_18008CD90
0x18008cd87  movzx   ebx, bx
0x18008cd8a  or      ebx, 80070000h
0x18008cd90  mov     eax, 80004005h
0x18008cd95  test    ebx, ebx
0x18008cd97  cmovns  ebx, eax
0x18008cd9a  jmp     short loc_18008CDDE
0x18008cd9c  call    cs:__imp_GetLastError
0x18008cda2  mov     ebx, eax
0x18008cda4  lea     rax, WPP_GLOBAL_Control
0x18008cdab  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cdb2  cmp     rcx, rax
0x18008cdb5  jz      short loc_18008CD83
0x18008cdb7  test    byte ptr [rcx+1Ch], 8
0x18008cdbb  jz      short loc_18008CD83
0x18008cdbd  cmp     byte ptr [rcx+19h], 2
0x18008cdc1  jb      short loc_18008CD83
0x18008cdc3  call    RdpX_GetActivityIdPrefix
0x18008cdc8  mov     edx, 10h
0x18008cdcd  jmp     short loc_18008CD65
0x18008cdcf  mov     rdx, rdi
0x18008cdd2  lea     rcx, [rsp+48h+arg_8]
0x18008cdd7  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008cddc  xor     ebx, ebx
0x18008cdde  mov     rcx, [rsp+48h+arg_8]
0x18008cde3  mov     [rsi], rcx
0x18008cde6  mov     rcx, rdi
0x18008cde9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18008cdef  nop
0x18008cdf0  xor     ecx, ecx; bstrString
0x18008cdf2  call    cs:__imp_SysFreeString
0x18008cdf8  mov     eax, ebx
0x18008cdfa  mov     rbx, [rsp+48h+arg_10]
0x18008cdff  mov     rsi, [rsp+48h+arg_18]
0x18008ce04  add     rsp, 40h
0x18008ce08  pop     rdi
0x18008ce09  retn
```
