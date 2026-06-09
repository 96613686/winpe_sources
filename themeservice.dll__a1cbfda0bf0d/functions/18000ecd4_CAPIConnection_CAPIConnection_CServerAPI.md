# CAPIConnection::CAPIConnection(CServerAPI *)

- ea: `0x18000ecd4`
- end: `0x18000ee44`
- name: `??0CAPIConnection@@QEAA@PEAVCServerAPI@@@Z`
- size: `368`
- prototype: `CAPIConnection *__fastcall(CAPIConnection *this, struct CServerAPI *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000db00`

## callees

- `0x180003f90`
- `0x18000ecd4`
- `0x18000f9da`
- `0x18000fa00`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ee09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ee09`
- `ntdll!RtlInitializeCriticalSection` at `0x18000ed35`
- `ntdll!RtlInitializeCriticalSection` at `0x18000ed35`
- `ntdll!NtAlpcCreatePort` at `0x18000edfc`
- `ntdll!NtAlpcCreatePort` at `0x18000edfc`
- `ntdll!RtlInitUnicodeString` at `0x18000eda9`
- `ntdll!RtlInitUnicodeString` at `0x18000eda9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000ed60`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000ed60`

## pseudocode

```c
CAPIConnection *__fastcall CAPIConnection::CAPIConnection(CAPIConnection *this, struct CServerAPI *a2)
{
  __int64 v4; // rax
  const WCHAR *v5; // rax
  int v6; // eax
  PSECURITY_DESCRIPTOR v7; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-69h] BYREF
  __int128 v10; // [rsp+28h] [rbp-61h] BYREF
  __int128 v11; // [rsp+38h] [rbp-51h]
  __int128 v12; // [rsp+48h] [rbp-41h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-31h] BYREF
  _DWORD v14[4]; // [rsp+70h] [rbp-19h] BYREF
  __int64 v15; // [rsp+80h] [rbp-9h]

  *((_DWORD *)this + 2) = 1;
  *((_BYTE *)this + 12) = 0;
  *(_QWORD *)this = &CAPIConnection::`vftable';
  *((_BYTE *)this + 20) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 4) = -1073741801;
  *((_QWORD *)this + 3) = a2;
  *((_DWORD *)this + 12) = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 56));
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  SecurityDescriptor = 0;
  _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;0x001F0001;;;SY)(A;;0x00020001;;;BA)(A;;0x00020001;;;S-1-5-90-0)(A;;0x00000001;;;AC)(A;;0x00000001;;;S-1-"
          "15-3-1024-1502825166-1963708345-2616377461-2562897074-4192028372-3968301570-1997628692-1435953622)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v10 = 0;
    v11 = 0;
    v12 = 0;
    memset_0(v14, 0, 0x48u);
    v4 = *(_QWORD *)a2;
    DestinationString = 0;
    v5 = (const WCHAR *)(*(__int64 (__fastcall **)(struct CServerAPI *))(v4 + 8))(a2);
    RtlInitUnicodeString(&DestinationString, v5);
    LODWORD(v10) = 48;
    *(_QWORD *)&v11 = &DestinationString;
    v12 = (unsigned __int64)SecurityDescriptor;
    *((_QWORD *)&v10 + 1) = 0;
    DWORD2(v11) = 0;
    memset_0(v14, 0, 0x48u);
    v14[0] = 0x20000;
    v15 = 112;
    v6 = NtAlpcCreatePort((char *)this + 32, &v10, v14);
    v7 = SecurityDescriptor;
    *((_DWORD *)this + 4) = v6;
    LocalFree(v7);
  }
  if ( *((int *)this + 4) < 0 )
    CCountedObject::Release(a2);
  return this;
}

