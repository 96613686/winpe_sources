# JobStore::GenerateJobSecurity(ushort const *,ushort const *,uchar,void *,JobSecurity &)

- ea: `0x1800204e0`
- end: `0x180020695`
- name: `?GenerateJobSecurity@JobStore@@QEBAJPEBG0EPEAXAEAVJobSecurity@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(JobStore *__hidden this, const unsigned __int16 *, LPCWSTR StringSecurityDescriptor, BOOLEAN IsDirectoryObject, HANDLE, PSECURITY_DESCRIPTOR *NewDescriptor)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001fa60`
- `0x18001fe44`
- `0x180047ee0`

## callees

- `0x18001fe10`
- `0x1800204e0`
- `0x1800206a0`
- `0x180041610`
- `0x180054c80`
- `0x180082a40`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002059c`
- `msvcrt!wcsrchr` at `0x18002059c`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002064f`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002064f`
- `ntdll!RtlNewSecurityObjectEx` at `0x180020631`
- `ntdll!RtlNewSecurityObjectEx` at `0x180020631`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020565`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020565`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002053d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002053d`

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
0x1800204e0  push    rbp
0x1800204e2  push    rbx
0x1800204e3  push    rsi
0x1800204e4  push    rdi
0x1800204e5  push    r12
0x1800204e7  push    r13
0x1800204e9  push    r14
0x1800204eb  push    r15
0x1800204ed  lea     rbp, [rsp-0Fh]
0x1800204f2  sub     rsp, 88h
0x1800204f9  mov     rax, cs:__security_cookie
0x180020500  xor     rax, rsp
0x180020503  mov     [rbp+47h+var_50], rax
0x180020507  mov     r12b, r9b
0x18002050a  mov     rax, r8
0x18002050d  mov     rsi, rdx
0x180020510  mov     r15, rcx
0x180020513  mov     r14, [rbp+47h+NewDescriptor]
0x180020517  mov     r13, [rbp+47h+arg_20]
0x18002051b  xor     ebx, ebx
0x18002051d  mov     [rbp+47h+SecurityDescriptor], rbx
0x180020521  mov     [rbp+47h+SecurityDescriptorSize], ebx
0x180020524  test    r8, r8
0x180020527  jz      short loc_180020581
0x180020529  cmp     [r8], bx
0x18002052d  jz      short loc_18002057A
0x18002052f  lea     r9, [rbp+47h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180020533  lea     r8, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x180020537  lea     edx, [rbx+1]; StringSDRevision
0x18002053a  mov     rcx, rax; StringSecurityDescriptor
0x18002053d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180020544  nop     dword ptr [rax+rax+00h]
0x180020549  test    eax, eax
0x18002054b  jnz     short loc_180020581
0x18002054d  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180020552  mov     ebx, eax
0x180020554  test    eax, eax
0x180020556  jns     short loc_180020576
0x180020558  mov     rcx, [rbp+47h+SecurityDescriptor]; hMem
0x18002055c  test    rcx, rcx
0x18002055f  jz      loc_180020672
0x180020565  call    cs:__imp_LocalFree
0x18002056c  nop     dword ptr [rax+rax+00h]
0x180020571  jmp     loc_180020672
0x180020576  xor     ebx, ebx
0x180020578  jmp     short loc_180020581
0x18002057a  mov     [rbp+47h+SecurityDescriptor], rbx
0x18002057e  mov     [rbp+47h+SecurityDescriptorSize], ebx
0x180020581  mov     r10, rbx
0x180020584  mov     [rbp+47h+var_70], rbx
0x180020588  mov     [rbp+47h+var_68], ebx
0x18002058b  mov     rcx, rsi; this
0x18002058e  call    ?IsRoot@tsched@@YA_NPEBG@Z; tsched::IsRoot(ushort const *)
0x180020593  test    al, al
0x180020595  jnz     short loc_1800205ED
0x180020597  mov     edx, 5Ch ; '\'; Ch
0x18002059c  call    cs:__imp_wcsrchr
0x1800205a3  nop     dword ptr [rax+rax+00h]
0x1800205a8  mov     rdi, rax
0x1800205ab  test    rax, rax
0x1800205ae  jz      short loc_1800205CE
0x1800205b0  cmp     rax, rsi
0x1800205b3  jz      short loc_1800205CE
0x1800205b5  mov     [rax], bx
0x1800205b8  lea     r8, [rbp+47h+var_70]; struct JobSecurity *
0x1800205bc  mov     rdx, rsi; unsigned __int16 *
0x1800205bf  mov     rcx, r15; this
0x1800205c2  call    ?RegJobSecurityQuery@JobStore@@QEBAJPEBGAEAVJobSecurity@@@Z; JobStore::RegJobSecurityQuery(ushort const *,JobSecurity &)
0x1800205c7  mov     word ptr [rdi], 5Ch ; '\'
0x1800205cc  jmp     short loc_1800205E1
0x1800205ce  lea     r8, [rbp+47h+var_70]; struct JobSecurity *
0x1800205d2  lea     rdx, asc_1800A7EC0; "\\"
0x1800205d9  mov     rcx, r15; this
0x1800205dc  call    ?RegJobSecurityQuery@JobStore@@QEBAJPEBGAEAVJobSecurity@@@Z; JobStore::RegJobSecurityQuery(ushort const *,JobSecurity &)
0x1800205e1  mov     ebx, eax
0x1800205e3  test    eax, eax
0x1800205e5  js      short loc_18002065F
0x1800205e7  mov     r10, [rbp+47h+var_70]
0x1800205eb  xor     ebx, ebx
0x1800205ed  mov     [rbp+47h+var_60.GenericRead], 120089h
0x1800205f4  mov     [rbp+47h+var_60.GenericWrite], 120116h
0x1800205fb  mov     [rbp+47h+var_60.GenericExecute], 1200A0h
0x180020602  mov     [rbp+47h+var_60.GenericAll], 1F01FFh
0x180020609  lea     rax, [rbp+47h+var_60]
0x18002060d  mov     [rsp+0C0h+GenericMapping], rax; GenericMapping
0x180020612  mov     [rsp+0C0h+Token], r13; Token
0x180020617  mov     [rsp+0C0h+AutoInheritFlags], 3; AutoInheritFlags
0x18002061f  mov     [rsp+0C0h+IsDirectoryObject], r12b; IsDirectoryObject
0x180020624  xor     r9d, r9d; ObjectType
0x180020627  mov     r8, r14; NewDescriptor
0x18002062a  mov     rdx, [rbp+47h+SecurityDescriptor]; CreatorDescriptor
0x18002062e  mov     rcx, r10; ParentDescriptor
0x180020631  call    cs:__imp_RtlNewSecurityObjectEx
0x180020638  nop     dword ptr [rax+rax+00h]
0x18002063d  test    eax, eax
0x18002063f  jns     short loc_18002064C
0x180020641  or      eax, 10000000h
0x180020646  jge     short loc_18002065F
0x180020648  mov     ebx, eax
0x18002064a  jmp     short loc_18002065F
0x18002064c  mov     rcx, [r14]; SecurityDescriptor
0x18002064f  call    cs:__imp_RtlLengthSecurityDescriptor
0x180020656  nop     dword ptr [rax+rax+00h]
0x18002065b  mov     [r14+8], eax
0x18002065f  lea     rcx, [rbp+47h+var_70]
0x180020663  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180020668  nop
0x180020669  lea     rcx, [rbp+47h+SecurityDescriptor]
0x18002066d  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180020672  mov     eax, ebx
0x180020674  mov     rcx, [rbp+47h+var_50]
0x180020678  xor     rcx, rsp; StackCookie
0x18002067b  call    __security_check_cookie
0x180020680  add     rsp, 88h
0x180020687  pop     r15
0x180020689  pop     r14
0x18002068b  pop     r13
0x18002068d  pop     r12
0x18002068f  pop     rdi
0x180020690  pop     rsi
0x180020691  pop     rbx
0x180020692  pop     rbp
0x180020693  retn
```
