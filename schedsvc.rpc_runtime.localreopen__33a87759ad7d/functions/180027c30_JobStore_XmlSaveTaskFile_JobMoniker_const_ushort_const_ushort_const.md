# JobStore::XmlSaveTaskFile(JobMoniker const &,ushort const *,ushort const *)

- ea: `0x180027c30`
- end: `0x180027ed9`
- name: `?XmlSaveTaskFile@JobStore@@QEAAJAEBVJobMoniker@@PEBG1@Z`
- size: `681`
- prototype: `__int64 __fastcall(JobStore *__hidden this, const struct JobMoniker *, const unsigned __int16 *, LPCWSTR StringSecurityDescriptor)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800213f8`
- `0x180045df0`
- `0x18004d868`
- `0x18006c840`

## callees

- `0x18001a260`
- `0x18002132c`
- `0x180027c30`
- `0x180027ee0`
- `0x180028300`
- `0x180056794`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180027c96`
- `OLEAUT32!__imp_SysStringLen` at `0x180027c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027dba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027dba`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027c60`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027d10`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027c60`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027d10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027da2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027da2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180027d5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180027d5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JobStore::XmlSaveTaskFile(
        JobStore *this,
        const struct JobMoniker *a2,
        const unsigned __int16 *a3,
        LPCWSTR StringSecurityDescriptor)
{
  BSTR *v8; // rax
  UINT v9; // eax
  __int64 *v10; // rax
  __int64 v11; // rcx
  unsigned __int16 *v12; // rdx
  int XmlFileSystemPath; // edi
  unsigned __int64 v14; // rdi
  ULONG v15; // ecx
  void *v16; // rsi
  PSECURITY_DESCRIPTOR v17; // rax
  signed int LastError; // eax
  int v19; // ebx
  unsigned int Path; // eax
  unsigned int v22; // [rsp+20h] [rbp-48h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-20h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+70h] [rbp+8h] BYREF

  while ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 23, 0, 0) )
    Sleep(0x64u);
  if ( !*(_DWORD *)(*((_QWORD *)this + 10) + 184LL) )
    return 0;
  lpMem = 0;
  v8 = (BSTR *)*((_QWORD *)a2 + 2);
  if ( v8 && (!*v8 ? (v9 = 0) : (v9 = SysStringLen(*v8)), v9) )
  {
    v10 = (__int64 *)*((_QWORD *)a2 + 2);
    if ( v10 )
      v11 = *v10;
    else
      v11 = 0;
    v12 = (unsigned __int16 *)(v11 + 14);
  }
  else
  {
    v12 = 0;
  }
  XmlFileSystemPath = JobStore::GetXmlFileSystemPath((WCHAR **)this, v12, &lpMem);
  if ( XmlFileSystemPath < 0 )
  {
    operator delete(lpMem);
    return (unsigned int)XmlFileSystemPath;
  }
  v14 = -1;
  do
    ++v14;
  while ( a3[v14] );
  if ( v14 <= 0xFFFFFFFF )
  {
    while ( 1 )
    {
      v15 = 0;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 23, 0, 0) )
        break;
      Sleep(0x64u);
    }
    v16 = lpMem;
    if ( !*(_DWORD *)(*((_QWORD *)this + 10) + 184LL) )
    {
      v19 = 0;
LABEL_28:
      if ( v16 )
        HeapFree(g_PrivateHeap, 0, v16);
      return (unsigned int)v19;
    }
    SecurityDescriptorSize = 0;
    v17 = 0;
    SecurityDescriptor = 0;
    if ( StringSecurityDescriptor && *StringSecurityDescriptor )
    {
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
              StringSecurityDescriptor,
              1u,
              &SecurityDescriptor,
              &SecurityDescriptorSize) )
      {
        LastError = GetLastError();
        v19 = LastError;
        if ( LastError > 0 )
          v19 = (unsigned __int16)LastError | 0x80070000;
        if ( v19 >= 0 )
          v19 = -2147467259;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
            (_DWORD)v16,
            v19);
        }
        goto LABEL_26;
      }
      v15 = SecurityDescriptorSize;
      v17 = SecurityDescriptor;
    }
    v19 = JobStore::SaveJobFile(this, (const unsigned __int16 *)v16, a3, v14, v22, v17, v15);
