# UmpoInternalAccessCheck

- ea: `0x1800037b0`
- end: `0x1800039f0`
- name: `UmpoInternalAccessCheck`
- size: `576`
- prototype: `__int64 __fastcall(__int64, __int64, void *, DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800036f0`
- `0x180004830`

## callees

- `0x1800037b0`
- `0x180003a00`
- `0x18000f3dc`
- `0x180010070`
- `0x180019010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000383c`
- `ntdll!RtlAllocateHeap` at `0x18000383c`
- `ntdll!RtlFreeHeap` at `0x180003922`
- `ntdll!RtlFreeHeap` at `0x180003922`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800038d5`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800038d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ab`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003878`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800039ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003878`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800039ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003907`

## pseudocode

```c
__int64 __fastcall UmpoInternalAccessCheck(__int64 a1, __int64 a2, void *a3, DWORD a4)
{
  WCHAR *v6; // rdi
  unsigned int v8; // esi
  DWORD LastError; // ebx
  WCHAR *Heap; // rax
  SIZE_T Size; // [rsp+40h] [rbp-49h] BYREF
  WINBOOL AccessStatus; // [rsp+48h] [rbp-41h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-39h] BYREF
  DWORD GrantedAccess; // [rsp+58h] [rbp-31h] BYREF
  int v16; // [rsp+5Ch] [rbp-2Dh] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp-29h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp-19h] BYREF
  __int128 v19; // [rsp+88h] [rbp-1h] BYREF

  GrantedAccess = 0;
  v16 = 0;
  AccessStatus = 0;
  SecurityDescriptor = 0;
  v19 = 0;
  v6 = 0;
  Size = 0;
  GenericMapping = 0;
  v8 = a1;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  LastError = UmpoReadSecurityDescriptor(a1, a2, 0, &Size);
  if ( LastError == 234 )
  {
    Heap = (WCHAR *)RtlAllocateHeap(UmpoHeapHandle, 8u, (unsigned int)Size);
    v6 = Heap;
    if ( !Heap )
    {
      LastError = 14;
      goto LABEL_10;
    }
    LastError = UmpoReadSecurityDescriptor(v8, a2, Heap, &Size);
  }
  if ( !LastError )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v6, 1u, &SecurityDescriptor, 0) )
      goto LABEL_6;
    if ( GetLastError() == 87 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"O:BAG:SYD:P(A;CI;KRKW;;;BU)(A;CI;KA;;;BA)(A;CI;KA;;;SY)(A;CI;KA;;;CO)(A;CI;KR;;;AC)(A;CI;KR;;;S-1-15-3-1024-1"
            "502825166-1963708345-2616377461-2562897074-4192028372-3968301570-1997628692-1435953622)",
           1u,
           &SecurityDescriptor,
           0) )
    {
LABEL_6:
      GenericMapping.GenericRead = 131097;
      *(_QWORD *)&GenericMapping.GenericWrite = 131078;
      GenericMapping.GenericAll = 131103;
      HIDWORD(Size) = 20;
      if ( AccessCheck(
             SecurityDescriptor,
             a3,
             a4,
             &GenericMapping,
             &PrivilegeSet,
             (LPDWORD)&Size + 1,
             &GrantedAccess,
             &AccessStatus) )
      {
        if ( AccessStatus )
        {
          LastError = 0;
          if ( v8 < 2 )
          {
            if ( qword_1800246B0 && !(unsigned int)qword_1800246B0(a2, v8, &v16) )
              LastError = 1260;
          }
          else if ( v8 == 19 && qword_1800246A8 && !(unsigned int)qword_1800246A8(&v19) )
          {
            LastError = 1260;
          }
        }
        else
        {
          LastError = 5;
        }
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = 5;
    }
  }
LABEL_10:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  if ( v6 )
    RtlFreeHeap(UmpoHeapHandle, 0, v6);
  return LastError;
}

