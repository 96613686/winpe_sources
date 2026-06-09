# CNTService::Uninstall(void)

- ea: `0x140049b50`
- end: `0x140049e6b`
- name: `?Uninstall@CNTService@@UEAAKXZ`
- size: `795`
- prototype: `unsigned int __fastcall(CNTService *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x140053cf0`

## callees

- `0x140003690`
- `0x14000b3b0`
- `0x14000c920`
- `0x140018df0`
- `0x14003f17c`
- `0x140045f20`
- `0x140047798`
- `0x1400488f4`
- `0x140049898`
- `0x140049b50`
- `0x140049f34`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x140049bbc`
- `ADVAPI32!OpenSCManagerW` at `0x140049bbc`
- `ADVAPI32!OpenServiceW` at `0x140049c30`
- `ADVAPI32!OpenServiceW` at `0x140049c30`
- `ADVAPI32!CloseServiceHandle` at `0x140049d7b`
- `ADVAPI32!CloseServiceHandle` at `0x140049da6`
- `ADVAPI32!CloseServiceHandle` at `0x140049d7b`
- `ADVAPI32!CloseServiceHandle` at `0x140049da6`
- `ADVAPI32!DeleteService` at `0x140049cc6`
- `ADVAPI32!DeleteService` at `0x140049cc6`
- `KERNEL32!GetTickCount` at `0x140049d81`
- `KERNEL32!GetTickCount` at `0x140049d81`
- `KERNEL32!GetLastError` at `0x140049bca`
- `KERNEL32!GetLastError` at `0x140049c3e`
- `KERNEL32!GetLastError` at `0x140049cfd`
- `KERNEL32!GetLastError` at `0x140049bca`
- `KERNEL32!GetLastError` at `0x140049c3e`
- `KERNEL32!GetLastError` at `0x140049cfd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNTService::Uninstall(LPCWSTR *this)
{
  SC_HANDLE v2; // rax
  struct SC_HANDLE__ *v3; // r14
  DWORD v4; // eax
  DWORD v5; // edi
  struct _EVENT_DESCRIPTOR v6; // xmm0
  const unsigned __int16 **v7; // rsi
  SC_HANDLE v8; // rax
  unsigned int v9; // r8d
  SC_HANDLE v10; // rbx
  DWORD v11; // eax
  DWORD LastError; // eax
  struct _EVENT_DESCRIPTOR v13; // xmm0
  unsigned __int16 *v15[2]; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DESCRIPTOR v16; // [rsp+40h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
  v16 = (struct _EVENT_DESCRIPTOR)WMC_I_SERVICE_UNINSTALLED;
  v2 = OpenSCManagerW(0, 0, 0xF003Fu);
  v3 = v2;
  if ( v2 )
  {
    v7 = this + 5;
    v8 = OpenServiceW(v2, this[5], 0x10024u);
    v10 = v8;
    if ( v8 )
    {
      StopService(v3, v8, v9);
      if ( DeleteService(v10) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
        }
        v5 = 0;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError == 1072 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
          }
          v5 = 0;
          v13 = (struct _EVENT_DESCRIPTOR)WMC_I_SERVICE_UNINSTALLED_MARKEDFORDELETE;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              69,
              &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids,
              LastError);
          }
          v13 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_UNINSTALL_FAILED_DELETESERVICE;
        }
        v16 = v13;
      }
      CloseServiceHandle(v10);
      GetTickCount();
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        v15,
        (const void **)this + 5);
      WaitForDeletion(v3);
    }
    else
    {
      v11 = GetLastError();
      v5 = v11;
      if ( v11 == 1060 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
        }
        v5 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v11);
        }
        v16 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_UNINSTALL_FAILED_OPENSERVICE;
      }
    }
    CloseServiceHandle(v3);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v4);
    }
    if ( v5 == 5 )
      v6 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_UNINSTALL_FAILED_OPENSCMANAGER_ACCESSDENIED;
    else
      v6 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_UNINSTALL_FAILED_OPENSCMANAGER_UNKNOWN;
    v16 = v6;
    v7 = this + 5;
  }
  if ( v5 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(v15);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
      v15,
      L"%lu",
      v5);
    CNTService::LogEvent((CNTService *)this, &v16, *v7, v15[0], 0);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v15);
  }
  else
  {
    CNTService::LogEvent((CNTService *)this, &v16, *v7, 0, 0);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)(v5 != 0 ? 2 : 5) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x140049b50  push    rbp
