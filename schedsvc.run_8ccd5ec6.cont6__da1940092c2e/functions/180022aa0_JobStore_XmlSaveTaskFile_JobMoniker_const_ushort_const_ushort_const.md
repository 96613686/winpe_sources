# JobStore::XmlSaveTaskFile(JobMoniker const &,ushort const *,ushort const *)

- ea: `0x180022aa0`
- end: `0x180022d6c`
- name: `?XmlSaveTaskFile@JobStore@@QEAAJAEBVJobMoniker@@PEBG1@Z`
- size: `716`
- prototype: `__int64 __fastcall(JobStore *__hidden this, const struct JobMoniker *, const unsigned __int16 *, LPCWSTR StringSecurityDescriptor)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001d7ac`
- `0x180047ee0`
- `0x18004fc18`
- `0x18006fed4`

## callees

- `0x18000cc40`
- `0x180022aa0`
- `0x180022d80`
- `0x1800231b0`
- `0x18002db74`
- `0x180059140`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180022b0c`
- `OLEAUT32!__imp_SysStringLen` at `0x180022b0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022be7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022c46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022c46`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180022ad0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180022b80`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180022ad0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180022b80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022c28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022c28`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180022bd3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180022bd3`

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
0x180022aa0  mov     [rsp+arg_8], rbx
0x180022aa5  mov     [rsp+arg_10], rbp
0x180022aaa  push    rsi
0x180022aab  push    rdi
0x180022aac  push    r14
0x180022aae  sub     rsp, 50h
0x180022ab2  mov     r14, r9
0x180022ab5  mov     rbp, r8
0x180022ab8  mov     rsi, rdx
0x180022abb  mov     rbx, rcx
0x180022abe  xchg    ax, ax
0x180022ac0  xor     ecx, ecx
0x180022ac2  xor     eax, eax
0x180022ac4  lock cmpxchg [rbx+5Ch], ecx
0x180022ac9  jnz     short loc_180022ADE
0x180022acb  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180022ad0  call    cs:__imp_Sleep
0x180022ad7  nop     dword ptr [rax+rax+00h]
0x180022adc  jmp     short loc_180022AC0
0x180022ade  mov     rax, [rbx+50h]
0x180022ae2  cmp     [rax+0B8h], ecx
0x180022ae8  jz      loc_180022C6F
0x180022aee  mov     [rsp+68h+lpMem], rcx
0x180022af3  mov     rax, [rsi+10h]
0x180022af7  test    rax, rax
0x180022afa  jz      loc_180022C73
0x180022b00  mov     rcx, [rax]; pbstr
0x180022b03  test    rcx, rcx
0x180022b06  jz      loc_180022C81
0x180022b0c  call    cs:__imp_SysStringLen
0x180022b13  nop     dword ptr [rax+rax+00h]
0x180022b18  test    eax, eax
0x180022b1a  jz      loc_180022C73
0x180022b20  mov     rax, [rsi+10h]
0x180022b24  test    rax, rax
0x180022b27  jz      loc_180022C7A
0x180022b2d  mov     rcx, [rax]
0x180022b30  lea     rdx, [rcx+0Eh]
0x180022b34  lea     r8, [rsp+68h+lpMem]
0x180022b39  mov     rcx, rbx
0x180022b3c  call    ?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x180022b41  mov     edi, eax
0x180022b43  test    eax, eax
0x180022b45  js      loc_180022C88
0x180022b4b  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180022b52  inc     rdi
0x180022b55  cmp     word ptr [rbp+rdi*2+0], 0
0x180022b5b  jnz     short loc_180022B52
0x180022b5d  mov     eax, 0FFFFFFFFh
0x180022b62  cmp     rdi, rax
0x180022b65  ja      loc_180022D06
0x180022b6b  nop     dword ptr [rax+rax+00h]
0x180022b70  xor     ecx, ecx
0x180022b72  xor     eax, eax
0x180022b74  lock cmpxchg [rbx+5Ch], ecx
0x180022b79  jnz     short loc_180022B8E
0x180022b7b  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180022b80  call    cs:__imp_Sleep
0x180022b87  nop     dword ptr [rax+rax+00h]
0x180022b8c  jmp     short loc_180022B70
0x180022b8e  mov     rax, [rbx+50h]
0x180022b92  mov     rsi, [rsp+68h+lpMem]
0x180022b97  cmp     [rax+0B8h], ecx
0x180022b9d  jz      loc_180022C6B
0x180022ba3  mov     [rsp+68h+SecurityDescriptorSize], ecx
0x180022ba7  xor     eax, eax
0x180022ba9  mov     [rsp+68h+SecurityDescriptor], rax
0x180022bae  test    r14, r14
0x180022bb1  jz      loc_180022CE5
0x180022bb7  cmp     [r14], ax
0x180022bbb  jz      loc_180022CE5
0x180022bc1  lea     r9, [rsp+68h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180022bc6  lea     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180022bcb  mov     edx, 1; StringSDRevision
0x180022bd0  mov     rcx, r14; StringSecurityDescriptor
0x180022bd3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180022bda  nop     dword ptr [rax+rax+00h]
0x180022bdf  test    eax, eax
0x180022be1  jnz     loc_180022CDC
0x180022be7  call    cs:__imp_GetLastError
0x180022bee  nop     dword ptr [rax+rax+00h]
0x180022bf3  mov     ebx, eax
0x180022bf5  test    eax, eax
0x180022bf7  jg      loc_180022C96
0x180022bfd  mov     eax, 80004005h
0x180022c02  test    ebx, ebx
0x180022c04  cmovns  ebx, eax
0x180022c07  lea     rax, WPP_GLOBAL_Control
0x180022c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c15  cmp     rcx, rax
0x180022c18  jnz     loc_180022CA4
0x180022c1e  mov     rcx, [rsp+68h+SecurityDescriptor]; hMem
0x180022c23  test    rcx, rcx
0x180022c26  jz      short loc_180022C35
0x180022c28  call    cs:__imp_LocalFree
0x180022c2f  nop     dword ptr [rax+rax+00h]
0x180022c34  nop
0x180022c35  test    rsi, rsi
0x180022c38  jz      short loc_180022C52
0x180022c3a  mov     r8, rsi; lpMem
0x180022c3d  xor     edx, edx; dwFlags
0x180022c3f  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180022c46  call    cs:__imp_HeapFree
0x180022c4d  nop     dword ptr [rax+rax+00h]
0x180022c52  mov     eax, ebx
0x180022c54  mov     rbx, [rsp+68h+arg_8]
0x180022c59  mov     rbp, [rsp+68h+arg_10]
0x180022c61  add     rsp, 50h
0x180022c65  pop     r14
0x180022c67  pop     rdi
0x180022c68  pop     rsi
0x180022c69  retn
0x180022c6b  xor     ebx, ebx
0x180022c6d  jmp     short loc_180022C35
0x180022c6f  xor     eax, eax
0x180022c71  jmp     short loc_180022C54
0x180022c73  xor     edx, edx
0x180022c75  jmp     loc_180022B34
0x180022c7a  xor     ecx, ecx
0x180022c7c  jmp     loc_180022B30
0x180022c81  xor     eax, eax
0x180022c83  jmp     loc_180022B18
0x180022c88  mov     rcx, [rsp+68h+lpMem]; void *
0x180022c8d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022c92  mov     eax, edi
0x180022c94  jmp     short loc_180022C54
0x180022c96  movzx   ebx, ax
0x180022c99  or      ebx, 80070000h
0x180022c9f  jmp     loc_180022BFD
0x180022ca4  test    dword ptr [rcx+1Ch], 40000h
0x180022cab  jz      loc_180022C1E
0x180022cb1  cmp     byte ptr [rcx+19h], 2
0x180022cb5  jb      loc_180022C1E
0x180022cbb  mov     edx, 44h ; 'D'
0x180022cc0  mov     [rsp+68h+var_48], ebx
0x180022cc4  mov     r9, rsi
0x180022cc7  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180022cce  mov     rcx, [rcx+10h]
0x180022cd2  call    WPP_SF_Sd
0x180022cd7  jmp     loc_180022C1E
0x180022cdc  mov     ecx, [rsp+68h+SecurityDescriptorSize]
0x180022ce0  mov     rax, [rsp+68h+SecurityDescriptor]
0x180022ce5  mov     r9d, edi; unsigned int
0x180022ce8  mov     [rsp+68h+var_38], ecx; unsigned int
0x180022cec  mov     [rsp+68h+var_40], rax; void *
0x180022cf1  mov     r8, rbp; unsigned __int16 *
0x180022cf4  mov     rdx, rsi; unsigned __int16 *
0x180022cf7  mov     rcx, rbx; this
0x180022cfa  call    ?SaveJobFile@JobStore@@AEBAJPEBG0KKPEAXK@Z; JobStore::SaveJobFile(ushort const *,ushort const *,ulong,ulong,void *,ulong)
0x180022cff  mov     ebx, eax
0x180022d01  jmp     loc_180022C1E
0x180022d06  lea     rax, WPP_GLOBAL_Control
0x180022d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d14  cmp     rcx, rax
0x180022d17  jz      short loc_180022D58
0x180022d19  test    dword ptr [rcx+1Ch], 40000h
0x180022d20  jz      short loc_180022D58
0x180022d22  cmp     byte ptr [rcx+19h], 2
0x180022d26  jb      short loc_180022D58
0x180022d28  mov     rcx, rsi; this
0x180022d2b  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180022d30  mov     edx, 23h ; '#'
0x180022d35  mov     [rsp+68h+var_48], 80070216h
0x180022d3d  mov     r9, rax
0x180022d40  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180022d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d4e  mov     rcx, [rcx+10h]
0x180022d52  call    WPP_SF_Sd
0x180022d57  nop
0x180022d58  mov     rcx, [rsp+68h+lpMem]; void *
0x180022d5d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022d62  mov     eax, 80070216h
0x180022d67  jmp     loc_180022C54
```
