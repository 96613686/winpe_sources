# LazySecurityBases::LazySecurityBases(void)

- ea: `0x14002d688`
- end: `0x14002d878`
- name: `??0LazySecurityBases@@QEAA@XZ`
- size: `496`
- prototype: `LazySecurityBases *__fastcall(LazySecurityBases *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002e75c`

## callees

- `0x140022cec`
- `0x14002bc70`
- `0x14002d688`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d6d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d7f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d6d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d7f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14002d6cc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14002d75d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14002d7ee`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14002d6cc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14002d75d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14002d7ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LazySecurityBases *__fastcall LazySecurityBases::LazySecurityBases(LazySecurityBases *this)
{
  PSECURITY_DESCRIPTOR *v2; // rax
  DWORD LastError; // ebx
  const char *v4; // r8
  PSECURITY_DESCRIPTOR *v5; // rax
  DWORD v6; // ebx
  const char *v7; // r8
  PSECURITY_DESCRIPTOR *v8; // rax
  DWORD v9; // ebx
  const char *v10; // r8
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v2 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(this);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, LastError);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, v4, 36);
    throw (EvtException *)pExceptionObject;
  }
  v5 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>((char *)this + 8);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;0xffff;;;SY)(A;;0xffff;;;BA)(A;;0xffff;;;S-1-5-80-880578595-1860270145-482643319-2788375705-1540778122)",
          1u,
          v5,
          0) )
  {
    v6 = GetLastError();
    if ( !v6 )
      v6 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v6);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v6, v7, 45);
    throw (EvtException *)pExceptionObject;
  }
  v8 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>((char *)this + 16);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;0xffff;;;SY)(A;;0xff7f;;;BA)(A;;0xffff;;;S-1-5-80-880578595-1860270145-482643319-2788375705-1540778122)",
          1u,
          v8,
          0) )
  {
    v9 = GetLastError();
    if ( !v9 )
      v9 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v9);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v9, v10, 54);
    throw (EvtException *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x14002d688  mov     [rsp+arg_8], rbx
0x14002d68d  mov     [rsp+arg_10], rsi
0x14002d692  mov     [rsp+arg_0], rcx
0x14002d697  push    rdi
0x14002d698  sub     rsp, 50h
0x14002d69c  mov     rbx, rcx
0x14002d69f  mov     qword ptr [rcx], 0
0x14002d6a6  mov     qword ptr [rcx+8], 0
0x14002d6ae  mov     qword ptr [rcx+10h], 0
0x14002d6b6  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x14002d6bb  xor     r9d, r9d; SecurityDescriptorSize
0x14002d6be  mov     r8, rax; SecurityDescriptor
0x14002d6c1  lea     edx, [r9+1]; StringSDRevision
0x14002d6c5  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0xffff;;;SY)(A;;0xfdff;;;"...
0x14002d6cc  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14002d6d2  test    eax, eax
0x14002d6d4  jnz     short loc_14002D743
0x14002d6d6  call    cs:__imp_GetLastError
0x14002d6dc  mov     ebx, eax
0x14002d6de  mov     eax, 507h
0x14002d6e3  test    ebx, ebx
0x14002d6e5  cmovz   ebx, eax
0x14002d6e8  lea     rax, WPP_GLOBAL_Control
0x14002d6ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d6f6  cmp     rcx, rax
0x14002d6f9  jz      short loc_14002D71F
0x14002d6fb  test    byte ptr [rcx+1Ch], 4
0x14002d6ff  jz      short loc_14002D71F
0x14002d701  cmp     byte ptr [rcx+19h], 2
0x14002d705  jb      short loc_14002D71F
0x14002d707  mov     edx, 0Ah
0x14002d70c  mov     r9d, ebx
0x14002d70f  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14002d716  mov     rcx, [rcx+10h]
0x14002d71a  call    WPP_SF_d
0x14002d71f  mov     r9d, 24h ; '$'; int
0x14002d725  mov     edx, ebx; unsigned int
0x14002d727  lea     rcx, [rsp+58h+pExceptionObject]; this
0x14002d72c  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002d731  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002d738  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x14002d73d  call    _CxxThrowException_0
0x14002d743  lea     rcx, [rbx+8]
0x14002d747  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x14002d74c  xor     r9d, r9d; SecurityDescriptorSize
0x14002d74f  mov     r8, rax; SecurityDescriptor
0x14002d752  lea     edx, [r9+1]; StringSDRevision
0x14002d756  lea     rcx, aOBagBadA0xffff_1; "O:BAG:BAD:(A;;0xffff;;;SY)(A;;0xffff;;;"...
0x14002d75d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14002d763  test    eax, eax
0x14002d765  jnz     short loc_14002D7D4
0x14002d767  call    cs:__imp_GetLastError
0x14002d76d  mov     ebx, eax
0x14002d76f  mov     eax, 507h
0x14002d774  test    ebx, ebx
0x14002d776  cmovz   ebx, eax
0x14002d779  lea     rax, WPP_GLOBAL_Control
0x14002d780  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d787  cmp     rcx, rax
0x14002d78a  jz      short loc_14002D7B0
0x14002d78c  test    byte ptr [rcx+1Ch], 4
0x14002d790  jz      short loc_14002D7B0
0x14002d792  cmp     byte ptr [rcx+19h], 2
0x14002d796  jb      short loc_14002D7B0
0x14002d798  mov     edx, 0Bh
0x14002d79d  mov     r9d, ebx
0x14002d7a0  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14002d7a7  mov     rcx, [rcx+10h]
0x14002d7ab  call    WPP_SF_d
0x14002d7b0  mov     r9d, 2Dh ; '-'; int
0x14002d7b6  mov     edx, ebx; unsigned int
0x14002d7b8  lea     rcx, [rsp+58h+pExceptionObject]; this
0x14002d7bd  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002d7c2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002d7c9  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x14002d7ce  call    _CxxThrowException_0
0x14002d7d4  lea     rcx, [rbx+10h]
0x14002d7d8  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x14002d7dd  xor     r9d, r9d; SecurityDescriptorSize
0x14002d7e0  mov     r8, rax; SecurityDescriptor
0x14002d7e3  lea     edx, [r9+1]; StringSDRevision
0x14002d7e7  lea     rcx, aOBagBadA0xffff; "O:BAG:BAD:(A;;0xffff;;;SY)(A;;0xff7f;;;"...
0x14002d7ee  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14002d7f4  test    eax, eax
0x14002d7f6  jnz     short loc_14002D865
0x14002d7f8  call    cs:__imp_GetLastError
0x14002d7fe  mov     ebx, eax
0x14002d800  mov     eax, 507h
0x14002d805  test    ebx, ebx
0x14002d807  cmovz   ebx, eax
0x14002d80a  lea     rax, WPP_GLOBAL_Control
0x14002d811  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d818  cmp     rcx, rax
0x14002d81b  jz      short loc_14002D841
0x14002d81d  test    byte ptr [rcx+1Ch], 4
0x14002d821  jz      short loc_14002D841
0x14002d823  cmp     byte ptr [rcx+19h], 2
0x14002d827  jb      short loc_14002D841
0x14002d829  mov     edx, 0Ch
0x14002d82e  mov     r9d, ebx
0x14002d831  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14002d838  mov     rcx, [rcx+10h]
0x14002d83c  call    WPP_SF_d
0x14002d841  mov     r9d, 36h ; '6'; int
0x14002d847  mov     edx, ebx; unsigned int
0x14002d849  lea     rcx, [rsp+58h+pExceptionObject]; this
0x14002d84e  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002d853  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002d85a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x14002d85f  call    _CxxThrowException_0
0x14002d865  mov     rax, rbx
0x14002d868  mov     rbx, [rsp+58h+arg_8]
0x14002d86d  mov     rsi, [rsp+58h+arg_10]
0x14002d872  add     rsp, 50h
0x14002d876  pop     rdi
0x14002d877  retn
```
