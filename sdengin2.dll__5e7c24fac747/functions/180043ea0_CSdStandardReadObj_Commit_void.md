# CSdStandardReadObj::Commit(void)

- ea: `0x180043ea0`
- end: `0x18004404d`
- name: `?Commit@CSdStandardReadObj@@UEAAJXZ`
- size: `429`
- prototype: `__int64 __fastcall(CSdStandardReadObj *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180043ea0`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18008f660`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x180043ff2`
- `ntdll!NtSetInformationFile` at `0x180043ff2`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180043f8b`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180043f8b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180043f48`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180043f48`

## string_xrefs

- `0x180043ecf`: `CSdStandardReadObj::Commit`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "CSdStandardReadObj::Commit", 391, 1);
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
0x180043ea0  mov     [rsp-8+arg_8], rbx
0x180043ea5  push    rbp
0x180043ea6  lea     rbp, [rsp-57h]
0x180043eab  sub     rsp, 0C0h
0x180043eb2  mov     rax, cs:__security_cookie
0x180043eb9  xor     rax, rsp
0x180043ebc  mov     [rbp+57h+var_10], rax
0x180043ec0  mov     rbx, rcx
0x180043ec3  mov     r9d, 1; unsigned __int16
0x180043ec9  mov     r8d, 187h; unsigned __int16
0x180043ecf  lea     rdx, aCsdstandardrea_12; "CSdStandardReadObj::Commit"
0x180043ed6  lea     rcx, [rbp+57h+var_88]; this
0x180043eda  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180043edf  mov     [rbp+57h+pDacl], 0
0x180043ee7  mov     [rbp+57h+bDaclPresent], 0
0x180043eee  mov     [rbp+57h+bDaclDefaulted], 0
0x180043ef5  xorps   xmm0, xmm0
0x180043ef8  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180043efc  mov     dword ptr [rbp+57h+FileInformation], 0
0x180043f03  xorps   xmm1, xmm1
0x180043f06  xor     eax, eax
0x180043f08  movups  xmmword ptr [rbp+57h+FileInformation+4], xmm1
0x180043f0c  movups  [rbp+57h+var_24], xmm1
0x180043f10  mov     [rbp+57h+var_14], eax
0x180043f13  mov     rax, [rbx+28h]
0x180043f17  inc     rax
0x180043f1a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180043f20  jnz     short loc_180043F33
0x180043f22  mov     [rbp+57h+var_88], 0
0x180043f29  mov     eax, 191h
0x180043f2e  jmp     loc_18004400F
0x180043f33  mov     rcx, [rbx+38h]; pSecurityDescriptor
0x180043f37  test    rcx, rcx
0x180043f3a  jz      short loc_180043FB4
0x180043f3c  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180043f40  lea     r8, [rbp+57h+pDacl]; pDacl
0x180043f44  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180043f48  call    cs:__imp_GetSecurityDescriptorDacl
0x180043f4e  test    eax, eax
0x180043f50  jnz     short loc_180043F68
0x180043f52  call    GetLastFailureAsHRESULT
0x180043f57  mov     [rbp+57h+var_88], eax
0x180043f5a  mov     eax, 196h
0x180043f5f  mov     [rbp+57h+var_82], ax
0x180043f63  jmp     loc_180044013
0x180043f68  mov     [rbp+57h+var_88], 0
0x180043f6f  mov     eax, 196h
0x180043f74  mov     [rbp+57h+var_84], ax
0x180043f78  cmp     [rbp+57h+bDaclPresent], 0
0x180043f7c  jz      short loc_180043FB4
0x180043f7e  mov     r8, [rbx+38h]; SecurityDescriptor
0x180043f82  mov     edx, 4; SecurityInformation
0x180043f87  mov     rcx, [rbx+28h]; Handle
0x180043f8b  call    cs:__imp_SetKernelObjectSecurity
0x180043f91  test    eax, eax
0x180043f93  jnz     short loc_180043FA4
0x180043f95  call    GetLastFailureAsHRESULT
0x180043f9a  mov     [rbp+57h+var_88], eax
0x180043f9d  mov     eax, 19Ah
0x180043fa2  jmp     short loc_180043F5F
0x180043fa4  mov     [rbp+57h+var_88], 0
0x180043fab  mov     eax, 19Ah
0x180043fb0  mov     [rbp+57h+var_84], ax
0x180043fb4  cmp     dword ptr [rbx+40h], 0
0x180043fb8  jz      short loc_180044013
0x180043fba  mov     rax, [rbx+48h]
0x180043fbe  mov     [rbp+57h+FileInformation], rax
0x180043fc2  mov     rax, [rbx+50h]
0x180043fc6  mov     [rbp+57h+var_30], rax
0x180043fca  mov     rax, [rbx+58h]
0x180043fce  mov     [rbp+2Fh], rax
0x180043fd2  mov     eax, [rbx+60h]
0x180043fd5  mov     dword ptr [rbp+57h+var_24+0Ch], eax
0x180043fd8  mov     [rsp+0C0h+FileInformationClass], 4; FileInformationClass
0x180043fe0  mov     r9d, 28h ; '('; Length
0x180043fe6  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180043fea  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180043fee  mov     rcx, [rbx+28h]; FileHandle
0x180043ff2  call    cs:__imp_NtSetInformationFile
0x180043ff8  mov     ecx, eax
0x180043ffa  call    HRESULTFromNTSTATUS
0x180043fff  mov     [rbp+57h+var_88], eax
0x180044002  test    eax, eax
0x180044004  mov     eax, 1A4h
0x180044009  js      loc_180043F5F
0x18004400f  mov     [rbp+57h+var_84], ax
0x180044013  mov     rax, [rbx]
0x180044016  mov     rcx, rbx
0x180044019  mov     rax, [rax+48h]
0x18004401d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044022  mov     ebx, [rbp+57h+var_88]
0x180044025  lea     rcx, [rbp+57h+var_88]; this
0x180044029  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004402e  mov     eax, ebx
0x180044030  mov     rcx, [rbp+57h+var_10]
0x180044034  xor     rcx, rsp; StackCookie
0x180044037  call    __security_check_cookie
0x18004403c  mov     rbx, [rsp+0C0h+arg_8]
0x180044044  add     rsp, 0C0h
0x18004404b  pop     rbp
0x18004404c  retn
```