LABEL_26:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    Path = (unsigned int)JobMoniker::GetPath(a2);
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
      Path,
      22);
  }
  operator delete(lpMem);
  return 2147942934LL;
}

```

## disassembly

```asm
0x180027c30  mov     [rsp+arg_8], rbx
0x180027c35  mov     [rsp+arg_10], rbp
0x180027c3a  push    rsi
0x180027c3b  push    rdi
0x180027c3c  push    r14
0x180027c3e  sub     rsp, 50h
0x180027c42  mov     r14, r9
0x180027c45  mov     rbp, r8
0x180027c48  mov     rsi, rdx
0x180027c4b  mov     rbx, rcx
0x180027c4e  xchg    ax, ax
0x180027c50  xor     ecx, ecx
0x180027c52  xor     eax, eax
0x180027c54  lock cmpxchg [rbx+5Ch], ecx
0x180027c59  jnz     short loc_180027C68
0x180027c5b  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180027c60  call    cs:__imp_Sleep
0x180027c66  jmp     short loc_180027C50
0x180027c68  mov     rax, [rbx+50h]
0x180027c6c  cmp     [rax+0B8h], ecx
0x180027c72  jz      loc_180027DDC
0x180027c78  mov     [rsp+68h+lpMem], rcx
0x180027c7d  mov     rax, [rsi+10h]
0x180027c81  test    rax, rax
0x180027c84  jz      loc_180027DE0
0x180027c8a  mov     rcx, [rax]; pbstr
0x180027c8d  test    rcx, rcx
0x180027c90  jz      loc_180027DEE
0x180027c96  call    cs:__imp_SysStringLen
0x180027c9c  test    eax, eax
0x180027c9e  jz      loc_180027DE0
0x180027ca4  mov     rax, [rsi+10h]
0x180027ca8  test    rax, rax
0x180027cab  jz      loc_180027DE7
0x180027cb1  mov     rcx, [rax]
0x180027cb4  lea     rdx, [rcx+0Eh]
0x180027cb8  lea     r8, [rsp+68h+lpMem]
0x180027cbd  mov     rcx, rbx
0x180027cc0  call    ?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x180027cc5  mov     edi, eax
0x180027cc7  test    eax, eax
0x180027cc9  js      loc_180027DF5
0x180027ccf  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180027cd6  nop     word ptr [rax+rax+00000000h]
0x180027ce0  inc     rdi
0x180027ce3  cmp     word ptr [rbp+rdi*2+0], 0
0x180027ce9  jnz     short loc_180027CE0
0x180027ceb  mov     eax, 0FFFFFFFFh
0x180027cf0  cmp     rdi, rax
0x180027cf3  ja      loc_180027E73
0x180027cf9  nop     dword ptr [rax+00000000h]
0x180027d00  xor     ecx, ecx
0x180027d02  xor     eax, eax
0x180027d04  lock cmpxchg [rbx+5Ch], ecx
0x180027d09  jnz     short loc_180027D18
0x180027d0b  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180027d10  call    cs:__imp_Sleep
0x180027d16  jmp     short loc_180027D00
0x180027d18  mov     rax, [rbx+50h]
0x180027d1c  mov     rsi, [rsp+68h+lpMem]
0x180027d21  cmp     [rax+0B8h], ecx
0x180027d27  jz      loc_180027DD8
0x180027d2d  mov     [rsp+68h+SecurityDescriptorSize], ecx
0x180027d31  xor     eax, eax
0x180027d33  mov     [rsp+68h+SecurityDescriptor], rax
0x180027d38  test    r14, r14
0x180027d3b  jz      loc_180027E52
0x180027d41  cmp     [r14], ax
0x180027d45  jz      loc_180027E52
0x180027d4b  lea     r9, [rsp+68h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180027d50  lea     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180027d55  mov     edx, 1; StringSDRevision
0x180027d5a  mov     rcx, r14; StringSecurityDescriptor
0x180027d5d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180027d63  test    eax, eax
0x180027d65  jnz     loc_180027E49
0x180027d6b  call    cs:__imp_GetLastError
0x180027d71  mov     ebx, eax
0x180027d73  test    eax, eax
0x180027d75  jg      loc_180027E03
0x180027d7b  mov     eax, 80004005h
0x180027d80  test    ebx, ebx
0x180027d82  cmovns  ebx, eax
0x180027d85  lea     rax, WPP_GLOBAL_Control
0x180027d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d93  cmp     rcx, rax
0x180027d96  jnz     short loc_180027E11
0x180027d98  mov     rcx, [rsp+68h+SecurityDescriptor]; hMem
0x180027d9d  test    rcx, rcx
0x180027da0  jz      short loc_180027DA9
0x180027da2  call    cs:__imp_LocalFree
0x180027da8  nop
0x180027da9  test    rsi, rsi
0x180027dac  jz      short loc_180027DC0
0x180027dae  mov     r8, rsi; lpMem
0x180027db1  xor     edx, edx; dwFlags
0x180027db3  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180027dba  call    cs:__imp_HeapFree
0x180027dc0  mov     eax, ebx
0x180027dc2  mov     rbx, [rsp+68h+arg_8]
0x180027dc7  mov     rbp, [rsp+68h+arg_10]
0x180027dcf  add     rsp, 50h
0x180027dd3  pop     r14
0x180027dd5  pop     rdi
0x180027dd6  pop     rsi
0x180027dd7  retn
0x180027dd8  xor     ebx, ebx
0x180027dda  jmp     short loc_180027DA9
0x180027ddc  xor     eax, eax
0x180027dde  jmp     short loc_180027DC2
0x180027de0  xor     edx, edx
0x180027de2  jmp     loc_180027CB8
0x180027de7  xor     ecx, ecx
0x180027de9  jmp     loc_180027CB4
0x180027dee  xor     eax, eax
0x180027df0  jmp     loc_180027C9C
0x180027df5  mov     rcx, [rsp+68h+lpMem]; void *
0x180027dfa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027dff  mov     eax, edi
0x180027e01  jmp     short loc_180027DC2
0x180027e03  movzx   ebx, ax
0x180027e06  or      ebx, 80070000h
0x180027e0c  jmp     loc_180027D7B
0x180027e11  test    dword ptr [rcx+1Ch], 40000h
0x180027e18  jz      loc_180027D98
0x180027e1e  cmp     byte ptr [rcx+19h], 2
0x180027e22  jb      loc_180027D98
0x180027e28  mov     edx, 44h ; 'D'
0x180027e2d  mov     [rsp+68h+var_48], ebx
0x180027e31  mov     r9, rsi
0x180027e34  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180027e3b  mov     rcx, [rcx+10h]
0x180027e3f  call    WPP_SF_Sd
0x180027e44  jmp     loc_180027D98
0x180027e49  mov     ecx, [rsp+68h+SecurityDescriptorSize]
0x180027e4d  mov     rax, [rsp+68h+SecurityDescriptor]
0x180027e52  mov     r9d, edi; unsigned int
0x180027e55  mov     [rsp+68h+var_38], ecx; unsigned int
0x180027e59  mov     [rsp+68h+var_40], rax; void *
0x180027e5e  mov     r8, rbp; unsigned __int16 *
0x180027e61  mov     rdx, rsi; unsigned __int16 *
0x180027e64  mov     rcx, rbx; this
0x180027e67  call    ?SaveJobFile@JobStore@@AEBAJPEBG0KKPEAXK@Z; JobStore::SaveJobFile(ushort const *,ushort const *,ulong,ulong,void *,ulong)
0x180027e6c  mov     ebx, eax
0x180027e6e  jmp     loc_180027D98
0x180027e73  lea     rax, WPP_GLOBAL_Control
0x180027e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e81  cmp     rcx, rax
0x180027e84  jz      short loc_180027EC5
0x180027e86  test    dword ptr [rcx+1Ch], 40000h
0x180027e8d  jz      short loc_180027EC5
0x180027e8f  cmp     byte ptr [rcx+19h], 2
0x180027e93  jb      short loc_180027EC5
0x180027e95  mov     rcx, rsi; this
0x180027e98  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180027e9d  mov     edx, 23h ; '#'
0x180027ea2  mov     [rsp+68h+var_48], 80070216h
0x180027eaa  mov     r9, rax
0x180027ead  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180027eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ebb  mov     rcx, [rcx+10h]
0x180027ebf  call    WPP_SF_Sd
0x180027ec4  nop
0x180027ec5  mov     rcx, [rsp+68h+lpMem]; void *
0x180027eca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027ecf  mov     eax, 80070216h
0x180027ed4  jmp     loc_180027DC2
```