```

## disassembly

```asm
0x1800037b0  push    rbp
0x1800037b2  push    rbx
0x1800037b3  push    rsi
0x1800037b4  push    rdi
0x1800037b5  push    r12
0x1800037b7  push    r13
0x1800037b9  push    r14
0x1800037bb  push    r15
0x1800037bd  lea     rbp, [rsp-1Fh]
0x1800037c2  sub     rsp, 0A8h
0x1800037c9  mov     rax, cs:__security_cookie
0x1800037d0  xor     rax, rsp
0x1800037d3  mov     [rbp+57h+var_48], rax
0x1800037d7  xor     r13d, r13d
0x1800037da  xorps   xmm0, xmm0
0x1800037dd  mov     r12d, r9d
0x1800037e0  mov     [rbp+57h+var_88], r13d
0x1800037e4  mov     r15, r8
0x1800037e7  mov     dword ptr [rbp+57h+Size+4], r13d
0x1800037eb  xorps   xmm1, xmm1
0x1800037ee  mov     [rbp+57h+var_84], r13d
0x1800037f2  xor     eax, eax
0x1800037f4  mov     [rbp+57h+var_98], r13d
0x1800037f8  lea     r9, [rbp+57h+Size]
0x1800037fc  mov     [rbp+57h+var_70.Privilege.Attributes], eax
0x1800037ff  xor     r8d, r8d
0x180003802  mov     [rbp+57h+SecurityDescriptor], r13
0x180003806  movups  [rbp+57h+var_58], xmm0
0x18000380a  mov     edi, r13d
0x18000380d  mov     dword ptr [rbp+57h+Size], r13d
0x180003811  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm1
0x180003815  mov     r14, rdx
0x180003818  mov     esi, ecx
0x18000381a  movups  xmmword ptr [rbp+57h+var_70.PrivilegeCount], xmm0
0x18000381e  call    UmpoReadSecurityDescriptor
0x180003823  mov     ebx, eax
0x180003825  cmp     eax, 0EAh
0x18000382a  jnz     short loc_180003861
0x18000382c  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180003830  mov     edx, 8; Flags
0x180003835  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x18000383c  call    cs:__imp_RtlAllocateHeap
0x180003842  mov     rdi, rax
0x180003845  test    rax, rax
0x180003848  jz      loc_1800039A1
0x18000384e  lea     r9, [rbp+57h+Size]
0x180003852  mov     r8, rax
0x180003855  mov     rdx, r14
0x180003858  mov     ecx, esi
0x18000385a  call    UmpoReadSecurityDescriptor
0x18000385f  mov     ebx, eax
0x180003861  test    ebx, ebx
0x180003863  jnz     loc_1800038FE
0x180003869  xor     r9d, r9d; SecurityDescriptorSize
0x18000386c  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180003870  mov     edx, 1; StringSDRevision
0x180003875  mov     rcx, rdi; StringSecurityDescriptor
0x180003878  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000387e  test    eax, eax
0x180003880  jz      loc_1800039AB
0x180003886  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18000388a  lea     rax, [rbp+57h+var_98]
0x18000388e  mov     [rsp+0E0h+AccessStatus], rax; AccessStatus
0x180003893  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180003897  lea     rax, [rbp+57h+var_88]
0x18000389b  mov     [rbp+57h+GenericMapping.GenericRead], 20019h
0x1800038a2  mov     [rsp+0E0h+GrantedAccess], rax; GrantedAccess
0x1800038a7  mov     r8d, r12d; DesiredAccess
0x1800038aa  lea     rax, [rbp+57h+Size+4]
0x1800038ae  mov     qword ptr [rbp+57h+GenericMapping.GenericWrite], 20006h
0x1800038b6  mov     [rsp+0E0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800038bb  mov     rdx, r15; ClientToken
0x1800038be  lea     rax, [rbp+57h+var_70]
0x1800038c2  mov     [rbp+57h+GenericMapping.GenericAll], 2001Fh
0x1800038c9  mov     [rsp+0E0h+PrivilegeSet], rax; PrivilegeSet
0x1800038ce  mov     dword ptr [rbp+57h+Size+4], 14h
0x1800038d5  call    cs:__imp_AccessCheck
0x1800038db  test    eax, eax
0x1800038dd  jz      loc_180003994
0x1800038e3  cmp     [rbp+57h+var_98], r13d
0x1800038e7  jz      loc_1800039E6
0x1800038ed  mov     ebx, r13d
0x1800038f0  cmp     esi, 1
0x1800038f3  jz      short loc_18000394A
0x1800038f5  test    esi, esi
0x1800038f7  jz      short loc_18000394A
0x1800038f9  cmp     esi, 13h
0x1800038fc  jz      short loc_180003970
0x1800038fe  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180003902  test    rcx, rcx
0x180003905  jz      short loc_180003911
0x180003907  call    cs:__imp_LocalFree
0x18000390d  mov     [rbp+57h+SecurityDescriptor], r13
0x180003911  test    rdi, rdi
0x180003914  jz      short loc_180003928
0x180003916  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x18000391d  mov     r8, rdi; P
0x180003920  xor     edx, edx; Flags
0x180003922  call    cs:__imp_RtlFreeHeap
0x180003928  mov     eax, ebx
0x18000392a  mov     rcx, [rbp+57h+var_48]
0x18000392e  xor     rcx, rsp; StackCookie
0x180003931  call    __security_check_cookie
0x180003936  add     rsp, 0A8h
0x18000393d  pop     r15
0x18000393f  pop     r14
0x180003941  pop     r13
0x180003943  pop     r12
0x180003945  pop     rdi
0x180003946  pop     rsi
0x180003947  pop     rbx
0x180003948  pop     rbp
0x180003949  retn
0x18000394a  mov     rax, cs:qword_1800246B0
0x180003951  test    rax, rax
0x180003954  jz      short loc_1800038FE
0x180003956  lea     r8, [rbp+57h+var_84]
0x18000395a  mov     edx, esi
0x18000395c  mov     rcx, r14
0x18000395f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003964  test    eax, eax
0x180003966  mov     ecx, 4ECh
0x18000396b  cmovz   ebx, ecx
0x18000396e  jmp     short loc_1800038FE
0x180003970  mov     rax, cs:qword_1800246A8
0x180003977  test    rax, rax
0x18000397a  jz      short loc_1800038FE
0x18000397c  lea     rcx, [rbp+57h+var_58]
0x180003980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003985  test    eax, eax
0x180003987  mov     ecx, 4ECh
0x18000398c  cmovz   ebx, ecx
0x18000398f  jmp     loc_1800038FE
0x180003994  call    cs:__imp_GetLastError
0x18000399a  mov     ebx, eax
0x18000399c  jmp     loc_1800038FE
0x1800039a1  mov     ebx, 0Eh
0x1800039a6  jmp     loc_1800038FE
0x1800039ab  call    cs:__imp_GetLastError
0x1800039b1  cmp     eax, 57h ; 'W'
0x1800039b4  jnz     short loc_1800039BB
0x1800039b6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800039bb  xor     r9d, r9d; SecurityDescriptorSize
0x1800039be  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800039c2  mov     edx, 1; StringSDRevision
0x1800039c7  lea     rcx, StringSecurityDescriptor; "O:BAG:SYD:P(A;CI;KRKW;;;BU)(A;CI;KA;;;B"...
0x1800039ce  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800039d4  test    eax, eax
0x1800039d6  jnz     loc_180003886
0x1800039dc  mov     ebx, 5
0x1800039e1  jmp     loc_1800038FE
0x1800039e6  mov     ebx, 5
0x1800039eb  jmp     loc_1800038FE
```
