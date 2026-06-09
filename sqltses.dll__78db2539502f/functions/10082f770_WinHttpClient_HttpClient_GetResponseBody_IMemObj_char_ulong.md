# WinHttpClient::HttpClient::GetResponseBody(IMemObj *,char * *,ulong *)

- ea: `0x10082f770`
- end: `0x10082f9a4`
- name: `?GetResponseBody@HttpClient@WinHttpClient@@UEAA?AUHttpOpResult@2@PEAVIMemObj@@PEAPEADPEAK@Z`
- size: `564`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x10048b440`
- `0x10082e040`
- `0x10082f770`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10082f889`
- `KERNEL32!GetLastError` at `0x10082f889`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082f7e3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082f945`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082f7e3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082f945`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f7ff`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f89e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f8b6`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f8f1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f98b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f7ff`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f89e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f8b6`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f8f1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f98b`
- `WININET!InternetReadFile` at `0x10082f820`
- `WININET!InternetReadFile` at `0x10082f86e`
- `WININET!InternetReadFile` at `0x10082f820`
- `WININET!InternetReadFile` at `0x10082f86e`

## string_xrefs

- `0x10082f933`: `Sql\Ntdbms\msql\security\inc\SecureStringBuilder.h`
- `0x10082f7d0`: `Sql\Ntdbms\msql\security\src\httpclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall WinHttpClient::HttpClient::GetResponseBody(
        __int64 a1,
        _QWORD *a2,
        struct IMemObj *a3,
        _QWORD *a4,
        _DWORD *dwNumberOfBytesRead)
{
  _DWORD *v9; // r13
  void *v10; // rbx
  unsigned __int64 v11; // rbp
  void *v12; // rax
  void *v13; // rdi
  unsigned __int64 v14; // rcx
  void *v15; // rcx
  void *v17; // rdx
  unsigned int v18; // r14d
  void *v19; // rax
  void *v20; // r15
  __int64 v21; // [rsp+30h] [rbp-58h]
  void *Source; // [rsp+48h] [rbp-40h] BYREF
  __int64 v23; // [rsp+50h] [rbp-38h]

  v9 = dwNumberOfBytesRead;
  *dwNumberOfBytesRead = 0;
  v21 = 0;
  LODWORD(dwNumberOfBytesRead) = 0;
  v10 = 0;
  Source = 0;
  LODWORD(v11) = 0;
  v23 = 0;
  v12 = operator new[](0x400u, a3, 1, "Sql\\Ntdbms\\msql\\security\\src\\httpclient.cpp", 440, 6u);
  v13 = v12;
  if ( v12 )
  {
    if ( InternetReadFile(*(HINTERNET *)(a1 + 8), v12, 0x400u, (LPDWORD)&dwNumberOfBytesRead) )
    {
      while ( (_DWORD)dwNumberOfBytesRead )
      {
        if ( !(unsigned __int8)SecureStringBuilder<char>::Append(&Source, a3, v13, (unsigned int)dwNumberOfBytesRead) )
        {
          *a2 = 23;
          operator delete[](v13);
          v17 = Source;
          if ( !Source )
            return a2;
          memset(Source, 0, (unsigned int)v23);
          v15 = v17;
          goto LABEL_12;
        }
        if ( !InternetReadFile(*(HINTERNET *)(a1 + 8), v13, 0x400u, (LPDWORD)&dwNumberOfBytesRead) )
        {
          LODWORD(v11) = v23;
          v10 = Source;
          goto LABEL_8;
        }
      }
      v11 = (unsigned int)v23;
      v10 = Source;
      if ( Source )
      {
        v18 = v23 + 1;
        v19 = operator new[](
                (unsigned int)(v23 + 1),
                a3,
                1,
                "Sql\\Ntdbms\\msql\\security\\inc\\SecureStringBuilder.h",
                106,
                6u);
        v20 = v19;
        if ( v19 )
        {
          memcpy_s(v19, v18, v10, v18);
          *a4 = v20;
          *v9 = v11;
          goto LABEL_9;
        }
      }
      *a4 = 0;
      *a2 = 22;
      operator delete[](v13);
      if ( v10 )
      {
        v14 = v11;
        goto LABEL_11;
      }
    }
    else
    {
LABEL_8:
      LODWORD(v21) = 20;
      HIDWORD(v21) = GetLastError();
LABEL_9:
      *a2 = v21;
      operator delete[](v13);
      if ( v10 )
      {
        v14 = (unsigned int)v11;
LABEL_11:
        memset(v10, 0, v14);
        v15 = v10;
LABEL_12:
        operator delete[](v15);
      }
    }
  }
  else
  {
    *a2 = 21;
    operator delete[](0);
  }
  return a2;
}

