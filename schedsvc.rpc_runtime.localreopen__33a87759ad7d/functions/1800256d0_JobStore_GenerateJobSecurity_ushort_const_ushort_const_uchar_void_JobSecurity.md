# JobStore::GenerateJobSecurity(ushort const *,ushort const *,uchar,void *,JobSecurity &)

- ea: `0x1800256d0`
- end: `0x180025866`
- name: `?GenerateJobSecurity@JobStore@@QEBAJPEBG0EPEAXAEAVJobSecurity@@@Z`
- size: `406`
- prototype: `__int64 __fastcall(JobStore *__hidden this, const unsigned __int16 *, LPCWSTR StringSecurityDescriptor, BOOLEAN IsDirectoryObject, HANDLE, PSECURITY_DESCRIPTOR *NewDescriptor)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024ce0`
- `0x18002506c`
- `0x180045df0`

## callees

- `0x180025040`
- `0x1800256d0`
- `0x180025870`
- `0x180040900`
- `0x180052584`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180025780`
- `msvcrt!wcsrchr` at `0x180025780`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180025827`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180025827`
- `ntdll!RtlNewSecurityObjectEx` at `0x18002580f`
- `ntdll!RtlNewSecurityObjectEx` at `0x18002580f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002574f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002574f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002572d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002572d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JobStore::GenerateJobSecurity(
        JobStore *this,
        unsigned __int16 *a2,
        LPCWSTR StringSecurityDescriptor,
        BOOLEAN IsDirectoryObject,
        HANDLE Token,
        PSECURITY_DESCRIPTOR *NewDescriptor)
{
  int LastHrError; // ebx
  tsched *v10; // rcx
  const wchar_t *v11; // rcx
  void *v12; // r10
  wchar_t *v13; // rax
  wchar_t *v14; // rdi
  int v15; // eax
  NTSTATUS v16; // eax
  int v17; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-39h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+48h] [rbp-31h] BYREF
  void *v21; // [rsp+50h] [rbp-29h] BYREF
  int v22; // [rsp+58h] [rbp-21h]
  struct _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp-19h] BYREF

  LastHrError = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( !StringSecurityDescriptor )
  {
LABEL_9:
    v21 = 0;
    v22 = 0;
    if ( !tsched::IsRoot((tsched *)a2, a2) )
    {
      v13 = wcsrchr(v11, 0x5Cu);
      v14 = v13;
      if ( !v13 || v13 == a2 )
      {
        v15 = JobStore::RegJobSecurityQuery(this, L"\\", (struct JobSecurity *)&v21);
      }
      else
      {
        *v13 = 0;
        v15 = JobStore::RegJobSecurityQuery(this, a2, (struct JobSecurity *)&v21);
        *v14 = 92;
      }
      LastHrError = v15;
      if ( v15 < 0 )
        goto LABEL_20;
      v12 = v21;
      LastHrError = 0;
    }
    GenericMapping.GenericRead = 1179785;
    GenericMapping.GenericWrite = 1179926;
    GenericMapping.GenericExecute = 1179808;
    GenericMapping.GenericAll = 2032127;
    v16 = RtlNewSecurityObjectEx(
            v12,
            SecurityDescriptor,
            NewDescriptor,
            0,
            IsDirectoryObject,
            3u,
            Token,
            &GenericMapping);
    if ( v16 >= 0 )
    {
      *((_DWORD *)NewDescriptor + 2) = RtlLengthSecurityDescriptor(*NewDescriptor);
    }
    else
    {
      v17 = v16 | 0x10000000;
      if ( v17 < 0 )
        LastHrError = v17;
    }
LABEL_20:
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v21);
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&SecurityDescriptor);
    return (unsigned int)LastHrError;
  }
  if ( !*StringSecurityDescriptor )
  {
    SecurityDescriptor = 0;
    SecurityDescriptorSize = 0;
    goto LABEL_9;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         StringSecurityDescriptor,
         1u,
         &SecurityDescriptor,
         &SecurityDescriptorSize) )
  {
    goto LABEL_9;
  }
  LastHrError = tsched::GetLastHrError(v10, (int)a2);
  if ( LastHrError >= 0 )
  {
    LastHrError = 0;
    goto LABEL_9;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return (unsigned int)LastHrError;
}