```

## disassembly

```asm
0x18000ecd4  mov     [rsp-8+arg_10], rbx
0x18000ecd9  mov     [rsp-8+arg_18], rsi
0x18000ecde  push    rbp
0x18000ecdf  push    rdi
0x18000ece0  push    r15
0x18000ece2  lea     rbp, [rsp-47h]
0x18000ece7  sub     rsp, 0D0h
0x18000ecee  mov     rax, cs:__security_cookie
0x18000ecf5  xor     rax, rsp
0x18000ecf8  mov     [rbp+57h+var_20], rax
0x18000ecfc  xor     r15d, r15d
0x18000ecff  mov     dword ptr [rcx+8], 1
0x18000ed06  lea     rax, ??_7CAPIConnection@@6B@; const CAPIConnection::`vftable'
0x18000ed0d  mov     [rcx+0Ch], r15b
0x18000ed11  mov     [rcx], rax
0x18000ed14  mov     rbx, rcx
0x18000ed17  mov     [rcx+14h], r15b
0x18000ed1b  mov     rdi, rdx
0x18000ed1e  mov     [rcx+20h], r15
0x18000ed22  mov     [rcx+28h], r15
0x18000ed26  mov     dword ptr [rcx+10h], 0C0000017h
0x18000ed2d  mov     [rcx+18h], rdx
0x18000ed31  add     rcx, 38h ; '8'; CriticalSection
0x18000ed35  call    cs:__imp_RtlInitializeCriticalSection
0x18000ed3b  mov     [rbx+30h], eax
0x18000ed3e  mov     [rbx+60h], r15
0x18000ed42  mov     [rbx+68h], r15
0x18000ed46  mov     [rbp+57h+SecurityDescriptor], r15
0x18000ed4a  lock inc dword ptr [rdi+8]
0x18000ed4e  xor     r9d, r9d; SecurityDescriptorSize
0x18000ed51  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000ed55  lea     edx, [r15+1]; StringSDRevision
0x18000ed59  lea     rcx, StringSecurityDescriptor; "D:(A;;0x001F0001;;;SY)(A;;0x00020001;;;"...
0x18000ed60  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000ed66  test    eax, eax
0x18000ed68  jz      loc_18000EE0F
0x18000ed6e  xorps   xmm0, xmm0
0x18000ed71  lea     r8d, [r15+48h]; Size
0x18000ed75  xor     edx, edx; Val
0x18000ed77  lea     rcx, [rbp+57h+var_70]; void *
0x18000ed7b  movups  [rbp+57h+var_B8], xmm0
0x18000ed7f  movups  [rbp+57h+var_A8], xmm0
0x18000ed83  movups  [rbp+57h+var_98], xmm0
0x18000ed87  call    memset_0
0x18000ed8c  mov     rax, [rdi]
0x18000ed8f  xorps   xmm0, xmm0
0x18000ed92  mov     rcx, rdi
0x18000ed95  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000ed99  mov     rax, [rax+8]
0x18000ed9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eda2  mov     rdx, rax; SourceString
0x18000eda5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000eda9  call    cs:__imp_RtlInitUnicodeString
0x18000edaf  lea     rax, [rbp+57h+DestinationString]
0x18000edb3  mov     dword ptr [rbp+57h+var_B8], 30h ; '0'
0x18000edba  mov     qword ptr [rbp+57h+var_A8], rax
0x18000edbe  lea     r8d, [r15+48h]; Size
0x18000edc2  mov     rax, [rbp+57h+SecurityDescriptor]
0x18000edc6  lea     rcx, [rbp+57h+var_70]; void *
0x18000edca  xor     edx, edx; Val
0x18000edcc  mov     qword ptr [rbp+57h+var_98], rax
0x18000edd0  mov     qword ptr [rbp+57h+var_B8+8], r15
0x18000edd4  mov     dword ptr [rbp+57h+var_A8+8], r15d
0x18000edd8  mov     qword ptr [rbp+57h+var_98+8], r15
0x18000eddc  call    memset_0
0x18000ede1  lea     r8, [rbp+57h+var_70]
0x18000ede5  mov     [rbp+57h+var_70], 20000h
0x18000edec  lea     rdx, [rbp+57h+var_B8]
0x18000edf0  mov     [rbp+57h+var_60], 70h ; 'p'
0x18000edf8  lea     rcx, [rbx+20h]
0x18000edfc  call    cs:__imp_NtAlpcCreatePort
0x18000ee02  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18000ee06  mov     [rbx+10h], eax
0x18000ee09  call    cs:__imp_LocalFree
0x18000ee0f  cmp     [rbx+10h], r15d
0x18000ee13  jge     short loc_18000EE1D
0x18000ee15  mov     rcx, rdi; this
0x18000ee18  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x18000ee1d  mov     rax, rbx
0x18000ee20  mov     rcx, [rbp+57h+var_20]
0x18000ee24  xor     rcx, rsp; StackCookie
0x18000ee27  call    __security_check_cookie
0x18000ee2c  lea     r11, [rsp+0E0h+var_10]
0x18000ee34  mov     rbx, [r11+30h]
0x18000ee38  mov     rsi, [r11+38h]
0x18000ee3c  mov     rsp, r11
0x18000ee3f  pop     r15
0x18000ee41  pop     rdi
0x18000ee42  pop     rbp
0x18000ee43  retn
```
