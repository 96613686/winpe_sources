# LazySecurityBases::LazySecurityBases(void)

- ea: `0x1800beea4`
- end: `0x1800bf0b3`
- name: `??0LazySecurityBases@@QEAA@XZ`
- size: `527`
- prototype: `LazySecurityBases *__fastcall(LazySecurityBases *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180078b74`

## callees

- `0x18003ee78`
- `0x180092008`
- `0x1800beea4`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800beeee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bef8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf02c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800beeee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bef8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf02c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800beee4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bef83`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bf022`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800beee4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bef83`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bf022`

## pseudocode

```c
LazySecurityBases *__fastcall LazySecurityBases::LazySecurityBases(LazySecurityBases *this)
{
  PSECURITY_DESCRIPTOR *v2; // rax
  DWORD LastError; // ebx
  PSECURITY_DESCRIPTOR *v4; // rax
  DWORD v5; // ebx
  PSECURITY_DESCRIPTOR *v6; // rax
  DWORD v7; // ebx
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+30h] [rbp-28h]
  DWORD v11; // [rsp+38h] [rbp-20h]
  int v12; // [rsp+3Ch] [rbp-1Ch]
  int v13; // [rsp+40h] [rbp-18h]

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v2 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>((__int64)this);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;0xffff;;;SY)(A;;0xfdff;;;S-1-5-80-880578595-1860270145-482643319-2788375705-1540778122)",
          1u,
          v2,
          0) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v10 = 0;
    v11 = LastError;
    v12 = -1;
    v13 = 36;
    throw (EvtException *)&pExceptionObject;
  }
  v4 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>((__int64)this + 8);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;0xffff;;;SY)(A;;0xffff;;;BA)(A;;0xffff;;;S-1-5-80-880578595-1860270145-482643319-2788375705-1540778122)",
          1u,
          v4,
          0) )
  {
    v5 = GetLastError();
    if ( !v5 )
      v5 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v5);
    }
    pExceptionObject = 0;
    v10 = 0;
    v11 = v5;
    v12 = -1;
    v13 = 45;
    throw (EvtException *)&pExceptionObject;
  }
  v6 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>((__int64)this + 16);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;0xffff;;;SY)(A;;0xff7f;;;BA)(A;;0xffff;;;S-1-5-80-880578595-1860270145-482643319-2788375705-1540778122)",
          1u,
          v6,
          0) )
  {
    v7 = GetLastError();
    if ( !v7 )
      v7 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v7);
    }
    pExceptionObject = 0;
    v10 = 0;
    v11 = v7;
    v12 = -1;
    v13 = 54;
    throw (EvtException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x1800beea4  mov     [rsp-20h+arg_0], rcx
0x1800beea9  push    rbp
0x1800beeaa  push    rbx
0x1800beeab  push    rsi
0x1800beeac  push    rdi
0x1800beead  mov     rbp, rsp
0x1800beeb0  sub     rsp, 58h
0x1800beeb4  mov     rbx, rcx
0x1800beeb7  mov     qword ptr [rcx], 0
0x1800beebe  mov     qword ptr [rcx+8], 0
0x1800beec6  mov     qword ptr [rcx+10h], 0
0x1800beece  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x1800beed3  xor     r9d, r9d; SecurityDescriptorSize
0x1800beed6  mov     r8, rax; SecurityDescriptor
0x1800beed9  lea     edx, [r9+1]; StringSDRevision
0x1800beedd  lea     rcx, aOBagBadA0xffff_0; "O:BAG:BAD:(A;;0xffff;;;SY)(A;;0xfdff;;;"...
0x1800beee4  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800beeea  test    eax, eax
0x1800beeec  jnz     short loc_1800BEF69
0x1800beeee  call    cs:__imp_GetLastError
0x1800beef4  mov     ebx, eax
0x1800beef6  mov     eax, 507h
0x1800beefb  test    ebx, ebx
0x1800beefd  cmovz   ebx, eax
0x1800bef00  lea     rax, WPP_GLOBAL_Control
0x1800bef07  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bef0e  cmp     rcx, rax
0x1800bef11  jz      short loc_1800BEF37
0x1800bef13  test    byte ptr [rcx+1Ch], 4
0x1800bef17  jz      short loc_1800BEF37
0x1800bef19  cmp     byte ptr [rcx+19h], 2
0x1800bef1d  jb      short loc_1800BEF37
0x1800bef1f  mov     edx, 0Ah
0x1800bef24  mov     r9d, ebx
0x1800bef27  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800bef2e  mov     rcx, [rcx+10h]
0x1800bef32  call    WPP_SF_d
0x1800bef37  xorps   xmm0, xmm0
0x1800bef3a  movdqu  [rbp+pExceptionObject], xmm0
0x1800bef3f  mov     [rbp+var_28], 0
0x1800bef47  mov     [rbp+var_20], ebx
0x1800bef4a  mov     [rbp+var_1C], 0FFFFFFFFh
0x1800bef51  mov     [rbp+var_18], 24h ; '$'
0x1800bef58  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bef5f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800bef63  call    _CxxThrowException_0
0x1800bef69  lea     rcx, [rbx+8]
0x1800bef6d  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x1800bef72  xor     r9d, r9d; SecurityDescriptorSize
0x1800bef75  mov     r8, rax; SecurityDescriptor
0x1800bef78  lea     edx, [r9+1]; StringSDRevision
0x1800bef7c  lea     rcx, aOBagBadA0xffff_1; "O:BAG:BAD:(A;;0xffff;;;SY)(A;;0xffff;;;"...
0x1800bef83  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800bef89  test    eax, eax
0x1800bef8b  jnz     short loc_1800BF008
0x1800bef8d  call    cs:__imp_GetLastError
0x1800bef93  mov     ebx, eax
0x1800bef95  mov     eax, 507h
0x1800bef9a  test    ebx, ebx
0x1800bef9c  cmovz   ebx, eax
0x1800bef9f  lea     rax, WPP_GLOBAL_Control
0x1800befa6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800befad  cmp     rcx, rax
0x1800befb0  jz      short loc_1800BEFD6
0x1800befb2  test    byte ptr [rcx+1Ch], 4
0x1800befb6  jz      short loc_1800BEFD6
0x1800befb8  cmp     byte ptr [rcx+19h], 2
0x1800befbc  jb      short loc_1800BEFD6
0x1800befbe  mov     edx, 0Bh
0x1800befc3  mov     r9d, ebx
0x1800befc6  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800befcd  mov     rcx, [rcx+10h]
0x1800befd1  call    WPP_SF_d
0x1800befd6  xorps   xmm0, xmm0
0x1800befd9  movdqu  [rbp+pExceptionObject], xmm0
0x1800befde  mov     [rbp+var_28], 0
0x1800befe6  mov     [rbp+var_20], ebx
0x1800befe9  mov     [rbp+var_1C], 0FFFFFFFFh
0x1800beff0  mov     [rbp+var_18], 2Dh ; '-'
0x1800beff7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800beffe  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800bf002  call    _CxxThrowException_0
0x1800bf008  lea     rcx, [rbx+10h]
0x1800bf00c  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x1800bf011  xor     r9d, r9d; SecurityDescriptorSize
0x1800bf014  mov     r8, rax; SecurityDescriptor
0x1800bf017  lea     edx, [r9+1]; StringSDRevision
0x1800bf01b  lea     rcx, aOBagBadA0xffff; "O:BAG:BAD:(A;;0xffff;;;SY)(A;;0xff7f;;;"...
0x1800bf022  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800bf028  test    eax, eax
0x1800bf02a  jnz     short loc_1800BF0A7
0x1800bf02c  call    cs:__imp_GetLastError
0x1800bf032  mov     ebx, eax
0x1800bf034  mov     eax, 507h
0x1800bf039  test    ebx, ebx
0x1800bf03b  cmovz   ebx, eax
0x1800bf03e  lea     rax, WPP_GLOBAL_Control
0x1800bf045  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf04c  cmp     rcx, rax
0x1800bf04f  jz      short loc_1800BF075
0x1800bf051  test    byte ptr [rcx+1Ch], 4
0x1800bf055  jz      short loc_1800BF075
0x1800bf057  cmp     byte ptr [rcx+19h], 2
0x1800bf05b  jb      short loc_1800BF075
0x1800bf05d  mov     edx, 0Ch
0x1800bf062  mov     r9d, ebx
0x1800bf065  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800bf06c  mov     rcx, [rcx+10h]
0x1800bf070  call    WPP_SF_d
0x1800bf075  xorps   xmm0, xmm0
0x1800bf078  movdqu  [rbp+pExceptionObject], xmm0
0x1800bf07d  mov     [rbp+var_28], 0
0x1800bf085  mov     [rbp+var_20], ebx
0x1800bf088  mov     [rbp+var_1C], 0FFFFFFFFh
0x1800bf08f  mov     [rbp+var_18], 36h ; '6'
0x1800bf096  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bf09d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800bf0a1  call    _CxxThrowException_0
0x1800bf0a7  mov     rax, rbx
0x1800bf0aa  add     rsp, 58h
0x1800bf0ae  pop     rdi
0x1800bf0af  pop     rsi
0x1800bf0b0  pop     rbx
0x1800bf0b1  pop     rbp
0x1800bf0b2  retn
```