```

## disassembly

```asm
0x1800256d0  push    rbp
0x1800256d2  push    rbx
0x1800256d3  push    rsi
0x1800256d4  push    rdi
0x1800256d5  push    r12
0x1800256d7  push    r13
0x1800256d9  push    r14
0x1800256db  push    r15
0x1800256dd  lea     rbp, [rsp-0Fh]
0x1800256e2  sub     rsp, 88h
0x1800256e9  mov     rax, cs:__security_cookie
0x1800256f0  xor     rax, rsp
0x1800256f3  mov     [rbp+47h+var_50], rax
0x1800256f7  mov     r12b, r9b
0x1800256fa  mov     rax, r8
0x1800256fd  mov     rsi, rdx
0x180025700  mov     r15, rcx
0x180025703  mov     r14, [rbp+47h+NewDescriptor]
0x180025707  mov     r13, [rbp+47h+arg_20]
0x18002570b  xor     ebx, ebx
0x18002570d  mov     [rbp+47h+SecurityDescriptor], rbx
0x180025711  mov     [rbp+47h+SecurityDescriptorSize], ebx
0x180025714  test    r8, r8
0x180025717  jz      short loc_180025765
0x180025719  cmp     [r8], bx
0x18002571d  jz      short loc_18002575E
0x18002571f  lea     r9, [rbp+47h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180025723  lea     r8, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x180025727  lea     edx, [rbx+1]; StringSDRevision
0x18002572a  mov     rcx, rax; StringSecurityDescriptor
0x18002572d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180025733  test    eax, eax
0x180025735  jnz     short loc_180025765
0x180025737  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18002573c  mov     ebx, eax
0x18002573e  test    eax, eax
0x180025740  jns     short loc_18002575A
0x180025742  mov     rcx, [rbp+47h+SecurityDescriptor]; hMem
0x180025746  test    rcx, rcx
0x180025749  jz      loc_180025844
0x18002574f  call    cs:__imp_LocalFree
0x180025755  jmp     loc_180025844
0x18002575a  xor     ebx, ebx
0x18002575c  jmp     short loc_180025765
0x18002575e  mov     [rbp+47h+SecurityDescriptor], rbx
0x180025762  mov     [rbp+47h+SecurityDescriptorSize], ebx
0x180025765  mov     r10, rbx
0x180025768  mov     [rbp+47h+var_70], rbx
0x18002576c  mov     [rbp+47h+var_68], ebx
0x18002576f  mov     rcx, rsi; this
0x180025772  call    ?IsRoot@tsched@@YA_NPEBG@Z; tsched::IsRoot(ushort const *)
0x180025777  test    al, al
0x180025779  jnz     short loc_1800257CB
0x18002577b  mov     edx, 5Ch ; '\'; Ch
0x180025780  call    cs:__imp_wcsrchr
0x180025786  mov     rdi, rax
0x180025789  test    rax, rax
0x18002578c  jz      short loc_1800257AC
0x18002578e  cmp     rax, rsi
0x180025791  jz      short loc_1800257AC
0x180025793  mov     [rax], bx
0x180025796  lea     r8, [rbp+47h+var_70]; struct JobSecurity *
0x18002579a  mov     rdx, rsi; unsigned __int16 *
0x18002579d  mov     rcx, r15; this
0x1800257a0  call    ?RegJobSecurityQuery@JobStore@@QEBAJPEBGAEAVJobSecurity@@@Z; JobStore::RegJobSecurityQuery(ushort const *,JobSecurity &)
0x1800257a5  mov     word ptr [rdi], 5Ch ; '\'
0x1800257aa  jmp     short loc_1800257BF
0x1800257ac  lea     r8, [rbp+47h+var_70]; struct JobSecurity *
0x1800257b0  lea     rdx, asc_1800A3DA8; "\\"
0x1800257b7  mov     rcx, r15; this
0x1800257ba  call    ?RegJobSecurityQuery@JobStore@@QEBAJPEBGAEAVJobSecurity@@@Z; JobStore::RegJobSecurityQuery(ushort const *,JobSecurity &)
0x1800257bf  mov     ebx, eax
0x1800257c1  test    eax, eax
0x1800257c3  js      short loc_180025831
0x1800257c5  mov     r10, [rbp+47h+var_70]
0x1800257c9  xor     ebx, ebx
0x1800257cb  mov     [rbp+47h+var_60.GenericRead], 120089h
0x1800257d2  mov     [rbp+47h+var_60.GenericWrite], 120116h
0x1800257d9  mov     [rbp+47h+var_60.GenericExecute], 1200A0h
0x1800257e0  mov     [rbp+47h+var_60.GenericAll], 1F01FFh
0x1800257e7  lea     rax, [rbp+47h+var_60]
0x1800257eb  mov     [rsp+0C0h+GenericMapping], rax; GenericMapping
0x1800257f0  mov     [rsp+0C0h+Token], r13; Token
0x1800257f5  mov     [rsp+0C0h+AutoInheritFlags], 3; AutoInheritFlags
0x1800257fd  mov     [rsp+0C0h+IsDirectoryObject], r12b; IsDirectoryObject
0x180025802  xor     r9d, r9d; ObjectType
0x180025805  mov     r8, r14; NewDescriptor
0x180025808  mov     rdx, [rbp+47h+SecurityDescriptor]; CreatorDescriptor
0x18002580c  mov     rcx, r10; ParentDescriptor
0x18002580f  call    cs:__imp_RtlNewSecurityObjectEx
0x180025815  test    eax, eax
0x180025817  jns     short loc_180025824
0x180025819  or      eax, 10000000h
0x18002581e  jge     short loc_180025831
0x180025820  mov     ebx, eax
0x180025822  jmp     short loc_180025831
0x180025824  mov     rcx, [r14]; SecurityDescriptor
0x180025827  call    cs:__imp_RtlLengthSecurityDescriptor
0x18002582d  mov     [r14+8], eax
0x180025831  lea     rcx, [rbp+47h+var_70]
0x180025835  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18002583a  nop
0x18002583b  lea     rcx, [rbp+47h+SecurityDescriptor]
0x18002583f  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180025844  mov     eax, ebx
0x180025846  mov     rcx, [rbp+47h+var_50]
0x18002584a  xor     rcx, rsp; StackCookie
0x18002584d  call    __security_check_cookie
0x180025852  add     rsp, 88h
0x180025859  pop     r15
0x18002585b  pop     r14
0x18002585d  pop     r13
0x18002585f  pop     r12
0x180025861  pop     rdi
0x180025862  pop     rsi
0x180025863  pop     rbx
0x180025864  pop     rbp
0x180025865  retn
```