```

## disassembly

```asm
0x10082f770  mov     r11, rsp
0x10082f773  push    rdi
0x10082f774  push    r12
0x10082f776  push    r13
0x10082f778  push    r14
0x10082f77a  push    r15
0x10082f77c  sub     rsp, 60h
0x10082f780  mov     qword ptr [r11-50h], 0FFFFFFFFFFFFFFFEh
0x10082f788  mov     [r11+8], rbx
0x10082f78c  mov     [r11+10h], rbp
0x10082f790  mov     [r11+18h], rsi
0x10082f794  mov     r12, r9
0x10082f797  mov     r15, r8
0x10082f79a  mov     rsi, rdx
0x10082f79d  mov     r14, rcx
0x10082f7a0  xor     eax, eax
0x10082f7a2  mov     r13, [rsp+88h+dwNumberOfBytesRead]
0x10082f7aa  mov     [r13+0], eax
0x10082f7ae  mov     [rsp+88h+var_58], rax
0x10082f7b3  mov     [r11+28h], eax
0x10082f7b7  mov     ebx, eax
0x10082f7b9  mov     [r11-40h], rax
0x10082f7bd  mov     ebp, eax
0x10082f7bf  mov     [r11-38h], rax
0x10082f7c3  mov     [rsp+88h+var_60], 6
0x10082f7c8  mov     [rsp+88h+var_68], 1B8h
0x10082f7d0  lea     r9, aSqlNtdbmsMsqlS_1; "Sql\\Ntdbms\\msql\\security\\src\\httpc"...
0x10082f7d7  lea     r8d, [rax+1]
0x10082f7db  mov     rdx, r15
0x10082f7de  mov     ecx, 400h
0x10082f7e3  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10082f7e9  mov     rdi, rax
0x10082f7ec  mov     [rsp+88h+var_48], rax
0x10082f7f1  test    rax, rax
0x10082f7f4  jnz     short loc_10082F80B
0x10082f7f6  mov     qword ptr [rsi], 15h
0x10082f7fd  xor     ecx, ecx
0x10082f7ff  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082f805  nop
0x10082f806  jmp     loc_10082F8BC
0x10082f80b  lea     r9, [rsp+88h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x10082f813  mov     r8d, 400h; dwNumberOfBytesToRead
0x10082f819  mov     rdx, rdi; lpBuffer
0x10082f81c  mov     rcx, [r14+8]; hFile
0x10082f820  call    cs:__imp_InternetReadFile
0x10082f826  test    eax, eax
0x10082f828  jz      short loc_10082F881
0x10082f82a  nop     word ptr [rax+rax]
0x10082f82f  nop
0x10082f830  mov     r9d, dword ptr [rsp+88h+dwNumberOfBytesRead]
0x10082f838  test    r9d, r9d
0x10082f83b  jz      loc_10082F912
0x10082f841  mov     r8, rdi
0x10082f844  mov     rdx, r15
0x10082f847  lea     rcx, [rsp+88h+Source]
0x10082f84c  call    ?Append@?$SecureStringBuilder@D@@QEAA_NPEAVIMemObj@@PEBDK@Z; SecureStringBuilder<char>::Append(IMemObj *,char const *,ulong)
0x10082f851  test    al, al
0x10082f853  jz      loc_10082F8DD
0x10082f859  lea     r9, [rsp+88h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x10082f861  mov     r8d, 400h; dwNumberOfBytesToRead
0x10082f867  mov     rdx, rdi; lpBuffer
0x10082f86a  mov     rcx, [r14+8]; hFile
0x10082f86e  call    cs:__imp_InternetReadFile
0x10082f874  test    eax, eax
0x10082f876  jnz     short loc_10082F830
0x10082f878  mov     ebp, dword ptr [rsp+88h+var_38]
0x10082f87c  mov     rbx, [rsp+88h+Source]
0x10082f881  mov     dword ptr [rsp+88h+var_58], 14h
0x10082f889  call    cs:__imp_GetLastError
0x10082f88f  mov     dword ptr [rsp+88h+var_58+4], eax
0x10082f893  mov     rax, [rsp+88h+var_58]
0x10082f898  mov     [rsi], rax
0x10082f89b  mov     rcx, rdi
0x10082f89e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082f8a4  nop
0x10082f8a5  test    rbx, rbx
0x10082f8a8  jz      short loc_10082F8BC
0x10082f8aa  mov     ecx, ebp
0x10082f8ac  xor     eax, eax
0x10082f8ae  mov     rdi, rbx
0x10082f8b1  rep stosb
0x10082f8b3  mov     rcx, rbx
0x10082f8b6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082f8bc  mov     rax, rsi
0x10082f8bf  lea     r11, [rsp+88h+var_28]
0x10082f8c4  mov     rbx, [r11+30h]
0x10082f8c8  mov     rbp, [r11+38h]
0x10082f8cc  mov     rsi, [r11+40h]
0x10082f8d0  mov     rsp, r11
0x10082f8d3  pop     r15
0x10082f8d5  pop     r14
0x10082f8d7  pop     r13
0x10082f8d9  pop     r12
0x10082f8db  pop     rdi
0x10082f8dc  retn
0x10082f8dd  mov     [rsp+88h+var_58], 17h
0x10082f8e6  mov     rax, [rsp+88h+var_58]
0x10082f8eb  mov     [rsi], rax
0x10082f8ee  mov     rcx, rdi
0x10082f8f1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082f8f7  nop
0x10082f8f8  mov     rdx, [rsp+88h+Source]
0x10082f8fd  test    rdx, rdx
0x10082f900  jz      short loc_10082F8BC
0x10082f902  mov     ecx, dword ptr [rsp+88h+var_38]
0x10082f906  mov     rdi, rdx
0x10082f909  xor     eax, eax
0x10082f90b  rep stosb
0x10082f90d  mov     rcx, rdx
0x10082f910  jmp     short loc_10082F8B6
0x10082f912  mov     ebp, dword ptr [rsp+88h+var_38]
0x10082f916  mov     rbx, [rsp+88h+Source]
0x10082f91b  test    rbx, rbx
0x10082f91e  jz      short loc_10082F971
0x10082f920  lea     eax, [rbp+1]
0x10082f923  mov     r14d, eax
0x10082f926  mov     [rsp+88h+var_60], 6
0x10082f92b  mov     [rsp+88h+var_68], 6Ah ; 'j'
0x10082f933  lea     r9, aSqlNtdbmsMsqlS_0; "Sql\\Ntdbms\\msql\\security\\inc\\Secur"...
0x10082f93a  mov     r8d, 1
0x10082f940  mov     rdx, r15
0x10082f943  mov     ecx, eax
0x10082f945  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10082f94b  mov     r15, rax
0x10082f94e  test    rax, rax
0x10082f951  jz      short loc_10082F971
0x10082f953  mov     r9d, r14d; SourceSize
0x10082f956  mov     r8, rbx; Source
0x10082f959  mov     edx, r14d; DestinationSize
0x10082f95c  mov     rcx, rax; Destination
0x10082f95f  call    memcpy_s
0x10082f964  mov     [r12], r15
0x10082f968  mov     [r13+0], ebp
0x10082f96c  jmp     loc_10082F893
0x10082f971  xor     eax, eax
0x10082f973  mov     [r12], rax
0x10082f977  mov     [rsp+88h+var_58], 16h
0x10082f980  mov     rax, [rsp+88h+var_58]
0x10082f985  mov     [rsi], rax
0x10082f988  mov     rcx, rdi
0x10082f98b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082f991  nop
0x10082f992  test    rbx, rbx
0x10082f995  jz      loc_10082F8BC
0x10082f99b  mov     rcx, rbp
0x10082f99e  jmp     loc_10082F8AC
```
