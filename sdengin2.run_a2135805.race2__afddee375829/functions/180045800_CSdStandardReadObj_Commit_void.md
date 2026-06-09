# CSdStandardReadObj::Commit(void)

- ea: `0x180045800`
- end: `0x1800459c4`
- name: `?Commit@CSdStandardReadObj@@UEAAJXZ`
- size: `452`
- prototype: `__int64 __fastcall(CSdStandardReadObj *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180045800`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180093698`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x180045962`
- `ntdll!NtSetInformationFile` at `0x180045962`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800458f5`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800458f5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800458ac`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800458ac`

## string_xrefs

- `0x18004582f`: `CSdStandardReadObj::Commit`

## pseudocode

```c
__int64 __fastcall CSdStandardReadObj::Commit(CSdStandardReadObj *this)
{
  __int16 v2; // ax
  void *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  WINBOOL bDaclPresent; // [rsp+30h] [rbp-39h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+34h] [rbp-35h] BYREF
  int LastFailureAsHRESULT; // [rsp+38h] [rbp-31h] BYREF
  __int16 v12; // [rsp+3Ch] [rbp-2Dh]
  __int16 v13; // [rsp+3Eh] [rbp-2Bh]
  PACL pDacl; // [rsp+70h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp+Fh] BYREF
  _BYTE FileInformation[36]; // [rsp+88h] [rbp+1Fh] BYREF
  int v17; // [rsp+ACh] [rbp+43h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdStandardReadObj::Commit",
    0x187u,
    1u);
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  IoStatusBlock = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v17 = 0;
  if ( ((*((_QWORD *)this + 5) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = 0;
    v2 = 401;
LABEL_13:
    v12 = v2;
    goto LABEL_14;
  }
  v3 = (void *)*((_QWORD *)this + 7);
  if ( v3 )
  {
    if ( !GetSecurityDescriptorDacl(v3, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v4);
      v2 = 406;
      goto LABEL_6;
    }
    LastFailureAsHRESULT = 0;
    v12 = 406;
    if ( bDaclPresent )
    {
      if ( !SetKernelObjectSecurity(*((HANDLE *)this + 5), 4u, *((PSECURITY_DESCRIPTOR *)this + 7)) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v5);
        v2 = 410;
        goto LABEL_6;
      }
      LastFailureAsHRESULT = 0;
      v12 = 410;
    }
  }
  if ( !*((_DWORD *)this + 16) )
    goto LABEL_14;
  *(_QWORD *)FileInformation = *((_QWORD *)this + 9);
  *(_QWORD *)&FileInformation[8] = *((_QWORD *)this + 10);
  *(_QWORD *)&FileInformation[16] = *((_QWORD *)this + 11);
  *(_DWORD *)&FileInformation[32] = *((_DWORD *)this + 24);
  v6 = NtSetInformationFile(*((HANDLE *)this + 5), &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v6);
  v2 = 420;
  if ( LastFailureAsHRESULT >= 0 )
    goto LABEL_13;
LABEL_6:
  v13 = v2;
LABEL_14:
  (*(void (__fastcall **)(CSdStandardReadObj *))(*(_QWORD *)this + 72LL))(this);
  v7 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v7;
}