0x140049b52  push    rbx
0x140049b53  push    rsi
0x140049b54  push    rdi
0x140049b55  push    r12
0x140049b57  push    r13
0x140049b59  push    r14
0x140049b5b  push    r15
0x140049b5d  mov     rbp, rsp
0x140049b60  sub     rsp, 68h
0x140049b64  mov     rax, cs:__security_cookie
0x140049b6b  xor     rax, rsp
0x140049b6e  mov     [rbp+var_18], rax
0x140049b72  mov     r15, rcx
0x140049b75  lea     r12, WPP_GLOBAL_Control
0x140049b7c  lea     r13, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140049b83  mov     rcx, cs:WPP_GLOBAL_Control
0x140049b8a  cmp     rcx, r12
0x140049b8d  jz      short loc_140049BA6
0x140049b8f  test    byte ptr [rcx+1Ch], 1
0x140049b93  jz      short loc_140049BA6
0x140049b95  mov     edx, 3Fh ; '?'
0x140049b9a  mov     r8, r13
0x140049b9d  mov     rcx, [rcx+10h]
0x140049ba1  call    WPP_SF_
0x140049ba6  movups  xmm0, cs:WMC_I_SERVICE_UNINSTALLED
0x140049bad  movdqu  xmmword ptr [rbp+var_28.Id], xmm0
0x140049bb2  xor     edx, edx; lpDatabaseName
0x140049bb4  xor     ecx, ecx; lpMachineName
0x140049bb6  mov     r8d, 0F003Fh; dwDesiredAccess
0x140049bbc  call    cs:__imp_OpenSCManagerW
0x140049bc2  mov     r14, rax
0x140049bc5  test    rax, rax
0x140049bc8  jnz     short loc_140049C20
0x140049bca  call    cs:__imp_GetLastError
0x140049bd0  mov     edi, eax
0x140049bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140049bd9  cmp     rcx, r12
0x140049bdc  jz      short loc_140049BFD
0x140049bde  test    byte ptr [rcx+1Ch], 2
0x140049be2  jz      short loc_140049BFD
0x140049be4  cmp     byte ptr [rcx+19h], 2
0x140049be8  jb      short loc_140049BFD
0x140049bea  lea     edx, [r14+40h]
0x140049bee  mov     r9d, eax
0x140049bf1  mov     r8, r13
0x140049bf4  mov     rcx, [rcx+10h]
0x140049bf8  call    WPP_SF_d
0x140049bfd  cmp     edi, 5
0x140049c00  jnz     short loc_140049C0B
0x140049c02  movups  xmm0, cs:WMC_E_SERVICE_UNINSTALL_FAILED_OPENSCMANAGER_ACCESSDENIED
0x140049c09  jmp     short loc_140049C12
0x140049c0b  movups  xmm0, cs:WMC_E_SERVICE_UNINSTALL_FAILED_OPENSCMANAGER_UNKNOWN
0x140049c12  movdqu  xmmword ptr [rbp+var_28.Id], xmm0
0x140049c17  lea     rsi, [r15+28h]
0x140049c1b  jmp     loc_140049DAC
0x140049c20  lea     rsi, [r15+28h]
0x140049c24  mov     r8d, 10024h; dwDesiredAccess
0x140049c2a  mov     rdx, [rsi]; lpServiceName
0x140049c2d  mov     rcx, r14; hSCManager
0x140049c30  call    cs:__imp_OpenServiceW
0x140049c36  mov     rbx, rax
0x140049c39  test    rax, rax
0x140049c3c  jnz     short loc_140049CB8
0x140049c3e  call    cs:__imp_GetLastError
0x140049c44  mov     edi, eax
0x140049c46  cmp     eax, 424h
0x140049c4b  jnz     short loc_140049C7B
0x140049c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140049c54  cmp     rcx, r12
0x140049c57  jz      short loc_140049C74
0x140049c59  test    byte ptr [rcx+1Ch], 2
0x140049c5d  jz      short loc_140049C74
0x140049c5f  cmp     byte ptr [rcx+19h], 4
0x140049c63  jb      short loc_140049C74
0x140049c65  lea     edx, [rbx+41h]
0x140049c68  mov     r8, r13
0x140049c6b  mov     rcx, [rcx+10h]
0x140049c6f  call    WPP_SF_
0x140049c74  xor     edi, edi
0x140049c76  jmp     loc_140049DA3
0x140049c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140049c82  cmp     rcx, r12
0x140049c85  jz      short loc_140049CA7
0x140049c87  test    byte ptr [rcx+1Ch], 2
0x140049c8b  jz      short loc_140049CA7
0x140049c8d  cmp     byte ptr [rcx+19h], 2
0x140049c91  jb      short loc_140049CA7
0x140049c93  mov     edx, 42h ; 'B'
0x140049c98  mov     r9d, eax
0x140049c9b  mov     r8, r13
0x140049c9e  mov     rcx, [rcx+10h]
0x140049ca2  call    WPP_SF_d
0x140049ca7  movups  xmm0, cs:WMC_E_SERVICE_UNINSTALL_FAILED_OPENSERVICE
0x140049cae  movdqu  xmmword ptr [rbp+var_28.Id], xmm0
0x140049cb3  jmp     loc_140049DA3
0x140049cb8  mov     rdx, rbx; struct SC_HANDLE__ *
0x140049cbb  mov     rcx, r14; struct SC_HANDLE__ *
0x140049cbe  call    ?StopService@@YAKPEAUSC_HANDLE__@@0K@Z; StopService(SC_HANDLE__ *,SC_HANDLE__ *,ulong)
0x140049cc3  mov     rcx, rbx; hService
0x140049cc6  call    cs:__imp_DeleteService
0x140049ccc  test    eax, eax
0x140049cce  jz      short loc_140049CFD
0x140049cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x140049cd7  cmp     rcx, r12
0x140049cda  jz      short loc_140049CF9
0x140049cdc  test    byte ptr [rcx+1Ch], 2
0x140049ce0  jz      short loc_140049CF9
0x140049ce2  cmp     byte ptr [rcx+19h], 4
0x140049ce6  jb      short loc_140049CF9
0x140049ce8  mov     edx, 43h ; 'C'
0x140049ced  mov     r8, r13
0x140049cf0  mov     rcx, [rcx+10h]
0x140049cf4  call    WPP_SF_
0x140049cf9  xor     edi, edi
0x140049cfb  jmp     short loc_140049D78
0x140049cfd  call    cs:__imp_GetLastError
0x140049d03  mov     edi, eax
0x140049d05  cmp     eax, 430h
0x140049d0a  jnz     short loc_140049D40
0x140049d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140049d13  cmp     rcx, r12
0x140049d16  jz      short loc_140049D35
0x140049d18  test    byte ptr [rcx+1Ch], 2
0x140049d1c  jz      short loc_140049D35
0x140049d1e  cmp     byte ptr [rcx+19h], 4
0x140049d22  jb      short loc_140049D35
0x140049d24  mov     edx, 44h ; 'D'
0x140049d29  mov     r8, r13
0x140049d2c  mov     rcx, [rcx+10h]
0x140049d30  call    WPP_SF_
0x140049d35  xor     edi, edi
0x140049d37  movups  xmm0, cs:WMC_I_SERVICE_UNINSTALLED_MARKEDFORDELETE
0x140049d3e  jmp     short loc_140049D73
0x140049d40  mov     rcx, cs:WPP_GLOBAL_Control
0x140049d47  cmp     rcx, r12
0x140049d4a  jz      short loc_140049D6C
0x140049d4c  test    byte ptr [rcx+1Ch], 2
0x140049d50  jz      short loc_140049D6C
0x140049d52  cmp     byte ptr [rcx+19h], 2
0x140049d56  jb      short loc_140049D6C
0x140049d58  mov     edx, 45h ; 'E'
0x140049d5d  mov     r9d, eax
0x140049d60  mov     r8, r13
0x140049d63  mov     rcx, [rcx+10h]
0x140049d67  call    WPP_SF_d
0x140049d6c  movups  xmm0, cs:WMC_E_SERVICE_UNINSTALL_FAILED_DELETESERVICE
0x140049d73  movdqu  xmmword ptr [rbp+var_28.Id], xmm0
0x140049d78  mov     rcx, rbx; hSCObject
0x140049d7b  call    cs:__imp_CloseServiceHandle
0x140049d81  call    cs:__imp_GetTickCount
0x140049d87  mov     ebx, eax
0x140049d89  mov     rdx, rsi
0x140049d8c  lea     rcx, [rbp+var_38]
0x140049d90  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x140049d95  mov     r8d, ebx
0x140049d98  mov     rdx, rax
0x140049d9b  mov     rcx, r14; hSCManager
0x140049d9e  call    ?WaitForDeletion@@YAKPEAUSC_HANDLE__@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@KK@Z; WaitForDeletion(SC_HANDLE__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ulong,ulong)
0x140049da3  mov     rcx, r14; hSCObject
0x140049da6  call    cs:__imp_CloseServiceHandle
0x140049dac  test    edi, edi
0x140049dae  jnz     short loc_140049DCD
0x140049db0  mov     [rsp+68h+var_48], 0; unsigned __int16 *
0x140049db9  xor     r9d, r9d; unsigned __int16 *
0x140049dbc  mov     r8, [rsi]; unsigned __int16 *
0x140049dbf  lea     rdx, [rbp+var_28]; struct _EVENT_DESCRIPTOR *
0x140049dc3  mov     rcx, r15; this
0x140049dc6  call    ?LogEvent@CNTService@@QEAAXAEBU_EVENT_DESCRIPTOR@@PEBG11@Z; CNTService::LogEvent(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ushort const *)
0x140049dcb  jmp     short loc_140049E10
0x140049dcd  lea     rcx, [rbp+var_38]
0x140049dd1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140049dd6  nop
0x140049dd7  mov     r8d, edi
0x140049dda  lea     rdx, aLu; "%lu"
0x140049de1  lea     rcx, [rbp+var_38]
0x140049de5  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x140049dea  mov     [rsp+68h+var_48], 0; unsigned __int16 *
0x140049df3  mov     r9, [rbp+var_38]; unsigned __int16 *
0x140049df7  mov     r8, [rsi]; unsigned __int16 *
0x140049dfa  lea     rdx, [rbp+var_28]; struct _EVENT_DESCRIPTOR *
0x140049dfe  mov     rcx, r15; this
0x140049e01  call    ?LogEvent@CNTService@@QEAAXAEBU_EVENT_DESCRIPTOR@@PEBG11@Z; CNTService::LogEvent(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ushort const *)
0x140049e06  nop
0x140049e07  lea     rcx, [rbp+var_38]
0x140049e0b  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140049e10  mov     rcx, cs:WPP_GLOBAL_Control
0x140049e17  cmp     rcx, r12
0x140049e1a  jz      short loc_140049E4C
0x140049e1c  test    byte ptr [rcx+1Ch], 1
0x140049e20  jz      short loc_140049E4C
0x140049e22  movzx   r9d, byte ptr [rcx+19h]
0x140049e27  mov     eax, edi
0x140049e29  neg     eax
0x140049e2b  sbb     edx, edx
0x140049e2d  and     edx, 0FFFFFFFDh
0x140049e30  add     edx, 5
0x140049e33  cmp     r9d, edx
0x140049e36  jb      short loc_140049E4C
0x140049e38  mov     edx, 46h ; 'F'
0x140049e3d  mov     r9d, edi
0x140049e40  mov     r8, r13
0x140049e43  mov     rcx, [rcx+10h]
0x140049e47  call    WPP_SF_d
0x140049e4c  mov     eax, edi
0x140049e4e  mov     rcx, [rbp+var_18]
0x140049e52  xor     rcx, rsp; StackCookie
0x140049e55  call    __security_check_cookie
0x140049e5a  add     rsp, 68h
0x140049e5e  pop     r15
0x140049e60  pop     r14
0x140049e62  pop     r13
0x140049e64  pop     r12
0x140049e66  pop     rdi
0x140049e67  pop     rsi
0x140049e68  pop     rbx
0x140049e69  pop     rbp
0x140049e6a  retn
```