```

## disassembly

```asm
0x180045800  mov     [rsp-8+arg_8], rbx
0x180045805  push    rbp
0x180045806  lea     rbp, [rsp-57h]
0x18004580b  sub     rsp, 0C0h
0x180045812  mov     rax, cs:__security_cookie
0x180045819  xor     rax, rsp
0x18004581c  mov     [rbp+57h+var_10], rax
0x180045820  mov     rbx, rcx
0x180045823  mov     r9d, 1; unsigned __int16
0x180045829  mov     r8d, 187h; unsigned __int16
0x18004582f  lea     rdx, aCsdstandardrea_12; "CSdStandardReadObj::Commit"
0x180045836  lea     rcx, [rbp+57h+var_88]; this
0x18004583a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004583f  mov     [rbp+57h+pDacl], 0
0x180045847  mov     [rbp+57h+bDaclPresent], 0
0x18004584e  mov     [rbp+57h+bDaclDefaulted], 0
0x180045855  xorps   xmm0, xmm0
0x180045858  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18004585c  mov     dword ptr [rbp+57h+FileInformation], 0
0x180045863  xorps   xmm1, xmm1
0x180045866  xor     eax, eax
0x180045868  movups  xmmword ptr [rbp+57h+FileInformation+4], xmm1
0x18004586c  movups  [rbp+57h+var_24], xmm1
0x180045870  mov     [rbp+57h+var_14], eax
0x180045873  mov     rax, [rbx+28h]
0x180045877  inc     rax
0x18004587a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180045880  jnz     short loc_180045893
0x180045882  mov     [rbp+57h+var_88], 0
0x180045889  mov     eax, 191h
0x18004588e  jmp     loc_180045985
0x180045893  mov     rcx, [rbx+38h]; pSecurityDescriptor
0x180045897  test    rcx, rcx
0x18004589a  jz      loc_180045924
0x1800458a0  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x1800458a4  lea     r8, [rbp+57h+pDacl]; pDacl
0x1800458a8  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x1800458ac  call    cs:__imp_GetSecurityDescriptorDacl
0x1800458b3  nop     dword ptr [rax+rax+00h]
0x1800458b8  test    eax, eax
0x1800458ba  jnz     short loc_1800458D2
0x1800458bc  call    GetLastFailureAsHRESULT
0x1800458c1  mov     [rbp+57h+var_88], eax
0x1800458c4  mov     eax, 196h
0x1800458c9  mov     [rbp+57h+var_82], ax
0x1800458cd  jmp     loc_180045989
0x1800458d2  mov     [rbp+57h+var_88], 0
0x1800458d9  mov     eax, 196h
0x1800458de  mov     [rbp+57h+var_84], ax
0x1800458e2  cmp     [rbp+57h+bDaclPresent], 0
0x1800458e6  jz      short loc_180045924
0x1800458e8  mov     r8, [rbx+38h]; SecurityDescriptor
0x1800458ec  mov     edx, 4; SecurityInformation
0x1800458f1  mov     rcx, [rbx+28h]; Handle
0x1800458f5  call    cs:__imp_SetKernelObjectSecurity
0x1800458fc  nop     dword ptr [rax+rax+00h]
0x180045901  test    eax, eax
0x180045903  jnz     short loc_180045914
0x180045905  call    GetLastFailureAsHRESULT
0x18004590a  mov     [rbp+57h+var_88], eax
0x18004590d  mov     eax, 19Ah
0x180045912  jmp     short loc_1800458C9
0x180045914  mov     [rbp+57h+var_88], 0
0x18004591b  mov     eax, 19Ah
0x180045920  mov     [rbp+57h+var_84], ax
0x180045924  cmp     dword ptr [rbx+40h], 0
0x180045928  jz      short loc_180045989
0x18004592a  mov     rax, [rbx+48h]
0x18004592e  mov     [rbp+57h+FileInformation], rax
0x180045932  mov     rax, [rbx+50h]
0x180045936  mov     [rbp+57h+var_30], rax
0x18004593a  mov     rax, [rbx+58h]
0x18004593e  mov     [rbp+2Fh], rax
0x180045942  mov     eax, [rbx+60h]
0x180045945  mov     dword ptr [rbp+57h+var_24+0Ch], eax
0x180045948  mov     [rsp+0C0h+FileInformationClass], 4; FileInformationClass
0x180045950  mov     r9d, 28h ; '('; Length
0x180045956  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18004595a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18004595e  mov     rcx, [rbx+28h]; FileHandle
0x180045962  call    cs:__imp_NtSetInformationFile
0x180045969  nop     dword ptr [rax+rax+00h]
0x18004596e  mov     ecx, eax
0x180045970  call    HRESULTFromNTSTATUS
0x180045975  mov     [rbp+57h+var_88], eax
0x180045978  test    eax, eax
0x18004597a  mov     eax, 1A4h
0x18004597f  js      loc_1800458C9
0x180045985  mov     [rbp+57h+var_84], ax
0x180045989  mov     rax, [rbx]
0x18004598c  mov     rcx, rbx
0x18004598f  mov     rax, [rax+48h]
0x180045993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045998  mov     ebx, [rbp+57h+var_88]
0x18004599b  lea     rcx, [rbp+57h+var_88]; this
0x18004599f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800459a4  mov     eax, ebx
0x1800459a6  mov     rcx, [rbp+57h+var_10]
0x1800459aa  xor     rcx, rsp; StackCookie
0x1800459ad  call    __security_check_cookie
0x1800459b2  mov     rbx, [rsp+0C0h+arg_8]
0x1800459ba  add     rsp, 0C0h
0x1800459c1  pop     rbp
0x1800459c2  retn
```
